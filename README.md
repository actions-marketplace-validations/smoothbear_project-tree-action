# Project tree workflow

### How to use
**Options**
| Key      | Description                       | Default value         |
|----------|-----------------------------------|-----------------------|
| title    | text to be replaced.              | Default Title         |
| path     | file to be replaced text.         | README.md             |
| message  | commit message when text updated. | update: project tree  |
| email    | to be committed user email.       | none                  |
| username | to be committed user name.        | none                  |
| token    | repository token or user token.   | none                  |


**Example Workflow**
```yml
name: Update to README

on:
  push:
    branches: [ "main" ]

jobs:
  change-readme:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Insert project tree
        uses: smoothbear/project-tree-action@main
        with:
          email: to be committed email
          username: to be committed username
          token: ${{ secrets.GITHUB_TOKEN }}
```

### Project Structure
```.
├── LICENSE
├── README.md
├── action.yml
├── dist
│   └── project
│       └── index.js
├── jest-config.js
├── package-lock.json
├── package.json
├── src
│   └── main.ts
└── tsconfig.json

3 directories, 9 files
```
