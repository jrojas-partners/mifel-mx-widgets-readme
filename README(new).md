# [DIMO] Activación [PF]
<p align="center">
    <a href="https://github.com/badges/shields/graphs/contributors" alt="Contributors">
        <img src="https://img.shields.io/github/contributors/badges/shields" /></a>
    <a href="#backers" alt="Backers on Open Collective">
        <img src="https://img.shields.io/opencollective/backers/shields" /></a>
    <a href="#sponsors" alt="Sponsors on Open Collective">
        <img src="https://img.shields.io/opencollective/sponsors/shields" /></a>
    <a href="https://github.com/badges/shields/pulse" alt="Activity">
        <img src="https://img.shields.io/github/commit-activity/m/badges/shields" /></a>
    <a href="https://circleci.com/gh/badges/shields/tree/master">
        <img src="https://img.shields.io/circleci/project/github/badges/shields/master" alt="build status"></a>
    <a href="https://circleci.com/gh/badges/daily-tests">
        <img src="https://img.shields.io/circleci/project/github/badges/daily-tests?label=service%20tests"
            alt="service-test status"></a>
    <a href="https://coveralls.io/github/badges/shields">
        <img src="https://img.shields.io/coveralls/github/badges/shields"
            alt="coverage"></a>
    <a href="https://github.com/modyo-connect/mifel-mx-widgets-commons">
        <img src="https://img.shields.io/badge/uptime-100%25-brightgreen"
            alt="github commons"></a>
</p>

## Tabla de contenido

