# HeadTracking
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PAINEL HEADTRACKING IOS ⚙️</title>
    <style>
        body {
            font-family: Arial, sans-serif;
        }
        .option {
            margin-bottom: 10px;
        }
        .notification {
            color: green;
            font-style: italic;
            margin-top: 5px;
        }
        .signature {
            margin-top: 20px;
            font-style: italic;
            color: #666;
        }
    </style>
    <script>
        async function loadImage(url) {
            return new Promise((resolve, reject) => {
                const img = new Image();
                img.onload = () => resolve(img);
                img.onerror = reject;
                img.src = url;
            });
        }

        async function setupBackgroundImage() {
            const backgroundImage = await loadImage("https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQj9l8dagDImF1soLf1xmH7cImbnjLevcMo2QpbmQBcG69qC3N__mKQrUc&s=10.png");
            document.body.style.backgroundImage = `url('${backgroundImage.src}')`;
        }

        function otimizacao() {
            const settings = [
                "settings put system ro.am.reschedule_service true",
                "settings put system touch.orientationAware 0",
                "settings put system touch.size.scale 1",
                "settings put system touch.size.isSummed 0",
                "settings put system ro.config.performanceMode true",
                "settings put system ro.config.lowBatteryUpgrade true",
                "settings put system ro.config.hw.logsystem.send 0",
                "settings put system ro.config.do_sdcard_upgrade true",
                "settings put system ro.config.hw_GSensorOptimize true",
                "settings put system touch.deviceType touchScreen",
                "settings put system ro.vendor.touchfeature.gamemode.enable true"
            ];
            
            settings.forEach(setting => {
                console.log(setting);
            });

            document.getElementById('otimizacao-notification').innerText = 'Ativado';
        }
    </script>
</head>
<body onload="setupBackgroundImage()">
    <h2> PAINEL HEADTRACKING IOS ⚙️</h2>
       <h2>Insira Login e Senha</h2>
  <ul>
    <li>LOGIN: <input type="name" class="percentage-input" min="0" max="100">
   <li>SENHA: <input type="number" class="percentage-input" min="0" max="100">
      <button class="confirm-button">OK</button>
    <div class="option">
        <label for="HEADTRACKING"> HEADTRACKING :</label>
        <input type="checkbox" id="HeadTracking" name="HEADTRACKING">
        <div id="HEADTRACKING-notification" class="notification"></div>
    </div>
    <div class="option">
        <label for="OTIMIZAÇÃO IOS"> OTIMIZAÇÃO IOS:</label>
        <input type="checkbox" id="OTIMIZAÇÃO IOS" name="OTIMIZAÇÃO IOS" onclick="OTIMIZACÃO IOS()"> 
        <div id="OTIMIZAÇÃO IOS-notification" class="notification"></div>
    </div>
    <div class="option">
        <label for="AIM ASSIST"> AIM ASSIST:</label>
        <input type="checkbox" id="ajuste" name="AIM ASSIST">
        <div id="AIM ASSIST-notification" class="notification"></div>
            <div id="AIM ASSIST-notification" class="notification"></div>
    </div>
    <div class="option">
        <label for="ATIVAR PAINEL "> ATIVAR PAINEL:</label>
        <input type="checkbox" id="ajuste" name="ATIVAR PAINEL">
        <div id="ATIVAR PAINEL-notification" class="notification"></div>
    </div>
<html>
<head>
  <title></title>
  <style>
    #calibration-area {
      width: 1560px;
      height: 720px;
      border: 1px solid #000;
      margin-bottom: 50px;
    }
  </style>
