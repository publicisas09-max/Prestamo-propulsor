index.html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Préstamo Propulsor</title>
  <style>
    body {
      font-family: 'Poppins', sans-serif;
      background: linear-gradient(180deg, #5a00ff, #ff00aa);
      color: white;
      text-align: center;
      margin: 0;
      padding: 0;
    }
    .container {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      height: 100vh;
      padding: 20px;
    }
    .card {
      background: rgba(255, 255, 255, 0.15);
      padding: 30px;
      border-radius: 20px;
      box-shadow: 0 4px 20px rgba(0,0,0,0.2);
      max-width: 350px;
      width: 100%;
    }
    input {
      width: 100%;
      padding: 12px;
      border: none;
      border-radius: 10px;
      margin-top: 10px;
      text-align: center;
      font-size: 16px;
    }
    button {
      width: 100%;
      padding: 12px;
      margin-top: 15px;
      border: none;
      border-radius: 10px;
      background-color: #ff00aa;
      color: white;
      font-weight: bold;
      font-size: 16px;
      cursor: pointer;
    }
    button:hover {
      background-color: #ff33bb;
    }
    .hidden { display: none; }
    .loading { font-size: 18px; }
  </style>
</head>
<body>
  <div class="container">
    <!-- Pantalla 1 -->
    <div id="pantalla1" class="card">
      <h2>Préstamo Propulsor</h2>
      <p>Consulta tu cupo disponible</p>
      <input type="number" id="cedula" placeholder="Ingresa tu cédula">
      <button onclick="consultar()">Consultar</button>
    </div>

    <!-- Pantalla 2 -->
    <div id="pantalla2" class="card hidden">
      <p class="loading">Consultando información...</p>
    </div>

    <!-- Pantalla 3 -->
    <div id="pantalla3" class="card hidden">
      <h2>Tu cupo aprobado es:</h2>
      <h1>$2.100.000</h1>
      <button onclick="continuar()">Continuar</button>
    </div>

    <!-- Pantalla 4 -->
    <div id="pantalla4" class="card hidden">
      <h2>Un asesor te escribirá</h2>
      <p>Gracias por confiar en Préstamo Propulsor 💜</p>
    </div>
  </div>

  <script>
    function consultar() {
      const cedula = document.getElementById("cedula").value;
      if (cedula === "") {
        alert("Por favor ingresa tu cédula.");
        return;
      }
      document.getElementById("pantalla1").classList.add("hidden");
      document.getElementById("pantalla2").classList.remove("hidden");

      setTimeout(() => {
        document.getElementById("pantalla2").classList.add("hidden");
        document.getElementById("pantalla3").classList.remove("hidden");
      }, 2000);
    }

    function continuar() {
      document.getElementById("pantalla3").classList.add("hidden");
      document.getElementById("pantalla4").classList.remove("hidden");
    }
  </script>
</body>
</html>
