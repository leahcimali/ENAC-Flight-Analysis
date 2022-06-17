# ENAC FLIGHT ANALYSIS
Problématiques :

1 - Analyser le comportement d’un vol en particulier chaque jeudi et vérifier si on peut comprendre les données de ce vol pour analyser ses éventuels retards ou l’impact du confinement sur ce vol.

2-Extrait de tous les vols avec FL ==0 tous les jeudi (pour être sûr d’avoir à chaque fois les mêmes vols). Analyse des paternes, peut- on prédire le décollage et l'atterrissage avec ces données ? Les retards ? l’impact du confinement ? … etc. 

DATASET : 

Données focalisés sur les jeudis du jeudi 10 septembre 2020 au jeudi 12 novembre 2020. à noter que le jeudi 29 octobre 2020 est le dernier jour avant le confinement qui à durée du 30 octobre 2020 au jusqu’au 15 décembre 2020.

Nous possédons donc des données à analyser pré-confinement au mois de septembre et octobre dans les fichier :
09-10.pcap','09-17.pcap','09-24.pcap','10-01.pcap','10-08.pcap','10-15.pcap','10-22.pcap','10-29.pcap'
et pendant le confinement avec les fichiers : 
,'11-05.pcap','11-12.pcap' 


Nous avons filtré et extrait les données avec l’application wireshark et un code python pour plus de facilité d’analyse. Puis nous avons extrait les données en csv pour lecture sur pandas avec python. Nous avons extrait deux dataset à nettoyer et filtrer seulement sur les paquet de catégorie 48 : 

'BCS28PTuesday.csv' : Il s’agit de données du vol “BCS28P” se passant tous les jeudi. 
Le vol BCS28P choisi correspond à un vol de la compagnie Cygnus Air opéré souvent avec DHL (fret) entre Leipzig (LEJ) en Allemagne et Nantes (NTE) dans la Loire atlantique. Il est souvent opéré par un Boeing de type B752.

‘FlightLevel0.csv’ : Il s’agit de données filtrés de tous les jeudi avec la donnée FL = 0.


Concernant les features présentes dans les dataset :

len : Longueur du message

src: adresse MAC source

tid: identification de l'avion

ts: timestamp (unix)

sac: System Area Code (code zone du radar)

sic: System Identification Code (code radar dans la zone)

tod: time of day (sec après minuit)

theta: 1ère coordonnée polaire de l'avion par rapport au radar

rho: 2ème coordonnée polaire de l'avion par rapport au radar

fl: altitude de l'avion (en pieds/1000)

cgs: calculated ground speed (peut être affecté par le vent)

chdg: heading (direction de vol de l'avion)


