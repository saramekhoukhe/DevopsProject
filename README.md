
## 1. Création d'une application Web avec NodeJs:
Pour commencer, nous avons créé une application API utilisateur avec la fonctionnalité utilisateur CRUD avec NodeJs en stockant les donnees dans une base de donnees  [MongoDB](https://www.mongodb.com/atlas/database).

#### Ses fonctionalitées:

**POST**: Ajouter et publier un USER (Username et UserInfos) dans la base de données

**GET**:  Récupérer les informations des USERS de la base de données en utilisant _Id attribué par cette dernière lors du POST

**PUT**: Mettre à jour, modifier un USER déjà existant dans la base de données

**DELETE**: Supprimer un USER de la base de données

Nous avons verifié le bon fonctionnement de l'application via **POSTMAN**:
![App Screenshot](https://user-images.githubusercontent.com/115075351/209561222-e37469c0-3484-41c6-a8c3-8c5189f994a6.PNG)
Le résultat sur la base de données  [MongoDB](https://www.mongodb.com/atlas/database):
![App Screenshot](https://user-images.githubusercontent.com/115075351/209561658-f2d27c44-466c-40ab-a2b6-26ca28e6d3da.PNG)

## 2. Application du pipeline CI/CD
Pour l'Intégration Continue, nous avons utilisé **Github Action**.
On a créé un Folder .github/workflows qui contient un fichier .YML et une autre branche appelée "develop".

Ce dernier, vérifie les push vers la branche "main" et les pullrequest vers la branche "develop"

![App Screenshot](https://user-images.githubusercontent.com/115075351/209561783-5dd4fa8b-4174-47e4-9bed-b9464d72672f.PNG)


Pour le deploiment, nous avons opté pour **Azure**:

Nous avons installé Azure Tools sur VS code, nous avons ensuite créé un compte sur la plateforme [Azure](https://azure.microsoft.com/fr-fr/), avec un abonnement **Azur for Student**, nous avons obtenu un essai gratuit pour 365jours:
![App Screenshot](https://user-images.githubusercontent.com/115075351/209599403-53ca6239-1bba-4217-be19-141d8552820e.PNG)

Depuis **Command Palette** de VS code, nous nous sommes connectées a [Azure](https://azure.microsoft.com/fr-fr/), ensuite deployer notre Web App.

## 3. Approvisonnement et la configuration de l'environnement:
Nous avons Installé Vagrant sur notre VM

Nous avons ensuite exécuté la commande: 
```bash
  Vagrant up
```

-Configuration de la VM avec Vagrant: 
![App Screenshot](https://user-images.githubusercontent.com/115075351/209582241-6601b9cf-0ac1-4828-af95-ef9c16c1c9e5.PNG)

-Par défault, Vagrant a généré le fichier **Vagrantfile**
![App Screenshot](https://user-images.githubusercontent.com/115075351/209585439-a676efbd-6416-4d9f-981b-7e6215220938.PNG)

-Installation d'Ansible sur la VM:
![App Screenshot](https://user-images.githubusercontent.com/115075351/209585263-0e62eb5e-a400-4c0f-9756-7d0774924ed4.PNG)

## 4. Création d'une image Docker de votre application
#### Commandes:
```bash
 ENTRYPOINT ls -l /
 docker build -t devops
 docker run devops
```
#### Résulat :

Image créé:
![App Screenshot](https://user-images.githubusercontent.com/115075351/209585748-63ed6d98-13b4-4d37-bc86-fad75ddbb31a.PNG)

**Pusher l'image créé vers [Docker HUB](https://hub.docker.com/):**

**Commandes:**
```bash
 docker login
 docker tag devops saramekhoukhe/devops
 docker push saramekhoukhe/devops
```
![App Screenshot](https://user-images.githubusercontent.com/115075351/209585828-877b2266-3cad-40f3-8185-7cdd8f8af338.PNG)
 
 **L'image sur [Docker HUB](https://hub.docker.com/):**
 ![App Screenshot](https://user-images.githubusercontent.com/115075351/209586105-64daa7dd-600c-47cb-ab58-1738a69a2498.PNG)
 ![App Screenshot](https://user-images.githubusercontent.com/115075351/209585872-ee6c18ab-3997-4918-827f-98356a797e3c.PNG)

## 5. L'orchestration des conteneurs à l'aide de Docker Compose
Le fichier Docker Compose:

**Commandes:**
```bash
 docker-compose up
```
![App Screenshot](https://user-images.githubusercontent.com/115075351/209585961-523f071f-5470-4de5-8306-e304cfde5b8c.PNG)
![App Screenshot](https://user-images.githubusercontent.com/115075351/209585965-3899337f-eee8-48e1-b3d5-5fc1795d22dc.PNG)

## 6. Orchestration docker avec Kubernetes

**Installation de minikube** 

**Commandes:**
```bash
 sudo apt install -y curl wget apt-transport-https
 sudo cp minikube-linux-amd64 /usr/local/bin/minikube
 sudo chmod +x /usr/local/bin/minikube
```

![App Screenshot](https://user-images.githubusercontent.com/115075351/209669982-2ace8fbc-cbb0-4aa3-b779-d11ccf7ef600.PNG)


**Installation du cluster Kubernetes à l'aide de Minikube** 

**Commandes**
```bash
minikube start
kubectl get nodes
```

![App Screenshot](https://user-images.githubusercontent.com/115075351/209670175-f989d4b7-ea00-4b34-b6b7-69c38233b96f.PNG)

![App Screenshot](https://user-images.githubusercontent.com/115075351/209670539-6016e7ef-f50f-4c83-a41f-1a4195ceae8b.PNG)

**Création des fichiers YAML de manifeste Kubernetes**

**Commandes**
```bash
vi pod.yml
kubectl create -f pod.yml
```
-Services: [pod-service.yml](https://github.com/saramekhoukhe/DevopsProject/blob/main/pod-service.yml)

-Deployment: [deployment.yml](https://github.com/saramekhoukhe/DevopsProject/blob/main/deployment.yml)

## 7.Servive Mesh avec Istio










