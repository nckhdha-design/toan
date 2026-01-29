<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Math Survivor - Đấu Trường Toán Học</title>
    <script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
    <script id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>
    <style>
        :root { --primary: #7c3aed; --danger: #ef4444; --success: #10b981; --bg: #1e1b4b; }
        body { font-family: 'Segoe UI', sans-serif; background-color: var(--bg); color: white; display: flex; justify-content: center; align-items: center; min-height: 100vh; margin: 0; overflow: hidden; user-select: none; }
        
        /* Layout chính */
        .game-container { width: 900px; height: 600px; background: url('https://img.freepik.com/free-vector/dark-cave-landscape_1308-16279.jpg?w=1380') no-repeat center center; background-size: cover; position: relative; border-radius: 20px; box-shadow: 0 0 50px rgba(0,0,0,0.8); overflow: hidden; }
        .overlay { position: absolute; top:0; left:0; width:100%; height:100%; background: rgba(0,0,0,0.6); z-index: 1; }
        
        /* SETUP SCREEN */
        #setup-screen { position: absolute; z-index: 10; width: 100%; height: 100%; display: flex; flex-direction: column; justify-content: center; align-items: center; background: rgba(17, 24, 39, 0.95); }
        select { padding: 12px; margin: 10px; width: 300px; border-radius: 8px; border: none; font-size: 1rem; cursor: pointer; }
        .btn-start { padding: 15px 40px; background: var(--primary); color: white; border: none; font-size: 1.5rem; font-weight: bold; cursor: pointer; border-radius: 50px; margin-top: 20px; transition: 0.3s; box-shadow: 0 0 20px var(--primary); }
        .btn-start:hover { transform: scale(1.1); background: #6d28d9; }

        /* BATTLE ARENA */
        #battle-screen { position: absolute; z-index: 5; width: 100%; height: 100%; display: none; }
        
        /* Nhân vật */
        .character { position: absolute; bottom: 180px; transition: transform 0.2s; }
        #hero { left: 100px; font-size: 8rem; filter: drop-shadow(0 0 10px blue); }
        #monster { right: 100px; font-size: 10rem; filter: drop-shadow(0 0 10px red); transition: filter 0.2s; }
        
        /* Health Bars */
        .hp-container { position: absolute; width: 250px; padding: 10px; background: rgba(0,0,0,0.7); border-radius: 10px; border: 2px solid #555; }
        .hp-bar { height: 20px; background: #333; border-radius: 10px; overflow: hidden; margin-top: 5px; }
        .hp-fill { height: 100%; transition: width 0.5s ease-out; }
        #hero-hp-box { top: 20px; left: 20px; }
        #hero-hp-fill { background: var(--success); width: 100%; }
        #monster-hp-box { top: 20px; right: 20px; text-align: right; }
        #monster-hp-fill { background: var(--danger); width: 100%; }

        /* Khu vực câu hỏi (UI chính) */
        .combat-ui { position: absolute; bottom: 0; width: 100%; height: 220px; background: rgba(15, 23, 42, 0.95); border-top: 4px solid var(--primary); display: flex; flex-direction: column; align-items: center; padding-top: 20px; box-sizing: border-box; }
        .question-text { font-size: 1.5rem; margin-bottom: 20px; text-align: center; max-width: 80%; }
        .options-container { display: grid; grid-template-columns: 1fr 1fr; gap: 15px; width: 80%; }
        .option-btn { background: #334155; color: white; border: 2px solid #475569; padding: 12px; cursor: pointer; font-size: 1.1rem; border-radius: 8px; transition: 0.2s; text-align: left; position: relative; }
        .option-btn:hover { background: #475569; border-color: var(--primary); }
        
        /* Hiệu ứng & Loading */
        .hidden { display: none !important; }
        .damage-text { position: absolute; font-size: 3rem; font-weight: bold; color: yellow; animation: floatUp 1s forwards; pointer-events: none; z-index: 20; }
        @keyframes floatUp { 0% { opacity: 1; transform: translateY(0); } 100% { opacity: 0; transform: translateY(-50px); } }
        
        .shake { animation: shake 0.5s; }
        @keyframes shake { 0% { transform: translate(1px, 1px) rotate(0deg); } 10% { transform: translate(-1px, -2px) rotate(-1deg); } 20% { transform: translate(-3px, 0px) rotate(1deg); } 30% { transform: translate(3px, 2px) rotate(0deg); } 100% { transform: translate(1px, -2px) rotate(-1deg); } }
        
        .attack-anim { animation: lunge 0.3s alternate 2; }
        @keyframes lunge { 0% { transform: translateX(0); } 100% { transform: translateX(50px); } }
        .attack-anim-m { animation: lungeM 0.3s alternate 2; }
        @keyframes lungeM { 0% { transform: translateX(0); } 100% { transform: translateX(-50px); } }

        .loader { border: 4px solid #f3f3f3; border-top: 4px solid var(--primary); border-radius: 50%; width: 30px; height: 30px; animation: spin 1s linear infinite; margin: 10px auto; }
        @keyframes spin { 0% { transform: rotate(0deg); } 100% { transform: rotate(360deg); } }
    </style>
</head>
<body>

<div class="game-container">
    <div class="overlay"></div>

    <div id="setup-screen">
        <h1 style="font-size: 3rem; color: var(--primary); text-shadow: 0 0 10px white; margin-bottom: 30px;">⚔️ MATH SURVIVOR</h1>
        
        <label>Chọn chủ đề:</label>
        <select id="topic">
            <option value="addition_fractions">Cộng trừ phân thức đại số (Lớp 8)</option>
            <option value="simplifying_fractions">Rút gọn phân thức (Lớp 8)</option>
            <option value="basic_algebra">Tính giá trị biểu thức</option>
        </select>

        <label>Độ khó:</label>
        <select id="difficulty">
            <option value="Easy">Dễ (Quái vật Blob - HP: 50)</option>
            <option value="Medium">Thường (Rồng lửa - HP: 100)</option>
            <option value="Hard">Khó (Quỷ Vương - HP: 200)</option>
        </select>

        <button class="btn-start" onclick="startGame()">VÀO TRẬN ĐẤU</button>
        <p style="color: #9ca3af; font-size: 0.9rem; margin-top: 20px;">*Tự động chuyển chế độ Offline nếu mất mạng</p>
    </div>

    <div id="battle-screen">
        <div id="hero-hp-box" class="hp-container">
            <div style="font-weight: bold;">🥷 Hiệp Sĩ</div>
            <div class="hp-bar"><div id="hero-hp-fill" class="hp-fill"></div></div>
            <div id="hero-hp-text">100/100</div>
        </div>

        <div id="monster-hp-box" class="hp-container">
            <div style="font-weight: bold;" id="monster-name">Quái Vật</div>
            <div class="hp-bar"><div id="monster-hp-fill" class="hp-fill"></div></div>
            <div id="monster-hp-text">100/100</div>
        </div>

        <div id="hero" class="character">🥷</div>
        <div id="monster" class="character">🐉</div>

        <div class="combat-ui">
            <div id="loading-box" class="hidden">
                <div class="loader"></div>
                <div style="color: #cbd5e1;">Quái vật đang niệm chú...</div>
            </div>
            
            <div id="question-area">
                <div id="question-text" class="question-text">Đang tải...</div>
                <div id="options-area" class="options-container"></div>
            </div>
            
            <div id="message-area" style="color: yellow; font-weight: bold; font-size: 1.2rem; margin-top: 10px;"></div>
        </div>
    </div>
</div>

<script>
    // --- CẤU HÌNH ---
    let gameState = {
        // ▼▼▼ DÁN API KEY CỦA BẠN VÀO GIỮA 2 DẤU NHÁY DƯỚI ĐÂY ▼▼▼
        apiKey: 'AIzaSyB8NLibfH2L-mjDfZ-bpsMJ2Ju9Yk355iE', 
        // ▲▲▲ VÍ DỤ: 'AIzaSyD-123456abcdef...' ▲▲▲
        
        topic: '',
        difficulty: '',
        heroHP: 100,
        monsterHP: 100,
        monsterMaxHP: 100,
        currentQuestion: null,
        isUsingOffline: false
    };

    const monsters = {
        'Easy': { icon: '🦠', name: 'Slime Nhầy Nhụa', hp: 50, dmg: 10 },
        'Medium': { icon: '🐉', name: 'Rồng Lửa', hp: 100, dmg: 20 },
        'Hard': { icon: '👹', name: 'Quỷ Vương', hp: 200, dmg: 35 }
    };

    // Ngân hàng câu hỏi dự phòng (Dùng khi mất mạng hoặc chưa có Key)
    const offlineBank = [
        { question: "Kết quả của phép tính $$\\frac{2x}{x+1} + \\frac{2}{x+1}$$ là:", options: ["$$2$$", "$$x$$", "$$\\frac{2}{x+1}$$", "$$1$$"], correctIndex: 0 },
        { question: "Mẫu thức chung của $$\\frac{1}{x^2-1}$$ và $$\\frac{1}{x+1}$$ là:", options: ["$$x^2-1$$", "$$x+1$$", "$$x-1$$", "$$(x+1)^2$$"], correctIndex: 0 },
        { question: "Thực hiện phép tính: $$\\frac{1}{x} - \\frac{1}{x+1}$$", options: ["$$\\frac{1}{x(x+1)}$$", "$$\\frac{-1}{x(x+1)}$$", "$$1$$", "$$0$$"], correctIndex: 0 },
        { question: "Điều kiện xác định của phân thức $$\\frac{x}{x-3}$$ là:", options: ["$$x \\neq 3$$", "$$x \\neq 0$$", "$$x = 3$$", "$$x \\neq -3$$"], correctIndex: 0 },
        { question: "Kết quả rút gọn của $$\\frac{x^2-4}{x+2}$$ là:", options: ["$$x-2$$", "$$x+2$$", "$$x-4$$", "$$\\frac{1}{x-2}$$"], correctIndex: 0 }
    ];

    function startGame() {
        gameState.topic = document.getElementById('topic').value;
        gameState.difficulty = document.getElementById('difficulty').value;

        // Cài đặt chỉ số Quái vật
        const mConfig = monsters[gameState.difficulty];
        gameState.monsterMaxHP = mConfig.hp;
        gameState.monsterHP = mConfig.hp;
        document.getElementById('monster').innerText = mConfig.icon;
        document.getElementById('monster-name').innerText = mConfig.name;

        // Chuyển màn hình
        document.getElementById('setup-screen').style.display = 'none';
        document.getElementById('battle-screen').style.display = 'block';
        
        updateHPUI();
        loadNewTurn();
    }

    async function loadNewTurn() {
        document.getElementById('loading-box').classList.remove('hidden');
        document.getElementById('question-area').classList.add('hidden');
        document.getElementById('message-area').innerText = "";

        // Gọi hàm lấy câu hỏi
        await fetchQuestion();

        document.getElementById('loading-box').classList.add('hidden');
        document.getElementById('question-area').classList.remove('hidden');
        renderQuestion();
    }

    async function fetchQuestion() {
        // Nếu không có Key hoặc đang dùng chế độ Offline -> Lấy luôn câu hỏi mẫu
        if (!gameState.apiKey || gameState.apiKey.includes('AIzaSyB8NLibfH2L-mjDfZ-bpsMJ2Ju9Yk355iE') || gameState.isUsingOffline) {
            useOfflineQuestion();
            return;
        }

        const prompt = `
            Create a multiple-choice math question for 8th grade students.
            Topic: ${gameState.topic}. Difficulty: ${gameState.difficulty}.
            Language: Vietnamese.
            Output JSON ONLY: { "question": "LaTeX string inside $$", "options": ["A", "B", "C", "D"], "correctIndex": 0 }
        `;

        try {
            const response = await fetch(`https://generativelanguage.googleapis.com/v1beta/models/gemini-1.5-flash:generateContent?key=${gameState.apiKey}`, {
                method: "POST",
                headers: { "Content-Type": "application/json" },
                body: JSON.stringify({ contents: [{ parts: [{ text: prompt }] }] })
            });

            if (!response.ok) throw new Error("API Error");

            const data = await response.json();
            let text = data.candidates[0].content.parts[0].text;
            text = text.replace(/```json/g, "").replace(/```/g, "").trim();
            gameState.currentQuestion = JSON.parse(text);

        } catch (e) {
            console.warn("Lỗi kết nối AI, chuyển sang chế độ Offline.");
            gameState.isUsingOffline = true; // Bật cờ offline để các lần sau không gọi API nữa cho đỡ lag
            useOfflineQuestion();
        }
    }

    function useOfflineQuestion() {
        // Lấy ngẫu nhiên và trộn đáp án sơ bộ
        const q = offlineBank[Math.floor(Math.random() * offlineBank.length)];
        gameState.currentQuestion = q;
    }

    function renderQuestion() {
        const q = gameState.currentQuestion;
        document.getElementById('question-text').innerHTML = q.question;
        
        const optsDiv = document.getElementById('options-area');
        optsDiv.innerHTML = '';
        
        // Tạo bản sao mảng options để trộn vị trí hiển thị mà không mất correctIndex logic
        // Cách đơn giản: Map options gốc sang objects có id
        let displayOptions = q.options.map((txt, idx) => ({ text: txt, originalIdx: idx }));
        
        // Trộn vị trí hiển thị
        displayOptions.sort(() => Math.random() - 0.5);

        displayOptions.forEach((opt) => {
            const btn = document.createElement('div');
            btn.className = 'option-btn';
            btn.innerHTML = opt.text;
            // Khi click, kiểm tra xem originalIdx có trùng với correctIndex không
            btn.onclick = () => handleAnswer(opt.originalIdx, btn);
            optsDiv.appendChild(btn);
        });

        MathJax.typesetPromise();
    }

    function handleAnswer(selectedIndex, btnElement) {
        // Khóa nút
        const btns = document.querySelectorAll('.option-btn');
        btns.forEach(b => b.style.pointerEvents = 'none');

        const isCorrect = selectedIndex === gameState.currentQuestion.correctIndex;

        if (isCorrect) {
            btnElement.style.background = 'var(--success)';
            btnElement.style.borderColor = 'var(--success)';
            performAttack('Hero');
        } else {
            btnElement.style.background = 'var(--danger)';
            btnElement.style.borderColor = 'var(--danger)';
            performAttack('Monster');
        }
    }

    function performAttack(attacker) {
        if (attacker === 'Hero') {
            document.getElementById('hero').classList.add('attack-anim');
            setTimeout(() => {
                const dmg = 25; 
                gameState.monsterHP = Math.max(0, gameState.monsterHP - dmg);
                showDamage(dmg, 'monster');
                document.getElementById('hero').classList.remove('attack-anim');
                document.getElementById('monster').classList.add('shake');
                checkWinCondition();
            }, 300);
        } else {
            document.getElementById('monster').classList.add('attack-anim-m');
            setTimeout(() => {
                const dmg = monsters[gameState.difficulty].dmg;
                gameState.heroHP = Math.max(0, gameState.heroHP - dmg);
                showDamage(dmg, 'hero');
                document.getElementById('monster').classList.remove('attack-anim-m');
                document.getElementById('hero').classList.add('shake');
                checkWinCondition();
            }, 300);
        }
    }

    function checkWinCondition() {
        updateHPUI();
        setTimeout(() => {
            document.getElementById('monster').classList.remove('shake');
            document.getElementById('hero').classList.remove('shake');

            if (gameState.monsterHP <= 0) {
                alert("CHIẾN THẮNG! Quái vật đã bị tiêu diệt! 🏆");
                location.reload();
            } else if (gameState.heroHP <= 0) {
                alert("THẤT BẠI! Hãy luyện tập thêm nhé... 💀");
                location.reload();
            } else {
                setTimeout(loadNewTurn, 1500);
            }
        }, 500);
    }

    function updateHPUI() {
        const hPct = (gameState.heroHP / 100) * 100;
        const mPct = (gameState.monsterHP / gameState.monsterMaxHP) * 100;

        document.getElementById('hero-hp-fill').style.width = `${hPct}%`;
        document.getElementById('hero-hp-text').innerText = `${gameState.heroHP}/100`;

        document.getElementById('monster-hp-fill').style.width = `${mPct}%`;
        document.getElementById('monster-hp-text').innerText = `${gameState.monsterHP}/${gameState.monsterMaxHP}`;
    }

    function showDamage(amount, targetId) {
        const el = document.createElement('div');
        el.className = 'damage-text';
        el.innerText = `-${amount}`;
        const target = document.getElementById(targetId);
        const rect = target.getBoundingClientRect();
        
        el.style.left = (rect.left + 50) + 'px';
        el.style.top = (rect.top) + 'px';
        el.style.color = targetId === 'hero' ? '#ef4444' : '#fbbf24';

        document.body.appendChild(el);
        setTimeout(() => el.remove(), 1000);
    }
</script>
</body>
</html>
