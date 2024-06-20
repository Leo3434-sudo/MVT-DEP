<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MVT ARV</title>
    <script>
        function createMessage() {
            var flightNumber = document.getElementById('flightNumber').value;
            var reg = document.getElementById('reg').value || "RA73";
            var pp = document.getElementById('pp').value;
            var td = document.getElementById('td').value;
            var ob = document.getElementById('ob').value;
            var doTime = document.getElementById('doTime').value;
            var paxC = document.getElementById('paxC').value;
            var paxY = document.getElementById('paxY').value;
            var paxINF = document.getElementById('paxINF').value;
            var paxINAD = document.getElementById('paxINAD').value;
            var bags = document.getElementById('bags').value;
            var cgo = document.getElementById('cgo').value;
            var wch = document.getElementById('wch').value;
            var crewAssist = document.getElementById('crewAssist').checked ? "✅" : "❌";
            
            var paxMessage = "PAX ";
            if (paxC) paxMessage += paxC + "C+";
            if (paxY) paxMessage += paxY + "Y+";
            if (paxINF) paxMessage += paxINF + "INF+";
            if (paxINAD) paxMessage += paxINAD + "INAD";

            var today = new Date();
            var dd = String(today.getDate()).padStart(2, '0');
            var mm = today.toLocaleString('default', { month: 'short' }).toUpperCase();
            var formattedDate = dd + mm;

            var message =
                flightNumber + "/" + formattedDate + "/" + reg + "\n" +
                "PP " + pp + "\n" +
                "TD " + td + "\n" +
                "OB " + ob + "\n" +
                "DO " + doTime + "\n" +
                paxMessage + "\n" +
                "BAG " + bags + "\n" +
                "CGO " + cgo + "\n" +
                "WCH " + wch + "\n" +
                "CREW ASSIST " + crewAssist;

            document.getElementById('output').value = message;
        }

        function copyToClipboard() {
            var message = document.getElementById('output').value;
            navigator.clipboard.writeText(message).then(function() {
                window.open("https://chat.whatsapp.com/L35Iex4zZNn8YvNA2kP1zN");
            });
        }
    </script>
</head>
<body>
    <h1>MVT ARV</h1>
    <form oninput="createMessage()">
        <label for="flightNumber">Uçuş No:</label>
        <input type="text" id="flightNumber"><br><br>

        <label for="reg">REG:</label>
        <input type="text" id="reg" value="RA73"><br><br>

        <label for="pp">PP:</label>
        <input type="text" id="pp"><br><br>

        <label for="td">TD:</label>
        <input type="time" id="td"><br><br>

        <label for="ob">OB:</label>
        <input type="time" id="ob"><br><br>

        <label for="doTime">DO:</label>
        <input type="time" id="doTime"><br><br>

        <label for="paxC">PAX:</label>
        <input type="number" id="paxC" placeholder="C"> 
        <input type="number" id="paxY" placeholder="Y">
        <input type="number" id="paxINF" placeholder="INF">
        <input type="number" id="paxINAD" placeholder="INAD"><br><br>

        <label for="bags">BAG:</label>
        <input type="text" id="bags"><br><br>

        <label for="cgo">CGO:</label>
        <input type="text" id="cgo"><br><br>

        <label for="wch">WCH:</label>
        <select id="wch">
            <option value="❌">❌</option>
            <option value="1️⃣">1️⃣</option>
            <option value="2️⃣">2️⃣</option>
            <option value="3️⃣">3️⃣</option>
            <option value="4️⃣">4️⃣</option>
            <option value="5️⃣">5️⃣</option>
        </select><br><br>

        <label for="crewAssist">CREW ASSIST:</label>
        <select id="crewAssist">
            <option value="❌">❌</option>
            <option value="✅">✅</option>
        </select><br><br>

        <button type="button" onclick="copyToClipboard()">Gönder</button>
    </form>

    <h2>Oluşturulan Mesaj</h2>
    <textarea id="output" rows="20" cols="50"></textarea>
</body>
</html>
