## UAC
(*Unified Access Control*)
(Contrôle d’Accès Unifié)

UAC est une solution de contrôle d’accès réseau (NAC*) développé par Juniper.
Unified Access Control (UAC) crée et propage les stratégies dynamiques en fonction de l'identité et du rôle de l'utilisateur, du type d'équipement et de son intégrité, ainsi que de son emplacement.
Juniper le présente comme une solution qui assure un contrôle d'accès au réseau pour les environnements réseau, cloud* et d'applications les plus complexes, (…).
L'accès au réseau, au cloud et aux applications est basé sur les identités, en sécurisant l'accès des équipements personnels, ce qui améliore la gestion, la visibilité et le contrôle de l'accès au réseau.(…)
Unified Access Control s'appuie sur les normes de l'industrie, notamment 802.1X, RADIUS*, IPsec et IF-MAP de TNC, qui permettent l'intégration de la solution UAC à n'importe quel équipement de sécurité et réseau tiers . 
Voir NAC.

## UCS
(*Universal Character Set*)
(Jeu de caractères universel)

Jeu de caractères universel défini par l’ISO 10646, permettant de coder l’ensemble des systèmes d’écriture (ou quasiment) pour faciliter leur traitement par les ordinateurs.
Voir ASCII, Unicode, UTF.

## UDP
(*User Datagram Protocol*)

Protocole de transport (couche 4 du modèle OSI* ou en-core couche transport du modèle TCP/IP*), il est dit « non orienté connexion » (à l’inverse de TCP*).
UDP ne fournit donc aucune information de contrôle de flux, ni de mécanisme de correction d’erreur.
Le protocole est décrit dans la RFC* 768.
Avec TCP, UDP est le protocole de transport le plus utilisé d’Internet.
Sa simplicité en fait un protocole très utile pour l’échange rapide de données qui ne craignent pas la perte d’un nombre limité de paquets* (il est par exemple utilisé pour la voix sur IP*).
Les informations de l’en-tête UDP sont donc très limitées, et regroupées dans quatre champs distincts représentés ci-dessous :

32 bits
Port source	Port destination
Taille	Somme de contrôle (checksum)
Données

* Port Source (16 bits) : indique le port source du pa-quet ;
* Port destination (16 bits) : le port destination du pa-quet ;
* Taille (16 bits) : indique la taille du segment complet UDP (données inclues) ;
* Checksum (16 bits) : Le checksum ou somme de con-trôle indique l’intégrité du paquet reçu. 

## UIT - Union Internationale des Télécommunications 
(*ITU – International Telecommunication Union*)

Organisme international qui regroupe 193 pays et environ 700 entités du secteur privé ou du monde universitaire.
L’UIT est l’organisme des Nations Unies en charge des technologies de l’information et de la communication (TIC).
Il est chargé de promouvoir et de coordonner le développement des TIC et est « déterminé à connecter tous les habitants de la planète ».
En outre, l’UIT attribue des fréquences radioélectriques et des orbites de satellite.
Il élabore des normes techniques qui permettent l’interconnexion des réseaux. Voir le site officiel http://www.itu.int

## UML
(*Unified Modeling Language*)
(Langage de modélisation unifié)

Langage graphique de modélisation utilisé pour la conception de logiciels, UML permet de représenter, à l’aide de diagrammes, un logiciel en cours de développement.

Le langage comprend 14 diagrammes regroupés en trois familles distinctes. On trouve ainsi :
* des diagrammes structurels (ou statiques), qui permet-tent de représenter des classes ou des objets ;
* des diagrammes comportementaux, pour représenter les activités, les états ou les interactions entre les utilisa-teurs et le système ;
* et les diagrammes d’interactions dynamiques, qui mo-délisent les échanges entre objets, ou les représentions sé-quentielles des interactions.

UML est un standard de l’OMG – Object Management Group très utilisé pour la conception d’applications orientées objet.
Voir Programmation orientée objet.

## UMTS
(*Universal Mobile Telecommunication System*)
(Système de télécommunication mobile universel)

UMTS est une norme de télécommunication mobile pour les systèmes de radiocommunication dits de troisième génération (3G).
Cette norme a été retenue en Europe. Elle reprend les spécifications d’IMT 2000*.
UMTS, basée sur une technologie d’accès radio de type WCDMA*, permet d’élargir la gamme de service en intégrant les échanges de données et d’images en plus de la voix.
Ces services sont rendus possibles par une augmentation de la bande passante* de chaque cellule qui dérive de l’amélioration du codage des signaux et permet la réutilisation de fréquences entre cellules adjacentes sans interférences.

##UMTS -TDD
(*Universal Mobile Telecommunication System Time Division Duplex*)

Variante d’UMTS qui propose en lieu et place de la division par fréquence (FDD*) du WCDMA*, une division temporelle.
UMTS-TDD utilise deux bandes de fréquences séparées du spectre (1900 – 1929 MHz et 2010 – 20125 MHz).
En France, la plupart des fréquences UMTS-TDD ne sont pas accessibles au public et réservées à un usage professionnel.

