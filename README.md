<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Motivational Quotes</title>
</head>
<body>
    <div style="text-align: center;">
        <img src="{{ quote.image }}" alt="Motivational Image" style="max-width: 100%; height: auto;">
        <p>{{ quote.text }}</p>
        <button onclick="fetchNewQuote()">Get New Quote</button>
    </div>
    <script>
        function fetchNewQuote() {
            fetch('/new_quote', { method: 'POST' })
                .then(response => response.json())
                .then(data => {
                    document.querySelector('img').src = data.image;
                    document.querySelector('p').textContent = data.text;
                });
        }
    </script>
</body>
</html>
