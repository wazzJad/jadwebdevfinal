<html>
    <head>
        <title>Number System Conversion Tool</title>
    </head>
        <body>
            <style>
            body {
            font-family: 'Arial', sans-serif;
            background: linear-gradient(135deg, #6e7fdb, #c56cf0);
            color: white;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            }
            .container {
            text-align: center;
            padding: 30px;
            border-radius: 10px;
            background-color: rgba(0, 0, 0, 0.6);
            }
            h1 {
            font-size: 36px;
            margin-bottom: 20px;
            }
            .converter input, .converter select {
            padding: 10px;
            margin: 10px;
            border-radius: 5px;
            border: none;
            font-size: 16px;
            }
            button {
            padding: 10px 20px;
            background-color: #f39c12;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            color: white;
            font-size: 16px;
            }
            button:hover {
            background-color: #e67e22;
            }
            .output p {
            font-size: 18px;
           margin: 10px;
            }
            </style>
                    <div class="container">
                        <h1>Number System Conversion</h1>
                            <div class="converter">
                                <input type="text" id="inputNumber" placeholder="Enter number" />
                                    <select id="inputSystem">
                                        <option value="bin">Binary</option>
                                        <option value="dec">Decimal</option>
                                        <option value="oct">Octal</option>
                                        <option value="hex">Hexadecimal</option>
                                    </select>
                                        <button onclick="convertNumber()">Convert</button>
                    </div>
                    <div class="output">
                        <h3>Converted Numbers:</h3>
                        <p id="binaryOutput">Binary: </p>
                        <p id="decimalOutput">Decimal: </p>
                        <p id="octalOutput">Octal: </p>
                        <p id="hexadecimalOutput">Hexadecimal: </p>
                    </div>
                    </div>
                    <script>
                            function convertNumber() {
                            let input = document.getElementById('inputNumber').value;
                            let inputSystem = document.getElementById('inputSystem').value;
                            let decimalNumber;
                        // Convert input to decimal based on the selected input system
                            if (inputSystem === 'bin') {
                            decimalNumber = parseInt(input, 2);
                             } else if (inputSystem === 'oct') {
                            decimalNumber = parseInt(input, 8);
                            } else if (inputSystem === 'hex') {
                            decimalNumber = parseInt(input, 16);
                            } else {
                            decimalNumber = parseInt(input, 10);
                            }
                        // Convert decimal to other systems
                            let binary = decimalNumber.toString(2);
                            let octal = decimalNumber.toString(8);
                            let hexadecimal = decimalNumber.toString(16).toUpperCase();
                        // Display the results
                            document.getElementById('binaryOutput').textContent = `Binary: ${binary}`;
                            document.getElementById('decimalOutput').textContent = `Decimal: ${decimalNumber}`;
                            document.getElementById('octalOutput').textContent = `Octal: ${octal}`;
                            document.getElementById('hexadecimalOutput').textContent = `Hexadecimal: ${hexadecimal}`;
                        }
                    </script>
        </body>
</html>
