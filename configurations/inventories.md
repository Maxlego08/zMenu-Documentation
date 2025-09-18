---
description: All information on inventories.
---

# 👨‍💻 Inventories

Informations

## Overview

The plugin includes an `inventories` folder that will contain all your inventories. Each inventory is represented by a separate file, allowing you to create as many inventories as needed, and you can organize them into subfolders.

In the default configuration, you have the following structure:

```
|- inventories
  |- test
    |- test3
      - example3.yml
    - example2.yml
  - example.yml
  - example_shop.yml
  - example_punish.yml
```

***

## Syntax

***

### `name`

```yaml
name: "&8Example #ff6677Hex Color"
```

The name of the inventory that will be displayed in-game. You can use colors (`&<code>`) to format the text and placeholders (`%placeholder%`) to dynamically insert values, such as player names or other variables. Keep in mind that some server versions may impose a character limit on inventory titles.

If your inventory has multiple pages, use these placeholders:

* `%page%` - Current page number
* `%maxPage%` - Last page number

***

### `size`

```yaml
size: 54
```

Defines the number of slots in the inventory. The size must be a multiple of 9, as Minecraft inventories are organized in rows of 9 slots. The inventory size can range from **9** to **54**, which translates to 1 to 6 rows. The valid options are:

* 9 (1 row)
* 18 (2 rows)
* 27 (3 rows)
* 36 (4 rows)
* 45 (5 rows)
* 54 (6 rows)

### `type`

```yaml
type: CHEST
```

Allows to modify the [inventory type](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/event/inventory/InventoryType.html) attention you can not put CRAFTING and PLAYER.

***

### `fill-item`

```yaml
fill-item:
  material: BLACK_STAINED_GLASS_PANE
```

This option allows you to fill all empty inventory slots with a specific item stack. This is useful for creating a consistent visual layout or preventing empty slots from being displayed. Refer to the [item information](items.md) for more details on how to define item stacks.

***

### `update-interval`

```yaml
update-interval: 1000 # 1000ms = 1s
```

