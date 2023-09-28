# mifel-mx-widgets-pb-pf-dimo-active-dimo

This repository is created in order to active the DiMo activation flow

## Table of Contents

- [About](#About)
- [Environments](#environments)
- [Layouts](#layouts)
- [Getting Started](#getting_started)
- [Usage](#usage)
- [Deployment](#deployment)

## [About](#about)

This project uses Vue 2.7.14, and as main dependencies libraries includes: vue-router, vue-i18n,  vee-validate, axios, bootstrap, core, date, liquidjs

## [Environments](#environments)

Here is sample of the environments where this widgets is available.

| Environments  | Url Base                         |
| ------------- | -------------------------------- |
| Mocks         | <https://un.modyo.build/mocks>   |
| Development   | <https://un.modyo.build/develop> |
| Certification | <https://un.modyo.build/>        |

Take into account environments have their own configuration, and must be specified at `.env` in order to publish environment deployment correct.

## [Layouts](#layouts)

According to the proyect structure it can be defined as many layout as the project needs, for eg.

| Layouts        |
| -------------- |
| HomeProfile    |
| SummaryProfile |

## [Getting Started](#getting_started)

To start the project in local server, you'll see the following folders and files:
```
/
├── public/
├── src/
│   └── liquid/
│       └── local-liquid-variables.js
└── package.json
```

Then you can appreciate about the registry common's package that mandatory need to provide into the root folder. start by creating a `.npmrc` file, then add the following token for the registries.

```
//npm.pkg.github.com/:_authToken=<YOUR_TOKEN>
@modyo:registry=https://npm.pkg.github.com
@modyo-connect:registry=https://npm.pkg.github.com
```

### Installing

Clone the repository from **develop branch** using SSH
```shell
git clone git@github.com:modyo/widget-name.git
```

Once cloned pull any existing changes and install all dependencies to be up to date.
```shell
npm install
```

## [Usage](#usage)

Here we describe in detail the widget flow including what endpoints are used, steps needed to go through the widget flow, if we need any dependencies and which version is being used, if we need to use some data from the platform instead of locally, the available views and what can we do inside each of them, and if we want we can include a table with mobile and desktop versions of said view to make things easier visually:

Create a new branch with accurate naming conventions (type of prefix, issue tracker ID and what change was made there.)
```shell
git branch task/0000-change-made
```
​
`widgetViewMobileVersion.vue` for mobile devices | ``widgetViewDesktopVersion.vue` for mobile devices | `panelMenu.vue` for desktop
.vue` for desktop
​

## [Deployment](#deployment)

Once all changes are made in the new branch, we can publish changes to the Modyo Platform following a GitHub workflow:
​

- To publish to **Certification**:
- first make sure the file _.github/workflows/publish-to-certification.yml_ exists.
- we commit the changes and push the branch with:

```shell
    git add .
    git commit -m "feat(where the change was made): what did we change there"
    git push origin branch-name
```

- we create a new Pull Request to merge the branch into _develop_ branch.
- To publish to **Prodution**:
- first make sure the file _.github/workflows/publish-to-production.yml_ exists.
- we create a new Pull Request to merge the _develop_ branch into _master_ branch.
- create a new Release with the new version (the first time it will probably have to be manually), following naming convention such as v1.0.0., and make sure its published and doesn't stay as a draft.
  ​
  Some things to consider:
- Don't create the widget manually on the Modyo platform, when the workflow runs the widget will automatically create itself and then we can add it to the Layout we need.
- Name the widget after the same name of the repo (_larrainvial-repo-name_ instead of _Repo Name_), so we can know this is a widget with the latest settings.
  ​
  In the event that we need to make a hotfix in a hurry we can also use the vue-cli interface. First we need to adjust the _.env_ file with the _MODYO_ACCOUNT_URL_ and _MODYO_TOKEN_ values so we aim to Certification or Production environment. Write in the console:
  ​

```shell
vue ui
```

​
There, go to _Tasks_ and just run _build_ and _modyo-push_, now you can see your changes uploaded to the widget in the builder. Ideally, we run the normal workflow afterwards.
