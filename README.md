# Telegram Web Apps for Bots / Mini App Example

Example HTML-file that contains a plain-JS interaction with Telegram Web Apps API. 

## Quick setup

#### 0. Optional: Host the Web App in GitHub Pages

The Web App must be hosted somewhere. Hosting it on a GitHub repository is a quick, free way to do it:

1. Create a repository (or fork this one)
2. On the repository: Settings –> Pages:
    - Source: Deploy from a branch
    - Branch: master, / (root), Save
3. Wait a few minutes for the web to be deployed. It will be available at: `https://{github-username}.github.io/{repository-name}/{location-inside-repository}`. In this case: `https://rhoncuss.github.io/telegram-web-app-bot-example/index.html`

#### 1. Show the user a button to open a Web App. There are two ways:

1. Show the user a special menu button (near the message input field):
   1. Go to [Bot Father](https://t.me/BotFather)
   2. Select your bot
   3. To set button in Bio: `Bot Settings` — `Configure Mini App`
   4. Send a URL to your Web App (in this case, `https://rhoncuss.github.io/telegram-web-app-bot-example/index.html`)
   5. To set corner button in Bot: `Bot Settings` — `Menu Button` — `Specify..`/`Edit menu button URL`
   6. Send a URL to your Web App (in this case, `https://rhoncuss.github.io/telegram-web-app-bot-example/index.html`)

2. The second way is to send a button with the data that contains field `web_app` with a URL to a Web App:
    ```json
    {
        "text": "Test web_app",
        "web_app": {
            "url": "https://rhoncuss.github.io/telegram-web-app-bot-example/index.html"
        }
    }
    ```

#### 2. Add script to your Web App

To connect a Web App to the Telegram client, place the script `telegram-web-app.js` in the `<head>` tag before any other scripts, using this code ([more info](https://core.telegram.org/bots/webapps#initializing-web-apps)):
```html
<script src="https://telegram.org/js/telegram-web-app.js"></script>
```

Once the script is connected, a `window.Telegram.WebApp` object will become available.

#### 3. Do the thing!
