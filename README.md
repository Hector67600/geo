<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <title>Virus en cours...</title>
    <style>
        /* Style pour l'écran de défilement noir et vert */
        body {
            background-color: #000;
            color: #0f0;
            font-family: 'Courier New', Courier, monospace;
            font-size: 16px;
            margin: 0;
            padding: 10px;
            overflow: hidden; /* Cache la barre de défilement pour faire plus propre */
            user-select: none;
        }
        #console {
            width: 100%;
            height: 100vh;
            white-space: pre-wrap;
            word-wrap: break-word;
        }
    </style>
    <script>
        // Étape 1 : Les petits messages successifs
        function lancerBlague() {
            alert("⚠️ Alerte : Une activité suspecte a été détectée sur votre système.");
            alert("❌ Tentative d'accès aux fichiers... Accès refusé.");
            alert("💾 Initialisation du protocole de secours...");
            alert("⚙️ Lancement du déchiffrement des données système.");
            
            // Étape 2 : Lancement du défilement infini après le dernier clic
            setInterval(defilerLignes, 20); // Déclenche une nouvelle ligne toutes les 30 millisecondes
        }

        // Fonction qui génère les fausses lignes de code
        function defilerLignes() {
            let consoleDiv = document.getElementById("console");
            
            // Génération de faux blocs textuels et de nombres aléatoires
            let randomNum = Math.floor(Math.random() * 99999999);
            let hexCode = Math.random().toString(16).substring(2, 10).toUpperCase();
            
            let faussesLignes = [
                `LOADING_DATA_SEGMENT_0x${hexCode}... SUCCESS\n`,
                `BYPASS_FIREWALL_STATUS: ${randomNum} - CONNECTED\n`,
                `${randomNum}${hexCode}${randomNum}${hexCode}${randomNum}\n`,
                `DUMPING_MEMORY_CORE_AT_ADDRESS_0x${hexCode}...\n`
            ];
            
            // Choix d'une ligne au hasard parmi la liste
            let ligneAleatoire = faussesLignes[Math.floor(Math.random() * faussesLignes.length)];
            
            // Ajout du texte dans la console
            consoleDiv.innerText += ligneAleatoire;

            // Fait défiler automatiquement vers le bas pour voir le flux en continu
            window.scrollTo(0, document.body.scrollHeight);
            
            // Pour éviter de saturer la mémoire du navigateur après plusieurs minutes
            if (consoleDiv.innerText.length > 5000) {
                consoleDiv.innerText = consoleDiv.innerText.substring(2000);
            }
        }
    </script>
</head>
<body onload="lancerBlague()">

    <!-- Zone où le faux code va défiler -->
    <div id="console"></div>

</body>
</html>
