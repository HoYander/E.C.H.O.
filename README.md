<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<title>Acesso Secreto</title>

<meta name="robots" content="noindex, nofollow">

<style>
/* FUNDO DA TELA */
body {
  margin: 0;
  height: 100vh;
  background: url("imagens/fundo.jpg") no-repeat center center fixed;
  background-size: cover;
  font-family: Arial, sans-serif;
  color: #e0e0e0;
}

/* SOBREPOSIÇÃO ESCURA */
.overlay {
  background: rgba(0,0,0,0.5);
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}

/* PAINEL DE LOGIN COM BLUR */
.panel {
  width: 320px;
  padding: 25px;
  background: rgba(10,20,30,0.7);
  backdrop-filter: blur(8px);
  border: 1px solid #1e90ff;
  border-radius: 10px;
  box-shadow: 0 0 25px rgba(30,144,255,0.3);
  text-align: center;
}

h1 {
  font-size: 18px;
  letter-spacing: 2px;
  margin-bottom: 5px;
}

.warning {
  font-size: 11px;
  color: #aaa;
  margin-bottom: 20px;
}

input {
  width: 100%;
  padding: 10px;
  margin-top: 10px;
  background: rgba(2,11,20,0.8);
  border: 1px solid #1e90ff;
  color: #fff;
  border-radius: 5px;
}

button {
  width: 100%;
  padding: 10px;
  margin-top: 15px;
  background: #1e90ff;
  border: none;
  color: #000;
  font-weight: bold;
  border-radius: 5px;
  cursor: pointer;
}

button:hover {
  background: #63b3ff;
}

.status {
  margin-top: 15px;
  font-size: 12px;
  height: 14px;
}

.footer {
  margin-top: 20px;
  font-size: 10px;
  color: #555;
}

/* TELA PÓS LOGIN */
#painelSecreto {
  display: none;
  color: #00ff99;
  font-size: 16px;
  text-align: center;
}
</style>
</head>

<body>

<div class="overlay">
  <div class="panel" id="loginPanel">
    <h1>ACESSO RESTRITO</h1>
    <div class="warning">Sistema confidencial • Monitorado</div>

    <input id="user" placeholder="Identificação">
    <input id="pass" type="password" placeholder="Credencial">

    <button onclick="autorizar()">AUTORIZAR</button>

    <div class="status" id="status"></div>

    <div class="footer">Projeto fictício • uso educacional</div>
  </div>

  <div id="painelSecreto">
    <h1>Área Secreta Acessada</h1>
    <p>Bem-vindo, <span id="nomeAgente"></span> 👁️‍🗨️</p>
    <p>Sessão segura iniciada...</p>
  </div>
</div>

<script>
function autorizar() {
  const u = document.getElementById("user").value;
  const p = document.getElementById("pass").value;
  const status = document.getElementById("status");
  const loginPanel = document.getElementById("loginPanel");
  const painelSecreto = document.getElementById("painelSecreto");
  const nomeAgente = document.getElementById("nomeAgente");

  status.innerText = "Verificando credenciais...";

  setTimeout(() => {
    // Defina aqui a Identificação e Senha corretas
    if (u === "AGENTE47" && p === "X9-ALFA") {
      status.style.color = "#00ff99";
      status.innerText = "Acesso autorizado ✔";

      // Mostra a tela secreta
      loginPanel.style.display = "none";
      painelSecreto.style.display = "block";
      nomeAgente.innerText = u;
    } else {
      status.style.color = "#ff4c4c";
      status.innerText = "Acesso negado ✖";
    }
  }, 1200);
}
</script>

</body>


</html>