</head>
<body>
  <h1>CALIBRADOR TOUCH/CURSO 🛠</h1>

  <h2>CALIBRAR TOUCH 🖱</h2>
  <p>Digite as coordenadas (x e y) desejadas e clique no botão abaixo para calibrar a posição do toque:</p>
  <input type="text" id="touch-x-input" placeholder="Posição X">
  <input type="text" id="touch-y-input" placeholder="Posição Y">
  <button id="calibrate-touch-btn">Calibrar</button>

  <h2>CALIBRAR CURSOR 🖱</h2>
  <p>Digite as coordenadas (x e y) desejadas e clique no botão abaixo para calibrar a posição do cursor:</p>
  <input type="text" id="cursor-x-input" placeholder="Posição X">
  <input type="text" id="cursor-y-input" placeholder="Posição Y">
  <button id="calibrate-cursor-btn">Calibrar</button>

  <h2>CALIBRAR SENSIBILIDADE 🖱</h2>
  <p>Digite a posição y do centro da tela e clique no botão abaixo para calibrar a sensibilidade:</p>
  <input type="text" id="center-y-input" placeholder="Posição Y do Centro">
  <button id="calibrate-sensitivity-btn">Calibrar</button>
  <h2> </h2>
  <script>
    // Calibração de Touch
    var calibrationArea = document.getElementById('calibration-area');
    var calibrateTouchBtn = document.getElementById('calibrate-touch-btn');
    var touchXInput = document.getElementById('touch-x-input');
    var touchYInput = document.getElementById('touch-y-input');

    function calibrateTouch() {
      var touchX = parseInt(touchXInput.value) || 780;
      var touchY = parseInt(touchYInput.value) || 360;

      calibrationArea.addEventListener('touchstart', function (e) {
        e.preventDefault();
        var touch = e.touches[0];
        touchX = touch.clientX;
        touchY = touch.clientY;
      });

      calibrationArea.addEventListener('touchmove', function (e) {
        e.preventDefault();
        var touch = e.touches[0];
        var deltaX = touch.clientX - touchX;
        var deltaY = touch.clientY - touchY;
        console.log('Delta X:', deltaX, 'Delta Y:', deltaY);
      });
    }

    calibrateTouchBtn.addEventListener('click', calibrateTouch);

    // Calibração de Cursor
    var calibrateCursorBtn = document.getElementById('calibrate-cursor-btn');
    var cursorXInput = document.getElementById('cursor-x-input');
    var cursorYInput = document.getElementById('cursor-y-input');

    function calibrateCursor() {
      var cursorX = parseInt(cursorXInput.value) || 0;
      var cursorY = parseInt(cursorYInput.value) || 0;

      document.addEventListener('mousemove', function (e) {
        cursorX = e.clientX;
        cursorY = e.clientY;
      });

      calibrateCursorBtn.addEventListener('click', function () {
        console.log('Cursor X:', cursorX, 'Cursor Y:', cursorY);
      });
    }

    calibrateCursorBtn.addEventListener('click', calibrateCursor);



    // Calibração de Sensibilidade
    var calibrateSensitivityBtn = document.getElementById('calibrate-sensitivity-btn');
    var centerYInput = document.getElementById('center-y-input');

    function calibrateSensitivity() {
      var centerY = parseInt(centerYInput.value) || 360;
      var sensitivity = 1;

      calibrateSensitivityBtn.addEventListener('click', function () {
        var currentY = window.innerHeight / 2;

        if (currentY < centerY) {
          sensitivity += 0.1;
          console.log('Sensibilidade aumentada:', sensitivity);
        } else if (currentY > centerY) {
          sensitivity -= 0.1;
          console.log('Sensibilidade diminuída:', sensitivity);
        } else {
          sensitivity = 1;
          console.log('Sensibilidade calibrada:', sensitivity);
        }
      });
    }

    calibrateSensitivityBtn.addEventListener('click', calibrateSensitivity);
  </script>
</body>
</html>
</body>
</html>
</html>
</tml>

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title style="color:black;">Painel Safari</title>
    <style>
        .optionButton {
            color: black;
            margin-bottom: 10px;
        }
        body {
            background-image: none;
            background-size: cover;
        }
    </style>
</head>
<body>
    <h1 style="color:black;">  </h1>
    
    <!-- Opções -->
    <button id="chooseFileButton" class="optionButton"> INJETAR HEADTRACKING </button><br>
    <button id="aimFovButton" class="optionButton"> AIMLOCK </button><br>
    <button id="aimLockButton" class="optionButton"> AIMFOV </button><br>
    <button id="frameRateButton" class="optionButton"> OTIMIZACÃO HZ </button><br>
    <button id="allPaperButton" class="optionButton"> IMAGEM PAINEL </button><br>

    <!-- Input de arquivo oculto -->
    <input type="file" id="fileInput" style="display: none;">

    <script>
        // Função para escolher arquivo
        function chooseFile() {
            document.getElementById('fileInput').click();
        }

        // Funções para cada opção
        function toggleAimFOV() {
            console.log("Aim FOV ativado");
            // Adicione aqui a lógica para ativar/desativar a opção Aim FOV
        }

        function toggleAimLock() {
            console.log("Aim Lock ativado");
            // Adicione aqui a lógica para ativar/desativar a opção Aim Lock
        }

        function toggleFrameRate() {
            console.log("Taxa de Frame ativada");
            // Adicione aqui a lógica para ativar/desativar a opção Taxa de Frame
        }

        function chooseBackgroundImage() {
            document.getElementById('fileInput').click();
        }

        // Event listeners para os botões
        document.getElementById('chooseFileButton').addEventListener('click', chooseFile);
        document.getElementById('aimFovButton').addEventListener('click', toggleAimFOV);
        document.getElementById('aimLockButton').addEventListener('click', toggleAimLock);
        document.getElementById('frameRateButton').addEventListener('click', toggleFrameRate);
        document.getElementById('allPaperButton').addEventListener('click', chooseBackgroundImage);

        
        // Event listener para quando um arquivo é selecionado
        document.getElementById('fileInput').addEventListener('change', function(event) {
            const file = event.target.files[0];
            if (file) {
                console.log("Arquivo selecionado:", file.name);
                // Definir a imagem como fundo da tela do painel
                document.body.style.backgroundImage = `url('${URL.createObjectURL(file)}')`;
            }
        });
    </script>
</body>
</html>
    </div>
    <div class="signature"> 🧑🏻‍💻 Criador @ediwzzx </div>
