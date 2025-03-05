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
/* Анимация сердечек - улучшенная версия */
.hearts-container {
    position: absolute;
    width: 100%;
    height: 100%;
    pointer-events: none;
    z-index: 1;
    overflow: visible;
}

.floating-heart {
    position: absolute;
    opacity: 0.3; /* Увеличена прозрачность */
    animation: float 8s infinite ease-in-out; /* Изменен тип анимации */
    width: 60px; /* Увеличен базовый размер */
    filter: drop-shadow(0 0 5px rgba(255,50,50,0.3)); /* Добавлена тень */
    transition: 0.3s;
}

/* Увеличены размеры и добавлены вариации */
.floating-heart:nth-child(1) { 
    animation-delay: 0s; 
    width: 55px; 
    animation-duration: 7s;
}
.floating-heart:nth-child(2) { 
    animation-delay: 1.5s; 
    width: 70px; 
    animation-duration: 9s;
}
.floating-heart:nth-child(3) { 
    animation-delay: 3s; 
    width: 50px; 
    animation-duration: 6s;
}
.floating-heart:nth-child(4) { 
    animation-delay: 4.5s; 
    width: 65px; 
    animation-duration: 8s;
}

/* Новая анимация с вращением и изменением прозрачности */
@keyframes float {
    0% {
        transform: translateY(0) rotate(-15deg) scale(0.9);
        opacity: 0;
    }
    20% {
        opacity: 0.4;
    }
    50% {
        transform: translateY(-100px) rotate(15deg) scale(1.1);
        opacity: 0.5;
    }
    80% {
        opacity: 0.3;
    }
    100% {
        transform: translateY(-200px) rotate(30deg) scale(0.8);
        opacity: 0;
    }
}

/* Позиции для мобильных устройств */
@media (max-width: 600px) {
    .floating-heart { 
        width: 40px !important; /* Уменьшенный размер для мобилок */
        opacity: 0.25;
    }
    .hearts-container {
        display: block; /* Показываем на мобильных */
    }
}

/* Новые позиции с большим разбросом */
.heart-pos-1 { left: 5%; top: 10%; animation-name: float-left; }
.heart-pos-2 { right: 5%; top: 15%; animation-name: float-right; }
.heart-pos-3 { left: 20%; bottom: 15%; animation-name: float-left; }
.heart-pos-4 { right: 25%; bottom: 20%; animation-name: float-right; }

/* Разные направления движения */
@keyframes float-left {
    0% { transform: translateX(0) translateY(0) rotate(-15deg); }
    100% { transform: translateX(-50px) translateY(-200px) rotate(25deg); }
}

@keyframes float-right {
    0% { transform: translateX(0) translateY(0) rotate(15deg); }
    100% { transform: translateX(50px) translateY(-200px) rotate(-25deg); }
}
