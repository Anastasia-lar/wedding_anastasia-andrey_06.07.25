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

