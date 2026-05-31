
Translate English into Skämål.


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
            height: 110px;
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
        button {
            background-color: #0056b3;
            color: #fff;
            padding: 12px 24px;
            border: none;
            border-radius: 6px;
            font-size: 16px;
            font-weight: bold;
            cursor: pointer;
            width: 100%;
            transition: background-color 0.2s;
        }
        button:hover {
            background-color: #004085;
        }
        .output-box {
            background: #f8f9fa;
            border-left: 5px solid #0056b3;
            padding: 18px;
            margin-top: 10px;
            min-height: 60px;
            white-space: pre-wrap;
            font-size: 20px;
            color: #111;
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
            <textarea id="englishInput" placeholder="Type your English phrase or sentences here..."></textarea>
        </div>
        <button onclick="translateToSkamal()">Translate into Skämål</button>
        
        <div class="form-group" style="margin-top: 25px;">
            <label>Skämål Target Translation:</label>
            <div id="skamalOutput" class="output-box"></div>
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
                    <tr><td>My</td><td>Jän- [Noun]</td><td>Language/Dialect</td><td>språkå</td></tr>
                    <tr><td>Police</td><td>vakt</td><td>Text</td><td>båkkt</td></tr>
                    <tr><td>Officer</td><td>onstapel</td><td>City</td><td>stadä</td></tr>
                    <tr><td>House</td><td>garda</td><td>Friend</td><td>sjelårad</td></tr>
                    <tr><td>Coffee</td><td>Kafe</td><td>Water</td><td>vatnå</td></tr>
                    <tr><td>Hot</td><td>skolå</td><td>Cold</td><td>kjölå</td></tr>
                    <tr><td>Is / Are</td><td>ös</td><td>Beautiful</td><td>skönå</td></tr>
                </tbody>
            </table>
        </div>
    </details>

    <script>
        // Master Protected Vocabulary
        const dictionary = {
            "hello": "Hejsan", "welcome": "Valkomma", "thank thank-you thank-you": "Väa", "thankyou": "Väa",
            "goodbye": "Väo", "yes": "Vïste", "no": "Vïsto", "language": "språkå", "dialect": "språkå", 
            "text": "båkkt", "person": "sjelå", "friend": "sjelårad", "police": "vakt", "officer": "onstapel", 
            "city": "stadä", "house": "garda", "tree": "stalmå", "coffee": "Kafe", "water": "vatnå", 
            "like": "lyskå", "likes": "lyskå", "am": "är", "is": "ös", "are": "ös", "hot": "skolå", 
            "warm": "skolå", "boiling": "skolå", "cold": "kjölå", "freezing": "kjölå", "beautiful": "skönå", 
            "a": "vå", "the": "hät", "to": "åt", "who": "Hå", "what": "Vät", "when": "Vëhn", "where": "Vär", 
            "why": "Vï", "how": "Hët", "1": "Än", "2": "Dva", "3": "Trå", "4": "Fjäl", "5": "Föm", 
            "6": "Sås", "7": "Sjå", "8": "Ått", "9": "Njö", "10": "Täl"
        };

        const pronouns = { "i": "Jäg", "you": "Dö", "he": "Hän", "she": "Hän", "it": "Dät", "we": "Vö", "they": "Då" };
        
        const possessives = { "my": "Jän-", "your": "Dön-", "his": "Häns-", "her": "Häns-", "its": "Däts-", "our": "Vön-", "their": "Dån-" };
        
        const contractions = { "i'm": "Jäg-ös", "you're": "Dö-ös", "he's": "Hän-ös", "she's": "Hän-ös", "it's": "Dät-ös", "we're": "Vö-ös", "they're": "Då-ös" };

        const adjectives = ["skolå", "kjölå", "skönå"];

        function runMechanicalRules(word) {
            let cleanWord = word;
            let suffix = "";
            
            // 1. Check & isolate Suffixes
            if (cleanWord.toLowerCase().endsWith("ing")) { suffix = "ing"; cleanWord = cleanWord.slice(0, -3); }
            else if (cleanWord.toLowerCase().endsWith("ed")) { suffix = "ed"; cleanWord = cleanWord.slice(0, -2); }
            else if (cleanWord.toLowerCase().endsWith("es")) { suffix = "es"; cleanWord = cleanWord.slice(0, -2); }
            else if (cleanWord.toLowerCase().endsWith("s") && !cleanWord.toLowerCase().endsWith("ss")) { suffix = "s"; cleanWord = cleanWord.slice(0, -1); }

            if (cleanWord.length === 0) return word;

            // 2. Vowel-Starting Prefix Placeholder Consonant
            let firstLetter = cleanWord.charAt(0);
            let startsWithVowel = /^[aeiouAEIOU]/.test(firstLetter);
            if (startsWithVowel) {
                cleanWord = (suffix === "") ? "T" + cleanWord : "J" + cleanWord;
            }

            // 3. Compress double elements & mark Umlaut rule criteria
            let compressed = "";
            let triggerUmlaut = false;
            for (let i = 0; i < cleanWord.length; i++) {
                if (i < cleanWord.length - 1 && cleanWord
