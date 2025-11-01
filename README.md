<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ruchit & Priya's Wedding</title>
    
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Open+Sans:wght@300;400;600;700&display=swap" rel="stylesheet">

    <style>
      
        /* --- Root Variables for Colors (Updated with purple shades) --- */
        :root {
            --primary-text: #4b0082; /* Dark purple for primary text */
            --secondary-text: #8a2be2; /* Medium purple for secondary text */
            --accent-purple: #9370db; /* Standard purple for accents */
            --accent-light-purple: #dda0dd; /* Light purple for subtle accents */
            --light-bg: #f3e5f5; /* Very light purple for backgrounds */
            --dark-bg: #6a0dad; /* Dark purple for dark elements */
            --border-light: #e1bee7; /* Light purple for borders */
            --shadow-light: rgba(138, 43, 226, 0.08);
            --shadow-hover: rgba(138, 43, 226, 0.15);
        }

        /* --- Global Styles & Fonts --- */
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Open Sans', sans-serif; /* Updated sans-serif font */
            color: var(--primary-text);
            line-height: 1.6;
            background-color: var(--light-bg); /* Use light-bg for a softer overall feel */
        }

        h1, h2 {
            font-family: 'Great Vibes', cursive; /* Updated script font for elegance */
            font-weight: normal; /* Great Vibes looks best with normal weight */
            color: var(--accent-purple); /* Purple for main headings */
        }

        h3, h4 {
            font-family: 'Open Sans', sans-serif;
            font-weight: 700;
            margin-bottom: 10px;
            color: var(--primary-text);
        }

        a {
            text-decoration: none;
            color: inherit;
            transition: color 0.3s ease; /* Smooth color transition on hover */
        }

        /* --- 1. Header & Hero Section --- */
        header {
            height: 100vh;
            min-height: 650px; /* Slightly more minimum height */
            
            /* Overlay with light purple for a unique touch */
            background-image: linear-gradient(rgba(221, 160, 221, 0.7), rgba(221, 160, 221, 0.7)), url('hero-background.jpg'); 
            background-size: cover;
            background-position: center;
            background-attachment: fixed; /* Parallax effect */
            
            display: flex;
            flex-direction: column;
            text-align: center;
            color: #fff; /* White text for contrast on purple overlay */
            position: relative; /* For the decorative elements */
            overflow: hidden; /* Hide anything overflowing from decorative elements */
        }

        /* Decorative element - subtle leaves/flourish (example: pseudo-elements) */
        header::before,
        header::after {
            content: '';
            position: absolute;
            width: 150px;
            height: 150px;
            background-repeat: no-repeat;
            opacity: 0.15; /* Slightly more visible */
            pointer-events: none;
            z-index: 1;
            background: radial-gradient(circle, var(--accent-purple) 0%, rgba(255,255,255,0) 70%); /* Purple for deco */
            border-radius: 50%;
        }
        header::before {
            top: 20px;
            left: 20px;
        }
        header::after {
            bottom: 20px;
            right: 20px;
        }


        nav {
            padding: 25px 0; /* Slightly more padding */
            background: rgba(0, 0, 0, 0.1); /* Subtle transparent background for nav */
            position: relative;
            z-index: 10; /* Ensure nav is above other elements */
        }

        nav ul {
            list-style: none;
            display: flex;
            justify-content: center;
            gap: 40px; /* More space between nav items */
        }

        nav ul li a {
            font-weight: 600; /* Bolder nav text */
            font-size: 1rem; /* Slightly larger */
            text-transform: uppercase;
            letter-spacing: 1.5px;
            color: #fff;
            position: relative;
        }

        nav ul li a::after { /* Underline effect on hover */
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0%;
            height: 2px;
            background-color: var(--accent-light-purple); /* Light purple underline */
            transition: width 0.3s ease;
        }

        nav ul li a:hover::after,
        nav ul li a.active::after { /* 'active' class for current page */
            width: 100%;
        }

        .hero-content {
            flex-grow: 1;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            padding: 20px;
            z-index: 5;
        }

        .hero-content h1 {
            font-size: 6rem; /* Larger heading */
            margin: 0;
            color: #fff; /* White for the name */
            text-shadow: 2px 2px 5px rgba(0,0,0,0.3); /* Subtle shadow for depth */
        }

        .hero-content .date {
            font-size: 1.4rem; /* Larger date */
            font-weight: 600;
            letter-spacing: 3px;
            text-transform: uppercase;
            margin-top: 10px;
            color: #fff;
        }

        .hero-content .invite {
            font-size: 1.2rem;
            margin-top: 20px;
            max-width: 80%;
            color: #eee;
            font-style: italic; /* Italic for the invite message */
        }

        /* Modernized Countdown Styling */
        #countdown {
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 20px;
            margin: 30px 0;
            flex-wrap: wrap;
        }

        #countdown div {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            width: 120px;
            height: 120px;
            background: linear-gradient(135deg, var(--accent-purple), var(--accent-light-purple));
            border-radius: 50%;
            box-shadow: 0 8px 20px rgba(138, 43, 226, 0.3);
            color: #fff;
            font-weight: bold;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        #countdown div::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,255,255,0.1) 0%, transparent 70%);
            animation: pulse 2s infinite;
            border-radius: 50%;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); opacity: 0.5; }
            50% { transform: scale(1.1); opacity: 1; }
        }

        #countdown div:hover {
            transform: scale(1.05);
            box-shadow: 0 12px 30px rgba(138, 43, 226, 0.4);
        }

        #countdown div span:first-child {
            font-size: 2.5em;
            line-height: 1;
            z-index: 1;
            position: relative;
        }

        #countdown div span:last-child {
            font-size: 0.8em;
            font-weight: 400;
            text-transform: uppercase;
            letter-spacing: 1px;
            margin-top: 5px;
            z-index: 1;
            position: relative;
        }

        /* Buttons */
        .btn-main {
            font-size: 1rem;
            padding: 12px 25px; /* More padding */
            border: 2px solid #fff; /* White border */
            border-radius: 30px; /* Pill shape (new!) */
            background: transparent;
            color: #fff;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 1px;
            transition: all 0.3s ease;
        }

        .btn-main:hover {
            background: #fff;
            color: var(--accent-purple); /* Purple text on hover */
            box-shadow: 0 8px 15px rgba(0,0,0,0.2);
            transform: translateY(-2px); /* Slight lift effect */
        }

        .btn-secondary {
            display: inline-block;
            font-size: 0.85rem;
            padding: 10px 18px;
            border: 1px solid var(--accent-purple); /* Purple border */
            border-radius: 20px; /* Rounded corners */
            background: var(--light-bg);
            color: var(--accent-purple); /* Purple text */
            font-weight: 600;
            margin: 10px 0;
            transition: all 0.3s ease;
            box-shadow: 0 2px 5px rgba(0,0,0,0.05);
        }

        .btn-secondary:hover {
            background: var(--accent-purple); /* Purple on hover */
            color: #fff;
            box-shadow: 0 4px 10px rgba(0,0,0,0.1);
        }

        /* --- 2. Marriage Ceremonies Section --- */
        #events {
            padding: 80px 20px; /* More vertical padding */
            text-align: center;
            background-color: var(--light-bg); /* Light background for the section */
        }

        #events h2 {
            font-size: 4.5rem; /* Larger heading */
            margin-bottom: 50px;
            position: relative;
        }
        #events h2::after { /* Decorative underline */
            content: '';
            position: absolute;
            bottom: -15px;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 2px;
            background-color: var(--accent-purple); /* Purple underline */
        }


        .events-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); /* Flexible columns */
            gap: 40px; /* More space between cards */
            max-width: 1200px; /* Wider grid */
            margin: 0 auto;
            text-align: left;
        }

        .event-card {
            border: 1px solid var(--border-light);
            border-radius: 12px; /* More rounded corners */
            padding: 30px; /* More padding */
            box-shadow: 0 5px 20px var(--shadow-light); /* Stronger, softer shadow */
            background-color: #fff;
            transition: transform 0.3s ease, box-shadow 0.3s ease; /* Hover effects */
            display: flex; /* Flexbox for internal alignment */
            flex-direction: column;
        }

        .event-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 30px var(--shadow-hover);
        }

        .event-card h3 {
            font-size: 1.4rem;
            color: var(--accent-purple); /* Purple for event titles */
            margin-bottom: 15px;
            border-bottom: 1px solid var(--border-light); /* Subtle separator */
            padding-bottom: 10px;
        }

        .event-card h4 {
            font-size: 1rem;
            color: var(--accent-light-purple); /* Light purple for location subtitles */
            text-transform: uppercase;
            margin-top: 20px;
            margin-bottom: 8px;
            letter-spacing: 0.5px;
        }

        .event-card .time-date {
            display: flex;
            justify-content: space-between;
            font-weight: 600;
            color: var(--secondary-text);
            margin-bottom: 15px;
            flex-wrap: wrap; 
            font-size: 0.95rem;
        }
        .event-card .time-date span {
            display: flex;
            align-items: center;
            gap: 5px;
        }
        .event-card .time-date span::before { /* Icon replacement example */
             content: ''; /* Or use font-awesome icons */
             width: 16px;
             height: 16px;
             display: inline-block;
             background-size: contain;
             margin-right: 5px;
             vertical-align: middle;
        }
        .event-card .time-date span:first-child::before {
            background-image: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="%239370db"><path d="M19 4h-1V2h-2v2H8V2H6v2H5c-1.11 0-1.99.9-1.99 2L3 20c0 1.1.89 2 2 2h14c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 16H5V9h14v11zM5 7V6h14v1H5z"/></svg>'); /* Purple icon */
        }
        .event-card .time-date span:last-child::before {
            background-image: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="%239370db"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm0 18c-4.41 0-8-3.59-8-8s3.59-8 8-8 8 3.59 8 8-3.59 8-8 8zm.5-13H11v6l5.25 3.15.75-1.23-4.5-2.67z"/></svg>'); /* Purple icon */
        }


        .event-card .address {
            font-size: 0.9rem;
            color: var(--secondary-text);
            margin-bottom: 15px;
        }

        .event-card .map-image {
            width: 100%;
            border-radius: 8px;
            margin-top: auto; /* Pushes button to the bottom if content varies */
            border: 1px solid var(--border-light);
            object-fit: cover; /* Ensures image fills space nicely */
            height: 150px; /* Fixed height for consistency */
            margin-bottom: 15px; /* Space between map and button */
        }
        
        .event-card .btn-secondary {
            align-self: flex-start; /* Align button to the left */
        }

        /* --- 3. Gallery Section --- */
        #gallery {
            padding: 80px 20px;
            background: #fff; /* White background */
            text-align: center;
        }

        #gallery h2 {
            font-size: 4.5rem;
            margin-bottom: 50px;
            position: relative;
        }
        #gallery h2::after { /* Decorative underline */
            content: '';
            position: absolute;
            bottom: -15px;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 2px;
            background-color: var(--accent-purple); /* Purple underline */
        }

        .gallery-grid {
            column-count: 2; 
            column-gap: 20px; /* More space between columns */
            max-width: 1500px;
            margin: 0 auto;
        }

        .gallery-grid img {
            width: 100%;
            display: block;
            border-radius: 10px; /* More rounded corners */
            margin-bottom: 20px; /* More space between images */
            box-shadow: 0 5px 15px var(--shadow-light); /* Subtle shadow */
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        
        .gallery-grid img:hover {
            transform: scale(1.02); /* Slight zoom on hover */
            box-shadow: 0 8px 20px var(--shadow-hover);
        }

        /* --- 4. Back to Top Button --- */
        .back-to-top {
            position: fixed;
            bottom: 30px; /* Slightly higher */
            right: 30px; /* Slightly more to the right */
            background: var(--accent-purple); /* Purple background */
            color: white;
            width: 50px; /* Larger button */
            height: 50px;
            border-radius: 50%;
            text-align: center;
            line-height: 50px;
            font-size: 1.8rem; /* Larger arrow */
            opacity: 0.8;
            transition: opacity 0.3s ease, background 0.3s ease, transform 0.3s ease;
            box-shadow: 0 4px 10px rgba(0,0,0,0.2);
            z-index: 99;
        }

        .back-to-top:hover {
            opacity: 1;
            background: var(--accent-light-purple); /* Light purple on hover */
            transform: translateY(-3px); /* Slight lift */
        }


        /* --- Responsive Design --- */
        @media (min-width: 768px) {
            .hero-content h1 {
                font-size: 8rem;
            }
            .hero-content .invite {
                max-width: 60%;
            }
            .events-grid {
                grid-template-columns: 1fr 1fr; 
            }
            .gallery-grid {
                column-count: 3;
           </style>
</head>
<body>

    <header id="home">
        <nav>
            <ul>
                <li><a href="#home" class="active">Home</a></li> <li><a href="#events">Events</a></li>
                <li><a href="#gallery">Gallery</a></li>
            </ul>
        </nav>

        <div class="hero-content">
            <h1>Ruchit ❤ Priya</h1>
            <p class="date">06 DEC 2025</p>
            <H3>"We invite you to celebrate our wedding"<H3>




            <div id="countdown">
        <div id="days-container">
            <span id="days">0</span>
            <span>Days</span>
        </div>
        <div id="hours-container">
            <span id="hours">0</span>
            <span>Hours</span>
        </div>
        <div id="minutes-container">
            <span id="minutes">0</span>
            <span>Minutes</span>
        </div>
        
    </div>

            <a href="#" class="btn-main">View Livestream</a>
        </div>
    </header>

    <main>
        <section id="events">
            <h2>Marriage Ceremonies</h2>
            <div class="events-grid">
                     
                <div class="event-card">
                    <h3>GANESH STHAPAN</h3>
                    <p class="time-date">
                        <span>📅 05th Dec 2025</span>
                        <span>🕒 08:00 AM</span>
                    </p>
                    <h4>AT OUR RESIDENCE</h4>
                    <a href="https://maps.app.goo.gl/yd2VBjmuptZoEWbRA?g_st=aw">Click For Address</a>
                </div>

       
           
                <div class="event-card">
                    <h3>MAMERU</h3>
                    <p class="time-date">
                        <span>📅 05th Dec 2025</span>
                        <span>🕒 10:00 AM</span>
                    </p>
                    <h4>AT OUR RESIDENCE</h4>
                    <a href="https://maps.app.goo.gl/yd2VBjmuptZoEWbRA?g_st=aw">Click For Address</a>
                </div>



                <div class="event-card">
                    <h3>BHOJAN SAMARAMBH</h3>
                    <p class="time-date">
                        <span>📅 05th Dec 2025</span>
                        <span>🕒 11:00 AM</span>
                    </p>
                    <h4>AT OUR RESIDENCE</h4>
                    <a href="https://maps.app.goo.gl/yd2VBjmuptZoEWbRA?g_st=aw">Click For Address</a>
                    </div>


                 <div class="event-card">
                    <h3>GRAH SANTI</h3>
                    <p class="time-date">
                        <span>📅 05th Dec 2025</span>
                        <span>🕒 01:00 PM</span>
                    </p>
                    <h4>AT OUR RESIDENCE</h4>
                    <a href="https://maps.app.goo.gl/yd2VBjmuptZoEWbRA?g_st=aw">Click For Address</a>
                   </div>


                <div class="event-card">
                    <h3>VARGODO</h3>
                    <p class="time-date">
                        <span>📅 05th Dec 2025</span>
                        <span>🕒 07:30 PM</span>
                    </p>
                    <h4>AT OUR RESIDENCE</h4>
                    <a href="https://maps.app.goo.gl/yd2VBjmuptZoEWbRA?g_st=aw">Click For Address</a>
                    </div>

                <div class="event-card">
                    <h3>JAAN PRASTHAN</h3>
                    <p class="time-date">
                        <span>📅 06th Dec 2025</span>
                        <span>🕒 09:30 AM</span>
                    </p>
                    <h4>AT OUR RESIDENCE</h4>
                   <a href="https://maps.app.goo.gl/yd2VBjmuptZoEWbRA?g_st=aw">Click For Address</a>
                    </div>

                <div class="event-card">
                    <h3>HAST MELAP</h3>
                    <p class="time-date">
                        <span>📅 06th Dec 2025</span>
                        <span>🕒 12:39 PM</span>
                    </p>
                    <h4>GAYATRI MANDIR HALL</h4>
                    
                     <a href="https://maps.app.goo.gl/LrfYLEMrQ6uxD1SB8?g_st=aw">Click For Address</a>
                    </div>


                 <div class="event-card">
                    <h3>RECEPTION VENUE</h3>
                    <p class="time-date">
                        <span>📅 08th Dec 2025</span>
                        <span>🕒 06:00 PM</span>
                    </p>
                    <h4>SAPTSRUNGI PARTY PLOT</h4>
                     <a href="https://maps.app.goo.gl/aNvEGUtDKKNqi9zy5?g_st=aw">Click For Address</a>
                 </div>

               
            </div>
        </section>

        <section id="gallery">
            <h2>Gallery</h2>
            <div class="gallery-grid">
                <img src="1.jpg" alt="Couple photo 1">
                <img src="2.jpg" alt="Couple photo 2">
                <img src="3.jpg" alt="Couple photo 3">
                <img src="4.jpg" alt="Couple photo 4">
                </div>
        </section>
    </main>

    <a href="#home" class="back-to-top">↑</a>

 <script>
        // Set the date we're counting down to
        // Note: Months are 0-indexed, so December is 11
        const countdownDate = new Date("2025-12-06T00:00:00").getTime();

        // Update the countdown every 1 second
        const interval = setInterval(function() {

            // Get today's date and time
            const now = new Date().getTime();

            // Find the time difference between now and the countdown date
            const distance = countdownDate - now;

            // Time calculations for days, hours, minutes, and seconds
            const days = Math.floor(distance / (1000 * 60 * 60 * 24));
            const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
            const seconds = Math.floor((distance % (1000 * 60)) / 1000);

            // Display the result in the elements with their respective IDs
            // We use String().padStart(2, '0') to add a leading zero if the number is less than 10
            document.getElementById("days").innerHTML = days;
            document.getElementById("hours").innerHTML = String(hours).padStart(2, '0');
            document.getElementById("minutes").innerHTML = String(minutes).padStart(2, '0');
            document.getElementById("seconds").innerHTML = String(seconds).padStart(2, '0');

            // If the countdown is finished, write some text
            if (distance < 0) {
                clearInterval(interval);
                document.getElementById("countdown").innerHTML = "<h2>The day is here!</h2>";
            }
        }, 1000); // 1000 milliseconds = 1 second
    </script>


    </body>
</html>




