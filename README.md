Extraction et Structuration de Conversations Copilot



📌 Présentation

Ce projet automatise l’extraction, la conversion, la vérification, l’archivage et l’agrégation de conversations issues de Microsoft Copilot. 


L’objectif ==>
              ==> est de disposer d’un pipeline fiable qui produit :

1- des exports JSON horodatés,

2- des bases SQLite correspondantes,

3- une base consolidée master.db toujours à jour et dédoublonnée.



⚙️ Fonctionnalités principales :

1- Export JSON via Playwright (navigateur automatisé).

2- Conversion en SQLite pour exploitation structurée.

3- Vérification automatique JSON ↔ DB (statut ✅ / ⚠️).

4- Archivage horodaté de chaque run (archives/).

5- Agrégation de toutes les DB archivées dans master.db.

6- Dédoublonnage automatique pour garder master.db propre.



🚀 Installation
Cloner le dépôt :

=> bash

git clone https://github.com/ton-compte/ton-projet.git
cd ton-projet
Créer un environnement virtuel Python (idéalement en Python 3.12).


=> bash

python -m venv .venv_clean
.\.venv_clean\Scripts\activate
Installer les dépendances :


=> bash

pip install -r requirements.txt



▶️ Utilisation

Option A 
  => Exécution standard (avec pause pour scroller manuellement)

=> powershell

.\run_export_and_convert.ps1

Option B
  => Exécution headless (sans pause, si ton sélecteur est fiable)

=> powershell

.\run_export_and_convert.ps1 -Headless



📂 Organisation des fichiers

- archives/ → contient tous les exports horodatés (.json + .db).

- master.db → base consolidée et dédoublonnée.

- tools/ → scripts utilitaires :

- export_copilot_chat_playwright.py → export JSON

- convert_export_to_sqlite.py → conversion JSON → SQLite

- aggregate_dbs.py → fusion des DB archivées

- dedupe_db.py → suppression des doublons



✅ Exemple de sortie

Code
[1/5] Export JSON...
[2/5] Conversion JSON -> SQLite...
[3/5] Vérification cohérence JSON/DB...
[4/5] Agrégation dans master.db...
[5/5] Dédoublonnage de master.db...
✅ Fin du processus — fichiers archivés, master.db mis à jour et nettoyé


## 📊 Rapports visuels

À la fin de chaque exécution du pipeline (`run_export_and_convert.ps1`), un rapport visuel est généré automatiquement.

- Les graphiques sont sauvegardés dans un dossier horodaté `reports/<YYYYMMDD_HHMMSS>/`.
- Chaque dossier contient au minimum :
  - `messages_par_auteur.png` → histogramme du nombre de messages par auteur (`user` vs `copilot`).
  - `messages_par_date.png` → courbe de l’évolution du volume de messages dans le temps.

### Exemple de sortie console




### Exemple de graphiques générés

*(ces images proviennent du dossier `reports/example/` inclus dans le dépôt)*

- **Messages par auteur**

![Exemple messages par auteur](reports/example/messages_par_auteur.png)

- **Évolution des messages dans le temps**

![Exemple messages par date](reports/example/messages_par_date.png)
