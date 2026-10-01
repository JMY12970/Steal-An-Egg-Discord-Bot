# Steal An Egg Discord Alert Bot

Features:
- /setup alert channels
- /status
- /nextreset
- /config
- /history
- /event
- /adminabuse
- /rare
- automatic estimated reset alerts
- SQLite alert history
- authenticated POST /ingest endpoint for a real-time observer/data source

Important: Discord/Roblox public APIs do not automatically expose arbitrary in-game egg spawns or admin-abuse actions. The bot therefore labels its timer as an estimate. For actual real-time alerts, a legitimate observer/data source must POST detected events to /ingest.

Install:
1. Install Node.js 18+.
2. Copy .env.example to .env and fill in your Discord values.
3. Run npm install
4. Run npm start
5. Invite the bot with bot + applications.commands scopes.

POST /ingest with header x-alert-secret matching ALERT_API_SECRET.
Example JSON:
{"type":"rare_egg","title":"RARE EGG SPAWN","description":"A rare egg was detected","egg":"Example Egg","rarity":"Mythic","server":"123"}

Supported types: reset, event, admin_abuse, rare_egg.
