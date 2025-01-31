# Consignes de l'examen 

Apportez les modifications suivantes sur la chart helm :

Modifiez le nom de chacune des ressources pour qu'elles commencent par les 4 premiers caractères du nom du déploiement helm. 

Mettez les variables d'environnement pour le pod mediawiki MEDIAWIKI_DB_NAME MEDIAWIKI_DB_HOST MEDIAWIKI_DB_PORT sous la forme (dans le fichiers values.yaml):
env:
  MEDIAWIKI... : mavaleur
  MEDIA..........

Ajoutez deux nouveaux fichiers dans templates : 

- Un fichier PV.yaml
- Un fichier PVC.yaml 

Ces deux fichiers contiendrons la configuration d'un volume pour le pod mysql qui pointerons vers un serveur nfs à l'adresse suivante : 192.168.1.56/public/nfs-share-openshift/groupe-x (attention je suis en nfs 3)

Cette configuration stockage, doit être présente seulement si la variable .Values.storage est égale à true. 

Créez des variables dans le fichier values qui vont permettre de définir pour chaque pod, une limite en ram et en cpu. Si jamais ces variables n'existent pas dans le fichier values.yaml, des valeurs par défault doivent être positionnées. 

Mettez sur l'ensemble des ressources des labels afin de pouvoir spécifier votre groupe, et si vous êtes dans un environnement de prod ou de dev. 

A NE PAS REFAIRE EN PRODUCTION 

Utilisez la vairbles à définir .Values.mysql.password  pour la renseigner dans le fichier secret.yaml (attention à la base64). 

Créez un deployment phpmyadmin sur le modèle de mediawiki par exemple et exposez ce deployment avec un service et saa route associée. (l'image c'est harbor.kakor.ovh/public/phpmyadmin:latest)

Rendez moi les éléments complétés avec une documentation en markdown dans un fichier zip sur moncampus. 

Bonne chance !

BONUS : 

Créez un fichier Notes.txt pour mettre un message de bienvenue à l'utilisateur qui déploira votre solution avec le lien des routes pour accéder à l'application. 

