
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#090909">
<title>Para Aleja 🖤</title>

<style>
@import url('https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,400;0,500;0,600;1,400;1,500&family=Montserrat:wght@300;400;500;600&display=swap');

:root {
  --red: #c51e38;
  --dark-red: #731326;
  --black: #090909;
  --white: #f5eeee;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  background: var(--black);
  color: var(--white);
  font-family: 'Montserrat', sans-serif;
  overflow-x: hidden;
}

button {
  font-family: inherit;
  cursor: pointer;
}

#particles {
  position: fixed;
  inset: 0;
  pointer-events: none;
  overflow: hidden;
  z-index: 0;
}

.particle {
  position: absolute;
  bottom: -20px;
  color: #c51e38;
  opacity: 0;
  animation: rise linear infinite;
}

@keyframes rise {
  0% { transform: translateY(0) rotate(0); opacity: 0; }
  15% { opacity: .65; }
  85% { opacity: .3; }
  100% { transform: translateY(-110vh) rotate(300deg); opacity: 0; }
}

.screen {
  min-height: 100vh;
  display: none;
  position: relative;
  z-index: 1;
  padding: 35px 20px;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  text-align: center;
  animation: appear 1s ease;
}

.screen.active {
  display: flex;
}

@keyframes appear {
  from { opacity: 0; transform: translateY(12px); }
  to { opacity: 1; transform: translateY(0); }
}

.eyebrow {
  font-size: 10px;
  letter-spacing: 5px;
  text-transform: uppercase;
  color: #c45a6b;
  margin-bottom: 25px;
}

h1, h2, .serif {
  font-family: 'Cormorant Garamond', serif;
  font-weight: 400;
}

h1 {
  font-size: clamp(55px, 13vw, 100px);
  line-height: 1;
  color: #fff;
}

h1 span {
  color: var(--red);
  font-style: italic;
}

.subtitle {
  font-size: 12px;
  color: #a9a0a0;
  letter-spacing: 2px;
  margin-top: 25px;
  line-height: 2;
}

.line {
  width: 55px;
  height: 1px;
  background: var(--red);
  margin: 28px auto;
}

