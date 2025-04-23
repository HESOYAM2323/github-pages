<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Wanted Shot</title>
  <style>
    body {
      background-color: #000;
      color: #00ff88;
      font-family: monospace;
      margin: 0;
      padding: 0 2rem;
    }
    header, footer {
      border-color: #00aa55;
      border-bottom: 1px solid;
      padding: 1rem 0;
    }
    header h1 {
      font-size: 2.5rem;
      margin: 0;
    }
    .cart-btn {
      background-color: #00aa55;
      color: black;
      padding: 0.5rem 1rem;
      border: none;
      cursor: pointer;
      border-radius: 20px;
    }
    .product-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 1.5rem;
      margin-top: 2rem;
    }
    .product-card {
      background: rgba(0, 255, 136, 0.1);
      border: 1px solid #00aa55;
      padding: 1rem;
      box-shadow: 0 0 10px #00aa55;
    }
    .product-card h2 {
      margin-top: 0;
    }
    .button-container {
      display: flex;
      justify-content: space-between;
      margin-top: 1rem;
    }
    .buy-btn, .add-to-cart-btn {
      background-color: #00aa55;
      color: black;
      border: none;
      padding: 0.3rem 0.8rem;
      cursor: pointer;
      width: 48%;
      border-radius: 10px;
      font-size: 0.9rem;
    }
    .buy-btn {
      background-color: #00aa55;
    }
    footer {
      border-top: 1px solid #00aa55;
      text-align: center;
      margin-top: 3rem;
    }
    .modal {
      display: none;
      position: fixed;
      top: 0;
      left: 0;
      width: 100vw;
      height: 100vh;
      background-color: rgba(0, 0, 0, 0.9);
      color: #00ff88;
      font-family: monospace;
      z-index: 999;
      justify-content: center;
      align-items: center;
    }
    .modal-content {
      background-color: #001f1f;
      border: 2px solid #00ff88;
      padding: 2rem;
      width: 80%;
      max-width: 500px;
      box-shadow: 0 0 20px #00ff88;
    }
    .modal-close {
      background: none;
      color: #00ff88;
      border: none;
      font-size: 1.2rem;
      float: right;
      cursor: pointer;
    }
    .modal h3 {
      margin-top: 0;
    }
    #alertaHacker {
      display: none;
      position: fixed;
      top: 20%;
      left: 50%;
      transform: translateX(-50%);
      background-color: #001f1f;
      border: 2px solid #ff0044;
      padding: 1rem 2rem;
      color: #ff0044;
      font-family: monospace;
      box-shadow: 0 0 20px #ff0044;
      z-index: 1000;
    }
    .delete-btn {
      background: none;
      color: #ff0044;
      border: none;
      font-size: 1.5rem;
      cursor: pointer;
      float: right;
    }
    .delete-btn::before {
      content: "🗑️";
      font-size: 1.5rem;
    }
    .cart-item {
      margin: 1rem 0;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }
    .about-section {
      background-color: #001f1f;
      padding: 2rem;
      border-radius: 10px;
      margin-top: 2rem;
      box-shadow: 0 0 15px #00ff88;
    }
    .about-section h2 {
      font-size: 2rem;
    }
  </style>
