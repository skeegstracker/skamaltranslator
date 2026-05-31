#skamaltranslator

Translate English into Skamal.

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>English to Skämål Translator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            margin: 40px auto;
            max-width: 800px;
            padding: 0 20px;
            color: #333;
            background-color: #fff;
        }
        h1 {
            color: #111;
            border-bottom: 2px solid #333;
            padding-bottom: 10px;
            font-size: 28px;
            text-align: center;
        }
        .translator-container {
            background: #f9f9f9;
            border: 1px solid #ddd;
            padding: 20px;
            border-radius: 8px;
            margin-bottom: 40px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.05);
        }
        .form-group {
            margin-bottom: 15px;
        }
        label {
            display: block;
            font-weight: bold;
            margin-bottom: 5px;
        }
        textarea {
            width: 100%;
            height: 100px;
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 4px;
            box-sizing: border-box;
            font-size: 16px;
            resize: vertical;
        }
        button {
            background-color: #333;
            color: #fff;
            padding: 10px 20px;
            border: none;
            border-radius: 4px;
            font-size: 16px;
            cursor: pointer;
            width: 100%;
        }
        button:hover {
            background-color: #555;
        }
        .output-box {
            background: #fff;
            border-left: 4px solid #333;
            padding: 15px;
            margin-top: 15px;
            min-height: 50px;
            white-space: pre-wrap;
            font-size: 18px;
            font-weight: bold;
        }
        details {
            background: #f1f1f1;
            padding: 15px;
            border-radius: 4px;
            cursor: pointer;
        }
        summary {
            font-weight: bold;
        }
        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 10px;
        }
        th, td {
            border: 1px solid #ddd;
            padding: 8px;
            text-align: left;
            font-size: 14px;
        }
        th {
            background-color: #eaeaea;
        }
    </style>
</head>
<body>

    <h1>English to Skämål Translator</h1>

    <div class="translator-container">
        <div class="form-group">
            <label for="englishInput">English Input:</label>
            <textarea id="englishInput" placeholder="Type your English text here..."></textarea>
        </div>
        <button onclick="translateToSkamal()">Translate</button>
        
        <div class="form-group">
            <label>Skämål Translation:</label>
            <div id="skamalOutput" class="output-box"></div>
        </div>
    </div>

    <details>
        <summary>View Language Dictionary & Rules Reference</summary>
        <h3>Protected Vocabulary Quick-Check</h3>
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
                <tr><td>My</td><td>Jän-</td><td>Language/Dialect</td><td>språkå</td></tr>
                <tr><td>Police</td><td>vakt</td><td>Text</td><td>båkkt</td></tr>
                <tr><td>Officer</td><td>onstapel</td><td>City</td><td>stadä</td></tr>
                <tr><td>House</td><td>garda</td><td>Friend</td><td>sjelårad</td></tr>
                <tr><td>Coffee</td><td>Kafe</td><td>Water</td><td>vatnå</td></tr>
                <tr><td>Hot</td><td>skolå</td><td>Cold</td><td>kjölå</td></tr>
                <tr><td>Is/Are</td><td>ös</td><td>Beautiful</td><td>skönå</td></tr>
            </tbody>
        </table>
    </details>

    <script>
