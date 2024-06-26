## TA
(*Time Advance*)
Dans un réseau GSM*, le time advance - TA est un décalage temporel entre les messages envoyés par les différents mobiles vers la station de base (BTS) afin d’éviter les collisions.
En effet, sans ce paramètre, les burst émis par les mobiles utilisant deux slots consécutifs risquent de se chevaucher au niveau de la BTS en raison du temps de propagation.
Le TA correspond au temps de propagation aller-retour entre un mobile et la BTS.

## Table de routage
(*Routing table*)
Une table de routage est un ensemble de données structurées, stocké par un routeur* ou un hôte IP (équipement connecté au réseau et utilisant le protocole IP pour communiquer), qui contient les informations nécessaires à l’acheminement des datagrammes* vers leurs destinations.
Les entrées de la table de routage possèdent généralement les champs suivants :
•	Destination : la destination peut être une adresse IP* complète ou celle d’un sous réseau ;
•	Masque de réseau : qui permet de faire correspondre à une adresse IP de destination la valeur du champ Destination ;
•	Tronçon suivant ou adresse de passerelle* : qui détermine l’adresse IP vers laquelle le paquet IP est transféré ;
•	Interface : qui désigne l’interface* réseau à utiliser pour transférer le paquet ;
•	Métrique : qui fait correspondre un coût à un itinéraire. Ce champ est utilisé par les protocoles de routage* pour déterminer la meilleure route en fonction des choix de routage effectués.

Un administrateur réseau peut configurer manuellement des routes dans une table de routage, elles sont appelées routes statiques et sont à distinguer des routes dynamiques qui sont mises à jour par l’intermédiaire de protocoles de routage (BGP* ou OSPF* par exemple).
En outre, une route par défaut est nécessaire pour indiquer la destination des paquets qui ne correspondent à aucune entrée de la table de routage.
Voir BGP, Routage.

## Tag Switching
(Commutation d’étiquette)
Le Tag Switching est une technologie de commutation de paquets* qui préfigure le label switching du protocole MPLS*.
Développé par CISCO System, il repose sur un mécanisme d’acheminement des paquets par l’utilisation d’étiquettes (tag).
Voir MPLS.

## Tarpit
Service* qui permet de ralentir les connexions entrantes dans un système.
Le tarpit a été développé par Tom Liston afin de contrer la propagation du ver CodeRed.
Un tarpit en fonction sur un port* où l’on ne doit pas recevoir de trafic permet, en cas de tentative de connexion, de répondre favorablement mais avec une valeur de taille de paquets très faible afin de limiter l’infiltration.

## Taux d'erreurs
(*Error Rate*)
Dans une transmission, le taux d’erreurs représente le rapport du nombre de bits erronés au nombre total de bits transmis.

## Taux d'erreurs résiduelles
(*Residual error-rate*)
Rapport du nombre des bits incorrectement reçus mais non détectés comme tels, au nombre total de bits transmis.

## TCP
(*Transmission Control Protocol*)
Protocole* de transport de la couche 4 du modèle OSI* (couche transport).
Très utilisé dans des applications internet (associé au protocole IP, TCP/IP) TCP peut représenter jusqu’à 90% du trafic mesuré.
Le protocole a été une première fois standardisé en 1981, dans la RFC* 793, pour répondre au besoin de fiabilité dans le transport au profit de certaines applications (messagerie, transfert de fichiers).
Ainsi, TCP établit des mécanismes de transfert bi-directionnels entre processus distants avec la possibilité pour chacun de moduler la vitesse du trafic en fonction de la disponibilité des ressources.
Ce mécanisme de « contrôle de flux » permet par exemple de demander la réexpédition d’un paquet* non reçu. 
En outre TCP dispose d’un mécanisme de contrôle de congestion qui permet à un émetteur de vérifier que la vitesse d’émission ne va pas entrainer un engorgement du réseau (et donc des pertes de paquets).
Cette évolution de TCP est dite Tahoe et est décrite dans la RFC 1122 qui date de 1989. 
En 1999, une autre version du protocole, dite Reno (RFC 2581) améliore Tahoe qui diminuait trop nettement l’efficacité des transmissions.
Le protocole TCP est orienté connexion et se découpe en trois phases : ouverture de la connexion, transfert des données, fermeture de la connexion.
Le flot d’octets à transmettre est découpé en segments qui sont déposés dans des paquets IP avant d’être transmis sur le réseau, chaque segment est numéroté afin de permettre un mécanisme d’acquittement et de retransmission.
TCP utilise deux méthodes pour détecter une perte de paquet.
Ainsi, il y a perte si l’émetteur ne reçoit pas un acquittement (dans un certain délai) ou s’il reçoit plusieurs acquittements qui ne correspondent pas à un paquet émis récemment. 
Dans le modèle Internet, il existe d’autres protocoles de transport, tel qu’UDP* par exemple, lorsque la fiabilité n’est pas une priorité. 

