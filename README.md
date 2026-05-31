# Skamal-Translator
Translate English into Skamal.

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Skämål Translator</title>
    <style>
        :root {
            --primary: #004B87;
            --accent: #FFCD00;
            --bg: #f4f6f9;
            --text: #333333;
            --card-bg: #ffffff;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: var(--bg);
            color: var(--text);
            margin: 0;
            padding: 20px;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
        }

        .container {
            width: 100%;
            max-width: 650px;
            background: var(--card-bg);
            padding: 30px;
            border-radius: 12px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.08);
            border-top: 8px solid var(--primary);
        }

        .header {
            text-align: center;
            margin-bottom: 25px;
        }

        .header h1 {
            margin: 0 0 5px 0;
            color: var(--primary);
            font-size: 28px;
        }

        .header p {
            margin: 0;
            color: #666;
            font-style: italic;
        }

        .form-group {
            margin-bottom: 20px;
        }

        label {
            display: block;
            font-weight: bold;
            margin-bottom: 8px;
            color: var(--primary);
        }

        textarea {
            width: 100%;
            height: 100px;
            padding: 12px;
            border: 2px solid #ddd;
            border-radius: 8px;
            font-size: 16px;
            resize: vertical;
            box-sizing: border-box;
            transition: border-color 0.2s;
        }

        textarea:focus {
            outline: none;
            border-color: var(--primary);
        }

        .output-box {
            width: 100%;
            min-height: 100px;
            background-color: #f8f9fa;
            border: 2px dashed var(--primary);
            border-radius: 8px;
            padding: 12px;
            font-size: 16px;
            box-sizing: border-box;
            white-space: pre-wrap;
        }
    </style>
</head>
<body>

<div class="container">
    <div class="header">
        <h1>🇸🇪 Skämål Translator 🇸🇪</h1>
        <p>Official Dialect Engine</p>
    </div>

    <div class="form-group">
        <label for="englishInput">English Input</label>
        <textarea id="englishInput" placeholder="Type an English sentence here... (e.g., Hello, my name is Skee.)"></textarea>
    </div>

    <div class="form-group">
        <label>Skämål Output</label>
        <div id="skamalOutput" class="output-box"></div>
    </div>
</div>