</head>
<body>
  <header>
    <div style="display: flex; justify-content: space-between; align-items: center;">
      <h1>Wanted Shot</h1>
      <button class="cart-btn" onclick="mostrarCarrito()">🛒 Carrito</button>
    </div>
  </header>

  <!-- Sección "Acerca de" -->
  <section class="about-section">
    <h2>¿Qué es Wanted Shot?</h2>
    <p>Wanted Shot es una tienda especializada en optimización de PCs para jugadores y entusiastas de la informática. Aquí podrás encontrar paquetes diseñados para mejorar el rendimiento de tu sistema, desde la aceleración de la red hasta la optimización de la memoria RAM.</p>
    <p>Si eres un gamer o alguien que busca sacar el máximo provecho de su PC, nuestros productos están hechos para ti. ¡No pierdas más tiempo y mejora tu experiencia digital ahora mismo!</p>
  </section>

  <main class="product-grid">
    <div class="product-card">
      <h2>Pack Turbo FPS</h2>
      <p>Optimiza tu PC al máximo para mejorar los FPS en juegos competitivos.</p>
      <div class="button-container">
        <button class="add-to-cart-btn" onclick="agregarAlCarrito('Pack Turbo FPS')">Agregar al carrito</button>
        <button class="buy-btn" onclick="window.open('https://paypal.me/HESOYAM2323?country.x=CO&locale.x=es_XC', '_blank')">Comprar</button>
      </div>
    </div>
    <!-- Aquí se agregan los demás productos de la tienda, como antes -->
    <div class="product-card">
      <h2>Pack Startup Boost</h2>
      <p>Acelera el arranque de tu sistema eliminando procesos innecesarios.</p>
      <div class="button-container">
        <button class="add-to-cart-btn" onclick="agregarAlCarrito('Pack Startup Boost')">Agregar al carrito</button>
        <button class="buy-btn" onclick="window.open('https://paypal.me/HESOYAM2323?country.x=CO&locale.x=es_XC', '_blank')">Comprar</button>
      </div>
    </div>
    <div class="product-card">
      <h2>Pack Gamer Pro</h2>
      <p>Configuraciones avanzadas para streamers y jugadores exigentes.</p>
      <div class="button-container">
        <button class="add-to-cart-btn" onclick="agregarAlCarrito('Pack Gamer Pro')">Agregar al carrito</button>
        <button class="buy-btn" onclick="window.open('https://paypal.me/HESOYAM2323?country.x=CO&locale.x=es_XC', '_blank')">Comprar</button>
      </div>
    </div>
    <div class="product-card">
      <h2>Pack Cyber Shield</h2>
      <p>Refuerza tu privacidad y reduce el rastreo digital con ajustes especializados.</p>
      <div class="button-container">
        <button class="add-to-cart-btn" onclick="agregarAlCarrito('Pack Cyber Shield')">Agregar al carrito</button>
        <button class="buy-btn" onclick="window.open('https://paypal.me/HESOYAM2323?country.x=CO&locale.x=es_XC', '_blank')">Comprar</button>
      </div>
    </div>
    <div class="product-card">
      <h2>Pack Overclock Lite</h2>
      <p>Maximiza el rendimiento del procesador sin comprometer la estabilidad.</p>
      <div class="button-container">
        <button class="add-to-cart-btn" onclick="agregarAlCarrito('Pack Overclock Lite')">Agregar al carrito</button>
        <button class="buy-btn" onclick="window.open('https://paypal.me/HESOYAM2323?country.x=CO&locale.x=es_XC', '_blank')">Comprar</button>
      </div>
    </div>
    <div class="product-card">
      <h2>Pack Ninja RAM</h2>
      <p>Limpieza y configuración de la memoria RAM para respuestas más rápidas.</p>
      <div class="button-container">
        <button class="add-to-cart-btn" onclick="agregarAlCarrito('Pack Ninja RAM')">Agregar al carrito</button>
        <button class="buy-btn" onclick="window.open('https://paypal.me/HESOYAM2323?country.x=CO&locale.x=es_XC', '_blank')">Comprar</button>
      </div>
    </div>
    <div class="product-card">
      <h2>Pack Network Pulse</h2>
      <p>Optimización de red para reducir el lag y mejorar la estabilidad de conexión.</p>
      <div class="button-container">
        <button class="add-to-cart-btn" onclick="agregarAlCarrito('Pack Network Pulse')">Agregar al carrito</button>
        <button class="buy-btn" onclick="window.open('https://paypal.me/HESOYAM2323?country.x=CO&locale.x=es_XC', '_blank')">Comprar</button>
      </div>
    </div>
    <div class="product-card">
      <h2>Pack Clean Shell</h2>
      <p>Elimina archivos basura y procesos ocultos para un sistema limpio y ágil.</p>
      <div class="button-container">
        <button class="add-to-cart-btn" onclick="agregarAlCarrito('Pack Clean Shell')">Agregar al carrito</button>
        <button class="buy-btn" onclick="window.open('https://paypal.me/HESOYAM2323?country.x=CO&locale.x=es_XC', '_blank')">Comprar</button>
      </div>
    </div>
  </main>

  <footer>
    <p>© 2025 Wanted Shot. Código y café ☕</p>
  </footer>

  <div id="modalCarrito" class="modal" onclick="cerrarModal(event)">
    <div class="modal-content" onclick="event.stopPropagation()">
      <button class="modal-close" onclick="cerrarModal()">X</button>
      <h3>🧠 Carrito Hacker</h3>
      <div id="contenidoCarrito">Cargando...</div>
    </div>
  </div>

  <div id="alertaHacker">⚠️ Acción no permitida.</div>

  <script>
    const carrito = [];
    const limiteProductos = 5;
    const alertaHacker = document.getElementById("alertaHacker");

    function mostrarAlerta(mensaje) {
      alertaHacker.textContent = mensaje;
      alertaHacker.style.display = "block";
      setTimeout(() => {
        alertaHacker.style.display = "none";
      }, 3000);
    }

    function agregarAlCarrito(producto) {
      if (carrito.includes(producto)) {
        mostrarAlerta("⚠️ Este producto ya está en tu carrito.");
        return;
      }
      if (carrito.length >= limiteProductos) {
        mostrarAlerta("🚫 Límite de productos alcanzado (máx. " + limiteProductos + ").");
        return;
      }
      carrito.push(producto);
      mostrarCarrito();
    }

    function mostrarCarrito() {
      const modal = document.getElementById("modalCarrito");
      const contenido = document.getElementById("contenidoCarrito");
      if (carrito.length === 0) {
        contenido.textContent = "Tu carrito está vacío... ejecutando limpieza...";
      } else {
        contenido.innerHTML = carrito.map((item, index) => `
          <div class="cart-item">
            [#${index + 1}] ${item}
            <button class="delete-btn" onclick="eliminarDelCarrito(${index})"></button>
          </div>
        `).join("");
      }
      modal.style.display = "flex";
    }

    function eliminarDelCarrito(index) {
      carrito.splice(index, 1);
      mostrarCarrito();
    }

    function cerrarModal(event) {
      const modal = document.getElementById("modalCarrito");
      modal.style.display = "none";
    }
  </script>
</body>
</html>
