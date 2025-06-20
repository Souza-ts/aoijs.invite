<h1 align="center">aoijs.invite</h1>

<p align="center">
  <a href="https://www.npmjs.com/package/aoijs.invite">
    <img src="https://img.shields.io/npm/v/aoijs.invite?style=for-the-badge"  alt="aoiinvite"/>
  </a>
  <a href="https://www.npmjs.com/package/aoijs.invite">
    <img src="https://img.shields.io/npm/dt/aoijs.invite?style=for-the-badge"  alt="aoiinvite"/>
  </a>

## Installation

```sh
npm i aoijs.invite
```

## Setup

```js
const {AoiClient} = require("aoi.js");

const client = new AoiClient({
    intents: ["MessageContent", "Guilds", "GuildMessages"],
    events: ["onMessage", "onInteractionCreate"],
    prefix: "Discord Bot Prefix",
    token: "Discord Bot Token",
    database: {
        type: "aoi.db",
        db: require("@aoijs/aoi.db"),
        dbType: "KeyValue",
        tables: ["main"],
        securityKey: "a-32-characters-long-string-here",
    }
});

// Ping Command
client.command({
    name: "ping",
    code: `Pong! $pingms`
});

const { InviteManager } = require("aoijs.invite");
const i = new InviteManager(client,{
    sk: "a-32-characters-long-string-here",
},['inviteJoin','inviteLeave']);
```