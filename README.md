<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>XV de Sofi</title>
  <style>
    body {
      margin: 0;
      font-family: 'Segoe UI', sans-serif;
      background: linear-gradient(to bottom, #fff, #ffe6f0);
      color: #333;
      scroll-behavior: smooth;
    }
    .section {
      padding: 80px 20px;
      text-align: center;
    }
    h1 {
      font-size: 2.5rem;
      color: #d63384;
    }
    .countdown-digital {
      font-family: 'Courier New', monospace;
      font-size: 3rem;
      background-color: #111;
      color: #0ff;
      padding: 20px;
      border-radius: 10px;
      display: inline-block;
      margin-top: 20px;
    }
    .countdown-estetico {
      display: flex;
      justify-content: center;
      gap: 30px;
      font-size: 1.5rem;
      margin-top: 20px;
    }
    .circle {
      background: #f8f0ff;
      border: 2px solid #ccc;
      border-radius: 50%;
      width: 80px;
      height: 80px;
      display: flex;
      align-items: center;
      justify-content: center;
      flex-direction: column;
    }
    .info-box {
      background: white;
      border-radius: 15px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
      max-width: 600px;
      margin: 30px auto;
      padding: 20px;
    }
    .mapa {
      margin-top: 20px;
    }
    .boton {
      background: #d63384;
      color: white;
      padding: 12px 25px;
      border: none;
      border-radius: 25px;
      font-size: 1rem;
      cursor: pointer;
      margin-top: 20px;
      transition: background 0.3s;
    }
    .boton:hover {
      background: #c2186b;
    }
    .galeria {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
      justify-content: center;
      margin-top: 20px;
    }
    .galeria img {
      width: 150px;
      height: 150px;
      object-fit: cover;
      border-radius: 10px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.2);
    }
  </style>
</head>
<body>
  <audio autoplay loop controls style="position: fixed; top: 10px; left: 10px; z-index: 1000;">
    <source src="musica.mp3" type="audio/mpeg">
    Tu navegador no soporta audio HTML5.
  </audio>

  <section class="section">
    <h1>¡Faltan solo...</h1>
    <div id="digitalCountdown" class="countdown-digital"></div>
    <br><br>
    <div id="esteticoCountdown" class="countdown-estetico"></div>
  </section>

  <section class="section">
    <div class="info-box">
      <h2>Detalles del Evento</h2>
      <p><strong>Fecha:</strong> 20 de septiembre de 2025</p>
      <p><strong>Hora:</strong> 20:00 hs</p>
      <p><strong>Lugar:</strong> Salón Flor de Loto, Calle Falsa 123</p>
      <div class="mapa">
        <iframe src="https://www.google.com/maps/embed?pb=!1m18!..." width="100%" height="250" style="border:0;" allowfullscreen="" loading="lazy"></iframe>
      </div>
      <a href="https://wa.me/5491234567890?text=Confirmo%20mi%20asistencia%20al%20XV%20de%20Sofi" target="_blank">
        <button class="boton">Confirmar Asistencia</button>
      </a>
    </div>
  </section>

  <section class="section">
    <div class="info-box">
      <h2>¡Bienvenidos!</h2>
      <p>Nos alegra muchísimo que nos acompañen en un día tan especial para Sofi. Este evento está lleno de amor, magia y recuerdos que quedarán para siempre.</p>
    </div>
  </section>

  <section class="section">
    <div class="info-box">
      <h2>Algunos Momentos</h2>
      <div class="galeria">
        <img src="foto1.jpg" alt="Foto 1">
        <img src="foto2.jpg" alt="Foto 2">
        <img src="foto3.jpg" alt="Foto 3">
        <img src="foto4.jpg" alt="Foto 4">
      </div>
    </div>
  </section>

  <script>
    const targetDate = new Date("September 20, 2025 20:00:00").getTime();

    function updateCountdowns() {
      const now = new Date().getTime();
      const distance = targetDate - now;

      const days = Math.floor(distance / (1000 * 60 * 60 * 24));
      const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
      const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
      const seconds = Math.floor((distance % (1000 * 60)) / 1000);

      document.getElementById("digitalCountdown").innerText = `${days}d ${hours}h ${minutes}m ${seconds}s`;

      document.getElementById("esteticoCountdown").innerHTML = `
        <div class="circle"><div>${days}</div><small>días</small></div>
        <div class="circle"><div>${hours}</div><small>horas</small></div>
        <div class="circle"><div>${minutes}</div><small>min</small></div>
        <div class="circle"><div>${seconds}</div><small>seg</small></div>
      `;
    }

    setInterval(updateCountdowns, 1000);
  </script>
</body>
</html>
