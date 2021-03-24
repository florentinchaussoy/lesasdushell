Le chiffrement, c'est quoi exactement ?
=======================================

* * * * *

[CYBERSÉCURITÉ](https://lesasdushell.fr/posts/category/cybersecurite/) / SAMEDI, OCTOBRE 19TH, 2019

Commençons par répondre à la première des questions qu'il convient de se poser : qu'est-ce que le chiffrement ? Pour faire simple, on pourrait dire qu'il s'agit de rendre illisible de la donnée, comme par exemple un fichier, excepté pour son destinataire. Pour cela, on utilise une clef de chiffrement.

Cette donnée peut prendre plusieurs formes : un message, une image, un fichier quelconque ou même votre disque dur complet. Le chiffrement a ainsi pour objectif la protection des données, notamment lorsqu'elles doivent être transportées ou transmises. Dans ce dernier cas, le messager (un prestataire ou un fournisseur d'accès par exemple) ne peut pas en prendre connaissance, seulement son destinataire.

Une analogie, qui n'est pas tout à fait correcte, mais qui est souvent utilisée dans le cadre de l'envoi d'un email chiffré, est celle de l'enveloppe pour le courrier. En effet, lorsque vous placez une lettre dans une enveloppe, le facteur peut la transporter sans en lire le contenu, contrairement à une carte postale. Chiffrer un message revient donc à placer une lettre dans une enveloppe.

### Cryptologie, Chiffrer, Déchiffrer, Décrypter : les bases

Avant d'aller plus loin il nous faut expliquer certains termes qui peuvent parfois être l'objet de confusions, et vous éviter quelques problèmes souvent rencontrés lorsque l'on parle de chiffrement.

Il y a effectivement des mots que l'on peut utiliser, d'autres non. Et certains que l'on accepte (mais seulement dans certains cas) :

-   **Chiffrer :** il s'agit de rendre un document illisible avec une clef de chiffrement, excepté pour son destinataire
-   **Déchiffrer :** il s'agit de rendre lisible un document chiffré, en ayant connaissance de la clef de chiffrement
-   **Décrypter :** il s'agit de rendre lisible un document chiffré, sans avoir connaissance de la clef de chiffrement
-   **Cryptologie :** il s'agit de la science du secret, c'est son sens étymologique. Elle regroupe plusieurs disciplines :
    -   La cryptographie : vise à étudier comment protéger par le chiffrement
    -   La cryptanalyse : vise à analyser les méthodes de chiffrement pour les casser

-   **Crypter :** cela n'existe pas
-   **Chiffrage :** cela existe, dans le domaine de la comptabilité ou [de la musique](https://fr.wikipedia.org/wiki/Chiffrage_des_accords)

Dans son [référentiel de sécurité](https://www.ssi.gouv.fr/uploads/2014/11/RGS_v-2-0_B1.pdf), l'Agence nationale de sécurité des systèmes d'information (ANSSI) indique pour sa part que « *le seul terme admis en français est celui de chiffrement. On entend cependant souvent parler de « cryptage » qui est un anglicisme, voire de « chiffrage », mais ces mots sont incorrects. L'opération inverse du chiffrement est le déchiffrement. On désigne par « décryptage », ou « décryptement », l'opération qui consiste à retrouver le clair correspondant à un chiffré donné sans connaître la clé secrète, après avoir trouvé une faille dans l'algorithme de chiffrement* ».

Notez une chose : si tous les dérivés de « Crypter » n'ont aucun sens (puisque l'on ne peut pas chiffrer sans clef), il existe une exception, [validée par l'Académie Française](https://fr.wikipedia.org/wiki/Discussion:Chiffrement#Copie_de_la_lettre_pr.C3.A9sente_dans_cryptage_.28la_fusion_a_.C3.A9t.C3.A9_effectu.C3.A9e.2C_voir_l.27historique_pour_les_auteurs.29), celui des « chaînes cryptées ». C'est un terme le plus souvent utilisé pour parler de chaînes à péage, comme Canal+.