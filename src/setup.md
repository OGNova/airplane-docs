# Setting Up Airplane

## How to Set Up

Once airplane has been added to your server, go to https://air.aetherya.stream/ to edit your server's configuration. Use the sidebar to read about each plugin, then use the example below along with the information in the sidebar to set up your own customized airplane configuration.

Below is a blank configuration example with web, utilities, admin, infractions, modlog, spam, and censor set up. While you can simply copy-paste this to your own server's configuration and fill in the blanks to have a perfectly usable airplane, it's highly encouraged that you read through the full documentation to understand each component and customize airplane to your server's needs.

```
web:
  000000000000000000: admin #Username
  000000000000000000: editor #Username
  000000000000000000: viewer #Username

commands:
  prefix: '!'
  overrides: []

levels:
  000000000000000000: 000 # Role

nickname: A1RPL4NE

plugins:

  utilities: {}

  admin: {}

  infractions:
    mute_role: 000000000000000000

  modlog:
    channels:
      00000000000000000000000:
        exclude: []
        include: []
    ignored_users: []

  spam:
    levels:
      0:
        punishment: TEMPMUTE
        punishment_duration: 120
        max_messages:
          count: 10
          interval: 7
        max_mentions:
          count: 8
          interval: 30
        max_links:
          count: 10
          interval: 60
        max_emojis:
          count: 100
          interval: 120
        max_newlines:
          count: 60
          interval: 120
        max_duplicates:
          count: 5
          interval: 30

  censor:
    levels:
      0:
        filter_invites: true
        invites_whitelist: ['discord-developers', 'discord-testers', 'discord-api', 'events', 'discord-linux', 'gamenight', 'discord-feedback']
        blocked_words: ['word1', 'word2', 'word3']
```
