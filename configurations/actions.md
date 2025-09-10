---
description: Actions that can be performed after a requirement
---

# ☢️ Actions

With a requirement, you can define actions for both success and failure. Here are the actions that can be performed.

**Example:** You will need to create an action list like this:

```yaml
success:
  - type: player_command
    commands:
      - "firstcommand"
      - "seconds commands %player%"
  - type: console_command
    commands:
      - "firstcommand"
      - "seconds commands %player%"      
  - type: message
    messages:
      - "firstcommand"
      - "seconds commands %player%"   
```

You can add a **delay**, in ticks, for each item in the list below. Do it like this:

```yaml
success:
  - type: player_command
    delay: 10 # 10 ticks
    commands:
      - "firstcommand"
      - "seconds commands %player%"
```

You can add a **chance** for each item in the list below. Do it like this:

```yaml
success:
  - type: player_command
    chance: 50 # 50% chance
    commands:
      - "firstcommand"
      - "seconds commands %player%"
```

***

## zMenu

Actions compatible with Dialogs are now marked with a badge:
<img src="https://img.shields.io/badge/Dialogs-%E2%9C%85%20Compatible-brightgreen?style=for-the-badge&logo=minecraft" alt="Dialogs "></img>

Actions not compatible are marked with:
<img src="https://img.shields.io/badge/Dialogs-%E2%9D%8C%20Not%20Compatible-red?style=for-the-badge&logo=minecraft" alt="Dialogs "></img>

### `player command` 

