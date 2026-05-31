
Translate English to Skämål

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>English to Skämål Translator</title>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            margin: 40px auto;
            max-width: 800px;
            padding: 0 20px;
            color: #333;
            background-color: #f4f6f9;
        }
        h1 {
            color: #1a1a1a;
            border-bottom: 3px solid #0056b3;
            padding-bottom: 12px;
            font-size: 32px;
            text-align: center;
        }
        .translator-container {
            background: #fff;
            border: 1px solid #e1e4e8;
            padding: 30px;
            border-radius: 12px;
            margin-bottom: 30px;
            box-shadow: 0 4px 12px rgba(0,0,0,0.05);
        }
        .form-group {
            margin-bottom: 20px;
        }
        label {
            display: block;
            font-weight: bold;
            margin-bottom: 8px;
            color: #495057;
            font-size: 14px;
            text-transform: uppercase;
            letter-spacing: 0.5px;
        }
        textarea {
            width: 100%;
            height: 120px;
            padding: 12px;
            border: 2px solid #ced4da;
            border-radius: 6px;
            box-sizing: border-box;
            font-size: 16px;
            resize: vertical;
            transition: border-color 0.2s;
        }
        textarea:focus {
            outline: none;
            border-color: #0056b3;
        }
        .output-textarea {
            background-color: #f8f9fa;
            color: #111;
            font-weight: 600;
            border-color: #dee2e6;
            cursor: default;
        }
        .status-badge {
            display: inline-block;
            font-size: 11px;
            background-color: #0056b3;
            color: white;
            padding: 3px 8px;
            border-radius: 50px;
            margin-bottom: 10px;
            font-weight: bold;
            text-transform: uppercase;
            letter-spacing: 0.5px;
        }
        details {
            background: #fff;
            padding: 20px;
            border-radius: 8px;
            border: 1px solid #e1e4e8;
            cursor: pointer;
        }
        summary {
            font-weight: bold;
            font-size: 16px;
            color: #0056b3;
        }
        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 15px;
        }
        th, td {
            border: 1px solid #dee2e6;
            padding: 10px;
            text-align: left;
            font-size: 14px;
        }
        th {
            background-color: #f1f3f5;
            color: #495057;
        }
    </style>
