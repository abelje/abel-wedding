# abel-wedding
This will be a website that will host wedding information.

## Workflow - Make The Website Serve Up on Linode
- make sure any images are in the public folder
- ```npm run build```
- copy and paste contents of dist folder into resources
- Upload and Pull onto the server using
  - ```cd /var/www/html```
  - Then navigate to your cloned folder
  - run ```git pull```

## New Workflow
- Main Github page
  - Actions
    - Setup workflow yourself
    - paste code
    - ```name: Automated Vuetify Deploy

on:
push:
branches:
- main  # This triggers the script every time you push to main

jobs:
build-and-deploy:
runs-on: ubuntu-latest

    steps:
      - name: Checkout Code
        uses: actions/checkout@v4

      - name: Install & Build
        run: |
          npm install
          npm run build

      - name: Deploy to Linode
        uses: easingthemes/ssh-deploy@main
        env:
          SSH_PRIVATE_KEY: ${{ secrets.SSH_PRIVATE_KEY }}
          REMOTE_HOST: ${{ secrets.LINODE_IP }}
          REMOTE_USER: ${{ secrets.REMOTE_USER }}
          SOURCE: "dist/"
          TARGET: "/var/www/html"
          # -rlgoDzvc: standard sync flags
          # --delete: removes old build files from server
          ARGS: "-rlgoDzvc -i --delete"
```
- repo settings
- Add private keys
  - cat ~/.ssh/id_ed25519