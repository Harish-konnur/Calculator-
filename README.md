# Calculator
<!DOCTYPE html>
<html lang="en">
<head>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculator</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="container">
        <div class="calci">
            <form>
                <div class="display">
                    <input type="text" name="display" id="display">
                </div>
                <div>
                    <input type="button" value="AC" onclick="clearDisplay()" class="operator">
                    <input type="button" value="DE" onclick="deleteLastChar()" class="operator">
                    <input type="button" value="." onclick="appendToDisplay('.')" class="operator">
                    <input type="button" value="/" onclick="appendToDisplay('/')" class="operator">
                </div>
                <div>
                    <input type="button" value="7" onclick="appendToDisplay('7')">
                    <input type="button" value="8" onclick="appendToDisplay('8')">
                    <input type="button" value="9" onclick="appendToDisplay('9')">
                    <input type="button" value="*" onclick="appendToDisplay('*')" class="operator">
                </div>
                <div>
                    <input type="button" value="4" onclick="appendToDisplay('4')">
                    <input type="button" value="5" onclick="appendToDisplay('5')">
                    <input type="button" value="6" onclick="appendToDisplay('6')">
                    <input type="button" value="-" onclick="appendToDisplay('-')" class="operator">
                </div>
                <div>
                    <input type="button" value="1" onclick="appendToDisplay('1')">
                    <input type="button" value="2" onclick="appendToDisplay('2')">
                    <input type="button" value="3" onclick="appendToDisplay('3')">
                    <input type="button" value="+" onclick="appendToDisplay('+')" class="operator">
                </div>
                <div>
                    <input type="button" value="00" onclick="appendToDisplay('00')">
                    <input type="button" value="0" onclick="appendToDisplay('0')">
                    <input type="button" value="=" onclick="calculateResult()" class="equal">
                </div>
            </form>
        </div>
    </div>
    
    <script>
        function clearDisplay() {
            document.getElementById('display').value = '';
        }

        function deleteLastChar() {
            let display = document.getElementById('display');
            display.value = display.value.toString().slice(0, -1);
        }

        function appendToDisplay(value) {
            document.getElementById('display').value += value;
        }

        function calculateResult() {
            let display = document.getElementById('display');
            try {
                display.value = Function('return ' + display.value)();
            } catch {
                display.value = 'Error';
            }
        }
    </script>
</body>
</html>
