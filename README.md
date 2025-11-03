# Consola Tamir

**IA que habla como vos. Traduce a código pro.**

> Escribís como en la esquina → apretás **PRO** → sale el código listo.

---

## Demo en vivo
[https://consola-tamir.vercel.app](https://consola-tamir.vercel.app) *(próximamente)*

---

## Cómo usarlo

1. Abrí `index.html`  
2. Escribí como hablás  
3. **CALLE** → respuesta fluida  
4. **PRO** → código listo

---

## Código (todo en un archivo)

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Consola Tamir</title>
  <style>
    body{font-family:Arial;margin:0;background:#111;color:#0f0;height:100vh;display:flex;flex-direction:column}
    #tamir{flex:1;display:flex;flex-direction:column;padding:20px}
    input,button{font:18px Arial;padding:15px;margin:5px;border:1px solid #0f0;background:#000;color:#0f0;flex:1}
    #salida{flex:3;background:#000;color:#0f0;padding:15px;margin:10px 0;overflow:auto;white-space:pre-wrap}
  </style>
</head>
<body>
  <div id="tamir">
    <input id="inp" placeholder="Escribí como hablás..." />
    <div>
      <button onclick="calle()">CALLE</button>
      <button onclick="pro()">PRO</button>
    </div>
    <pre id="salida">Consola Tamir lista. Escribí algo.</pre>
  </div>

  <script>
    const salida = document.getElementById('salida');
    window.calle = () => {
      const txt = document.getElementById('inp').value || "nada";
      salida.textContent = `¡Dale, ${txt}! Te entendí. Acción en 3...2...1...`;
    };
    window.pro = () => {
      const txt = document.getElementById('inp').value || "sin idea";
      salida.textContent = 
`// TRADUCCIÓN ÉLITE
const input = "${txt}";
const accion = "EJECUTAR: " + input.toUpperCase().replace(/ /g, "_");
console.log(accion);
// → Lanza a tu IA, checklist o sistema`;
    };
  </script>
</body>
</html>