L’entête TCP
TCP mettant en œuvre des mécanismes de contrôle, l’en-tête des paquets est nécessairement porteuse de plus d’informations.
Outre les ports* source et destination (sur 16 bits chacun) qui indiquent la source et la destination du paquet, on trouve un champ numéro de séquence (sur 32 bits).
Ce champ permet de numéroter un paquet dans une séquence afin de pouvoir respecter l’ordre de réassemblage et est nécessaire au mécanisme d’acquittement.
Le numéro d’acquittement d’un paquet correspond au numéro de séquence du paquet attendu.
Ce champ permet de renvoyer vers l’émetteur le décompte des paquets reçus et indique s’il y a eu des pertes.
Le champ « décalage des données » est aussi appelé « taille de l’en-tête » et indique la longueur de l’en-tête du paquet.

On trouve ensuite un champ réservé avec un système de « drapeaux » (flag*) chaque drapeau ayant une signification particulière :
• URG : urgent
• ACK : le paquet est un accusé de réception
• PSH : push données à « pousser », à envoyer sans délai ;
• RST : reset
• SYN : demande de synchronisation
• FIN : demande de fin de connexion.
Le champ fenêtre indique la taille souhaitée de la fenêtre de congestion (mécanisme de contrôle de congestion de TCP).
Cela traduit le nombre d’octet que le récepteur peut recevoir sans accuser réception.
Le champ somme de contrôle, permet de vérifier l’intégrité du paquet (le checksum est calculé sur l’ensemble de l’en-tête TCP et du champ de données).
Le champ pointeur Urgent, indique la position des dernières données urgentes
 
32 bits
Port source	Port destination
Numéro de séquence
Numéro d’acquittement
Taille de l’en-tête	Réservé	ECN/NS	CWR	ECE	URG	ACK	PSH	RST	SYN	FIN	Fenêtre
Somme de contrôle	Pointeur de données urgentes
Options	Remplissage
Données

Voir UDP User Datagram Protocol.

TCP/IP (modèle)
Reposant sur les mêmes principes d’abstraction que le modèle OSI* (qui permet de normaliser les modes de communication entre ordinateurs en réseau), le modèle TCP/IP est une simplification appliquée à Internet.
Le modèle ne contient que 4 couches qui regroupent plusieurs couches du modèle OSI.
•	La couche accès, qui utilise les protocoles Ethernet*, PPP* ou token ring*. Cette couche regroupe la couche physique* et liaison de données du modèle OSI (couche 1 et couche 2), elle se charge de définir la forme suivant laquelle les données seront acheminées.
•	La couche internet, qui utilise le protocole IP, c’est la couche réseau du modèle OSI (couche 3), elle constitue le datagramme* (paquet de données) qui sera acheminé par la couche transport ;
•	La couche transport (identique au modèle OSI), qui utilise le protocole TCP et assure le transport des datagrammes et le contrôle des connexions.
•	La couche application, qui regroupe les couches application, présentation et session du modèle OSI.
Le principe repose sur un mécanisme d’encapsulation des données en fonction des couches (chacune ajoute les informations nécessaires à son traitement par la couche adjacente).
Ainsi, lorsqu’une application souhaite envoyer un message vers une autre application, celui-ci est encapsulé (on lui rajoute une en-tête TCP) et devient un segment de la couche transport.
Ce segment est lui-même encapsulé pour devenir un paquet de la couche IP avant de circuler sous forme de trame* au niveau de la couche accès. 

