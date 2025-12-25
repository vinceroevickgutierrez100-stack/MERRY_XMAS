<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Maligayang Pasko Greeting</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Mountains+of+Christmas:wght@700&family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Poppins', sans-serif;
            background: linear-gradient(180deg, #0c1b33 0%, #1a3666 30%, #0c1b33 100%);
            color: white;
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            overflow: hidden;
            position: relative;
        }

        /* Snow Background */
        .snow-background {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(to bottom, #0c1b33, #1a3666 30%, #2a4a80);
            z-index: 1;
        }

        /* Snow on ground */
        .snow-ground {
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 180px;
            background: linear-gradient(to top, #f0f8ff, #e6f2ff);
            z-index: 2;
            border-top-left-radius: 60% 40px;
            border-top-right-radius: 60% 40px;
            box-shadow: 
                inset 0 15px 30px rgba(255, 255, 255, 0.9),
                0 -5px 20px rgba(255, 255, 255, 0.5);
        }

        /* Christmas Tree 1 */
        .tree-1 {
            position: absolute;
            bottom: 180px;
            right: 10%;
            width: 180px;
            height: 230px;
            z-index: 4;
            animation: sway 8s ease-in-out infinite alternate;
        }

        .tree-1 .tree-layer {
            position: absolute;
            width: 0;
            height: 0;
            border-left: 45px solid transparent;
            border-right: 45px solid transparent;
            border-bottom: 75px solid #0a7e3a;
        }

        .tree-1 .tree-layer-1 {
            bottom: 0;
            left: 45px;
            border-bottom-color: #0a7e3a;
        }

        .tree-1 .tree-layer-2 {
            bottom: 55px;
            left: 35px;
            border-left: 55px solid transparent;
            border-right: 55px solid transparent;
            border-bottom: 85px solid #0b8c42;
        }

        .tree-1 .tree-layer-3 {
            bottom: 110px;
            left: 25px;
            border-left: 65px solid transparent;
            border-right: 65px solid transparent;
            border-bottom: 95px solid #0c9a4a;
        }

        .tree-1 .tree-trunk {
            position: absolute;
            bottom: 0;
            left: 80px;
            width: 18px;
            height: 35px;
            background: #8B4513;
            z-index: 5;
        }

        /* Christmas Tree 2 */
        .tree-2 {
            position: absolute;
            bottom: 180px;
            left: 10%;
            width: 150px;
            height: 200px;
            z-index: 4;
            animation: sway 7s ease-in-out infinite alternate-reverse;
        }

        .tree-2 .tree-layer {
            position: absolute;
            width: 0;
            height: 0;
            border-left: 40px solid transparent;
            border-right: 40px solid transparent;
            border-bottom: 65px solid #0a7e3a;
        }

        .tree-2 .tree-layer-1 {
            bottom: 0;
            left: 35px;
            border-bottom-color: #0c9a4a;
        }

        .tree-2 .tree-layer-2 {
            bottom: 50px;
            left: 25px;
            border-left: 50px solid transparent;
            border-right: 50px solid transparent;
            border-bottom: 75px solid #0b8c42;
        }

        .tree-2 .tree-layer-3 {
            bottom: 95px;
            left: 15px;
            border-left: 60px solid transparent;
            border-right: 60px solid transparent;
            border-bottom: 85px solid #0a7e3a;
        }

        .tree-2 .tree-trunk {
            position: absolute;
            bottom: 0;
            left: 65px;
            width: 15px;
            height: 30px;
            background: #8B4513;
            z-index: 5;
        }

        /* Tree decorations */
        .tree-decoration {
            position: absolute;
            width: 14px;
            height: 14px;
            border-radius: 50%;
            z-index: 6;
            box-shadow: 0 0 10px currentColor;
            animation: twinkle 2s infinite alternate;
        }

        /* Gifts */
        .gift {
            position: absolute;
            z-index: 4;
            border-radius: 10px;
            box-shadow: 
                0 10px 20px rgba(0, 0, 0, 0.4),
                inset 0 0 15px rgba(0, 0, 0, 0.2);
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .gift-1 {
            bottom: 180px;
            left: 5%;
            width: 100px;
            height: 100px;
            background: linear-gradient(45deg, #ff0000, #cc0000);
            animation: bounce 3s ease-in-out infinite;
        }

        .gift-2 {
            bottom: 180px;
            right: 5%;
            width: 110px;
            height: 110px;
            background: linear-gradient(45deg, #00cc00, #009900);
            animation: bounce 3.5s ease-in-out infinite 0.5s;
        }

        .gift-3 {
            bottom: 220px;
            left: 20%;
            width: 90px;
            height: 90px;
            background: linear-gradient(45deg, #ffff00, #ffcc00);
            animation: bounce 4s ease-in-out infinite 1s;
        }

        .gift-4 {
            bottom: 220px;
            right: 20%;
            width: 95px;
            height: 95px;
            background: linear-gradient(45deg, #ff00ff, #cc00cc);
            animation: bounce 3.2s ease-in-out infinite 0.8s;
        }

        .gift-ribbon {
            position: absolute;
            background: white;
        }

        .gift-ribbon-horizontal {
            width: 100%;
            height: 20px;
            top: 50%;
            transform: translateY(-50%);
        }

        .gift-ribbon-vertical {
            width: 20px;
            height: 100%;
            left: 50%;
            transform: translateX(-50%);
        }

        .gift-bow {
            position: absolute;
            width: 35px;
            height: 35px;
            background: white;
            border-radius: 50%;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            z-index: 5;
        }

        /* Snowman */
        .snowman {
            position: absolute;
            bottom: 180px;
            left: 40%;
            width: 120px;
            height: 180px;
            z-index: 4;
            animation: float 4s ease-in-out infinite;
        }

        .snowman-bottom {
            width: 100px;
            height: 100px;
            background: white;
            border-radius: 50%;
            position: absolute;
            bottom: 0;
            left: 10px;
            box-shadow: inset -5px -5px 10px rgba(0, 0, 0, 0.1);
        }

        .snowman-middle {
            width: 80px;
            height: 80px;
            background: white;
            border-radius: 50%;
            position: absolute;
            bottom: 70px;
            left: 20px;
            box-shadow: inset -5px -5px 10px rgba(0, 0, 0, 0.1);
        }

        .snowman-head {
            width: 60px;
            height: 60px;
            background: white;
            border-radius: 50%;
            position: absolute;
            bottom: 130px;
            left: 30px;
            box-shadow: inset -5px -5px 10px rgba(0, 0, 0, 0.1);
        }

        .snowman-hat {
            width: 70px;
            height: 20px;
            background: #333;
            position: absolute;
            bottom: 170px;
            left: 25px;
            border-radius: 5px;
        }

        .snowman-hat-top {
            width: 50px;
            height: 40px;
            background: #333;
            position: absolute;
            bottom: 190px;
            left: 35px;
            border-radius: 10px 10px 0 0;
        }

        .snowman-eye {
            position: absolute;
            width: 8px;
            height: 8px;
            background: #333;
            border-radius: 50%;
        }

        .snowman-eye-left {
            top: 20px;
            left: 15px;
        }

        .snowman-eye-right {
            top: 20px;
            right: 15px;
        }

        .snowman-nose {
            position: absolute;
            width: 0;
            height: 0;
            border-left: 15px solid transparent;
            border-right: 15px solid transparent;
            border-top: 25px solid #ff6600;
            top: 30px;
            left: 15px;
            transform: rotate(180deg);
        }

        .snowman-button {
            position: absolute;
            width: 10px;
            height: 10px;
            background: #333;
            border-radius: 50%;
            left: 50%;
            transform: translateX(-50%);
        }

        .button-1 { top: 25px; }
        .button-2 { top: 40px; }
        .button-3 { top: 55px; }

        /* Christmas lights */
        .christmas-lights {
            position: absolute;
            top: 30px;
            width: 100%;
            height: 30px;
            z-index: 5;
        }

        .light-string {
            display: flex;
            justify-content: center;
            gap: 25px;
        }

        .light {
            width: 22px;
            height: 22px;
            border-radius: 50%;
            animation: lightTwinkle 1.5s infinite alternate;
            position: relative;
        }

        .light::after {
            content: '';
            position: absolute;
            bottom: -8px;
            left: 50%;
            transform: translateX(-50%);
            width: 3px;
            height: 20px;
            background-color: #333;
        }

        .light:nth-child(1) { background-color: #ff0000; animation-delay: 0s; }
        .light:nth-child(2) { background-color: #00ff00; animation-delay: 0.2s; }
        .light:nth-child(3) { background-color: #ffff00; animation-delay: 0.4s; }
        .light:nth-child(4) { background-color: #ff00ff; animation-delay: 0.6s; }
        .light:nth-child(5) { background-color: #00ffff; animation-delay: 0.8s; }
        .light:nth-child(6) { background-color: #ff8800; animation-delay: 1s; }
        .light:nth-child(7) { background-color: #8800ff; animation-delay: 1.2s; }
        .light:nth-child(8) { background-color: #ff0088; animation-delay: 1.4s; }

        /* Name Input */
        .name-input-container {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            z-index: 20;
            background: rgba(0, 0, 0, 0.85);
            padding: 50px;
            border-radius: 25px;
            text-align: center;
            width: 90%;
            max-width: 600px;
            border: 4px solid #ffcc00;
            box-shadow: 
                0 0 40px rgba(255, 204, 0, 0.7),
                inset 0 0 30px rgba(255, 204, 0, 0.2);
            backdrop-filter: blur(10px);
        }

        .name-input-container h1 {
            font-family: 'Mountains of Christmas', cursive;
            font-size: 4rem;
            color: #ffcc00;
            margin-bottom: 20px;
            text-shadow: 0 0 15px rgba(255, 204, 0, 0.8);
        }

        .name-input-container p {
            font-size: 1.5rem;
            margin-bottom: 40px;
            color: #e6f2ff;
            line-height: 1.6;
        }

        .name-input {
            width: 100%;
            padding: 20px;
            font-size: 1.5rem;
            border: 3px solid #4a90e2;
            border-radius: 15px;
            margin-bottom: 30px;
            text-align: center;
            background: rgba(255, 255, 255, 0.95);
            color: #0c1b33;
            font-family: 'Poppins', sans-serif;
            transition: all 0.3s;
        }

        .name-input:focus {
            outline: none;
            border-color: #ffcc00;
            box-shadow: 0 0 20px rgba(255, 204, 0, 0.8);
        }

        .submit-btn {
            background: linear-gradient(to bottom, #ff3333, #cc0000);
            color: white;
            border: none;
            padding: 20px 50px;
            font-size: 1.8rem;
            border-radius: 15px;
            cursor: pointer;
            transition: all 0.3s;
            font-family: 'Mountains of Christmas', cursive;
            letter-spacing: 2px;
            box-shadow: 0 10px 20px rgba(204, 0, 0, 0.5);
            position: relative;
            overflow: hidden;
        }

        .submit-btn:hover {
            transform: translateY(-7px);
            box-shadow: 0 15px 25px rgba(204, 0, 0, 0.7);
            background: linear-gradient(to bottom, #ff5555, #dd0000);
        }

        .submit-btn:active {
            transform: translateY(-3px);
        }

        /* Card Container */
        .card-container {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            z-index: 15;
            width: 90%;
            max-width: 700px;
            opacity: 0;
            transition: opacity 1s ease;
            pointer-events: none;
        }

        .card-container.active {
            opacity: 1;
            pointer-events: all;
        }

        /* Card */
        .card {
            background: rgba(255, 255, 255, 0.97);
            border-radius: 25px;
            padding: 50px;
            box-shadow: 
                0 25px 50px rgba(0, 0, 0, 0.5),
                inset 0 0 40px rgba(139, 0, 0, 0.15);
            border: 8px solid #b22222;
            position: relative;
            overflow: hidden;
            min-height: 450px;
            display: flex;
            flex-direction: column;
            justify-content: center;
        }

        .card::before {
            content: '';
            position: absolute;
            top: -15px;
            left: -15px;
            right: -15px;
            bottom: -15px;
            background: linear-gradient(45deg, #ff0000, #ff9900, #ffff00, #00ff00, #00ffff, #0000ff, #9900ff);
            background-size: 400% 400%;
            z-index: -1;
            border-radius: 35px;
            animation: borderGlow 8s ease infinite;
            filter: blur(15px);
            opacity: 0.6;
        }

        /* Greeting Text */
        .greeting {
            text-align: center;
            position: relative;
            z-index: 2;
        }

        .greeting-line {
            margin-bottom: 25px;
            min-height: 70px;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .greeting-text {
            font-family: 'Mountains of Christmas', cursive;
            font-size: 4rem;
            display: inline-block;
        }

        .letter {
            display: inline-block;
            opacity: 0;
            transform: translateY(40px);
            color: #b22222;
        }

        .exclamation {
            color: #ff0000;
            font-weight: bold;
            animation: pulse 1s infinite;
        }

        .personal-name {
            color: #0c9a4a;
            font-weight: bold;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.2);
        }

        .space {
            display: inline-block;
            width: 25px;
        }

        .tagalog-text .letter {
            color: #1a3666;
        }

        .from-bins {
            font-family: 'Mountains of Christmas', cursive;
            font-size: 3.5rem;
            color: #2c3e50;
            margin-top: 60px;
            opacity: 0;
            transform: translateY(30px);
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.2);
        }

        /* Snowflakes on text */
        .text-snowflake {
            position: absolute;
            width: 10px;
            height: 10px;
            background: white;
            border-radius: 50%;
            pointer-events: none;
            opacity: 0;
            z-index: 5;
            box-shadow: 0 0 10px white;
        }

        /* Cursor */
        .cursor {
            display: inline-block;
            width: 5px;
            height: 60px;
            background-color: #ffcc00;
            margin-left: 10px;
            animation: blink 1s infinite;
            vertical-align: middle;
            box-shadow: 0 0 10px #ffcc00;
        }

        /* Close Button */
        .close-card {
            position: absolute;
            top: 25px;
            right: 25px;
            background: #b22222;
            color: white;
            border: none;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            font-size: 1.8rem;
            cursor: pointer;
            z-index: 16;
            display: flex;
            justify-content: center;
            align-items: center;
            transition: all 0.3s;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
        }

        .close-card:hover {
            transform: rotate(90deg) scale(1.1);
            background: #ff0000;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.4);
        }

        /* Falling Snow */
        .falling-snow {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 3;
        }

        .snowflake-fall {
            position: absolute;
            background-color: white;
            border-radius: 50%;
            opacity: 0.9;
            top: -10px;
            box-shadow: 0 0 10px white;
        }

        /* Parols (Filipino Christmas Lanterns) */
        .parol {
            position: absolute;
            z-index: 4;
            width: 60px;
            height: 90px;
            animation: floatParol 6s ease-in-out infinite;
        }

        .parol-1 {
            top: 15%;
            left: 8%;
            animation-delay: 0s;
        }

        .parol-2 {
            top: 20%;
            right: 8%;
            animation-delay: 1s;
        }

        .parol-body {
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, #ff0000, #ff9900, #ffff00);
            border-radius: 10px;
            position: relative;
            box-shadow: 
                0 0 20px #ff9900,
                inset 0 0 20px rgba(255, 255, 255, 0.5);
        }

        .parol-spikes {
            position: absolute;
            width: 10px;
            height: 20px;
            background: #ffcc00;
            top: -10px;
            left: 50%;
            transform: translateX(-50%);
        }

        .parol-tassel {
            position: absolute;
            width: 5px;
            height: 30px;
            background: #ffcc00;
            bottom: -30px;
            left: 50%;
            transform: translateX(-50%);
        }

        /* Animations */
        @keyframes sway {
            0% { transform: translateX(0) rotate(0.5deg); }
            100% { transform: translateX(10px) rotate(-0.5deg); }
        }

        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-20px); }
        }

        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-15px); }
        }

        @keyframes floatParol {
            0%, 100% { transform: translateY(0) rotate(0deg); }
            50% { transform: translateY(-25px) rotate(5deg); }
        }

        @keyframes twinkle {
            0% { opacity: 0.5; transform: scale(0.9); }
            100% { opacity: 1; transform: scale(1.1); }
        }

        @keyframes lightTwinkle {
            0% { opacity: 0.3; box-shadow: 0 0 5px currentColor; }
            100% { opacity: 1; box-shadow: 0 0 20px currentColor; }
        }

        @keyframes borderGlow {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        @keyframes blink {
            0%, 50% { opacity: 1; }
            51%, 100% { opacity: 0; }
        }

        @keyframes fall {
            0% { transform: translateY(-10px) rotate(0deg); }
            100% { transform: translateY(100vh) rotate(360deg); }
        }

        @keyframes letterAppear {
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes snowOnText {
            0% { transform: translateY(-15px) scale(0); opacity: 0; }
            50% { opacity: 1; }
            100% { transform: translateY(15px) scale(1); opacity: 0; }
        }

        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.3); }
            100% { transform: scale(1); }
        }

        /* Responsive */
        @media (max-width: 768px) {
            .name-input-container {
                padding: 30px;
            }
            
            .name-input-container h1 {
                font-size: 3rem;
            }
            
            .greeting-text {
                font-size: 2.8rem;
            }
            
            .from-bins {
                font-size: 2.5rem;
            }
            
            .tree-1, .tree-2 {
                width: 120px;
                height: 160px;
            }
            
            .gift {
                width: 70px;
                height: 70px;
            }
            
            .snowman {
                left: 35%;
                width: 90px;
                height: 140px;
            }
        }

        @media (max-width: 480px) {
            .name-input-container h1 {
                font-size: 2.5rem;
            }
            
            .greeting-text {
                font-size: 2.2rem;
            }
            
            .from-bins {
                font-size: 2rem;
            }
            
            .tree-1, .tree-2 {
                width: 90px;
                height: 130px;
            }
            
            .gift {
                width: 60px;
                height: 60px;
            }
            
            .parol {
                width: 40px;
                height: 60px;
            }
        }
    </style>
</head>
<body>
    <!-- Snow Background -->
    <div class="snow-background"></div>
    <div class="snow-ground"></div>
    
    <!-- Christmas Lights -->
    <div class="christmas-lights">
        <div class="light-string">
            <div class="light"></div>
            <div class="light"></div>
            <div class="light"></div>
            <div class="light"></div>
            <div class="light"></div>
            <div class="light"></div>
            <div class="light"></div>
            <div class="light"></div>
        </div>
    </div>
    
    <!-- Falling Snow -->
    <div class="falling-snow" id="fallingSnow"></div>
    
    <!-- Christmas Trees -->
    <div class="tree-1">
        <div class="tree-layer tree-layer-1"></div>
        <div class="tree-layer tree-layer-2"></div>
        <div class="tree-layer tree-layer-3"></div>
        <div class="tree-trunk"></div>
        
        <!-- Tree decorations -->
        <div class="tree-decoration" style="top: 40px; left: 85px; background: #ff0000;"></div>
        <div class="tree-decoration" style="top: 80px; left: 55px; background: #ffcc00;"></div>
        <div class="tree-decoration" style="top: 80px; left: 115px; background: #00ff00;"></div>
        <div class="tree-decoration" style="top: 120px; left: 35px; background: #ff00ff;"></div>
        <div class="tree-decoration" style="top: 120px; left: 135px; background: #00ffff;"></div>
    </div>
    
    <div class="tree-2">
        <div class="tree-layer tree-layer-1"></div>
        <div class="tree-layer tree-layer-2"></div>
        <div class="tree-layer tree-layer-3"></div>
        <div class="tree-trunk"></div>
        
        <!-- Tree decorations -->
        <div class="tree-decoration" style="top: 30px; left: 65px; background: #ff6600;"></div>
        <div class="tree-decoration" style="top: 70px; left: 40px; background: #cc00ff;"></div>
        <div class="tree-decoration" style="top: 70px; left: 90px; background: #00ccff;"></div>
        <div class="tree-decoration" style="top: 110px; left: 25px; background: #ffff00;"></div>
        <div class="tree-decoration" style="top: 110px; left: 105px; background: #ff0000;"></div>
    </div>
    
    <!-- Gifts -->
    <div class="gift gift-1">
        <div class="gift-ribbon gift-ribbon-horizontal"></div>
        <div class="gift-ribbon gift-ribbon-vertical"></div>
        <div class="gift-bow"></div>
    </div>
    
    <div class="gift gift-2">
        <div class="gift-ribbon gift-ribbon-horizontal"></div>
        <div class="gift-ribbon gift-ribbon-vertical"></div>
        <div class="gift-bow"></div>
    </div>
    
    <div class="gift gift-3">
        <div class="gift-ribbon gift-ribbon-horizontal"></div>
        <div class="gift-ribbon gift-ribbon-vertical"></div>
        <div class="gift-bow"></div>
    </div>
    
    <div class="gift gift-4">
        <div class="gift-ribbon gift-ribbon-horizontal"></div>
        <div class="gift-ribbon gift-ribbon-vertical"></div>
        <div class="gift-bow"></div>
    </div>
    
    <!-- Snowman -->
    <div class="snowman">
        <div class="snowman-bottom"></div>
        <div class="snowman-middle"></div>
        <div class="snowman-head"></div>
        <div class="snowman-hat"></div>
        <div class="snowman-hat-top"></div>
        <div class="snowman-eye snowman-eye-left"></div>
        <div class="snowman-eye snowman-eye-right"></div>
        <div class="snowman-nose"></div>
        <div class="snowman-button button-1"></div>
        <div class="snowman-button button-2"></div>
        <div class="snowman-button button-3"></div>
    </div>
    
    <!-- Parols (Filipino Christmas Lanterns) -->
    <div class="parol parol-1">
        <div class="parol-body"></div>
        <div class="parol-spikes"></div>
        <div class="parol-tassel"></div>
    </div>
    
    <div class="parol parol-2">
        <div class="parol-body"></div>
        <div class="parol-spikes"></div>
        <div class="parol-tassel"></div>
    </div>
    
    <!-- Name Input -->
    <div class="name-input-container" id="nameInputContainer">
        <h1>Maligayang Pasko!</h1>
        <p>Enter your name to receive a special Filipino Christmas greeting with noche buena wishes!</p>
        <input type="text" class="name-input" id="userName" placeholder="Enter your name here" maxlength="25" autocomplete="off">
        <button class="submit-btn" id="submitName">
            <i class="fas fa-star"></i> Buksan ang Greeting
        </button>
    </div>
    
    <!-- Card Container -->
    <div class="card-container" id="cardContainer">
        <div class="card">
            <button class="close-card" id="closeCard">
                <i class="fas fa-times"></i>
            </button>
            
            <div class="greeting" id="greeting">
                <div class="greeting-line">
                    <div class="greeting-text" id="greetingText1"></div>
                </div>
                <div class="greeting-line">
                    <div class="greeting-text" id="greetingText2"></div>
                </div>
                <div class="greeting-line">
                    <div class="greeting-text tagalog-text" id="greetingText3"></div>
                </div>
                <div class="greeting-line">
                    <div class="greeting-text tagalog-text" id="greetingText4"></div>
                </div>
                
                <div class="from-bins" id="fromBins">From Bins</div>
                <div class="cursor" id="cursor"></div>
            </div>
        </div>
    </div>

    <script>
        // DOM Elements
        const nameInputContainer = document.getElementById('nameInputContainer');
        const cardContainer = document.getElementById('cardContainer');
        const userNameInput = document.getElementById('userName');
        const submitNameBtn = document.getElementById('submitName');
        const closeCardBtn = document.getElementById('closeCard');
        const greetingText1 = document.getElementById('greetingText1');
        const greetingText2 = document.getElementById('greetingText2');
        const greetingText3 = document.getElementById('greetingText3');
        const greetingText4 = document.getElementById('greetingText4');
        const fromBins = document.getElementById('fromBins');
        const cursor = document.getElementById('cursor');
        const fallingSnow = document.getElementById('fallingSnow');
        
        // Animation Variables
        let userName = '';
        let typingSpeed = 100;
        let animationTimeout;
        let currentLetterIndex = 0;
        let lines = [];
        
        // Create falling snow
        function createFallingSnow() {
            const snowflakeCount = 150;
            
            for (let i = 0; i < snowflakeCount; i++) {
                const snowflake = document.createElement('div');
                snowflake.classList.add('snowflake-fall');
                
                // Random size
                const size = Math.random() * 8 + 4;
                snowflake.style.width = `${size}px`;
                snowflake.style.height = `${size}px`;
                
                // Random position
                snowflake.style.left = `${Math.random() * 100}vw`;
                
                // Random opacity
                snowflake.style.opacity = Math.random() * 0.8 + 0.2;
                
                // Random animation
                const duration = Math.random() * 12 + 6;
                const delay = Math.random() * 5;
                snowflake.style.animation = `fall ${duration}s linear ${delay}s infinite`;
                
                // Add to falling snow container
                fallingSnow.appendChild(snowflake);
            }
        }
        
        // Create snow effect on text
        function createTextSnowflake(x, y) {
            const snowflake = document.createElement('div');
            snowflake.classList.add('text-snowflake');
            
            // Position
            snowflake.style.left = `${x}px`;
            snowflake.style.top = `${y}px`;
            
            // Random size
            const size = Math.random() * 8 + 4;
            snowflake.style.width = `${size}px`;
            snowflake.style.height = `${size}px`;
            
            // Random color (sometimes colored like Christmas)
            if (Math.random() > 0.7) {
                const colors = ['#ff0000', '#00ff00', '#ffff00', '#ff9900'];
                snowflake.style.background = colors[Math.floor(Math.random() * colors.length)];
            }
            
            // Add to card
            document.querySelector('.card').appendChild(snowflake);
            
            // Animate
            snowflake.style.animation = `snowOnText 1.5s forwards`;
            
            // Remove after animation
            setTimeout(() => {
                snowflake.remove();
            }, 1500);
        }
        
        // Initialize greeting lines with the exact message
        function initGreetingLines() {
            lines = [
                "Merry Christmas!!!",
                userName + ",",
                "Sana masarap noche",
                "buena nyoooo!!!"
            ];
            
            // Clear previous content
            greetingText1.innerHTML = '';
            greetingText2.innerHTML = '';
            greetingText3.innerHTML = '';
            greetingText4.innerHTML = '';
            fromBins.style.opacity = '0';
            fromBins.style.transform = 'translateY(30px)';
            
            currentLetterIndex = 0;
            
            // Create letter elements for each line
            createLetterElements(greetingText1, lines[0], false, true); // First line has exclamation marks
            createLetterElements(greetingText2, lines[1], true, false); // This line has the name
            createLetterElements(greetingText3, lines[2], false, false);
            createLetterElements(greetingText4, lines[3], false, true); // Last line has exclamation marks
            
            cursor.style.display = 'inline-block';
        }
        
        // Create letter elements for a line
        function createLetterElements(container, text, isNameLine = false, hasExclamation = false) {
            for (let i = 0; i < text.length; i++) {
                const char = text.charAt(i);
                
                if (char === ' ') {
                    const space = document.createElement('span');
                    space.className = 'space';
                    container.appendChild(space);
                } else {
                    const letter = document.createElement('span');
                    letter.className = 'letter';
                    letter.textContent = char;
                    
                    // Add personal name styling
                    if (isNameLine) {
                        letter.classList.add('personal-name');
                    }
                    
                    // Add exclamation styling
                    if (hasExclamation && (char === '!')) {
                        letter.classList.add('exclamation');
                    }
                    
                    container.appendChild(letter);
                }
            }
        }
        
        // Start typing animation
        function startTypingAnimation() {
            const letters = document.querySelectorAll('.letter');
            let currentIndex = 0;
            
            function typeNextLetter() {
                if (currentIndex < letters.length) {
                    // Get position for snowflake effect
                    const rect = letters[currentIndex].getBoundingClientRect();
                    const cardRect = document.querySelector('.card').getBoundingClientRect();
                    
                    // Calculate position relative to card
                    const x = rect.left - cardRect.left + rect.width / 2;
                    const y = rect.top - cardRect.top + rect.height / 2;
                    
                    // Create snowflake effect (more often for a festive look)
                    if (Math.random() > 0.5) {
                        createTextSnowflake(x, y);
                    }
                    
                    // Special effect for exclamation marks
                    if (letters[currentIndex].classList.contains('exclamation')) {
                        letters[currentIndex].style.animation = `letterAppear 0.6s forwards, pulse 1s 0.6s infinite`;
                    } else {
                        letters[currentIndex].style.animation = `letterAppear 0.6s forwards`;
                    }
                    
                    // Add a little bounce for some letters
                    if (Math.random() > 0.7 && !letters[currentIndex].classList.contains('exclamation')) {
                        letters[currentIndex].style.animation = `letterAppear 0.6s forwards, bounce 0.5s 0.6s`;
                    }
                    
                    currentIndex++;
                    animationTimeout = setTimeout(typeNextLetter, typingSpeed);
                } else {
                    // All letters typed, show "From Bins"
                    setTimeout(() => {
                        fromBins.style.animation = 'letterAppear 1.2s forwards';
                        cursor.style.display = 'none';
                        
                        // Add some final snowflakes
                        for (let i = 0; i < 15; i++) {
                            setTimeout(() => {
                                const x = Math.random() * 500 + 100;
                                const y = Math.random() * 300 + 50;
                                createTextSnowflake(x, y);
                            }, i * 100);
                        }
                    }, 800);
                }
            }
            
            typeNextLetter();
        }
        
        // Handle name submission
        function handleNameSubmit() {
            userName = userNameInput.value.trim();
            
            if (!userName) {
                userName = "Kaibigan";
            }
            
            // Add festive effect to button
            submitNameBtn.innerHTML = '<i class="fas fa-spinner fa-spin"></i> Naghahanda ng Greeting...';
            
            setTimeout(() => {
                // Hide name input
                nameInputContainer.style.opacity = '0';
                
                setTimeout(() => {
                    nameInputContainer.style.display = 'none';
                    
                    // Show card container
                    cardContainer.classList.add('active');
                    
                    // Initialize and start animation
                    initGreetingLines();
                    setTimeout(startTypingAnimation, 800);
                    
                    // Reset button text
                    submitNameBtn.innerHTML = '<i class="fas fa-star"></i> Buksan ang Greeting';
                }, 500);
            }, 800);
        }
        
        // Close card and restart
        function closeCard() {
            cardContainer.classList.remove('active');
            
            setTimeout(() => {
                nameInputContainer.style.display = 'block';
                setTimeout(() => {
                    nameInputContainer.style.opacity = '1';
                    userNameInput.value = '';
                    userNameInput.focus();
                }, 50);
            }, 500);
        }
        
        // Add twinkling effect to tree decorations
        function addTwinkleEffects() {
            const decorations = document.querySelectorAll('.tree-decoration');
            decorations.forEach((decoration, index) => {
                setInterval(() => {
                    const scale = Math.random() * 0.3 + 0.9;
                    decoration.style.transform = `scale(${scale})`;
                }, 1000 + index * 200);
            });
        }
        
        // Event Listeners
        submitNameBtn.addEventListener('click', handleNameSubmit);
        
        userNameInput.addEventListener('keypress', (e) => {
            if (e.key === 'Enter') {
                handleNameSubmit();
            }
        });
        
        closeCardBtn.addEventListener('click', closeCard);
        
        // Initialize on page load
        document.addEventListener('DOMContentLoaded', () => {
            // Focus on name input
            userNameInput.focus();
            
            // Create falling snow
            createFallingSnow();
            
            // Add twinkle effects
            addTwinkleEffects();
            
            // Add interactivity to gifts
            document.querySelectorAll('.gift').forEach(gift => {
                gift.addEventListener('click', function() {
                    this.style.transform = 'scale(1.2) rotate(10deg)';
                    setTimeout(() => {
                        this.style.transform = '';
                    }, 300);
                });
            });
            
            // Add keyboard shortcuts
            document.addEventListener('keydown', (e) => {
                if (e.key === 'Escape' && cardContainer.classList.contains('active')) {
                    closeCard();
                }
            });
            
            // Add some random snowflakes in the background occasionally
            setInterval(() => {
                if (Math.random() > 0.7) {
                    const x = Math.random() * window.innerWidth;
                    const snowflake = document.createElement('div');
                    snowflake.classList.add('snowflake-fall');
                    snowflake.style.width = '12px';
                    snowflake.style.height = '12px';
                    snowflake.style.left = `${x}px`;
                    snowflake.style.opacity = '0.9';
                    snowflake.style.animation = `fall 8s linear forwards`;
                    fallingSnow.appendChild(snowflake);
                    
                    // Remove after animation
                    setTimeout(() => {
                        if (snowflake.parentNode) {
                            snowflake.remove();
                        }
                    }, 8000);
                }
            }, 500);
            
            // Add extra exclamation mark animation
            setInterval(() => {
                const exclamations = document.querySelectorAll('.exclamation');
                exclamations.forEach(exclamation => {
                    if (Math.random() > 0.7) {
                        exclamation.style.transform = 'scale(1.5)';
                        setTimeout(() => {
                            exclamation.style.transform = 'scale(1)';
                        }, 300);
                    }
                });
            }, 2000);
        });
    </script>
</body>
</html>
