# Infractions Plugin

The infractions plugin provides a set of useful moderator commands. These commands are intended to be used together and help handle/track misbehaving users over time.

## Commands

| Name | Description | Default Level | Usage |
|------|-------------|---------------|-------|
| `!warn {user} [reason]` | Adds a warning infraction to a user | Moderator | `!warn 232921983317180416 1st warning, spamming emoji` OR `!warn @airplane#1595 2nd warning, going off-topic` |
| `!mute {user} [reason]` | Mutes a user. This will only work if `mute_role` is set in the config | Moderator | `!mute 232921983317180416 spamming` OR  `!tempmute @airplane#1595 60m spamming` |
| `!unmute {user}` | Unmutes a user | Moderator | `!unmute 232921983317180416` |
| `!tempmute {user} {duration} [reason]` | Temporarily mutes a user. Will only work if `temp_mute_role` or `mute_role` is set in the config | Moderator | `!tempmute 232921983317180416 30m spamming` OR `!tempmute @airplane#1595 30m spamming` |
| `!kick {user} [reason]` | Kicks the user from the server | Moderator | `!kick 232921983317180416 spamming` OR `!kick @airplane#1595 spamming` |
| `!mkick {users] -r [reason]` | Kicks multiple users from the server | Moderator | `!mkick 232921983317180416 80351110224678912 108598213681922048 -r spamming` |
| `!ban {user} [reason]` | Bans a user from the server | Moderator | `!ban 232921983317180416 spamming` OR `!ban @airplane#1595 spamming` |
| `!unban {user} [reason]` | Unbans a user | Moderator | `!unban 232921983317180416` |
| `!forceban {User ID} [reason]` | Force bans a user who is not currently in the server | Moderator | `!forceban 232921983317180416 spamming` |
| `!softban {user} [reason]` | Softbans (bans/unbans) a user and deletes the user's messages sent within the last 7 days | Moderator | `!softban 232921983317180416 spamming` OR `!softban @airplane#1595 spamming` |
| `!tempban {user} {duration} [reason]` | Temporarily bans a user | Moderator | `!tempban 232921983317180416 5h spamming` OR `!tempban @airplane#1595 5h spamming` |
| `!inf archive` | Creates a CSV file of all infractions on the server | Administrator | `!inf archive` |
| `!inf search {query}` | Searches infractions database for given query | Moderator | `!inf search 232921983317180416` OR `!inf search airplane#1595` OR `!inf search spamming`
| `!inf info {inf}` | Presents information on the given infraction | Moderator | `!inf info 1274`
| `!inf duration {inf|ml} {duration}` | Updates the duration of the given infraction. Duration starts from time of initial action | Moderator | `!inf duration 1274 5h` |
| `!inf reason {inf|ml} {reason}` | Updates the reason of a given infraction | Moderator | `!inf reason 1274 rude behaviour towards staff` |

## Configuration Options

| Option | Description | Type | Default |
|--------|-------------|------|---------|
| confirm\_actions | Whether to confirm that an action was done in the current channel | bool | true |
| confirm\_actions\_reaction | Whether to confirm actions done in the channel using a checkmark reaction | bool | false |
| confirm\_actions\_expiry | The duration after which to delete the confirmed action message. If zero the message will never be deleted | int | 0 |
| mute\_role| Role ID that is set for users who are muted | id | none |
| reason\_edit\_level | Minimum level to allow users to edit other users' infraction reasons | int | 100 |

## Configuration Example

```
  infractions:
    confirm_actions: false
    mute_role: 289494296703533058
    reason_edit_level: 50
```
