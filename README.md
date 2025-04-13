
<!DOCTYPE html>
<html>
  <head>
    <title>Miniapp con contador</title>
    <style>
      body {
        font-family: sans-serif;
        text-align: center;
        padding: 50px;
      }
      button {
        padding: 10px 20px;
        font-size: 16px;
        margin: 10px;
      }
    </style>
  </head>
  <body>
    <h1>Bienvenido a mi miniapp</h1>
    <p id="wallet">Cargando wallet...</p>

    <h2>Contador</h2>
    <p id="contador">0</p>
    <button onclick="aumentar()">Aumentar</button>
    <button onclick="reiniciar()">Reiniciar</button>

    <script type="module">
      import { MiniKit } from "https://cdn.jsdelivr.net/npm/@worldcoin/minikit-js@1.0.0/+esm"

      MiniKit.install()

      let contador = 0

      async function mostrarWallet() {
        const walletEl = document.getElementById("wallet")
        if (MiniKit.isInstalled()) {
          const wallet = await MiniKit.getAddress()
          walletEl.textContent = "Tu wallet es: " + wallet
        } else {
          walletEl.textContent = "No estás dentro de World App"
        }
      }

      function aumentar() {
        contador++
        document.getElementById("contador").textContent = contador
      }

      function reiniciar() {
        contador = 0
        document.getElementById("contador").textContent = contador
      }

      mostrarWallet()
    </script>
  </body>
</html>