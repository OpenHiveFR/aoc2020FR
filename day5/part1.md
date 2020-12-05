## --- Jour 5 : Embarquement Binaire ---

Vous embarquez dans votre avion et découvrez un nouveau problème : vous avez perdu votre billet d'embarquement ! Vous ne savez pas quel siège est le vôtre, et tous les agents de bord sont occupés par la vague de passagers ayant soudainement passé les contrôles de passeports.

Vous écrivez rapidement un programme pour utiliser la caméra de votre téléphone pour scanner tous les billets à proximité (l'entrée de votre puzzle) ; peut-être que vous serez capable de trouver votre place par élimination.

Au lieu de [zones ou de groupes](https://www.youtube.com/watch?v=oAHbLRjF0vo), cette compagnie aérienne utilise *un partitionnement binaire de l'espace* pour placer les passagers. Un siège peut être désigné comme ``FBFBBFFRLR``, où ``F`` signifie "front" (devant), ``B`` siginifie "back" (arrière), ``L`` signifie "left" (gauche), et ``R`` signifie "right" (droite).

Les 7 premiers caractères seront soit ``F`` ou ``B``. Ceux-ci désignent exactement l'une des *128 lignes* de l'avion (numérotées de ``0`` à ``127``). Chaque lettre vous montre dans quelle moitié de la région se trouve le siège en question. Démarrez en considérant toute la liste des lignes : la première lettre indique si le siège est *à l'avant* (lignes de ``0`` à ``63``) ou *à l'arrière* (lignes de ``64`` à ``127``). La lettre suivante indique dans quelle moitié de la région retenue se trouve le siège, et ainsi de suite jusqu'à ce que vous vous retrouviez avec une seule ligne.

Par exemple, prenez les sept premiers caractères de ``FBFBBFFRLR`` :

- Démarrez en considérant la totalité des lignes de ``0`` à ``127``.
- ``F`` indique qu'il faut prendre la *moitié basse*, gardant les lignes de ``0`` à ``63``.
- ``B`` indique qu'il faut prendre la *moitié haute*, gardant les lignes de ``32`` à ``63``.
- ``F`` indique qu'il faut prendre la *moitié basse*, gardant les lignes de ``32`` à ``47``.
- ``B`` indique qu'il faut prendre la *moitié haute*, gardant les lignes de ``40`` à ``47``.
- ``B`` garde les lignes de ``44`` à ``47``.
- ``F`` garde les lignes de ``44`` à ``45``.
- Le ``F`` final garde la ligne la plus basse des deux, *la ligne ``44``*

Les trois derniers caractères seront soit ``L`` soit ``R``. Ceux-ci indiquent exactement l'une des *8 colonnes* de sièges de l'avion (numérotés de ``0`` à ``7``). Le même processus qu'au-dessus s'applique à nouveau, cette fois en seulement trois étapes. ``L`` indique qu'il faut garder la *moitié basse*  tandis que ``R`` indique qu'il faut garder la *moitié haute*.

Par exemple, prenez cette fois les 3 derniers caractères de ``FBFBBFFRLR`` :

- Démarrez en considérant la totalité des colonnes de ``0`` à ``7``.
- ``R`` indique qu'il faut garder la *moitié haute*, gardant les colonnes de ``4`` à ``7``.
- ``L`` indique qu'il faut garder la *moitié basse*, gardant les colonnes de ``4`` à ``5``.
- Le ``R`` final garde la plus haute colonne des deux, la *colonne ``5``*.

Ainsi, décoder ``FBFBBFFRLR`` révèle que le siège qu'il désigne se trouve *ligne ``44``, colonne ``5``*.

Chaque siège possède également un *Identificateur de siège* (ID) : multipliez sa ligne par 8, puis additionnez-lui la colonne. Dans cet exemple, le siège à pour ID <code>44 * 8 + 5 = <em>357</em></code>.

Voici quelques autres billets d'embarquement :

- ``BFFFBBFRRR`` : ligne ``70``, colonne ``7``, ID ``567``.
- ``FFFBBBFRRR`` : ligne ``14``, colonne ``7``, ID ``119``.
- ``BBFFBBFRLL`` : ligne ``102``, colonne ``4``, ID ``820``.

Pour vérifier que vos données sont bonnes, vérifiez vote liste de billets d'embarquement. *Quel est le plus grand ID sur un billet d'embarquement ?* 