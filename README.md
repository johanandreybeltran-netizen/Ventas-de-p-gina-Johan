# Ventas-de-p-gina-Johanfrom IPython.display import HTML

html_content = """
<!DOCTYPE html>
<html>
<head>
  <title>Mi Tienda bolsos familia Beltrán</title>
</head>
<body>
  <h1>🛍️ Mi Tienda de hermosos bolsos</h1>

  <div id="productos"></div>

  <h2>🛒 Carrito</h2> ver

  <ul id="carrito"></ul>

  <script>
    const productos = [
      { id: 1, nombre: "bolsos tejidos", precio: 20 },
      { id: 2, nombre: "lindos bolsos tejidos", precio: 50 },
      { id: 3, nombre: "bolsos tejidos bonitos" , precio: 15 }
    ];

    const carrito = [];

    function mostrarProductos() {
      const contenedor = document.getElementById("productos");

      productos.forEach(p => {
        const div = document.createElement("div");
        div.innerHTML = `
          <p>${p.nombre} - $${p.precio}</p>
          <button onclick="agregar(${p.id})">Agregar</button>
        `;
        contenedor.appendChild(div);
      });
    }

    function agregar(id) {
      const producto = productos.find(p => p.id === id);
      carrito.push(producto);
      actualizarCarrito(); // Fixed: Removed 'si' as it was undefined and the function takes no arguments
    }

    function actualizarCarrito() {
      const lista = document.getElementById("carrito");
      lista.innerHTML = "";

      carrito.forEach(p => {
        const item = document.createElement("li");
        item.textContent = p.nombre + " - $" + p.precio;
        lista.appendChild(item);
      });
    }

    mostrarProductos();
  </script>
</body>
</html>
"""

HTML(html_content)
Johan ventas