- [Pasos previos](#pasos-previos)
- [Estructura del proyecto](#estructura-del-proyecto)
- [Primeros pasos](#primeros-pasos)
- [Comandos para servir widget](#comandos-para-servir-widget)
- [Arquitectura de Widget](#arquitectura-de-widget)
- [Flujo de servicios](#flujo-de-servicios)
- [Diseño](#diseño)
- [Acciones de GitHub](#acciones-de-github)

## Pasos previos
En esta sección, describiremos los pasos previos necesarios para configurar el entorno de desarrollo en la plataforma Modyo. Esto incluye la preparación para utilizar la plataforma, uso de herramientas, entornos del lenguaje etc.
[Ver ruta de aprendizaje](https://help.modyo.com/es/collections/3962662-learning-paths),<br/>
[Ver documentación oficial](https://docs.modyo.com/es/)
<br/><br/>
![image](https://downloads.intercomcdn.com/i/o/709091580/3337c599202ba824c678d565/Learning+Path+01+-+Intro+a+Modyo.png)


## Estructura del proyecto
Aquí proporcionaremos una visión general de la estructura del proyecto de software, incluyendo la organización de archivos y carpetas. 

```
/
├── .github/                          <- Workflows
├── .husky/                           <- Acciones pre-commit, pre-push
├── .vscode/                          <- Config. workspace
├── public/                           <- Carpeta publica con indice del root de la app
├── src/
│   └── components/                   <- Componentes de apoyo o flujo de inicio
│   └── helpers/                      <- Utilidades
│   └── liquid/
│       └── local-liquid-variables.js <- Config. sesión por stage
│   └── locales/                      <- Traducciones o internacionalización 
│   └── repositories/                 <- Capa de repositorio con servicios externos 
│   └── router/*                      <- Indice de rutas internas
│   └── scss/                         <- Estilos del tema y globales del widget
│   └── stores/                       <- Gestor de estado por sección
│   └── views/*                       <- Vistas de las rutas internas
│   └── main.js                       <- Punto central de dependencias 
│   └── vee-validate-config.js        <- Config. de validaciones de formulario
└── package.json                      <- Gestor de dependencias del proyecto
```

(*) Carpetas con este apartado pueden incluir o no gestor de rutas.

### Version de Node (Recomendada)
En esta sección, se presentará la versión altamente recomendada para su uso en el proyecto, desde la instalación de paquetes hasta los casos de uso más habituales de cada comando. Es importante destacar que esta versión se sugiere debido a su amplia compatibilidad con la mayoría de los paquetes. No obstante, es posible optar por la última versión, aunque esto conlleva un cierto riesgo de incompatibilidad con algunas dependencias internas. Por lo tanto, se recomienda utilizar la versión sugerida para garantizar la estabilidad y coherencia del proyecto al igual que manejar el siguiente paquete: [NVM](https://github.com/nvm-sh/nvm#installing-and-updating)

```bash
$ node --version
 v16.18.0
```

### Husky
Funciones git nativos modernas utilizadas en el proyecto para mantener convenciones para la creación de ramas, validación de mensajes de commit, ejecución de comandos previo al envío de Github. 

```
.husky/
 └── commit-msg      <- Helper de config. commitlint.config
 └── post-checkout   <- Se ejecuta después de hacer un cambio de rama
 └── pre-commit      <- Se ejecuta antes de hacer un commit
 └── pre-push        <- Se ejecuta antes de hacer un push a Github  
```

*``pre-push`` Ejecuta los comandos: ``npm run lint``, ``npm run lint:style``, ``npm run test:unit`` esto asegura que se cumplan los requisitos mínimos para envió de código limpio y factible a los correspondientes stages. 

### VScode
Tiene una gran variedad de características útiles para agilizar el trabajo, que lo hacen el editor preferido por muchos desarrolladores Javascript para trabajar los proyectos. A continuación se listan algunas de las extensiones que debido a su relación con las dependencias instaladas en el proyecto. 

<ul>
    <li>Eslint: <b>dbaeumer.vscode-eslint</b></li>
    <li>EditorConfig: <b>EditorConfig.EditorConfig</b></li>
    <li>i18n: <b>lokalise.i18n-ally</b></li>
    <li>Stylelint: <b>stylelint.vscode-stylelint</b></li>
    <li>Vue Volar: <b>Vue.volar</b></li>
</ul>

## Primeros pasos
En esta sección, se presentarán los primeros pasos esenciales para empezar a trabajar en el proyecto. Esto incluye la clonación del repositorio, la configuración inicial y la preparación del entorno de desarrollo.

### Clonación del repositorio
```
git clone git@github.com:modyo-connect/mifel-mx-widgets-pb-pf-dimo-active-dimo.git
```

### Inicio de sesión en el widget
En el proyecto para iniciar el flujo de negocio del proyecto, es necesaria instalar la [extension](https://chrome.google.com/webstore/detail/modyo-version-chrome-plug/acjfedcdlpamblighjfehlbhpcnajkgl) de Modyo en su navegador. Este tiene la habilidad de obtener en un sitio construido en Modyo el `token` de sesión. Una vez copiado este deberá ubicarse en la propiedad de `access_token`. Se debe tener en cuenta que este token dura el tiempo de sesión destinado y/o configurado en la aplicación, quiere decir que desde local durara el mismo tiempo que este configurado según el stage en el que este apuntando este archivo de configuración. 

``
local-liquid-variables.js
``
```js
export default {
  user: {
    access_token: "<TOKEN DE SESIÓN>",
  },
  account: {},
  site: {},
  vars: {},
};

```

## Comandos para servir widget
Mostraremos los comandos clave para servir el widget y ejecutarlo localmente. Estos comandos son cruciales para instalar dependencias, iniciar, probar y/o depurar el widget durante el desarrollo.

| Command                       | Action                                                    |
| :---------------------        | :-----------------------------------------------          |
| `npm install`                 | Installs dependencies                                     |
| `npm start`                   | Starts local dev server at `localhost:8080`               |
| `npm run lint:style`          | Lints stylesheets or CSS/SCSS                             |
| `npm run lint:style:fix`      | Lints stylesheets or CSS/SCSS and fix it                  |

## Arquitectura de Widget
Aquí se explicará la arquitectura subyacente del widget, detallando los componentes clave y cómo interactúan entre sí. Esto proporcionará una comprensión más profunda de la estructura del widget, consumo de servicios y sus propiedades especificas, ver el Diagrama De Flujo Y Servicios
[(DFS)](https://www.figma.com/file/qKPXoJC8n498wpVhsKGzVg/TBC-%7C-DiMo-(Copy)?type=whiteboard&node-id=1520-47041&t=yRcpe7T1QN26Nuge-0)

### Componentes universales 
En todo el proyecto es ampliamente utilizando una serie de componentes que siguen la definición establecida del Design System (DS), un paquete de componentes ampliamente utilizado para armonizar y mantener una misma linea gráfica y funcional en toda la aplicación. 

```bash
npm i @modyo-connect/mifel-mx-widgets-commons@[Version actual del paquete]
```

### Consideraciones del widget
De la presentes consideraciones se deberá tener en cuenta que si el token tiene marcado el siguiente check, deberá tenerse en cuenta en el lanzamiento y configuración:

Eg. Si contiene 
- ✅ TokenGenerator 
- ✅ QueryParams

Eg. No contiene 
- ⬜️ TokenGenerator 
- ⬜️ QueryParams

## Flujo de servicios
Describiremos el flujo de servicios dentro del proyecto, destacando cómo se comunican los distintos componentes y cómo se gestionan los datos y las solicitudes, 
[Ver Miro](https://miro.com/app/board/uXjVM4PpWqc=/?moveToWidget=3458764558837164706&cot=14|https://miro.com/app/board/uXjVM4PpWqc=/?moveToWidget=3458764558837164706&cot=14|smart-link)

## Diseño
Aquí se visualizaran aspectos relacionados con el diseño de la interfaz del widget, incluyendo la usabilidad, la apariencia y las pautas de diseño. 
[Ver Figma](https://www.figma.com/file/eWEYBtvr6T1PVeScE5BbLB/%F0%9F%A7%A9-DS-%7C-Mifel-2022?node-id=16%3A129&t=5Jw3S8uOn7fqg8RK-0|https://www.figma.com/file/eWEYBtvr6T1PVeScE5BbLB/%F0%9F%A7%A9-DS-%7C-Mifel-2022?node-id=16%3A129&t=5Jw3S8uOn7fqg8RK-0|smart-link)


## Acciones de GitHub
Aquí se enumerarán las acciones y procesos específicos relacionados con GitHub, como la gestión de ramas, las solicitudes de extracción y las prácticas recomendadas para el trabajo en equipo. Workflows para que los cambios realizados en el widget puedan subirse correctamente.
