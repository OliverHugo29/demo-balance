<!DOCTYPE html>
<html lang="en">
<head>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        /* Mobile-First Design */
        body { font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif; background-color: #f8f9fa; margin: 0; padding: 15px; }
        
        /* Bank Card Style */
        .app-container { max-width: 400px; margin: 0 auto; }
        .card { background: white; padding: 25px; border-radius: 20px; box-shadow: 0 5px 15px rgba(0,0,0,0.08); margin-bottom: 20px; }
        
        /* Balance Styling */
        .account-name { color: #6c757d; font-size: 0.85rem; text-transform: uppercase; letter-spacing: 1px; }
        .balance { font-size: 2.2rem; font-weight: 700; color: #212529; margin: 10px 0; }
        
        /* Form & Buttons */
        input { width: 100%; padding: 14px; margin: 10px 0; border: 1px solid #dee2e6; border-radius: 12px; box-sizing: border-box; font-size: 1rem; }
        button { width: 100%; padding: 14px; background-color: #0d6efd; color: white; border: none; border-radius: 12px; font-weight: 600; font-size: 1rem; cursor: pointer; }
        
        /* History Section */
        h3 { font-size: 1.1rem; color: #495057; margin-top: 25px; }
        .history-list { list-style: none; padding: 0; }
        .history-item { background: white; padding: 15px; border-bottom: 1px solid #f1f3f5; display: flex; justify-content: space-between; align-items: center; }
        .history-item span:last-child { font-weight: bold; }
    </style>
</head>
<body>

<div class="app-container">
    <div class="card">
        <div class="account-name">Oliver's Primary Account</div>
        <div class="balance" id="balance">$300,000</div>
    </div>

    <div class="card">
        <h3>New Transaction</h3>
        <input type="text" id="desc" placeholder="e.g. Salary, Rent">
        <input type="number" id="amount" placeholder="Amount ($)">
        <button onclick="addTransaction()">Update Balance</button>
    </div>

    <h3>Transaction History</h3>
    <div id="history" class="history-list"></div>
</div>

<script>
    let balance = 300000;
    function addTransaction() {
        let desc = document.getElementById('desc').value;
        let amount = parseFloat(document.getElementById('amount').value);
        
        if(!isNaN(amount) && desc !== "") {
            balance += amount;
            document.getElementById('balance').innerText = '$' + balance.toLocaleString();
            
            let item = document.createElement('div');
            item.className = 'history-item';
            item.innerHTML = `<span>${desc}</span> <span>${amount >= 0 ? '+' : ''}$${amount.toLocaleString()}</span>`;
            document.getElementById('history').prepend(item);
            
            document.getElementById('desc').value = "";
            document.getElementById('amount').value = "";
        }
    }
</script>

</body>
</html>
