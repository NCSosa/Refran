<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Refrán Program - Estilo Shell</title>
    <style>
        body {
            font-family: "Courier New", Courier, monospace;
            background-color: #000; /* Fondo negro */
            color: #00ff00; /* Letras verde brillante como una terminal */
            margin: 0;
            padding: 20px;
        }
        h1 {
            text-align: center;
            color: #00ff00; /* Título en verde */
        }
        .container {
            max-width: 600px;
            margin: 0 auto;
            padding: 20px;
            background-color: #222; /* Fondo gris oscuro dentro del contenedor */
            border-radius: 8px;
            box-shadow: 0 0 15px rgba(0, 0, 0, 0.5);
        }
        input[type="text"] {
            width: 100%;
            padding: 10px;
            margin-top: 10px;
            margin-bottom: 20px;
            border: none;
            background-color: #333; /* Fondo del input en gris oscuro */
            color: #00ff00; /* Texto verde dentro del input */
            font-size: 16px;
            font-family: "Courier New", Courier, monospace;
            border-radius: 5px;
        }
        button {
            width: 100%;
            padding: 10px;
            background-color: #555; /* Botón en gris */
            color: #00ff00; /* Texto del botón en verde */
            border: none;
            border-radius: 5px;
            font-size: 16px;
            cursor: pointer;
            font-family: "Courier New", Courier, monospace;
        }
        button:hover {
            background-color: #777; /* Botón en gris más claro al hacer hover */
        }
        p {
            text-align: center;
            font-size: 18px;
            color: #00ff00; /* Texto de la respuesta en verde */
        }
    </style>
    <script>
        function responder() {
            // Capturamos el input del usuario
            const refran = document.getElementById("refranInput").value;

            // Mostramos la respuesta fija con un smiley :)
            const respuesta = document.getElementById("respuesta");
            respuesta.innerText = "... patada en los cojones :)";

            // Preguntamos si quiere intentarlo de nuevo
            setTimeout(function() {
                const intentarDeNuevo = confirm("¿Quieres probar de nuevo? (sí/no)");
                if (intentarDeNuevo) {
                    reiniciarPrograma(); // Reiniciar si responde que sí
                } else {
                    mostrarSoloRespuestaFinal(); // Mostrar solo la respuesta final si responde no
                }
            }, 1000); // Esperamos 1 segundo antes de preguntar
        }

        function reiniciarPrograma() {
            // Limpiamos el input y la respuesta
            document.getElementById("refranInput").value = '';
            document.getElementById("respuesta").innerText = '';
        }

        function mostrarSoloRespuestaFinal() {
            // Limpiamos todo el contenido y mostramos solo la respuesta final
            document.body.innerHTML = '<p style="text-align: center; color: #00ff00; font-size: 24px;">Todos los caminos llevan a Roma.</p>';
        }

        document.addEventListener("DOMContentLoaded", function() {
            // Aseguramos que el botón funcione correctamente
            const boton = document.getElementById("botonEnviar");
            boton.addEventListener("click", responder);
        });
    </script>
</head>
<body>
    <h1>Termina el refrán</h1>
    
    <div class="container">
        <label for="refranInput">Escribe la primera parte de un refrán:</label>
        <input type="text" id="refranInput" placeholder="Ejemplo: A quien madruga...">
        <button id="botonEnviar">Enviar</button>
        
        <p id="respuesta"></p>
    </div>
</body>
</html>
