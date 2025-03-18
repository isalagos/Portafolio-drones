<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portafolio Semanal - Curso de Drones</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
            background-color: #f4f4f4;
        }
        .container {
            max-width: 800px;
            margin: auto;
            background: white;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        h2 {
            text-align: center;
        }
        input, textarea, button {
            width: 100%;
            margin: 10px 0;
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 5px;
        }
        .entry {
            background: #e9ecef;
            padding: 10px;
            margin-top: 10px;
            border-radius: 5px;
        }
        .entry img {
            max-width: 100%;
            margin-top: 10px;
            border-radius: 5px;
        }
    </style>
</head>
<body>
    <div class="container">
        <h2>Portafolio Semanal - Curso de Drones</h2>
        <input type="text" id="week" placeholder="Semana (Ejemplo: Semana 1)">
        <textarea id="activity" placeholder="Describe tu actividad de esta semana..."></textarea>
        <input type="file" id="image" accept="image/*">
        <button onclick="addEntry()">Agregar Actividad</button>
        <div id="entries"></div>
    </div>
    <div class="team-container">
        <div class="team-member">
            <img src="https://via.placeholder.com/100" alt="Integrante 1">
            <h3>Integrante 1</h3>
            <a href="#integrante1">Ver perfil</a>
        </div>
        <div class="team-member">
            <img src="https://via.placeholder.com/100" alt="Integrante 2">
            <h3>Integrante 2</h3>
            <a href="#integrante2">Ver perfil</a>
        </div>
        <div class="team-member">
            <img src="https://via.placeholder.com/100" alt="Integrante 3">
            <h3>Integrante 3</h3>
            <a href="#integrante3">Ver perfil</a>
        </div>
        <div class="team-member">
            <img src="https://via.placeholder.com/100" alt="Integrante 4">
            <h3>Integrante 4</h3>
            <a href="#integrante4">Ver perfil</a>
        </div>
    </div>
    <script>
        function addEntry() {
            let week = document.getElementById("week").value;
            let activity = document.getElementById("activity").value;
            let imageInput = document.getElementById("image");
            let imageFile = imageInput.files[0];
            
            if (week && activity) {
                let entryDiv = document.createElement("div");
                entryDiv.classList.add("entry");
                entryDiv.innerHTML = `<strong>${week}:</strong> <p>${activity}</p>`;
                
                if (imageFile) {
                    let reader = new FileReader();
                    reader.onload = function(e) {
                        let img = document.createElement("img");
                        img.src = e.target.result;
                        entryDiv.appendChild(img);
                    }
                    reader.readAsDataURL(imageFile);
                }
                
                document.getElementById("entries").appendChild(entryDiv);
                
                document.getElementById("week").value = "";
                document.getElementById("activity").value = "";
                document.getElementById("image").value = "";
            } else {
                alert("Por favor, completa ambos campos.");
            }
        }
    </script>
</body>
</html>
