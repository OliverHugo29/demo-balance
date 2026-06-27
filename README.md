<!DOCTYPE html>
<html>
<head>
    <title>My Balance</title>
</head>
<body style="text-align: center; font-family: sans-serif; margin-top: 50px; background-color: #f4f4f4;">

    <div style="background: white; padding: 20px; border-radius: 10px; display: inline-block; box-shadow: 0 4px 8px rgba(0,0,0,0.1);">
        <h1>Current Balance</h1>
        <div id="balance" style="font-size: 3rem; color: #2ecc71; font-weight: bold;">$300,000</div>
        <br>
        <button onclick="addMoney()" style="padding: 10px 20px; font-size: 1rem; cursor: pointer;">Add $100</button>
    </div>

    <script>
        let balance = 300000;
        function addMoney() {
            balance += 100;
            document.getElementById('balance').innerText = '$' + balance.toLocaleString();
        }
    </script>

</body>


</html>
