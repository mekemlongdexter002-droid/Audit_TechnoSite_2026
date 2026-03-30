





SIMULATION 2 : SHODAN.IO - EXPOSITION DES ÉQUIPEMENTS INDUSTRIELS

Date : 28/03/2026

Outil : Shodan.io

RECHERCHES EFFECTUÉES :

| Recherche           | Requête | Résultats         | Risque associé |



| Modbus (industriel) | port:502 | 1150 équipements | Sabotage industriel |

| Siemens PLC | "Siemens PLC" | 392 automates | Altération consignes |

| MQTT IoT | port:1883 | 938706 serveurs | Exfiltration données |

| Caméras IP | "webcam" port:80 | 146 caméras | Intrusion physique |

| Maintenance web | "maintenance" http | 33130 applications | Accès non autorisé |

| VPN | port:1194 openvpn | 953783 serveurs | Accès distant forcé |

ANALYSE POUR TECHNOSITE INDUSTRIE :

Si TechnoSite Industrie a des équipements exposés :

1\. MODBUS : Un attaquant pourrait envoyer des consignes aux PLC

2\. MQTT : Les données de production pourraient être interceptées

3\. CAMÉRAS : Un attaquant pourrait surveiller le site

4\. APPLICATION WEB : Une faille SQL permettrait l'intrusion

5\. VPN : Des attaques par brute force pourraient compromettre l'accès

RECOMMANDATIONS :

1\. Effectuer un audit Shodan régulier de l'infrastructure

2\. Ne pas exposer d'équipements industriels directement sur Internet

3\. Utiliser un VPN pour l'accès distant

4\. Mettre en place une authentification forte (MFA)

5\. Chiffrer tous les flux de données

