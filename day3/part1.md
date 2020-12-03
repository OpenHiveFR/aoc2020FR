## --- Jour 3 : La Trajectoire du Toboggan ---

Une fois le problème d'authentification du toboggan résolu, vous partez en direction de l'aéroport. Bien que voyager en toboggan est facile, ce n'est clairement pas sûr : leur maniabilité est très basse et la zone est couverte d'arbres. Vous devrez trouver quel angle vous fera rencontrer le moins d'arbres.

À cause de la géologie locale, les arbres de cette zone poussent exactement sur les coordonnées d'une grille. Vous créez une carte (votre entrée de puzzle) de la zone, en notant les carrés vides (``.``) et les arbres (``#``). Par exemple :

```
..##.......
#...#...#..
.#....#..#.
..#.#...#.#
.#...##..#.
..#.##.....
.#.#.#....#
.#........#
#.##...#...
#...##....#
.#..#...#.#
```

Ce ne sont cependant pas les seuls arbres : à cause de quelque chose à propos de laquelle vous avez lu un article un jour impliquant la génétique arboricole et la stabilité des biomes, le même schéma se répète vers la droite beaucoup de fois :

<pre><code><em>..##.......</em>..##.........##.........##.........##.........##.......  --->
<em>#...#...#..</em>#...#...#..#...#...#..#...#...#..#...#...#..#...#...#..
<em>.#....#..#.</em>.#....#..#..#....#..#..#....#..#..#....#..#..#....#..#.
<em>..#.#...#.#</em>..#.#...#.#..#.#...#.#..#.#...#.#..#.#...#.#..#.#...#.#
<em>.#...##..#.</em>.#...##..#..#...##..#..#...##..#..#...##..#..#...##..#.
<em>..#.##.....</em>..#.##.......#.##.......#.##.......#.##.......#.##.....  --->
<em>.#.#.#....#</em>.#.#.#....#.#.#.#....#.#.#.#....#.#.#.#....#.#.#.#....#
<em>.#........#</em>.#........#.#........#.#........#.#........#.#........#
<em>#.##...#...</em>#.##...#...#.##...#...#.##...#...#.##...#...#.##...#...
<em>#...##....#</em>#...##....##...##....##...##....##...##....##...##....#
<em>.#..#...#.#</em>.#..#...#.#.#..#...#.#.#..#...#.#.#..#...#.#.#..#...#.#  ---></code></pre>

Vous commencez dans le carré vide (``.``) dans le coin en haut à gauche et devez atteindre le fond (en dessous de la ligne la plus basse de votre carte).

Le toboggan peut uniquement suivre quelques pentes spécifiques (vous en avez pris un moins cher qui préfère les nombres rationnels) ; commencez par *compter tous les arbres* que vous rencontreriez en utilisant la pente *droite 3, bas 1* :

À partir de votre position de départ en haut à gauche, vérifiez la position se trouvant à droite de 3 cases et en-dessous d'1 case. Ensuite, vérifiez la position se trouvant à droite de cette nouvelle case de 3 cases et en dessous d'1 case, et ainsi de suite jusqu'à ce que vous ayez atteint le fond de la carte.

Les endroits que vous devriez vérifier dans l'exemple ci-dessus sont marqués ici d'un <code><em>O</em></code> là où se trouve un carré vide et d'un <code><em>X</em></code> là où se trouve un arbre.

<pre><code>..##.........##.........##.........##.........##.........##.......  --->
#..<em>O</em>#...#..#...#...#..#...#...#..#...#...#..#...#...#..#...#...#..
.#....<em>X</em>..#..#....#..#..#....#..#..#....#..#..#....#..#..#....#..#.
..#.#...#<em>O</em>#..#.#...#.#..#.#...#.#..#.#...#.#..#.#...#.#..#.#...#.#
.#...##..#..<em>X</em>...##..#..#...##..#..#...##..#..#...##..#..#...##..#.
..#.##.......#.<em>X</em>#.......#.##.......#.##.......#.##.......#.##.....  --->
.#.#.#....#.#.#.#.<em>O</em>..#.#.#.#....#.#.#.#....#.#.#.#....#.#.#.#....#
.#........#.#........<em>X</em>.#........#.#........#.#........#.#........#
#.##...#...#.##...#...#.<em>X</em>#...#...#.##...#...#.##...#...#.##...#...
#...##....##...##....##...#<em>X</em>....##...##....##...##....##...##....#
.#..#...#.#.#..#...#.#.#..#...<em>X</em>.#.#..#...#.#.#..#...#.#.#..#...#.#  ---></code></pre>

Dans cet exemple, traverser la zone en utilisant la pente prédéfinie (droite 3, bas1) causerait la rencontre de <code><em>7</code></em> arbres.

Démarrant au coin en haut à gauche de votre carte et suivant une pente de droite 3 et bas 1, *combien d'arbres rencontreriez vous ?*