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
Get Github to push the website to your page without moving it yourself.
- Main Website Github page
  - Actions
    - Setup workflow yourself
    - paste code
    ```
      name: Automated Vuetify Deploy
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
- Go to repo settings, secrets and variables, actions
  - Add Repo Secret 'LINODE_IP' and paste in the IP to your server
  - Add Repo Secret 'REMOTE_USER' and insert the username, for example root
  - Add Repo Secret 'SSH-PRIVATE-KEY'
    - Add your machines Private key 
    - cat ~/.ssh/id_ed25519
    - copy and paste the entire output in the box
  - If it doesn't work after merging to main, go to the server and ```nano ~/.ssh/authorized_keys``` and add your public key from ```cat ~/.ssh/id_ed25519.pub```
### Server setting changes
  - ```emacs /etc/nginx/sites-available/default```
    - Change root to ```/var/www/html```
    - In location / {, add ```/index/html``` right before ```=404```
    - the reload nginx ```systemctl restart nginx```