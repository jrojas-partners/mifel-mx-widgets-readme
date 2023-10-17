# [DIMO] Activación [PF]
## Widget: mifel-mx-widgets-pb-pf-dimo-active-dimo

## Table of Contents

- [Pasos previos](#previos_steps)
- [Estructura del proyecto](#project_structure)
- [Primeros pasos](#firs_steps)
- [Comandos para servir widget](#commands)
- [Arquitectura de Widget](#arkitecture)
- [Flujo de servicios](#services)
- [Diseño](#design)
- [Acciones de GitHub](#github_actions)

## [Pasos previos Modyo Platform](#previos_steps)
En esta sección, describiremos los pasos previos necesarios para configurar el entorno de desarrollo en la plataforma Modyo. Esto incluye la preparación para utilizar la plataforma, uso de herramientas, entornos del lenguaje etc. 

## [Estructura del proyecto)](#project_structure)
Aquí proporcionaremos una visión general de la estructura del proyecto de software, incluyendo la organización de archivos y carpetas. 

```
/
├── public/
├── src/
│   └── liquid/
│       └── local-liquid-variables.js
└── package.json
```

## [Primeros pasos)](#firs_steps)
En esta sección, se presentarán los primeros pasos esenciales para empezar a trabajar en el proyecto. Esto incluye la clonación del repositorio, la configuración inicial y la preparación del entorno de desarrollo.

```
git clone git@github.com:modyo-connect/mifel-mx-widgets-pb-pf-dimo-active-dimo.git
```

## [💻 Comandos para servir widget](#commands)
Mostraremos los comandos clave para servir el widget y ejecutarlo localmente. Estos comandos son cruciales para instalar dependencias, iniciar, probar y/o depurar el widget durante el desarrollo.

| Command                       | Action                                                    |
| :---------------------        | :-----------------------------------------------          |
| `npm install`                 | Installs dependencies                                     |
| `npm start`                   | Starts local dev server at `localhost:8080`               |
| `npm run lint:style`          | Lints stylesheets or CSS/SCSS                             |
| `npm run lint:style:fix`      | Lints stylesheets or CSS/SCSS and fix it                  |

## [⚙️ Arquitectura de Widget](#arkitecture)
Aquí se explicará la arquitectura subyacente del widget, detallando los componentes clave y cómo interactúan entre sí. Esto proporcionará una comprensión más profunda de la estructura del widget, consumo de servicios y sus propiedades especificas,
[Ver TBC](https://www.figma.com/file/qKPXoJC8n498wpVhsKGzVg/TBC-%7C-DiMo-(Copy)?type=whiteboard&node-id=1520-47041&t=yRcpe7T1QN26Nuge-0)

## [🛠️ Flujo de servicios](#services)
Describiremos el flujo de servicios dentro del proyecto, destacando cómo se comunican los distintos componentes y cómo se gestionan los datos y las solicitudes, 
[Ver Miro](https://miro.com/app/board/uXjVM4PpWqc=/?moveToWidget=3458764558837164706&cot=14|https://miro.com/app/board/uXjVM4PpWqc=/?moveToWidget=3458764558837164706&cot=14|smart-link)

## [🎨 Diseño](#design)
Aquí se visualizaran aspectos relacionados con el diseño de la interfaz del widget, incluyendo la usabilidad, la apariencia y las pautas de diseño. 
[Ver Figma](https://www.figma.com/file/eWEYBtvr6T1PVeScE5BbLB/%F0%9F%A7%A9-DS-%7C-Mifel-2022?node-id=16%3A129&t=5Jw3S8uOn7fqg8RK-0|https://www.figma.com/file/eWEYBtvr6T1PVeScE5BbLB/%F0%9F%A7%A9-DS-%7C-Mifel-2022?node-id=16%3A129&t=5Jw3S8uOn7fqg8RK-0|smart-link)

## [📈 Acciones de GitHub](#github_actions)
Aquí se enumerarán las acciones y procesos específicos relacionados con GitHub, como la gestión de ramas, las solicitudes de extracción y las prácticas recomendadas para el trabajo en equipo. Workflows para que los cambios realizados en el widget puedan subirse correctamente.