Specifies how often the buttons in the inventory should be refreshed, in milliseconds. This is useful for dynamic inventories that need to update their content regularly, such as displaying live player stats. Note that for buttons to be updated, they must have the update option enabled. More details can be found [here](buttons.md#update).

***

### `clear-inventory`

```yaml
clear-inventory: true
```

When set to true, this option clears the player's inventory upon opening the custom inventory and restores it when closing. This is particularly useful for displaying an unobstructed view or image within the inventory without any interference from the player's items.

***

### `matrix`

The matrix configuration helps organize items visually in an inventory by representing slot arrangements using characters. Each character in the matrix corresponds to an item defined in the items section, making it easier to create complex layouts.

In the example below, the inventory is named `&8Test` and has a size of 54 slots. The **matrix** defines the arrangement of items in the inventory, where the character `A` represents slots filled with diamonds. This creates a bordered layout with diamonds. The **items** section maps the character `A` to a diamond item, making the configuration more intuitive and simplifying the creation of visually structured inventories.

```yaml
name: "&8Test"
size: 54
matrix:
  - "AAAAAAAAA"
  - "A       A"
  - "A       A"
  - "A       A"
  - "A       A"
  - "AAAAAAAAA"
items:
  A:
    item:
      material: DIAMOND
```

***

### `items`

```yaml
items: <buttons>
```

Defines the buttons or items that will be placed in the inventory. Each button can be configured to perform specific actions, such as executing commands or opening other inventories. For detailed information on configuring buttons, please refer to the [button configuration guide](https://zmenu.groupez.dev/configurations/buttons).

***

### `open-with-item`

Opens the inventory through interaction with an item. You must define the item's details, the actions to be performed (full list [here](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/block/Action.html)), and the type of verification required.

```yaml
# Open this menu by clicking a specific item
# You can use /zm giveopenitem <inventory> <player> to retrieve the item to use
#
open-with-item:
  # Define the item that will be clicked
  item:
    material: compass
    name: "&eOpen Basic Inventory"
    lore:
      - "&7Click on me !"
  # Look at https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/block/Action.html
  actions:
    - RIGHT_CLICK_BLOCK
    - RIGHT_CLICK_AIR
  # Define the type of verification.
  # Depending on your configuration and need you will define a certain type of verification. Here are all the types that exist:
  # - full -> Allows to check the itemStack in full, will use the ItemStack#isSimilar method.
  # - material -> Allows to check only the material
  # - name -> Allows to check only the display name
  # - lore -> Allows to check only the lore
  # - modelid -> Allows to check only the Custom Model Id
  type: full
```

***

### `open-requirement`

For more information, refer to [here](requirements.md#open-requirement).

***

### `translated-name`

Allows you to translate the inventory name into multiple languages.

```yaml
# Inventory name (https://docs.zmenu.dev/configurations/inventories#name)
#
# This is the title of your inventory. You can put anything in it.
# Color code and placeholders are supported.
# If you are on Paper, Purpur or PufferFish you have access to the color code of MiniMessage (https://docs.advntr.dev/minimessage/format.html)
#
name: "&7Basics Inventory"

# Translate the inventory name into multiple languages
# You must define the language and the country used
# The vanilla Minecraft client will use lowercase language / country pairs separated by an underscore, but custom resource packs may use any format they wish.
translated-name:
  - locale: "fr_fr" # Allows to define the language in French
    name: "&aInventaire Basique"
  - locale: "es_es" # Allows to define the language in Spanish
    name: "&aInventario Básico"
```

***

### `patterns`

After creating your [patterns](patterns.md), add them to your inventory like this:

```yaml
size: 54

name: "&4Advanced &cInventory &7%page%&8/&7%maxPage%"
patterns:
  - "pattern_example"
```

You must place the name of your file in the `patterns` folder. You can add as many patterns as you want.

Example from **zAuctionHouseV3**:

```yaml
name: '&8ᴀᴜᴄᴛɪᴏɴ &8(&f%page%&8/&f%maxPage%&8)'  # Title of the menu, supports color codes and placeholders

size: 54  # Size of the Minecraft inventory menu, must be a multiple of 9

patterns:  # List of pattern identifiers used in the menu
  - "zauctionhouse_decoration"  # Pattern for decorative elements
  - "zauctionhouse_pagination"  # Pattern for navigation between menu pages
  - "zauctionhouse_auction"  # Pattern related to auction items or functionalities

items:
  display-items:
    type: ZAUCTIONHOUSE_AUCTION  # Type of items to display, specific to auction house items
    isPermanent: true  # Indicates these items will always be displayed and not dynamically updated
    slots:  # Specifies the slots in the menu for the items
      - 10-16  # Items occupy slots 10 through 16
      - 19-25  # Items occupy slots 19 through 25
      - 28-34  # Items occupy slots 28 through 34
      - 37-43  # Items occupy slots 37 through 43
    else:
      slots:
        - 22
      item:
        material: BARRIER
        name: '&c&nNo Items Found'
```

Using patterns helps reduce the complexity and size of individual inventory configurations by allowing you to define reusable layouts or elements. This is particularly useful for maintaining consistency across multiple inventories and making future adjustments easier.

***

### `conditional-name`

Allows dynamic inventory names based on player [requirements](requirements.md).

```yaml
# Default inventory name displayed if no conditional name matches
name: "&8Example &7Player"

# Conditional names based on player requirements
conditional-name:
  - name: "&8Example &7Admin"  # Display name if the player meets the admin requirements
    priority: 1  # Higher priority, this name will be used if requirements are met
    requirements:
      - type: permission  # Requirement type: permission-based
        permission: zmenu.admin  # The player must have this permission

  - name: "&8Example &7Moderator"  # Display name if the player meets the moderator requirements
    priority: 0  # Lower priority than admin, but higher than the default name
    requirements:
      - type: permission  # Requirement type: permission-based
        permission: zmenu.mod  # The player must have this permission
```

{% hint style="warning" %}
This feature is only available with [zMenu+](../zmenu+.md) !
{% endhint %}

#### `name`

The alternative inventory name displayed when the conditions are met.

#### `priority`

Determines which name is selected if multiple conditions are met. **Higher** values take precedence over lower values.

#### `requirements`

[Requirements](requirements.md) that must be met for a specific name to be applied

{% embed url="https://youtu.be/4MZtWmMXn7I" fullWidth="false" %}

***

### `cancel-item-pickup`

```yaml
cancel-item-pickup: true # Default: false
```

When set to true, this option prevents players from picking up items on the floor while the inventory is open. This is useful to avoid overlapping the inventory with undesirable items.

***

### `target-player-name-placeholder`

```yaml
target-player-name-placeholder: "%zmenu_argument_target%" # Default: "%player_name%"
```

This placeholder is used to parse the inventory items, placeholders and permissions for the target player. By default, it is set to %player\_name%, which refers to the player who opened the inventory.

***

### `enable`

```yaml
enable: true
```

Allows you to activate or not the loading of an inventory.
