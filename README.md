# Guichet ML

API FastAPI qui détecte la langue d'un texte (fr / en / ar), avec un fournisseur simulé (mode MOCK) utilisable hors ligne.

## Installation (Windows PowerShell)

```powershell
py -m venv .venv
.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
copy .env.example .env
```

## Lancer l'API

```powershell
uvicorn app.main:app --reload
```

Puis ouvrir http://127.0.0.1:8000/docs

## Tests

```powershell
pytest -q
```

## Routes

- `GET /health` : état du service, mode et fournisseur
- `POST /detect-language` : corps `{"text": "..."}` (3 à 1000 caractères)

Codes : 200 (succès), 422 (requête invalide), 503 (fournisseur indisponible).