## TD/CDMA
(*Time Division / CDMA*)
Mode d’accès radio utilisé pour la téléphonie mobile entre un terminal et une station de base*.
Il combine plusieurs types de multiplexage.
Voir Accès multiple

## TDM
(*Time Division Multiplexing*)
(Multiplexage temporel)
Le TDM est une technique de multiplexage* qui permet de transmettre sur un même support de communication plusieurs canaux numériques.
Chaque station dispose d’un intervalle de temps dédié (slot*) pendant lequel elle peut transmettre sur le lien.
Elle dispose donc, durant une courte période de temps, de l’ensemble de la bande passante*.
Voir AMRT, Multiplexage.

## TDMA
(*Time Division Multiple Access*)
Technique de multiplexage* temporel du signal utilisé dans les modes d’accès multiples*.
Voir Accès multiple, AMRT.

## Téléchargement
(*Download*) 
Le téléchargement consiste à transférer un fichier depuis un ordinateur distant (serveur*) vers un ordinateur local (client*) par l’intermédiaire d’un réseau.

## Télécharger
(*Upload*) 
Action inverse du téléchargement*, l’upload consiste à transférer une donnée (fichier) depuis un client vers le réseau. 

## Téléphonie sur IP – TOIP
(*Telephone over IP*)
La téléphonie sur IP est un service permettant la communication téléphonique en utilisant le protocole IP.
La voix, après numérisation*, est scindée en paquets et transportée comme n’importe quel autre type de données.
On parle également de VoIP – Voice over IP ou de Voix sur IP*.

## TELNET
(*TELecommunication NETwork*)
Telnet est un protocole* de niveau applicatif qui permet d’assurer la communication entre deux machines en réseau (utilisant la suite TCP/IP*).
Telnet est présenté dans les RFC* 854 et 855.
Au-delà du protocole, Telnet est aussi la commande (dans un terminal*) qui permet de créer une session* Telnet entre un client et un serveur.
Telnet, en raison de sa simplicité, ne prend pas en compte de mécanismes de sécurité.
Aucun chiffrement des échanges n’est effectué.
Il demeure cependant utile pour disposer d’un accès distant sur certains équipements lorsqu’ils ne disposent pas d’une interface Web de gestion par exemple.

## Témoin de connexion
(*Cookie*) 
Voir Cookie.

## Temps de latence 
(*Latency*)
Le temps de latence d’un équipement réseau désigne la durée nécessaire pour qu’une trame* soit traitée par l’équipement.
Il s’agit donc typiquement du délai entre l’instant d’arrivée de la trame et sa sortie de l’équipement.
A l’échelle d’un réseau, la latence est donc le temps minimal nécessaire à un paquet pour rejoindre une destination depuis la source.
La latence a un fort impact sur certaines applications de communication (comme le transport de la voix par exemple).
La variation dans le temps de la latence est par ailleurs appelée gigue*.
Voir Gigue.

## Temps de réponse
Le temps de réponse d’un système désigne la durée nécessaire à l’accomplissement d’une commande.
C’est le délai de réaction d’une application.

## Terminal 
(*Terminal*)
Le terminal désigne, en informatique, l’ensemble des périphériques qui permettent de communiquer avec un ordinateur.
L’expression vient du fait qu’à l’origine, la taille des ordinateurs interdisait qu’ils puissent être « physiquement » dans les mêmes pièces que les utilisateurs.
Ces derniers avaient donc recours à des équipements « terminaux » (clavier, écran) pour communiquer leurs instructions.
Aujourd’hui, un terminal est une « invite de commande »  (un shell*) qui permet de dialoguer avec le système par l’intermédiaire de lignes de commande.
De façon synthétique, un terminal est donc un appareil qui permet l’accès à distance à un système informatique .

