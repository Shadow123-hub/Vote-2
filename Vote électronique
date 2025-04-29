<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Vote Électronique</title>
  <link rel="stylesheet" href="style.css">
  <style>
    body {
      background: #f0f4f8;
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 20px;
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
    }

    .container {
      background: white;padding: 30px;
      border-radius: 12px;
      box-shadow: 0 8px 16px rgba(0,0,0,0.1);
      text-align: center;
      width: 90%;
      max-width: 500px;
    }

    h2 {
      font-weight: bold;
      color: #333;
      margin-bottom: 20px;
    }

    button {
      font-size: 18px;
      padding: 10px 20px;
      margin: 10px;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      transition: 0.3s ease;
    }

    #pourBtn {
      background-color: #b6f7b0; /* vert clair */
      color: #034d02;
    }

    #pourBtn:hover {
      background-color: #a3e7a1;
    }

    #contreBtn {
      background-color: #f7b0b0; /* rouge clair */
      color: #4d0202;
    }

    #contreBtn:hover {
      background-color: #e69a9a;
    }

    .admin-container {
      margin-bottom: 20px;
    }

    .vote-counts {
      margin-top: 20px;
    }
  </style>
</head>
<body>
  
  <div class="admin-container">
    <h3>Modifier le sujet du vote et le nombre de personnes autorisées à voter</h3>
    <input type="text" id="newSujet" placeholder="Entrez un nouveau sujet de vote" />
    <input type="number" id="maxVotes" placeholder="Nombre de personnes autorisées à voter" min="1" /><button onclick="changerSujet()">Modifier</button>
  </div>

  
  <div class="container">
    <h2 id="sujetAffiche">Sujet du vote : Qui est le meilleur joueur ?</h2>
    <button id="pourBtn" onclick="voter('pour')">POUR</button>
    <button id="contreBtn" onclick="voter('contre')">CONTRE</button>
    <p id="message"></p>

    
    <div class="vote-counts">
      <p>Nombre de votes POUR : <span id="pourCount">0</span></p>
      <p>Nombre de votes CONTRE : <span id="contreCount">0</span></p>
    </div>
  </div>

  
  <script>
    let aVoté = false;
    let maxVotes = 1000;
    let votesCount = 0;
    let pourCount = 0;
    let contreCount = 0;
    function changerSujet() {
      const newSujet = document.getElementById('newSujet').value;
      const newMaxVotes = document.getElementById('maxVotes').value;

      if (newSujet) {
        document.getElementById('sujetAffiche').innerText = "Sujet du vote : " + newSujet;
      }if (newMaxVotes && !isNaN(newMaxVotes) && newMaxVotes > 0) {
        maxVotes = parseInt(newMaxVotes);
        alert("Le nombre de personnes autorisées à voter a été modifié à " + maxVotes);
      } else {
        alert("Veuillez entrer un nombre valide de personnes autorisées à voter !");
      }
    }

 
    function voter(vote) {
      if (votesCount >= maxVotes) {
        document.getElementById('message').innerText = "Le nombre maximum de votes a été atteint. Merci !";
        return;
      }

      
      if (aVoté) {
        document.getElementById('message').innerText = "Vous avez déjà voté !";
        return; 
      }

      
      aVoté = true;
      votesCount++; 

      
      if (vote === 'pour') {
        pourCount++;
        document.getElementById('message').innerText = "Vous avez voté POUR ! Merci de votre participation.";
      } else if (vote === 'contre') {
        contreCount++;
        document.getElementById('message').innerText = "Vous avez voté CONTRE ! Merci de votre participation.";
      }
      document.getElementById('pourBtn').disabled = true;
      document.getElementById('contreBtn').disabled = true;

 
      document.getElementById('pourCount').innerText = pourCount;
      document.getElementById('contreCount').innerText = contreCount;
    }
  </script>
</body>
</html>
