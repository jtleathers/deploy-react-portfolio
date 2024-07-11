# Deploy Your React Portfolio

Use the following guide to deploy your React portfolio to the root folder, **public_html**, folder on your server.

## Edit package.json
If you have a "homepage" key, set its value to "/".

    "homepage": "/"

## Edit main.jsx
If you have a basename attribute in `<BrowserRouter>`, set the value to "/".

    <BrowserRouter basename="/">

## Edit vite-config.js
In the **defineConfig** object, set the value of **base** to '/'.

    base: '/'

## Create .htaccess file
In the **public** folder, create a file called **.htaccess**. Add the following code to allow your app to refresh without errors:

    <IfModule mod_rewrite.c>
      RewriteEngine On
      RewriteBase /
      RewriteRule ^index\.html$ - [L]
      RewriteCond %{REQUEST_FILENAME} !-f
      RewriteCond %{REQUEST_FILENAME} !-d
      RewriteCond %{REQUEST_FILENAME} !-l
      RewriteRule . /index.html [L]
    </IfModule>


## Build the App
Run the following command:

    npm run build

## Upload the App
Upload the **contents** of the "dist" folder to the root folder on your server, public_html. Open your domain in a browser to check that the app loads properly.
