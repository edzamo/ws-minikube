# Minikube

Bienvenido al curso de Minikube. En este curso aprenderás a desplegar y gestionar clústeres de Kubernetes de manera local utilizando Minikube.

## ¿Qué es Minikube?

Minikube es una herramienta que permite ejecutar un clúster de Kubernetes localmente en tu máquina. Es ideal para aprender, desarrollar y probar aplicaciones en Kubernetes sin necesidad de utilizar recursos en la nube.

## Instalación

### macOS

1. Instala Homebrew si no lo tienes:
    ```sh
    /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
    ```
2. Instala Minikube:
    ```sh
    brew install minikube
    ```
3. Inicia Minikube:
    ```sh
    minikube start
    ```

### Linux

1. Descarga el binario de Minikube:
    ```sh
    curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
    ```
2. Instala Minikube:
    ```sh
    sudo install minikube-linux-amd64 /usr/local/bin/minikube
    ```
3. Inicia Minikube:
    ```sh
    minikube start
    ```

## Comandos más importantes

| Comando | Descripción |
|---------|-------------|
| `minikube status` | Muestra el estado del clúster (running, stopped, etc.) |
| `minikube start` | Inicia el clúster local de Kubernetes |
| `minikube start --kubernetes-version=v1.32` | Inicia el clúster con una versión específica de Kubernetes. La versión 1.32 es la más actual al momento de este ejercicio |
| `minikube stop` | Detiene el clúster |
| `minikube delete` | Elimina el clúster y todos sus recursos |
| `minikube dashboard` | Abre el panel web de Kubernetes en el navegador |
| `minikube ip` | Muestra la dirección IP del clúster |
| `minikube ssh` | Abre una sesión SSH dentro del nodo de Minikube |
| `minikube tunnel` | Crea un túnel para exponer servicios tipo LoadBalancer (requiere sudo) |
| `minikube addons list` | Lista los complementos disponibles y su estado |
| `minikube kubectl --` | Ejecuta `kubectl` en el clúster de Minikube (ej: `minikube kubectl -- get pods`) |

### Ejemplos rápidos

```sh
# Ver si el clúster está corriendo
minikube status

# Iniciar Minikube con una versión específica de Kubernetes
# La versión 1.32 es la más actual al momento de este ejercicio
minikube start --kubernetes-version=v1.32

# Iniciar el dashboard
minikube dashboard

# Ver la IP del clúster
minikube ip
```

## Versiones de Kubernetes en la nube

### AWS EKS (Elastic Kubernetes Service)

AWS EKS soporta múltiples versiones de Kubernetes. A partir de enero de 2026, **Kubernetes versión 1.35** está disponible en AWS EKS.

**Versiones con soporte estándar:**
- 1.32
- 1.31
- 1.30

**Versiones con soporte extendido:**
- 1.29, 1.28, 1.27, 1.26, 1.25

Las versiones menores reciben 14 meses de soporte estándar, seguidos de 12 meses de soporte extendido.

### GCP GKE (Google Kubernetes Engine)

Google Cloud Platform también ofrece soporte para múltiples versiones de Kubernetes en GKE. Las versiones disponibles pueden variar según la región y el tipo de clúster (Standard o Autopilot).

Para verificar las versiones disponibles más recientes, consulta la [documentación oficial de GKE](https://cloud.google.com/kubernetes-engine/docs).

### Nota importante

Para este curso y ejercicios prácticos, se recomienda usar **Kubernetes versión 1.32** con Minikube, ya que es una versión estable y ampliamente soportada tanto en AWS EKS como en otros proveedores de nube.

## Documentación

La documentación completa está organizada en píldoras de aprendizaje en el directorio `01-documentation/`:

- **[01. Inicialización y primeros pasos](01-documentation/01.-init.md)** - Configuración inicial, comandos básicos, directorios importantes y verbos de kubectl
- **[02. Manifiestos vs Comandos](01-documentation/02.-manifest-vs%20commands.md)** - Comparación entre enfoques declarativo e imperativo
- **[03. Pods](01-documentation/03.-%20pods.md)** - Información sobre pods en Kubernetes
- **[04. Herramientas Linux útiles con Minikube](01-documentation/04.-herramientas-linux-minikube.md)** - Herramientas del sistema (htop, jq, watch) y comandos avanzados

¡Listo! Ya puedes comenzar a trabajar con Kubernetes en tu entorno local.