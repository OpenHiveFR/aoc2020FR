## --- Jour 4 : Traitement de passeport ---

Vous arrivez à l'aéroport et réalisez une fois là-bas que vous avez emporté votre Carte d'Identité du Pôle Nord au lieu de votre passeport. Même si ces documents sont extrêmement similaires, la Carte d'Identité du Pôle Nord n'est pas distribuée par un pays et n'est donc pas un document valide pour voyager dans la majorité du monde.

Apparemment, vous n'êtes pas le seul à avoir des problèmes : une très longue file d'attente s'est formée devant les scanners automatiques de passeports, et le délai pourrait gêner votre itinéraire de voyage.

Grâce à la sécurité discutable du réseau de l'aéroport, vous vous rendez compte que vous pourriez peut être régler ces deux problèmes en même temps.

Les scanners automatiques de passeports sont lents parce qu'ils ont du mal à *détecter quels passeports ont les champs requis*. Les champs attendus sont les suivants :

- ``byr`` ("Birth of Year", l'année de naissance)
- ``iyr`` ("Issue Year", l'année de distribution)
- ``eyr`` ("Expiration Year", l'année d'expiration)
- ``hgt`` ("Height", la taille)
- ``hcl`` ("Hair Color", la couleur des cheveux)
- ``ecl`` ("Eye Color", la couleur des yeux)
- ``pid`` ("Passport ID", l'identifiant du passeport)
- ``cid`` ("Country ID", l'identifiant du pays)

Les données des passeports sont validés en fichiers groupés (l'entrée de votre puzzle). Chaque passeport est représenté par une séquence de paires ``clef:valeur`` séparées par des espaces ou des sauts de ligne. Les passeports différents sont séparés par des lignes vides.

Voici un exemple de fichier groupé content quatre passeports :

```
ecl:gry pid:860033327 eyr:2020 hcl:#fffffd
byr:1937 iyr:2017 cid:147 hgt:183cm

iyr:2013 ecl:amb cid:350 eyr:2023 pid:028048884
hcl:#cfa07d byr:1929

hcl:#ae17e1 iyr:2013
eyr:2024
ecl:brn pid:760753108 byr:1931
hgt:179cm

hcl:#cfa07d eyr:2025 pid:166559648
iyr:2011 ecl:brn hgt:59in
```

Le premier passeport est *valide* (tous les huit champs sont présents). Le second passeport est *invalide* (il manque le champ ``hgt``, la taille).

Le troisième passeport est intéressant ; le *seul champ manquant* est ``cid``, on dirait donc des données provenant d'une Carte d'Identité du Pôle Nord, pas un passeport du tout ! À tous les coups, ça n'embêterait personne si vous faisiez en sorte que le système ignore temporairement les champs ``cid`` manquants. Traitez ce "passeport" comme *valide*.

Le quatrième passeport manque de deux champs : ``cid`` et ``byr``. Un ``cid`` manquant ne pose pas de problème, mais manquer de n'importe quel autre champ rend le passeport *invalide*.

Selon les règles ci-dessus, votre système amélioré considérerait <code><em>2</em></code> passeports valides.

Comptez le nombre de passeports *valides* (ceux qui ont tous les champs requis). Traitez ``cid`` comme un champs optionnel. *Dans votre fichier groupé, combien de passeports sont valides ?*