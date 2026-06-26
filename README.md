# For-aadya
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Our Little World</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght@600&family=Poppins:wght@300;400;600&display=swap');

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Poppins', sans-serif;
            background-color: #fff5f5;
            color: #4a4a4a;
            overflow-x: hidden;
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            background: linear-gradient(180deg, #ffe3e3 0%, #fff5f5 100%);
            padding: 20px;
        }

        .hero h1 {
            font-family: 'Dancing Script', cursive;
            font-size: 3.5rem;
            color: #ff6b6b;
            margin-bottom: 10px;
        }

        .hero p {
            font-size: 1.1rem;
            letter-spacing: 2px;
            text-transform: uppercase;
            color: #888;
        }

        /* Counter Section */
        .counter-container {
            padding: 60px 20px;
            text-align: center;
            background: #fff;
            margin: 40px 20px;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(255, 107, 107, 0.05);
        }

        .counter-container h2 {
            font-size: 1.5rem;
            margin-bottom: 20px;
            color: #ff6b6b;
        }

        #timer {
            font-size: 2rem;
            font-weight: 600;
            color: #333;
        }

        /* Photo Gallery */
        .gallery {
            padding: 40px 20px;
            max-width: 1000px;
            margin: 0 auto;
        }

        .gallery h2 {
            text-align: center;
            font-family: 'Dancing Script', cursive;
            font-size: 3rem;
            color: #ff6b6b;
            margin-bottom: 30px;
        }

        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
        }

        .polaroid {
            background: white;
            padding: 15px;
            padding-bottom: 25px;
            box-shadow: 0 10px 20px rgba(0,0,0,0.05);
            border-radius: 4px;
            transform: rotate(-1deg);
            transition: transform 0.3s ease;
        }

        .polaroid:nth-child(even) {
            transform: rotate(1.5deg);
        }

        .polaroid:hover {
            transform: scale(1.03) rotate(0deg);
        }

        .polaroid img {
            width: 100%;
            height: 250px;
            object-fit: cover;
            border-radius: 2px;
        }

        .polaroid .caption {
            font-family: 'Dancing Script', cursive;
            font-size: 1.5rem;
            text-align: center;
            margin-top: 15px;
            color: #555;
        }

        /* Interactive Letter */
        .letter-section {
            padding: 80px 20px;
            display: flex;
            flex-direction: column;
            align-items: center;
            background: linear-gradient(180deg, #fff5f5 0%, #ffe3e3 100%);
        }

        .envelope {
            background: #ff8787;
            width: 300px;
            height: 200px;
            border-radius: 10px;
            display: flex;
            justify-content: center;
            align-items: center;
            cursor: pointer;
            color: white;
            font-weight: 600;
            box-shadow: 0 10px 20px rgba(0,0,0,0.1);
            transition: transform 0.3s;
        }

        .envelope:hover {
            transform: translateY(-5px);
        }

        .paper {
            display: none;
            max-width: 600px;
            background: white;
            padding: 40px;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.05);
            margin-top: 20px;
            line-height: 1.8;
            text-align: center;
        }

        .paper p {
            margin-bottom: 20px;
        }

        .heart {
            color: #ff6b6b;
            font-size: 1.5rem;
        }
    </style>
</head>
<body>

    <!-- Hero Section -->
    <section class="hero">
        <h1>Aadya & Tanish</h1>
        <p>Our Little World</p>
    </section>

    <!-- Relationship Timer -->
    <section class="counter-container">
        <h2>Time spent loving you:</h2>
        <div id="timer">Loading our memories...</div>
    </section>

    <!-- Photo Gallery -->
    <section class="gallery">
        <h2>Caught in the Moment</h2>
        <div class="grid">
            <!-- Photo 1 -->
            <div class="polaroid">
                <!-- Replace 'photo1.jpg' with your actual image file name later -->
                <img src="photo1.jpg" alt="Memory 1">
                <div class="caption">Favorite Day</div>
            </div>
            <!-- Photo 2 -->
            <div class="polaroid">
                <img src="photo2.jpg" alt="Memory 2">
                <div class="caption">The Way You Smile</div>
            </div>
            <!-- Photo 3 -->
            <div class="polaroid">
                <img src="photo3.jpg" alt="Memory 3">
                <div class="caption">Forever to Go</div>
            </div>
        </div>
    </section>

    <!-- Interactive Letter -->
    <section class="letter-section">
        <div class="envelope" id="envelope" onclick="openLetter()">
            Click to open my letter 💌
        </div>
        <div class="paper" id="paper">
            <p>From the quietest moments to our loudest laughs, being with you has completely changed my world, Aadya. You have this incredible way of making everything brighter just by being in it.</p>
            <p>Looking back at all our photos and memories, I’m just reminded of how incredibly lucky I am to have you by my side. You are my safe space, my favorite person, and the absolute best part of every single day.</p>
            <p>Thank you for making every moment feel like an adventure. I love you, always. <span class="heart">♥</span></p>
        </div>
    </section>

    <script>
        // RELATIONSHIP TIMER CONFIGURATION
        // Set your anniversary date below: Year, Month (0-11, Jan=0, Feb=1, etc), Day
        // Example: February 14, 2025 -> new Date(2025, 1, 14)
        const anniversaryDate = new Date(2025, 1, 14); 

        function updateTimer() {
            const now = new Date();
            const difference = now - anniversaryDate;

            const days = Math.floor(difference / (1000 * 60 * 60 * 24));
            const hours = Math.floor((difference % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((difference % (1000 * 60 * 60)) / (1000 * 60));
            const seconds = Math.floor((difference % (1000 * 60)) / 1000);

            document.getElementById('timer').innerHTML = 
                `${days} Days, ${hours} Hours, ${minutes} Mins, ${seconds} Secs`;
        }

        setInterval(updateTimer, 1000);
        updateTimer();

        // Interactive Letter Function
        function openLetter() {
            document.getElementById('envelope').style.display = 'none';
            document.getElementById('paper').style.display = 'block';
        }
    </script>
</body>
</html>
