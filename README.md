# modyo-connect: mifel-mx-widgets-pb-pf-dimo-active-dimo

```
git clone git@github.com:modyo-connect/mifel-mx-widgets-pb-pf-dimo-active-dimo.git
```

## 🚀 Project Structure

To start the project in local server, you'll see the following folders and files:

```
/
├── public/
├── src/
│   └── liquid/
│       └── local-liquid-variables.js
└── package.json
```

### First steps 👟👟

The application sesson looks for `.local-liquid-variables.js` file in the `src/liquid/` directory then to have to apply the session token in order to start the application.

```
export default {
  user: {
    access_token: "<YOUR_TOKEN>",
  },
  account: { ... },
  site: { ... },
  vars: { ... },
};
```

🤚 There's an important note about the registry common's package that mandatory need to provide into the root folder. start by creating a `.npmrc` file, then add the following token for the registries:

```
//npm.pkg.github.com/:_authToken=<YOUR_TOKEN>
@modyo:registry=https://npm.pkg.github.com
@modyo-connect:registry=https://npm.pkg.github.com
```

Any static assets, like images, can be uploaded into the cloud modyo platform

## 🧞 Commands

All commands are run from the root of the project, from a terminal:

| Command                       | Action                                                    |
| :---------------------        | :-----------------------------------------------          |
| `npm install`                 | Installs dependencies                                     |
| `npm start`                   | Starts local dev server at `localhost:8080`               |
| `npm run serve`               | Starts local dev server at `localhost:8080`               |
| `npm run build`               | Build your production site to `./dist/`                   |
| `npm run test`                | Runs project tests to ensure code correctness             |
| `npm run test:unit`           | Specifically tests individual code units                  |
| `npm run test:coverage`       | Generates code coverage report                            |
| `npm run lint`                | Checks code for style and format issues                   |
| `npm run i18n:report`         | Handles internationalization tasks                        |
| `npm run lint:style`          | Lints stylesheets or CSS/SCSS                             |
| `npm run lint:style:fix`      | Lints stylesheets or CSS/SCSS and fix it                  |
| `npm run modyo-push`          | Push the local `./dist/` files to Modyo platform          |
| `npm run build-and-push`      | Runs the `npm run build` command and  `npm run modyo-push`|
| `npm run modyo-serve`         | Starts local dev server in order to test `./dist/`        |
| `npm run validate-branch-name`| Validate branch rules specification                       |
| `npm run postinstall`         | Excutes husky package specification file                  |

## 🎨 Design
Feel free to check [Figma](https://www.figma.com/file/eWEYBtvr6T1PVeScE5BbLB/%F0%9F%A7%A9-DS-%7C-Mifel-2022?node-id=16%3A129&t=5Jw3S8uOn7fqg8RK-0|https://www.figma.com/file/eWEYBtvr6T1PVeScE5BbLB/%F0%9F%A7%A9-DS-%7C-Mifel-2022?node-id=16%3A129&t=5Jw3S8uOn7fqg8RK-0|smart-link)

## 🛠️ Services included into the widget
Feel free to check [Miro documentation](https://miro.com/app/board/uXjVM4PpWqc=/?moveToWidget=3458764558837164706&cot=14|https://miro.com/app/board/uXjVM4PpWqc=/?moveToWidget=3458764558837164706&cot=14|smart-link)

## 👀 Want to know more about the architecture?
Feel free to check [our documentation or something we call it, TBC](https://www.figma.com/file/qKPXoJC8n498wpVhsKGzVg/TBC-%7C-DiMo-(Copy)?type=whiteboard&node-id=1520-47041&t=yRcpe7T1QN26Nuge-0)
