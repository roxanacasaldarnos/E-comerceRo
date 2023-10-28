# E-comerceRo
Proyecto Final E-commerce
Este es un proyecto de E-commer en donde se encuentra el código html, css y javascript con sus funcionalidades en el se encuntra un archivo productos json no utilice API ya que estoy aprendiendo.

Parte del código de html del carrito creación del aside
 <aside>
            <button class="close-menu" id="close-menu">
                <i class="bi bi-x"></i>
            </button>
            <header>
                <img  class="mariposa" src="/Multimedia/mariposas/mariposa2.webp" alt="">
                <h1 class="logo">Darling tienda en linea</h1>
            </header>
            <nav>
                <ul>
                    <li>
                        <a class="boton-menu boton-volver" href="./index.html">
                            <i class="bi bi-arrow-return-left"></i> Seguir comprando
                        </a>
                    </li>
                    <li>
                        <a class="boton-menu boton-carrito active" href="./carrito.html">
                            <i class="bi bi-cart-fill"></i> Carrito
                        </a>
                      </li>
                </ul>
            </nav>
            <footer>
                <hr>
                <p class="texto-footer">Todos los derechos reservados © 2023 <br><b>Roxana Casaldarnos</b></p>
            </footer>
        </aside>




Este es parte del código de eventos para el filtro de categorias 


botonesCategorias.forEach(boton => {
    boton.addEventListener("click", (e) => {

        botonesCategorias.forEach(boton => boton.classList.remove("active"));
        e.currentTarget.classList.add("active");

        if (e.currentTarget.id != "todos") {
            const productoCategoria = productos.find(producto => producto.categoria.id === e.currentTarget.id);
            tituloPrincipal.innerText = productoCategoria.categoria.nombre;
            const productosBoton = productos.filter(producto => producto.categoria.id === e.currentTarget.id);
            cargarProductos(productosBoton);
        } else {
            tituloPrincipal.innerText = "Todos los productos";
            cargarProductos(productos);
        }

    })
});
