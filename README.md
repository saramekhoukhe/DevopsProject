
## 1. Création d'une application Web avec NodeJs:
Pour commencer, on a cree une application API utilisateur avec la fonctionnalité utilisateur CRUD avec NodeJs en stockant les donnees dans une base de donnees MongoDB.

![App Screenshot](https://user-images.githubusercontent.com/115075351/209561658-f2d27c44-466c-40ab-a2b6-26ca28e6d3da.PNG)
On a verifie le bon fonctionnement de l'application avec Postman.

![App Screenshot](https://user-images.githubusercontent.com/115075351/209561222-e37469c0-3484-41c6-a8c3-8c5189f994a6.PNG)

## 2. Application du pipeline CI/CD
Pour l'Intégration Continue, on a utilisé Github Action.
On a créé un Folder .github/workflows qui contient un fichier .YML et une autre branche appelée "develop".

Ce dernier, vérifie les push vers la branche "main" et les pullrequest vers la branche "develop"

![App Screenshot](https://user-images.githubusercontent.com/115075351/209561783-5dd4fa8b-4174-47e4-9bed-b9464d72672f.PNG)

## 3. Approvisonnement et la configuration de l'environnement:

-Configuration de la VM avec Vagrant: 
![App Screenshot](https://user-images.githubusercontent.com/115075351/209582241-6601b9cf-0ac1-4828-af95-ef9c16c1c9e5.PNG)

![App Screenshot](https://user-images.githubusercontent.com/115075351/209585439-a676efbd-6416-4d9f-981b-7e6215220938.PNG)
-Installation d'Ansible sur la VM:
![App Screenshot](https://user-images.githubusercontent.com/115075351/209585263-0e62eb5e-a400-4c0f-9756-7d0774924ed4.PNG)

## 4. Création d'une image Docker de votre application
1-L'image créé: "devops"
![App Screenshot](https://user-images.githubusercontent.com/115075351/209585748-63ed6d98-13b4-4d37-bc86-fad75ddbb31a.PNG)

2-Pusher l'image créé vers Docker HUB:
![App Screenshot](https://user-images.githubusercontent.com/115075351/209585828-877b2266-3cad-40f3-8185-7cdd8f8af338.PNG)
 
 L'image sur Dokcer HUB:
 ![App Screenshot](https://user-images.githubusercontent.com/115075351/209586105-64daa7dd-600c-47cb-ab58-1738a69a2498.PNG)
 ![App Screenshot](https://user-images.githubusercontent.com/115075351/209585872-ee6c18ab-3997-4918-827f-98356a797e3c.PNG)

## 5. L'orchestration des conteneurs à l'aide de Docker Compose
Le fichier Docker Compose:
![App Screenshot](https://user-images.githubusercontent.com/115075351/209585961-523f071f-5470-4de5-8306-e304cfde5b8c.PNG)
![App Screenshot](https://user-images.githubusercontent.com/115075351/209585965-3899337f-eee8-48e1-b3d5-5fc1795d22dc.PNG)

## 6. Oorchestration docker avec Kubernetes



