<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dog Care SOP</title>
    <!-- Importing Poppins Font -->
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Poppins', sans-serif;
            background-color: #ffdbb6; /* Main Background */
            margin: 0;
            padding: 20px;
            color: #333;
        }

        .container {
            max-width: 800px;
            margin: 0 auto;
        }

        .header-section {
            text-align: center;
            margin-bottom: 30px;
        }

        h1 {
            color: #5d688a;
            font-size: 3rem;
            font-weight: 700;
            margin-bottom: 5px;
        }

        .author {
            font-size: 1.1rem;
            color: #5d688a;
            margin-bottom: 20px;
            display: block;
        }

        .intro {
            font-style: italic;
            background: white;
            padding: 15px;
            border-radius: 10px;
            margin-bottom: 30px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.05);
        }

        .section-box {
            background-color: #fff2ef; /* Section Background */
            padding: 25px;
            border-radius: 15px;
            margin-bottom: 30px;
            box-shadow: 0 4px 6px rgba(0,0,0,0.05);
        }

        h2 {
            color: #7a5a58; /* Adjusted slightly for better contrast */
            font-size: 2rem;
            font-weight: 700;
            margin-top: 0;
            border-bottom: 2px solid #7a5a58;
            padding-bottom: 10px;
        }

        ul {
            list-style-type: none;
            padding: 0;
        }

        li {
            margin-bottom: 15px;
            line-height: 1.6;
        }

        strong {
            color: #5d688a;
        }

        /* Routine Grid */
        .routine-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 10px;
        }

        .time-slot {
            background: rgba(255, 255, 255, 0.5);
            padding: 10px;
            border-radius: 8px;
            border-left: 4px solid #7a5a58;
            display: flex;
            align-items: center;
        }

        .time-label {
            font-weight: 600;
            min-width: 80px;
            color: #7a5a58;
        }

        .activity-input {
            border: none;
            background: transparent;
            font-family: 'Poppins', sans-serif;
            width: 100%;
            outline: none;
        }
    </style>
</head>
<body>

<div class="container">
    <!-- Header -->
    <div class="header-section">
        <h1>🐾 Dog Care SOP</h1>
        <span class="author">made by Poppy H.</span>
    </div>

    <!-- Intro -->
    <div class="intro">
        Welcome to the Dog Care Manual! We hope this helps first-time dog owners get started quickly. Wishing you and your dog a wonderful time together!
    </div>

    <!-- Checklist Section -->
    <div class="section-box">
        <h2>Checklist</h2>
        <p>Before bringing your dog home, please ensure you have prepared the following items:</p>
        <ul>
            <li><strong>🍴 Diet:</strong> Puppy/Adult kibble, stainless steel or ceramic food and water bowls. Please do not use gravity ball-style water bottles; they are unsuitable for dogs and prevent them from drinking enough water.</li>
            <li><strong>😴 Sleep:</strong> A comfortable bed or a pet-specific breathable cot. For dogs lacking security, use a playpen initially or buy a roofed kennel to help them feel safe.</li>
            <li><strong>🧼 Hygiene:</strong> Pet pee pads, poop bags, dog shampoo, nail clippers, and grooming scissors/clippers. If you are inexperienced or the dog is not yet comfortable with you, it is recommended to visit a professional groomer for nail trimming and haircuts.</li>
            <li><strong>🏥 Medical:</strong> Phone number and address of the nearest 24HR veterinary clinic, and a sturdy pet carrier.</li>
        </ul>
    </div>

    <!-- Daily Routine Section -->
    <div class="section-box">
        <h2>Daily Routine</h2>
        <div class="routine-grid">
            <!-- JavaScript will generate time slots from 05:00 to 00:00 -->
            <script>
                const start = 5; // 5 AM
                const end = 24;  // 12 AM
                const container = document.currentScript.parentElement;

                for (let i = start; i <= end; i++) {
                    const hour = i === 24 ? "00" : (i < 10 ? "0" + i : i);
                    
                    // Create :00 slot
                    createSlot(`${hour}:00`);
                    
                    // Create :30 slot (except for the very last one)
                    if (i < 24) {
                        createSlot(`${hour}:30`);
                    }
                }

                function createSlot(time) {
                    const div = document.createElement('div');
                    div.className = 'time-slot';
                    div.innerHTML = `<span class="time-label">${time}</span><input type="text" class="activity-input" placeholder="Add activity...">`;
                    container.appendChild(div);
                }
            </script>
        </div>
    </div>
</div>

</body>
</html>
