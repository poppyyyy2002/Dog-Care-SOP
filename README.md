<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dog Care SOP - Poppy H.</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;700&display=swap" rel="stylesheet">
    <script src="https://cdn.jsdelivr.net/npm/mermaid/dist/mermaid.min.js"></script>
    <script>mermaid.initialize({ startOnLoad: true, theme: 'neutral' });</script>
    
    <style>
        /* 設置全域背景色 */
        body {
            background-color: #ffdbb6; 
            font-family: 'Poppins', sans-serif;
            margin: 0;
            padding: 40px 20px;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        .container {
            max-width: 900px;
            width: 100%;
        }

        /* 標題 1 樣式: #5d688a, 粗體放大 */
        h1 {
            color: #5d688a;
            font-size: 3.5rem;
            font-weight: 700;
            margin-bottom: 5px;
            text-align: center;
        }

        .author {
            color: #5d688a;
            font-size: 1.2rem;
            text-align: center;
            margin-bottom: 40px;
            font-weight: 400;
        }

        .intro-text {
            text-align: center;
            font-size: 1.1rem;
            color: #333;
            margin-bottom: 50px;
            line-height: 1.6;
        }

        /* 段落區塊背景樣式: #fff2ef */
        .section-box {
            background-color: #fff2ef;
            padding: 40px;
            border-radius: 25px;
            margin-bottom: 40px;
            box-shadow: 0 10px 20px rgba(0,0,0,0.05);
        }

        /* 小標題樣式: #7a5a58, 放大加粗 */
        h2 {
            color: #7a5a58;
            font-size: 2.2rem;
            font-weight: 700;
            margin-top: 0;
            border-bottom: 2px solid #7a5a58;
            padding-bottom: 10px;
            margin-bottom: 25px;
        }

        h3 {
            color: #7a5a58;
            font-size: 1.3rem;
            margin-top: 20px;
            margin-bottom: 10px;
        }

        p, li {
            font-size: 1.05rem;
            color: #444;
            line-height: 1.7;
        }

        .warning-text {
            color: #b91c1c;
            font-weight: 600;
        }

        /* Routine 表格樣式 */
        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 20px;
        }

        th {
            background-color: #7a5a58;
            color: white;
            padding: 12px;
            text-align: left;
        }

        td {
            padding: 10px;
            border-bottom: 1px solid #e5e7eb;
        }

        .time-slot {
            font-weight: 600;
            color: #7a5a58;
            width: 120px;
        }

        .editable-cell {
            color: #666;
            font-style: italic;
        }
    </style>
</head>
<body>

<div class="container">
    <h1>🐾 Dog Care SOP</h1>
    <div class="author">made by Poppy H.</div>

    <div class="intro-text">
        Welcome to the Dog Care Guide! I hope this helps first-time dog owners get started quickly. <br>
        Wishing you and your dog a wonderful time together!
    </div>

    <div class="section-box">
        <h2>📋 Checklist</h2>
        <p>Before bringing your dog home, please ensure you have the following items ready:</p>
        
        <h3>🍖 Diet</h3>
        <ul>
            <li>Puppy or Adult dog food.</li>
            <li>Stainless steel or ceramic bowls for food and water.</li>
            <li><span class="warning-text">Important:</span> Do not use roller-ball water bottles. They prevent dogs from drinking sufficient water and can be harmful.</li>
        </ul>

        <h3>💤 Sleep</h3>
        <ul>
            <li>A comfortable pet bed or a breathable pet cot.</li>
            <li>Playpens are recommended for dogs lacking security to establish a safe space.</li>
            <li>Roofed dog houses help reduce fear for anxious dogs.</li>
        </ul>

        <h3>🧼 Hygiene</h3>
        <ul>
            <li>Pet pee pads, poop bags, and dog-specific shampoo.</li>
            <li>Nail clippers, grooming scissors, or electric clippers.</li>
            <li>Recommendation: If inexperienced, visit a professional groomer for nail trimming and haircuts initially.</li>
        </ul>

        <h3>🏥 Medical</h3>
        <ul>
            <li>Phone number and address of the nearest 24HR veterinary clinic.</li>
            <li>A sturdy pet carrier or crate for safe travel.</li>
        </ul>
    </div>

    <div class="section-box">
        <h2>🕒 Daily Routine</h2>
        <p>Standardized 30-minute block schedule (05:00 - 00:00):</p>
        
        <table>
            <thead>
                <tr>
                    <th>Time</th>
                    <th>Activity</th>
                </tr>
            </thead>
            <tbody id="routine-table">
                </tbody>
        </table>
    </div>

    <div class="section-box">
        <h2>🛡️ Health Management Flow</h2>
        <div class="mermaid">
            graph TD
                Start[Abnormal Behavior Detected] --> A{Is the dog active?}
                A -- Yes --> B[Observe for 12 hours]
                A -- Lethargic --> C{Vomiting or Diarrhea?}
                C -- Yes --> D[Contact 24HR Vet Immediately]
                C -- No --> B
        </div>
    </div>
</div>

<script>
    // 生成從 05:00 到 00:00 每半小時一格的表格
    const tableBody = document.getElementById('routine-table');
    const startHour = 5;
    const endHour = 24;

    for (let h = startHour; h <= endHour; h++) {
        for (let m of ['00', '30']) {
            if (h === 24 && m === '30') break;
            const hourDisplay = h === 24 ? '00' : (h < 10 ? '0' + h : h);
            const row = document.createElement('tr');
            
            // 填入一些範例文字
            let activity = "Free time / Rest";
            if(hourDisplay == "07" && m == "00") activity = "Morning Feeding";
            if(hourDisplay == "07" && m == "30") activity = "Morning Walk";
            if(hourDisplay == "18" && m == "00") activity = "Dinner Time";

            row.innerHTML = `
                <td class="time-slot">${hourDisplay}:${m}</td>
                <td class="editable-cell">${activity}</td>
            `;
            tableBody.appendChild(row);
            if (h === 24) break; 
        }
    }
</script>

</body>
</html>