## Test d’intrusion
(*Pentest – penetration test*)
Le test d’intrusion est l’un des outils d’évaluation de la sécurité d’un système d’information, il peut être effectué dans le cadre d’un audit de sécurité dans des conditions particulières.
Dans son référentiel d’exigences, l’ANSSI le présente comme suit :
Le principe du test d’intrusion est de découvrir des vulnérabilités sur le système d’information audité et de vérifier leur exploitabilité et leur impact, dans les conditions réelles d’une attaque sur le système d’information, à la place d’un attaquant potentiel.
Les vulnérabilités testées peuvent également avoir été identifiées au cours d’autres activités d’audit.
Cette activité d’audit peut être réalisée soit depuis l’extérieur du système d’information audité (notamment depuis Internet ou le réseau interconnecté d’un tiers), soit depuis l’intérieur.
Un test d’intrusion seul n’a pas vocation à être exhaustif.
Il s’agit d’une activité qui doit être effectuée en complément d’autres activités d’audit afin d’en améliorer l’efficacité ou de démontrer la faisabilité de l’exploitation des failles et vulnérabilités découvertes à des fins de sensibilisation.
Les tests de vulnérabilité, notamment automatisés, ne représentent pas à eux seuls une activité d’audit au sens du Référentiel .
La relative facilité à se procurer des outils de test d’intrusion, il existe d’ailleurs des frameworks* dédiés, ne doit pas faire oublier que ces pratiques sont rigoureusement encadrées par la loi française (Code Pénal art 321-1).
Voir Audit.

## TETRA
(*Terrestrial Trunked Radio Access*)
A l’inverse du GSM* utilisé pour les communications personnelles, TETRA est un standard européen (de l’European Telecommunications Standards Institute - ETSI) développé pour le marché des communications radio mobile professionnelles.
TETRA offre un moyen sécurisé et portable pour les radiocommunications de nombreuses unités de police ou des services d’urgence dans le monde.
Ainsi, un réseau TETRA offre un canal radio ouvert en permanence à un groupe restreint d’utilisateurs (lorsqu’un utilisateur est en émission, l’ensemble du groupe reçoit l’appel).


## Tiers de confiance
(*Trusted third party – TTP*)
Voir Confiance.

## Time Out
Délai maximal pour qu’un équipement effectue une tâche.
Au-delà de ce délai, un message d’erreur (ou une mise hors circuit) est envoyé. 
Ainsi, le protocole de contrôle ICMP* utilise le message ICMP_TIME_OUT pour informer une station émettrice d’un paquet* que celui-ci va être détruit car son TTL* (Time To Live) est à zéro.
Ces mécanismes permettent d’éviter que des paquets ne circulent indéfiniment dans le réseau tout en informant la station émettrice de ce dysfonctionnement.
Voir ICMP, TTL.

## TKIP
(*Temporal Key Integrity Protocol*)
Protocole qui permet de sécuriser l’authentification* dans un réseau Wi-Fi, TKIP a été développé pour palier aux faiblesses de sécurité de WEP*.
Le mécanisme TKIP (norme 802.11i) consiste à fournir de nouvelles clés de façon périodique (et non plus unique comme WEP).
L’algorithme de cryptographie sous-jacent demeure RC4.

## TLD
(*Top Level Domain*)
(Domaine de premier niveau)
Un domaine de premier niveau est un sous-domaine de la racine dans le système de noms de domaine*.
Sur Internet, il existe environ 250 domaines de premier niveau « nationaux ». Ce sont les .fr pour la France, .uk pour le Royaume-Unis, .be pour le Royaume de Belgique etc.
Outre ces domaines nationaux, environ 300 sont dits génériques (.org, .com, .net).
La gestion des noms de domaine relève de l’ICANN*.
Voir Domaine, DNS, ICANN.

