<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <title>Server Terminal</title>
  <style>
    body {
      background: black;
      color: lime;
      font-family: monospace;
      padding: 20px;
    }
    #terminal {
      white-space: pre-line;
    }
  </style>
</head>
<body>
  <div id="terminal"></div>

  <script>
    const terminal = document.getElementById("terminal");

    // daftar teks yang akan ditampilkan seperti di Python
    const lines = [
      "Connecting to a secret server...",
      "Downloading file secret....",
      "Access personal files...",
      "Get a password...",
      "⚠️PASSWORD FOUND  ⚠️",
      "Send to serverr... 10%",
      "Send to server... 50%",
      "Send to server... 100%",
      "Server has found...",
      "Hacking has on bercyanda brok."
    ];
    let delay = 50; // kecepatan ketik (ms)
    let lineDelay = 800; // jeda antar baris

    async function typeLine(text) {
      for (let char of text) {
        terminal.innerHTML += char;
        await new Promise(r => setTimeout(r, delay));
      }
      terminal.innerHTML += "\n";
    }

    async function start() {
      for (let line of lines) {
        await typeLine(line);
        await new Promise(r => setTimeout(r, lineDelay));
      }
    }

    start();
  </script>
</body>
</html>
