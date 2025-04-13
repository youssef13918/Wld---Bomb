# Wld---Bomb
<!DOCTYPE html>
<html>
<head>
  <title>Mi primera miniapp</title>
</head>
<body>
  <h1>Hola, estás en mi miniapp</h1>
  <button onclick="verWallet()">Ver mi wallet</button>

  <script type="module">
    import { MiniKit } from "https://cdn.jsdelivr.net/npm/@worldcoin/minikit-js@1.0.0/+esm"

    MiniKit.install()

    async function verWallet() {
      if (MiniKit.isInstalled()) {
        const wallet = await MiniKit.getAddress()
        alert("Tu wallet es: " + wallet)
      } else {
        alert("No estás dentro de World App")
      }
    }
  </script>
</body>
</html>