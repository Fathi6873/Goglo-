<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Yusuf Dhol Secondary School</title>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        body {
            font-family: 'Roboto', sans-serif;
            margin: 0;
            padding: 0;
            background-color: #e9ecef;
            color: #343a40;
        }
        header {
            background-color: #007bff;
            color: white;
            padding: 20px;
            text-align: center;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
        }
        nav {
            margin: 10px 0;
        }
        nav a {
            margin: 0 15px;
            color: white;
            text-decoration: none;
            font-weight: 700;
            transition: color 0.3s;
        }
        nav a:hover {
            color: #ffdd57;
        }
        .container {
            width: 80%;
            margin: auto;
            display: flex;
            flex-direction: column;
            gap: 20px;
        }
        section {
            background: white;
            padding: 30px;
            margin: 10px 0;
            border-radius: 8px;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s;
        }
        section:hover {
            transform: translateY(-2px);
        }
        footer {
            text-align: center;
            padding: 15px 0;
            background-color: #007bff;
            color: white;
            position: relative;
            margin-top: 20px;
            border-top: 4px solid #ffdd57;
        }
        img {
            max-width: 100%;
            height: auto;
            border-radius: 8px;
        }
        .icon {
            width: 50px;
            height: 50px;
            vertical-align: middle;
        }
        form {
            display: flex;
            flex-direction: column;
            gap: 10px;
        }
        form input, form textarea {
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 4px;
        }
        form button {
            background-color: #007bff;
            color: white;
            padding: 10px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }
        form button:hover {
            background-color: #0056b3;
        }
        @media (max-width: 768px) {
            .container {
                width: 95%;
            }
            nav a {
                display: block;
                margin: 5px 0;
            }
        }
    </style>
</head>
<body>

    <header>
        <h1>Yusuf Dhol Secondary School</h1>
        <img src="logo.png" alt="School Logo" style="width: 100px;"/>
        <nav>
            <a href="#about">About Us</a>
            <a href="#academics">Academics</a>
            <a href="#faculty">Faculty</a>
            <a href="#events">Events</a>
            <a href="#contact">Contact Us</a>
        </nav>
    </header>

    <div class="container">
        <section id="about">
            <h2><i class="fas fa-school icon"></i> About Us</h2>
            <p>Welcome to Yusuf Dhol Secondary School - where excellence is our tradition.</p>
            <img src="about-image.jpg" alt="School Building" style="width: 100%; height: auto;"/>
        </section>
        
        <section id="academics">
            <h2><i class="fas fa-book-open icon"></i> Academics</h2>
            <p>Explore our diverse course offerings designed to nurture and develop young minds.</p>
            <img src="academics-image.jpg" alt="Academic Activities" style="width: 100%; height: auto;"/>
        </section>

        <section id="faculty">
            <h2><i class="fas fa-user-graduate icon"></i> Faculty</h2>
            <p>Meet our dedicated team of educators who are here to guide you.</p>
            <img src="faculty-image.jpg" alt="Teachers" style="width: 100%; height: auto;"/>
        </section>

        <section id="events">
            <h2><i class="fas fa-calendar-alt icon"></i> Upcoming Events</h2>
            <p>Stay tuned for upcoming events and important dates.</p>
            <button id="eventButton">Show Events</button>
            <ul id="eventList" style="display:none;">
                <li>Open House: March 10, 2023</li>
                <li>Science Fair: April 5, 2023</li>
                <li>Graduation Ceremony: June 15, 2023</li>
            </ul>
            <img src="events-image.jpg" alt="School Events" style="width: 100%; height: auto;"/>
        </section>

        <section id="contact">
            <h2><i class="fas fa-envelope icon"></i> Contact Us</h2>
            <p>For more information, feel free to reach out.</p>
            
            <form id="contactForm" onsubmit="return validateForm()">
                <label for="name">Name:</label>
                <input type="text" id="name" name="name" required aria-required="true">
                
                <label for="email">Email:</label>
                <input type="email" id="email" name="email" required aria-required="true">
                
                <label for="message">Message:</label>
                <textarea id="message" name="message" required aria-required="true"></textarea>
                
                <button type="submit">Send</button>
            </form>

            <div id="formMessage" style="color: green; margin-top: 10px;"></div>
        </section>
    </div>

    <footer>
        <p>&copy; 2023 Yusuf Dhol Secondary School. All rights reserved.</p>
    </footer>

    <script>
        document.getElementById("eventButton").onclick = function() {
            var eventList = document.getElementById("eventList");
            if (eventList.style.display === "none") {
                eventList.style.display = "block";
            } else {
                eventList.style.display = "none";
            }
        };

        function validateForm() {
            var name = document.getElementById("name").value;
            var email = document.getElementById("email").value;
            var message = document.getElementById("message").value;
            
            if (name === "" || email === "" || message === "") {
                alert("All fields must be filled out");
                return false;
            }

            document.getElementById("formMessage").innerText = "Thank you for your message, " + name + "!";
            return false;  // Prevent actual form submission for this demo
        }
    </script>

</body>
</html>
