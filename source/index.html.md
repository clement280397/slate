---
title: API Reference

language_tabs:
  - JSON


toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Rail commander

Welcome to the Rail Commander API! You can use our API to access Rail Commander  API endpoints, which can get information on various trips, users, and statistics in our database.

Our API just respond some *JSON* content, depending on your request.



# Users

## Add a user
> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  }
]
```
This endpoint makes you able to add a user:
### HTTP Request

`POST /users`

## Update a user
> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  }
]
```
This endpoint makes you able to update an user:
### HTTP Request

`PUT /users`

## Get a user
> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  }
]
```
Retourne un JSON user
Prend en paramètre l'adresse mail de l'utilisateur
### HTTP Request

`POST : /users/login`

## Update user like
> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  }
]
```
En BDD cette valeur (number) est initialisée à 1.
Prend en paramètre un json avec l'adresse mail de l'utilisateur et la valeur du like (1 ou 0).
Met à jour cette valeur en BDD.
### HTTP Request

`PUT : /users/like`

## Get user like
> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  }
]
```
Ne prend pas de paramètre
Retourne la valeur dans un json (1 data suffit).
Cette data est le pourcentage de like total.
### HTTP Request

`GET : /users/likes`

## Get user email
> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  }
]
```
Prend en paramètre une adresse mail
Retourne une adresse mail si l'email existe déjà en BDD
Retourne false ou null si l'email n'existe pas (ton choix)
### HTTP Request

`GET : /user/email`

## Get number of users
> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  }
]
```
Retourne le nombre total d'utilisateurs inscrits
### HTTP Request

`GET : /users/number`

# Trips

## Get All Trips
> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  }
]
```
Retourne un JSON avec la liste des voyages
### HTTP Request
`GET : /trips`

## Get most visited town
> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  }
]
```
Ne prend pas de paramètres.
Retourne une valeur au format JSON (cle = mostVisitedTown).
Contient une string avec la ville la plus fréquentée.
Calcul : +1 pour chaque appel de cette ville en tant que ville de destination dans la liste des tickets.


### HTTP Request
`GET : /trips/most-visited-town`

## Get most bought travel
> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  }
]
```
Ne prend pas de paramètres.
Retourne une valeur au format JSON (cle = mostBoughtTravel).
Contient une string avec le voyage le plus acheté. (Ville de départ - Ville d'arrivée).
Calcul : +1 pour chaque appel de ce voyage dans la liste des tickets.


### HTTP Request
`GET : /trips/most-bought-travel`

# Carts

## Add a cart
> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  }
]
```
Ajoute un achat ou plusieurs achats en BDD
Prend en paramètre un JSON qui contient :
1. L'email de l'utilisateur (UNIQUE)
2. Un tableau avec la référence des voyages (ID/UNIQUE) et la quantité

### HTTP Request
`POST : /cart`
