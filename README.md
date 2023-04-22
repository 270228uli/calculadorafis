# calculadorafis
<!DOCTYPE html>
<html>
<head>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.2/jquery.min.js"></script>
<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.1/css/bootstrap.min.css">
<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.1/css/bootstrap-theme.min.css">
<script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.1/js/bootstrap.min.js"></script>;
<title>Fisica</title>
</head>
<body>
    <nav class="navbar navbar-dark bg-dark" style="background-color: blue">
      </nav>
    <div class="jumbotron jumbotron-fluid">
        <div class="container">
          <h1 class="display-4">Calculadora Fisica</h1>
          <p class="lead">Fundamentación Teórica La Física es la ciencia que estudia las propiedades de la materia, radiación y energía en todas sus formas, con base en el Método Científico, utilizando un lenguaje matemático. <br> Las estructuras observables microscópicas, mesoscópicas y macroscópicas. Provee la infraestructura básica necesaria para el entendimiento de las otras ciencias, por ejemplo las químicas, las biológicas y las ambientales.
           <br> El Profesional en Física debe dominar los conocimientos básicos de las siguientes ramas: electromagnetismo mecánica teórica mecánica cuántica técnicas experimentales de la física métodos matemáticos de la física.</p>
          </div>
        </div>
        <form id="formulario">
          <label for="distancia">DISTANCIA:</label>
          <input type="text" id="distancia" name="distancia">
          <select id="distanciaUnidad">
              <option value="metros">metros</option>
              <option value="pies">pies</option>
          </select>
          <br>
          <label for="tiempo">TIEMPO:</label>
          <input type="text" id="tiempo" name="tiempo">
          <select id="tiempoUnidad">
              <option value="segundos">segundos</option>
              <option value="horas">horas</option>
              </select>
              <br>
              <label for="velocidadUnidad">UNIDADES DE VELOCIDAD:</label>
              <select id="velocidadUnidad">
                  <option value="metros_por_segundo">m/s</option>
                  <option value="pies_por_segundo">ft/s</option>
                  <option value="kilometros_por_hora">km/hr</option>
                  <option value="millas_por_hora">mph</option>
              </select>
              <br>
              <br>
              <button type="button" class="btn btn-warning" value="calcular" onclick="calcular()">CALCULAR</button>
        </form>
        <br>
        <p id="resultado"></p>
        <p style="color: red; background-color: yellow;">VELOCIDAD: <span id="velocidad"></span></p>
        <p style="color: red; background-color: yellow;">ACELERACION: <span id="aceleracion"></span></p>
        <p style="color: red; background-color: yellow;">RAPIDEZ: <span id="rapidez"></span></p>
          <script>
        function calcular(){
            const distancia=parseFloat(document.getElementById('distancia').value);
            const tiempo = parseFloat(document.getElementById('tiempo').value);
            const distanciaUnidad = document.getElementById('distanciaUnidad').value;
             const tiempoUnidad = document.getElementById('tiempoUnidad').value;
             const velocidadUnidad = document.getElementById('velocidadUnidad').value;
              let distanciaSI = 0;
              let tiempoSI = 0;
              if (distanciaUnidad === 'metros') {
                distanciaSI = distancia;
              }else if (distanciaUnidad === 'pies') {
                distanciaSI = distancia / 3.281;
              }
              if (tiempoUnidad=== 'segundos') {
                tiempoSI = tiempo;
              }else if (tiempoUnidad === 'horas') {
                tiempoSI = tiempo * 3600;
              }
              let velocidad = 0;
              let aceleracion = 0;
              let rapidez = 0;
              if (velocidadUnidad === 'metros_por_segundo') {
                velocidad = distanciaSI / tiempoSI;
                rapidez = velocidad;
                aceleracion = velocidad / tiempoSI;
              }else if (velocidadUnidad === 'pies_por_segundo') {
                velocidad = (distanciaSI * 3.281 ) / tiempoSI;
                rapidez = velocidad;
                aceleracion = velocidad / tiempoSI;
              }else if (velocidadUnidad === 'kilometros_por_hora') {
                velocidad = (distanciaSI / 1000) / (tiempoSI / 3600);
                rapidez = velocidad;
                aceleracion = velocidad / (tiempoSI / 3600);
              }else if (velocidadUnidad === 'millas_por_hora') {
                velocidad = (distanciaSI / 1609) / (tiempoSI / 3600);
                rapidez = velocidad;
                aceleracion = velocidad / (tiempoSI / 3600);
        }
        let resultado = '';
        document.getElementById('velocidad').textContent = velocidad.toFixed(2) + ' ' + velocidadUnidad;
        document.getElementById('aceleracion').textContent = aceleracion.toFixed(2) + ' '+ 'm/s^2';
        document.getElementById('rapidez').textContent = rapidez.toFixed(2) + ' ' + velocidadUnidad;
         document.getElementById('resultado').innerHTML = resultado;
     }
      </script>
</body>
</html>