[![Dialogs ✅](https://img.shields.io/badge/Dialogs-✅%20Compatible-brightgreen?style=for-the-badge&logo=minecraft)]()

```yaml
- type: player command
  commands:
    - "firstcommand"
    - "seconds commands %player%"
  command-in-chat: false # false by default
```

Executes commands as the player. You can also send the command in the player's chat.

***

### `random player command`

[![Dialogs ✅](https://img.shields.io/badge/Dialogs-✅%20Compatible-brightgreen?style=for-the-badge&logo=minecraft)]()

```yaml
- type: random_player_command
  amount: 1 # Default value
  commands:
    - "firstcommand"
    - "seconds commands %player%"
  command-in-chat: false # false by default
```

Executes random commands as the player. You can also send the command in the player's chat.

{% hint style="warning" %}
This feature is only available with [zMenu+](../zmenu+.md) !
{% endhint %}

***

### `console command`

[![Dialogs ✅](https://img.shields.io/badge/Dialogs-✅%20Compatible-brightgreen?style=for-the-badge&logo=minecraft)]()

```yaml
- type: console_command
  commands:
    - "firstcommand"
    - "seconds commands %player%"
```

Executes commands as the console.

***

### `random console command`

[![Dialogs ✅](https://img.shields.io/badge/Dialogs-✅%20Compatible-brightgreen?style=for-the-badge&logo=minecraft)]()

```yaml
- type: random_console_command
  amount: 1 # Default value
  commands:
    - "firstcommand"
    - "seconds commands %player%"
```

Execute random commands from the list.

{% hint style="warning" %}
This feature is only available with [zMenu+](../zmenu+.md) !
{% endhint %}

***

### `player command as op`

[![Dialogs ✅](https://img.shields.io/badge/Dialogs-✅%20Compatible-brightgreen?style=for-the-badge&logo=minecraft)]()

```yaml
- type: player command as op
  commands:
    - <command>
```

Allows the execution of a command while being op.

{% hint style="danger" %}
Attention, this action will give all the permissions to the player while they execute the command. Please be careful when using this action.
{% endhint %}

***

### `message`

[![Dialogs ✅](https://img.shields.io/badge/Dialogs-✅%20Compatible-brightgreen?style=for-the-badge&logo=minecraft)]()

```yaml
- type: message
  messages:
    - "my message"
    - "my second messages"
  mini-message: true # true by default
```

Sends a message to the player. You can use placeholders, color codes, and format codes. The **MiniMessage** format is enabled by default if your server supports it.

***

### `broadcast`

[![Dialogs ✅](https://img.shields.io/badge/Dialogs-✅%20Compatible-brightgreen?style=for-the-badge&logo=minecraft)]()

```yaml
- type: broadcast
  messages:
    - "my name %receiver%"
    - "my second message send by %sender%"
  mini-message: true # true by default
  requirements: 
    - type: permission
      permission: "admin.use"
```

Sends a message to all online players. You can use placeholders, color codes, and format codes. The **MiniMessage** format is enabled by default if your server supports it.

`%sender%` is the name of the player **sending** the broadcast\
`%receiver%` is the name of the player who will **receive** the message.

You can set a list of [requirements](requirements.md) to send a message to certain players.

***

### `chat`

[![Dialogs ✅](https://img.shields.io/badge/Dialogs-✅%20Compatible-brightgreen?style=for-the-badge&logo=minecraft)]()

```yaml
- type: chat
  messages:
    - "my message"
```

Sends messages on behalf of the player. You can use placeholders, color codes, and format codes. **MiniMessage** format is enabled by default if your server supports it.

***

### `close`

[![Dialogs ❌](https://img.shields.io/badge/Dialogs-❌%20Not%20Compatible-red?style=for-the-badge&logo=minecraft)]()


```yaml
- type: close
```

Closes the player's inventory.

***

### `inventory`

[![Dialogs ✅](https://img.shields.io/badge/Dialogs-✅%20Compatible-brightgreen?style=for-the-badge&logo=minecraft)]()

```yaml
- type: inventory
  inventory: <inventory name>
  plugin: <plugin name>
  page: <page>
  arguments: <argument list>
```

Opens an inventory.

### `connect`

[![Dialogs ✅](https://img.shields.io/badge/Dialogs-✅%20Compatible-brightgreen?style=for-the-badge&logo=minecraft)]()

```yaml
- type: connect
  server: <server name>
```

Allows sending the player to another server, only works with BungeeCord and Velocity.

***

### `sound`

[![Dialogs ✅](https://img.shields.io/badge/Dialogs-✅%20Compatible-brightgreen?style=for-the-badge&logo=minecraft)]()

```yaml
- type: sound
  sound: <xsound>
  pitch: <sound pitch> # 1.0f by default
  volume: <sound volume> # 1.0f by default
```

Send a sound to a player, you must use [XSound](https://github.com/CryptoMorin/XSeries/blob/master/src/main/java/com/cryptomorin/xseries/XSound.java) for sound.

***

### `broadcast sound`

[![Dialogs ✅](https://img.shields.io/badge/Dialogs-✅%20Compatible-brightgreen?style=for-the-badge&logo=minecraft)]()

```yaml
- type: broadcast_sound
  sound: <xsound>
  pitch: <sound pitch> # 1.0f by default
  volume: <sound volume> # 1.0f by default
```

Send a sound to the online players, you must use [XSound](https://github.com/CryptoMorin/XSeries/blob/master/src/main/java/com/cryptomorin/xseries/XSound.java) for sound.

***

### `data`

[![Dialogs ✅](https://img.shields.io/badge/Dialogs-✅%20Compatible-brightgreen?style=for-the-badge&logo=minecraft)]()

```yaml
- type: data
  action: <SET/REMOVE/ADD/SUBTRACT>
  key: <data key>
  value: <data value>
  seconds: <expire seconds> # 0 by default
  math: <true/false>
```

Update [player data](player-data.md).

You can use mathematical expressions if you set math to true, this allows you to do more complex actions. Work only with ADD and SUBTRACT.

***

### `refresh`

[![Dialogs ❌](https://img.shields.io/badge/Dialogs-❌%20Not%20Compatible-red?style=for-the-badge&logo=minecraft)]()

```yaml
- type: refresh  
```

Refresh current button. Works only in click requirement.

{% hint style="warning" %}
If you update the status of a player with orders, to be sure that the inventory update is done correctly, you must put a delay of 1 tick.
{% endhint %}

***

### `refresh inventory`

[![Dialogs ❌](https://img.shields.io/badge/Dialogs-❌%20Not%20Compatible-red?style=for-the-badge&logo=minecraft)]()


```yaml
- type: refresh inventory
```

Refreshes the currently open inventory.

***

### `back`

[![Dialogs ❌](https://img.shields.io/badge/Dialogs-❌%20Not%20Compatible-red?style=for-the-badge&logo=minecraft)]()


```yaml
- type: back
```

Return to previous inventory.

***

### `shopkeeper`

[![Dialogs ✅](https://img.shields.io/badge/Dialogs-✅%20Compatible-brightgreen?style=for-the-badge&logo=minecraft)]()

```yaml
- type: shopkeeper
  name: <shopkeeper name>
```

Open a [Shopkeeper](https://www.spigotmc.org/threads/shopkeepers.447969/) trading inventory

***

### `book`

[![Dialogs ✅](https://img.shields.io/badge/Dialogs-✅%20Compatible-brightgreen?style=for-the-badge&logo=minecraft)]()

```yaml
- type: book
  author: "Maxlego08" # Book author
  title: "&cTest" # Book title
  lines: # Book pages
    1: # First page
      - '     #34ebe8zMenu'
      - ''
      - ''
      - '<hover:show_text:"#34eba8Open an url !"><click:open_url:"https://minecraft-inventory-builder.com/">#f0af24Open URL<reset>'
```

Opens a book for the player. You can specify the title, author, and pages of the book.

***

### `actionbar`

[![Dialogs ✅](https://img.shields.io/badge/Dialogs-✅%20Compatible-brightgreen?style=for-the-badge&logo=minecraft)]()

```yaml
- type: actionbar
  message: "my message"
  minimessage: true # true by default
```

Allows you to send a message in the action bar of the player. You can use placeholders and color/format codes here. **MiniMessage** format is enabled by default if your server supports it.

***

### `withdraw`

[![Dialogs ✅](https://img.shields.io/badge/Dialogs-✅%20Compatible-brightgreen?style=for-the-badge&logo=minecraft)]()

```yaml
- type: withdraw
  amount: <amount>
  currency: <currency name>
  economy: <economy name> # Only the zEssentials, CoinsEngine and EcoBits plugins need this  
```

Allows you to withdraw money from the player’s account. Works with the [BeastTokens](https://www.spigotmc.org/resources/beasttokens-custom-currency.20806/), [Vault](https://www.spigotmc.org/resources/34315/), [PlayerPoints](https://www.spigotmc.org/resources/80745/), [ElementalTokens](https://builtbybit.com/resources/16707/), [ElementalGems](https://builtbybit.com/resources/14920/), [Level](https://www.minecraft.net/), [Experience](https://www.minecraft.net/), [**zEssentials**](https://www.spigotmc.org/resources/118014/), [EcoBits](https://www.spigotmc.org/resources/109967/), [CoinsEngine](https://www.spigotmc.org/resources/84121/) and [VotingPlugin](https://www.spigotmc.org/resources/15358/).\
CurrenciesAPI : [https://github.com/Traqueur-dev/CurrenciesAPI](https://github.com/Traqueur-dev/CurrenciesAPI)

***

### `deposit`

[![Dialogs ✅](https://img.shields.io/badge/Dialogs-✅%20Compatible-brightgreen?style=for-the-badge&logo=minecraft)]()

```yaml
- type: deposit
  amount: <amount>
  currency: <currency name>
  economy: <economy name> # Only the zEssentials, CoinsEngine and EcoBits plugins need this
```

Allows you to deposit money from the player’s account. Works with the [BeastTokens](https://www.spigotmc.org/resources/beasttokens-custom-currency.20806/), [Vault](https://www.spigotmc.org/resources/34315/), [PlayerPoints](https://www.spigotmc.org/resources/80745/), [ElementalTokens](https://builtbybit.com/resources/16707/), [ElementalGems](https://builtbybit.com/resources/14920/), [Level](https://www.minecraft.net/), [Experience](https://www.minecraft.net/), [**zEssentials**](https://www.spigotmc.org/resources/118014/), [EcoBits](https://www.spigotmc.org/resources/109967/), [CoinsEngine](https://www.spigotmc.org/resources/84121/) and [VotingPlugin](https://www.spigotmc.org/resources/15358/).\
CurrenciesAPI : [https://github.com/Traqueur-dev/CurrenciesAPI](https://github.com/Traqueur-dev/CurrenciesAPI)

***

### `title`

[![Dialogs ✅](https://img.shields.io/badge/Dialogs-✅%20Compatible-brightgreen?style=for-the-badge&logo=minecraft)]()

```yaml
- type: title
  title: <title>
  subtitle: <sub title>
  start: <start in milliseconds>
  duration: <duration in milliseconds>
  end: <end in milliseconds>
```

Send a title. You can use placeholders and color/format codes here. **MiniMessage** format is enabled by default if your server supports it.

***

### `teleport`

[![Dialogs ✅](https://img.shields.io/badge/Dialogs-✅%20Compatible-brightgreen?style=for-the-badge&logo=minecraft)]()

```yaml
- type: teleport
  world: <world> # default world is "world"
  x: <x>
  y: <y>
  z: <z>
  yaw: <yaw>
  pitch: <pitch>
```

Teleport a player

***

### `discord`

[![Dialogs ✅](https://img.shields.io/badge/Dialogs-✅%20Compatible-brightgreen?style=for-the-badge&logo=minecraft)]()

```yaml
- type: discord
  webhook: "https://discord.com/api/webhooks/<url>"
  message: "Test webhook"
```

Allow to send a discord webhook. You can add a embeds, username, tts etc.

```yaml
- type: discord
  webhook: <url>
  message: <content>
  avatar: <avatar url>
  username: <webhook username>
  embeds:
    - title: <embed title>
      description: <embed description>
      url: <url>
      color: <hex color>
      footer:
        text: <text footer>
        icon-url: <icon url>
      thumbnail:
        url: <url>
      image:
        url: <url>
      author:
        name: <author name>
        url: <author url>
        icon-url: <author icon url>
      fields:
        - name: <field name>
          value: <field value>
          inline: true/false
```

***

### `discord component`

[![Dialogs ✅](https://img.shields.io/badge/Dialogs-✅%20Compatible-brightgreen?style=for-the-badge&logo=minecraft)]()

```yaml
- type: discord component
  webhook: "https://discord.com/api/webhooks/<url>"
  username: "GroupeZ" #Optional
  avatar_url: "" #Optional
  component: [
    {
      "type": 10,
      "content": "Never trust a alien with a giant spaghetti."
    },
    {
      "type": 14,
      "divider": true,
      "spacing": 2
    },
    {
      "type": 10,
      "content": "If life gives you invisible unicorn, make invisible unicorn soup."
    },
    {
      "type": 17,
      "accent_color": 14951974,
      "spoiler": true,
      "components": [
        {
          "type": 10,
          "content": "Never trust a grandma with a giant spaghetti."
        }
      ]
    }
  ]
```

Send a [webhook discord components](https://discord.com/developers/docs/components/reference). To generate your component you must go to the site [https://discord.builders/](https://discord.builders/), then you must copy the result json. You can simplify your json into one line [here](https://jsonformatter.org/json-minify).

### `permission set`

[![Dialogs ✅](https://img.shields.io/badge/Dialogs-✅%20Compatible-brightgreen?style=for-the-badge&logo=minecraft)]()

<pre class="language-yaml"><code class="lang-yaml">- type: permission set
<strong>  permission: &#x3C;permission>
</strong>  value: &#x3C;true/false>
</code></pre>

Allows you to add or remove a permission from a player, works with luckperms.

***

### `toast`

[![Dialogs ✅](https://img.shields.io/badge/Dialogs-✅%20Compatible-brightgreen?style=for-the-badge&logo=minecraft)]()

```yaml
- type: toast
  toast-type: <TASK/GOAL/CHALLENGE>
  message: <your message>
  material: <material>
  model-id: <material model id> # Default is 0 #Can be a float value or string for itemModel "<namespace>:<model name>"
  glowing: <true/false>
```

Allows you to send a toast message to the player. You can use a material from another plugin to define the material and model id to use.

***

## zQuests

Lists of actions working with the [zQuests](https://groupez.dev/resources/zquests.335) plugin.

### `start quest`

```yaml
- type: start quest
  quests:
    - <quest name>
```

Allows you to start several quests.

***

## zJobs

Lists of actions working with the [zJobs](https://groupez.dev/resources/zjobs.336) plugin.

### `zjobs add points`

```yaml
- type: zjobs add points
  points: <points>
```

Allows you to add job points

***

### `zjobs claim reward`

```yaml
- type: zjobs claim reward
  reward: <reward id>
```

Allows you to claim a reward

***

### `zjobs remove points`

```yaml
- type: zjobs remove points
  points: <points>
```

Allows you to remove job points

***
