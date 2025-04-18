<!DOCTYPE html>
<html>
<head>
    <title>3D Happy Birthday Book</title>
    <style type="text/css">
        body {
            height: 100%;
            margin: 0;
            background-image: url('https://i.postimg.cc/W4wrpGWZ/dd00d1723df7d1cfd492b8c64e92de08.jpg');
            background-size: cover;
            background-position: center;
            display: flex;
            justify-content: center;
            align-items: center;
            background-color: #f4f4f4;
        }

        .scene {
            perspective: 1200px;
            width: 320px;
            height: 600px; /* Increased height for the book */
        }

        .book {
            position: relative;
            width: 100%;
            height: 100%;
            transform-style: preserve-3d;
            transition: transform 1s ease-in-out;
            cursor: pointer;
            background: rgba(255, 255, 255, 0.3);
            border-radius: 12px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
        }

        .book:hover {
            transform: rotateY(-180deg);
        }

        .book .side {
            position: absolute;
            width: 100%;
            height: 100%;
            backface-visibility: hidden;
            border-radius: 12px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
            background: rgba(255, 255, 255, 0.3);
        }

        /* Front side */
        .book .front {
            background: linear-gradient(to bottom, rgba(255, 255, 255, 0.3), rgba(255, 255, 0, 0.1));
            display: flex;
            justify-content: center;
            align-items: center;
            border: 10px solid #9612eb;
            color: white;
            text-align: center;
            flex-direction: column;
        }

        /* Back side */
        .book .back {
            background: rgba(0, 0, 0, 0);
            transform: rotateY(180deg);
            display: flex;
            justify-content: center;
            align-items: center;
            text-align: center;
        }

        /* Add photo to the front */
        .imgset {
            position: relative;
            z-index: 1;
            margin-top: 20px;
        }

        .imgset img {
            width: 80%;
            border-radius: 10px;
            box-shadow: 0px 6px 11px 7px rgba(0, 0, 0, 0.22);
        }

        .text-container {
            padding: 20px;
            text-align: center;
        }

        .text-container #head {
            font-family: 'Nobile', sans-serif;
            font-size: 2em;
            color: white;
            text-shadow: 2px 2px 10px rgba(0, 0, 0, 0.7);
            margin-top: 20px;
        }

        .text-container p {
            font-size: 1.1em;
            color: #331717;
            font-style: italic;
            margin-top: 20px;
        }

        .text-container h5 {
            color: #9612eb;
            margin-top: 5px;
        }
    </style>
</head>
<body>

<div class="scene">
    <div class="book">
        <!-- Front side -->
        <div class="side front">
            <div class="imgset">
                <!-- Image above the text -->
                <img id="birthday-img" src="https://i.postimg.cc/rpNrQyML/IMG-20250323-230931.jpg" alt="Birthday Image">
            </div>
            <div class="text-container">
                <p id="head">Happy Birthday Arpan!</p>
            </div>
        </div>

        <!-- Back side -->
        <div class="side back">
            <div class="text-container">
                <p>Happy Birthday, ARPAN (AR7)!<br>
                    Wishing you a day filled with love, laughter, and unforgettable memories. May this year bring you success, happiness, and all your heart desires. Enjoy your special day to the fullest and once again Happy Birthday Arpan Ladve!
                </p>
            </div>
        </div>
    </div>
</div>

<script>
    let images = [
        "https://i.postimg.cc/50ptTpPP/IMG-20250324-WA0006.jpg",
        "https://i.postimg.cc/B6J6mRCL/IMG-20250324-WA0008.jpg",
        "https://i.postimg.cc/R07hQvwx/IMG-20250324-WA0010.jpg",
        "https://i.postimg.cc/bvcdtZDR/IMG-20250324-WA0012.jpg",
        "https://i.postimg.cc/Ghf4b7bV/IMG-20250324-WA0014.jpg",
        "https://i.postimg.cc/XYypqfJJ/IMG-20250324-WA0016.jpg",
        "https://i.postimg.cc/Fszf55X0/IMG-20250324-WA0018.jpg",
        "https://i.postimg.cc/fWB3rWpw/IMG-20250324-WA0019.jpg",
        "https://i.postimg.cc/yd6S5q83/IMG-20250323-230907.jpg",
        "https://i.postimg.cc/25DWQLpw/IMG-20250323-230919.jpg",
        "https://i.postimg.cc/rpNrQyML/IMG-20250323-230931.jpg"
    ];

    let index = 0;
    function changeImage() {
        document.getElementById('birthday-img').src = images[index];
        index = (index + 1) % images.length; // Loop back to the first image after the last one
    }

    setInterval(changeImage, 3000); // Change image every 3 seconds
</script>

</body>
</html>
