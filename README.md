<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Salimos?</title>
    <style>
        body {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: flex-start; /* Alinear el contenido hacia arriba */
            height: 100vh;
            margin: 0;
            font-family: Arial, sans-serif;
            background-color: #007BFF; /* Fondo azul */
            background-image: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" width="200" height="200" viewBox="0 0 24 24"><path fill="red" d="M12 21.35l-1.45-1.32C5.4 15.36 2 12.28 2 8.5 2 5.42 4.42 3 7.5 3c1.74 0 3.41.81 4.5 2.09C13.09 3.81 14.76 3 16.5 3 19.58 3 22 5.42 22 8.5c0 3.78-3.4 6.86-8.55 11.54L12 21.35z"/></svg>'); /* Corazones dispersos */
            background-size: 200px 200px; /* Aumenta el tamaño de los corazones */
            background-position: 0px 0px; /* Ajusta la posición inicial del fondo */
            background-repeat: repeat; /* Repite el fondo */
        }
        h1 {
            margin-top: 30px; /* Mueve el título hacia arriba */
            margin-bottom: 20px; /* Espacio para el contenido */
            font-size: 32px; /* Ajusta el tamaño del título */
            color: white; /* Color del texto */
        }
        .button-container {
            display: flex;
            justify-content: space-between;
            width: 100%;
            max-width: 400px; /* Ajusta el ancho máximo de los botones */
            margin-top: 20px; /* Espacio adicional para subir botones */
        }
        .button {
            padding: 15px 30px;
            font-size: 16px;
            border: none;
            cursor: pointer;
            margin: 10px;
            transition: font-size 0.1s;
            flex: 1; /* Permite que los botones se expandan igualmente */
            margin: 0 5px; /* Espaciado entre botones */
        }
        .morado {
            background-color: purple;
            color: white;
        }
        .azul {
            background-color: blue;
            color: white;
        }
        /* Estilo para el modal */
        .modal {
            display: none;
            position: fixed;
            z-index: 1;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            overflow: auto;
            background-color: rgba(0, 0, 0, 0.5);
        }
        .modal-content {
            background-color: white;
            margin: 15% auto;
            padding: 20px;
            border: 1px solid #888;
            width: 80%;
            text-align: center;
        }
        .close {
            color: red;
            float: right;
            font-size: 28px;
            font-weight: bold;
        }
        .close:hover,
        .close:focus {
            color: darkred;
            text-decoration: none;
            cursor: pointer;
        }
    </style>
</head>
<body>

    <h1>Salimos?</h1>
    <div class="button-container">
        <button class="button morado" onclick="handleYes()">Sí</button>
        <button class="button azul" onclick="handleNo(this)">No</button>
    </div>

    <!-- Modal -->
    <div id="myModal" class="modal">
        <div class="modal-content">
            <span class="close" onclick="closeModal()">&times;</span>
            <p>Ok, te quiero y apúrate</p>
        </div>
    </div>

    <script>
        function handleYes() {
            document.getElementById('myModal').style.display = "block";
        }

        function handleNo(button) {
            // Cambiar el tamaño del botón "No"
            let currentSize = parseInt(window.getComputedStyle(button).fontSize);
            if (currentSize > 0) {
                button.style.fontSize = (currentSize - 2) + 'px';
            }
        }

        function closeModal() {
            document.getElementById('myModal').style.display = "none";
        }

        // Cerrar el modal si se hace clic fuera de él
        window.onclick = function(event) {
            const modal = document.getElementById('myModal');
            if (event.target == modal) {
                modal.style.display = "none";
            }
        }
    </script>

</body>
</html>


