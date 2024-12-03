<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Online Shop</title>
    <style>
        /* General Styles */
        body {
            font-family: 'Arial', sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f9;
            color: #333;
        }

        header {
            background-color: #007B55;
            padding: 30px 0;
            text-align: center;
            color: white;
            font-size: 32px;
            font-weight: bold;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }

        .container {
            max-width: 1200px;
            margin: 40px auto;
            padding: 0 20px;
        }

        .product {
            background: #fff;
            border-radius: 10px;
            padding: 25px;
            margin-bottom: 30px;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
            text-align: center;
        }

        .product h3 {
            font-size: 28px;
            color: #333;
            margin-bottom: 20px;
        }

        .product p {
            font-size: 18px;
            color: #555;
            margin-bottom: 20px;
        }

        .product .price-display {
            font-size: 22px;
            font-weight: bold;
            color: #4CAF50;
            margin-top: 20px;
            display: none; /* Hidden by default */
        }

        .contact {
            margin-top: 20px;
            display: none; /* Hidden by default */
        }

        .contact a {
            font-size: 18px;
            padding: 12px 30px;
            text-decoration: none;
            border-radius: 8px;
            display: inline-block;
            margin: 10px 10px;
            font-weight: bold;
            background-color: #25D366; /* WhatsApp green */
            color: white;
            transition: background-color 0.3s ease;
        }

        .contact a:hover {
            opacity: 0.8;
        }

        select {
            padding: 12px;
            font-size: 16px;
            border-radius: 8px;
            border: 1px solid #ddd;
            width: 220px;
            margin: 10px 0;
        }

        footer {
            margin-top: 60px;
            padding: 30px 20px;
            text-align: center;
            background-color: #333;
            color: white;
            font-size: 14px;
        }

        footer a {
            color: #4CAF50;
            text-decoration: none;
        }

        footer a:hover {
            text-decoration: underline;
        }
    </style>
</head>
<body>
    <header>Online Shop</header>

    <div class="container">
        <!-- Ranked Product -->
        <div class="product">
            <h3>Ranked</h3>
            <p>Reach Master! Select your current rank.</p>
            <div class="dropdown">
                <label for="rank-select">Select your rank:</label>
                <select id="rank-select">
                    <option value="40">Bronze 1, 2, 3</option>
                    <option value="36">Silver 1, 2, 3</option>
                    <option value="32">Gold 1, 2, 3</option>
                    <option value="31">Diamond 1</option>
                    <option value="29">Diamond 2</option>
                    <option value="27">Diamond 3</option>
                    <option value="25">Mythic 1</option>
                    <option value="23">Mythic 2</option>
                    <option value="22">Mythic 3</option>
                    <option value="20">Legendary 1</option>
                    <option value="17">Legendary 2</option>
                    <option value="14">Legendary 3</option>
                </select>
            </div>
            <p class="price-display" id="rank-price-display"></p>
            <div class="contact" id="rank-contact">
                <a href="https://wa.me/message/2GZG735AETJPI1" target="_blank">Contact on WhatsApp</a>
            </div>
        </div>

        <!-- Brawler Product -->
        <div class="product">
            <h3>Brawler 🏆</h3>
            <p>Choose your current rank and the rank you want.</p>
            <div class="dropdown">
                <label for="current-brawler">Current rank:</label>
                <select id="current-brawler">
                    <option value="10">0</option>
                    <option value="9">100</option>
                    <option value="8">200</option>
                    <option value="7">300</option>
                    <option value="6">400</option>
                    <option value="5">500</option>
                    <option value="4">600</option>
                    <option value="3">700</option>
                    <option value="2">800</option>
                    <option value="1">900</option>
                    <option value="0">1000+</option>
                </select>
            </div>
            <div class="dropdown">
                <label for="desired-brawler">Desired rank:</label>
                <select id="desired-brawler">
                    <option value="7">1100</option>
                    <option value="12">1200</option>
                    <option value="18">1300</option>
                    <option value="24">1400</option>
                    <option value="28">1500</option>
                    <option value="34">1600</option>
                    <option value="38">1700</option>
                    <option value="44">1800</option>
                    <option value="50">1900</option>
                    <option value="59">2000</option>
                </select>
            </div>
            <p class="price-display" id="brawler-price-display"></p>
            <div class="contact" id="brawler-contact">
                <a href="https://wa.me/message/2GZG735AETJPI1" target="_blank">Contact on WhatsApp</a>
            </div>
        </div>
    </div>

    <footer>
        <p>© 2024 Online Shop. All rights reserved.</p>
        <p>Using this site means you agree to our <a href="#">terms and conditions</a>.</p>
    </footer>

    <script>
        // Ranked Price Calculation
        const rankSelect = document.getElementById("rank-select");
        const rankPriceDisplay = document.getElementById("rank-price-display");
        const rankContact = document.getElementById("rank-contact");

        rankSelect.addEventListener("change", () => {
            const selectedPrice = rankSelect.value;
            rankPriceDisplay.textContent = `Price: €${selectedPrice}`;
            rankPriceDisplay.style.display = "block";
            rankContact.style.display = "block";
        });

        // Brawler Price Calculation
        const currentBrawler = document.getElementById("current-brawler");
        const desiredBrawler = document.getElementById("desired-brawler");
        const brawlerPriceDisplay = document.getElementById("brawler-price-display");
        const brawlerContact = document.getElementById("brawler-contact");

        function updateBrawlerPrice() {
            const currentPrice = parseInt(currentBrawler.value);
            const desiredPrice = parseInt(desiredBrawler.value);
            const totalPrice = currentPrice + desiredPrice;
            brawlerPriceDisplay.textContent = `Price: €${totalPrice}`;
            brawlerPriceDisplay.style.display = "block";
            brawlerContact.style.display = "block";
        }

        currentBrawler.addEventListener("change", updateBrawlerPrice);
        desiredBrawler.addEventListener("change", updateBrawlerPrice);
    </script>
</body>
</html>
