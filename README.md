## Introduction
Si comme moi vous vous souciez de la santé de la planète je vous invite à lire ce qui suit.

Lors de l'envoi de mails contenant des images intégrées dans le corps du texte, celles-ci sont généralement transférées dans leurs dimensions initiales. Peu importe la source de l'image (copie d'écran, photo prise par votre smartphone, récupérée sur le net, etc.), même si vous en réduisez les dimensions dans votre message cela ne fera pas "maigrir" le fichier sous-jacent. Ceci n'est pas spécifique aux mails ; le principe est identique pour les images insérées dans des pages web ou dans des documents bureautiques par exemple.

Rares sont les utilisateurs qui en ont conscience mais il est important de savoir que cela engendre une consommation inutile de diverses ressources :
- Bande passante réseau : le poids du fichier restant inchangé malgré la réduction de sa taille à l'affichage, le transfert de l'image utilise inutilement plus de bande passante que nécessaire, à l'envoi comme à la réception.
- Stockage : sur les serveurs de messagerie et sur les appareils des utilisateurs, les images occupent de l'espace de stockage. Si les images sont envoyées et stockées à leur taille native, cela peut entraîner une utilisation inefficace de l'espace de stockage.
- Processeur/mémoire : lorsqu'un destinataire ouvre le message, le client de messagerie (ou le navigateur, dans le cas d'un accès de type webmail) doit redimensionner l'image pour l'afficher aux dimensions définies par l'expéditeur. Si l'image est envoyée à sa taille native, cela nécessite plus de ressources processeur et mémoire pour effectuer ce redimensionnement sur chaque poste client, ce qui peut ralentir le processus d'affichage ainsi que les autres traitements en cours sur l'appareil. Sensation de lenteur qui peut aboutir à un renouvellement précoce de la machine.

In fine, en utilisant plus de bande passante, d'espace de stockage et de ressources processeur, cela contribue à une empreinte carbone plus importante étant donné que la transmission de données via le réseau et l'utilisation de ressources informatiques nécessitent de l'énergie.

En réduisant la taille des images avant de les insérer dans un message on peut optimiser l'utilisation des ressources, réduire la consommation de bande passante, minimiser l'occupation d'espace de stockage et contribuer ainsi à une approche plus efficace et respectueuse de l'environnement dans la communication par e-mail. C'est dans ce contexte que des outils de compression et de visualisation des informations sur les images peuvent jouer un rôle crucial en vue de réduire notre empreinte carbone en minimisant l'usage de matières premières nécessaires pour produire l'électricité, fabriquer les équipements, refroidir les serveurs, etc...).

## Présentation de l'outil
Face à cette aberration, j'ai développé ce petit composant pour Outlook afin de sensibiliser les utilisateurs quant à aux gâchis évitables que cela induit et que chacun prenne conscience qu'il doit contribuer à l'effort nécessaire pour sauver la planète.

Cet outil affiche un récapitulatif des images contenues dans un mail, incluant les dimensions dans lesquelles elles sont affichées, leurs dimensions natives et leur poids (lorsque l'information est disponible). Si les dimensions natives d'une image sont supérieures à celles de son affichage, cela signifie que des économies auraient pu être faites en réduisant l'image avant de l'insérer dans le mail. Mais il est également possible, en appliquant une méthode suggérée par l'outil, de réduire l'image après son insertion dans le message.

L'analyse est accessible tant pour les mails déjà reçus/envoyés que lors de la phase de rédaction d'un message.

## Mise en œuvre de l'outil
Elle est très simple puisqu'il suffit, lorsqu'un message est affiché, de cliquer sur le bouton "Afficher les informations (ImageInfo)" présent dans la barre des outils du ruban "Accueil" d'Outlook (en mode webmail le bouton se trouve dans le menu des applications). Un volet s'ouvre alors et présente un tableau contenant les images insérées dans ledit message.

Lorsque le composant est utilisé en mode rédaction (d'un message) et qu'il décèle la présence d'images surdimensionnées, le tableau est accompagné de conseils pour réduire le poids des images.

## Précisions techniques
L'outil distingue plusieurs types d'images présentes dans un message :
- intégrée : l'image est présente directement dans le corps du message, sous forme d'une chaîne encodée en base64
- jointe : l'image est présente en tant que fichier joint
- externe : l'image n'est pas réellement présente dans le message, elle est récupérée sur un serveur distant (internet ou intranet)

## Problèmes connus
- impossibilité d'obtenir le poids des images externes
- dans certains cas, Outlook ne donne pas accès aux dimensions natives
- dans certains cas, Outlook ne permet pas de déterminer avec certitude la source d'une image. Dans ce cas l'outil tente le rapprochement entre les images affichées/jointes par un traitement sur le ratio de celles-ci, des erreurs sont alors possibles. Dans ce cas une mention est ajoutée pour en informer l'utilisateur.

Merci pour votre attention et vos actions pour préserver la planète.