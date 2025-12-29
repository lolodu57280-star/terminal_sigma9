<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<title>Accès Sécurisé – Sigma-9</title>
<style>
body { background:black; color:#0f0; font-family:Consolas, monospace; text-align:center; padding-top:80px; }
input { padding:10px; font-size:20px; margin-top:20px; }
button { padding:10px; font-size:20px; margin-left:10px; cursor:pointer; }
#msg { margin-top:30px; font-size:22px; }
.hidden { display:none; }
</style>
</head>
<body>

<h1>🔒 Terminal de Sécurité A.R.E.E – Sigma-9</h1>
<p>Entrez le mot de passe d’évacuation :</p>

<input id="code" type="password" maxlength="20">
<button onclick="checkCode()">VALIDER</button>

<div id="msg"></div>

<script>
let essais = 5;
const mdp = "EXTINCTION";

function checkCode() {
  let saisie = document.getElementById("code").value.toUpperCase();
  if (saisie === mdp) {
    document.body.innerHTML = "<h1 style='color:#0f0;'>ACCÈS AUTORISÉ</h1><p>Procédure d’évacuation enclenchée…</p>";
  } else {
    essais--;
    if (essais <= 0) {
      document.body.innerHTML = "<h1 style='color:red;'>ÉCHEC IRRÉVERSIBLE</h1><p>Procédure d’extermination humaine engagée…</p>";
      return;
    }
    document.getElementById("msg").innerHTML =
      "Code incorrect.<br>Essais restants : " + essais;
  }
}
</script>

</body>
</html>
