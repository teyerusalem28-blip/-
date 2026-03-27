
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For My Love ❤️</title>
    <style>
        body {
            margin: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(to bottom, #0a0000, #4a0000);
            color: white;
            text-align: center;
            overflow-x: hidden;
        }

        #loginPage {
            display: flex;
            height: 100vh;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            background: #000;
        }

        .page { display: none; padding: 20px; animation: fadeIn 2s; }

        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }

        h1 { font-size: 2.5rem; text-shadow: 0 0 15px #ff0000; margin-top: 20px; }

        .card {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 20px;
            padding: 15px;
            margin: 20px auto;
            max-width: 450px;
            border: 1px solid rgba(255, 255, 255, 0.2);
            box-shadow: 0 10px 30px rgba(0,0,0,0.5);
        }

        img, video { width: 100%; border-radius: 15px; display: block; }

        /* --- TIMELINE STYLES --- */
        .timeline {
            max-width: 500px;
            margin: 40px auto;
            position: relative;
            padding: 20px 0;
            text-align: left;
        }

        .timeline::before {
            content: '';
            position: absolute;
            left: 20px;
            top: 0;
            bottom: 0;
            width: 2px;
            background: #ff4d4d;
        }

        .milestone {
            margin-bottom: 30px;
            padding-left: 50px;
            position: relative;
        }

        .milestone::before {
            content: '❤️';
            position: absolute;
            left: 10px;
            top: 0;
            font-size: 18px;
        }

        .milestone h4 { margin: 0; color: #ffcccc; font-size: 1.1rem; }
        .milestone p { margin: 5px 0 0; font-size: 0.9rem; opacity: 0.8; }

        .counter {
            font-size: 1.5rem;
            color: #ff4d4d;
            font-weight: bold;
            margin: 20px 0;
            text-shadow: 0 0 10px rgba(255, 77, 77, 0.3);
        }

        input { padding: 15px; border-radius: 30px; border: none; width: 250px; text-align: center; }
        button { margin-top: 15px; padding: 12px 40px; border-radius: 30px; border: none; background: #ff0000; color: white; cursor: pointer; }
        
        .heart { position: fixed; top: -10%; color: #ff4d4d; animation: fall linear forwards; z-index: 999; }
        @keyframes fall { to { transform: translateY(110vh) rotate(360deg); opacity: 0; } }
    </style>
</head>
<body>

<div id="loginPage">
    <h2>🔒 Locked with Love</h2>
    <p>Hint: Our first date year</p>
    <input type="password" id="pass" placeholder="Enter Year">
    <button onclick="unlock()">Open My Heart ❤️</button>
</div>

<div id="mainPage" class="page">
    <h1>Happy Anniversary! 🌹</h1>
    
    <div class="counter" id="daysCounter">Calculating our time...</div>

    <div class="card">
        <img src="YOUR_DIRECT_LINK_HERE" alt="Us">
        <p style="font-style: italic; color: #ffcccc;">Yene bal ❤️❤️</p>
    </div>

    <div class="timeline">
        <div class="milestone">
            <h4>The Day We Met</h4>
            <p>The moment my world changed forever.</p>
        </div>
        <div class="milestone">
            <h4>Our First Date</h4>
            <p>Two years and two months ago today.</p>
        </div>
        <div class="milestone">
            <h4>Every Day Since</h4>
            <p>Falling in love with you more and more.</p>
        </div>
    </div>

    <div class="card">
        <video controls>
            <source src="YOUR_VIDEO_LINK_HERE" type="video/mp4">
        </video>
    </div>

    <h3>Scan for a surprise 💌</h3>
    <img src="https://api.qrserver.com/v1/create-qr-code/?size=150x150&data=I%20love%20you%20forever" style="width: 150px; margin: 0 auto; border: none;">
</div>

<script>
function unlock() {
    if(document.getElementById('pass').value === "2021") {
        document.getElementById('loginPage').style.display = 'none';
        document.getElementById('mainPage').style.display = 'block';
        startHearts();
        calculateDays();
    } else { alert("Try again, love! 😢"); }
}

function calculateDays() {
    // Note: This calculates from Jan 1st 2021 as a placeholder
    // Update the date below to your actual first date!
    const startDate = new Date("2021-01-01"); 
    const today = new Date();
    const diffTime = Math.abs(today - startDate);
    const diffDays = Math.ceil(diffTime / (1000 * 60 * 60 * 24)); 
    document.getElementById('daysCounter').innerHTML = diffDays + " Days Together ❤️";
}

function startHearts() {
    setInterval(() => {
        const h = document.createElement("div");
        h.className = "heart";
        h.innerHTML = "❤️";
        h.style.left = Math.random() * 100 + "vw";
        h.style.animationDuration = (Math.random() * 3 + 2) + "s";
        document.body.appendChild(h);
        setTimeout(() => h.remove(), 5000);
    }, 400);
}
</script>

</body>
</html>
