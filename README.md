# Tesla


<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Tesla | Investment Demo</title>
<style>
:root {
  --bg: #090b0f;
  --panel: #141820;
  --line: #292f3a;
  --text: #f5f7fa;
  --muted: #9ba5b5;
  --red: #e82127;
  --green: #43d49a;
}
* { box-sizing: border-box; }
body {
  margin: 0;
  background: var(--bg);
  color: var(--text);
  font-family: Arial, sans-serif;
}
header {
  padding: 20px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  border-bottom: 1px solid var(--line);
}
.brand { font-size: 25px; font-weight: 800; letter-spacing: 2px; }
.brand span { color: var(--red); }
.demo {
  font-size: 10px;
  color: #ffb6b6;
  border: 1px solid #73353a;
  padding: 7px 9px;
  border-radius: 20px;
}
main { max-width: 900px; margin: auto; padding: 22px 16px 40px; }
h1 { font-size: 27px; margin-bottom: 7px; }
p { color: var(--muted); line-height: 1.6; }
.card {
  background: var(--panel);
  border: 1px solid var(--line);
  border-radius: 16px;
  padding: 20px;
  margin: 18px 0;
}
.label { color: var(--muted); font-size: 13px; }
.balance { font-size: 35px; font-weight: 700; margin: 12px 0; }
.pill { color: var(--green); font-size: 13px; }
.grid {
  display: grid;
  grid-template-columns: repeat(2, minmax(0,1fr));
  gap: 12px;
}
.stat {
  background: #10141b;
  border: 1px solid var(--line);
  border-radius: 12px;
  padding: 15px;
}
.stat strong { display: block; margin-top: 10px; font-size: 20px; }
h2 { font-size: 19px; }
.plans { display: grid; gap: 12px; }
.plan {
  border: 1px solid var(--line);
  background: #10141b;
  border-radius: 12px;
  padding: 17px;
}
.plan h3 { margin: 0 0 8px; }
.plan p { font-size: 13px; }
button {
  background: var(--red);
  color: white;
  border: 0;
  border-radius: 9px;
  padding: 13px 16px;
  font-size: 14px;
  font-weight: bold;
  cursor: pointer;
}
button:active { opacity: .8; }
.secondary { background: #292f3a; }
.actions { display: flex; gap: 10px; flex-wrap: wrap; }
.notice {
  border-left: 3px solid var(--red);
  padding: 12px;
  background: #17151a;
  color: #d7d9df;
  font-size: 12px;
  line-height: 1.6;
}
nav {
  display: flex;
  justify-content: space-around;
  gap: 6px;
  padding: 16px 4px;
  border-top: 1px solid var(--line);
  position: sticky;
  bottom: 0;
  background: #090b0f;
}
nav button { background: transparent; color: var(--muted); padding: 10px; }
footer { text-align: center; color: var(--muted); font-size: 12px; padding: 20px; }
@media (min-width: 650px) {
  .plans { grid-template-columns: repeat(3, minmax(0,1fr)); }
}
</style>
</head>
<body>
<header>
  <div class="brand">TESLA<span>.</span></div>
  <div class="demo">DEMO MODE</div>
</header>

<main>
  <section id="home">
    <p>INVESTMENT DASHBOARD</p>
    <h1>Welcome to Tesla Demo</h1>
    <p>Explore your sample dashboard and investment interface.</p>

    <div class="card">
      <div class="label">Demo account balance</div>
      <div class="balance" id="balance">$10,000.00</div>
      <div class="pill">● Sample funds only — no real money</div>
      <hr style="border-color:var(--line);margin:20px 0">
      <div class="grid">
        <div class="stat">
          <div class="label">Demo investments</div>
          <strong id="invested">$2,000.00</strong>
        </div>
        <div class="stat">
          <div class="label">Demo earnings</div>
          <strong>$0.00</strong>
        </div>
      </div>
    </div>

    <div class="actions">
      <button onclick="showMessage()">Deposit (disabled)</button>
      <button class="secondary" onclick="showMessage()">Withdraw (disabled)</button>
    </div>
    <p id="message" aria-live="polite"></p>
  </section>

  <section id="plans">
    <h2>Investment Plans</h2>
    <p>Sample plans for exploring the interface. These are not real offers.</p>
    <div class="plans">
      <div class="plan">
        <h3>Starter</h3>
        <p>For exploring the demo platform.</p>
        <strong>$100 – $999</strong>
        <p>No promised returns.</p>
        <button onclick="selectPlan('Starter')">Explore plan</button>
      </div>
      <div class="plan">
        <h3>Growth</h3>
        <p>A sample mid-level plan layout.</p>
        <strong>$1,000 – $4,999</strong>
        <p>No promised returns.</p>
        <button onclick="selectPlan('Growth')">Explore plan</button>
      </div>
      <div class="plan">
        <h3>Premium</h3>
        <p>A sample premium plan layout.</p>
        <strong>$5,000+</strong>
        <p>No promised returns.</p>
        <button onclick="selectPlan('Premium')">Explore plan</button>
      </div>
    </div>
    <p id="planMessage" aria-live="polite"></p>
  </section>

  <section id="account">
    <h2>Account overview</h2>
    <div class="card">
      <p>Account status: <strong>Demo only</strong></p>
      <p>Transactions: <strong>Not enabled</strong></p>
      <p>Payments: <strong>Not connected</strong></p>
      <p>Authentication: <strong>Not configured</strong></p>
    </div>
  </section>

  <div class="notice">
    DEMONSTRATION ONLY. This prototype is not an official Tesla, Inc.
    website or investment service. Balances are fictional. No deposits,
    withdrawals, real accounts, or financial transactions are processed.
  </div>
</main>

<nav>
  <button onclick="goTo('home')">Home</button>
  <button onclick="goTo('plans')">Plans</button>
  <button onclick="goTo('account')">Account</button>
</nav>

<footer>TESLA DEMO • Website prototype</footer>

<script>
function showMessage() {
  document.getElementById('message').textContent =
    'Payments are disabled in this demonstration.';
}
function selectPlan(name) {
  document.getElementById('planMessage').textContent =
    name + ' plan selected for preview only. No investment has been made.';
}
function goTo(id) {
  document.getElementById(id).scrollIntoView({ behavior: 'smooth' });
}
</script>
</body>
</html>