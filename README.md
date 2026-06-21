<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>🔪 BLuMP • Пятница </title>
  <!-- Font Awesome Icons -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">
  <style>
    /* ГЛОБАЛЬНЫЙ СТИЛЬ — ПЯТНИЦА 13-Я */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      cursor: none;
    }

    body {
      background: #0a0505;
      background-image: radial-gradient(circle at 20% 30%, #1f0f0f 0%, #0a0303 100%);
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      font-family: 'Courier New', Courier, 'Lucida Sans Typewriter', monospace;
      padding: 20px;
      position: relative;
      box-shadow: inset 0 0 150px rgba(80, 0, 0, 0.6);
    }

    body::before, body::after {
      content: '';
      position: fixed;
      pointer-events: none;
      z-index: -1;
      border-radius: 50%;
      background: radial-gradient(circle, rgba(150, 0, 0, 0.15) 0%, transparent 70%);
      animation: bloodDrip 8s ease-in-out infinite;
    }

    body::before {
      width: 400px;
      height: 400px;
      top: -100px;
      right: -100px;
      animation-delay: 0s;
    }

    body::after {
      width: 300px;
      height: 300px;
      bottom: -80px;
      left: -80px;
      animation-delay: 4s;
    }

    @keyframes bloodDrip {
      0%, 100% { transform: translate(0, 0) scale(1); opacity: 0.3; }
      50% { transform: translate(30px, 20px) scale(1.3); opacity: 0.6; }
    }

    .blood-particle {
      position: fixed;
      pointer-events: none;
      z-index: -1;
      color: rgba(150, 0, 0, 0.15);
      font-size: 2rem;
      animation: floatBlood 15s ease-in-out infinite;
    }

    @keyframes floatBlood {
      0%, 100% { transform: translate(0, 0) rotate(0deg); opacity: 0.2; }
      25% { transform: translate(50px, -100px) rotate(45deg); opacity: 0.5; }
      50% { transform: translate(-30px, -200px) rotate(90deg); opacity: 0.3; }
      75% { transform: translate(80px, -50px) rotate(135deg); opacity: 0.6; }
    }

    .custom-cursor {
      position: fixed;
      pointer-events: none;
      z-index: 9999;
      font-size: 26px;
      color: #ff0000;
      text-shadow: 0 0 20px #ff0000, 0 0 40px #cc0000, 0 0 60px #880000;
      transform: translate(-50%, -50%);
      line-height: 1;
      opacity: 1;
      font-family: 'Courier New', monospace;
      font-weight: bold;
      transition: none;
    }

    .custom-cursor i {
      display: block;
      animation: cursorPulse 1.2s ease-in-out infinite;
    }

    @keyframes cursorPulse {
      0%, 100% { transform: scale(1); }
      50% { transform: scale(1.15); }
    }

    .vink-container {
      max-width: 1000px;
      width: 100%;
      background: #120808;
      background: linear-gradient(145deg, #1e0e0e 0%, #0f0505 100%);
      border: 2px solid #5f2b2b;
      border-radius: 40px 12px 40px 12px;
      padding: 30px 30px 45px;
      box-shadow: 0 20px 60px rgba(0, 0, 0, 0.9), 0 0 0 2px #4d1a1a inset, 0 0 0 5px #2a0d0d inset;
      position: relative;
      transition: all 0.2s;
      backdrop-filter: blur(2px);
      animation: containerGlow 4s ease-in-out infinite;
    }

    @keyframes containerGlow {
      0%, 100% { box-shadow: 0 20px 60px rgba(0, 0, 0, 0.9), 0 0 0 2px #4d1a1a inset, 0 0 0 5px #2a0d0d inset; }
      50% { box-shadow: 0 20px 80px rgba(150, 0, 0, 0.4), 0 0 0 3px #7a2e2e inset, 0 0 0 6px #3f0f0f inset; }
    }

    .vink-container::before {
      content: '';
      position: absolute;
      top: -6px;
      left: -6px;
      right: -6px;
      bottom: -6px;
      border-radius: 44px 16px 44px 16px;
      background: repeating-linear-gradient(45deg, #6e1f1f, #3f0f0f 8px, #1f0505 8px, #2a0a0a 16px);
      z-index: -1;
      filter: blur(3px);
      opacity: 0.5;
    }

    .blood-corner {
      position: absolute;
      font-size: 2.5rem;
      color: rgba(150, 0, 0, 0.15);
      pointer-events: none;
      animation: cornerPulse 3s ease-in-out infinite;
    }

    .blood-corner.tl { top: 10px; left: 15px; }
    .blood-corner.tr { top: 10px; right: 15px; transform: scaleX(-1); }
    .blood-corner.bl { bottom: 10px; left: 15px; transform: scaleY(-1); }
    .blood-corner.br { bottom: 10px; right: 15px; transform: scale(-1, -1); }

    @keyframes cornerPulse {
      0%, 100% { opacity: 0.15; }
      50% { opacity: 0.4; }
    }

    .header {
      display: flex;
      justify-content: space-between;
      align-items: baseline;
      border-bottom: 3px double #7a2e2e;
      padding-bottom: 18px;
      margin-bottom: 30px;
      flex-wrap: wrap;
    }

    .header h1 {
      font-size: 3.6rem;
      font-weight: 700;
      letter-spacing: 8px;
      color: #c9a9a9;
      text-shadow: 0 0 20px #aa2b2b, 0 0 40px #661515, 0 0 80px #3d0a0a;
      font-family: 'Impact', 'Arial Black', sans-serif;
      text-transform: uppercase;
      word-break: break-word;
      background: linear-gradient(180deg, #e7d7d7, #a55);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      filter: drop-shadow(2px 4px 6px #250000);
      animation: titleGlow 3s ease-in-out infinite;
    }

    @keyframes titleGlow {
      0%, 100% { filter: drop-shadow(2px 4px 6px #250000); }
      50% { filter: drop-shadow(2px 4px 20px #aa2b2b); }
    }

    .header .slash-icon {
      color: #7a2e2e;
      font-size: 2.8rem;
      text-shadow: 0 0 20px #ff4444;
      margin-left: 10px;
    }

    .video-section {
      background: #0c0303;
      border-radius: 30px 8px 30px 8px;
      padding: 14px;
      border: 1px solid #643030;
      box-shadow: 0 0 30px rgba(150, 0, 0, 0.5), inset 0 0 20px #1a0808;
      margin-bottom: 28px;
    }

    .video-wrapper {
      position: relative;
      width: 100%;
      padding-top: 56.25%;
      background: #000;
      border-radius: 20px 4px 20px 4px;
      overflow: hidden;
      box-shadow: inset 0 0 40px #2f0a0a;
    }

    .video-wrapper video {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      object-fit: cover;
      display: block;
      background: #0d0404;
      border: none;
      outline: none;
    }

    /* АВАТАРКА ВИДЕО */
    .video-thumbnail {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      object-fit: cover;
      z-index: 1;
      display: none;
      background: #0a0303;
    }

    .video-thumbnail.active {
      display: block;
    }

    .video-thumbnail img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }

    .video-controls {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-top: 12px;
      color: #b99;
      font-size: 0.9rem;
      padding: 0 8px;
      flex-wrap: wrap;
      gap: 10px;
    }

    .file-upload-label {
      background: #281111;
      padding: 10px 22px;
      border-radius: 40px 4px 40px 4px;
      border: 1px solid #8f3a3a;
      color: #ddbbbb;
      font-weight: bold;
      letter-spacing: 2px;
      text-transform: uppercase;
      font-size: 1rem;
      transition: 0.2s;
      box-shadow: 0 0 16px #3d0e0e;
      cursor: none;
      display: inline-flex;
      align-items: center;
      gap: 12px;
    }

    .file-upload-label i { font-size: 1.4rem; color: #c55; }
    .file-upload-label:hover {
      background: #3f1a1a;
      border-color: #cc6a6a;
      box-shadow: 0 0 30px #8f2a2a;
      transform: scale(1.02);
    }

    .file-upload-label.hidden {
      display: none;
    }

    #videoInput { display: none; }

    .video-status {
      background: #1d0b0b;
      padding: 6px 18px;
      border-radius: 30px;
      border-left: 4px solid #a33;
      font-size: 0.95rem;
      color: #be8a8a;
      display: flex;
      align-items: center;
      gap: 6px;
    }

    .quality-control {
      display: flex;
      align-items: center;
      gap: 10px;
      background: #1d0b0b;
      padding: 4px 14px 4px 18px;
      border-radius: 30px;
      border-left: 4px solid #a33;
    }

    .quality-control label { color: #be8a8a; font-size: 0.85rem; letter-spacing: 1px; }
    .quality-control select {
      background: #281111;
      border: 1px solid #643030;
      border-radius: 20px 2px 20px 2px;
      color: #ddbbbb;
      padding: 6px 12px;
      font-family: 'Courier New', monospace;
      font-size: 0.85rem;
      outline: none;
      cursor: none;
      transition: 0.2s;
    }
    .quality-control select:hover {
      border-color: #cc6a6a;
      box-shadow: 0 0 20px #8f2a2a;
    }
    .quality-control select option { background: #1a0808; color: #ddbbbb; }

    .series-section {
      background: #100808;
      padding: 18px 20px;
      border-radius: 30px 4px 30px 4px;
      border: 1px solid #552a2a;
      margin-top: 16px;
      box-shadow: inset 0 0 20px #1b0808;
    }

    .series-section .series-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      flex-wrap: wrap;
      gap: 10px;
      margin-bottom: 12px;
    }

    .series-section .series-header h3 {
      color: #cc5555;
      font-size: 1.2rem;
      letter-spacing: 2px;
      font-family: 'Impact', 'Arial Black', sans-serif;
    }

    .series-section .series-header .series-count {
      color: #884444;
      font-size: 0.9rem;
    }

    .series-list {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
    }

    .series-item {
      background: #1a0a0a;
      border: 1px solid #643030;
      border-radius: 20px 2px 20px 2px;
      padding: 10px 18px;
      display: flex;
      align-items: center;
      gap: 12px;
      transition: 0.2s;
      cursor: none;
      flex: 1 1 auto;
      min-width: 180px;
    }

    .series-item:hover {
      border-color: #cc6a6a;
      box-shadow: 0 0 20px #8f2a2a;
    }

    .series-item .series-thumb {
      width: 40px;
      height: 40px;
      border-radius: 10px 2px 10px 2px;
      object-fit: cover;
      border: 1px solid #5f2b2b;
      background: #0a0303;
    }

    .series-item .series-info {
      display: flex;
      flex-direction: column;
      flex: 1;
    }

    .series-item .series-num {
      color: #cc3333;
      font-weight: bold;
      font-size: 0.8rem;
    }

    .series-item .series-name {
      color: #ddbbbb;
      font-size: 0.9rem;
    }

    .series-item .series-actions {
      display: flex;
      gap: 8px;
      align-items: center;
    }

    .series-item .series-play {
      color: #6b3;
      cursor: none;
      transition: 0.2s;
      font-size: 1.2rem;
    }

    .series-item .series-play:hover {
      color: #8d5;
      transform: scale(1.2);
    }

    .series-item .series-delete {
      color: #884444;
      cursor: none;
      transition: 0.2s;
      font-size: 1.1rem;
    }

    .series-item .series-delete:hover {
      color: #cc3333;
      transform: scale(1.2);
    }

    .series-item.current {
      border-color: #ccaa33;
      box-shadow: 0 0 30px rgba(200, 170, 50, 0.2);
    }

    .auth-section {
      display: flex;
      flex-wrap: wrap;
      gap: 15px;
      background: #100808;
      padding: 18px 20px;
      border-radius: 30px 4px 30px 4px;
      border: 1px solid #552a2a;
      margin-top: 16px;
      box-shadow: inset 0 0 20px #1b0808;
      align-items: center;
      justify-content: space-between;
    }

    .auth-inputs {
      display: flex;
      flex-wrap: wrap;
      gap: 12px;
      flex: 2;
      min-width: 200px;
    }

    .auth-inputs input {
      background: #1c0b0b;
      border: 1px solid #643030;
      border-radius: 40px 4px 40px 4px;
      padding: 12px 18px;
      font-family: 'Courier New', monospace;
      font-size: 1rem;
      color: #e0caca;
      outline: none;
      flex: 1 1 140px;
      box-shadow: inset 0 0 12px #0f0505;
    }

    .auth-inputs input::placeholder { color: #6b4444; }

    .auth-buttons {
      display: flex;
      gap: 12px;
      flex-wrap: wrap;
    }

    .auth-btn {
      background: #281111;
      border: 1px solid #8f3a3a;
      color: #ddbbbb;
      padding: 10px 22px;
      border-radius: 40px 4px 40px 4px;
      font-weight: bold;
      letter-spacing: 2px;
      font-size: 0.9rem;
      transition: 0.2s;
      box-shadow: 0 0 16px #3d0e0e;
      cursor: none;
      display: inline-flex;
      align-items: center;
      gap: 10px;
      font-family: 'Courier New', monospace;
      text-decoration: none;
    }

    .auth-btn i { color: #c55; }
    .auth-btn:hover {
      background: #3f1a1a;
      border-color: #cc6a6a;
      box-shadow: 0 0 30px #8f2a2a;
      transform: scale(1.02);
    }

    .auth-status {
      color: #be8a8a;
      font-size: 0.95rem;
      padding: 6px 14px;
      background: #1d0b0b;
      border-radius: 30px;
      border-left: 4px solid #a33;
      display: flex;
      align-items: center;
      gap: 8px;
      flex: 1;
      min-width: 120px;
    }

    .auth-status i { color: #a33; }

    .welcome-banner {
      display: none;
      background: #1a0808;
      border: 2px solid #7a2e2e;
      border-radius: 30px 4px 30px 4px;
      padding: 18px 25px;
      margin-top: 16px;
      text-align: center;
      box-shadow: 0 0 40px rgba(150, 0, 0, 0.3), inset 0 0 30px #1a0808;
      animation: glowPulse 2s ease-in-out infinite;
    }

    .welcome-banner.active { display: block; }

    @keyframes glowPulse {
      0%, 100% { box-shadow: 0 0 40px rgba(150, 0, 0, 0.3), inset 0 0 30px #1a0808; }
      50% { box-shadow: 0 0 60px rgba(200, 0, 0, 0.5), inset 0 0 40px #2a0a0a; }
    }

    .welcome-banner .welcome-content {
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 20px;
      flex-wrap: wrap;
    }

    .welcome-banner .welcome-icon {
      font-size: 3.5rem;
      color: #cc3333;
      text-shadow: 0 0 30px #ff0000, 0 0 60px #aa0000;
      animation: cursorPulse 1.5s ease-in-out infinite;
    }

    .welcome-banner .welcome-text {
      font-family: 'Impact', 'Arial Black', sans-serif;
      font-size: 2rem;
      letter-spacing: 4px;
      background: linear-gradient(180deg, #ff4444, #cc0000);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      filter: drop-shadow(0 0 20px #ff2222);
    }

    .welcome-banner .welcome-sub { color: #be8a8a; font-size: 1.1rem; letter-spacing: 2px; -webkit-text-fill-color: #be8a8a; }
    .welcome-banner .welcome-user { color: #ff6666; font-weight: bold; font-size: 1.3rem; -webkit-text-fill-color: #ff6666; }

    .action-buttons {
      display: flex;
      gap: 12px;
      flex-wrap: wrap;
      margin-top: 16px;
    }

    .action-btn {
      background: #281111;
      border: 1px solid #8f3a3a;
      color: #ddbbbb;
      padding: 12px 24px;
      border-radius: 40px 4px 40px 4px;
      font-weight: bold;
      letter-spacing: 2px;
      font-size: 0.9rem;
      transition: 0.2s;
      box-shadow: 0 0 16px #3d0e0e;
      cursor: none;
      display: inline-flex;
      align-items: center;
      gap: 12px;
      font-family: 'Courier New', monospace;
      flex: 1;
      justify-content: center;
      min-width: 140px;
    }

    .action-btn i { color: #c55; font-size: 1.2rem; }
    .action-btn:hover {
      background: #3f1a1a;
      border-color: #cc6a6a;
      box-shadow: 0 0 30px #8f2a2a;
      transform: scale(1.02);
    }

    .action-btn.admin-btn {
      border-color: #ccaa33;
      box-shadow: 0 0 30px rgba(200, 170, 50, 0.2);
    }
    .action-btn.admin-btn i { color: #ccaa33; }
    .action-btn.admin-btn:hover {
      border-color: #ffdd44;
      box-shadow: 0 0 50px rgba(200, 170, 50, 0.4);
    }

    .modal-page {
      display: none;
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(10, 5, 5, 0.95);
      justify-content: center;
      align-items: center;
      z-index: 1000;
      padding: 20px;
      overflow-y: auto;
    }

    .modal-page.active { display: flex; }

    .modal-box {
      background: #120808;
      background: linear-gradient(145deg, #1e0e0e 0%, #0f0505 100%);
      border: 2px solid #5f2b2b;
      border-radius: 40px 12px 40px 12px;
      padding: 40px;
      max-width: 750px;
      width: 100%;
      max-height: 90vh;
      overflow-y: auto;
      box-shadow: 0 20px 60px rgba(0, 0, 0, 0.9), 0 0 0 2px #4d1a1a inset;
    }

    .modal-box h2 {
      color: #c9a9a9;
      font-size: 2.2rem;
      text-align: center;
      margin-bottom: 25px;
      text-shadow: 0 0 20px #aa2b2b;
      letter-spacing: 4px;
      font-family: 'Impact', 'Arial Black', sans-serif;
      background: linear-gradient(180deg, #e7d7d7, #a55);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }

    .modal-box .close-btn {
      float: right;
      background: transparent;
      border: none;
      color: #be8a8a;
      font-size: 2rem;
      cursor: none;
      transition: 0.2s;
      padding: 0 10px;
    }

    .modal-box .close-btn:hover { color: #ff4444; transform: scale(1.2); }

    /* ОПИСАНИЕ */
    .description-content { color: #be8a8a; line-height: 1.8; font-size: 1rem; }
    .description-content .film-poster {
      text-align: center;
      font-size: 4rem;
      color: #cc3333;
      text-shadow: 0 0 40px #ff0000, 0 0 80px #880000;
      margin-bottom: 20px;
      animation: cursorPulse 2s ease-in-out infinite;
    }
    .description-content h3 {
      color: #cc5555;
      margin: 25px 0 12px;
      font-size: 1.3rem;
      letter-spacing: 2px;
      border-bottom: 1px dashed #522;
      padding-bottom: 8px;
    }
    .description-content p { margin-bottom: 12px; color: #be8a8a; }

    .description-content .info-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 10px;
      margin: 15px 0;
    }
    .description-content .info-grid span {
      background: #1a0a0a;
      padding: 8px 14px;
      border-radius: 10px;
      border-left: 3px solid #a33;
    }
    .description-content .info-grid .label { color: #884444; }
    .description-content .info-grid .value { color: #ddbbbb; }

    .actors-list {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 8px;
      margin: 10px 0;
    }
    .actors-list .actor-item {
      background: #0a0303;
      padding: 6px 14px;
      border-radius: 20px 2px 20px 2px;
      border-left: 3px solid #8f3a3a;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }
    .actors-list .actor-item .role { color: #884444; font-size: 0.85rem; }
    .actors-list .actor-item .name { color: #ddbbbb; font-weight: bold; }

    /* ОТЗЫВЫ */
    .reviews-section {
      margin-top: 20px;
      border-top: 2px dashed #522;
      padding-top: 20px;
    }

    .reviews-section .review-stats {
      display: flex;
      align-items: center;
      gap: 20px;
      flex-wrap: wrap;
      margin-bottom: 15px;
      background: #0a0303;
      padding: 12px 18px;
      border-radius: 20px 4px 20px 4px;
      border: 1px solid #552a2a;
    }

    .reviews-section .review-stats .avg-rating {
      font-size: 2rem;
      color: #cc5555;
      font-family: 'Impact', 'Arial Black', sans-serif;
    }

    .reviews-section .review-stats .stars-display {
      color: #ccaa33;
      font-size: 1.5rem;
      letter-spacing: 5px;
    }

    .reviews-section .review-stats .count {
      color: #884444;
      font-size: 0.9rem;
    }

    .review-form {
      background: #1a0a0a;
      padding: 18px;
      border-radius: 20px 4px 20px 4px;
      border: 1px solid #643030;
      margin-bottom: 20px;
    }

    .review-form .stars-select {
      display: flex;
      gap: 8px;
      margin: 10px 0 15px;
      font-size: 2rem;
      color: #555;
    }

    .review-form .stars-select .star {
      cursor: none;
      transition: 0.2s;
      color: #555;
    }

    .review-form .stars-select .star.active { color: #ccaa33; text-shadow: 0 0 20px #ccaa33; }
    .review-form .stars-select .star:hover { transform: scale(1.2); }

    .review-form textarea {
      width: 100%;
      background: #0a0303;
      border: 1px solid #643030;
      border-radius: 20px 4px 20px 4px;
      padding: 14px 18px;
      font-family: 'Courier New', monospace;
      font-size: 0.95rem;
      color: #e0caca;
      outline: none;
      resize: vertical;
      min-height: 70px;
      box-shadow: inset 0 0 12px #0f0505;
    }

    .review-form textarea:focus {
      border-color: #b55;
      box-shadow: 0 0 30px #8f2a2a, inset 0 0 20px #3d0e0e;
    }

    .review-form .review-actions {
      display: flex;
      gap: 12px;
      margin-top: 12px;
      flex-wrap: wrap;
    }

    .review-form .review-actions .auth-btn { flex: 1; justify-content: center; min-width: 100px; }

    .review-item {
      background: #0f0505;
      border-radius: 20px 4px 20px 4px;
      border-left: 4px solid #a33;
      padding: 16px 20px;
      margin-bottom: 12px;
    }

    .review-item .review-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      flex-wrap: wrap;
      margin-bottom: 8px;
    }

    .review-item .review-header .review-user { color: #ddbbbb; font-weight: bold; font-size: 1rem; }
    .review-item .review-header .review-stars { color: #ccaa33; letter-spacing: 3px; }
    .review-item .review-header .review-date { color: #664444; font-size: 0.75rem; }

    .review-item .review-text {
      color: #be8a8a;
      font-size: 0.95rem;
      line-height: 1.6;
      word-wrap: break-word;
    }

    .review-item .review-text.spoiler {
      filter: blur(8px);
      cursor: pointer;
      transition: 0.3s;
      user-select: none;
    }

    .review-item .review-text.spoiler:hover { filter: blur(0); }
    .review-item .review-text.spoiler.revealed { filter: blur(0); }

    .review-item .spoiler-hint {
      color: #884444;
      font-size: 0.75rem;
      font-style: italic;
      margin-top: 4px;
    }

    .review-item .review-answer {
      margin-top: 10px;
      padding-top: 10px;
      border-top: 1px dashed #522;
      color: #cc8888;
      font-size: 0.9rem;
    }

    .review-item .review-answer .admin-label { color: #ccaa33; font-weight: bold; }

    .review-item .review-actions-small {
      display: flex;
      gap: 10px;
      margin-top: 10px;
      flex-wrap: wrap;
    }

    .review-item .review-actions-small button {
      background: transparent;
      border: 1px solid #643030;
      color: #884444;
      padding: 4px 14px;
      border-radius: 20px;
      font-family: 'Courier New', monospace;
      font-size: 0.75rem;
      cursor: none;
      transition: 0.2s;
    }

    .review-item .review-actions-small button:hover {
      border-color: #cc6a6a;
      color: #ddbbbb;
    }

    .review-item .review-actions-small button.answer-btn { border-color: #ccaa33; color: #ccaa33; }
    .review-item .review-actions-small button.answer-btn:hover { background: #3f1a1a; }

    .review-answer-form {
      margin-top: 10px;
      padding: 12px;
      background: #0a0303;
      border-radius: 15px 2px 15px 2px;
      display: none;
    }

    .review-answer-form.active { display: block; }

    .review-answer-form textarea {
      width: 100%;
      background: #0a0303;
      border: 1px solid #643030;
      border-radius: 15px 2px 15px 2px;
      padding: 10px 14px;
      font-family: 'Courier New', monospace;
      font-size: 0.9rem;
      color: #e0caca;
      outline: none;
      resize: vertical;
      min-height: 50px;
    }

    .review-answer-form .answer-actions {
      display: flex;
      gap: 10px;
      margin-top: 8px;
    }

    .review-answer-form .answer-actions button {
      padding: 6px 18px;
      border-radius: 20px 2px 20px 2px;
      border: 1px solid #643030;
      background: #281111;
      color: #ddbbbb;
      font-family: 'Courier New', monospace;
      font-size: 0.8rem;
      cursor: none;
      transition: 0.2s;
    }

    .review-answer-form .answer-actions button:hover {
      background: #3f1a1a;
      border-color: #cc6a6a;
    }

    /* АДМИН ПАНЕЛЬ */
    .admin-content { color: #be8a8a; }
    .admin-content .admin-stats {
      display: grid;
      grid-template-columns: 1fr 1fr 1fr 1fr;
      gap: 15px;
      margin: 20px 0;
    }
    .admin-content .stat-card {
      background: #1a0a0a;
      padding: 20px;
      border-radius: 20px 4px 20px 4px;
      border: 1px solid #5f2b2b;
      text-align: center;
    }
    .admin-content .stat-card .num {
      font-size: 2rem;
      color: #cc3333;
      font-family: 'Impact', 'Arial Black', sans-serif;
      text-shadow: 0 0 20px #ff2222;
    }
    .admin-content .stat-card .label { font-size: 0.8rem; color: #884444; margin-top: 5px; }

    .admin-content .admin-list { margin: 15px 0; max-height: 200px; overflow-y: auto; }
    .admin-content .admin-list .list-item {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 8px 14px;
      background: #0f0505;
      border-radius: 10px;
      margin-bottom: 4px;
      border-left: 3px solid #a33;
      flex-wrap: wrap;
      gap: 8px;
    }
    .admin-content .admin-list .list-item .name { color: #ddbbbb; }
    .admin-content .admin-list .list-item .status { color: #6b3; font-size: 0.8rem; }
    .admin-content .admin-list .list-item .status.blocked { color: #cc3333; }
    .admin-content .admin-list .list-item .block-btn {
      background: transparent;
      border: 1px solid #643030;
      color: #884444;
      padding: 2px 12px;
      border-radius: 15px;
      font-family: 'Courier New', monospace;
      font-size: 0.7rem;
      cursor: none;
      transition: 0.2s;
    }
    .admin-content .admin-list .list-item .block-btn:hover {
      border-color: #cc6a6a;
      color: #ddbbbb;
    }
    .admin-content .admin-list .list-item .block-btn.unblock { border-color: #6b3; color: #6b3; }
    .admin-content .admin-list .list-item .block-btn.unblock:hover { border-color: #8d5; color: #8d5; }

    .admin-content .admin-actions {
      display: flex;
      gap: 10px;
      flex-wrap: wrap;
      margin-top: 20px;
    }
    .admin-content .admin-actions .auth-btn { flex: 1; justify-content: center; min-width: 100px; }

    /* БАННЕР БЛОКИРОВКИ */
    .blocked-banner {
      display: none;
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(10, 5, 5, 0.98);
      justify-content: center;
      align-items: center;
      z-index: 99999;
      padding: 20px;
    }
    .blocked-banner.active { display: flex; }

    .blocked-box {
      background: #120808;
      border: 3px solid #cc0000;
      border-radius: 40px 12px 40px 12px;
      padding: 50px 40px;
      max-width: 500px;
      width: 100%;
      text-align: center;
      box-shadow: 0 0 100px rgba(200, 0, 0, 0.3), inset 0 0 50px #1a0808;
      animation: glowPulse 1.5s ease-in-out infinite;
    }
    .blocked-box .blocked-icon { font-size: 5rem; color: #cc0000; text-shadow: 0 0 60px #ff0000, 0 0 120px #880000; margin-bottom: 20px; }
    .blocked-box h2 { color: #cc3333; font-size: 2.2rem; font-family: 'Impact', 'Arial Black', sans-serif; letter-spacing: 4px; text-shadow: 0 0 30px #ff2222; margin-bottom: 15px; }
    .blocked-box p { color: #be8a8a; font-size: 1.1rem; line-height: 1.6; margin-bottom: 20px; }
    .blocked-box .blocked-timer { color: #ff6666; font-size: 2.5rem; font-weight: bold; text-shadow: 0 0 30px #ff0000; font-family: 'Impact', 'Arial Black', sans-serif; }

    /* КАПЧА */
    .captcha-container {
      background: #1a0a0a;
      border: 1px solid #5f2b2b;
      border-radius: 20px 4px 20px 4px;
      padding: 20px;
      margin-bottom: 20px;
      text-align: center;
    }

    .captcha-container .captcha-text {
      font-size: 2.5rem;
      font-weight: bold;
      letter-spacing: 15px;
      color: #cc5555;
      text-shadow: 0 0 30px #ff2222, 0 0 60px #880000;
      font-family: 'Impact', 'Arial Black', sans-serif;
      background: #0a0303;
      padding: 15px;
      border-radius: 10px;
      border: 2px dashed #8f3a3a;
      margin-bottom: 15px;
      user-select: none;
    }

    .captcha-container .captcha-input-wrap {
      display: flex;
      gap: 12px;
      align-items: center;
      justify-content: center;
      flex-wrap: wrap;
    }

    .captcha-container .captcha-input-wrap input {
      flex: 1;
      min-width: 150px;
      background: #1c0b0b;
      border: 1px solid #643030;
      border-radius: 40px 4px 40px 4px;
      padding: 12px 18px;
      font-family: 'Courier New', monospace;
      font-size: 1.1rem;
      color: #e0caca;
      outline: none;
      box-shadow: inset 0 0 12px #0f0505;
      text-align: center;
      letter-spacing: 3px;
    }

    .captcha-container .captcha-input-wrap input::placeholder { color: #6b4444; letter-spacing: 1px; }
    .captcha-container .captcha-input-wrap input:focus {
      border-color: #b55;
      box-shadow: 0 0 30px #8f2a2a, inset 0 0 20px #3d0e0e;
    }

    .captcha-container .captcha-refresh {
      background: #281111;
      border: 1px solid #8f3a3a;
      color: #ddbbbb;
      padding: 12px 16px;
      border-radius: 40px 4px 40px 4px;
      font-size: 1.2rem;
      transition: 0.2s;
      box-shadow: 0 0 16px #3d0e0e;
      cursor: none;
      display: inline-flex;
      align-items: center;
      gap: 8px;
      font-family: 'Courier New', monospace;
    }

    .captcha-container .captcha-refresh:hover {
      background: #3f1a1a;
      border-color: #cc6a6a;
      box-shadow: 0 0 30px #8f2a2a;
      transform: scale(1.05);
    }

    .captcha-container .captcha-error { color: #cc5555; font-size: 0.85rem; margin-top: 10px; min-height: 20px; }

    .register-box .register-actions {
      display: flex;
      gap: 15px;
      margin-top: 25px;
      justify-content: center;
      flex-wrap: wrap;
    }
    .register-box .register-actions .auth-btn { flex: 1; justify-content: center; min-width: 120px; }

    .register-box .error-msg { color: #cc5555; text-align: center; margin-top: 15px; font-size: 0.9rem; min-height: 24px; }
    .register-box .success-msg { color: #55cc55; text-align: center; margin-top: 15px; font-size: 0.9rem; min-height: 24px; }

    .blood-line {
      display: flex;
      justify-content: flex-end;
      margin-top: 25px;
      font-size: 0.9rem;
      color: #6a3a3a;
      letter-spacing: 4px;
      gap: 15px;
      flex-wrap: wrap;
      border-top: 1px solid #3f1a1a;
      padding-top: 20px;
    }
    .blood-line span i { margin-right: 8px; color: #a22; }
    .blood-line .knife-icon { font-size: 1.6rem; transform: rotate(45deg); color: #aa7a7a; text-shadow: 0 0 20px #b33; }

    .register-page {
      display: none;
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(10, 5, 5, 0.95);
      justify-content: center;
      align-items: center;
      z-index: 1000;
      padding: 20px;
      overflow-y: auto;
    }
    .register-page.active { display: flex; }

    .register-box {
      background: #120808;
      background: linear-gradient(145deg, #1e0e0e 0%, #0f0505 100%);
      border: 2px solid #5f2b2b;
      border-radius: 40px 12px 40px 12px;
      padding: 40px;
      max-width: 480px;
      width: 100%;
      box-shadow: 0 20px 60px rgba(0, 0, 0, 0.9), 0 0 0 2px #4d1a1a inset;
    }

    .register-box h2 {
      color: #c9a9a9;
      font-size: 2.4rem;
      text-align: center;
      margin-bottom: 30px;
      text-shadow: 0 0 20px #aa2b2b;
      letter-spacing: 4px;
      font-family: 'Impact', 'Arial Black', sans-serif;
      background: linear-gradient(180deg, #e7d7d7, #a55);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }

    .register-box .input-group { margin-bottom: 20px; }
    .register-box .input-group label { color: #b99; display: block; margin-bottom: 8px; font-size: 0.9rem; letter-spacing: 2px; }
    .register-box .input-group input {
      width: 100%;
      background: #1c0b0b;
      border: 1px solid #643030;
      border-radius: 40px 4px 40px 4px;
      padding: 14px 20px;
      font-family: 'Courier New', monospace;
      font-size: 1rem;
      color: #e0caca;
      outline: none;
      box-shadow: inset 0 0 12px #0f0505;
    }
    .register-box .input-group input::placeholder { color: #6b4444; }
    .register-box .input-group input:focus {
      border-color: #b55;
      box-shadow: 0 0 30px #8f2a2a, inset 0 0 20px #3d0e0e;
    }

    @media (max-width: 700px) {
      .vink-container { padding: 20px 15px 30px; }
      .header h1 { font-size: 2.6rem; letter-spacing: 4px; }
      .file-upload-label { font-size: 0.8rem; padding: 8px 14px; }
      .auth-section { flex-direction: column; align-items: stretch; }
      .register-box { padding: 30px 20px; }
      .register-box h2 { font-size: 1.8rem; }
      .welcome-banner .welcome-text { font-size: 1.4rem; }
      .welcome-banner .welcome-icon { font-size: 2.5rem; }
      .captcha-container .captcha-text { font-size: 1.8rem; letter-spacing: 10px; }
      .blocked-box { padding: 30px 20px; }
      .blocked-box h2 { font-size: 1.6rem; }
      .description-content .info-grid { grid-template-columns: 1fr; }
      .admin-content .admin-stats { grid-template-columns: 1fr 1fr; }
      .modal-box { padding: 25px 20px; }
      .action-btn { min-width: 100%; }
      .actors-list { grid-template-columns: 1fr; }
      .series-item { min-width: 100%; }
      .series-item .series-thumb { width: 30px; height: 30px; }
    }

    @media (max-width: 480px) {
      .header h1 { font-size: 2rem; }
      .custom-cursor { font-size: 20px; }
      .captcha-container .captcha-text { font-size: 1.5rem; letter-spacing: 8px; }
      .quality-control select { font-size: 0.7rem; padding: 4px 8px; }
      .quality-control label { font-size: 0.7rem; }
      .admin-content .admin-stats { grid-template-columns: 1fr; }
    }

    ::-webkit-scrollbar { width: 12px; background: #1a0808; }
    ::-webkit-scrollbar-thumb { background: #6a2a2a; border-radius: 20px; border: 2px solid #2c0a0a; }
  </style>
</head>
<body>
  <!-- КУРСОР -->
  <div class="custom-cursor" id="redCursor"><i class="fas fa-plus"></i></div>

  <!-- ПАРЯЩИЕ КАПЛИ КРОВИ -->
  <div class="blood-particle" style="top:10%; left:5%; animation-delay:0s; font-size:3rem;"><i class="fas fa-tint"></i></div>
  <div class="blood-particle" style="top:30%; right:8%; animation-delay:5s; font-size:2rem;"><i class="fas fa-tint"></i></div>
  <div class="blood-particle" style="bottom:20%; left:10%; animation-delay:3s; font-size:2.5rem;"><i class="fas fa-tint"></i></div>
  <div class="blood-particle" style="bottom:40%; right:5%; animation-delay:7s; font-size:1.8rem;"><i class="fas fa-tint"></i></div>
  <div class="blood-particle" style="top:50%; left:50%; animation-delay:2s; font-size:2.2rem;"><i class="fas fa-tint"></i></div>
  <div class="blood-particle" style="top:15%; right:25%; animation-delay:9s; font-size:1.5rem;"><i class="fas fa-tint"></i></div>

  <!-- БАННЕР БЛОКИРОВКИ -->
  <div class="blocked-banner" id="blockedBanner">
    <div class="blocked-box">
      <div class="blocked-icon"><i class="fas fa-skull"></i></div>
      <h2>⚠️ ДОСТУП ЗАБЛОКИРОВАН</h2>
      <p>Обнаружена подозрительная активность. Доступ к сайту временно ограничен.</p>
      <div class="blocked-timer" id="blockedTimer">30</div>
    </div>
  </div>

  <!-- МОДАЛКА: ОПИСАНИЕ -->
  <div class="modal-page" id="descriptionModal">
    <div class="modal-box">
      <button class="close-btn" id="closeDescription"><i class="fas fa-times"></i></button>
      <h2><i class="fas fa-film"></i> О фильме</h2>
      <div class="description-content">
        <div class="film-poster"><i class="fas fa-skull"></i></div>

        <h3>📖 Сюжет</h3>
        <p>Компания друзей отправляется на отдых к реке — искупаться, выпить пива, отвлечься от повседневных забот. Веселье, шутки, флирт, игры — поначалу всё выглядит как типичная вылазка на природу. Но идиллию нарушает нечто зловещее: в лесу появился Маньяк, мотивы которого окутаны тайной. Атмосфера постепенно накаляется, а беззаботное времяпрепровождение оборачивается борьбой за выживание.</p>

        <div class="info-grid">
          <span><span class="label">🎬 Режиссёр:</span> <span class="value">Всеволод К.</span></span>
          <span><span class="label">📅 Год:</span> <span class="value">2026</span></span>
          <span><span class="label">📍 Город:</span> <span class="value">Каменск-Уральский</span></span>
          <span><span class="label">🌍 Страна:</span> <span class="value">Россия</span></span>
          <span><span class="label">⏱️ Длительность:</span> <span class="value">25 мин</span></span>
          <span><span class="label">🔞 Возраст:</span> <span class="value">18+</span></span>
          <span><span class="label">🏷️ Жанр:</span> <span class="value">Психологический слэшер, драма</span></span>
        </div>

        <h3>🎭 Актёры и роли</h3>
        <div class="actors-list">
          <div class="actor-item"><span class="name">Матвей</span><span class="role">Маньяк</span></div>
          <div class="actor-item"><span class="name">Севастьян</span><span class="role">Парень Даши</span></div>
          <div class="actor-item"><span class="name">Дарья</span><span class="role">Девушка Севы</span></div>
          <div class="actor-item"><span class="name">Анастасия</span><span class="role">Сестра Матвея</span></div>
          <div class="actor-item"><span class="name">Павел</span><span class="role">Муж сестры Матвея</span></div>
          <div class="actor-item"><span class="name">Максим</span><span class="role">Тихоня, друг Севы и Матвея</span></div>
          <div class="actor-item"><span class="name">Егор</span><span class="role">Весёлая часть компании</span></div>
          <div class="actor-item"><span class="name">Андрей</span><span class="role">Малословный друг Севы</span></div>
          <div class="actor-item"><span class="name">Кирилл</span><span class="role">Гитарист, друг Василисы</span></div>
          <div class="actor-item"><span class="name">Василиса</span><span class="role">Подруга Кирилла</span></div>
        </div>

        <h3>🔪 О фильме</h3>
        <p>Короткометражный хоррор в лучших традициях слэшеров. Атмосфера напряжения, неожиданные повороты и психологическая глубина делают эту историю уникальной в своём жанре.</p>
        <p style="color:#884444; font-size:0.85rem; margin-top:10px;">
          <i class="fas fa-tag"></i> Производство: Каменск-Уральский, Россия • 2026
        </p>
      </div>
    </div>
  </div>

  <!-- МОДАЛКА: АДМИН ПАНЕЛЬ -->
  <div class="modal-page" id="adminModal">
    <div class="modal-box">
      <button class="close-btn" id="closeAdmin"><i class="fas fa-times"></i></button>
      <h2><i class="fas fa-crown"></i> Админ-панель</h2>
      <div class="admin-content">
        <p style="text-align:center; color:#cc5555; margin-bottom:10px;">
          <i class="fas fa-shield-alt"></i> Добро пожаловать, Администратор!
        </p>
        <div class="admin-stats">
          <div class="stat-card"><div class="num" id="adminUsersCount">0</div><div class="label">👥 Пользователей</div></div>
          <div class="stat-card"><div class="num" id="adminBlockedCount">0</div><div class="label">🚫 Заблокировано</div></div>
          <div class="stat-card"><div class="num" id="adminReviewsCount">0</div><div class="label">💬 Отзывов</div></div>
          <div class="stat-card"><div class="num" id="adminAvgRating">0</div><div class="label">⭐ Средний рейтинг</div></div>
        </div>

        <h3 style="color:#cc5555; margin: 15px 0 10px;">📋 Пользователи</h3>
        <div class="admin-list" id="adminUserList"></div>

        <div class="admin-actions">
          <button class="auth-btn" id="adminClearUsers"><i class="fas fa-trash"></i> Очистить всех</button>
          <button class="auth-btn" id="adminClearVideos"><i class="fas fa-video-slash"></i> Очистить видео</button>
          <button class="auth-btn" id="adminRefreshStats"><i class="fas fa-sync"></i> Обновить</button>
        </div>
        <div style="margin-top:15px; padding:12px; background:#0a0303; border-radius:10px; border-left:3px solid #a33;">
          <p style="color:#884444; font-size:0.85rem;"><i class="fas fa-info-circle"></i> Все действия логируются.</p>
        </div>
      </div>
    </div>
  </div>

  <!-- РЕГИСТРАЦИЯ -->
  <div class="register-page" id="registerPage">
    <div class="register-box">
      <h2><i class="fas fa-user-plus"></i> Регистрация</h2>
      <div class="input-group">
        <label><i class="fas fa-user"></i> Логин</label>
        <input type="text" id="regLogin" placeholder="Придумайте логин">
      </div>
      <div class="input-group">
        <label><i class="fas fa-lock"></i> Пароль</label>
        <input type="password" id="regPassword" placeholder="Придумайте пароль">
      </div>
      <div class="input-group">
        <label><i class="fas fa-check-circle"></i> Подтверждение</label>
        <input type="password" id="regPasswordConfirm" placeholder="Повторите пароль">
      </div>
      <div class="captcha-container">
        <div class="captcha-text" id="captchaText">XK4P</div>
        <div class="captcha-input-wrap">
          <input type="text" id="captchaInput" placeholder="Введите код" maxlength="6" autocomplete="off">
          <button class="captcha-refresh" id="captchaRefresh"><i class="fas fa-sync-alt"></i></button>
        </div>
        <div class="captcha-error" id="captchaError"></div>
      </div>
      <div class="error-msg" id="regError"></div>
      <div class="success-msg" id="regSuccess"></div>
      <div class="register-actions">
        <button class="auth-btn" id="regSubmitBtn"><i class="fas fa-user-plus"></i> Зарегистрироваться</button>
        <button class="auth-btn" id="regCancelBtn"><i class="fas fa-times"></i> Отмена</button>
      </div>
    </div>
  </div>

  <!-- ОСНОВНОЙ КОНТЕЙНЕР -->
  <div class="vink-container">
    <!-- КРОВАВЫЕ УГЛЫ -->
    <div class="blood-corner tl"><i class="fas fa-cross"></i></div>
    <div class="blood-corner tr"><i class="fas fa-cross"></i></div>
    <div class="blood-corner bl"><i class="fas fa-cross"></i></div>
    <div class="blood-corner br"><i class="fas fa-cross"></i></div>

    <div class="header">
      <h1>BLuMP</h1>
      <div class="slash-icon">
        <i class="fas fa-skull"></i>
        <span style="margin: 0 6px;">/</span>
        <i class="fas fa-hat-wizard" style="opacity:0.7;"></i>
      </div>
    </div>

    <!-- ВИДЕО -->
    <div class="video-section">
      <div class="video-wrapper">
        <div class="video-thumbnail" id="videoThumbnail">
          <img id="thumbnailImg" src="" alt="Обложка видео">
        </div>
        <video id="videoPlayer" controls playsinline><source src="" type="video/mp4"></video>
      </div>
      <div class="video-controls">
        <label for="videoInput" class="file-upload-label" id="uploadLabel">
          <i class="fas fa-upload"></i> Загрузить видео
        </label>
        <input type="file" id="videoInput" accept="video/*">
        <input type="file" id="thumbnailInput" accept="image/*" style="display:none;">
        <div class="quality-control">
          <label><i class="fas fa-sliders-h"></i> Качество</label>
          <select id="qualitySelect">
            <option value="auto">Авто</option>
            <option value="1080p">1080p</option>
            <option value="720p">720p</option>
            <option value="480p">480p</option>
            <option value="360p">360p</option>
          </select>
        </div>
        <span class="video-status" id="videoStatus"><i class="fas fa-video"></i> Нет видео</span>
      </div>
    </div>

    <!-- СПИСОК СЕРИЙ -->
    <div class="series-section">
      <div class="series-header">
        <h3><i class="fas fa-list"></i> Список серий</h3>
        <span class="series-count" id="seriesCount">Всего: 0 серий</span>
      </div>
      <div class="series-list" id="seriesList">
        <p style="color:#664444; text-align:center; width:100%; padding:20px;">
          <i class="fas fa-video-slash"></i> Нет загруженных серий
        </p>
      </div>
    </div>

    <!-- ПРИВЕТСТВИЕ -->
    <div class="welcome-banner" id="welcomeBanner">
      <div class="welcome-content">
        <div class="welcome-icon"><i class="fas fa-skull"></i></div>
        <div>
          <div class="welcome-text">ДОБРО ПОЖАЛОВАТЬ В FRIDAY</div>
          <div class="welcome-sub">
            <i class="fas fa-user" style="color:#a33;"></i> 
            <span class="welcome-user" id="welcomeUser">Гость</span>
            <i class="fas fa-droplet" style="color:#a33; margin-left: 10px;"></i>
          </div>
        </div>
        <div class="welcome-icon"><i class="fas fa-knife"></i></div>
      </div>
    </div>

    <!-- КНОПКИ -->
    <div class="action-buttons">
      <button class="action-btn" id="showDescriptionBtn"><i class="fas fa-info-circle"></i> Описание</button>
      <button class="action-btn admin-btn" id="showAdminBtn" style="display:none;"><i class="fas fa-crown"></i> Админ-панель</button>
    </div>

    <!-- ОТЗЫВЫ -->
    <div class="reviews-section" id="reviewsSection">
      <div class="review-stats">
        <span class="avg-rating" id="avgRating">0.0</span>
        <span class="stars-display" id="starsDisplay">☆☆☆☆☆</span>
        <span class="count" id="reviewsCount">0 отзывов</span>
      </div>

      <div class="review-form" id="reviewForm">
        <div class="stars-select" id="starsSelect">
          <span class="star" data-value="1">☆</span>
          <span class="star" data-value="2">☆</span>
          <span class="star" data-value="3">☆</span>
          <span class="star" data-value="4">☆</span>
          <span class="star" data-value="5">☆</span>
        </div>
        <textarea id="reviewText" placeholder="Ваш отзыв (спойлеры скрываются автоматически)..."></textarea>
        <div class="review-actions">
          <button class="auth-btn" id="submitReviewBtn"><i class="fas fa-pen"></i> Оставить отзыв</button>
        </div>
      </div>

      <div id="reviewsList"></div>
    </div>

    <!-- АВТОРИЗАЦИЯ -->
    <div class="auth-section">
      <div class="auth-inputs">
        <input type="text" id="loginInput" placeholder="Логин">
        <input type="password" id="passwordInput" placeholder="Пароль">
      </div>
      <div class="auth-buttons">
        <button class="auth-btn" id="showRegisterBtn"><i class="fas fa-user-plus"></i> Регистрация</button>
        <button class="auth-btn" id="loginBtn"><i class="fas fa-sign-in-alt"></i> Вход</button>
        <button class="auth-btn" id="logoutBtn"><i class="fas fa-sign-out-alt"></i> Выйти</button>
      </div>
      <div class="auth-status" id="authStatus"><i class="fas fa-circle" style="color:#6b3;"></i> Гость</div>
    </div>

    <div class="blood-line">
      <span><i class="fas fa-droplet"></i> Пятница </span>
      <span><i class="fas fa-dagger"></i> резня</span>
      <span class="knife-icon"><i class="fas fa-cut"></i></span>
      <span><i class="fas fa-film"></i> слэшер</span>
    </div>
  </div>

  <script>
    (function() {
      "use strict";

      // ============================================================
      // 1. КУРСОР
      // ============================================================
      const redCursor = document.getElementById('redCursor');
      if (redCursor) {
        document.addEventListener('mousemove', (e) => {
          redCursor.style.left = e.clientX + 'px';
          redCursor.style.top = e.clientY + 'px';
        });
        document.addEventListener('mouseleave', () => { redCursor.style.opacity = '0'; });
        document.addEventListener('mouseenter', () => { redCursor.style.opacity = '1'; });
      }

      // ============================================================
      // 2. АНТИ-DDoS
      // ============================================================
      const blockedBanner = document.getElementById('blockedBanner');
      const blockedTimer = document.getElementById('blockedTimer');
      let clickCount = 0;
      let clickTimer = null;
      let isBlocked = false;
      let blockTimerInterval = null;

      function blockAccess(seconds = 30) {
        if (isBlocked) return;
        isBlocked = true;
        blockedBanner.classList.add('active');
        let remaining = seconds;
        blockedTimer.textContent = remaining;
        if (blockTimerInterval) clearInterval(blockTimerInterval);
        blockTimerInterval = setInterval(() => {
          remaining--;
          blockedTimer.textContent = remaining;
          if (remaining <= 0) {
            clearInterval(blockTimerInterval);
            blockTimerInterval = null;
            blockedBanner.classList.remove('active');
            isBlocked = false;
            clickCount = 0;
          }
        }, 1000);
      }

      document.addEventListener('click', function(e) {
        if (isBlocked) { e.preventDefault(); e.stopPropagation(); return; }
        clickCount++;
        if (clickTimer) clearTimeout(clickTimer);
        clickTimer = setTimeout(() => { clickCount = 0; }, 3000);
        if (clickCount > 20) { blockAccess(30); clickCount = 0; }
      }, true);

      let lastActionTime = 0;
      function throttleAction() {
        const now = Date.now();
        if (now - lastActionTime < 500) return false;
        lastActionTime = now;
        return true;
      }

      // ============================================================
      // 3. КАПЧА
      // ============================================================
      const captchaText = document.getElementById('captchaText');
      const captchaInput = document.getElementById('captchaInput');
      const captchaRefresh = document.getElementById('captchaRefresh');
      const captchaError = document.getElementById('captchaError');
      let currentCaptcha = '';

      function generateCaptcha() {
        const chars = 'ABCDEFGHJKLMNPQRSTUVWXYZ23456789';
        let result = '';
        for (let i = 0; i < 4; i++) result += chars.charAt(Math.floor(Math.random() * chars.length));
        return result;
      }

      function refreshCaptcha() {
        currentCaptcha = generateCaptcha();
        captchaText.textContent = currentCaptcha;
        captchaInput.value = '';
        captchaError.textContent = '';
        captchaText.style.animation = 'none';
        setTimeout(() => { captchaText.style.animation = 'cursorPulse 0.5s ease-in-out'; }, 10);
      }

      if (captchaRefresh) captchaRefresh.addEventListener('click', refreshCaptcha);
      refreshCaptcha();

      // ============================================================
      // 4. УПРАВЛЕНИЕ СЕРИЯМИ
      // ============================================================
      const ADMIN_LOGIN = 'Admin';
      const ADMIN_PASSWORD = 'Admin123$';

      function getCurrentUser() { return localStorage.getItem('vinkCurrentUser') || null; }
      function isAdmin() { return getCurrentUser() === ADMIN_LOGIN; }

      function getSeries() {
        return JSON.parse(localStorage.getItem('vinkSeries') || '[]');
      }

      function saveSeries(series) {
        localStorage.setItem('vinkSeries', JSON.stringify(series));
        renderSeries();
      }

      function addSeries(name, data, thumbnail) {
        if (!isAdmin()) {
          alert('⛔ Только администратор может загружать видео!');
          return false;
        }
        const series = getSeries();
        const newSeries = {
          id: Date.now(),
          name: name || 'Серия ' + (series.length + 1),
          data: data,
          thumbnail: thumbnail || null,
          date: new Date().toLocaleDateString('ru-RU')
        };
        series.push(newSeries);
        saveSeries(series);
        return true;
      }

      function deleteSeries(id) {
        if (!isAdmin()) {
          alert('⛔ Только администратор может удалять видео!');
          return false;
        }
        let series = getSeries();
        const index = series.findIndex(s => s.id === id);
        if (index === -1) return false;
        if (series[index].data && series[index].data.startsWith('blob:')) {
          URL.revokeObjectURL(series[index].data);
        }
        if (series[index].thumbnail && series[index].thumbnail.startsWith('blob:')) {
          URL.revokeObjectURL(series[index].thumbnail);
        }
        series.splice(index, 1);
        saveSeries(series);
        const currentId = parseInt(localStorage.getItem('vinkCurrentSeriesId') || '0');
        if (currentId === id) {
          localStorage.removeItem('vinkCurrentSeriesId');
          document.getElementById('videoPlayer').src = '';
          document.getElementById('videoStatus').innerHTML = '<i class="fas fa-video"></i> Нет видео';
          document.getElementById('videoThumbnail').classList.remove('active');
        }
        return true;
      }

      function playSeries(id) {
        const series = getSeries();
        const item = series.find(s => s.id === id);
        if (!item) return;
        const video = document.getElementById('videoPlayer');
        const thumbnail = document.getElementById('videoThumbnail');
        const thumbImg = document.getElementById('thumbnailImg');

        if (video.src && video.src.startsWith('blob:')) {
          URL.revokeObjectURL(video.src);
        }

        // Устанавливаем видео
        if (item.data && item.data.startsWith('blob:')) {
          video.src = item.data;
        } else if (item.data) {
          video.src = item.data;
        }
        video.load();

        // Устанавливаем обложку
        if (item.thumbnail && item.thumbnail.startsWith('blob:')) {
          thumbImg.src = item.thumbnail;
          thumbnail.classList.add('active');
        } else {
          thumbnail.classList.remove('active');
        }

        localStorage.setItem('vinkCurrentSeriesId', String(id));
        document.getElementById('videoStatus').innerHTML = 
          `<i class="fas fa-play" style="color:#b33;"></i> ${item.name}`;
        renderSeries();
      }

      // ============================================================
      // 5. ВИДЕО ПЛЕЕР + ЗАГРУЗКА
      // ============================================================
      const videoInput = document.getElementById('videoInput');
      const thumbnailInput = document.getElementById('thumbnailInput');
      const videoPlayer = document.getElementById('videoPlayer');
      const videoStatus = document.getElementById('videoStatus');
      const qualitySelect = document.getElementById('qualitySelect');
      const uploadLabel = document.getElementById('uploadLabel');
      const videoThumbnail = document.getElementById('videoThumbnail');
      const thumbnailImg = document.getElementById('thumbnailImg');

      let pendingVideoFile = null;
      let pendingThumbnailFile = null;

      function updateUploadButton() {
        if (isAdmin()) {
          uploadLabel.classList.remove('hidden');
          uploadLabel.innerHTML = '<i class="fas fa-upload"></i> Загрузить видео';
        } else {
          uploadLabel.classList.add('hidden');
        }
      }

      // Обработка загрузки видео
      if (videoInput) {
        videoInput.addEventListener('change', function(e) {
          if (!isAdmin()) {
            alert('⛔ Только администратор может загружать видео!');
            this.value = '';
            return;
          }
          if (isBlocked) { alert('Доступ временно заблокирован.'); this.value = ''; return; }

          const file = this.files[0];
          if (!file) return;
          
          if (!file.type.startsWith('video/')) {
            alert('Пожалуйста, выберите видеофайл.');
            this.value = '';
            return;
          }

          const MAX_SIZE = 10 * 1024 * 1024 * 1024;
          if (file.size > MAX_SIZE) {
            alert('Файл слишком большой! Максимум 10 ГБ.');
            this.value = '';
            return;
          }

          pendingVideoFile = file;
          
          // Проверяем, есть ли уже обложка
          if (pendingThumbnailFile) {
            processUpload();
          } else {
            // Предлагаем загрузить обложку
            if (confirm('Хотите добавить обложку для видео?')) {
              thumbnailInput.click();
            } else {
              processUpload();
            }
          }
        });
      }

      // Обработка загрузки обложки
      if (thumbnailInput) {
        thumbnailInput.addEventListener('change', function(e) {
          const file = this.files[0];
          if (!file) return;
          if (!file.type.startsWith('image/')) {
            alert('Пожалуйста, выберите изображение для обложки!');
            this.value = '';
            return;
          }
          pendingThumbnailFile = file;
          if (pendingVideoFile) {
            processUpload();
          }
        });
      }

      function processUpload() {
        if (!pendingVideoFile) return;

        const seriesName = prompt('Введите название серии:', 'Серия ' + (getSeries().length + 1));
        if (seriesName === null) {
          pendingVideoFile = null;
          pendingThumbnailFile = null;
          videoInput.value = '';
          thumbnailInput.value = '';
          return;
        }

        // Создаём blob для видео
        const videoUrl = URL.createObjectURL(pendingVideoFile);
        
        // Создаём blob для обложки
        let thumbUrl = null;
        if (pendingThumbnailFile) {
          thumbUrl = URL.createObjectURL(pendingThumbnailFile);
          // Показываем обложку
          thumbnailImg.src = thumbUrl;
          videoThumbnail.classList.add('active');
        }

        // Сохраняем серию
        addSeries(seriesName.trim() || 'Серия ' + (getSeries().length + 1), videoUrl, thumbUrl);

        // Воспроизводим
        videoPlayer.src = videoUrl;
        videoPlayer.load();
        videoStatus.innerHTML = `<i class="fas fa-play" style="color:#b33;"></i> ${seriesName}`;

        // Сбрасываем
        pendingVideoFile = null;
        pendingThumbnailFile = null;
        videoInput.value = '';
        thumbnailInput.value = '';
      }

      // Качество
      if (qualitySelect) {
        qualitySelect.addEventListener('change', function() {
          const quality = this.value;
          if (quality === 'auto') {
            videoPlayer.removeAttribute('height');
            videoPlayer.removeAttribute('width');
            videoPlayer.style.width = '100%';
            videoPlayer.style.height = '100%';
          } else {
            const height = parseInt(quality);
            videoPlayer.style.height = height + 'px';
            videoPlayer.style.width = 'auto';
          }
        });
      }

      // ============================================================
      // 6. ОТРИСОВКА СЕРИЙ
      // ============================================================
      function renderSeries() {
        const container = document.getElementById('seriesList');
        const series = getSeries();
        const count = document.getElementById('seriesCount');
        const currentId = parseInt(localStorage.getItem('vinkCurrentSeriesId') || '0');
        const isAdminUser = isAdmin();

        count.textContent = 'Всего: ' + series.length + ' серий';

        if (series.length === 0) {
          container.innerHTML = `
            <p style="color:#664444; text-align:center; width:100%; padding:20px;">
              <i class="fas fa-video-slash"></i> Нет загруженных серий
            </p>
          `;
          return;
        }

        let html = '';
        series.forEach(item => {
          const isCurrent = item.id === currentId;
          const thumbSrc = item.thumbnail && item.thumbnail.startsWith('blob:') ? item.thumbnail : '';
          html += `
            <div class="series-item ${isCurrent ? 'current' : ''}">
              ${thumbSrc ? `<img class="series-thumb" src="${thumbSrc}" alt="Обложка">` : 
                `<div class="series-thumb" style="display:flex;align-items:center;justify-content:center;color:#664444;font-size:1.2rem;"><i class="fas fa-video"></i></div>`}
              <div class="series-info">
                <span class="series-num">#${series.indexOf(item) + 1}</span>
                <span class="series-name">${item.name}</span>
              </div>
              <div class="series-actions">
                <span class="series-play" onclick="playSeries(${item.id})" title="Воспроизвести">
                  <i class="fas fa-play"></i>
                </span>
                ${isAdminUser ? `
                  <span class="series-delete" onclick="deleteSeries(${item.id})" title="Удалить серию">
                    <i class="fas fa-trash"></i>
                  </span>
                ` : ''}
              </div>
            </div>
          `;
        });
        container.innerHTML = html;
      }

      window.playSeries = playSeries;
      window.deleteSeries = deleteSeries;

      // ============================================================
      // 7. РЕГИСТРАЦИЯ
      // ============================================================
      const registerPage = document.getElementById('registerPage');
      const showRegisterBtn = document.getElementById('showRegisterBtn');
      const regCancelBtn = document.getElementById('regCancelBtn');
      const regSubmitBtn = document.getElementById('regSubmitBtn');
      const regLogin = document.getElementById('regLogin');
      const regPassword = document.getElementById('regPassword');
      const regPasswordConfirm = document.getElementById('regPasswordConfirm');
      const regError = document.getElementById('regError');
      const regSuccess = document.getElementById('regSuccess');

      let registrationAttempts = 0;
      let registrationBlocked = false;

      function showRegisterPage() {
        if (isBlocked) { alert('Доступ временно заблокирован.'); return; }
        registerPage.classList.add('active');
        regError.textContent = '';
        regSuccess.textContent = '';
        regLogin.value = '';
        regPassword.value = '';
        regPasswordConfirm.value = '';
        refreshCaptcha();
      }

      function hideRegisterPage() { registerPage.classList.remove('active'); }

      if (showRegisterBtn) showRegisterBtn.addEventListener('click', showRegisterPage);
      if (regCancelBtn) regCancelBtn.addEventListener('click', hideRegisterPage);
      registerPage.addEventListener('click', function(e) { if (e.target === registerPage) hideRegisterPage(); });

      function validateCaptcha() {
        const userInput = captchaInput.value.trim().toUpperCase();
        if (userInput !== currentCaptcha) {
          captchaError.textContent = '❌ Неверный код! Попробуйте снова.';
          refreshCaptcha();
          return false;
        }
        captchaError.textContent = '';
        return true;
      }

      if (regSubmitBtn) {
        regSubmitBtn.addEventListener('click', function() {
          if (isBlocked) { alert('Доступ временно заблокирован.'); return; }
          if (registrationBlocked) { regError.textContent = '⛔ Слишком много попыток. Подождите 60 сек.'; return; }
          if (!throttleAction()) { regError.textContent = '⏳ Слишком быстро! Подождите секунду.'; return; }

          const login = regLogin.value.trim();
          const password = regPassword.value.trim();
          const confirm = regPasswordConfirm.value.trim();

          regError.textContent = '';
          regSuccess.textContent = '';

          if (!validateCaptcha()) {
            registrationAttempts++;
            if (registrationAttempts >= 3) {
              registrationBlocked = true;
              regError.textContent = '⛔ Слишком много неудачных попыток. Подождите 60 секунд.';
              setTimeout(() => { registrationBlocked = false; registrationAttempts = 0; }, 60000);
            }
            return;
          }

          registrationAttempts = 0;

          if (!login) { regError.textContent = '❌ Введите логин!'; return; }
          if (login.length < 3) { regError.textContent = '❌ Логин должен содержать минимум 3 символа!'; return; }
          if (!password) { regError.textContent = '❌ Введите пароль!'; return; }
          if (password.length < 4) { regError.textContent = '❌ Пароль должен содержать минимум 4 символа!'; return; }
          if (password !== confirm) { regError.textContent = '❌ Пароли не совпадают!'; return; }

          const badLogins = ['admin', 'root', 'test', 'user', 'guest', 'bot', 'spam', 'hacker'];
          if (badLogins.includes(login.toLowerCase())) {
            regError.textContent = '❌ Этот логин запрещён для регистрации!';
            return;
          }

          const blockedUsers = JSON.parse(localStorage.getItem('vinkBlockedUsers') || '[]');
          if (blockedUsers.includes(login)) {
            regError.textContent = '❌ Этот пользователь заблокирован!';
            return;
          }

          const users = JSON.parse(localStorage.getItem('vinkUsers') || '{}');
          if (users[login]) { regError.textContent = '❌ Пользователь с таким логином уже существует!'; return; }

          users[login] = password;
          localStorage.setItem('vinkUsers', JSON.stringify(users));

          regSuccess.textContent = '✅ Регистрация успешна! Можете войти.';
          regError.textContent = '';

          setTimeout(() => {
            hideRegisterPage();
            document.getElementById('loginInput').value = login;
            document.getElementById('passwordInput').value = '';
            updateAuthUI();
          }, 1500);
        });
      }

      if (captchaInput) {
        captchaInput.addEventListener('keypress', function(e) { if (e.key === 'Enter') regSubmitBtn.click(); });
      }

      // ============================================================
      // 8. ВХОД / ВЫХОД
      // ============================================================
      const loginInput = document.getElementById('loginInput');
      const passwordInput = document.getElementById('passwordInput');
      const loginBtn = document.getElementById('loginBtn');
      const logoutBtn = document.getElementById('logoutBtn');
      const authStatus = document.getElementById('authStatus');
      const welcomeBanner = document.getElementById('welcomeBanner');
      const welcomeUser = document.getElementById('welcomeUser');
      const showAdminBtn = document.getElementById('showAdminBtn');

      let loginAttempts = 0;
      let loginBlocked = false;

      function setCurrentUser(username) {
        if (username) localStorage.setItem('vinkCurrentUser', username);
        else localStorage.removeItem('vinkCurrentUser');
        updateAuthUI();
        updateWelcomeBanner();
        updateAdminButton();
        updateReviewForm();
        updateUploadButton();
        renderSeries();
      }

      function isUserBlocked(username) {
        const blocked = JSON.parse(localStorage.getItem('vinkBlockedUsers') || '[]');
        return blocked.includes(username);
      }

      function updateAuthUI() {
        const user = getCurrentUser();
        if (user) authStatus.innerHTML = `<i class="fas fa-user-check" style="color:#6b3;"></i> ${user}`;
        else authStatus.innerHTML = `<i class="fas fa-circle" style="color:#6b3;"></i> Гость`;
      }

      function updateWelcomeBanner() {
        const user = getCurrentUser();
        if (user) { welcomeBanner.classList.add('active'); welcomeUser.textContent = user; }
        else { welcomeBanner.classList.remove('active'); welcomeUser.textContent = 'Гость'; }
      }

      function updateAdminButton() {
        showAdminBtn.style.display = isAdmin() ? 'inline-flex' : 'none';
      }

      function updateReviewForm() {
        const user = getCurrentUser();
        const form = document.getElementById('reviewForm');
        if (!user) {
          form.innerHTML = `
            <p style="color:#884444; text-align:center; padding:20px;">
              <i class="fas fa-lock"></i> Войдите, чтобы оставить отзыв
            </p>
          `;
        } else {
          form.innerHTML = `
            <div class="stars-select" id="starsSelect">
              <span class="star" data-value="1">☆</span>
              <span class="star" data-value="2">☆</span>
              <span class="star" data-value="3">☆</span>
              <span class="star" data-value="4">☆</span>
              <span class="star" data-value="5">☆</span>
            </div>
            <textarea id="reviewText" placeholder="Ваш отзыв (спойлеры скрываются автоматически)..."></textarea>
            <div class="review-actions">
              <button class="auth-btn" id="submitReviewBtn"><i class="fas fa-pen"></i> Оставить отзыв</button>
            </div>
          `;
          initReviewStars();
          const newSubmitBtn = document.getElementById('submitReviewBtn');
          if (newSubmitBtn) newSubmitBtn.addEventListener('click', submitReview);
        }
      }

      function loginUser() {
        if (isBlocked) { alert('Доступ временно заблокирован.'); return; }
        if (loginBlocked) { alert('⛔ Слишком много неудачных попыток. Подождите 30 сек.'); return; }
        if (!throttleAction()) { alert('⏳ Слишком быстро! Подождите секунду.'); return; }

        const login = loginInput.value.trim();
        const password = passwordInput.value.trim();

        if (!login || !password) { alert('Введите логин и пароль!'); return; }

        if (isUserBlocked(login)) {
          alert('🚫 Этот пользователь заблокирован администратором!');
          return;
        }

        if (login === ADMIN_LOGIN && password === ADMIN_PASSWORD) {
          loginAttempts = 0;
          setCurrentUser(ADMIN_LOGIN);
          alert('👑 Добро пожаловать, Администратор!');
          updateAuthUI();
          updateWelcomeBanner();
          updateAdminButton();
          updateReviewForm();
          updateUploadButton();
          renderSeries();
          return;
        }

        const users = JSON.parse(localStorage.getItem('vinkUsers') || '{}');
        if (users[login] && users[login] === password) {
          loginAttempts = 0;
          setCurrentUser(login);
          alert('🩸 Добро пожаловать в Friday, ' + login + '!');
          updateAuthUI();
          updateWelcomeBanner();
          updateAdminButton();
          updateReviewForm();
          updateUploadButton();
          renderSeries();
        } else {
          loginAttempts++;
          if (loginAttempts >= 3) {
            loginBlocked = true;
            alert('⛔ Слишком много неудачных попыток. Доступ заблокирован на 30 секунд.');
            setTimeout(() => { loginBlocked = false; loginAttempts = 0; }, 30000);
          } else {
            alert('❌ Неверный логин или пароль! Осталось попыток: ' + (3 - loginAttempts));
          }
        }
      }

      function logoutUser() {
        if (getCurrentUser()) {
          setCurrentUser(null);
          alert('Вы вышли из аккаунта.');
          updateAuthUI();
          updateWelcomeBanner();
          updateAdminButton();
          updateReviewForm();
          updateUploadButton();
          renderSeries();
        } else {
          alert('Вы уже не в системе.');
        }
      }

      if (loginBtn) loginBtn.addEventListener('click', loginUser);
      if (logoutBtn) logoutBtn.addEventListener('click', logoutUser);
      if (passwordInput) passwordInput.addEventListener('keypress', function(e) { if (e.key === 'Enter') loginUser(); });
      if (loginInput) loginInput.addEventListener('keypress', function(e) { if (e.key === 'Enter') loginUser(); });

      // ============================================================
      // 9. ОПИСАНИЕ
      // ============================================================
      const descriptionModal = document.getElementById('descriptionModal');
      const showDescriptionBtn = document.getElementById('showDescriptionBtn');
      const closeDescription = document.getElementById('closeDescription');

      if (showDescriptionBtn) {
        showDescriptionBtn.addEventListener('click', () => descriptionModal.classList.add('active'));
      }
      if (closeDescription) closeDescription.addEventListener('click', () => descriptionModal.classList.remove('active'));
      descriptionModal.addEventListener('click', function(e) { if (e.target === descriptionModal) descriptionModal.classList.remove('active'); });

      // ============================================================
      // 10. ОТЗЫВЫ
      // ============================================================
      function initReviewStars() {
        const stars = document.querySelectorAll('.star');
        window._selectedRating = 0;

        stars.forEach(star => {
          star.addEventListener('click', function() {
            window._selectedRating = parseInt(this.dataset.value);
            stars.forEach(s => s.classList.remove('active'));
            for (let i = 0; i < window._selectedRating; i++) {
              stars[i].classList.add('active');
              stars[i].textContent = '★';
            }
            for (let i = window._selectedRating; i < stars.length; i++) {
              stars[i].textContent = '☆';
            }
          });

          star.addEventListener('mouseenter', function() {
            const val = parseInt(this.dataset.value);
            stars.forEach(s => s.style.color = '#555');
            for (let i = 0; i < val; i++) stars[i].style.color = '#ccaa33';
          });

          star.addEventListener('mouseleave', function() {
            stars.forEach(s => s.style.color = '#555');
            stars.forEach(s => { if (s.classList.contains('active')) s.style.color = '#ccaa33'; });
          });
        });
      }

      function submitReview() {
        const user = getCurrentUser();
        if (!user) { alert('Войдите, чтобы оставить отзыв!'); return; }
        if (isUserBlocked(user)) { alert('Вы заблокированы!'); return; }

        const text = document.getElementById('reviewText').value.trim();
        const rating = window._selectedRating || 0;

        if (!text) { alert('Напишите отзыв!'); return; }
        if (rating === 0) { alert('Поставьте оценку звёздами!'); return; }

        const spoilerWords = ['конец', 'финал', 'смерть', 'убийство', 'маньяк', 'джейсон', 'воскрешение', 'спойлер'];
        const hasSpoiler = spoilerWords.some(word => text.toLowerCase().includes(word));

        const review = {
          id: Date.now(),
          user: user,
          rating: rating,
          text: text,
          date: new Date().toLocaleDateString('ru-RU'),
          hasSpoiler: hasSpoiler,
          answer: null
        };

        const reviews = JSON.parse(localStorage.getItem('vinkReviews') || '[]');
        reviews.push(review);
        localStorage.setItem('vinkReviews', JSON.stringify(reviews));

        document.getElementById('reviewText').value = '';
        window._selectedRating = 0;
        document.querySelectorAll('.star').forEach(s => { s.classList.remove('active'); s.textContent = '☆'; });

        renderReviews();
        updateAdminStats();
      }

      function renderReviews() {
        const container = document.getElementById('reviewsList');
        const reviews = JSON.parse(localStorage.getItem('vinkReviews') || '[]');
        const isAdminUser = isAdmin();

        if (reviews.length === 0) {
          container.innerHTML = `
            <p style="color:#664444; text-align:center; padding:30px;">
              <i class="fas fa-comment-slash"></i> Пока нет отзывов. Будьте первым!
            </p>
          `;
          return;
        }

        reviews.sort((a, b) => b.id - a.id);

        let html = '';
        reviews.forEach((review) => {
          const stars = '★'.repeat(review.rating) + '☆'.repeat(5 - review.rating);
          const isSpoiler = review.hasSpoiler;

          html += `
            <div class="review-item" data-id="${review.id}">
              <div class="review-header">
                <span class="review-user"><i class="fas fa-user"></i> ${review.user}</span>
                <span class="review-stars">${stars}</span>
                <span class="review-date">${review.date}</span>
              </div>
              <div class="review-text ${isSpoiler ? 'spoiler' : ''}" onclick="this.classList.toggle('revealed')">
                ${review.text}
              </div>
              ${isSpoiler ? `<div class="spoiler-hint">⚠️ Содержит спойлеры. Нажмите, чтобы показать.</div>` : ''}
              ${review.answer ? `
                <div class="review-answer">
                  <span class="admin-label">👑 Админ:</span> ${review.answer}
                </div>
              ` : ''}
              ${isAdminUser ? `
                <div class="review-actions-small">
                  <button class="answer-btn" onclick="toggleAnswerForm(${review.id})">
                    <i class="fas fa-reply"></i> Ответить
                  </button>
                  ${!isSpoiler ? `<button onclick="markAsSpoiler(${review.id})"><i class="fas fa-eye-slash"></i> Спойлер</button>` : ''}
                  <button onclick="deleteReview(${review.id})" style="border-color:#cc3333; color:#cc3333;">
                    <i class="fas fa-trash"></i> Удалить
                  </button>
                </div>
                <div class="review-answer-form" id="answerForm_${review.id}">
                  <textarea placeholder="Ответ администратора..." id="answerText_${review.id}"></textarea>
                  <div class="answer-actions">
                    <button onclick="submitAnswer(${review.id})"><i class="fas fa-check"></i> Отправить</button>
                    <button onclick="toggleAnswerForm(${review.id})">Отмена</button>
                  </div>
                </div>
              ` : ''}
            </div>
          `;
        });

        container.innerHTML = html;
        updateReviewStats(reviews);
      }

      function updateReviewStats(reviews) {
        if (!reviews) reviews = JSON.parse(localStorage.getItem('vinkReviews') || '[]');
        const count = reviews.length;
        const totalRating = reviews.reduce((sum, r) => sum + r.rating, 0);
        const avg = count > 0 ? (totalRating / count) : 0;

        document.getElementById('reviewsCount').textContent = count + ' отзывов';
        document.getElementById('avgRating').textContent = avg.toFixed(1);

        const fullStars = Math.round(avg);
        let starsDisplay = '';
        for (let i = 0; i < 5; i++) {
          starsDisplay += i < fullStars ? '★' : '☆';
        }
        document.getElementById('starsDisplay').textContent = starsDisplay;
      }

      window.toggleAnswerForm = function(reviewId) {
        const form = document.getElementById('answerForm_' + reviewId);
        if (form) form.classList.toggle('active');
      };

      window.submitAnswer = function(reviewId) {
        const textarea = document.getElementById('answerText_' + reviewId);
        const text = textarea.value.trim();
        if (!text) { alert('Введите ответ!'); return; }

        const reviews = JSON.parse(localStorage.getItem('vinkReviews') || '[]');
        const review = reviews.find(r => r.id === reviewId);
        if (review) {
          review.answer = text;
          localStorage.setItem('vinkReviews', JSON.stringify(reviews));
          renderReviews();
          updateAdminStats();
        }
      };

      window.deleteReview = function(reviewId) {
        if (!confirm('Удалить отзыв?')) return;
        let reviews = JSON.parse(localStorage.getItem('vinkReviews') || '[]');
        reviews = reviews.filter(r => r.id !== reviewId);
        localStorage.setItem('vinkReviews', JSON.stringify(reviews));
        renderReviews();
        updateAdminStats();
      };

      window.markAsSpoiler = function(reviewId) {
        const reviews = JSON.parse(localStorage.getItem('vinkReviews') || '[]');
        const review = reviews.find(r => r.id === reviewId);
        if (review) {
          review.hasSpoiler = true;
          localStorage.setItem('vinkReviews', JSON.stringify(reviews));
          renderReviews();
        }
      };

      // ============================================================
      // 11. АДМИН ПАНЕЛЬ
      // ============================================================
      const adminModal = document.getElementById('adminModal');
      const showAdmin = document.getElementById('showAdminBtn');
      const closeAdmin = document.getElementById('closeAdmin');

      function updateAdminStats() {
        const users = JSON.parse(localStorage.getItem('vinkUsers') || '{}');
        const blocked = JSON.parse(localStorage.getItem('vinkBlockedUsers') || '[]');
        const reviews = JSON.parse(localStorage.getItem('vinkReviews') || '[]');

        const userCount = Object.keys(users).length;
        document.getElementById('adminUsersCount').textContent = userCount;
        document.getElementById('adminBlockedCount').textContent = blocked.length;
        document.getElementById('adminReviewsCount').textContent = reviews.length;

        const totalRating = reviews.reduce((sum, r) => sum + r.rating, 0);
        const avg = reviews.length > 0 ? (totalRating / reviews.length) : 0;
        document.getElementById('adminAvgRating').textContent = avg.toFixed(1);

        let html = '';
        for (let login in users) {
          const isAdminUser = login === ADMIN_LOGIN;
          const isBlocked = blocked.includes(login);
          html += `
            <div class="list-item">
              <span class="name"><i class="fas fa-user"></i> ${login}</span>
              <span class="status ${isBlocked ? 'blocked' : ''}">
                ${isAdminUser ? '👑 Администратор' : (isBlocked ? '🚫 Заблокирован' : '✅ Активен')}
              </span>
              ${!isAdminUser ? `
                <button class="block-btn ${isBlocked ? 'unblock' : ''}" onclick="toggleBlockUser('${login}')">
                  ${isBlocked ? '🔓 Разблокировать' : '🔒 Заблокировать'}
                </button>
              ` : ''}
            </div>
          `;
        }
        if (!html) html = '<div class="list-item"><span class="name" style="color:#884444;">Нет пользователей</span></div>';
        document.getElementById('adminUserList').innerHTML = html;
      }

      window.toggleBlockUser = function(username) {
        if (username === ADMIN_LOGIN) { alert('Нельзя заблокировать администратора!'); return; }
        let blocked = JSON.parse(localStorage.getItem('vinkBlockedUsers') || '[]');
        const index = blocked.indexOf(username);
        if (index > -1) {
          blocked.splice(index, 1);
          alert('🔓 Пользователь ' + username + ' разблокирован.');
        } else {
          blocked.push(username);
          alert('🔒 Пользователь ' + username + ' заблокирован.');
        }
        localStorage.setItem('vinkBlockedUsers', JSON.stringify(blocked));
        updateAdminStats();
      };

      if (showAdmin) {
        showAdmin.addEventListener('click', function() {
          if (!isAdmin()) { alert('Доступ запрещён! Только для администратора.'); return; }
          updateAdminStats();
          adminModal.classList.add('active');
        });
      }

      if (closeAdmin) closeAdmin.addEventListener('click', () => adminModal.classList.remove('active'));
      adminModal.addEventListener('click', function(e) { if (e.target === adminModal) adminModal.classList.remove('active'); });

      if (document.getElementById('adminClearUsers')) {
        document.getElementById('adminClearUsers').addEventListener('click', function() {
          if (confirm('⚠️ Удалить ВСЕХ пользователей (кроме Admin)?')) {
            const users = JSON.parse(localStorage.getItem('vinkUsers') || '{}');
            const newUsers = {};
            if (users[ADMIN_LOGIN]) newUsers[ADMIN_LOGIN] = users[ADMIN_LOGIN];
            localStorage.setItem('vinkUsers', JSON.stringify(newUsers));
            localStorage.setItem('vinkBlockedUsers', JSON.stringify([]));
            updateAdminStats();
            alert('✅ Все пользователи (кроме Admin) удалены.');
          }
        });
      }

      if (document.getElementById('adminClearVideos')) {
        document.getElementById('adminClearVideos').addEventListener('click', function() {
          if (confirm('⚠️ Удалить все серии?')) {
            const series = getSeries();
            series.forEach(s => {
              if (s.data && s.data.startsWith('blob:')) URL.revokeObjectURL(s.data);
              if (s.thumbnail && s.thumbnail.startsWith('blob:')) URL.revokeObjectURL(s.thumbnail);
            });
            localStorage.removeItem('vinkSeries');
            localStorage.removeItem('vinkCurrentSeriesId');
            videoPlayer.src = '';
            videoPlayer.load();
            videoStatus.innerHTML = '<i class="fas fa-video"></i> Нет видео';
            document.getElementById('videoThumbnail').classList.remove('active');
            renderSeries();
            updateAdminStats();
            alert('✅ Все серии удалены.');
          }
        });
      }

      if (document.getElementById('adminRefreshStats')) {
        document.getElementById('adminRefreshStats').addEventListener('click', function() {
          updateAdminStats();
          alert('✅ Статистика обновлена.');
        });
      }

      // ============================================================
      // 12. XSS ЗАЩИТА
      // ============================================================
      function sanitizeInput(str) {
        const element = document.createElement('div');
        element.textContent = str;
        return element.innerHTML;
      }

      document.querySelectorAll('input').forEach(input => {
        input.addEventListener('blur', function() {
          if (this.value) this.value = sanitizeInput(this.value);
        });
      });

      // ============================================================
      // 13. ИНИЦИАЛИЗАЦИЯ
      // ============================================================
      const users = JSON.parse(localStorage.getItem('vinkUsers') || '{}');
      if (!users[ADMIN_LOGIN]) {
        users[ADMIN_LOGIN] = ADMIN_PASSWORD;
        localStorage.setItem('vinkUsers', JSON.stringify(users));
        console.log('👑 Аккаунт Admin создан');
      }

      updateAuthUI();
      updateWelcomeBanner();
      updateAdminButton();
      updateUploadButton();
      renderSeries();
      
      renderReviews();
      updateReviewForm();
      setTimeout(() => {
        const submitBtn = document.getElementById('submitReviewBtn');
        if (submitBtn) submitBtn.addEventListener('click', submitReview);
        initReviewStars();
      }, 100);

      const currentId = localStorage.getItem('vinkCurrentSeriesId');
      if (currentId) {
        const series = getSeries();
        const item = series.find(s => s.id === parseInt(currentId));
        if (item && item.data) {
          videoPlayer.src = item.data;
          videoPlayer.load();
          if (item.thumbnail && item.thumbnail.startsWith('blob:')) {
            thumbnailImg.src = item.thumbnail;
            videoThumbnail.classList.add('active');
          }
          videoStatus.innerHTML = `<i class="fas fa-play" style="color:#b33;"></i> ${item.name}`;
        }
      }

      console.log('🩸 ВИНК | Пятница 13-я активирована');
      console.log('👑 Admin: ' + ADMIN_LOGIN + ' / ' + ADMIN_PASSWORD);
      console.log('📁 Лимит загрузки: 10 ГБ');
      console.log('📹 Обложки видео: поддерживаются');
    })();
  </script>
</body>
</html>
