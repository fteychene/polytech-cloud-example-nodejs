# App fournie — TP PaaS Clever Cloud

API REST minimaliste utilisée dans la Partie 1 du TP.

## Endpoints

| Méthode | Route | Description |
|---------|-------|-------------|
| GET | `/health` | Statut de l'app et de la base de données |
| GET | `/items` | Liste tous les items |
| POST | `/items` | Crée un item |

## Variables d'environnement

| Variable | Description |
|----------|-------------|
| `PORT` | Port d'écoute (injecté par Clever Cloud) |
| `POSTGRESQL_ADDON_URI` | URI PostgreSQL (injecté par Clever Cloud) |
| `APP_VERSION` | Version affichée dans `/health` |

## Lancer en local

```bash
cp .env.example .env
# Remplir .env avec vos valeurs locales

npm install
npm run dev
```

## Déployer sur Clever Cloud

```bash
clever create --type node
clever addon create postgresql-addon --plan dev
clever service link-addon <addon-id>
git push clever main
```
