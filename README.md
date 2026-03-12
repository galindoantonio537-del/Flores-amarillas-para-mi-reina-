<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Para Ti 💛</title>
    <link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Quicksand:wght@500;700&display=swap" rel="stylesheet">
    
    <style>
        /* --- ESTILOS (CSS) --- */
        body {
            text-align: center;
            background: linear-gradient(135deg, #fff9c4 0%, #ffe082 50%, #ffcc80 100%);
            background-attachment: fixed;
            font-family: 'Quicksand', sans-serif;
            padding: 20px;
            margin: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            overflow-x: hidden; /* Evita que la pantalla se desplace a los lados por los pétalos */
            animation: fadeInBody 1.5s ease-in-out;
        }

        .container {
            background: rgba(255, 255, 255, 0.85);
            padding: 40px 30px;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.15);
            max-width: 600px;
            width: 100%;
            position: relative;
            z-index: 10; /* Asegura que la tarjeta esté por encima de los pétalos */
        }

        h1#mensaje {
            color: #ff8f00;
            font-family: 'Dancing Script', cursive;
            font-size: 45px;
            margin-bottom: 10px;
            margin-top: 0;
        }

        h2.subtitulo {
            color: #d84315;
            font-size: 20px;
            font-weight: 700;
            margin-bottom: 20px;
        }

        img {
            width: 100%;
            max-width: 350px;
            border-radius: 15px;
            margin-top: 10px;
            box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
            transition: transform 0.3s ease;
        }

        img:hover {
            transform: scale(1.03);
        }

        p {
            font-size: 18px;
            color: #4e342e;
            line-height: 1.6;
            margin: 15px 0;
        }

        .quote {
            font-size: 19px;
            color: #5d4037;
            font-style: italic;
            background: #fff3e0;
            padding: 15px;
            border-left: 5px solid #ff9800;
            border-radius: 5px;
            margin: 25px 0;
        }

        #btn-sorpresa {
            background-color: #ff9800;
            color: white;
            border: none;
            padding: 15px 25px;
            font-size: 18px;
            font-family: 'Quicksand', sans-serif;
            font-weight: bold;
            border-radius: 30px;
            cursor: pointer;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
            transition: background-color 0.3s, transform 0.2s;
            margin-top: 10px;
        }

        #btn-sorpresa:hover {
            background-color: #f57c00;
            transform: translateY(-2px);
        }

        #mensaje-oculto {
            display: none;
            font-size: 22px;
            color: #d84315;
            font-family: 'Dancing Script', cursive;
            margin-top: 20px;
            font-weight: bold;
            animation: fadeInBody 1s ease-in-out;
        }

        @keyframes fadeInBody {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* --- ESTILOS DE LOS PÉTALOS --- */
        .petalo {
            position: absolute;
            background-color: #ffd54f; /* Color amarillo del pétalo */
            border-radius: 15px 0 15px 0; /* Forma de hojita/pétalo */
            opacity: 0.8;
            pointer-events: none; /* Para que no interfieran al hacer clic en otras cosas */
            z-index: 1;
            top: -10%;
            animation: caer linear forwards;
        }

        @keyframes caer {
            0% {
                top: -10%;
                transform: translateX(0) rotate(0deg);
                opacity: 1;
            }
            100% {
                top: 110%;
                transform: translateX(100px) rotate(360deg);
                opacity: 0;
            }
        }
    </style>
</head>
<body>

    <div class="container">
        <h1 id="mensaje">Te Amo Mucho mi reina 💛</h1>
        <h2 class="subtitulo">Las flores amarillas significan alegría y tú llegaste a darle sentido y alegría a mi vida.</h2>
        
        <img src="https://i.pinimg.com/1200x/f6/1a/f9/f61af98806a712ec81b19e6d34650975.jpg" alt="Flores Amarillas">
        
        <p>Eres lo mejor que me ha pasado 💖</p>
        <p>Sé que soy difícil de amar pero intento cambiar todos los días con tal de no perderte y hacerte feliz.</p>
        
        <blockquote class="quote">
            "Te quiero no por quien eres, sino por quien soy cuando estoy contigo."<br>– Mario Benedetti
        </blockquote>

        <button id="btn-sorpresa">Toca aquí para una sorpresa 🎁</button>
        <p id="mensaje-oculto">¡Gracias por existir! Prometo cuidarte siempre. 🥰🌻</p>
    </div>

    <script>
        /* --- JAVASCRIPT --- */
        document.addEventListener("DOMContentLoaded", function() {
            
            // 1. Animación inicial del título
            const mensaje = document.getElementById("mensaje");
            mensaje.style.opacity = "0";
            setTimeout(() => {
                mensaje.style.transition = "opacity 2.5s ease-in-out";
                mensaje.style.opacity = "1";
            }, 500);

            // 2. Funcionalidad del botón sorpresa
            const boton = document.getElementById("btn-sorpresa");
            const mensajeOculto = document.getElementById("mensaje-oculto");

            boton.addEventListener("click", function() {
                mensajeOculto.style.display = "block";
                boton.style.display = "none";
            });

            // 3. Sistema de creación de pétalos
            function crearPetalo() {
                const petalo = document.createElement("div");
                petalo.classList.add("petalo");

                // Posición horizontal aleatoria
                petalo.style.left = Math.random() * 100 + "vw";

                // Tamaño aleatorio para que se vea más natural
                const tamaño = Math.random() * 10 + 10; // Entre 10px y 20px
                petalo.style.width = tamaño + "px";
                petalo.style.height = tamaño + "px";

                // Duración de la caída aleatoria (entre 4 y 8 segundos)
                petalo.style.animationDuration = Math.random() * 4 + 4 + "s";

                document.body.appendChild(petalo);

                // Eliminar el pétalo después de que termina su animación para no saturar la memoria
                setTimeout(() => {
                    petalo.remove();
                }, 8000);
            }

            // Crear un pétalo nuevo cada 400 milisegundos
            setInterval(crearPetalo, 400);
        });
    </script>
</body>
</html>
![115477](https://github.com/user-attachments/assets/1f570165-9d75-48be-93a1-938e6ea3190d)
