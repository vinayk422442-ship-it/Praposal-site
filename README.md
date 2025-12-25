# Praposal-site
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Will You Be My Girlfriend?</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="container">
        <h1>Dear [Her Name],</h1>
        <p>From the moment I met you, my world has been brighter. Your smile lights up my day, and I can't imagine life without you by my side.</p>
        <p>Will you make me the happiest person and be my girlfriend?</p>
        <img src="your-photo.jpg" alt="A beautiful photo of us or something romantic" class="photo">
        <div class="buttons">
            <button id="yes-btn">Yes! 💕</button>
            <button id="no-btn">No 😢</button>
        </div>
        <div id="response" class="hidden">
            <p id="message"></p>
        </div>
    </div>
    <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.5.1/dist/confetti.browser.min.js"></script>
    <script src="script.js"></script>
</body>
</html>
body {
    font-family: 'Arial', sans-serif;
    background: linear-gradient(to bottom, #ff9a9e, #fecfef);
    color: #333;
    text-align: center;
    margin: 0;
    padding: 0;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    overflow: hidden;
}

.container {
    max-width: 600px;
    padding: 20px;
    background: rgba(255, 255, 255, 0.9);
    border-radius: 15px;
    box-shadow: 0 0 20px rgba(0, 0, 0, 0.1);
    animation: fadeIn 2s;
}

h1 {
    color: #e91e63;
    font-size: 2.5em;
    animation: bounce 1s;
}

p {
    font-size: 1.2em;
    line-height: 1.6;
}

.photo {
    max-width: 100%;
    height: auto;
    border-radius: 10px;
    margin: 20px 0;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
    animation: slideIn 1.5s;
}

.buttons {
    margin-top: 20px;
}

button {
    padding: 10px 20px;
    font-size: 1.2em;
    margin: 0 10px;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    transition: all 0.3s;
}

#yes-btn {
    background: #4caf50;
    color: white;
}

#yes-btn:hover {
    background: #45a049;
    transform: scale(1.1);
}

#no-btn {
    background: #f44336;
    color: white;
}

#no-btn:hover {
    background: #da190b;
    transform: scale(1.1);
}

#response {
    margin-top: 20px;
    font-size: 1.5em;
    font-weight: bold;
    animation: fadeIn 1s;
}

.hidden {
    display: none;
}

@keyframes fadeIn {
    from { opacity: 0; }
    to { opacity: 1; }
}

@keyframes bounce {
    0%, 20%, 50%, 80%, 100% { transform: translateY(0); }
    40% { transform: translateY(-10px); }
    60% { transform: translateY(-5px); }
}

@keyframes slideIn {
    from { transform: translateY(50px); opacity: 0; }
    to { transform: translateY(0); opacity: 1; }
}
document.getElementById('yes-btn').addEventListener('click', function() {
    document.getElementById('message').textContent = "Yay! I love you! 💖 Let's celebrate!";
    document.getElementById('response').classList.remove('hidden');
    // Trigger confetti
    confetti({
        particleCount: 100,
        spread: 70,
        origin: { y: 0.6 }
    });
});

document.getElementById('no-btn').addEventListener('click', function() {
    document.getElementById('message').textContent = "That's okay, I'll keep trying! 😊";
    document.getElementById('response').classList.remove('hidden');
});
