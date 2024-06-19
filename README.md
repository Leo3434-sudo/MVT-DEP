<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MVT DEP</title>
    <script>
        function createMessage() {
            var flightNumber = document.getElementById('flightNumber').value;
            var boardingStart = document.getElementById('boardingStart').value;
            var boardingFinish = document.getElementById('boardingFinish').value;
            var doorClosed = document.getElementById('doorClosed').value;
            var pushback = document.getElementById('pushback').value;
            var pax = document.getElementById('pax').value;
            var bags = document.getElementById('bags').value;
            var cargo = document.getElementById('cargo').value;
            var wch = document.getElementById('wch').value;
            var petc = document.getElementById('petc').value;
            var avih = document.getElementById('avih').value;
            var ovs = document.getElementById('ovs').value;

            var services = [];
            document.querySelectorAll('input[name="services"]:checked').forEach((checkbox) => {
                services.push(checkbox.value);
            });

            var message =
                "FLIGHT NUMBER: " + flightNumber + "\n" +
                "BOARDING START: " + boardingStart + "\n" +
                "BOARDING FINISH: " + boardingFinish + "\n" +
                "DOOR CLOSED: " + doorClosed + "\n" +
                "PUSHBACK: " + pushback + "\n" +
                "PAX: " + pax + "\n" +
                "BAGS: " + bags + "\n" +
                "CARGO: " + cargo + "\n" +
                "WCH: " + wch + "\n" +
                "PETC: " + petc + "\n" +
                "AVIH: " + avih + "\n" +
                "OVS: " + ovs + "\n" +
                "Alınan Hizmetler:\n" + services.join("\n");

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
    <h1>MVT DEP</h1>
    <form oninput="createMessage()">
        <label for="flightNumber">FLIGHT NUMBER:</label>
        <input type="text" id="flightNumber"><br><br>

        <label for="boardingStart">BOARDING START:</label>
        <input type="time" id="boardingStart"><br><br>

        <label for="boardingFinish">BOARDING FINISH:</label>
        <input type="time" id="boardingFinish"><br><br>

        <label for="doorClosed">DOOR CLOSED:</label>
        <input type="time" id="doorClosed"><br><br>

        <label for="pushback">PUSHBACK:</label>
        <input type="time" id="pushback"><br><br>

        <label for="pax">PAX:</label>
        <input type="text" id="pax"><br><br>

        <label for="bags">BAGS:</label>
        <input type="text" id="bags"><br><br>

        <label for="cargo">CARGO:</label>
        <input type="text" id="cargo"><br><br>

        <label for="wch">WCH:</label>
        <select id="wch">
            <option value="❌">❌</option>
            <option value="1️⃣">1️⃣</option>
            <option value="2️⃣">2️⃣</option>
            <option value="3️⃣">3️⃣</option>
            <option value="4️⃣">4️⃣</option>
            <option value="5️⃣">5️⃣</option>
        </select><br><br>

        <label for="petc">PETC:</label>
        <select id="petc">
            <option value="❌">❌</option>
            <option value="1️⃣">1️⃣</option>
            <option value="2️⃣">2️⃣</option>
            <option value="3️⃣">3️⃣</option>
            <option value="4️⃣">4️⃣</option>
            <option value="5️⃣">5️⃣</option>
        </select><br><br>

        <label for="avih">AVIH:</label>
        <select id="avih">
            <option value="❌">❌</option>
            <option value="1️⃣">1️⃣</option>
            <option value="2️⃣">2️⃣</option>
            <option value="3️⃣">3️⃣</option>
            <option value="4️⃣">4️⃣</option>
            <option value="5️⃣">5️⃣</option>
        </select><br><br>

        <label for="ovs">OVS:</label>
        <select id="ovs">
            <option value="❌">❌</option>
            <option value="1️⃣">1️⃣</option>
            <option value="2️⃣">2️⃣</option>
            <option value="3️⃣">3️⃣</option>
            <option value="4️⃣">4️⃣</option>
            <option value="5️⃣">5️⃣</option>
        </select><br><br>

        <label>Alınan Hizmetleri Seçin:</label><br>
        <input type="checkbox" id="gpu" name="services" value="GPU">
        <label for="gpu">GPU</label><br>
        <input type="checkbox" id="acu" name="services" value="ACU">
        <label for="acu">ACU</label><br>
        <input type="checkbox" id="asu" name="services" value="ASU">
        <label for="asu">ASU</label><br>
        <input type="checkbox" id="water" name="services" value="Water">
        <label for="water">Water</label><br>
        <input type="checkbox" id="fuel" name="services" value="Fuel">
        <label for="fuel">Fuel</label><br>
        <input type="checkbox" id="fireTruck" name="services" value="Fire Truck">
        <label for="fireTruck">Fire Truck</label><br>
        <input type="checkbox" id="crewAssist" name="services" value="Crew Assist">
        <label for="crewAssist">Crew Assist</label><br><br>

        <button type="button" onclick="copyToClipboard()">Gönder</button>
    </form>

    <h2>Oluşturulan Mesaj</h2>
    <textarea id="output" rows="20" cols="50"></textarea>
</body>
</html>