## Token Ring
(Anneau à jeton)
Token Ring est une technique d’accès pour réseau local* où chaque station est reliée à une seule autre station par un lien unidirectionnel.
Le token ring fonctionne sur le principe d’une communication alternée.
Chaque station n’est autorisée à émettre que lorsque la précédente a terminé (principe du jeton).
Dans une telle topologie*, les stations sont reliées à un équipement spécifique qui est en charge de la « gestion du jeton ».
Cet équipement est un répartiteur appelé MAU Multistation Access Unit. 
Ce type de réseaux locaux est standardisé par l’IEEE 802.5.

## Tolérance aux pannes
(*Fault tolerance*)
Aptitude d’un système informatique à demeurer fonctionnel malgré certaines pannes et ses constituants .

## Topologie de réseau 
(*Network topology*)
La topologie de réseau désigne le mode d’organisation physique ou logique d’un réseau.
On distingue ainsi plusieurs topologies classiques initialement décrites suivant les connexions physiques entre machines.
•	Topologie en bus : les stations sont reliées entre-elles via un câble unique.
•	Topologie en anneau : les stations sont reliées une à une suivant une boucle.
•	Topologie en étoile : une station centrale connecte des stations périphériques. Cette station est un concentrateur.
•	Topologie en « arbre » ou hiérarchisée : une topologie sous forme de pyramide avec une station « mère ».
•	Topologie maillée : les stations sont reliées entre-elles suivant plusieurs liaisons point à point sans hiérarchie. Une station peut ainsi être reliée à plusieurs autres en point à point.

Ces différentes topologies sont présentes dans les réseaux locaux*.
Elles sont en général mixées en fonction des besoins particuliers de l’entité.
La sécurité d’un réseau repose ainsi largement sur les combinaisons de topologies mises en place.
Dans les architectures hiérarchisées, les hubs et concentrateurs sont évidemment des points d’intérêts majeurs pour la sécurité.

## TOR
(*The Onion Router*)
TOR est un réseau décentralisé qui permet d’anonymiser les connexions sur Internet.
Le principe du « routage en oignon » permet de protéger l’utilisateur de l’enregistrement de son adresse IP* par les sites Web visités mais également réduit les risques d’analyse simple de flux.
TOR fait donc transiter les paquets TCP* par une série de routeurs* dédiés.
Les échanges entre ces routeurs sont en outre chiffrés et un « circuit » est établi entre le nœud TOR d’entrée et celui de sortie.
TOR propose également des services particuliers appelés services cachés pour lesquels l’adresse IP du serveur est cachée.
Celui-ci dispose d’une adresse en .onion (du type monsite.onion) et est accessible uniquement via TOR.
Orienté sur la préservation de l’anonymat et la sécurité des échanges, TOR est ainsi recommandé pour tous ceux qui cherchent à se protéger des systèmes de contrôle ou de filtrage mis en place.
Les journalistes, opposants politiques, activistes font donc naturellement parti du public ciblé pour l’usage de TOR.
Malheureusement, ce système permet également à des réseaux criminels de développer leurs activités avec une certaine impunité.
Certains « services cachés » étant de véritables marchés en ligne pour l’achat de produits stupéfiants ou encore de contrefaçon.
Reposant sur le principe de préservation de l’anonymat des usagers et du contournement de la censure, TOR génère de nombreuses attentes et est régulièrement confronté à des rumeurs de découvertes de failles de sécurité.
En la matière, il convient de souligner qu’aucun système ne peut garantir une sécurité totale, de nombreux usagers de TOR ont pu être mis en cause en raison d’erreurs de comportement.
Le code étant libre, les bases techniques de l’application sont connus (y compris leurs faiblesses).
Pour autant, TOR demeure un outil puissant de sécurisation des usages numériques.

## Trace
Voir Log.

## Trafic
(*Trafic*)
Densité d'un événement donné sur un canal de transmission.

## Traitement automatique de données
(*Automatic data processing – ADP*)
Ensemble des opérations réalisées par des moyens automatiques, relatif à la collecte, l’enregistrement, l’élaboration, la modification, la conservation, la destruction, l’édition de données et, de façon générale, leur exploitation .

