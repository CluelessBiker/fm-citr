### React: 
```
npx create-react-app . --use-npm
```
- course is taught with this version:
```
npm install react@17.0.2 react-dom@17.0.2
```
 - to downgrade react version, follow this [StackOverflow article](https://stackoverflow.com/questions/46566830/how-to-use-create-react-app-with-an-older-react-version)

### Prettier:
- run:
```
npm install -D prettier@2.5.1
```

- update `package.json` with:
```
"scripts": {
    "format": "prettier --write \"src/**/*.{js,jsx}\""
},
```

- in the root directory, create a `.prettierrc` file, and populate it with `{}`.
 - The empty {} signifies that the code has been formatted with the default prettier settings.

- In GitPod or VS code, install the `Prettier - Code formatter` by esbenp.
 - navigate into the extension settings, & enable `Format on Save` & `Require Config`

- you can then run the command:
```
npm run format
```

### ESLint:

- run:
```
npm install -D eslint@8.8.0 eslint-config-prettier@8.3.0
```

- inside root drictory, create the file `.eslintrc.json` & populate it :
```
{
    "extends": ["eslint:recommended", "prettier"],
    "plugins": [],
    "parserOptions": {
        "ecmaVersion": 2022,
        "sourceType": "module",
        "ecmaFeatures": {
        "jsx": true
        }
    },
    "env": {
        "es6": true,
        "browser": true,
        "node": true
    }
}
```
 - `"prettier"` MUST come last.

- Install the GitPod / VS Code extension `ESLint` by dbaeumer (official microsoft version)

- update the `"scripts"` in `package.json` with:
```
"lint": "eslint \"src/**/*.{js,jsx}\" --quiet"
```
 - don't forget to add the `,` at the end of the line above.

- if you would like the build to fail should the prettier checks not pass, add the following line to the `"scripts"` as well:
```
"format:check": "prettier --check \"src/**/*.{js,jsx}\""
```

### Git:
- run :
```
git init
```

- create a `.gitignore` file & populate it with:
```
node_modules
.parcel-cache/
dist/
.env
.DS_Store
coverage/
.vscode/
```

### Parcel:
(used to bundle porjects)

- run:
```
npm install -D parcel@2.2.1
```

- update the `"scripts"` in `package.json` with:
```
"dev": "parcel src/index.html"
```

- add the following to the `package.json` file as well:
```
"browserslist": [
    "last 2 Chrome versions"
]
```