<script>
    // --- PROTECTED VOCABULARY DATA ---
    const FIXED_WORDS = {
        "who": "hå", "what": "vät", "when": "vëhn", "where": "vär", "why": "vï", "how": "hët",
        "police": "polis", "officer": "onstapel",
        "hello": "hejsan", "welcome": "valkomma", "thank you": "väa", "goodbye": "väo",
        "name": "ämne", // Fixed custom override with ä
        "is": "ös", "are": "ös", "yes": "vïste", "language": "vïste", 
        "dialect": "vïste", "text": "vïste", "no": "vïsto",
        "i": "jäg", "you": "dö", "he": "hän", "she": "hän", "it": "dat", "we": "vö", "they": "då"
    };

    const POSSESSIVE_PRONOUNS = {
        "my": "jän-", "your": "dön-", "his": "häns-", "her": "häns-", "its": "däts-", "our": "vön-", "their": "dån-"
    };

    const CONTRACTIONS = {
        "i'm": "jäg-ös", "you're": "dö-ös", "he's": "hän-ös", "she's": "hän-ös", "it's": "dät-ös", "we're": "vö-ös", "they're": "då-ös"
    };

    const NUMBERS = {
        "1": "än", "2": "dva", "3": "trå", "4": "fjäl", "5": "föm", "6": "sås", "7": "sjå", "8": "ått", "9": "njö", "10": "täl"
    };

    const VOWELS = "aeiouyAEIOUY";

    function translateWord(word, isFirstWord) {
        let cleanWord = word.replace(/[.,!?;:]/g, '');
        let punctuation = word.substring(cleanWord.length);

        if (cleanWord.length === 0) return word;

        // 1. Proper Noun Rule Verification
        // If it starts with a Capital but is NOT the very first word, it is a proper noun.
        const isTitleCase = cleanWord[0] === cleanWord[0].toUpperCase() && cleanWord.substring(1) === cleanWord.substring(1).toLowerCase();
        const isAllCaps = cleanWord === cleanWord.toUpperCase() && cleanWord.length > 1;
        
        if ((isTitleCase || isAllCaps) && !isFirstWord) {
            return word; // Keep completely unchanged (Proper Noun exemption)
        }

        let lowerWord = cleanWord.toLowerCase();

        // 2. Check Protected Lists
        if (CONTRACTIONS[lowerWord]) return CONTRACTIONS[lowerWord] + punctuation;
        if (POSSESSIVE_PRONOUNS[lowerWord]) return POSSESSIVE_PRONOUNS[lowerWord] + punctuation;
        if (FIXED_WORDS[lowerWord]) {
            let trans = FIXED_WORDS[lowerWord];
            if (isFirstWord) trans = trans.charAt(0).toUpperCase() + trans.slice(1);
            return trans + punctuation;
        }
        if (NUMBERS[lowerWord]) return NUMBERS[lowerWord] + punctuation;

        // --- SECTION 1: MECHANICAL ENGINE ---
        const hasSuffix = lowerWord.endsWith('ing') || lowerWord.endsWith('ed') || lowerWord.endsWith('es') || (lowerWord.endsWith('s') && !lowerWord.endsWith('ss'));

        // Strip Suffixes
        if (lowerWord.endsWith('ing')) lowerWord = lowerWord.slice(0, -3);
        else if (lowerWord.endsWith('ed')) lowerWord = lowerWord.slice(0, -2);
        else if (lowerWord.endsWith('es')) lowerWord = lowerWord.slice(0, -2);
        else if (lowerWord.endsWith('s') && !lowerWord.endsWith('ss')) lowerWord = lowerWord.slice(0, -1);

        // Compress double letters + switch vowel compress to accents
        let compressed = "";
        let i = 0;
        while (i < lowerWord.length) {
            if (i < lowerWord.length - 1 && lowerWord[i] === lowerWord[i+1]) {
                let char = lowerWord[i];
                if ("aeiou".includes(char)) {
                    compressed += "ae".includes(char) ? 'ä' : 'ö';
                } else {
                    compressed += char;
                }
                i += 2;
            } else {
                compressed += lowerWord[i];
                i += 1;
            }
        }
        lowerWord = compressed;

        if (!lowerWord) return word;

        // Vowel Placeholder Prefix (Forces lowercase add)
        if (VOWELS.includes(lowerWord[0])) {
            lowerWord = (hasSuffix ? 'j' : 't') + lowerWord;
        }

        // Shift First Letter to End as lowercase
        let firstLetter = lowerWord[0].toLowerCase();
        let shiftedWord = lowerWord.slice(1) + firstLetter;

        // The "W" Drop Rule
        if (shiftedWord.endsWith('w')) {
            shiftedWord = shiftedWord.slice(0, -1);
        }

        // Slide Accents to Inner Vowels & No Y Rule
        let chars = shiftedWord.split('');
        for (let idx = 1; idx < chars.length; idx++) {
            let c = chars[idx];
            if (c === 'o') chars[idx] = 'å';
            else if (c === 'a' || c === 'e') chars[idx] = 'ä';
            else if (c === 'u' || c === 'i') chars[idx] = 'ö';
            else if (c === 'y') chars[idx] = 'e';
        }

        let finalWord = chars.join('');
        if (isFirstWord) {
            finalWord = finalWord.charAt(0).toUpperCase() + finalWord.slice(1);
        }

        return finalWord + punctuation;
    }

    function translateSentence(sentence) {
        // Clear out banned apostrophes completely
        sentence = sentence.replace(/'/g, "");
        let words = sentence.trim().split(/\s+/);
        if (words.length === 0 || words[0] === "") return "";

        let translatedWords = [];
        let isQuestion = sentence.trim().endsWith("?");

        if (isQuestion) {
            translatedWords.push("Må");
        }

        for (let i = 0; i < words.length; i++) {
            let isFirst = (i === 0);
            translatedWords.push(translateWord(words[i], isFirst));
        }

        return translatedWords.join(" ");
    }

    // Interactive Input Event Listener
    const inputArea = document.getElementById('englishInput');
    const outputArea = document.getElementById('skamalOutput');

    inputArea.addEventListener('input', (e) => {
        const text = e.target.value;
        if(text.trim() === "") {
            outputArea.innerText = "";
        } else {
            outputArea.innerText = translateSentence(text);
        }
    });
</script>

</body>
</html>
