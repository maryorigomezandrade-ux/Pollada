# Pollada
Pollada pro fondos
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Pollada Solidaria</title>
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #fff7e6;
      margin: 0;
      padding: 0;
    }
    .container {
      max-width: 500px;
      margin: auto;
      background: white;
      padding: 20px;
      border-radius: 10px;
      margin-top: 20px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
    }
    h1 {
      text-align: center;
      color: #c0392b;
    }
    label {
      font-weight: bold;
      margin-top: 10px;
      display: block;
    }
    input, select, textarea, button {
      width: 100%;
      padding: 10px;
      margin-top: 5px;
      border-radius: 5px;
      border: 1px solid #ccc;
    }
    button {
      background: #c0392b;
      color: white;
      font-size: 16px;
      border: none;
      margin-top: 15px;
      cursor: pointer;
    }
    button:hover {
      background: #a93226;
    }
    .resumen {
      background: #fbeee6;
      padding: 10px;
      margin-top: 15px;
      border-radius: 5px;
    }
  </style>
</head>

<body>

<div class="container">
  <h1>🐔 Pollada Solidaria</h1>

  <label>Nombre</label>
  <input type="text" id="nombre" placeholder="Tu nombre">

  <label>Cantidad de polladas</label>
  <input type="number" id="cantidad" min="1" value="1">

  <label>¿Qué incluye la pollada?</label>
  <select id="menu">
    <option>Pollo + papas + ensalada</option>
    <option>Pollo + arroz + ensalada</option>
    <option>Pollo entero</option>
    <option>Combo familiar</option>
  </select>

  <label>Dirección de entrega</label>
  <textarea id="direccion" rows="3" placeholder="Escribe la dirección completa"></textarea>

  <label>Comentario (opcional)</label>
  <textarea id="comentario" rows="2"></textarea>

  <button onclick="enviarPedido()">Enviar pedido</button>

  <div class="resumen" id="resumen" style="display:none;"></div>
</div>

<script>
function enviarPedido() {
  const nombre = document.getElementById("nombre").value;
  const cantidad = document.getElementById("cantidad").value;
  const menu = document.getElementById("menu").value;
  const direccion = document.getElementById("direccion").value;
  const comentario = document.getElementById("comentario").value;

  if (!nombre || !direccion) {
    alert("Por favor completa nombre y dirección");
    return;
  }

  const texto = `
Pedido de Pollada Solidaria
Nombre: ${nombre}
Cantidad: ${cantidad}
Menú: ${menu}
Dirección: ${direccion}
Comentario: ${comentario}
`;

  document.getElementById("resumen").style.display = "block";
  document.getElementById("resumen").innerText = texto;

  // ENVIAR POR WHATSAPP (cambia el número)
  const telefono = "393000000000"; // ← número con prefijo país
  const url = `https://wa.me/${telefono}?text=${encodeURIComponent(texto)}`;
  window.open(url, "_blank");
}
</script>

</body>
</html>
