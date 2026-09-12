LABORATOIRE 1 - 6GEI311 - Architecture des logiciels
PARTIE 2 - SITUATION 1
Rendre accessible sur GitHub un projet existant uniquement en local

Etudiants : Abdoul Razack Tégawindé ZONGO  ;  Compte GitHub : abdoulrazackZONGO

Coéquipier : Tounwendsida Julien ZONGO     ;  Compte GitHub : zongo-julien

Dépôt concerné :
https://github.com/abdoulrazackZONGO/repo-gei311-lab1-Abdoul


PROBLEME POSE

Le membre A possède un projet versionne uniquement sur sa machine :
aucun dépôt n'existe sur GitHub. Il doit rendre ce projet accessible au
membre B afin que les deux puissent collaborer via GitHub, sans perdre
l'historique des commits déjà réalisés localement.


ETAPES SUIVIES :

Etape 1 - Création du depot local (situation de depart)
   Le dépôt a été initialise localement, avec la meme structure que la
   Partie 1 (Dossier_A contenant textA.txt), sans aucun lien avec GitHub.

       mkdir repo-gei311-lab1-Abdoul
       cd repo-gei311-lab1-Abdoul
       git init
       mkdir Dossier_A
       echo "labo 1, gestion de version, Abdoul" > Dossier_A\textA.txt
       git add -A
       git commit -m "Création d'un autre repos pour la situation 1"

   Remarque : la branche créée par défaut par Git s'appelait "master".
   Elle a été renommée en "main" pour correspondre a la convention
   utilisée sur GitHub :

       git branch -M main


Etape 2 - Création d'un dépôt vide sur GitHub
  - Un nouveau dépôt a été créé sur github.com sous le nom
   repo-gei311-lab1-Abdoul.

Etape 3 - Liaison du dépôt local au depot distant
   -La commande "git remote add" crée le lien entre le dépôt local et le
   depot GitHub, en lui donnant le nom conventionnel "origin" :

       git remote add origin https://github.com/abdoulrazackZONGO/repo-gei311-lab1-Abdoul.git

   -Verification du lien :
       git remote -v


Etape 4 - Envoi du contenu local vers GitHub
   L'option -u (--set-upstream) lie la branche locale "main" a la branche
   distante "origin/main", ce qui permet d'utiliser simplement "git push"
   et "git pull" par la suite, sans repréciser les noms :

       git push -u origin main

   Résultat obtenu :
       * [new branch]      main -> main
       branch 'main' set up to track 'origin/main'.

   L'intégralité de l'historique local (et non seulement les fichiers) a
   ainsi été transférée sur GitHub.


Etape 5 - Ajout du membre B comme collaborateur

Etape 6 - Acceptation de l'invitation par le membre B
   Le membre B reçoit une notification (courriel et/ou notification
   GitHub) et clique sur "Accept invitation".


Etape 7 - Clonage du dépôt par le membre B
   Le membre B peut désormais récupérer le projet et y contribuer :

       git clone https://github.com/abdoulrazackZONGO/repo-gei311-lab1-Abdoul.git
       cd repo-gei311-lab1-Abdoul  


VERIFICATION DE LA SOLUTION

La solution à été validée par les contrôles suivants :

   1. Presence de Dossier_A/textA.txt sur la page GitHub du depot.
   2. Presence de l'historique des commits dans l'onglet "Commits"
      (l'historique local a bien été conservé, pas seulement les
      fichiers).
   3. Présence du membre B dans Settings > Collaborators, sans la mention
      "Pending" après son acceptation.
   4. Clonage effectif du depot par le membre B, puis modification et
      push réussis de sa part, confirmant l'accès en écriture.
