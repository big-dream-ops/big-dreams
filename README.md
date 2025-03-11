# big-dreams
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Mother's Day & Women's Day Presentation</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>

    <header>
        <h1>Welcome to Our Interactive Presentation</h1>
    </header>

    <section>
        <h2>How would you describe your mother in one word?</h2>
        <input type="text" id="userInput" placeholder="Type your word here">
        <button onclick="submitAnswer()">Submit</button>
        <p id="response"></p>
    </section>

    <section>
        <h2>Inspirational Quotes</h2>
        <div id="quoteDisplay"></div>
    </section>

    <section>
        <h2>Thank You, Mom!</h2>
        <p>Scan the QR code to leave a thank-you note for your mother.</p>
        <div id="qrcode"></div>
    </section>

    <footer>
        <p>&copy; 2025 Interactive Presentation</p>
    </footer>

    <script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"></script>
    <script src="script.js"></script>

</body>
</html>
body {
    font-family: Arial, sans-serif;
    text-align: center;
    background-color: #f9f9f9;
    color: #333;
}

header {
    background-color: #ff8c00;
    padding: 20px;
    color: white;
    font-size: 24px;
}

section {
    margin: 20px;
    padding: 20px;
    background: white;
    border-radius: 10px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

input, button {
    padding: 10px;
    margin: 10px;
}

#qrcode {
    margin-top: 20px;
}
function submitAnswer() {
    let input = document.getElementById("userInput").value.trim();
    if (input) {
        document.getElementById("response").innerText = `You described your mother as: "${input}"`;
    } else {
        document.getElementById("response").innerText = "Please enter a word.";
    }
}

// Display random inspirational quotes
const quotes = [
    "A mother’s love is endless.",
    "Women are the real architects of society.",
    "Behind every great person is a great mother.",
    "The future belongs to those who believe in the beauty of their dreams.",
    "Empowered women empower the world."
];

function displayRandomQuote() {
    let randomIndex = Math.floor(Math.random() * quotes.length);
    document.getElementById("quoteDisplay").innerText = quotes[randomIndex];
}

// Generate QR Code for the thank-you note
new QRCode(document.getElementById("qrcode"), {
    text: "https://big-dream-ops.github.io/big-dreams/",
    width: 128,
    height: 128
});

// Show a new quote every 5 seconds
setInterval(displayRandomQuote, 5000);

// Initialize the first quote
displayRandomQuote();

