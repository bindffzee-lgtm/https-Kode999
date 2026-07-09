<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Quiz Spesial Buat Kamu ❤️</title>
<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

html, body {
    width: 100%;
    height: 100%;
    overflow: hidden;
}

body {
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    background: linear-gradient(-45deg, #ff9ecf, #ffd6e8, #ffb3d9, #ff85b3);
    background-size: 400% 400%;
    font-family: 'Arial', sans-serif;
    animation: gradientShift 15s ease infinite;
}

@keyframes gradientShift {
    0% {
        background-position: 0% 50%;
    }
    50% {
        background-position: 100% 50%;
    }
    100% {
        background-position: 0% 50%;
    }
}

.container {
    position: relative;
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 20px;
}

/* Loading Screen */
.loading-screen {
    text-align: center;
    animation: fadeIn 0.8s ease-out;
}

.loading-screen h1 {
    font-size: 48px;
    color: white;
    margin-bottom: 20px;
    text-shadow: 3px 3px 10px rgba(0, 0, 0, 0.2);
    animation: bounce 1s ease-in-out infinite;
}

.loading-screen p {
    font-size: 24px;
    color: white;
    margin-bottom: 40px;
    text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.2);
}

.start-btn {
    padding: 20px 50px;
    font-size: 20px;
    background: linear-gradient(135deg, #ff4d6d, #ff2d5a);
    color: white;
    border: none;
    border-radius: 15px;
    cursor: pointer;
    transition: all 0.3s ease;
    box-shadow: 0 10px 30px rgba(255, 77, 109, 0.4);
    font-weight: bold;
}

.start-btn:hover {
    transform: scale(1.1);
    box-shadow: 0 15px 40px rgba(255, 77, 109, 0.6);
}

/* Quiz Card */
.quiz-card {
    background: rgba(255, 255, 255, 0.98);
    padding: 50px 40px;
    border-radius: 30px;
    box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
    width: 90%;
    max-width: 550px;
    animation: slideInUp 0.6s cubic-bezier(0.34, 1.56, 0.64, 1);
    border: 3px solid #ff4d6d;
}

@keyframes slideInUp {
    from {
        opacity: 0;
        transform: translateY(60px);
    }
    to {
        opacity: 1;
        transform: translateY(0);
    }
}

@keyframes fadeIn {
    from {
        opacity: 0;
    }
    to {
        opacity: 1;
    }
}

@keyframes bounce {
    0%, 100% {
        transform: translateY(0);
    }
    50% {
        transform: translateY(-10px);
    }
}

/* Progress Bar */
.progress-container {
    margin-bottom: 30px;
}

.progress-info {
    display: flex;
    justify-content: space-between;
    margin-bottom: 10px;
    font-size: 14px;
    color: #666;
}

.progress-bar {
    width: 100%;
    height: 10px;
    background: #f0f0f0;
    border-radius: 10px;
    overflow: hidden;
    border: 2px solid #ff4d6d;
}

.progress-fill {
    height: 100%;
    background: linear-gradient(90deg, #ff4d6d, #ff2d5a);
    transition: width 0.5s ease;
    width: 0%;
}

/* Question */
.question-container {
    margin-bottom: 30px;
}

.question-number {
    font-size: 14px;
    color: #ff4d6d;
    font-weight: bold;
    margin-bottom: 10px;
}

.question-text {
    font-size: 28px;
    color: #333;
    font-weight: bold;
    margin-bottom: 30px;
    line-height: 1.4;
    text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.1);
}

/* Options */
.options-container {
    display: flex;
    flex-direction: column;
    gap: 15px;
}

.option-btn {
    padding: 15px 20px;
    background: #f5f5f5;
    border: 2px solid #ddd;
    border-radius: 12px;
    font-size: 16px;
    cursor: pointer;
    transition: all 0.3s ease;
    text-align: left;
    color: #333;
    font-weight: 500;
}

.option-btn:hover {
    background: #ffe4ec;
    border-color: #ff4d6d;
    transform: translateX(10px);
}

.option-btn.selected {
    background: linear-gradient(135deg, #ff4d6d, #ff2d5a);
    color: white;
    border-color: #ff2d5a;
    box-shadow: 0 5px 15px rgba(255, 77, 109, 0.3);
}

/* Next Button */
.next-btn {
    width: 100%;
    padding: 15px;
    background: linear-gradient(135deg, #ff4d6d, #ff2d5a);
    color: white;
    border: none;
    border-radius: 12px;
    font-size: 16px;
    font-weight: bold;
    cursor: pointer;
    transition: all 0.3s ease;
    margin-top: 20px;
    box-shadow: 0 5px 15px rgba(255, 77, 109, 0.3);
    opacity: 0.5;
    pointer-events: none;
}

.next-btn:not(:disabled) {
    opacity: 1;
    pointer-events: all;
}

.next-btn:hover:not(:disabled) {
    transform: translateY(-2px);
    box-shadow: 0 8px 20px rgba(255, 77, 109, 0.5);
}

/* Result Screen */
.result-screen {
    text-align: center;
    animation: fadeIn 0.8s ease-out;
}

.result-screen h1 {
    font-size: 48px;
    color: white;
    margin-bottom: 20px;
    text-shadow: 3px 3px 10px rgba(0, 0, 0, 0.2);
}

.score-display {
    font-size: 72px;
    color: white;
    margin: 30px 0;
    text-shadow: 3px 3px 10px rgba(0, 0, 0, 0.2);
    animation: scaleIn 0.8s cubic-bezier(0.34, 1.56, 0.64, 1);
}

@keyframes scaleIn {
    from {
        transform: scale(0);
    }
    to {
        transform: scale(1);
    }
}

.result-message {
    font-size: 24px;
    color: white;
    margin-bottom: 40px;
    text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.2);
    line-height: 1.6;
}

.continue-btn {
    padding: 15px 50px;
    font-size: 18px;
    background: white;
    color: #ff4d6d;
    border: none;
    border-radius: 15px;
    cursor: pointer;
    transition: all 0.3s ease;
    font-weight: bold;
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
}

.continue-btn:hover {
    transform: scale(1.1);
    box-shadow: 0 15px 40px rgba(0, 0, 0, 0.3);
}

/* Final Question Screen */
.final-question {
    background: rgba(255, 255, 255, 0.98);
    padding: 60px 40px;
    border-radius: 30px;
    box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
    width: 90%;
    max-width: 550px;
    animation: slideInUp 0.6s cubic-bezier(0.34, 1.56, 0.64, 1);
    border: 3px solid #ff4d6d;
    text-align: center;
}

.final-emoji {
    font-size: 100px;
    margin-bottom: 30px;
    display: inline-block;
    animation: pulse 1.5s ease-in-out infinite;
}

@keyframes pulse {
    0%, 100% {
        transform: scale(1);
    }
    50% {
        transform: scale(1.1);
    }
}

.final-question h2 {
    font-size: 36px;
    color: #ff4d6d;
    margin-bottom: 20px;
    text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.1);
}

.final-question p {
    font-size: 18px;
    color: #666;
    margin-bottom: 40px;
    line-height: 1.6;
}

.final-buttons {
    display: flex;
    gap: 20px;
    justify-content: center;
    flex-wrap: wrap;
}

.yes-btn, .no-btn {
    padding: 15px 35px;
    font-size: 18px;
    border: none;
    border-radius: 15px;
    cursor: pointer;
    transition: all 0.3s ease;
    font-weight: bold;
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
}

.yes-btn {
    background: linear-gradient(135deg, #4caf50, #45a049);
    color: white;
    min-width: 150px;
}

.yes-btn:hover {
    transform: scale(1.1);
    box-shadow: 0 10px 25px rgba(76, 175, 80, 0.4);
}

.no-btn {
    background: #f0f0f0;
    color: #333;
    min-width: 120px;
    position: relative;
}

.no-btn:hover {
    background: #e0e0e0;
}

/* Success Screen */
.success-screen {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    background: linear-gradient(135deg, #ffe4ec 0%, #ffb3d9 50%, #ff85b3 100%);
    animation: fadeIn 0.8s ease-out;
    z-index: 9999;
    overflow: hidden;
}

.success-content {
    text-align: center;
    animation: zoomIn 0.6s cubic-bezier(0.34, 1.56, 0.64, 1);
}

@keyframes zoomIn {
    from {
        opacity: 0;
        transform: scale(0.3);
    }
    to {
        opacity: 1;
        transform: scale(1);
    }
}

.success-emoji {
    font-size: 120px;
    display: inline-block;
    animation: bounce-success 0.6s ease-in-out infinite;
    margin-bottom: 30px;
}

@keyframes bounce-success {
    0%, 100% {
        transform: translateY(0);
    }
    50% {
        transform: translateY(-40px);
    }
}

.success-screen h1 {
    font-size: 60px;
    color: white;
    margin-bottom: 20px;
    text-shadow: 3px 3px 10px rgba(0, 0, 0, 0.2);
}

.success-screen p {
    font-size: 24px;
    color: white;
    margin-bottom: 20px;
    text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.2);
}

.heart-emoji {
    font-size: 80px;
    display: inline-block;
    margin-top: 40px;
    animation: heartbeat 0.8s ease-in-out infinite;
}

@keyframes heartbeat {
    0%, 100% {
        transform: scale(1);
    }
    50% {
        transform: scale(1.2);
    }
}

/* Animasi hati jatuh */
.heart {
    position: fixed;
    font-size: 30px;
    pointer-events: none;
    animation: fall 3s linear forwards;
    filter: drop-shadow(0 0 3px rgba(255, 77, 109, 0.5));
}

@keyframes fall {
    0% {
        opacity: 1;
        transform: translateY(0) translateX(0) rotate(0deg);
    }
    100% {
        opacity: 0;
        transform: translateY(100vh) translateX(50px) rotate(360deg);
    }
}

/* Animasi confetti */
.confetti {
    position: fixed;
    pointer-events: none;
    animation: confetti-fall 4s ease-in forwards;
    filter: drop-shadow(0 0 2px rgba(255, 200, 100, 0.5));
}

@keyframes confetti-fall {
    0% {
        opacity: 1;
        transform: translateY(-100px) translateX(0) rotate(0deg) scale(1);
    }
    100% {
        opacity: 0;
        transform: translateY(100vh) translateX(100px) rotate(720deg) scale(0);
    }
}

/* Responsive */
@media (max-width: 600px) {
    .quiz-card, .final-question {
        padding: 40px 25px;
        margin: 20px;
    }
    
    .question-text {
        font-size: 22px;
    }
    
    .option-btn {
        font-size: 14px;
        padding: 12px 15px;
    }
    
    .success-screen h1 {
        font-size: 45px;
    }
    
    .success-screen p {
        font-size: 20px;
    }
}
</style>
</head>
<body>

<div class="container" id="container"></div>

<script>
const quizData = [
    {
        question: "Kapan kita pertama kali bertemu?",
        options: ["Entah lupa, tapi aku ingat perasaanmu", "Itu hari terindah dalam hidupku", "Waktu tidak penting, yang penting ada kamu", "Setiap hari bareng kamu terasa istimewa"]
    },
    {
        question: "Hal apa yang paling aku sukai dari dirimu?",
        options: ["Senyuman indah kamu", "Cara kamu peduli kepada orang lain", "Kepribadian yang hangat dan baik hati", "Semua hal dari dirimu"]
    },
    {
        question: "Moment terindah apa yang kita punya?",
        options: ["Saat kita tertawa bersama", "Saat kita berdua diam tapi nyaman", "Saat kita saling menatap", "Semua moment bareng kamu indah"]
    },
    {
        question: "Jika bisa memilih, aku ingin...?",
        options: ["Menghabiskan setiap hari denganmu", "Tua bersama kamu", "Membuat kamu selalu tersenyum", "Semuanya dengan kamu"]
    },
    {
        question: "Bagaimana perasaanku saat kita berpisah?",
        options: ["Sangat sedih dan kesepian", "Hati serasa ada yang hilang", "Hanya berpikir tentangmu", "Ingin cepat bertemu lagi"]
    },
    {
        question: "Apa alasan utama aku menyayangimu?",
        options: ["Karena kamu adalah diriku yang sempurna", "Karena kamu membuatku ingin jadi lebih baik", "Karena kamu adalah takdir", "Karena aku jatuh cinta pada jiwamu"]
    },
    {
        question: "Jika aku bisa menghapus satu kesalahan...?",
        options: ["Aku ingin menghapus semua yang menyakiti kamu", "Aku ingin memulai dari awal dengan lebih baik", "Aku ingin kita tidak pernah berpisah", "Aku ingin waktu kembali untuk memperbaiki semuanya"]
    },
    {
        question: "Mimpi terbesarku adalah...?",
        options: ["Bahagia selamanya denganmu", "Membangun keluarga bersama kamu", "Tua dan harmonis bersama orang terkasih", "Kamu tersenyum karena aku setiap hari"]
    },
    {
        question: "Apa yang membuat cinta aku tetap ada meski kita berpisah?",
        options: ["Karena cintaku terlalu dalam", "Karena kamu adalah satu-satunya", "Karena kamu bagian dari jiwaku", "Karena cinta sejati tidak pernah hilang"]
    },
    {
        question: "Apakah aku benar-benar masih sayang sama kamu?",
        options: ["Tidak pernah berhenti", "Lebih dari sebelumnya", "Selamanya dan sepenuh hati", "Ya, dengan seluruh jiwaku"]
    }
];

let currentQuestion = 0;
let score = 0;
let selectedAnswer = null;
let answered = false;

function init() {
    showLoadingScreen();
}

function showLoadingScreen() {
    const container = document.getElementById('container');
    container.innerHTML = `
        <div class="loading-screen">
            <h1>❤️ Quiz Spesial Buat Kamu ❤️</h1>
            <p>Yuk jawab beberapa pertanyaan dari hatiku</p>
            <button class="start-btn" onclick="startQuiz()">Mulai Quiz</button>
        </div>
    `;
}

function startQuiz() {
    playClickSound();
    currentQuestion = 0;
    score = 0;
    showQuestion();
}

function showQuestion() {
    const container = document.getElementById('container');
    const question = quizData[currentQuestion];
    const progress = ((currentQuestion + 1) / quizData.length) * 100;
    
    selectedAnswer = null;
    answered = false;

    container.innerHTML = `
        <div class="quiz-card">
            <div class="progress-container">
                <div class="progress-info">
                    <span>Pertanyaan ${currentQuestion + 1} dari ${quizData.length}</span>
                    <span>${Math.round(progress)}%</span>
                </div>
                <div class="progress-bar">
                    <div class="progress-fill" style="width: ${progress}%"></div>
                </div>
            </div>

            <div class="question-container">
                <div class="question-number">Pertanyaan ${currentQuestion + 1}</div>
                <div class="question-text">${question.question}</div>
            </div>

            <div class="options-container" id="optionsContainer">
                ${question.options.map((option, index) => `
                    <button class="option-btn" onclick="selectAnswer(${index})">
                        ${option}
                    </button>
                `).join('')}
            </div>

            <button class="next-btn" id="nextBtn" onclick="nextQuestion()">Lanjut ke Pertanyaan Berikutnya</button>
        </div>
    `;
}

function selectAnswer(index) {
    if (answered) return;
    
    playClickSound();
    selectedAnswer = index;
    answered = true;
    score++;

    const options = document.querySelectorAll('.option-btn');
    options[index].classList.add('selected');
    document.getElementById('nextBtn').disabled = false;
    document.getElementById('nextBtn').style.opacity = '1';
    document.getElementById('nextBtn').style.pointerEvents = 'auto';
}

function nextQuestion() {
    playClickSound();
    currentQuestion++;
    
    if (currentQuestion < quizData.length) {
        showQuestion();
    } else {
        showResultScreen();
    }
}

function showResultScreen() {
    const container = document.getElementById('container');
    const percentage = (score / quizData.length) * 100;
    
    let message = "";
    if (percentage === 100) {
        message = "Kamu sempurna! Kamu tahu semuanya tentang perasaanku 💕";
    } else if (percentage >= 80) {
        message = "Luar biasa! Kamu memahami hatiku dengan baik 💖";
    } else if (percentage >= 60) {
        message = "Bagus! Tapi masih ada yang perlu kamu ketahui tentangku 💗";
    } else {
        message = "Saatnya kita lebih dekat dan saling memahami 💕";
    }

    container.innerHTML = `
        <div class="result-screen">
            <h1>Quiz Selesai! 🎉</h1>
            <div class="score-display">${score}/${quizData.length}</div>
            <div class="result-message">${message}</div>
            <button class="continue-btn" onclick="showFinalQuestion()">Lanjutkan</button>
        </div>
    `;
}

function showFinalQuestion() {
    playClickSound();
    const container = document.getElementById('container');
    
    container.innerHTML = `
        <div class="final-question">
            <div class="final-emoji">🥺</div>
            <h2>Ada Satu Pertanyaan Lagi Nih...</h2>
            <p>Setelah semua ini... apakah kamu mau balikan sama aku? Aku janji akan lebih baik 💕</p>
            
            <div class="final-buttons">
                <button class="yes-btn" onclick="sayYes()">Mau ❤️</button>
                <button class="no-btn" id="noBtn">Nggak 😔</button>
            </div>
        </div>
    `;

    setupNoButton();
}

function setupNoButton() {
    const noBtn = document.getElementById('noBtn');
    let clickCount = 0;

    noBtn.addEventListener('mouseover', () => {
        clickCount++;
        noBtn.style.position = 'absolute';
        
        const randomX = Math.random() * (window.innerWidth - 120);
        const randomY = Math.random() * (window.innerHeight - 50);
        noBtn.style.left = randomX + 'px';
        noBtn.style.top = randomY + 'px';
    });

    noBtn.addEventListener('click', (e) => {
        e.preventDefault();
        playClickSound();
        
        const responses = [
            '😭 Yah, tapi aku masih sayang sama kamu...',
            '💔 Beri aku satu kesempatan lagi dong...',
            '😢 Kamu yakin? Pikirkan lagi...',
            '😩 Ini bukan jawaban yang aku harapkan...',
            '🥺 Pleaseee... aku berjanji akan lebih baik!'
        ];
        
        const randomResponse = responses[Math.floor(Math.random() * responses.length)];
        alert(randomResponse);
        setTimeout(() => {
            location.reload();
        }, 500);
    });
}

function sayYes() {
    playClickSound();
    
    createConfetti();
    for (let i = 0; i < 8; i++) {
        setTimeout(() => createHearts(), i * 200);
    }
    
    setTimeout(() => {
        document.body.innerHTML = `
        <div class="success-screen">
            <div class="success-content">
                <div class="success-emoji">🥰</div>
                <h1>YEAY!! 🎉</h1>
                <p>Makasih udah mau kasih aku kesempatan lagi 💖</p>
                <p style="font-size: 22px; margin-top: 20px; font-weight: normal;">Semoga kali ini kita lebih baik dari sebelumnya</p>
                <div class="heart-emoji">❤️</div>
            </div>
        </div>`;
        
        setInterval(() => {
            createHearts();
            createConfetti();
        }, 600);
    }, 800);
}

function createHearts() {
    const heart = document.createElement('div');
    heart.classList.add('heart');
    heart.textContent = '❤️';
    heart.style.left = Math.random() * window.innerWidth + 'px';
    heart.style.top = '-30px';
    document.body.appendChild(heart);
    
    setTimeout(() => heart.remove(), 3000);
}

function createConfetti() {
    const colors = ['🎉', '✨', '💕', '🌹', '💖', '🎊', '⭐', '💝', '🎈', '🎁'];
    for (let i = 0; i < 30; i++) {
        const confetti = document.createElement('div');
        confetti.classList.add('confetti');
        confetti.textContent = colors[Math.floor(Math.random() * colors.length)];
        confetti.style.left = Math.random() * window.innerWidth + 'px';
        confetti.style.top = '-30px';
        confetti.style.fontSize = Math.random() * 30 + 15 + 'px';
        confetti.style.animationDuration = (Math.random() * 1.5 + 2.5) + 's';
        document.body.appendChild(confetti);
        
        setTimeout(() => confetti.remove(), 4000);
    }
}

function playClickSound() {
    // Simple beep sound using Web Audio API
    const audioContext = new (window.AudioContext || window.webkitAudioContext)();
    const oscillator = audioContext.createOscillator();
    const gain = audioContext.createGain();
    
    oscillator.connect(gain);
    gain.connect(audioContext.destination);
    
    oscillator.frequency.value = 800;
    oscillator.type = 'sine';
    
    gain.gain.setValueAtTime(0.3, audioContext.currentTime);
    gain.gain.exponentialRampToValueAtTime(0.01, audioContext.currentTime + 0.1);
    
    oscillator.start(audioContext.currentTime);
    oscillator.stop(audioContext.currentTime + 0.1);
}

init();
</script>

</body>
</html>