## UNI
(*User to Network Interface*)

UNI est un protocole de signalisation* dans les réseaux ATM*.
Il permet d’établir une connexion entre deux utilisateurs terminaux du réseau.
UNI est normalisé par l’ISO sous l’appellation Q2931 UNI Signalling.
Le user to network interface désigne également l’interface de raccordement entre un commutateur ATM* et un utilisateur.
L’interface de raccordement entre les commutateurs ATM est appelée NNI* Network to Network Interface.
Voir NNI.

## Unicast
(Envoi individuel)

Unicast est un mode de transmission point à point* qui consiste à communiquer entre deux hôtes distincts d’un réseau identifiés par leur adresse (d’un émetteur unique vers un destinataire unique).
L’adresse IP* étant unique elle permet ce mode de transmission.
Il existe d’autres modes de transmission dans un réseau : le multicast (diffusion d’un émetteur vers un groupe de récepteurs) et le broadcast (diffusion d’un émetteur vers tous les récepteurs potentiels). 
Voir Multicast, Broadcast.

## Unicode
Pour permettre à un processeur d’interpréter un caractère, il est nécessaire de le coder et de lui faire correspondre un nom unique et un nombre entier positif qui sera lui même manipulé sous forme binaire (d’ou le mécanisme de transformation UTF).
Dans ce contexte, Unicode est un standard qui assure le codage de caractères dans n’importe quel système d’écriture au niveau mondial.
Unicode permet le codage d’environ 110 000 caractères différents, il est compatible avec la norme ISO 10646 (il permet de coder le jeu universel de caractères – Universal Character Set – UCS).
Voir ASCII, UTF.

## URI
(*Uniform Resource Identifier*)
(Identificateur Uniforme de Ressources)

L’URI est un chaine de caractères qui permet d’identifier une ressource sur un réseau.
L’URI est présentée dans le RFC* 3986. 
Elle est très répandue pour définir et localiser une ressource sur Internet. 
Il existe deux types d’URI :
L’URL, Uniform ressource locator  (voir ci-dessous) et l’URN, Uniform ressource name.
Voir URL, URN.

## URL
(*Uniform Resource Locator*)
(Adresse réticulaire – adresse universelle)

L’URL est une URI*, donc un format de nommage commun, qui désigne une ressource sur Internet.
Il permet de « localiser » cette ressource et ainsi d’y accéder.
Le format d’une URL est décrit une première fois en 1994 dans la RFC*1738.

## URN
(*Uniform Ressource Name*)

Forme particulière d’URI* qui permet d’identifier une ressource dans un espace de nommage et non par sa localisation.
L’URN permet donc de parler d’une ressource ou d’un objet sans avoir d’information sur sa localisation (dans un réseau) ou le moyen d’y accéder.
Le code ISBN est un exemple d’URN pour les livres. Il permet de classer les ouvrages dans une base de noms sans pour autant utiliser les titres.
L’ISBN est plus simple à manipuler.

## USB
(*Universal Serial Bus*)
(Bus série universel)

Interface entrée-sortie d’un équipement basé sur l’architecture série .
Le port USB permet donc la connexion de nombreux périphériques différents.
Il existe trois versions d’USB en fonction de l’évolution des débits :
• USB 1.0 : 12 Mb/s
• USB 2.0 : 480 Mb/s
• USB 3.0 : 4,8 Gb/s 
Voir Clé USB.

## USENET
(*UNIX user network*)

Usenet, abréviation de UNIX user network, est un réseau de forums, aujourd’hui interconnecté à l’Internet, qui utilise le protocole NNTP.
Il permet la diffusion et la lecture de contenus associés à des communautés d’intérêts. 

## Usurpation d’adresse
(*Address spoofing*)

Action malveillante qui consiste à utiliser délibérément l’adresse d’un autre système en lieu et place de la sienne.
Remarques : Il faut rapprocher cette action de l’usurpation d’identité, considérée comme un délit par le droit pénal français.
L’idée est de faire passer son système d’information pour un autre.
L’adresse usurpée peut être une adresse MAC* (pour Medium Access Control), une adresse IP*, une adresse de messagerie, etc .
Voir Mystification – spoofing.


## UTF
(*Unicode Transformation Format*)

UTF est un système qui permet la transformation de tout point de code du répertoire universel de caractères définit par la norme ISO 10646.
Unicode* permet le codage des caractères dans l’ensemble des systèmes d’écriture, chaque caractère se voit attribuer un nom unique et un nombre entier positif.
Ce dernier constitue le « point de code ».
UTF – 8 est ainsi un standard de l’internet (STD 63) compatible avec ASCII qui assure la transformation des points de code sur 8 bits, il est utilisé par environ 90% des sites Internet.
UTF-8 est un format de transformation de la norme ISO 10646, il est standardisé par la RFC* 3629.
Voir Unicode, ASCII.
