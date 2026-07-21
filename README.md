<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Birthday Muskan</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        @import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700;900&family=Poppins:wght@300;400;500;600;700&display=swap');

        body {
            font-family: 'Poppins', sans-serif;
            background: linear-gradient(135deg, #1a1a2e 0%, #16213e 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            min-height: 100vh;
            padding: 20px;
            overflow-x: hidden;
        }

        .container {
            width: 100%;
            max-width: 1000px;
        }

        .book-wrapper {
            perspective: 1000px;
            height: 600px;
            margin-bottom: 40px;
        }

        .book {
            background: #f5f5f5;
            border-radius: 15px;
            box-shadow: 0 30px 80px rgba(0, 0, 0, 0.5), inset 0 1px 0 rgba(255, 255, 255, 0.6);
            height: 100%;
            display: flex;
            position: relative;
            overflow: hidden;
        }

        .book::before {
            content: '';
            position: absolute;
            left: 0;
            top: 0;
            bottom: 0;
            width: 20px;
            background: linear-gradient(to right, rgba(0, 0, 0, 0.1), transparent);
            z-index: 10;
        }

        .pages-container {
            flex: 1;
            position: relative;
            overflow: hidden;
            display: flex;
        }

        .page {
            min-width: 100%;
            padding: 50px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            position: relative;
            transition: opacity 0.6s ease;
            opacity: 0;
            pointer-events: none;
        }

        .page.active {
            opacity: 1;
            pointer-events: auto;
        }

        /* Page 1 - Cover */
        .page1 {
            background: linear-gradient(135deg, #2d1b69 0%, #6a3093 50%, #d946ef 100%);
            color: white;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .page1::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background-image: 
                radial-gradient(circle at 20% 50%, rgba(255, 255, 255, 0.1) 0%, transparent 50%),
                radial-gradient(circle at 80% 80%, rgba(255, 215, 0, 0.15) 0%, transparent 50%);
            pointer-events: none;
        }

        .page1-content {
            position: relative;
            z-index: 2;
        }

        .page1 .subtitle {
            font-size: 18px;
            font-weight: 300;
            letter-spacing: 4px;
            margin-bottom: 20px;
            opacity: 0.9;
            text-transform: uppercase;
        }

        .page1 .title {
            font-family: 'Playfair Display', serif;
            font-size: 72px;
            font-weight: 900;
            margin: 20px 0;
            text-shadow: 2px 4px 20px rgba(0, 0, 0, 0.3);
        }

        .page1 .name {
            color: #ffd700;
            font-size: 80px;
            font-weight: 900;
            font-style: italic;
            text-shadow: 2px 4px 20px rgba(0, 0, 0, 0.4);
        }

        .page1 .emoji-large {
            font-size: 60px;
            margin: 30px 0;
            animation: bounce 2s infinite;
        }

        .page1 .quote {
            font-size: 18px;
            font-style: italic;
            margin-top: 30px;
            line-height: 1.8;
            font-weight: 300;
        }

        /* Page 2 - Crime Partner */
        .page2 {
            background: linear-gradient(135deg, #fef3e2 0%, #f5e6d3 100%);
            color: #4a3728;
        }

        .page-title {
            font-family: 'Playfair Display', serif;
            font-size: 48px;
            margin-bottom: 30px;
            color: #6a3093;
        }

        .page2-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 40px;
            align-items: center;
        }

        .page2-text h2 {
            font-family: 'Playfair Display', serif;
            font-size: 42px;
            color: #6a3093;
            margin-bottom: 25px;
        }

        .page2-text p {
            font-size: 16px;
            line-height: 1.9;
            margin-bottom: 20px;
            color: #4a3728;
        }

        .page2-text .highlight {
            color: #d946ef;
            font-weight: 600;
        }

        .page2-image {
            font-size: 120px;
            text-align: center;
            animation: float 3s ease-in-out infinite;
        }

        .emoji-star {
            color: #ffd700;
            margin: 0 8px;
        }

        /* Page 3 - You're */
        .page3 {
            background: linear-gradient(135deg, #c7ceea 0%, #b5d0f5 50%, #a8d8ea 100%);
            color: #2c3e50;
        }

        .feature-box {
            background: rgba(255, 255, 255, 0.7);
            padding: 20px;
            margin: 15px 0;
            border-left: 5px solid #d946ef;
            border-radius: 5px;
            font-size: 16px;
            line-height: 1.7;
        }

        .feature-icon {
            font-size: 24px;
            margin-right: 12px;
            vertical-align: middle;
        }

        /* Page 4 - Code & Learning */
        .page4 {
            background: linear-gradient(135deg, #ffeaa7 0%, #fdcb6e 50%, #e17055 100%);
            color: #2d3436;
        }

        .page4 .page-title {
            color: #d63031;
            margin-bottom: 30px;
        }

        .code-block {
            background: rgba(0, 0, 0, 0.8);
            color: #00ff00;
            padding: 25px;
            border-radius: 10px;
            font-family: 'Courier New', monospace;
            font-size: 14px;
            line-height: 1.8;
            margin: 25px 0;
            border: 2px solid #d946ef;
            box-shadow: inset 0 0 20px rgba(0, 0, 0, 0.5);
        }

        .code-block .keyword { color: #ff00ff; }
        .code-block .string { color: #00ffff; }
        .code-block .tag { color: #ffff00; }

        .loading-bar {
            width: 100%;
            height: 8px;
            background: rgba(0, 0, 0, 0.2);
            border-radius: 10px;
            margin-top: 20px;
            overflow: hidden;
        }

        .loading-fill {
            height: 100%;
            background: linear-gradient(90deg, #d946ef, #ffd700);
            width: 99%;
            border-radius: 10px;
        }

        /* Page 5 - Dreams */
        .page5 {
            background: linear-gradient(135deg, #a8edea 0%, #fed6e3 100%);
            color: #2c3e50;
        }

        .page5 .page-title {
            color: #d946ef;
        }

        .dream-text {
            background: rgba(255, 255, 255, 0.8);
            padding: 30px;
            border-radius: 15px;
            font-size: 18px;
            line-height: 2;
            margin: 20px 0;
            font-weight: 300;
        }

        .dream-text strong {
            color: #6a3093;
            font-weight: 600;
        }

        .checklist {
            margin-top: 30px;
            font-size: 16px;
        }

        .checklist-item {
            margin: 15px 0;
            padding-left: 30px;
            position: relative;
        }

        .checklist-item::before {
            content: '✓';
            position: absolute;
            left: 0;
            color: #6a3093;
            font-weight: bold;
            font-size: 20px;
        }

        /* Page 6 - Thank You */
        .page6 {
            background: linear-gradient(135deg, #9b59b6 0%, #8e44ad 50%, #c39bd3 100%);
            color: white;
        }

        .page6 .page-title {
            color: #ffd700;
        }

        .thanks-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
            margin: 30px 0;
        }

        .thanks-item {
            background: rgba(255, 255, 255, 0.15);
            padding: 20px;
            border-radius: 10px;
            border: 2px solid rgba(255, 255, 255, 0.3);
            font-size: 16px;
            line-height: 1.8;
        }

        .thanks-item::before {
            content: '✓ ';
            color: #ffd700;
            font-weight: bold;
        }

        .gratitude {
            margin-top: 30px;
            font-size: 17px;
            line-height: 1.9;
            text-align: center;
            font-style: italic;
        }

        /* Page 7 - Envelope */
        .page7 {
            background: linear-gradient(135deg, #e0c3fc 0%, #8ec5fc 100%);
            color: #2c3e50;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            gap: 30px;
        }

        .page7 .page-title {
            color: #6a3093;
        }

        .envelope-container {
            perspective: 1000px;
        }

        .envelope {
            width: 200px;
            height: 140px;
            background: linear-gradient(135deg, #d946ef 0%, #d946ef 100%);
            border: 3px solid #6a3093;
            border-radius: 8px;
            position: relative;
            cursor: pointer;
            transition: all 0.6s cubic-bezier(0.68, -0.55, 0.265, 1.55);
            transform-style: preserve-3d;
        }

        .envelope:hover {
            transform: scale(1.05);
        }

        .envelope.opened {
            transform: rotateX(90deg);
        }

        .envelope-front {
            position: absolute;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, #d946ef 0%, #c838d4 100%);
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            flex-direction: column;
            backface-visibility: hidden;
        }

        .envelope-front::before {
            content: '';
            position: absolute;
            width: 0;
            height: 0;
            border-left: 100px solid transparent;
            border-right: 100px solid transparent;
            border-top: 70px solid rgba(0, 0, 0, 0.2);
            top: 0;
            animation: envelope-open 0.8s ease-out forwards;
        }

        .envelope-text {
            color: white;
            font-size: 18px;
            font-weight: 600;
            text-align: center;
            position: relative;
            z-index: 2;
        }

        .envelope.opened .envelope-front::before {
            display: none;
        }

        .envelope-back {
            position: absolute;
            width: 100%;
            height: 100%;
            background: white;
            border-radius: 8px;
            padding: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            backface-visibility: hidden;
            transform: rotateX(180deg);
            font-size: 13px;
            text-align: center;
            line-height: 1.8;
            color: #6a3093;
        }

        @keyframes envelope-open {
            0% { border-top: 70px solid rgba(0, 0, 0, 0.2); }
            100% { border-top: 0px solid rgba(0, 0, 0, 0.2); }
        }

        .envelope-hint {
            font-size: 14px;
            color: #6a3093;
            font-style: italic;
            margin-top: 15px;
        }

        /* Page 8 - Final */
        .page8 {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 50%, #f093fb 100%);
            color: white;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .page8::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background-image: 
                radial-gradient(circle at 20% 50%, rgba(255, 255, 255, 0.1) 0%, transparent 50%);
            pointer-events: none;
        }

        .page8-content {
            position: relative;
            z-index: 2;
        }

        .page8 .page-title {
            color: #ffd700;
            font-size: 52px;
        }

        .final-message {
            font-size: 18px;
            line-height: 2;
            margin: 30px 0;
            font-weight: 300;
        }

        .heart {
            color: #ff1493;
            font-size: 24px;
            animation: heartbeat 1.5s ease-in-out infinite;
        }

        @keyframes heartbeat {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.2); }
        }

        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-20px); }
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }

        /* Navigation */
        .nav-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            gap: 20px;
            margin-bottom: 30px;
        }

        .nav-btn {
            background: linear-gradient(135deg, #d946ef 0%, #6a3093 100%);
            color: white;
            border: none;
            padding: 14px 40px;
            border-radius: 50px;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 8px 20px rgba(217, 70, 239, 0.4);
            font-family: 'Poppins', sans-serif;
        }

        .nav-btn:hover:not(:disabled) {
            transform: translateY(-3px);
            box-shadow: 0 12px 30px rgba(217, 70, 239, 0.6);
        }

        .nav-btn:disabled {
            opacity: 0.4;
            cursor: not-allowed;
        }

        .dots-container {
            display: flex;
            gap: 10px;
            justify-content: center;
        }

        .dot {
            width: 12px;
            height: 12px;
            border-radius: 50%;
            background: rgba(217, 70, 239, 0.3);
            cursor: pointer;
            transition: all 0.3s ease;
            border: 2px solid transparent;
        }

        .dot.active {
            background: #d946ef;
            transform: scale(1.3);
            border: 2px solid #6a3093;
        }

        .page-counter {
            color: rgba(217, 70, 239, 0.8);
            font-weight: 600;
            font-size: 14px;
            min-width: 60px;
            text-align: center;
        }

        .keyboard-hint {
            text-align: center;
            color: rgba(217, 70, 239, 0.6);
            font-size: 13px;
            margin-top: 20px;
        }

        @media (max-width: 768px) {
            .page {
                padding: 30px;
            }

            .page1 .title {
                font-size: 48px;
            }

            .page1 .name {
                font-size: 56px;
            }

            .book-wrapper {
                height: 500px;
            }

            .page2-grid {
                grid-template-columns: 1fr;
                gap: 20px;
            }

            .thanks-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="book-wrapper">
            <div class="book">
                <div class="pages-container">
                    <!-- Page 1 -->
                    <div class="page page1 active">
                        <div class="page1-content">
                            <div class="subtitle">To My Crime Partner</div>
                            <div class="title">Happy</div>
                            <div class="name">Birthday</div>
                            <div class="emoji-large">🎂 💝 🎉</div>
                            <div class="quote">
                                To my confidant, my happiness<br>
                                — my forever person!
                            </div>
                        </div>
                    </div>

                    <!-- Page 2 -->
                    <div class="page page2">
                        <div class="page2-grid">
                            <div class="page2-text">
                                <h2>More than a Sister,<br><span class="highlight">You're CRIME PARTNER</span></h2>
                                <p>From tiny giggles to big dreams, you've been my constant.</p>
                                <p>We may have 4 years gap, but our bond is timeless.</p>
                                <p style="margin-top: 25px; font-size: 15px;">Like twin sisters in different years! <span class="emoji-star">💕</span></p>
                            </div>
                            <div class="page2-image">📸</div>
                        </div>
                    </div>

                    <!-- Page 3 -->
                    <div class="page page3">
                        <h1 class="page-title">You're...</h1>
                        <div class="feature-box">
                            <span class="feature-icon">❤️</span>My go-to person when I need something
                        </div>
                        <div class="feature-box">
                            <span class="feature-icon">🔐</span>My secret keeper - I share everything with you
                        </div>
                        <div class="feature-box">
                            <span class="feature-icon">😊</span>The one who makes me talk to Mama and gets things done!
                        </div>
                        <div class="feature-box">
                            <span class="feature-icon">😄</span>The reason I laugh a little louder and worry a little less
                        </div>
                    </div>

                    <!-- Page 4 -->
                    <div class="page page4">
                        <h1 class="page-title">You + Code = Magic <span style="font-size: 0.8em;">💻</span></h1>
                        <p style="font-size: 17px; margin: 20px 0; font-weight: 300;">Your love for learning inspires me every day!</p>
                        <div class="code-block">
<span class="tag">&lt;html&gt;</span><br>
&nbsp;&nbsp;<span class="tag">&lt;body&gt;</span><br>
&nbsp;&nbsp;&nbsp;&nbsp;<span class="tag">&lt;h1&gt;</span><span class="string">Muskan</span><span class="tag">&lt;/h1&gt;</span><br>
&nbsp;&nbsp;&nbsp;&nbsp;<span class="tag">&lt;p&gt;</span><span class="string">Future AI Engineer</span><span class="tag">&lt;/p&gt;</span><br>
&nbsp;&nbsp;<span class="tag">&lt;/body&gt;</span><br>
<span class="tag">&lt;/html&gt;</span>
                        </div>
                        <p style="font-size: 16px; margin-top: 20px;">Future AI Engineer - loading...</p>
                        <div class="loading-bar">
                            <div class="loading-fill"></div>
                        </div>
                        <p style="font-size: 18px; margin-top: 15px; font-weight: 600;">99%</p>
                    </div>

                    <!-- Page 5 -->
                    <div class="page page5">
                        <h1 class="page-title">Chasing Dreams<br>Building Future</h1>
                        <div class="dream-text">
                            You dream big, <strong>learn fearlessly</strong> and work <strong>passionately</strong>.<br>
                            The world is yours, and I can't wait to see you <strong>shine!</strong> ✨
                        </div>
                        <div class="checklist">
                            <div class="checklist-item">📝 Keep learning</div>
                            <div class="checklist-item">📈 Keep growing</div>
                            <div class="checklist-item">💫 Keep slowing down</div>
                        </div>
                    </div>

                    <!-- Page 6 -->
                    <div class="page page6">
                        <h1 class="page-title">Thank You For...</h1>
                        <div class="thanks-grid">
                            <div class="thanks-item">Being my safe place</div>
                            <div class="thanks-item">Understanding me</div>
                            <div class="thanks-item">Standing by me</div>
                            <div class="thanks-item">Making every day better</div>
                            <div class="thanks-item" style="grid-column: 1/3;">Being YOU!</div>
                        </div>
                        <div class="gratitude">
                            I'm so lucky to have you in my life.<br>
                            I don't know what I'd do without you. <span class="heart">❤️</span><br><br>
                            <strong>LOTS OF LOVE</strong><br>
                            always & forever
                        </div>
                    </div>

                    <!-- Page 7 -->
                    <div class="page page7">
                        <h1 class="page-title">A Special Surprise For You!</h1>
                        <p style="font-size: 15px; color: #6a3093;">Click the envelope to open your wishes</p>
                        <div class="envelope-container">
                            <div class="envelope" id="envelope">
                                <div class="envelope-front">
                                    <div class="envelope-text">💌</div>
                                </div>
                                <div class="envelope-back">
                                    Dear Muskan,<br><br>
                                    On your special day, just want to say how beautiful you're becoming.<br><br>
                                    May your dreams come true! May you always be happy, successful and surrounded by love.<br><br>
                                    Keep shining, my star! ⭐<br><br>
                                    Always yours ❤️
                                </div>
                            </div>
                        </div>
                        <div class="envelope-hint">💫 Click to reveal 💫</div>
                    </div>

                    <!-- Page 8 -->
                    <div class="page page8">
                        <div class="page8-content">
                            <h1 class="page-title">Dear Muskan,</h1>
                            <div class="final-message">
                                On your special day, I just want to say<br>
                                how amazing you are.<br><br>
                                <strong>May your every dream come true.</strong><br>
                                May you always be happy,<br>
                                successful and surrounded by love.<br><br>
                                <strong>Keep shining, my star!</strong> ⭐<br><br>
                                <span class="heart">❤️</span> <strong>Happy Birthday!</strong> <span class="heart">❤️</span><br><br>
                                <strong style="font-size: 20px;">Always yours</strong>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <div class="nav-container">
            <button class="nav-btn" id="prevBtn" onclick="prevPage()">← Previous</button>
            <div class="dots-container" id="dotsContainer"></div>
            <button class="nav-btn" id="nextBtn" onclick="nextPage()">Next →</button>
        </div>

        <div style="text-align: center;">
            <div class="page-counter"><span id="currentPage">1</span> / 8</div>
            <div class="keyboard-hint">💡 Tip: Use arrow keys (← →) to navigate</div>
        </div>
    </div>

    <script>
        let currentPage = 0;
        const totalPages = 8;

        function initDots() {
            const container = document.getElementById('dotsContainer');
            for (let i = 0; i < totalPages; i++) {
                const dot = document.createElement('div');
                dot.className = 'dot' + (i === 0 ? ' active' : '');
                dot.onclick = () => goToPage(i);
                container.appendChild(dot);
            }
        }

        function updateView() {
            // Update pages
            document.querySelectorAll('.page').forEach((page, index) => {
                page.classList.toggle('active', index === currentPage);
            });

            // Update dots
            document.querySelectorAll('.dot').forEach((dot, index) => {
                dot.classList.toggle('active', index === currentPage);
            });

            // Update buttons
            document.getElementById('prevBtn').disabled = currentPage === 0;
            document.getElementById('nextBtn').disabled = currentPage === totalPages - 1;

            // Update page counter
            document.getElementById('currentPage').textContent = currentPage + 1;
        }

        function nextPage() {
            if (currentPage < totalPages - 1) {
                currentPage++;
                updateView();
            }
        }

        function prevPage() {
            if (currentPage > 0) {
                currentPage--;
                updateView();
            }
        }

        function goToPage(page) {
            currentPage = page;
            updateView();
        }

        // Keyboard navigation
        document.addEventListener('keydown', (e) => {
            if (e.key === 'ArrowRight') nextPage();
            if (e.key === 'ArrowLeft') prevPage();
        });

        // Envelope interaction
        document.getElementById('envelope').addEventListener('click', function() {
            this.classList.toggle('opened');
        });

        // Initialize
        initDots();
        updateView();
    </script>
</body>
</html>
