<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Juegos de Programación</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <h1>Juegos de Programación</h1>
    </header>
    <main>
        <div class="container">
            <input type="text" id="gameName" placeholder="Nombre del juego...">
            <button onclick="buscarCodigo()">Buscar</button>
            <div id="codigoContainer"></div>
        </div>
    </main>
    <footer>
        <p>© 2024 Juegos de Programación</p>
    </footer>
    <script src="script.js"></script>
</body>
</html>








body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    background-color: #f4f4f4;
}

header {
    background-color: #333;
    color: #fff;
    text-align: center;
    padding: 20px 0;
}

h1 {
    margin: 0;
}

main {
    padding: 20px;
}

.container {
    max-width: 600px;
    margin: 0 auto;
    background-color: #fff;
    padding: 20px;
    border-radius: 8px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

input[type="text"] {
    width: calc(100% - 80px);
    padding: 10px;
    margin-right: 10px;
    border-radius: 5px;
    border: 1px solid #ccc;
}

button {
    padding: 10px 20px;
    background-color: #333;
    color: #fff;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}

button:hover {
    background-color: #555;
}

#codigoContainer {
    margin-top: 20px;
    white-space: pre-wrap;
}

footer {
    text-align: center;
    padding: 20px 0;
    background-color: #333;
    color: #fff;
}










function buscarCodigo() {
    var gameName = document.getElementById('gameName').value;
    fetch('/buscar?juego=' + gameName)
        .then(response => response.text())
        .then(data => {
            document.getElementById('codigoContainer').innerText = data;
        });
}



from flask import Flask, request, render_template

app = Flask(__name__)

# Diccionario de juegos y sus códigos correspondientes
codigos = {
    'juego1': 'Código del juego 1 en C#',
    'juego2': 'Código del juego 2 en C#',
    # Agrega más juegos según sea necesario
}

@app.route('/')
def index():
    return render_template('index.html')

@app.route('/buscar')
def buscar_codigo():
    juego = request.args.get('juego')
    return codigos.get(juego, 'No se encontró el juego')

if __name__ == '__main__':
    app.run(debug=True)





from flask import Flask, request, render_template

app = Flask(__name__)

# Diccionario de juegos y sus códigos correspondientes
codigos = {
    'juego1': 'Código del juego 1 en C#',
    'juego2': 'Código del juego 2 en C#',
    # Agrega más juegos según sea necesario
}

@app.route('/')
def index():
    return render_template('index.html')

@app.route('/buscar')
def buscar_codigo():
    juego = request.args.get('juego')
    return codigos.get(juego, 'No se encontró el juego')

if __name__ == '__main__':
    app.run(debug=True)