## Traitement de données à caractère personnel
La Loi Informatique et Liberté présente le traitement de données à caractère personnel comme : toute opération ou tout ensemble d’opérations portant sur de telles don-nées, quel que soit le procédé utilisé, et notamment la col-lecte, l’enregistrement, l’organisation, la conservation, l’adaptation ou la modification, l’extraction, la consulta-tion, l’utilisation, la communication par transmission, dif-fusion ou tout autre forme de mise à disposition, le rap-prochement ou l’interconnexion, ainsi que le verrouillage, l’effacement ou la destruction .

## Trame
(*Frame*)
La commission générale de terminologie et de néologie définit en France une trame comme : un ensemble structuré d'éléments numériques consécutifs, spécifié par un protocole de communication.
En multiplexage* dans le temps, une trame est un cycle du signal multiplex, constitué par les éléments numériques insérés dans les créneaux temporels d'un ensemble répétitif de créneaux temporels consécutifs.
Dans la procédure HDLC* de transmission de données, une trame comporte des champs de commande de longueur fixe qui encadrent un champ de données de longueur variable .
Dans un réseau informatique, une trame est l’unité de données qui circule sur la couche 2 du modèle OSI*.
Ainsi un paquet* IP (unité de données de la couche 3) est encapsulé dans une trame pour pouvoir être acheminé.
Voir Paquet.

## Transceiver
(Émetteur – récepteur)
En télécommunication (radio) un transceiver est un équipement qui assure la réception et l’émission de signaux.
Dans un réseau informatique, il s’agit d’un équipement qui assure le lien entre une interface* physique d’une station et la liaison Ethernet* du réseau local*.

## Transcodage
(*Transrating*)
Action qui consiste à modifier le format d’encodage d’une information (type de compression utilisée pour les fichiers audio et vidéo).
Il peut ainsi s’agir de changer le débit du signal comprimé, ou le nombre de pixels sur une image.

## Transfert de paquets
Le transfert de paquets dans un réseau est une technique générique qui consiste à transporter des blocs d’information de nœud en nœud pour les acheminer vers un récepteur .

## Transfert de zone (DNS)
(*Zone transfer*)
Le transfert de zone est un mécanisme qui permet de répliquer les données DNS* entre serveurs.
Ainsi, pour améliorer la fiabilité globale du réseau, une zone doit être servie par au moins deux serveurs (qui doivent donc disposer de la même information).
Les TLD* (Top Level Domain) par exemple utilisent rsync ou d’autres mécanismes de réplication de bases.
AXFR* qui n’est pas une norme mais un standard décrit par les RFC* 1034 et 1035, est toutefois largement utilisé par les logiciels de serveurs de noms.
AXFR se distingue du transfert incrémental (IXFR) par le fait qu’il assure une recopie complète de la base sur la base d’une transaction en mode « client-serveur » entre un serveur client dit « esclave » et un maître
(nota : il y a toujours un serveur primaire maître par zone, voir RFC 2136).

## Transhumanisme
(*Transhumanism*)
Le transhumanisme ou post-humanisme est une idéologie assez controversée, essentiellement représentée dans les sociétés occidentales, qui affirme qu’il est du devoir de l’homme d’utiliser toutes les avancées des sciences et des nouvelles technologies pour augmenter ses performances (physiques et cognitives).
Le mouvement diffuse ses théories via de nombreux relais, le plus célèbre étant la « Singularity University » fondée par Ray Kurzweil en Californie.
Cet établissement bénéficie entre autre des financements de Google* et, dans une moindre mesure, de la NASA.
Dans le domaine de « l’homme augmenté » deux visions s’opposent, les détracteurs du transhumanisme condamnent les dérives possibles qui conduiraient à l’émergence d’une nouvelle race d’hominidé.
Le monde de demain serait ainsi divisé entre deux humanités l’une biologique et l’autre formée de cyborgs, plus résistants, plus performants, plus rapides…
Comment et sur quels critères aura-t-on accès à cette « sur-humanité » ?

