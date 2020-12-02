## --- Jour 2 : Philosophie des mots-de-passe ---

Votre vol décolle dans quelques jours de l'aéroport côtier. Le chemin le plus simple pour aller à la côte depuis icci est le [toboggan](https://fr.wikipedia.org/wiki/Toboggan_(tra%C3%AEneau)).

Le gérant du Magasin de Location de Toboggan du Pôle Nord est dans un mauvais jour. "Quelque chose ne va pas avec nos ordinateurs, on ne peux pas s'authentifier !". Vous demandez si vous pouvez jeter un coup d'oeil.

Leur base de données de mots-de-passe a l'air légèrement corrompue : certains de leurs mots-de-passe n'étaient pas été en accord avec la Politique Officielle des Entreprises de Toboggan qui était applicable à l'époque où ils ont été choisis.

Pour essayer de déboguer le problème, ils ont créé une liste (votre entrée de puzzle) de *mots-de-passe* (selon la base de données corrrompue) et *la politique d'entreprise applicable à l'époque où chaque mot-de-passe a été choisi*.

Par exemple, supposez que vous ayiez la liste suivante :

<pre><code>1-3 a: abcde
1-3 b: cdefg
2-9 c: ccccccccc
</code></pre>

Chaque ligne donne la politique d'un mot-de-passe, puis le mot-de-passe en question. La politique d'un mot-de-passe indique le plus bas et le plus haut nombre de fois qu'une lettre doit appartaître dans un mot-de-passe pour être valide. Par exemple, ``1-3 a`` signifie que le mot-de-passe doit contenir ``a`` au moins ``1`` fois et au plus ``3`` fois.

Dans l'exemple ci-dessus, <code><em>2</code></em> mots-de-passe sont valides. Le mot-de-passe du milieu, ``cdefg``, ne l'est pas : Il ne contient aucune instance de ``b``, mais sa politique en exige au moins ``1``. Le premier et le troisième mots-de-passe sont valides : ils contiennent un ``a`` ou neuf ``c``, chacun restant alors dans les bornes de leurs politiques respectives.

*Combien de mots-de-passe sont valides* selon leurs politiques ?