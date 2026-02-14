<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>💖 For My Sveta | Fajr's World</title>
    
    <!-- Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Cedarville+Cursive&family=Playfair+Display:wght@400;700;900&family=Montserrat:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        /* ===== COMPLETE DESIGN SYSTEM ===== */
        :root {
            --primary-pink: #ff85a2;
            --primary-red: #ff4757;
            --primary-gold: #ffd700;
            --primary-purple: #9b59b6;
            --primary-blue: #3498db;
            --bg-light: #f0f8ff;
            --bg-soft: #b3e0ff;
            --text-dark: #2c3e50;
            --white: #ffffff;
            --shadow-sm: 0 10px 30px rgba(0, 0, 0, 0.08);
            --shadow-md: 0 20px 50px rgba(0, 0, 0, 0.12);
            --shadow-lg: 0 30px 70px rgba(0, 0, 0, 0.15);
            --gradient-pink: linear-gradient(135deg, #ff85a2, #ff4757);
            --gradient-gold: linear-gradient(135deg, #ffd700, #ffb347);
            --gradient-purple: linear-gradient(135deg, #9b59b6, #8e44ad);
            --gradient-blue: linear-gradient(135deg, #3498db, #2980b9);
            --gradient-sunset: linear-gradient(135deg, #ff6b8b, #ff4757, #ff85a2);
        }
        
        * { margin: 0; padding: 0; box-sizing: border-box; }
        
        html { scroll-behavior: smooth; font-size: 16px; }
        
        body {
            font-family: 'Montserrat', sans-serif;
            background: linear-gradient(135deg, var(--bg-light), var(--bg-soft));
            color: var(--text-dark);
            min-height: 100vh;
            overflow-x: hidden;
            position: relative;
        }
        
        h1, h2, h3, .page-title { font-family: 'Playfair Display', serif; }
        .handwriting { font-family: 'Cedarville Cursive', cursive; }
        
        /* ===== FLOATING HEARTS ===== */
        .heaven-container {
            position: fixed;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
        }
        
        .floating-heart {
            position: absolute;
            font-size: 24px;
            opacity: 0.4;
            animation: floatAround 25s infinite linear;
            color: var(--primary-pink);
        }
        
        @keyframes floatAround {
            0% { transform: translateY(100vh) translateX(0) rotate(0deg); opacity: 0; }
            10% { opacity: 0.5; }
            90% { opacity: 0.5; }
            100% { transform: translateY(-100px) translateX(100px) rotate(360deg); opacity: 0; }
        }
        
        /* ===== FALLING PETALS ===== */
        .petal {
            position: fixed;
            font-size: 20px;
            opacity: 0.6;
            pointer-events: none;
            z-index: 9998;
            animation: fall linear forwards;
        }
        
        @keyframes fall {
            to { transform: translateY(100vh) rotate(360deg); }
        }
        
        /* ===== LOADING SCREEN ===== */
        #loading-screen {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, #667eea, #764ba2, #9b59b6);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            z-index: 9999;
            transition: opacity 1s ease;
        }
        
        .loading-heart {
            width: 180px;
            height: 180px;
            background: rgba(255, 255, 255, 0.15);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 50px;
            animation: heartbeat 1.5s infinite;
            border: 4px solid rgba(255, 255, 255, 0.3);
            box-shadow: 0 0 80px rgba(255, 255, 255, 0.5);
        }
        
        .loading-heart i { font-size: 6rem; color: white; filter: drop-shadow(0 0 20px gold); }
        
        .loading-text {
            font-family: 'Playfair Display', serif;
            font-size: 3rem;
            color: white;
            text-align: center;
            margin-bottom: 40px;
            text-shadow: 2px 2px 20px rgba(0,0,0,0.3);
            animation: glow 2s infinite alternate;
        }
        
        @keyframes glow {
            from { text-shadow: 0 0 20px gold; }
            to { text-shadow: 0 0 40px #ff6b8b, 0 0 20px gold; }
        }
        
        .loading-bar-container {
            width: 500px;
            height: 8px;
            background: rgba(255, 255, 255, 0.2);
            border-radius: 4px;
            overflow: hidden;
        }
        
        .loading-bar {
            height: 100%;
            width: 0%;
            background: linear-gradient(90deg, #ffd700, #ff6b8b, #9b59b6);
            transition: width 0.4s;
        }
        
        @keyframes heartbeat { 0%,100%{transform:scale(1)} 50%{transform:scale(1.1)} }
        
        /* ===== PASSWORD SCREEN ===== */
        #password-screen {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, #667eea, #764ba2, #9b59b6);
            display: none;
            justify-content: center;
            align-items: center;
            z-index: 9998;
            backdrop-filter: blur(10px);
        }
        
        .password-crystal {
            background: rgba(255, 255, 255, 0.98);
            padding: 60px;
            border-radius: 50px;
            box-shadow: 0 40px 80px rgba(0,0,0,0.3);
            text-align: center;
            max-width: 600px;
            width: 90%;
            border: 4px solid var(--primary-gold);
            animation: crystalGlow 3s infinite alternate;
        }
        
        @keyframes crystalGlow {
            from { box-shadow: 0 0 30px rgba(255, 215, 0, 0.3); }
            to { box-shadow: 0 0 60px rgba(255, 215, 0, 0.6); }
        }
        
        .password-crystal h2 {
            font-family: 'Playfair Display', serif;
            font-size: 3rem;
            background: var(--gradient-pink);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 20px;
        }
        
        #password-input {
            font-family: 'Montserrat', sans-serif;
            font-size: 1.3rem;
            padding: 20px 30px;
            border: 3px solid #e0e0e0;
            border-radius: 60px;
            width: 100%;
            text-align: center;
            margin: 30px 0;
            transition: all 0.3s;
        }
        
        #password-input:focus {
            outline: none;
            border-color: var(--primary-gold);
            box-shadow: 0 0 0 8px rgba(255, 215, 0, 0.2);
        }
        
        /* ===== MAIN CONTAINER ===== */
        .main-universe {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
            display: none;
        }
        
        /* ===== LOVE PAGES ===== */
        .love-page {
            background: rgba(255, 255, 255, 0.97);
            min-height: 85vh;
            padding: 70px 60px;
            margin: 50px 0 80px;
            border-radius: 60px;
            box-shadow: var(--shadow-lg);
            position: relative;
            display: none;
            transform: translateY(50px);
            opacity: 0;
            transition: all 0.8s cubic-bezier(0.34, 1.56, 0.64, 1);
            border: 3px solid rgba(255, 133, 162, 0.4);
        }
        
        .love-page.active { display: block; transform: translateY(0); opacity: 1; }
        
        .page-title {
            font-family: 'Playfair Display', serif;
            font-size: 3.5rem;
            text-align: center;
            background: var(--gradient-sunset);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 50px;
            position: relative;
            padding-bottom: 25px;
        }
        
        .page-title::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 200px;
            height: 5px;
            background: var(--gradient-sunset);
            border-radius: 3px;
        }
        
        .page-content {
            font-family: 'Montserrat', sans-serif;
            font-size: 1.2rem;
            line-height: 2;
            text-align: center;
            padding: 0 30px;
        }
        
        /* ===== NAVIGATION BUTTONS ===== */
        .nav-buttons {
            display: flex;
            justify-content: space-between;
            margin-top: 70px;
            padding: 0 30px;
        }
        
        .nav-btn {
            background: var(--gradient-pink);
            color: white;
            border: none;
            padding: 18px 45px;
            border-radius: 60px;
            font-family: 'Montserrat', sans-serif;
            font-size: 1.2rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
            box-shadow: 0 15px 30px rgba(255, 133, 162, 0.3);
            display: flex;
            align-items: center;
            gap: 12px;
            position: relative;
            overflow: hidden;
        }
        
        .nav-btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.3), transparent);
            transition: 0.5s;
        }
        
        .nav-btn:hover::before { left: 100%; }
        .nav-btn:hover { transform: translateY(-8px); box-shadow: 0 20px 40px rgba(255, 133, 162, 0.5); }
        .nav-btn.hidden { visibility: hidden; }
        
        /* ===== MUSIC PLAYER ===== */
        .music-station {
            position: fixed;
            top: 25px;
            right: 25px;
            background: rgba(255, 255, 255, 0.98);
            border-radius: 60px;
            padding: 15px 30px;
            box-shadow: var(--shadow-lg);
            display: flex;
            align-items: center;
            gap: 20px;
            z-index: 100;
            border: 3px solid var(--primary-pink);
            backdrop-filter: blur(10px);
        }
        
        #music-toggle {
            background: var(--gradient-pink);
            border: none;
            width: 55px;
            height: 55px;
            border-radius: 50%;
            color: white;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.4rem;
            transition: all 0.3s;
        }
        
        #music-toggle:hover { transform: scale(1.15) rotate(15deg); box-shadow: 0 0 30px var(--primary-pink); }
        
        /* ===== BIRTHDAY COUNTDOWN ===== */
        .birthday-box {
            background: linear-gradient(135deg, var(--primary-pink), var(--primary-red));
            color: white;
            padding: 30px;
            border-radius: 30px;
            margin: 30px auto;
            max-width: 400px;
            text-align: center;
            box-shadow: var(--shadow-lg);
        }
        
        .birthday-number {
            font-size: 4rem;
            font-weight: bold;
            margin: 15px 0;
        }
        
        /* ===== REASONS COUNTER ===== */
        .reasons-box {
            background: linear-gradient(135deg, var(--primary-gold), #ffb347);
            color: white;
            padding: 30px;
            border-radius: 30px;
            margin: 30px auto;
            max-width: 400px;
            text-align: center;
            box-shadow: var(--shadow-lg);
        }
        
        .reasons-number {
            font-size: 4rem;
            font-weight: bold;
            margin: 15px 0;
        }
        
        .reasons-btn {
            background: white;
            color: var(--primary-red);
            border: none;
            padding: 15px 30px;
            border-radius: 50px;
            font-size: 1.2rem;
            cursor: pointer;
            transition: all 0.3s;
            margin-top: 15px;
        }
        
        .reasons-btn:hover {
            transform: scale(1.1);
            box-shadow: 0 10px 20px rgba(0,0,0,0.2);
        }
        
        /* ===== QUIZ SYSTEM ===== */
        .quiz-container {
            max-width: 800px;
            margin: 40px auto;
            padding: 40px;
            background: white;
            border-radius: 40px;
            box-shadow: var(--shadow-lg);
            border: 3px solid var(--primary-pink);
            min-height: 500px;
        }
        
        .quiz-question {
            font-size: 1.8rem;
            font-weight: 600;
            color: var(--primary-red);
            margin-bottom: 40px;
            text-align: center;
            animation: slideIn 0.5s ease;
        }
        
        .quiz-options { display: flex; flex-direction: column; gap: 20px; margin-bottom: 30px; }
        
        .quiz-option {
            padding: 20px 30px;
            background: linear-gradient(135deg, #f8f9fa, #f1f3f5);
            border-radius: 60px;
            cursor: pointer;
            transition: all 0.4s;
            border: 3px solid transparent;
            font-weight: 500;
            font-size: 1.2rem;
            text-align: left;
        }
        
        .quiz-option:hover { background: var(--gradient-pink); color: white; transform: translateX(20px); }
        .quiz-option.correct { background: #d4edda; border-color: #28a745; color: #155724; animation: correctPulse 0.5s; }
        .quiz-option.wrong { background: #f8d7da; border-color: #dc3545; color: #721c24; animation: shake 0.5s; }
        
        @keyframes correctPulse {
            0%,100%{transform:scale(1)} 50%{transform:scale(1.05); background:#c3e6cb;}
        }
        
        @keyframes shake {
            0%,100%{transform:translateX(0)} 25%{transform:translateX(-10px)} 75%{transform:translateX(10px)}
        }
        
        @keyframes slideIn { from{opacity:0;transform:translateX(-30px)} to{opacity:1;transform:translateX(0)} }
        
        .quiz-counter { font-size: 1.1rem; color: #666; margin-bottom: 20px; text-align: center; }
        
        .quiz-result {
            margin-top: 40px;
            padding: 30px;
            background: linear-gradient(135deg, #fff9e6, #fff3cd);
            border-radius: 30px;
            border: 3px solid var(--primary-gold);
            animation: fadeIn 0.5s;
        }
        
        .quiz-result h3 { font-size: 2rem; color: var(--primary-red); margin-bottom: 20px; }
        .quiz-result p { font-size: 1.3rem; line-height: 1.6; }
        
        .quiz-progress {
            width: 100%;
            height: 8px;
            background: #f0f0f0;
            border-radius: 4px;
            margin: 20px 0;
            overflow: hidden;
        }
        
        .quiz-progress-bar { height: 100%; background: var(--gradient-pink); width: 0%; transition: width 0.3s; }
        
        /* ===== TIMELINE MASTER ===== */
        .timeline-master {
            position: relative;
            max-width: 900px;
            margin: 60px auto;
        }
        
        .timeline-beam {
            position: absolute;
            left: 50%;
            top: 0;
            bottom: 0;
            width: 6px;
            background: var(--gradient-pink);
            transform: translateX(-50%);
            box-shadow: 0 0 30px var(--primary-pink);
            border-radius: 3px;
        }
        
        .timeline-star {
            position: relative;
            margin-bottom: 80px;
            width: 100%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            cursor: pointer;
        }
        
        .timeline-star:nth-child(even) { flex-direction: row-reverse; }
        
        .star-date {
            width: 45%;
            padding: 25px;
            background: white;
            border-radius: 25px;
            border: 4px solid var(--primary-pink);
            text-align: center;
            transition: all 0.3s;
            box-shadow: var(--shadow-md);
        }
        
        .star-date:hover { transform: scale(1.08) rotate(1deg); border-color: var(--primary-gold); }
        .star-date::before { content: '⭐'; position: absolute; top: -15px; left: -15px; font-size: 2rem; }
        
        .star-memory {
            width: 45%;
            padding: 25px;
            background: var(--gradient-pink);
            border-radius: 25px;
            color: white;
            display: none;
            animation: fadeIn 0.5s;
            box-shadow: var(--shadow-md);
        }
        
        .timeline-star.active .star-memory { display: block; }
        
        /* ===== MEMORY TEMPLE (GAME) ===== */
        .memory-temple {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 20px;
            margin: 50px auto;
            max-width: 600px;
        }
        
        .memory-card {
            aspect-ratio: 1;
            background: var(--gradient-pink);
            border-radius: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 3rem;
            color: white;
            cursor: pointer;
            transition: all 0.4s;
            transform-style: preserve-3d;
            box-shadow: var(--shadow-md);
        }
        
        .memory-card.flipped { background: white; color: var(--primary-pink); transform: rotateY(180deg); }
        .memory-card.matched { opacity: 0.5; cursor: default; filter: grayscale(0.7); }
        
        /* ===== DREAM GARDEN ===== */
        .dream-garden {
            display: flex;
            flex-wrap: wrap;
            gap: 35px;
            justify-content: center;
            margin: 60px 0;
        }
        
        .dream-flower {
            width: 220px;
            padding: 40px 20px;
            background: linear-gradient(135deg, #667eea, #764ba2);
            border-radius: 40px 40px 20px 20px;
            text-align: center;
            color: white;
            cursor: pointer;
            transition: all 0.4s;
            position: relative;
            overflow: hidden;
            box-shadow: var(--shadow-md);
        }
        
        .dream-flower:nth-child(2n) { background: linear-gradient(135deg, #ff6b8b, #ff4757); }
        .dream-flower:nth-child(3n) { background: linear-gradient(135deg, #00b4db, #0083b0); }
        .dream-flower:hover { transform: translateY(-20px) rotate(3deg); }
        
        .dream-flower i { font-size: 4rem; margin-bottom: 20px; }
        
        .dream-petal {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.95);
            border-radius: 40px 40px 20px 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 25px;
            opacity: 0;
            transition: opacity 0.3s;
            pointer-events: none;
            color: white;
        }
        
        .dream-flower:hover .dream-petal { opacity: 1; }
        
        /* ===== HEART HUNT ===== */
        .treasure-map {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 25px;
            margin: 50px auto;
            max-width: 500px;
        }
        
        .treasure-cell {
            aspect-ratio: 1;
            background: linear-gradient(135deg, #f8f9fa, #e9ecef);
            border-radius: 25px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2.5rem;
            cursor: pointer;
            border: 4px dashed #adb5bd;
            transition: all 0.3s;
        }
        
        .treasure-cell:hover { transform: scale(1.1); border-color: var(--primary-gold); }
        .treasure-cell.found { background: linear-gradient(135deg, #d4edda, #c3e6cb); border-color: #28a745; }
        
        /* ===== LOVE COMPASS ===== */
        .love-compass {
            display: flex;
            flex-wrap: wrap;
            gap: 40px;
            align-items: center;
            justify-content: center;
            margin: 50px 0;
        }
        
        .compass-input {
            padding: 20px 30px;
            border: 3px solid var(--primary-pink);
            border-radius: 60px;
            font-size: 1.2rem;
            width: 280px;
            transition: all 0.3s;
            background: white;
        }
        
        .compass-input:focus {
            outline: none;
            border-color: var(--primary-gold);
            box-shadow: 0 0 0 8px rgba(255, 133, 162, 0.2);
            transform: scale(1.05);
        }
        
        .compass-heart { font-size: 3.5rem; animation: heartbeat 1.5s infinite; }
        .compass-result { font-size: 4rem; font-weight: 800; background: var(--gradient-sunset); -webkit-background-clip: text; -webkit-text-fill-color: transparent; }
        
        /* ===== HER SPECIAL PAGE ===== */
        .her-section {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 30px;
            margin: 50px 0;
        }
        
        .her-card {
            background: white;
            padding: 30px;
            border-radius: 30px;
            box-shadow: var(--shadow-md);
            border: 3px solid var(--primary-gold);
            text-align: center;
            transition: all 0.4s;
        }
        
        .her-card:hover { transform: translateY(-10px); border-color: var(--primary-pink); }
        .her-card i { font-size: 3rem; color: var(--primary-pink); margin-bottom: 15px; }
        .her-card h3 { color: var(--primary-red); margin-bottom: 15px; }
        
        /* ===== OUR SONG LYRICS PAGE ===== */
        .lyrics-container {
            max-width: 700px;
            margin: 40px auto;
            padding: 40px;
            background: rgba(255,255,255,0.9);
            border-radius: 40px;
            border: 3px solid var(--primary-pink);
            white-space: pre-line;
            line-height: 2;
            font-size: 1.3rem;
            text-align: center;
        }
        
        .highlight-lyric {
            color: var(--primary-red);
            font-weight: bold;
            font-size: 1.5rem;
        }
        
        /* ===== SPOTIFY PLAYLIST ===== */
        .spotify-container {
            max-width: 600px;
            margin: 30px auto;
            border-radius: 30px;
            overflow: hidden;
            box-shadow: var(--shadow-lg);
        }
        
        /* ===== LOVE LETTER GENERATOR ===== */
        .letter-generator {
            background: white;
            padding: 40px;
            border-radius: 40px;
            box-shadow: var(--shadow-lg);
            text-align: center;
            margin: 40px 0;
        }
        
        .generated-letter {
            font-size: 1.5rem;
            padding: 30px;
            background: linear-gradient(135deg, #fff5f7, #ffeef1);
            border-radius: 30px;
            margin: 20px 0;
            min-height: 150px;
            display: flex;
            align-items: center;
            justify-content: center;
            border: 3px dashed var(--primary-pink);
        }
        
        /* ===== GOOD MORNING/NIGHT BUTTON ===== */
        .greeting-buttons {
            display: flex;
            gap: 20px;
            justify-content: center;
            margin: 40px 0;
        }
        
        .greeting-btn {
            padding: 20px 40px;
            font-size: 1.5rem;
            background: var(--gradient-pink);
            color: white;
            border: none;
            border-radius: 60px;
            cursor: pointer;
            transition: all 0.3s;
            box-shadow: var(--shadow-md);
        }
        
        .greeting-btn:hover { transform: scale(1.1); }
        
        /* ===== FUTURE PLANS MAP ===== */
        .plans-map {
            display: flex;
            flex-wrap: wrap;
            gap: 30px;
            justify-content: center;
            margin: 50px 0;
        }
        
        .plan-location {
            width: 250px;
            padding: 30px;
            background: var(--gradient-blue);
            border-radius: 30px;
            color: white;
            text-align: center;
            transition: all 0.4s;
        }
        
        .plan-location:hover { transform: translateY(-15px) scale(1.05); }
        .plan-location i { font-size: 3rem; margin-bottom: 15px; }
        .plan-dream { margin-top: 15px; font-size: 0.9rem; opacity: 0.9; }
        
        /* ===== PHOTO GALLERY (NO TITLES) ===== */
        .photo-gallery {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 30px;
            margin: 50px 0;
        }
        
        .photo-frame {
            aspect-ratio: 1;
            background: linear-gradient(135deg, #f8f9fa, #e9ecef);
            border-radius: 30px;
            overflow: hidden;
            border: 4px solid var(--primary-pink);
            box-shadow: var(--shadow-md);
            transition: all 0.4s;
        }
        
        .photo-frame:hover { transform: translateY(-15px) rotate(2deg); border-color: var(--primary-gold); }
        .photo-frame img { width: 100%; height: 100%; object-fit: cover; }
        
        .photo-message {
            text-align: center;
            margin-top: 30px;
            padding: 20px;
            background: linear-gradient(135deg, #fff5f7, #ffeef1);
            border-radius: 30px;
            font-size: 1.5rem;
            color: var(--primary-red);
            border: 2px dashed var(--primary-pink);
        }
        
        /* ===== VOICE NOTES ===== */
        .voice-gallery {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 30px;
            margin: 50px 0;
        }
        
        .voice-card {
            background: white;
            padding: 30px;
            border-radius: 30px;
            box-shadow: var(--shadow-md);
            border: 3px solid var(--primary-pink);
            text-align: center;
            transition: all 0.4s;
            cursor: pointer;
        }
        
        .voice-card:hover { transform: translateY(-10px); border-color: var(--primary-gold); }
        .voice-icon { font-size: 4rem; color: var(--primary-pink); margin-bottom: 15px; animation: pulse 2s infinite; }
        .voice-title { font-size: 1.5rem; font-weight: 600; margin-bottom: 10px; }
        
        .voice-player {
            width: 100%;
            height: 50px;
            background: #f0f0f0;
            border-radius: 25px;
            display: flex;
            align-items: center;
            padding: 0 20px;
            gap: 15px;
        }
        
        .voice-play-btn {
            width: 40px;
            height: 40px;
            background: var(--gradient-pink);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            cursor: pointer;
            transition: all 0.3s;
        }
        
        .voice-play-btn:hover { transform: scale(1.1); }
        
        .voice-progress {
            flex: 1;
            height: 6px;
            background: #ddd;
            border-radius: 3px;
            overflow: hidden;
        }
        
        .voice-progress-bar { height: 100%; width: 0%; background: var(--gradient-pink); transition: width 0.1s; }
        .voice-time { font-size: 0.9rem; color: #999; }
        
        @keyframes pulse { 0%,100%{transform:scale(1)} 50%{transform:scale(1.1)} }
        
        /* ===== VALENTINE FINAL ===== */
        .valentine-sanctuary {
            text-align: center;
            margin: 70px 0;
            padding: 70px;
            background: linear-gradient(135deg, #fff5f7, #ffeef1);
            border-radius: 80px;
            border: 5px solid var(--primary-gold);
            position: relative;
            overflow: hidden;
        }
        
        .valentine-sanctuary::before {
            content: '💖💕💗';
            position: absolute;
            font-size: 15rem;
            opacity: 0.1;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            white-space: nowrap;
        }
        
        .valentine-question { font-size: 3.5rem; color: var(--primary-red); margin: 40px 0; font-weight: 800; }
        
        .valentine-btn {
            font-size: 2.5rem;
            padding: 35px 100px;
            background: var(--gradient-pink);
            border: none;
            color: white;
            border-radius: 100px;
            cursor: pointer;
            transition: all 0.3s;
            animation: heartbeat 1.5s infinite;
            margin: 40px 0;
            box-shadow: 0 20px 50px rgba(255, 133, 162, 0.5);
        }
        
        .valentine-btn:hover { transform: scale(1.15); box-shadow: 0 0 80px var(--primary-pink); }
        #valentine-response { display: none; margin-top: 50px; }
        .signature { font-family: 'Playfair Display', serif; font-size: 3rem; color: var(--primary-red); margin-top: 40px; }
        
        /* ===== RESPONSIVE ===== */
        @media (max-width: 992px) {
            .love-page { padding: 50px 40px; }
            .page-title { font-size: 2.8rem; }
            .quiz-question { font-size: 1.5rem; }
        }
        
        @media (max-width: 768px) {
            .music-station { top: 15px; right: 15px; padding: 10px 20px; }
            .love-page { padding: 40px 25px; }
            .page-title { font-size: 2.2rem; }
            .nav-buttons { flex-direction: column; gap: 20px; }
            .nav-btn { width: 100%; justify-content: center; }
            .quiz-container { padding: 30px 20px; }
            .quiz-option { padding: 15px 20px; font-size: 1rem; }
            .memory-temple { grid-template-columns: repeat(3, 1fr); }
            .photo-gallery { grid-template-columns: repeat(2, 1fr); gap: 20px; }
            .voice-gallery { grid-template-columns: 1fr; }
            .valentine-question { font-size: 2.5rem; }
            .valentine-btn { font-size: 1.8rem; padding: 25px 60px; }
            .greeting-buttons { flex-direction: column; }
        }
        
        @media (max-width: 480px) {
            .page-title { font-size: 1.8rem; }
            .memory-temple { grid-template-columns: repeat(2, 1fr); }
            .photo-gallery { grid-template-columns: 1fr; }
            .valentine-question { font-size: 2rem; }
        }
        
        @keyframes fadeIn { from{opacity:0;transform:translateY(20px)} to{opacity:1;transform:translateY(0)} }
        @keyframes floatDown { to{transform:translateY(100vh) rotate(360deg)} }
        @keyframes slideUp { from{opacity:0;transform:translateX(-50%) translateY(50px)} to{opacity:1;transform:translateX(-50%) translateY(0)} }
        @keyframes slideDown { from{opacity:1;transform:translateX(-50%) translateY(0)} to{opacity:0;transform:translateX(-50%) translateY(50px)} }
    </style>
</head>
<body>
    <!-- Floating Hearts -->
    <div class="heaven-container" id="heaven"></div>
    
    <!-- Loading Screen -->
    <div id="loading-screen">
        <div class="loading-heart"><i class="fas fa-heart"></i></div>
        <div class="loading-text" id="loading-text">🌌 Creating Sveta's World...</div>
        <div class="loading-bar-container"><div class="loading-bar" id="loading-bar"></div></div>
    </div>
    
    <!-- Password Screen -->
    <div id="password-screen">
        <div class="password-crystal">
            <h2>🔮 Only Someone Special</h2>
            <p style="font-size: 1.3rem; color: #666; margin-bottom: 30px;">Only someone special can enter this world… and that person is you, Sveta.</p>
            <input type="text" id="password-input" placeholder="Enter the magic word..." autocomplete="off">
            <button class="nav-btn" id="password-submit" style="width: 100%; justify-content: center;">
                <i class="fas fa-key"></i> Enter My World
            </button>
            <p style="margin-top: 30px; color: #888; font-style: italic;">💡 Hint: cat app 🐱</p>
        </div>
    </div>
    
    <!-- Main Universe -->
    <div class="main-universe" id="main-universe">
        <!-- Music Player -->
        <div class="music-station">
            <button id="music-toggle"><i class="fas fa-play"></i></button>
            <div style="font-weight: 600;">🎵 For Sveta</div>
        </div>
        
        <!-- ===== PAGE 1: WELCOME ===== -->
        <div class="love-page active" id="page1">
            <h1 class="page-title">Hey my Sveta 🤍</h1>
            <div class="page-content">
                <p class="handwriting" style="font-size: 2rem;">This isn't just a website… it's a little world made only for us.</p>
                <p style="margin: 30px 0; font-size: 1.3rem;">Every page here holds a memory, a feeling, or something I never want you to forget.</p>
                <p style="font-size: 1.3rem;">Take your time, read slowly, and just feel how much you mean to me.</p>
                
                <!-- Birthday Countdown -->
                <div class="birthday-box">
                    <h3>🎂 Sveta's Birthday is in:</h3>
                    <div class="birthday-number" id="birthday-countdown">...</div>
                    <div>days! (June 16)</div>
                </div>
                
                <!-- Reasons Counter -->
                <div class="reasons-box">
                    <h3>💕 Reasons I Love You</h3>
                    <div class="reasons-number" id="reasons-counter">100</div>
                    <div>and counting...</div>
                    <button class="reasons-btn" onclick="addReason()">
                        <i class="fas fa-plus"></i> Add Another Reason
                    </button>
                </div>
                
                <!-- Good Morning/Good Night Buttons -->
                <div class="greeting-buttons">
                    <button class="greeting-btn" onclick="sendGreeting('morning')">☀️ Good Morning my Sveta</button>
                    <button class="greeting-btn" onclick="sendGreeting('night')">🌙 Good Night my love</button>
                </div>
                
                <div style="margin: 50px 0;">
                    <i class="fas fa-heart" style="font-size: 3rem; color: var(--primary-pink); margin: 0 10px;"></i>
                    <i class="fas fa-heart" style="font-size: 4rem; color: var(--primary-red); margin: 0 10px;"></i>
                    <i class="fas fa-heart" style="font-size: 3rem; color: var(--primary-gold); margin: 0 10px;"></i>
                </div>
            </div>
            <div class="nav-buttons">
                <button class="nav-btn hidden">Previous</button>
                <button class="nav-btn next-btn" onclick="nextPage(2)">Begin Journey <i class="fas fa-arrow-right"></i></button>
            </div>
        </div>
        
        <!-- ===== PAGE 2: TIMELINE ===== -->
        <div class="love-page" id="page2">
            <h1 class="page-title">⏳ Our Memories</h1>
            <div class="page-content">
                <p>Click on each star to unlock the memory ✨</p>
                <div class="timeline-master">
                    <div class="timeline-beam"></div>
                    
                    <div class="timeline-star" onclick="toggleMemory(1)">
                        <div class="star-date"><h3>Memory 1</h3><p>The Beginning</p></div>
                        <div class="star-memory" id="memory1"><p>The moment we met, something felt different. I didn't know it yet, but my heart had already started choosing you, Sveta.</p></div>
                    </div>
                    
                    <div class="timeline-star" onclick="toggleMemory(2)">
                        <div class="star-date"><h3>Memory 2</h3><p>First Real Conversation</p></div>
                        <div class="star-memory" id="memory2"><p>That moment when talking to you felt easy, natural… like I already knew you.</p></div>
                    </div>
                    
                    <div class="timeline-star" onclick="toggleMemory(3)">
                        <div class="star-date"><h3>Memory 3</h3><p>First Laugh Together</p></div>
                        <div class="star-memory" id="memory3"><p>The first time you made me laugh and I realized I wanted more moments like that forever.</p></div>
                    </div>
                    
                    <div class="timeline-star" onclick="toggleMemory(4)">
                        <div class="star-date"><h3>Memory 4</h3><p>First Deep Talk</p></div>
                        <div class="star-memory" id="memory4"><p>When we shared real feelings and I felt closer to you than ever.</p></div>
                    </div>
                    
                    <div class="timeline-star" onclick="toggleMemory(5)">
                        <div class="star-date"><h3>Memory 5</h3><p>First Movie Night</p></div>
                        <div class="star-memory" id="memory5"><p>Even through a screen, it felt warm… like we were already creating our little world.</p></div>
                    </div>
                    
                    <div class="timeline-star" onclick="toggleMemory(6)">
                        <div class="star-date"><h3>Memory 6</h3><p>The Realization</p></div>
                        <div class="star-memory" id="memory6"><p>The moment I understood that you weren't just someone special… you were becoming my favorite person.</p></div>
                    </div>
                </div>
                
                <div style="margin-top: 40px; padding: 30px; background: rgba(255,255,255,0.8); border-radius: 20px;">
                    <p class="handwriting" style="font-size: 1.8rem;">My love 🤍</p>
                    <p>If you're reading this, I want you to remember something simple: you are deeply loved.</p>
                    <p>Not for being perfect, but for being real.</p>
                    <p>Every little thing about you has become part of my happiness.</p>
                    <p style="margin-top: 20px;">This page exists because you exist.</p>
                    <p>Because someone like you deserves a place where every word reminds her how loved she truly is.</p>
                </div>
            </div>
            <div class="nav-buttons">
                <button class="nav-btn prev-btn" onclick="prevPage(1)"><i class="fas fa-arrow-left"></i> Back</button>
                <button class="nav-btn next-btn" onclick="nextPage(3)">Next <i class="fas fa-arrow-right"></i></button>
            </div>
        </div>
        
        <!-- ===== PAGE 3: MEMORY GAME ===== -->
        <div class="love-page" id="page3">
            <h1 class="page-title">🎮 Memory Match Game</h1>
            <div class="page-content">
                <p>Find matching pairs of our special symbols!</p>
                <div class="memory-temple" id="memory-game"></div>
                <div style="margin-top: 30px;">Pairs found: <span id="pairs-found">0</span>/6</div>
                <button class="nav-btn" onclick="resetMemoryGame()" style="margin: 20px auto;">Reset Game</button>
            </div>
            <div class="nav-buttons">
                <button class="nav-btn prev-btn" onclick="prevPage(2)"><i class="fas fa-arrow-left"></i> Back</button>
                <button class="nav-btn next-btn" onclick="nextPage(4)">Next <i class="fas fa-arrow-right"></i></button>
            </div>
        </div>
        
        <!-- ===== PAGE 4: QUIZ 1 ===== -->
        <div class="love-page" id="page4">
            <h1 class="page-title">💌 Quiz 1: How Well Do You Know Us?</h1>
            <div class="page-content">
                <div class="quiz-container" id="quiz1-container">
                    <div class="quiz-progress"><div class="quiz-progress-bar" id="quiz1-progress"></div></div>
                    <div class="quiz-counter" id="quiz1-counter">Question 1/5</div>
                    <div class="quiz-question" id="quiz1-question"></div>
                    <div class="quiz-options" id="quiz1-options"></div>
                    <div id="quiz1-result" class="quiz-result" style="display: none;"></div>
                </div>
            </div>
            <div class="nav-buttons">
                <button class="nav-btn prev-btn" onclick="prevPage(3)"><i class="fas fa-arrow-left"></i> Back</button>
                <button class="nav-btn next-btn" onclick="nextPage(5)">Next <i class="fas fa-arrow-right"></i></button>
            </div>
        </div>
        
        <!-- ===== PAGE 5: QUIZ 2 ===== -->
        <div class="love-page" id="page5">
            <h1 class="page-title">🌙 Quiz 2: Guess What I Think About You</h1>
            <div class="page-content">
                <div class="quiz-container" id="quiz2-container">
                    <div class="quiz-progress"><div class="quiz-progress-bar" id="quiz2-progress"></div></div>
                    <div class="quiz-counter" id="quiz2-counter">Question 1/5</div>
                    <div class="quiz-question" id="quiz2-question"></div>
                    <div class="quiz-options" id="quiz2-options"></div>
                    <div id="quiz2-result" class="quiz-result" style="display: none;"></div>
                </div>
            </div>
            <div class="nav-buttons">
                <button class="nav-btn prev-btn" onclick="prevPage(4)"><i class="fas fa-arrow-left"></i> Back</button>
                <button class="nav-btn next-btn" onclick="nextPage(6)">Next <i class="fas fa-arrow-right"></i></button>
            </div>
        </div>
        
        <!-- ===== PAGE 6: QUIZ 3 ===== -->
        <div class="love-page" id="page6">
            <h1 class="page-title">🌍 Quiz 3: Future Dreams</h1>
            <div class="page-content">
                <div class="quiz-container" id="quiz3-container">
                    <div class="quiz-progress"><div class="quiz-progress-bar" id="quiz3-progress"></div></div>
                    <div class="quiz-counter" id="quiz3-counter">Question 1/5</div>
                    <div class="quiz-question" id="quiz3-question"></div>
                    <div class="quiz-options" id="quiz3-options"></div>
                    <div id="quiz3-result" class="quiz-result" style="display: none;"></div>
                </div>
            </div>
            <div class="nav-buttons">
                <button class="nav-btn prev-btn" onclick="prevPage(5)"><i class="fas fa-arrow-left"></i> Back</button>
                <button class="nav-btn next-btn" onclick="nextPage(7)">Next <i class="fas fa-arrow-right"></i></button>
            </div>
        </div>
        
        <!-- ===== PAGE 7: QUIZ 4 ===== -->
        <div class="love-page" id="page7">
            <h1 class="page-title">😂 Quiz 4: Our Funny Moments</h1>
            <div class="page-content">
                <div class="quiz-container" id="quiz4-container">
                    <div class="quiz-progress"><div class="quiz-progress-bar" id="quiz4-progress"></div></div>
                    <div class="quiz-counter" id="quiz4-counter">Question 1/5</div>
                    <div class="quiz-question" id="quiz4-question"></div>
                    <div class="quiz-options" id="quiz4-options"></div>
                    <div id="quiz4-result" class="quiz-result" style="display: none;"></div>
                </div>
            </div>
            <div class="nav-buttons">
                <button class="nav-btn prev-btn" onclick="prevPage(6)"><i class="fas fa-arrow-left"></i> Back</button>
                <button class="nav-btn next-btn" onclick="nextPage(8)">Next <i class="fas fa-arrow-right"></i></button>
            </div>
        </div>
        
        <!-- ===== PAGE 8: QUIZ 5 ===== -->
        <div class="love-page" id="page8">
            <h1 class="page-title">❤️ Quiz 5: Final Heart Quiz</h1>
            <div class="page-content">
                <div class="quiz-container" id="quiz5-container">
                    <div class="quiz-progress"><div class="quiz-progress-bar" id="quiz5-progress"></div></div>
                    <div class="quiz-counter" id="quiz5-counter">Question 1/5</div>
                    <div class="quiz-question" id="quiz5-question"></div>
                    <div class="quiz-options" id="quiz5-options"></div>
                    <div id="quiz5-result" class="quiz-result" style="display: none;"></div>
                </div>
            </div>
            <div class="nav-buttons">
                <button class="nav-btn prev-btn" onclick="prevPage(7)"><i class="fas fa-arrow-left"></i> Back</button>
                <button class="nav-btn next-btn" onclick="nextPage(9)">Next <i class="fas fa-arrow-right"></i></button>
            </div>
        </div>
        
        <!-- ===== PAGE 9: DREAM GARDEN ===== -->
        <div class="love-page" id="page9">
            <h1 class="page-title">🌸 Dream Garden</h1>
            <div class="page-content">
                <p>Hover over each flower to see our dreams ✨</p>
                <div class="dream-garden">
                    <div class="dream-flower"><i class="fas fa-coffee"></i><h3>First Coffee Together</h3><div class="dream-petal">Just sitting across from you, finally real ☕</div></div>
                    <div class="dream-flower"><i class="fas fa-utensils"></i><h3>Cooking Together</h3><div class="dream-petal">Laughing in the kitchen, even if we mess up 👨‍🍳</div></div>
                    <div class="dream-flower"><i class="fas fa-moon"></i><h3>Late Night Walk</h3><div class="dream-petal">Talking about everything and nothing 🌙</div></div>
                    <div class="dream-flower"><i class="fas fa-tree"></i><h3>Picnic Day</h3><div class="dream-petal">Simple food, soft laughs, and peace ☀️</div></div>
                    <div class="dream-flower"><i class="fas fa-camera"></i><h3>Photos Together</h3><div class="dream-petal">Capturing moments we waited so long for 📸</div></div>
                    <div class="dream-flower"><i class="fas fa-heart"></i><h3>No Distance</h3><div class="dream-petal">Just us, side by side 💖</div></div>
                </div>
            </div>
            <div class="nav-buttons">
                <button class="nav-btn prev-btn" onclick="prevPage(8)"><i class="fas fa-arrow-left"></i> Back</button>
                <button class="nav-btn next-btn" onclick="nextPage(10)">Next <i class="fas fa-arrow-right"></i></button>
            </div>
        </div>
        
        <!-- ===== PAGE 10: HEART HUNT ===== -->
        <div class="love-page" id="page10">
            <h1 class="page-title">🔍 Heart Hunt</h1>
            <div class="page-content">
                <p>Find all 9 hidden hearts!</p>
                <div class="treasure-map">
                    <div class="treasure-cell" onclick="findHeart(1)" id="heart1">❓</div>
                    <div class="treasure-cell" onclick="findHeart(2)" id="heart2">❓</div>
                    <div class="treasure-cell" onclick="findHeart(3)" id="heart3">❓</div>
                    <div class="treasure-cell" onclick="findHeart(4)" id="heart4">❓</div>
                    <div class="treasure-cell" onclick="findHeart(5)" id="heart5">❓</div>
                    <div class="treasure-cell" onclick="findHeart(6)" id="heart6">❓</div>
                    <div class="treasure-cell" onclick="findHeart(7)" id="heart7">❓</div>
                    <div class="treasure-cell" onclick="findHeart(8)" id="heart8">❓</div>
                    <div class="treasure-cell" onclick="findHeart(9)" id="heart9">❓</div>
                </div>
                <p>Hearts found: <span id="hearts-found">0</span>/9</p>
                <div id="treasure-reward" style="display: none; margin-top: 30px; padding: 30px; background: linear-gradient(135deg, #ffd700, #ffb347); border-radius: 20px;">
                    <h2>🎉 YOU FOUND ANOTHER HEART! 🎉</h2>
                    <p>"You found another heart 🤍 Just like you keep finding new places inside mine."</p>
                </div>
            </div>
            <div class="nav-buttons">
                <button class="nav-btn prev-btn" onclick="prevPage(9)"><i class="fas fa-arrow-left"></i> Back</button>
                <button class="nav-btn next-btn" onclick="nextPage(11)">Next <i class="fas fa-arrow-right"></i></button>
            </div>
        </div>
        
        <!-- ===== PAGE 11: LOVE COMPASS ===== -->
        <div class="love-page" id="page11">
            <h1 class="page-title">🧭 Love Compass</h1>
            <div class="page-content">
                <p>Type our names to see the magic ✨</p>
                <div class="love-compass">
                    <input type="text" id="name1" class="compass-input" placeholder="Your name" value="Fajr">
                    <span class="compass-heart">❤️</span>
                    <input type="text" id="name2" class="compass-input" placeholder="Her name" value="Sveta">
                </div>
                <button class="nav-btn" onclick="calculateCompatibility()" style="margin: 20px auto;">Calculate Love</button>
                <div id="compatibility-result" class="compass-result">100%</div>
                <div id="compatibility-message">Perfect Match! 💖</div>
            </div>
            <div class="nav-buttons">
                <button class="nav-btn prev-btn" onclick="prevPage(10)"><i class="fas fa-arrow-left"></i> Back</button>
                <button class="nav-btn next-btn" onclick="nextPage(12)">Next <i class="fas fa-arrow-right"></i></button>
            </div>
        </div>
        
        <!-- ===== PAGE 12: HER SPECIAL PAGE (SVETA) ===== -->
        <div class="love-page" id="page12">
            <h1 class="page-title">👸 All About Sveta</h1>
            <div class="page-content">
                <p>Everything that makes you, YOU 🤍</p>
                
                <div class="her-section">
                    <div class="her-card">
                        <i class="fas fa-smile"></i>
                        <h3>Her Smile</h3>
                        <p>The kind that stays in my mind even after we stop talking</p>
                    </div>
                    <div class="her-card">
                        <i class="fas fa-heart"></i>
                        <h3>Her Kindness</h3>
                        <p>Soft, real, and stronger than she realizes</p>
                    </div>
                    <div class="her-card">
                        <i class="fas fa-laugh"></i>
                        <h3>Her Laugh</h3>
                        <p>The sound that instantly makes my day better</p>
                    </div>
                    <div class="her-card">
                        <i class="fas fa-star"></i>
                        <h3>Her Dreams</h3>
                        <p>I want to see every one of them come true</p>
                    </div>
                    <div class="her-card">
                        <i class="fas fa-heart"></i>
                        <h3>Her Heart</h3>
                        <p>Sensitive, beautiful, and full of love</p>
                    </div>
                    <div class="her-card">
                        <i class="fas fa-infinity"></i>
                        <h3>Her Impact</h3>
                        <p>She made my life feel different in the best way 🤍</p>
                    </div>
                </div>
            </div>
            <div class="nav-buttons">
                <button class="nav-btn prev-btn" onclick="prevPage(11)"><i class="fas fa-arrow-left"></i> Back</button>
                <button class="nav-btn next-btn" onclick="nextPage(13)">Next <i class="fas fa-arrow-right"></i></button>
            </div>
        </div>
        
        <!-- ===== PAGE 13: OUR SONG ===== -->
        <div class="love-page" id="page13">
            <div style="position: absolute; top: 20px; right: 30px; font-size: 1.2rem; color: var(--primary-pink); font-weight: 600;">
                🎵 For Sveta
            </div>
            <h1 class="page-title">🎵 505 - Arctic Monkeys</h1>
            <div class="page-content">
                <p>The song that reminds me of you 🤍</p>
                
                <div class="lyrics-container" id="lyrics-container">
                    <p class="highlight-lyric">"505" - Arctic Monkeys</p>
                    <p>But I crumble completely when you cry<br>
                    It feels like once again we've missed the train<br>
                    And I'm not going to get to see you soon</p>
                    <p class="highlight-lyric">I'd probably still adore you with your hands around my neck<br>
                    Or I did last time I saw you</p>
                    <button class="nav-btn" onclick="playSong505()" style="margin-top: 30px;">
                        <i class="fas fa-play"></i> Play Our Song
                    </button>
                </div>
            </div>
            <div class="nav-buttons">
                <button class="nav-btn prev-btn" onclick="prevPage(12)"><i class="fas fa-arrow-left"></i> Back</button>
                <button class="nav-btn next-btn" onclick="nextPage(14)">Next <i class="fas fa-arrow-right"></i></button>
            </div>
        </div>
        
        <!-- ===== PAGE 14: SPOTIFY PLAYLIST ===== -->
        <div class="love-page" id="page14">
            <h1 class="page-title">🎧 Our Playlist</h1>
            <div class="page-content">
                <p>Songs that tell our story</p>
                
                <div class="spotify-container">
                    <iframe style="border-radius:12px" 
                            src="https://open.spotify.com/embed/playlist/1w02QAtkiQxU9mlAsv9Nl2?utm_source=generator&theme=0" 
                            width="100%" 
                            height="380" 
                            frameBorder="0" 
                            allowfullscreen="" 
                            allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture">
                    </iframe>
                </div>
            </div>
            <div class="nav-buttons">
                <button class="nav-btn prev-btn" onclick="prevPage(13)"><i class="fas fa-arrow-left"></i> Back</button>
                <button class="nav-btn next-btn" onclick="nextPage(15)">Next <i class="fas fa-arrow-right"></i></button>
            </div>
        </div>
        
        <!-- ===== PAGE 15: LOVE LETTER GENERATOR ===== -->
        <div class="love-page" id="page15">
            <h1 class="page-title">💌 Love Letter Generator</h1>
            <div class="page-content">
                <p>Click for a random love message</p>
                
                <div class="letter-generator">
                    <div class="generated-letter" id="love-letter">
                        You calm my heart 🤍
                    </div>
                    <button class="nav-btn" onclick="generateLoveLetter()">
                        <i class="fas fa-random"></i> Generate New Message
                    </button>
                </div>
            </div>
            <div class="nav-buttons">
                <button class="nav-btn prev-btn" onclick="prevPage(14)"><i class="fas fa-arrow-left"></i> Back</button>
                <button class="nav-btn next-btn" onclick="nextPage(16)">Next <i class="fas fa-arrow-right"></i></button>
            </div>
        </div>
        
        <!-- ===== PAGE 16: FUTURE PLANS MAP ===== -->
        <div class="love-page" id="page16">
            <h1 class="page-title">🗺️ Future Plans</h1>
            <div class="page-content">
                <p>Places we dream about together 🤍</p>
                
                <div class="plans-map">
                    <div class="plan-location">
                        <i class="fas fa-mosque"></i>
                        <h3>Istanbul</h3>
                        <p>Our first hug after all the waiting</p>
                        <p class="plan-dream">Walking together without rushing anywhere 🌅</p>
                    </div>
                    <div class="plan-location">
                        <i class="fas fa-balloon"></i>
                        <h3>Cappadocia</h3>
                        <p>Watching the sky together at sunrise 🎈</p>
                        <p class="plan-dream">Just us and quiet happiness</p>
                    </div>
                    <div class="plan-location">
                        <i class="fas fa-umbrella-beach"></i>
                        <h3>Antalya</h3>
                        <p>A peaceful day by the sea</p>
                        <p class="plan-dream">Laughing, talking, finally side by side 🏖️</p>
                    </div>
                    <div class="plan-location">
                        <i class="fas fa-mountain"></i>
                        <h3>Algeria</h3>
                        <p>Showing you my world</p>
                        <p class="plan-dream">Sharing food, moments, and real memories 🍲</p>
                    </div>
                </div>
            </div>
            <div class="nav-buttons">
                <button class="nav-btn prev-btn" onclick="prevPage(15)"><i class="fas fa-arrow-left"></i> Back</button>
                <button class="nav-btn next-btn" onclick="nextPage(17)">Next <i class="fas fa-arrow-right"></i></button>
            </div>
        </div>
        
        <!-- ===== PAGE 17: PHOTO GALLERY (NO TITLES) ===== -->
        <div class="love-page" id="page17">
            <h1 class="page-title">📸 Photo Gallery</h1>
            <div class="page-content">
                <p>6 moments that feel like little pieces of us 🤍</p>
                <div class="photo-gallery" id="photo-gallery"></div>
                <div class="photo-message">
                    "you are the most beautiful girl i ever saw😍"
                </div>
            </div>
            <div class="nav-buttons">
                <button class="nav-btn prev-btn" onclick="prevPage(16)"><i class="fas fa-arrow-left"></i> Back</button>
                <button class="nav-btn next-btn" onclick="nextPage(18)">Next <i class="fas fa-arrow-right"></i></button>
            </div>
        </div>
        
        <!-- ===== PAGE 18: VOICE NOTES ===== -->
        <div class="love-page" id="page18">
            <h1 class="page-title">🎙️ Voice Notes</h1>
            <div class="page-content">
                <p>Listen when you miss me 🤍</p>
                <div class="voice-gallery" id="voice-gallery"></div>
            </div>
            <div class="nav-buttons">
                <button class="nav-btn prev-btn" onclick="prevPage(17)"><i class="fas fa-arrow-left"></i> Back</button>
                <button class="nav-btn next-btn" onclick="nextPage(19)">Final Page <i class="fas fa-arrow-right"></i></button>
            </div>
        </div>
        
        <!-- ===== PAGE 19: VALENTINE FINAL ===== -->
        <div class="love-page" id="page19">
            <h1 class="page-title">💘 The Question</h1>
            <div class="page-content">
                <div class="valentine-sanctuary">
                    <p style="font-size: 1.8rem;">After all these pages, memories, questions, and little pieces of my heart…</p>
                    
                    <div class="valentine-question">
                        Will you keep being my Valentine, Sveta? 💕
                    </div>
                    
                    <button class="valentine-btn" id="valentine-btn">
                        <i class="fas fa-heart"></i> YES!
                    </button>
                    
                    <div id="valentine-response">
                        <h2 style="color: var(--primary-red); font-size: 3rem;">🎉 YOU SAID YES! 🎉</h2>
                        <p style="font-size: 1.5rem; margin: 30px 0;">Distance might exist, but what we built feels stronger than it.</p>
                        <p style="font-size: 1.5rem;">From Algeria to you, my heart keeps choosing the same person every day. ♾️</p>
                        
                        <div class="signature">
                            Forever yours,<br>
                            <span style="color: var(--primary-red);">Fajr 🤍</span>
                        </div>
                        
                        <p style="margin-top: 40px; font-size: 1.3rem;">If you reached this page… thank you for walking through my heart.</p>
                        <p style="font-size: 1.3rem;">Everything here was made for one reason only:</p>
                        <p style="font-size: 1.5rem; font-weight: bold;">because you are worth every effort, every memory, and every dream.</p>
                    </div>
                </div>
            </div>
            <div class="nav-buttons">
                <button class="nav-btn prev-btn" onclick="prevPage(18)"><i class="fas fa-arrow-left"></i> Back</button>
                <button class="nav-btn" onclick="location.reload()" style="background: linear-gradient(135deg, #27ae60, #229954);">
                    <i class="fas fa-redo"></i> Start Over
                </button>
            </div>
        </div>
    </div>
    
    <!-- Hidden Audio Player -->
    <audio id="audio-player"></audio>
    <div id="youtube-player" style="display: none;"></div>

    <script>
        // ========================================
        // ===== PERSONALIZED CONTENT =====
        // ========================================
        
        const HER_NAME = "Sveta";
        const YOUR_NAME = "Fajr";
        
        // ===== 6 PHOTO URLs - THUMBNAIL METHOD =====
        const PHOTO_URLS = [
            "https://drive.google.com/thumbnail?id=1Nlq1fOZ6c9Nyd6AyHJZuNOdhyGQqXj_e&sz=w1000",
            "https://drive.google.com/thumbnail?id=1jUua3K7hBQUDRyeTE88uySPYIQEygAbN&sz=w1000",
            "https://drive.google.com/thumbnail?id=1qR6y8HSof5e9n4fUnApSkcFMmyaU4l9X&sz=w1000",
            "https://drive.google.com/thumbnail?id=1SJ77Gq13BiQJ0Du9n0S94BJu8U7pbRqc&sz=w1000",
            "https://drive.google.com/thumbnail?id=1puzehH7pBLzsYyW_3GbKTfaRz8yw3akg&sz=w1000",
            "https://drive.google.com/thumbnail?id=1rbz9gwsQ3W4oe7lEARKgNy4ezp6_aJ3U&sz=w1000"
        ];
        
        // ===== 6 VOICE NOTE URLs =====
        const VOICE_URLS = [
            "YOUR_VOICE_1_URL", // Replace with your audio links
            "YOUR_VOICE_2_URL",
            "YOUR_VOICE_3_URL",
            "YOUR_VOICE_4_URL",
            "YOUR_VOICE_5_URL",
            "YOUR_VOICE_6_URL"
        ];
        
        const VOICE_TITLES = [
            "💌 The moment I realized you were special",
            "💕 What I feel when your name appears on my phone",
            "🌙 A soft goodnight just for you",
            "✨ The way you changed my days",
            "🎵 Why my heart chose you",
            "💖 A promise I mean with all my heart"
        ];
        
        // ===== LOVE LETTERS =====
        const loveLetters = [
            "You calm my heart 🤍",
            "Every day with you feels lighter",
            "You made distance feel smaller",
            "Your voice feels like home to me",
            "I'm proud to have you in my life",
            "You made me believe in something real",
            "Even silence feels warm with you",
            "My heart keeps choosing you",
            "You are my safe place",
            "I'm grateful for you every day 💖"
        ];
        
        // ========================================
        // ===== QUIZ QUESTIONS =====
        // ========================================
        const quiz1Questions = [
            { question: "Where did we first really start talking?", options: ["Instagram", "WhatsApp", "Telegram", "A random game"], correct: 2 },
            { question: "What was the first thing I noticed about you?", options: ["Your smile", "Your voice", "Your kindness", "Your humor"], correct: 1 },
            { question: "What time do we usually talk the most?", options: ["Morning", "Afternoon", "Late night", "Random all day"], correct: 2 },
            { question: "What do I love most about our conversations?", options: ["Laughing together", "Deep talks", "Voice notes", "All of the above"], correct: 3 },
            { question: "What is my favorite thing to call you?", options: ["My love", "My favorite person", "Beautiful", "Princess"], correct: 1 }
        ];
        
        const quiz1Results = [
            { min: 0, max: 2, message: "Time for more late-night talks together 😉" },
            { min: 3, max: 4, message: "Pretty good! You're officially a relationship expert 😄" },
            { min: 5, max: 5, message: "You know us perfectly. That means you really pay attention to us 💖" }
        ];
        
        const quiz2Questions = [
            { question: "When I see a message from you, I feel:", options: ["Calm", "Happy", "Excited", "All of them"], correct: 3 },
            { question: "Your best quality in my eyes:", options: ["Kindness", "Cuteness", "Intelligence", "Everything"], correct: 3 },
            { question: "If I could describe you in one word:", options: ["Amazing", "Beautiful", "Special", "Unique"], correct: 2 },
            { question: "What makes me smile the most?", options: ["Your voice", "Your jokes", "Your care", "Just you"], correct: 3 },
            { question: "What do I miss the most when you're away?", options: ["Talking", "Laughing", "Hearing you", "Everything"], correct: 3 }
        ];
        
        const quiz2Results = [
            { min: 0, max: 2, message: "Looks like I need to remind you more often 💌" },
            { min: 3, max: 4, message: "Almost perfect – but I still adore you 😌" },
            { min: 5, max: 5, message: "You understand exactly how much you mean to me 🥺" }
        ];
        
        const quiz3Questions = [
            { question: "One thing I dream of doing with you:", options: ["Traveling", "Watching sunsets", "Long walks", "All of them"], correct: 3 },
            { question: "Our perfect day together would be:", options: ["Staying home", "Exploring a city", "Beach day", "Doesn't matter if it's with you"], correct: 3 },
            { question: "Where would I love to meet you someday?", options: ["Airport hug", "Café date", "Park walk", "Anywhere you are"], correct: 3 },
            { question: "What matters most to me in our future?", options: ["Trust", "Happiness", "Being together", "All"], correct: 3 },
            { question: "Do I believe in us?", options: ["Yes", "Absolutely", "100%", "Forever"], correct: 3 }
        ];
        
        const quiz3Results = [
            { min: 0, max: 2, message: "Let me keep dreaming for both of us then 💖" },
            { min: 3, max: 4, message: "We're on the same road, just different steps 😊" },
            { min: 5, max: 5, message: "Looks like we share the same dreams 💫" }
        ];
        
        const quiz4Questions = [
            { question: "Who talks more?", options: ["Me", "You", "Both", "Depends on the day"], correct: 2 },
            { question: "Who gets sleepy first?", options: ["Me", "You", "Same", "Never sleep"], correct: 1 },
            { question: "Who says 'just 5 more minutes'?", options: ["Me", "You", "Both", "Always you 😄"], correct: 3 },
            { question: "Who sends more voice notes?", options: ["Me", "You", "Equal", "Depends"], correct: 0 },
            { question: "Who misses the other more?", options: ["Me", "You", "Both", "Impossible to measure"], correct: 3 }
        ];
        
        const quiz4Results = [
            { min: 0, max: 2, message: "Looks like we need more funny moments together!" },
            { min: 3, max: 4, message: "Good enough – team us!" },
            { min: 5, max: 5, message: "You officially mastered our chaos 😄" }
        ];
        
        const quiz5Questions = [
            { question: "Do I care about you deeply?", options: ["Yes", "Of course", "More than you know", "All"], correct: 3 },
            { question: "Are you important to me?", options: ["Very", "Extremely", "More than words", "Yes yes yes"], correct: 3 },
            { question: "Do I appreciate you?", options: ["Every day", "Every moment", "Always", "Forever"], correct: 3 },
            { question: "Am I lucky to have you?", options: ["Yes", "Obviously", "Definitely", "The luckiest"], correct: 3 },
            { question: "Do I want you in my life?", options: ["Today", "Tomorrow", "Always", "All of the above"], correct: 3 }
        ];
        
        const quiz5Results = [
            { min: 0, max: 0, message: "No matter the answers, one thing is true: You mean a lot to me, and this quiz was just another way to remind you 💖" },
            { min: 1, max: 5, message: "No matter the answers, one thing is true: You mean a lot to me, and this quiz was just another way to remind you 💖" }
        ];
        
        // ========================================
        // ===== GLOBAL VARIABLES =====
        // ========================================
        const quizState = { 1: { index: 0, score: 0 }, 2: { index: 0, score: 0 }, 3: { index: 0, score: 0 }, 4: { index: 0, score: 0 }, 5: { index: 0, score: 0 } };
        let memoriesUnlocked = 0;
        let memoryGameCards = [];
        let flippedCards = [];
        let matchedPairs = 0;
        let heartsFound = 0;
        let currentPage = 1;
        const totalPages = 19;
        let reasonsCount = 100;
        
        // ========================================
        // ===== PAGE NAVIGATION =====
        // ========================================
        window.nextPage = function(page) {
            if (page > totalPages) return;
            document.getElementById(`page${currentPage}`).classList.remove('active');
            currentPage = page;
            document.getElementById(`page${currentPage}`).classList.add('active');
            window.scrollTo({ top: 0, behavior: 'smooth' });
        };
        
        window.prevPage = function(page) {
            if (page < 1) return;
            document.getElementById(`page${currentPage}`).classList.remove('active');
            currentPage = page;
            document.getElementById(`page${currentPage}`).classList.add('active');
            window.scrollTo({ top: 0, behavior: 'smooth' });
        };
        
        // ========================================
        // ===== BIRTHDAY COUNTDOWN =====
        // ========================================
        function updateBirthdayCountdown() {
            const today = new Date();
            const birthday = new Date(today.getFullYear(), 5, 16); // June 16 (month is 0-based, so 5 = June)
            
            if (today > birthday) {
                birthday.setFullYear(birthday.getFullYear() + 1);
            }
            
            const diffTime = birthday - today;
            const diffDays = Math.ceil(diffTime / (1000 * 60 * 60 * 24));
            
            document.getElementById('birthday-countdown').textContent = diffDays;
        }
        
        // ========================================
        // ===== REASONS COUNTER =====
        // ========================================
        window.addReason = function() {
            reasonsCount++;
            document.getElementById('reasons-counter').textContent = reasonsCount;
            createFloatingHearts(3);
            showMessage(`💕 Reason #${reasonsCount} added!`);
        };
        
        // ========================================
        // ===== FALLING PETALS =====
        // ========================================
        function createPetals() {
            setInterval(() => {
                const petal = document.createElement('div');
                petal.className = 'petal';
                petal.innerHTML = ['🌸', '🌼', '🌺'][Math.floor(Math.random() * 3)];
                petal.style.left = Math.random() * 100 + 'vw';
                petal.style.top = '-20px';
                petal.style.fontSize = (Math.random() * 15 + 15) + 'px';
                petal.style.animationDuration = (Math.random() * 5 + 5) + 's';
                petal.style.opacity = Math.random() * 0.5 + 0.3;
                document.body.appendChild(petal);
                
                setTimeout(() => petal.remove(), 10000);
            }, 2000);
        }
        
        // ========================================
        // ===== GREETING FUNCTIONS =====
        // ========================================
        window.sendGreeting = function(time) {
            if (time === 'morning') {
                showMessage(`☀️ Good morning my Sveta 🤍 I hope today is soft, peaceful, and full of small smiles. Remember someone is thinking about you.`);
            } else {
                showMessage(`🌙 Goodnight my love 🤍 Rest peacefully. Even when you sleep, you stay in my heart.`);
            }
            createFloatingHearts(5);
        };
        
        // ========================================
        // ===== TIMELINE FUNCTIONS =====
        // ========================================
        window.toggleMemory = function(id) {
            const memory = document.getElementById(`memory${id}`);
            const item = memory.closest('.timeline-star');
            item.classList.toggle('active');
        };
        
        // ========================================
        // ===== MEMORY GAME FUNCTIONS =====
        // ========================================
        function initMemoryGame() {
            const symbols = ['🐪', '🐪', '🇹🇷', '🇹🇷', '💖', '💖', '📱', '📱', '🎵', '🎵', '☕', '☕'];
            memoryGameCards = symbols.sort(() => Math.random() - 0.5);
            
            let html = '';
            memoryGameCards.forEach((symbol, i) => {
                html += `<div class="memory-card" onclick="flipCard(this, ${i})">?</div>`;
            });
            
            document.getElementById('memory-game').innerHTML = html;
            matchedPairs = 0;
            document.getElementById('pairs-found').textContent = '0';
        }
        
        window.flipCard = function(card, index) {
            if (card.classList.contains('flipped') || card.classList.contains('matched') || flippedCards.length >= 2) return;
            
            card.classList.add('flipped');
            card.textContent = memoryGameCards[index];
            flippedCards.push({ card, index });
            
            if (flippedCards.length === 2) {
                const [card1, card2] = flippedCards;
                
                if (memoryGameCards[card1.index] === memoryGameCards[card2.index]) {
                    card1.card.classList.add('matched');
                    card2.card.classList.add('matched');
                    matchedPairs++;
                    document.getElementById('pairs-found').textContent = matchedPairs;
                    createFloatingHearts(3);
                } else {
                    setTimeout(() => {
                        card1.card.classList.remove('flipped');
                        card1.card.textContent = '?';
                        card2.card.classList.remove('flipped');
                        card2.card.textContent = '?';
                    }, 1000);
                }
                flippedCards = [];
            }
        };
        
        window.resetMemoryGame = function() {
            initMemoryGame();
            flippedCards = [];
        };
        
        // ========================================
        // ===== QUIZ FUNCTIONS =====
        // ========================================
        function initQuiz(quizNum, questions) {
            quizState[quizNum].index = 0;
            quizState[quizNum].score = 0;
            loadQuizQuestion(quizNum, questions);
        }
        
        function loadQuizQuestion(quizNum, questions) {
            const q = questions[quizState[quizNum].index];
            if (!q) return;
            
            document.getElementById(`quiz${quizNum}-question`).textContent = q.question;
            document.getElementById(`quiz${quizNum}-counter`).textContent = `Question ${quizState[quizNum].index + 1}/5`;
            document.getElementById(`quiz${quizNum}-progress`).style.width = `${((quizState[quizNum].index) / 5) * 100}%`;
            
            let html = '';
            q.options.forEach((opt, i) => {
                html += `<div class="quiz-option" onclick="checkAnswer(${quizNum}, ${i})">${opt}</div>`;
            });
            document.getElementById(`quiz${quizNum}-options`).innerHTML = html;
        }
        
        window.checkAnswer = function(quizNum, selected) {
            const questions = getQuizQuestions(quizNum);
            const q = questions[quizState[quizNum].index];
            const options = document.querySelectorAll(`#quiz${quizNum}-options .quiz-option`);
            
            options.forEach(opt => opt.style.pointerEvents = 'none');
            
            if (selected === q.correct) {
                options[selected].classList.add('correct');
                quizState[quizNum].score++;
                createFloatingHearts(5);
            } else {
                options[selected].classList.add('wrong');
                options[q.correct].classList.add('correct');
            }
            
            setTimeout(() => {
                quizState[quizNum].index++;
                if (quizState[quizNum].index < 5) {
                    loadQuizQuestion(quizNum, questions);
                } else {
                    showQuizResult(quizNum);
                }
            }, 1000);
        };
        
        function getQuizQuestions(quizNum) {
            switch(quizNum) {
                case 1: return quiz1Questions;
                case 2: return quiz2Questions;
                case 3: return quiz3Questions;
                case 4: return quiz4Questions;
                case 5: return quiz5Questions;
                default: return [];
            }
        }
        
        function getQuizResults(quizNum) {
            switch(quizNum) {
                case 1: return quiz1Results;
                case 2: return quiz2Results;
                case 3: return quiz3Results;
                case 4: return quiz4Results;
                case 5: return quiz5Results;
                default: return [];
            }
        }
        
        function showQuizResult(quizNum) {
            const score = quizState[quizNum].score;
            const results = getQuizResults(quizNum);
            
            let message = '';
            for (let r of results) {
                if (score >= r.min && score <= r.max) {
                    message = r.message;
                    break;
                }
            }
            
            document.getElementById(`quiz${quizNum}-options`).innerHTML = '';
            document.getElementById(`quiz${quizNum}-question`).style.display = 'none';
            document.getElementById(`quiz${quizNum}-counter`).style.display = 'none';
            document.getElementById(`quiz${quizNum}-progress`).style.width = '100%';
            
            const resultDiv = document.getElementById(`quiz${quizNum}-result`);
            resultDiv.style.display = 'block';
            resultDiv.innerHTML = `<h3>Quiz Complete! 🎉</h3><p style="font-size: 2rem;">Score: ${score}/5</p><p style="font-size: 1.3rem;">${message}</p>`;
            createFloatingHearts(score * 5);
        }
        
        // ========================================
        // ===== HEART HUNT FUNCTIONS =====
        // ========================================
        window.findHeart = function(id) {
            const heart = document.getElementById(`heart${id}`);
            if (!heart.classList.contains('found')) {
                heart.classList.add('found');
                heart.innerHTML = '💖';
                heartsFound++;
                document.getElementById('hearts-found').textContent = heartsFound;
                if (heartsFound === 9) {
                    document.getElementById('treasure-reward').style.display = 'block';
                }
            }
        };
        
        // ========================================
        // ===== COMPATIBILITY FUNCTIONS =====
        // ========================================
        window.calculateCompatibility = function() {
            const name1 = document.getElementById('name1').value;
            const name2 = document.getElementById('name2').value;
            document.getElementById('compatibility-result').textContent = '100%';
            document.getElementById('compatibility-message').innerHTML = `${name1} + ${name2} = Perfect Match! 💖`;
        };
        
        // ========================================
        // ===== LOVE LETTER GENERATOR =====
        // ========================================
        window.generateLoveLetter = function() {
            const randomIndex = Math.floor(Math.random() * loveLetters.length);
            document.getElementById('love-letter').textContent = loveLetters[randomIndex];
            createFloatingHearts(3);
        };
        
        // ========================================
        // ===== PHOTO GALLERY FUNCTIONS =====
        // ========================================
        function loadPhotoGallery() {
            const gallery = document.getElementById('photo-gallery');
            let html = '';
            
            for (let i = 0; i < 6; i++) {
                const photoUrl = PHOTO_URLS[i];
                html += `<div class="photo-frame"><img src="${photoUrl}" alt="Memory ${i+1}" onerror="this.onerror=null; this.src='https://drive.google.com/uc?export=view&id=${photoUrl.split('=')[1].split('&')[0]}';"></div>`;
            }
            gallery.innerHTML = html;
        }
        
        // ========================================
        // ===== VOICE NOTES FUNCTIONS =====
        // ========================================
        function loadVoiceGallery() {
            const gallery = document.getElementById('voice-gallery');
            let html = '';
            
            for (let i = 0; i < 6; i++) {
                html += `
                    <div class="voice-card" onclick="playVoiceNote(${i})">
                        <div class="voice-icon"><i class="fas fa-microphone-alt"></i></div>
                        <div class="voice-title">${VOICE_TITLES[i]}</div>
                        <div class="voice-description">Click to listen 💕</div>
                        <div class="voice-player" onclick="event.stopPropagation()">
                            <div class="voice-play-btn" onclick="playVoiceNote(${i})"><i class="fas fa-play"></i></div>
                            <div class="voice-progress"><div class="voice-progress-bar" id="voice-progress-${i}"></div></div>
                            <div class="voice-time" id="voice-time-${i}">0:00</div>
                        </div>
                    </div>
                `;
            }
            gallery.innerHTML = html;
        }
        
        window.playVoiceNote = function(index) {
            const url = VOICE_URLS[index];
            if (!url || url.startsWith('YOUR_')) {
                showMessage(`🎙️ Add your voice note URL for: ${VOICE_TITLES[index]}`);
                return;
            }
            
            const player = document.getElementById('audio-player');
            player.src = url;
            player.play();
            
            const progressBar = document.getElementById(`voice-progress-${index}`);
            const timeDisplay = document.getElementById(`voice-time-${index}`);
            
            player.ontimeupdate = function() {
                const progress = (player.currentTime / player.duration) * 100;
                progressBar.style.width = progress + '%';
                const minutes = Math.floor(player.currentTime / 60);
                const seconds = Math.floor(player.currentTime % 60);
                timeDisplay.textContent = `${minutes}:${seconds.toString().padStart(2, '0')}`;
            };
        };
        
        // ========================================
        // ===== SONG FUNCTIONS =====
        // ========================================
        window.playSong505 = function() {
            const videoId = "qU9mHegkTc4"; // 505 by Arctic Monkeys
            if (videoId) {
                document.getElementById('youtube-player').innerHTML = `
                    <iframe id="yt-iframe" width="560" height="315" 
                        src="https://www.youtube.com/embed/${videoId}?autoplay=1&enablejsapi=1" 
                        frameborder="0" allow="autoplay; encrypted-media" allowfullscreen>
                    </iframe>
                `;
                showMessage('🎵 Playing 505 - Arctic Monkeys');
            }
        };
        
        document.getElementById('music-toggle').addEventListener('click', function() {
            const icon = this.querySelector('i');
            
            const videoId = "w6C4zvCwaHo"; // "For Us" - TV Girl - Lovers Rock
            if (videoId) {
                document.getElementById('youtube-player').innerHTML = `
                    <iframe id="yt-iframe" width="560" height="315" 
                        src="https://www.youtube.com/embed/${videoId}?autoplay=1&enablejsapi=1" 
                        frameborder="0" allow="autoplay; encrypted-media" allowfullscreen>
                    </iframe>
                `;
                icon.className = 'fas fa-pause';
                showMessage('🎵 Playing "For Us" - TV Girl');
            }
        });
        
        // ========================================
        // ===== HELPER FUNCTIONS =====
        // ========================================
        function createFloatingHearts(count) {
            const heaven = document.getElementById('heaven');
            for (let i = 0; i < count; i++) {
                setTimeout(() => {
                    const heart = document.createElement('div');
                    heart.className = 'floating-heart';
                    heart.innerHTML = ['💖', '💕', '💗', '💓'][Math.floor(Math.random() * 4)];
                    heart.style.left = Math.random() * 100 + '%';
                    heart.style.fontSize = (Math.random() * 20 + 15) + 'px';
                    heaven.appendChild(heart);
                    setTimeout(() => heart.remove(), 25000);
                }, i * 100);
            }
        }
        
        function showMessage(text) {
            const msg = document.createElement('div');
            msg.innerHTML = text;
            msg.style.cssText = `
                position: fixed; bottom: 30px; left: 50%; transform: translateX(-50%);
                background: white; padding: 18px 35px; border-radius: 60px;
                box-shadow: 0 20px 40px rgba(0,0,0,0.2); z-index: 10000;
                border: 3px solid var(--primary-pink); animation: slideUp 0.3s;
                font-weight: 500;
            `;
            document.body.appendChild(msg);
            setTimeout(() => { msg.style.animation = 'slideDown 0.3s'; setTimeout(() => msg.remove(), 300); }, 3000);
        }
        
        // ========================================
        // ===== PASSWORD =====
        // ========================================
        document.getElementById('password-submit').addEventListener('click', function() {
            const input = document.getElementById('password-input');
            const answer = input.value.trim().toLowerCase();
            
            if (answer === 'purp') {
                document.getElementById('password-screen').style.opacity = '0';
                setTimeout(() => {
                    document.getElementById('password-screen').style.display = 'none';
                    document.getElementById('main-universe').style.display = 'block';
                    showMessage(`✨ Welcome to your world, Sveta! ✨`);
                    
                    document.title = `💖 For ${HER_NAME} | Fajr's World`;
                    
                    // Start falling petals
                    createPetals();
                    
                    // Start birthday countdown
                    updateBirthdayCountdown();
                    setInterval(updateBirthdayCountdown, 1000 * 60 * 60 * 24); // Update daily
                }, 800);
            } else {
                input.style.borderColor = '#ff4757';
                input.style.animation = 'shake 0.5s';
                setTimeout(() => { input.style.animation = ''; }, 500);
                input.value = '';
                input.placeholder = 'Try again...';
            }
        });
        
        // ========================================
        // ===== VALENTINE BUTTON =====
        // ========================================
        document.getElementById('valentine-btn').addEventListener('click', function() {
            document.getElementById('valentine-response').style.display = 'block';
            this.style.display = 'none';
            
            for (let i = 0; i < 100; i++) {
                setTimeout(() => {
                    const heart = document.createElement('div');
                    heart.innerHTML = ['💖', '💕', '💗', '💓', '💘'][Math.floor(Math.random() * 5)];
                    heart.style.cssText = `
                        position: fixed; left: ${Math.random() * 100}vw; top: -50px;
                        font-size: ${Math.random() * 40 + 20}px;
                        animation: floatDown ${Math.random() * 3 + 2}s linear;
                        z-index: 9999; filter: drop-shadow(0 0 10px gold);
                    `;
                    document.body.appendChild(heart);
                    setTimeout(() => heart.remove(), 5000);
                }, i * 20);
            }
        });
        
        // ========================================
        // ===== INITIALIZATION =====
        // ========================================
        document.addEventListener('DOMContentLoaded', function() {
            createFloatingHearts(40);
            
            const stages = ["🌌 Creating Sveta's world...", "💫 Loading memories...", "📸 Photos...", "🎙️ Voice notes...", "💖 Almost ready...", `✨ Welcome, Sveta!`];
            let stage = 0;
            const bar = document.getElementById('loading-bar');
            const text = document.getElementById('loading-text');
            
            const interval = setInterval(() => {
                stage++;
                bar.style.width = (stage / stages.length) * 100 + '%';
                text.textContent = stages[stage - 1];
                
                if (stage >= stages.length) {
                    clearInterval(interval);
                    setTimeout(() => {
                        document.getElementById('loading-screen').style.opacity = '0';
                        setTimeout(() => {
                            document.getElementById('loading-screen').style.display = 'none';
                            document.getElementById('password-screen').style.display = 'flex';
                            
                            initMemoryGame();
                            initQuiz(1, quiz1Questions);
                            initQuiz(2, quiz2Questions);
                            initQuiz(3, quiz3Questions);
                            initQuiz(4, quiz4Questions);
                            initQuiz(5, quiz5Questions);
                            loadPhotoGallery();
                            loadVoiceGallery();
                        }, 1000);
                    }, 500);
                }
            }, 500);
        });
    </script>
</body>
</html>
