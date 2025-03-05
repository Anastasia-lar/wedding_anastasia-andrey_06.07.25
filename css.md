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

.tiny-heart {
    width: 17px !important;
    height: 17px !important;
    margin: 10px auto; /* Уменьшенные отступы */
    opacity: 0.5;
    display: block;
    transition: all 0.3s;
}

/* Мини-анимация при наведении */
.tiny-heart:hover {
    transform: scale(1.3);
    opacity: 0.8;
}

/* Для мобильных */
@media (max-width: 600px) {
    .tiny-heart {
        width: 6px;
        height: 6px;
        margin: 3px auto;
    }
}