</head>
<body>

    <h1>English to Skämål Translator</h1>

    <div class="translator-container">
        <div class="form-group">
            <label for="englishInput">English Source Text:</label>
            <textarea id="englishInput" placeholder="Start typing your English text here..."></textarea>
        </div>
        
        <div class="form-group" style="margin-top: 25px;">
            <span class="status-badge">Live Full Mechanical Translation Engine</span>
            <label for="skamalOutput">Skämål Target Translation:</label>
            <textarea id="skamalOutput" class="output-textarea" readonly placeholder="Skämål translation will appear here automatically..."></textarea>
        </div>
    </div>

    <details>
        <summary>View Core Language Vocabulary & Rules Matrix</summary>
        <div style="cursor: default; margin-top: 15px;">
            <h3>Protected Dictionary Reference</h3>
            <table>
                <thead>
                    <tr><th>English</th><th>Skämål</th><th>English</th><th>Skämål</th></tr>
                </thead>
                <tbody>
                    <tr><td>I</td><td>Jäg</td><td>Hello</td><td>Hejsan</td></tr>
                    <tr><td>You</td><td>Dö</td><td>Welcome</td><td>Valkomma</td></tr>
                    <tr><td>He/She</td><td>Hän</td><td>Thank you</td><td>Väa</td></tr>
                    <tr><td>It</td><td>Dät</td><td>Goodbye</td><td>Väo</td></tr>
                    <tr><td>We</td><td>Vö</td><td>Yes</td><td>Vïste</td></tr>
                    <tr><td>They</td><td>Då</td><td>No</td><td>Vïsto</td></tr>
                    <tr><td>My</td><td>Jän- [Noun]</td><td>Name</td><td>nåmn</td></tr>
                    <tr><td>Language/Dialect</td><td>språkå</td><td>Text</td><td>båkkt</td></tr>
                    <tr><td>Police</td><td>vakt</td><td>Officer</td><td>onstapel</td></tr>
                    <tr><td>City</td><td>stadä</td><td>Friend</td><td>sjelårad</td></tr>
                    <tr><td>Coffee</td><td>Kafe</td><td>Water</td><td>vatnå</td></tr>
                    <tr><td>Hot</td><td>skolå</td><td>Beautiful</td><td>skönå</td></tr>
                </tbody>
            </table>
        </div>
    </details>

    <script>
        const dictionary = {
            "hello": "Hejsan", "welcome": "Valkomma", "thank": "Väa", "thankyou": "Väa",
            "goodbye": "Väo", "yes": "Vïste", "no": "Vïsto", "language": "språkå", "dialect": "språkå", 
            "text": "båkkt", "name": "nåmn", "person": "sjelå", "friend": "sjelårad", "police": "vakt", 
            "officer": "onstapel", "city": "stadä", "house": "garda", "tree": "stalmå", "coffee": "Kafe", 
            "water": "vatnå", "like": "lyskå", "likes": "lyskå", "am": "är", "is": "ös", "are": "ös", 
            "hot": "skolå", "warm": "skolå", "boiling": "skolå", "cold": "kjölå", "freezing": "kjölå", 
            "beautiful": "skönå", "a": "vå", "the": "hät", "to": "åt", "who": "Hå", "what": "Vät", 
            "when": "Vëhn", "where": "Vär", "why": "Vï", "how": "Hët", "1": "Än", "2": "Dva", 
            "3": "Trå", "4": "Fjäl", "5": "Föm", "6": "Sås", "7": "Sjå", "8": "Ått", "9": "Njö", "10": "Täl"
        };

        const pronouns = { "i": "Jäg", "you": "Dö", "he": "Hän", "she": "Hän", "it": "Dät", "we": "Vö", "they": "Då" };
        const possessives = { "my": "Jän-", "your": "Dön-", "his": "Häns-", "her": "Häns-", "its": "Däts-", "our": "Vön-", "their": "Dån-" };
        const contractions = { "i'm": "Jäg-ös", "you're": "Dö-ös", "he's": "Hän-ös", "she's": "Hän-ös", "it's": "Dät-ös", "we're": "Vö-ös", "they're": "Då-ös" };
        const adjectives = ["skolå", "kjölå", "skönå"];

        document.getElementById('englishInput').addEventListener('input', translateToSkamal);

        // Core 8-Step Structural Mechanical Shift Rules Engine
        function runMechanicalRules(word) {
            let cleanWord = word;
            let suffix = "";
            
            // Step 1: Isolate suffixes
            if (cleanWord.toLowerCase().endsWith("ing")) { suffix = "ing"; cleanWord = cleanWord.slice(0, -3); }
            else if (cleanWord.toLowerCase().endsWith("ed")) { suffix = "ed"; cleanWord = cleanWord.slice(0, -2); }
            else if (cleanWord.toLowerCase().endsWith("es")) { suffix = "es"; cleanWord = cleanWord.slice(0, -2); }
            else if (cleanWord.toLowerCase().endsWith("s") && !cleanWord.toLowerCase().endsWith("ss")) { suffix = "s"; cleanWord = cleanWord.slice(0, -1); }

            if (cleanWord.length === 0) return word;

            // Step 2: Vowel prefix logic
            let firstLetter = cleanWord.charAt(0);
            let startsWithVowel = /^[aeiouAEIOU]/.test(firstLetter);
            if (startsWithVowel) {
                cleanWord = (suffix === "") ? "T" + cleanWord : "J" + cleanWord;
            }

            // Step 3: Compress twins
            let compressed = "";
            let triggerUmlaut = false;
            for (let i = 0; i < cleanWord.length; i++) {
                if (i < cleanWord.length - 1 && cleanWord[i].toLowerCase() === cleanWord[i+1].toLowerCase()) {
                    if (/[aeiouAEIOU]/.test(cleanWord[i])) triggerUmlaut = true;
                    compressed += cleanWord[i];
                    i++; 
                } else {
                    compressed += cleanWord[i];
                }
            }
            cleanWord = compressed;

            // Step 4: Front letter to tail end
            if (cleanWord.length > 1) {
                let f = cleanWord.charAt(0);
                cleanWord = cleanWord.substring(1) + f;
            }

            // Step 5: The "W" Drop Rule
            if (cleanWord.toLowerCase().endsWith("w")) {
                cleanWord = cleanWord.slice(0, -1);
            }

            // Steps 6, 7 & 8: Vowel Accent Shifting
            let arr = cleanWord.split("");
            for (let i = 0; i < arr.length; i++) {
                let charLower = arr[i].toLowerCase();
                let isVowel = /[aeiouy]/.test(charLower);
                
                if (isVowel) {
                    if (i === 0) {
                        if (charLower === 'y') arr[i] = (arr[i] === 'Y') ? 'I' : 'i';
                        continue;
                    }
                    
                    let isCap = (arr[i] === arr[i].toUpperCase());
                    if (triggerUmlaut) {
                        if (charLower === 'a' || charLower === 'e') arr[i] = isCap ? 'Ä' : 'ä';
                        else if (charLower === 'o' || charLower === 'u') arr[i] = isCap ? 'Ö' : 'ö';
                    } else {
                        if (charLower === 'o') arr[i] = isCap ? 'Å' : 'å';
                        else if (charLower === 'a' || charLower === 'e') arr[i] = isCap ? 'Ä' : 'ä';
                        else if (charLower === 'u' || charLower === 'i') arr[i] = isCap ? 'Ö' : 'ö';
                    }
                    if (charLower === 'y') arr[i] = isCap ? 'I' : 'i';
                }
            }
            return arr.join("");
        }

        function translateToSkamal() {
            let input = document.getElementById("englishInput").value;
            if (!input.trim()) {
                document.getElementById("skamalOutput").value = "";
                return;
            }

            let isQuestion = false;
            let cleanInput = input.trim();
            if (cleanInput.toLowerCase().startsWith("why ") || cleanInput.toLowerCase().startsWith("what ") || cleanInput.toLowerCase().startsWith("where ") || cleanInput.toLowerCase().startsWith("when ") || cleanInput.toLowerCase().startsWith("who ") || cleanInput.toLowerCase().startsWith("how ") || cleanInput.endsWith("?")) {
                isQuestion = true;
            }

            cleanInput = cleanInput.replace(/thank\s+you/gi, "thankyou");

            // Bulletproof sequential splitter tracking both words and formatting gaps
            let tokens = cleanInput.split(/([a-zA-Z0-9'’]+)/g);
            let translatedTokens = [];

            for (let i = 0; i < tokens.length; i++) {
                let token = tokens[i];
                if (!token) continue;
                
                let lowerToken = token.toLowerCase();

                // Pass spaces and punctuation directly through without parsing
                if (!/[a-zA-Z0-9]/.test(token)) {
                    translatedTokens.push({ text: token, isWord: false });
                    continue;
                }

                // Skip proper noun capitalizations
                if (i > 0 && /^[A-Z]/.test(token) && !contractions[lowerToken] && !possessives[lowerToken] && !dictionary[lowerToken]) {
                    translatedTokens.push({ text: token, isWord: true });
                    continue;
                }

                if (contractions[lowerToken]) {
                    translatedTokens.push({ text: contractions[lowerToken], isWord: true });
                    continue;
                }

                // Handle possessives with clean trailing target pairing
                if (possessives[lowerToken]) {
                    let nextWord = "";
                    let nextIdx = i + 1;
                    
                    // Look ahead past spaces to grab the modified noun
                    while (nextIdx < tokens.length && !/[a-zA-Z0-9]/.test(tokens[nextIdx])) {
                        nextIdx++;
                    }
                    
                    if (nextIdx < tokens.length) {
                        let targetedNoun = tokens[nextIdx];
                        let targetedNounLower = targetedNoun.toLowerCase();
                        nextWord = dictionary[targetedNounLower] || pronouns[targetedNounLower] || runMechanicalRules(targetedNoun);
                        
                        // Wipe the original structural noun token location so it doesn't print twice
                        tokens[nextIdx] = ""; 
                    }
                    
                    let combinedResult = nextWord ? possessives[lowerToken] + nextWord.toLowerCase() : possessives[lowerToken];
                    translatedTokens.push({ text: combinedResult, isWord: true });
                    continue;
                }

                if (pronouns[lowerToken]) {
                    translatedTokens.push({ text: pronouns[lowerToken], isWord: true });
                    continue;
                }

                if (dictionary[lowerToken]) {
                    translatedTokens.push({ text: dictionary[lowerToken], isWord: true });
                    continue;
                }

                // If not in dictionary, process through the 8-step engine automatically
                let convertedResult = runMechanicalRules(token);
                translatedTokens.push({ text: convertedResult, isWord: true });
            }

            // Adjective inversion filter
            for (let i = 0; i < translatedTokens.length - 1; i++) {
                if (translatedTokens[i].isWord && translatedTokens[i+1].isWord) {
                    let currentValLower = translatedTokens[i].text.toLowerCase();
                    let nextValLower = translatedTokens[i+1].text.toLowerCase();
                    
                    if (adjectives.includes(currentValLower) && !adjectives.includes(nextValLower)) {
                        let temp = translatedTokens[i];
                        translatedTokens[i] = translatedTokens[i+1];
                        translatedTokens[i+1] = temp;
                        i++;
                    }
                }
            }

            // Construct string output text layout
            let finalOutput = "";
            for (let i = 0; i < translatedTokens.length; i++) {
                finalOutput += translatedTokens[i].text;
            }

            if (isQuestion) {
                finalOutput = "Må " + finalOutput;
            }

            document.getElementById("skamalOutput").value = finalOutput;
        }
    </script>
</body>
</html>
