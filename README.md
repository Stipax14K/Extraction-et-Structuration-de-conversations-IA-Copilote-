# Extraction-et-Structuration-de-conversations-IA-Copilote-
Méthode efficace pour extraire, structurer une ou plusieurs conversations (IA) dans l'objectif d'exploiter le contenu. 

  # Conversation-Indexer

But : pipeline d'extraction, structuration et exploitation des conversations pour produire résumés, actions, décisions et exports structurés.

Structure recommandée :
- /docs
- /src
- /scripts
- /configs
- /notebooks
- /infra
- /.github/workflows
- /tests/fixtures

Prérequis :
- Python 3.10+
- PostgreSQL
- Meilisearch ou Elasticsearch
- Docker (optionnel)
- GitHub Actions (pour CI/ETL)

Quickstart (développement) :
1. Cloner le repo
2. Créer un environnement virtuel Python et installer les dépendances
   ```bash
   python -m venv .venv
   source .venv/bin/activate
   pip install -r requirements.txt
