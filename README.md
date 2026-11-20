# Tafl — les échecs vikings

Jeu de tafl à deux joueurs sur le même écran, dans le navigateur : Hnefatafl (règles Wikipédia, Copenhague, Fetlar, 13×13), Tablut, Tawl-bwrdd, Brandubh, Ard-Rí, Alea evangelii, Gwyddbwyll, Fidchell et Halatafl. Toutes les règles sont réglables.

## Jouer en ligne

https://williamloree.github.io/Tafl/

## Jouer sans rien installer

Ouvrir `index.html` dans un navigateur.

## Docker en local

```sh
docker compose up -d --build
```

Le jeu est servi sur http://localhost:8080.

## Image publiée

À chaque push sur `main`, GitHub Actions construit l'image (amd64 et arm64) et la publie sur GHCR :

```
ghcr.io/williamloree/tafl:latest
```

Un tag `vX.Y.Z` publie aussi `X.Y.Z` et `X.Y`.

## Portainer

Stacks → Add stack → Repository (ce dépôt, fichier `docker-compose.portainer.yml`) ou Web editor (coller le fichier). Variables possibles : `TAFL_PORT` (8080 par défaut), `TAFL_TAG` (`latest` par défaut).

Si le dépôt est privé, le paquet GHCR l'est aussi : ajouter le registre `ghcr.io` dans Portainer (Registries) avec votre identifiant GitHub et un token ayant le droit `read:packages`, ou rendre le paquet public dans les réglages du paquet sur GitHub.
