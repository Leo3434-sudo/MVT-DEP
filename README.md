<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MVT DEP</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }
        .container {
            background-color: #fff;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            max-width: 100%;
            width: 100%;
            box-sizing: border-box;
            margin: 0 10px;
        }
        h1 {
            font-size: 24px;
            margin-bottom: 20px;
            text-align: center;
        }
        form {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
        }
        .form-group {
            width: 100%;
            margin-bottom: 15px;
            box-sizing: border-box;
        }
        .form-group.half-width {
            width: calc(50% - 10px);
        }
        label {
            margin-bottom: 5px;
            font-weight: bold;
            display: block;
        }
        input[type="text"],
        input[type="time"],
        input[type="number"],
        select {
            padding: 8px;
            border: 1px solid #ccc;
            border-radius: 4px;
            font-size: 14px;
            width: 100%;
            box-sizing: border-box;
        }
        button {
            padding: 10px;
            background-color: #4CAF50;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-size: 16px;
            width: 100%;
        }
        button:hover {
            background-color: #45a049;
        }
        textarea {
            width: calc(100% - 16px);
            resize: none;
            padding: 8px;
            border: 1px solid #ccc;
            border-radius: 4px;
            font-size: 14px;
            box-sizing: border-box;
        }
        .output-container {
            margin-top: 20px;
            text-align: center;
        }
    </style>
    <script>
        function createMessage() {
            var flightNumber = document.getElementById('flightNumber').value;
            var boardingStart = document.getElementById('boardingStart').value;
            var boardingFinish = document.getElementById('boardingFinish').value;
            var doorClosed = document.getElementById('doorClosed').value;
            var pushback = document.getElementById('pushback').value;
            var paxC = document.getElementById('paxC').value;
            var paxY = document.getElementById('paxY').value;
            var paxINF = document.getElementById('paxINF').value;
            var paxINAD = document.getElementById('paxINAD').value;
            var bags = document.getElementById('bags').value;
            var cargo = document.getElementById('cargo').value || "❌";
            var wch = document.getElementById('wch').value;
            var petc = document.getElementById('petc').value;
            var avih = document.getElementById('avih').value;
            var ovs = document.getElementById('ovs').value;
            var gpu = document.getElementById('gpu').checked ? "✅" : "❌";
            var acu = document.getElementById('acu').checked ? "✅" : "❌";
            var asu = document.getElementById('asu').checked ? "✅" : "❌";
            var water = document.getElementById('water').checked ? "✅" : "❌";
            var fuel = document.getElementById('fuel').checked ? "✅" : "❌";
            var fireTruck = document.getElementById('fireTruck').checked ? "✅" : "❌";
            var crewAssist = document.getElementById('crewAssist').checked ? "✅" : "❌";

            var paxMessage = "PAX ";
            if (paxC) paxMessage += paxC + "C+";
            if (paxY) paxMessage += paxY + "Y+";
            if (paxINF) paxMessage += paxINF + "INF+";
            if (paxINAD) paxMessage += paxINAD + "INAD";
            if (!paxC && !paxY && !paxINF && !paxINAD) paxMessage += "N/A";

            var today = new Date();
            var dd = String(today.getDate()).padStart(2, '0');
            var mm = today.toLocaleString('default', { month: 'short' }).toUpperCase();
            var formattedDate = dd + mm;

            var message =
                flightNumber.substring(0, 8) + "\n" +
                "BS: " + boardingStart + "   BF: " + boardingFinish + "\n" +
                "DC: " + doorClosed + "   PB: " + pushback + "\n" +
                paxMessage + "\n" +
                "BAGS: " + bags + "\n" +
                "CARGO: " + cargo + "\n" +
                "WCH: " + wch + "\n" +
                "PETC: " + petc + "\n" +
                "AVIH: " + avih + "\n" +
                "OVS: " + ovs + "\n" +
                "GPU: " + gpu + "\n" +
                "ACU: " + acu + "\n" +
                "ASU: " + asu + "\n" +
                "Water: " + water + "\n" +
                "Fuel: " + fuel + "\n" +
                "Fire Truck: " + fireTruck + "\n" +
                "Crew Assist: " + crewAssist;

            document.getElementById('output').value = message;
        }

        function copyToClipboard() {
            var output = document.getElementById('output');
            output.select();
            output.setSelectionRange(0, 99999); // For mobile devices

            try {
                document.execCommand('copy');
                alert('Message copied to clipboard');
            } catch (err) {
                alert('Failed to copy message');
            }

            window.location.href = "https://chat.whatsapp.com/EXAJWqIDyk91zBHukgg020";
        }
    </script>
