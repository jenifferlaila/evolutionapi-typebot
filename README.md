# Evolution_Typebot integration

This project started off aiming at integrating EvolutionAPI and Typebot in such a way as to allow for them to be ran alongside each other, and has gained many other integrations and features since its conception.

It now integrates:

- EvolutionAPI
- Typebot
- Chatwoot
- N8n

But why? The main idea is:

1. You control both Chatwoot and Typebot via EvolutionAPI, so that you can comsume them in WhatsApp
2. You can create and publish chat bots in Typebot, with all of its features fully unlocked, locally
3. You manage conversations and answer messages from your WhatsApp through Chatwoot
4. And you can unpause chatbot instances by running automations with N8n

## How to use this project

First and foremost, ensure `docker`, `docker-engine` and `docker-compose` are installed in your machine. Then, you follow the steps bellow:

1. Clone this repo
2. Inside the repo's local directory in your machine:
   - Create copies the `*.env.example` files, naming them `*.env`
   - Modify the values found in the newly created files
3. Run `docker compose up -d` to start all containers
4. Navigate to whatever url you attributed to the `NEXTAUTH_URL` variable
5. Login and create a new Typebot, importing from the file under `/typebot_templates/with_chatwoot_integration.json`
6. Publish your bot
7. Navigate to `http://localhost:8080/manager` and login using the API Key you attributed to the `AUTHENTICATION_API_KEY` variable
8. Create a new instance
9. Connect your WhatsApp account to it
10. Integrate your newly published Typebot
11. Head over to whatever url you attributed to the `FRONTEND_URL` variable in the `chatwoot.env` file in the following manner:
    - `$FRONTEND_URL/installation/onboarding`
    - This will allow you to setup an admin account, and is allow available the first time you run the project
12. In the EvolutionAPI manager, integrate your Chatwoot instance
