# **KEYCLOAK**
This project aims to help you to deploy a Keycloak instance using docker and docker-compose in a few minutes.

There are many ways to deploy Keycloak, but this project is focused on deploying it as a self-contained application ready to production and a proxied keycloak ready to production.

## **Requirements**
- Docker
- Docker-compose

## **How to use**

Please, before running, check out the files and change it according to your needs. This is just a base reference to help you through the process.

### **Self-contained**

To deploy a self-contained Keycloak instance, you just need to:

Within your prefered terminal, navigate to the **self-contained** folder and run the following command:
```bash
docker-compose -f docker-compose.yml up -d
```

### **Proxied**

To deploy a proxied Keycloak instance, you just need to:

Within your prefered terminal, navigate to the **proxied** folder and run the following command:
```bash
docker-compose -f docker-compose.yml up -d
```


## VSCODE
If you are opening this project with **VSCODE**, open it using the **.workspace** file, then you can select the correct run configuration and press **F5**.

