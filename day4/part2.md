## --- Partie Deux ---

La file d'attente avance plus rapidement maintenant, mais avez succinctement entendu l'équipe de sécurité de l'aéroport parler du fait que des passeports avec des données invalides passent au travers des scanners. Vous feriez mieux d'ajouter une validation des données, et vite !

Vous pouvez continuer à ignorer le champs ``cid``, mais tout autre champs a des règles stricte dictant quelles valeurs sont valides pour la validation automatique :

- ``byr`` ("Birth of Year", l'année de naissance) - quatre chiffres; au moins ``1920`` et au plus ``2002``.
- ``iyr`` ("Issue Year", l'année de distribution) - quatre chiffres; au moins ``2010`` et au plus ``2020``.
- ``eyr`` ("Expiration Year", l'année d'expiration) - quatre chiffres; au moins ``2020`` et au plus ``2030``.
- ``hgt`` ("Height", la taille) - Un nombre suivi soit par ``cm`` soit par ``in`` :
    - Si c'est ``cm``, le nombre doit être au moins ``150`` et au plus ``193``.
    - Si c'est ``in``, le nombre doit être au moins ``59`` et au plus ``76``.
- ``hcl`` ("Hair Color", la couleur des cheveux) - un ``#`` suivi par exactement six caractères ``0``-``9`` ou ``a``-``f``.
- ``ecl`` ("Eye Color", la couleur des yeux) - Exactement un mot parmi : ``amb``, ``blu``, ``brn``, ``gry``, ``grn``, ``hzl`` ou ``oth``. 
- ``pid`` ("Passport ID", l'identifiant du passeport) - un nombre a neuf chiffres, incluant d'éventuels zéros en tête.
- ``cid`` ("Country ID", l'identifiant du pays) - Ignoré, manquant ou non.

Votre travail est de compter les passeports pour lesquels tous les champs requis sont *présents* et *valides* selon les règles ci-dessus. Voici quelques exemples de valeurs :

```
byr valide:   2002
byr invalide: 2003

hgt valide:   60in
hgt valide:   190cm
hgt invalide: 190in
hgt invalide: 190

hcl valide:   #123abc
hcl invalide: #123abz
hcl invalide: 123abc

ecl valide:   brn
ecl invalide: wat

pid valide:   000000001
pid invalide: 0123456789
```

Voici quelques passeports invalides :

```
eyr:1972 cid:100
hcl:#18171d ecl:amb hgt:170 pid:186cm iyr:2018 byr:1926

iyr:2019
hcl:#602927 eyr:1967 hgt:170cm
ecl:grn pid:012533040 byr:1946

hcl:dab227 iyr:2012
ecl:brn hgt:182cm pid:021572410 eyr:2020 byr:1992 cid:277

hgt:59cm ecl:zzz
eyr:2038 hcl:74454a iyr:2023
pid:3556412378 byr:2007
```

Voici quelques passeports valides :

```
pid:087499704 hgt:74in ecl:grn iyr:2012 eyr:2030 byr:1980
hcl:#623a2f

eyr:2029 ecl:blu cid:129 byr:1989
iyr:2014 pid:896056539 hcl:#a97842 hgt:165cm

hcl:#888785
hgt:164cm byr:2001 iyr:2015 cid:88
pid:545766238 ecl:hzl
eyr:2022

iyr:2010 hgt:158cm hcl:#b6652a ecl:blu byr:1944 eyr:2021 pid:093154719
```

Comptez le nombre de passeports *valides* (ceux ayant tous les champs requis *avec des valeurs valides*). Continuez de compter le champ ``cid`` comme optionnel. *Dans votre fichier groupé, combien de passeports sont valides ?*