.btn {
  background: linear-gradient(120deg, #a91630, #5e1020);
  color: white;
  border: 1px solid #bd3b50;
  border-radius: 50px;
  padding: 15px 30px;
  font-size: 11px;
  letter-spacing: 2px;
  text-transform: uppercase;
  transition: .3s;
  box-shadow: 0 0 25px #a9163033;
}

.btn:hover {
  transform: translateY(-3px);
  box-shadow: 0 0 35px #c51e3866;
}

.btn.secondary {
  background: transparent;
  border-color: #55303a;
  color: #d6aeb6;
  box-shadow: none;
}

.heart {
  font-size: 38px;
  color: var(--red);
  animation: heartbeat 1.5s infinite;
  margin-bottom: 25px;
}

@keyframes heartbeat {
  0%,100% { transform: scale(1); }
  50% { transform: scale(1.15); }
}

/* SOBRE */

.envelope {
  width: min(310px, 85vw);
  height: 190px;
  background: #321019;
  position: relative;
  margin: 45px auto;
  border: 1px solid #873044;
  border-radius: 4px;
  box-shadow: 0 15px 55px #000;
  cursor: pointer;
  transition: .5s;
}

.envelope:before {
  content: "";
  position: absolute;
  inset: 0;
  background: linear-gradient(145deg, transparent 49%, #581326 50%);
  z-index: 2;
  clip-path: polygon(0 0, 100% 0, 50% 65%);
}

.envelope:after {
  content: "";
  position: absolute;
  inset: 0;
  background: linear-gradient(35deg, #260c13 50%, transparent 51%);
  z-index: 1;
  clip-path: polygon(0 100%, 0 0, 50% 65%, 100% 0, 100% 100%);
}

.seal {
  position: absolute;
  z-index: 3;
  top: 55%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 45px;
  height: 45px;
  background: #a61934;
  border-radius: 50%;
  display: grid;
  place-items: center;
  box-shadow: 0 0 20px #c51e3855;
  font-size: 20px;
}

.envelope.open {
  transform: translateY(10px);
  opacity: .3;
}

/* CARTA */

.letter {
  max-width: 570px;
  width: 100%;
  background: linear-gradient(145deg, #151112, #0d0c0d);
  border: 1px solid #49202a;
  padding: clamp(25px, 6vw, 48px);
  text-align: left;
  box-shadow: 0 20px 70px #000;
  position: relative;
}

.letter:before {
  content: "✦";
  position: absolute;
  right: 22px;
  top: 18px;
  color: #9e354b;
}

.letter h2 {
  font-size: 38px;
  color: #e8c5ca;
  margin-bottom: 25px;
}

.letter p {
  font-size: 13px;
  color: #c4b9bb;
  line-height: 2.2;
  margin-bottom: 17px;
  font-weight: 300;
}

.letter .signature {
  font-family: 'Cormorant Garamond', serif;
  font-size: 27px;
  font-style: italic;
  color: #d85a71;
  margin-top: 25px;
}

.section-title {
  font-size: clamp(38px, 9vw, 55px);
  margin-bottom: 20px;
}

.message-grid {
  width: min(500px, 100%);
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 12px;
  margin: 25px auto;
}

.message-card {
  min-height: 110px;
  background: #151012;
  border: 1px solid #44202a;
  padding: 18px 10px;
  color: #d7c4c8;
  font-family: 'Cormorant Garamond', serif;
  font-size: 19px;
  transition: .3s;
  border-radius: 5px;
}

.message-card:hover {
  border-color: #b72c47;
  transform: translateY(-4px);
  background: #211016;
}

.message-card span {
  display: block;
  font-family: 'Montserrat', sans-serif;
  font-size: 9px;
  letter-spacing: 2px;
  color: #b84b61;
  margin-bottom: 12px;
}

.photo-frame {
  width: min(280px, 80vw);
  height: 330px;
  border: 1px solid #9a3549;
  padding: 9px;
  margin: 25px auto;
  background: #171012;
  box-shadow: 0 0 40px #9c19352b;
}

.photo-frame img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
}

.photo-placeholder {
  display: none;
  height: 100%;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  color: #b88a93;
  font-family: 'Cormorant Garamond', serif;
  font-size: 23px;
  gap: 15px;
}

.final-text {
  font-family: 'Cormorant Garamond', serif;
  font-size: clamp(28px, 7vw, 43px);
  line-height: 1.5;
  color: #ead9dc;
  max-width: 600px;
}

.small {
  font-size: 11px;
  color: #8d8184;
  margin-top: 22px;
  line-height: 2;
}

footer {
  position: relative;
  z-index: 1;
  text-align: center;
  padding: 20px;
  font-size: 9px;
  color: #62565a;
  letter-spacing: 3px;
}

</style>
</head>

<body>

<div id="particles"></div>

<!-- PANTALLA 1 -->
<section class="screen active" id="s1">
  <div class="eyebrow">Una pequeña sorpresa para ti</div>
  <div class="heart">♥</div>
  <h1>Hola,<br><span>Aleja.</span></h1>
  <div class="line"></div>
  <p class="subtitle">
    Hay cosas que a veces no sabemos expresar<br>
    en el momento indicado...
  </p>
  <br><br>
  <button class="btn" onclick="go(2)">Tengo algo que decirte</button>
  <p class="small">Hecho con cariño, especialmente para ti.</p>
</section>

<!-- PANTALLA 2 -->
<section class="screen" id="s2">
  <div class="eyebrow">Un pequeño detalle</div>
  <h2 class="section-title">Antes de continuar...</h2>
  <p class="subtitle">Preparé algo que me gustaría que leyeras.</p>
  <div class="envelope" id="envelope" onclick="openLetter()">
    <div class="seal">♥</div>
  </div>
  <p class="small">Toca el sobre para abrirlo</p>
</section>

<!-- PANTALLA 3 -->
<section class="screen" id="s3">
  <div class="eyebrow">Unas palabras sinceras</div>
  <div class="letter">
    <h2>Para Aleja...</h2>

    <p>
      Primero que todo, quiero pedirte disculpas por lo que pasó.
      Sé que tuvimos una pequeña discusión y reconozco que eliminar
      esos mensajes por ser tan puntilloso no fue la mejor manera
      de reaccionar.
    </p>

    <p>
      Quizás en ese momento me dejé llevar por lo que estaba sintiendo
      y terminé haciendo algo que no te gustó. No quiero justificarlo,
      simplemente reconocer que pude haber actuado mejor.
    </p>

    <p>
      No me gusta que las cosas queden así entre nosotros.
      Valoro mucho nuestras conversaciones, nuestras bromas y esos
      pequeños momentos que hacen especial nuestra amistad.
    </p>

    <p>
      No espero que por leer esto tengas que olvidar lo sucedido
      inmediatamente. Solo quería tomarme un momento para decirte
      que lo siento de corazón.
    </p>

    <p>
      A veces puedo ser un poquito complicado, lo admito jajaja,
      pero eso no significa que no valore a las personas que tengo
      cerca.
    </p>

    <p>
      Espero que podamos dejar atrás este pequeño momento y seguir
      compartiendo cosas bonitas, sin malos ratos.
    </p>

    <div class="signature">Con mucho cariño. ♥</div>
  </div>
  <br>
  <button class="btn" onclick="go(4)">Continuar</button>
</section>

<!-- PANTALLA 4 -->
<section class="screen" id="s4">
  <div class="eyebrow">Unas pequeñas verdades</div>
  <h2 class="section-title">Quiero que sepas...</h2>
  <p class="subtitle">Hay algunas cosas que no quería dejar sin decir.</p>

  <div class="message-grid">
    <button class="message-card" onclick="reveal(this, 'Valoro mucho que formes parte de mis días.')">
      <span>01 · TOCA AQUÍ</span>
      Una razón...
    </button>

    <button class="message-card" onclick="reveal(this, 'Tus conversaciones pueden mejorar hasta un día cualquiera.')">
      <span>02 · TOCA AQUÍ</span>
      Un detalle...
    </button>

    <button class="message-card" onclick="reveal(this, 'No quisiera que una pequeña discusión borre los buenos momentos.')">
      <span>03 · TOCA AQUÍ</span>
      Algo importante...
    </button>

    <button class="message-card" onclick="reveal(this, 'Incluso cuando soy un poquito insoportable jajaja, te tengo mucho cariño.')">
      <span>04 · TOCA AQUÍ</span>
      Una confesión...
    </button>
  </div>

  <button class="btn" onclick="go(5)">Hay algo más...</button>
</section>

<!-- PANTALLA 5: FOTO -->
<section class="screen" id="s5">
  <div class="eyebrow">Un pequeño recuerdo</div>
  <h2 class="section-title">Un espacio especial</h2>

  <div class="photo-frame">
    <img src="foto.jpg" alt="Una fotografía especial"
      onerror="this.style.display='none'; document.getElementById('placeholder').style.display='flex';">

    <div class="photo-placeholder" id="placeholder">
      <span style="font-size:45px">♥</span>
      <span>Un recuerdo bonito</span>
      <span style="font-size:11px">Aquí puedes colocar tu fotografía</span>
    </div>
  </div>

  <p class="subtitle">
    Porque incluso los días normales<br>
    pueden guardar momentos bonitos.
  </p>
  <br>
  <button class="btn" onclick="go(6)">Una última cosita</button>
</section>

<!-- PANTALLA 6 -->
<section class="screen" id="s6">
  <div class="heart">♥</div>
  <div class="eyebrow">Y para terminar...</div>

  <h2 class="final-text">
    No todas las conversaciones tienen que terminar con un silencio.
    A veces basta con dar un pasito y reconocer que nos equivocamos.
  </h2>

  <div class="line"></div>

  <p class="subtitle">
    Gracias por tomarte el tiempo de llegar hasta aquí, Aleja.
    <br>
    Espero que tengas una bonita sonrisa al terminar de leer esto.
  </p>

  <br><br>

  <button class="btn" onclick="showFinal()">Una última sorpresa ♥</button>

  <p class="small">Sin presiones, sin condiciones. Solo un detalle sincero.</p>
</section>

<!-- PANTALLA FINAL -->
<section class="screen" id="s7">
  <div class="heart" style="font-size:65px">♥</div>

  <div class="eyebrow">Para ti, Aleja</div>

  <h1 style="font-size:clamp(45px,11vw,75px)">
    Lo siento,<br><span>de corazón.</span>
  </h1>

  <div class="line"></div>

  <p class="final-text" style="font-size:29px">
    Y ojalá podamos seguir compartiendo muchos momentos bonitos.
  </p>

  <p class="small">
    Este pequeño detalle no cambia lo sucedido,<br>
    pero quería que supieras que me importas.
  </p>

  <br><br>
  <button class="btn secondary" onclick="go(1)">Volver a comenzar ↻</button>
</section>

<footer>
  UN DETALLE HECHO CON CARIÑO · ALEJA ♥
</footer>

<script>

// CAMBIO DE PANTALLAS
function go(n) {
  document.querySelectorAll('.screen').forEach(s => {
    s.classList.remove('active');
  });

  document.getElementById('s' + n).classList.add('active');
  window.scrollTo({top: 0, behavior: 'smooth'});
}

// ABRIR SOBRE
function openLetter() {
  const envelope = document.getElementById('envelope');
  envelope.classList.add('open');

  setTimeout(() => {
    go(3);
  }, 650);
}

// MENSAJES INTERACTIVOS
function reveal(button, message) {
  button.innerHTML = '<span>♥ UN MENSAJE PARA TI</span>' + message;
  button.style.borderColor = '#c51e38';
  button.style.background = '#291017';
  button.disabled = true;
}

// FINAL CON LLUVIA DE CORAZONES
function showFinal() {
  go(7);

  for (let i = 0; i < 35; i++) {
    const heart = document.createElement('div');
    heart.innerHTML = '♥';
    heart.style.position = 'fixed';
    heart.style.left = Math.random() * 100 + 'vw';
    heart.style.top = '-30px';
    heart.style.color = '#c51e38';
    heart.style.fontSize = (12 + Math.random() * 20) + 'px';
    heart.style.zIndex = '10';
    heart.style.pointerEvents = 'none';
    heart.style.transition = 'transform 4s linear, opacity 4s';
    document.body.appendChild(heart);

    setTimeout(() => {
      heart.style.transform =
        'translateY(' + (window.innerHeight + 80) + 'px) rotate(500deg)';
      heart.style.opacity = '0';
    }, 50);

    setTimeout(() => heart.remove(), 4300);
  }
}

// PARTÍCULAS DE FONDO
function createParticles() {
  const container = document.getElementById('particles');

  for (let i = 0; i < 22; i++) {
    const particle = document.createElement('div');
    particle.className = 'particle';
    particle.innerHTML = Math.random() > 0.5 ? '♥' : '✦';

    particle.style.left = Math.random() * 100 + '%';
    particle.style.fontSize = (8 + Math.random() * 12) + 'px';
    particle.style.animationDuration = (9 + Math.random() * 13) + 's';
    particle.style.animationDelay = (Math.random() * 12) + 's';

    container.appendChild(particle);
  }
}

createParticles();

</script>

</body>
</html>