## TRANSPAC
Transpac est un réseau à commutation de paquets* créé en 1979 par l’opérateur national français, France Télécom.
Il s’agissait d’un service public de transmission de données utilisant un réseau national suivant la norme X.25*.
Le réseau comptait 10 000 abonnés en 1981 et 45 000 en 1986.
L’arrivée des technologies IP et le déploiement de l’Internet a rapidement conduit à l’abandon de TRANSPAC dont la gestion a été arrêtée le 1er octobre 2011.
Quelques mois plus tard, l’opérateur Orange stoppait également l’exploitation de X.25. 

## Transport (couche)
(*Transport layer*)
De façon classique le transport désigne une fonction particulière qui assure l’acheminement des informations entre deux points appartenant à un réseau.
Dans le modèle OSI*, la couche transport (couche 4) assure cette liaison de « bout en bout » entre une source et une destination.
Elle opère au niveau logique entre des processus présents sur des hôtes* distants.
Par l’intermédiaire de protocoles de transport, la couche 4 assure, les services suivants :
•	Livraison fiable, en point à point* et séquencée : via le protocole TCP* ;
•	Livraison non fiabilisée, point à point ou multicast, en mode « best effort » : via le protocole UDP.

## TRAU
(*Transcoding Rate and Adaptation Unit*)
(Unité de transcodage et d’adaptation du débit)
Unité dans un réseau GSM* qui permet le transcodage et la conversion des signaux de 13 kb/s en signaux de 64 kb/s (et vice et versa).
Cette fonction est nécessaire pour l’interconnexion avec le réseau fixe (RTC*) dont le canal de liaison est à 64 kb/s.

## Triple DES
Algorithme de chiffrement* symétrique par bloc qui repose sur trois applications successives de DES*.
Développé pour dépasser les limites de DES, dont la taille de clés permettait l’attaque par force brute, triple DES consiste alors à chaîner trois chiffrements DES avec deux ou trois clés distinctes.
Voir DES. 

## Trojan
Voir Cheval de Troie.

## Troll 
Personnage de la mythologie scandinave, le troll est un être de la nuit, associé aux forces de la nature.
Généralement repoussant, il a mauvais caractère et est souvent impatient.
Par extension, un troll sur Internet est une personne qui intervient sur un forum, un chat, ou dans des commentaires, et dont le seul but est de choquer, critiquer et agresser les participants.
Il cherche systématiquement la polémique et génère des contre-débats qui éloignent, en général, du sujet principal de la conversation.

## TTL
(*Time-To-Live*)
(Durée de vie)
Le TTL est utilisé dans les en-têtes de paquets* IP mais également dans les serveurs DNS*.
Dans ce dernier cas, le TTL représente la durée de rétention d’une information en mémoire cache du serveur DNS.
Au-delà de cette durée, la donnée est considérée comme obsolète est doit être mise à jour.
Dans le cas d’un paquet IP, le TTL indique le nombre maximal de routeurs que peut traverser le paquet.
Au-delà, le paquet est détruit s’il n’est pas arrivé à destination.
Dans l’en-tête du paquet, un champ codé sur huit bits permet de fixer le TTL. Au passage de chaque routeur, le TTL est décrémenté et le paquet détruit lorsque celui-ci arrive à zéro.
Ce mécanisme permet d’éviter que des paquets ne circulent en boucle dans le réseau.
Voir ICMP, Time Out.

## Tunnel
(*Tunnel*)
Un tunnel est une connexion sécurisée (chiffrée) entre deux systèmes via un réseau non contrôlé. 
Voir VPN.

## Typosquatting
(Faute de frappe opportuniste, coquille)
Action malveillante qui consiste à déposer un nom de domaine* très proche d’un autre nom de domaine, dont seuls un ou deux caractères diffèrent .
Remarques : les objectifs de cette action sont de capter une partie du trafic adressé au site officiel.
Voir Cybersquat.
