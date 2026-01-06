<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Copiar reclamo</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f4f4f4;
      padding: 15px;
    }
    textarea {
      width: 100%;
      height: 260px;
      font-size: 16px;
      padding: 10px;
    }
    button {
      width: 100%;
      padding: 15px;
      font-size: 18px;
      background: #25D366;
      color: white;
      border: none;
      border-radius: 6px;
      margin-top: 10px;
    }
  </style>
</head>
<body>

<h3>📲 Mensaje para WhatsApp</h3>

<textarea id="mensaje"></textarea>

<button onclick="copiar()">📋 COPIAR MENSAJE</button>

<script>
  function getParam(name) {
    const url = new URL(window.location.href);
    return url.searchParams.get(name) || '';
  }

  const texto =
`📌 RECLAMO
Fecha: ${getParam('fecha')}
N° Reclamo: ${getParam('nro')}
Barrio: ${getParam('barrio')}
Detalle: ${getParam('detalle')}`;

  document.getElementById('mensaje').value = texto;

  function copiar() {
    const t = document.getElementById('mensaje');
    t.select();
    t.setSelectionRange(0, 99999);
    document.execCommand('copy');
    alert('Mensaje copiado. Pegalo en el grupo de WhatsApp.');
  }
</script>

</body>
</html>
