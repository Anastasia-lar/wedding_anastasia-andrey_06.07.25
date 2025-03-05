<script>
  document.getElementById('weddingForm').addEventListener('submit', function(e) {
    e.preventDefault();
    fetch(this.action, {
      method: 'POST',
      body: new FormData(this),
      headers: { 'Accept': 'application/json' }
    })
    .then(response => alert('Спасибо! Ваш ответ сохранён.'))
    .catch(error => alert('Ошибка! Попробуйте ещё раз.'));
  });
</script>

.hearts-container {
    position: fixed; /* Изменено с absolute на fixed */
    width: 100vw;
    height: 100vh;
    pointer-events: none;
    z-index: 9999; /* Увеличено значение */
    overflow: visible;
    top: 0;
    left: 0;
}

.floating-heart {
    position: absolute;
    opacity: 0.4; /* Увеличена прозрачность */
    animation: float 8s infinite ease-in-out;
    width: 100px; /* Увеличен размер */
    filter: 
        drop-shadow(0 0 8px rgba(255,80,80,0.4)) 
        hue-rotate(15deg); /* Добавлен цветовой эффект */
}

/* Увеличено количество сердечек и их вариации */
.floating-heart:nth-child(1) { width: 90px; animation-duration: 9s; }
.floating-heart:nth-child(2) { width: 110px; animation-duration: 11s; }
.floating-heart:nth-child(3) { width: 85px; animation-duration: 8s; }
.floating-heart:nth-child(4) { width: 95px; animation-duration: 10s; }
.floating-heart:nth-child(5) { width: 105px; animation-duration: 12s; }
.floating-heart:nth-child(6) { width: 80px; animation-duration: 7s; }
.floating-heart:nth-child(7) { width: 100px; animation-duration: 9s; }
.floating-heart:nth-child(8) { width: 90px; animation-duration: 10s; }

/* Новые позиции */
.heart-pos-1 { left: 2%; top: 5%; }
.heart-pos-2 { right: 3%; top: 10%; }
.heart-pos-3 { left: 15%; bottom: 5%; }
.heart-pos-4 { right: 18%; bottom: 15%; }
.heart-pos-5 { left: 25%; top: 20%; }
.heart-pos-6 { right: 30%; top: 25%; }
.heart-pos-7 { left: 40%; bottom: 10%; }
.heart-pos-8 { right: 5%; bottom: 5%; }

@media (max-width: 600px) {
    .floating-heart { 
        width: 60px !important; 
        opacity: 0.3;
    }
}

/* Стили для разделительных иконок */
.divider-icon {
    width: 10px;
    height: 10px;
    margin: 5px auto;
    display: block;
    opacity: 0.7;
}

.wish-item {
    margin: 30px 0;
    padding: 15px 0;
}

.wish-item p {
    font-size: 1rem;
    line-height: 1.5;
    margin: 0 auto;
    max-width: 400px;
}

@media (max-width: 600px) {
    .divider-icon {
        width: 7px;
        height: 7px;
        margin: 3px auto;
    }
    
    .wish-item {
        margin: 25px 0;
    }
    
    .wish-item p {
        font-size: 0.9rem;
        padding: 0 15px;
    }
}
.dress-code-container {
    background: white;
    padding: 30px;
    border-radius: 20px;
    box-shadow: 0 4px 20px rgba(0,0,0,0.08);
    max-width: 800px;
    margin: 20px auto;
}

.dress-code-description {
    color: #5a2a3a;
    margin: 0 auto 30px;
    line-height: 1.6;
    max-width: 600px;
}

.color-palette-wrapper {
    display: grid;
    gap: 30px;
}

.gender-section {
    text-align: center;
}

.gender-title {
    font-family: 'Montserrat', sans-serif;
    font-weight: 500;
    margin-bottom: 20px;
    position: relative;
    padding-bottom: 10px;
}

.gender-title::after {
    content: '';
    position: absolute;
    bottom: 0;
    left: 50%;
    transform: translateX(-50%);
    width: 40px;
    height: 2px;
}

.gender-title.female::after { background: #ff8095; }
.gender-title.male::after { background: #6c8cff; }

.color-palette {
    display: flex;
    justify-content: center;
    gap: 20px;
    flex-wrap: wrap;
}

.color-box {
    width: 130px;
    height: 130px;
    border-radius: 18px;
    position: relative;
    overflow: hidden;
    transition: transform 0.3s;
    box-shadow: 0 4px 15px rgba(0,0,0,0.1);
}

.color-box:hover {
    transform: translateY(-5px);
}

.color-label {
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    background: rgba(255,255,255,0.9);
    padding: 8px;
    font-size: 0.9em;
    color: #333;
}

@media (max-width: 600px) {
    .dress-code-container {
        padding: 20px;
        margin: 20px 15px;
    }
    
    .color-box {
        width: 100px;
        height: 100px;
    }
    
    .color-label {
        font-size: 0.8em;
        padding: 5px;
    }
}
