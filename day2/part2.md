## --- Partie Deux ---

Alors qu'il apparaît que vous avez correctement validé les mots-de-passe, ils n'ont pas l'air d'être ce que le Systeme Officiel d'Authentification des Entreprises de Toboggan attends.

Le gérrant du magasin de location réalise soudainement qu'il vient de vous expliquer accidentellement les règles des politiques de mots-de-passe de son ancien travail, au magasin de location de luges plus bas dans la rue ! En réalité, la Politique Officielle des Entreprises de Toboggan fonctionne un peu différemment.

Chaque politique décrit en fait deux *positions dans le mot-de-passe*, où ``1`` désigne le premier caractère, ``2`` le deuxième caractère, et ainsi de suite (Attention, les Politiques des Entreprises de Toboggan n'utilisent pas le concept "index zéro" !). *Exactement une de ces positions* doit contenir la lettre donnée. D'autres éventuelles occurrences de cette lettre dans le mot-de-passe sont hors du champ d'application des politiques.

Selon la même liste d'exemples qu'au-dessus :
    - <code>1-3 a: <em>a</em>b<em>c</em>de</code> est *valide* : la position ``1`` contient la lettre ``a`` et la position ``3`` ne la contient pas.
    - <code>1-3 b: <em>c</em>d<em>e</em>fg</code> est *invalide* : aucune des positions ``1`` ou ``3``  ne contiennent la lettre ``b``.
    - <code>2-9 c: c<em>c</em>cccccc<em>c</em></code> est *invalide* : les positions ``2`` et ``9`` contiennent toutes les deux la lettre ``c``.

*Combien de mots-de-passe sont valides* selon la nouvelle interprétation des politiques ?