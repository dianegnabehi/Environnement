# Environnement

Simulation en Python des températures d'une journée complète pour chacune des quatre saisons. Le script combine une plage thermique saisonnière, une onde sinusoïdale et une part d'aléatoire pour produire un relevé toutes les 30 minutes, affiché en temps réel en degrés Celsius. Projet IA & Machine Learning, 42 Paris.

## Aperçu

`environment.py` simule l'évolution de la température sur 24 heures à partir d'une
saison choisie par l'utilisateur. La température de départ est tirée au hasard dans
la plage de la saison, puis chaque tranche de 30 minutes applique :

- une variation sinusoïdale (amplitude de 5 °C) pour reproduire le cycle jour/nuit ;
- un bruit aléatoire de ±1 °C pour l'irrégularité naturelle.

Les 48 relevés sont arrondis à deux décimales et affichés un par un, avec une pause
d'une seconde entre chaque ligne pour simuler le temps réel (environ 48 secondes au
total).

## Prérequis

- Python 3.8 ou supérieur
- Aucune dépendance externe (uniquement `time`, `random` et `math`)

## Installation

```bash
git clone https://github.com/<utilisateur>/Environnement.git
cd Environnement
```

## Utilisation

```bash
python3 environment.py
```

Le programme demande la saison, par mot-clé ou par numéro :

| Saison | Mot-clé          | Numéro | Plage de base |
| ------ | ---------------- | ------ | ------------- |
| Hiver  | `winter`         | `1`    | 0 – 10 °C     |
| Printemps | `spring`      | `2`    | 10 – 20 °C    |
| Été    | `summer`         | `3`    | 20 – 30 °C    |
| Automne | `autumn` / `fall` | `4`   | 10 – 20 °C    |

Exemple :

```text
Enter the season (winter, spring, summer, autumn) or (1, 2, 3, 4): 3
 1: 24.87 °C
 2: 25.31 °C
 3: 26.04 °C
...
48: 23.79 °C
```

Toute autre valeur lève une `ValueError` affichée proprement dans la console.

## Structure du projet

```text
.
├── environment.py   # Script de simulation
├── README.md        # Documentation du projet
└── .gitignore       # Fichiers exclus du dépôt
```

## Fonctions principales

| Fonction | Rôle |
| -------- | ---- |
| `get_season_temperature_range(season)` | Renvoie la plage `(min, max)` associée à une saison. |
| `simulate_temperature(season)` | Génère et affiche les 48 relevés d'une journée. |
| `main()` | Point d'entrée : lit la saison au clavier et gère les erreurs. |

## Auteur

Diane Gnabehi —  projet 42 Paris.

## Licence

Ce projet est distribué sous licence MIT — voir le fichier [LICENSE](LICENSE).