</head>
<body>
    <div class="container">
        <h1>MVT DEP</h1>
        <form oninput="createMessage()">
            <div class="form-group full-width">
                <label for="flightNumber">Uçuş No:</label>
                <input type="text" id="flightNumber" maxlength="8">
            </div>
            <div class="form-group half-width">
                <label for="boardingStart">BS:</label>
                <input type="time" id="boardingStart">
            </div>
            <div class="form-group half-width">
                <label for="boardingFinish">BF:</label>
                <input type="time" id="boardingFinish">
            </div>
            <div class="form-group half-width">
                <label for="doorClosed">DC:</label>
                <input type="time" id="doorClosed">
            </div>
            <div class="form-group half-width">
                <label for="pushback">PB:</label>
                <input type="time" id="pushback">
            </div>
            <div class="form-group full-width">
                <label for="paxC">PAX:</label>
                <input type="number" id="paxC" placeholder="C" style="width: 22%;">
                <input type="number" id="paxY" placeholder="Y" style="width: 22%;">
                <input type="number" id="paxINF" placeholder="INF" style="width: 22%;">
                <input type="number" id="paxINAD" placeholder="INAD" style="width: 22%;">
            </div>
            <div class="form-group half-width">
                <label for="bags">BAGS:</label>
                <input type="text" id="bags" placeholder="PCS/KGS">
            </div>
            <div class="form-group half-width">
                <label for="cargo">CARGO:</label>
                <input type="text" id="cargo" placeholder="PCS/KGS">
            </div>
            <div class="form-group half-width">
                <label for="wch">WCH:</label>
                <select id="wch">
                    <option value="❌">❌</option>
                    <option value="1️⃣">1️⃣</option>
                    <option value="2️⃣">2️⃣</option>
                    <option value="3️⃣">3️⃣</option>
                    <option value="4️⃣">4️⃣</option>
                    <option value="5️⃣">5️⃣</option>
                </select>
            </div>
            <div class="form-group half-width">
                <label for="petc">PETC:</label>
                <select id="petc">
                    <option value="❌">❌</option>
                    <option value="1️⃣">1️⃣</option>
                    <option value="2️⃣">2️⃣</option>
                    <option value="3️⃣">3️⃣</option>
                    <option value="4️⃣">4️⃣</option>
                    <option value="5️⃣">5️⃣</option>
                </select>
            </div>
            <div class="form-group half-width">
                <label for="avih">AVIH:</label>
                <select id="avih">
                    <option value="❌">❌</option>
                    <option value="1️⃣">1️⃣</option>
                    <option value="2️⃣">2️⃣</option>
                    <option value="3️⃣">3️⃣</option>
                    <option value="4️⃣">4️⃣</option>
                    <option value="5️⃣">5️⃣</option>
                </select>
            </div>
            <div class="form-group half-width">
                <label for="ovs">OVS:</label>
                <select id="ovs">
                    <option value="❌">❌</option>
                    <option value="1️⃣">1️⃣</option>
                    <option value="2️⃣">2️⃣</option>
                    <option value="3️⃣">3️⃣</option>
                    <option value="4️⃣">4️⃣</option>
                    <option value="5️⃣">5️⃣</option>
                </select>
            </div>
            <div class="form-group full-width">
                <label for="gpu">GPU:</label>
                <input type="checkbox" id="gpu">
            </div>
            <div class="form-group full-width">
                <label for="acu">ACU:</label>
                <input type="checkbox" id="acu">
            </div>
            <div class="form-group full-width">
                <label for="asu">ASU:</label>
                <input type="checkbox" id="asu">
            </div>
            <div class="form-group full-width">
                <label for="water">Water:</label>
                <input type="checkbox" id="water">
            </div>
            <div class="form-group full-width">
                <label for="fuel">Fuel:</label>
                <input type="checkbox" id="fuel">
            </div>
            <div class="form-group full-width">
                <label for="fireTruck">Fire Truck:</label>
                <input type="checkbox" id="fireTruck">
            </div>
            <div class="form-group full-width">
                <label for="crewAssist">Crew Assist:</label>
                <input type="checkbox" id="crewAssist">
            </div>
            <button type="button" onclick="copyToClipboard()">MVT'yi Kopyala, WhatsApp'ı Aç</button>
        </form>
        <div class="output-container">
            <h2>MVT DEP Ön İzleme</h2>
            <textarea id="output" rows="20"></textarea>
        </div>
    </div>
</body>
</html>