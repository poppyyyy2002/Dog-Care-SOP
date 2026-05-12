<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dog Care SOP</title>
    <link href="https://fonts.googleapis.com/css2?family=Fredoka+One&family=Poppins:wght@400;600;700&display=swap" rel="stylesheet">
    <style>
        /* 1. 全域字體改為 Poppins */
        body {
            font-family: 'Poppins', sans-serif;
            background-color: #ffdbb6; /* 總背景色 */
            margin: 0;
            padding: 40px 20px;
            color: #333;
            line-height: 1.6;
        }

        .container {
            max-width: 900px;
            margin: 0 auto;
        }

        /* 2. 大標題樣式 */
        .header-section {
            text-align: center;
            margin-bottom: 40px;
        }

        h1 {
            font-family: 'Fredoka One', cursive; /* 標題指定字體 */
            color: #5d688a; /* 指定顏色 */
            font-size: 4.5rem; /* 放大 */
            font-weight: bold;
            margin-bottom: 5px;
            letter-spacing: 2px;
        }

        .author {
            color: #5d688a;
            font-size: 1.2rem;
            margin-top: 0;
            display: block;
            font-weight: 600;
        }

        /* 3. 預告詞 (背景不要反白) */
        .intro-text {
            color: #5d688a;
            font-size: 1.3rem;
            text-align: center;
            margin: 40px auto;
            max-width: 800px;
            font-style: italic;
            font-weight: 500;
        }

        /* 4. 內容區塊區塊樣式 */
        .section-box {
            background-color: #fff2ef; /* 區塊背景色 */
            padding: 50px;
            border-radius: 30px;
            margin-bottom: 40px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.05);
        }

        /* 5. 小標題置中放大 */
        h2 {
            color: #7a5a58; /* 指定顏色 */
            font-size: 3rem; /* 放大 */
            font-weight: bold;
            text-align: center; /* 置中 */
            margin-top: 0;
            margin-bottom: 10px;
        }

        .subtitle-note {
            color: #7a5a58;
            text-align: center;
            display: block;
            margin-bottom: 30px;
            font-weight: 600;
            font-size: 1.1rem;
        }

        /* Checklist 內容 */
        .checklist-item {
            margin-bottom: 30px;
        }

        .checklist-item strong {
            color: #7a5a58;
            font-size: 1.4rem;
            display: block;
            margin-bottom: 8px;
        }

        /* Daily Routine 網格 */
        .routine-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 15px;
        }

        .time-slot {
            background: white;
            padding: 15px 20px;
            border-radius: 12px;
            display: flex;
            align-items: center;
            border-left: 6px solid #7a5a58;
        }

        .time-label {
            font-weight: bold;
            color: #7a5a58;
            width: 80px;
            font-size: 1.1rem;
        }

        .activity-placeholder {
            color: #ccc;
            font-size: 0.9rem;
        }
    </style>
</head>
<body>

<div class="container">
    <div class="header-section">
        <h1>🐾 Dog Care SOP</h1>
        <span class="author">made by Poppy H.</span>
    </div>

    <div class="intro-text">
        Welcome to the Dog Care Manual! We hope this helps first-time dog owners get started quickly. Wishing you and your dog a wonderful time together!
    </div>

    <div class="section-box">
        <h2>Checklist</h2>
        <div class="checklist-content">
            <div class="checklist-item">
                <strong>Diet:</strong>
                Puppy/Adult kibble, stainless steel or ceramic food and water bowls. Please do not use gravity ball-style water bottles; they are unsuitable for dogs and prevent them from drinking enough water.
            </div>
            <div class="checklist-item">
                <strong>Sleep:</strong>
                A comfortable bed or a pet-specific breathable cot. For dogs lacking security, use a playpen initially or buy a roofed kennel to help them feel safe.
            </div>
            <div class="checklist-item">
                <strong>Hygiene:</strong>
                Pet pee pads, poop bags, dog shampoo, nail clippers, and grooming scissors/clippers. If you are inexperienced or the dog is not yet comfortable with you, it is recommended to visit a professional groomer for nail trimming and haircuts.
            </div>
            <div class="checklist-item">
                <strong>Medical:</strong>
                Phone number and address of the nearest 24HR veterinary clinic, and a sturdy pet carrier.
            </div>
        </div>
    </div>

    <div class="section-box">
        <h2>Daily Routine</h2>
        <span class="subtitle-note">試試看自己規劃和寶貝的每日行程吧！</span>
        
        <div class="routine-grid" id="routineGrid">
            </div>
    </div>
</div>

<script>
    // 自動生成 05:00 到 00:00 每半小時一格
    const grid = document.getElementById('routineGrid');
    for (let h = 5; h <= 24; h++) {
        const hour = h === 24 ? "00" : (h < 10 ? "0" + h : h);
        addSlot(`${hour}:00`);
        if (h < 24) addSlot(`${hour}:30`);
    }

    function addSlot(time) {
        const div = document.createElement('div');
        div.className = 'time-slot';
        div.innerHTML = `<span class="time-label">${time}</span> <span class="activity-placeholder">Click to plan...</span>`;
        grid.appendChild(div);
    }
</script>

</body>
</html>
