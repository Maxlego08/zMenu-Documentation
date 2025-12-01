# 🪁 Items

Before you start configuring the plugin itemstack, make sure you are using the correct material for your version of the game. Each button must be accompanied by an itemstack (except in certain specific cases).

## `material`

```yaml
material: <material>
```

<table data-full-width="true"><thead><tr><th>Type</th><th>Format / Example</th></tr></thead><tbody><tr><td>Material (Bukkit)</td><td><code>material: STONE</code></td></tr><tr><td><a href="https://www.spigotmc.org/resources/placeholderapi.6245/">PlaceholderAPI</a></td><td><code>material: %your_placeholder_material%</code></td></tr><tr><td>Armor (slot)</td><td><code>material: "armor:&#x3C;slot>"</code> (e.g. HEAD, CHEST, LEGS, FEET)</td></tr><tr><td><a href="https://www.spigotmc.org/resources/zhead-database.115717/">zHead (FREE)</a></td><td><code>material: "zhd:&#x3C;id>"</code></td></tr><tr><td><a href="https://polymart.org/resource/magic-cosmetics-20-off.2070">MagicCosmetics (PAID)</a></td><td><code>material: "magic_cosmetics:&#x3C;HAT/BAG/WALKING_STICK/BALLOON/SPRAY>"</code></td></tr><tr><td><a href="https://www.spigotmc.org/resources/hmccosmetics.100107/">Hmccosmetics (PAID)</a></td><td><code>material: "hmc_cosmetics:&#x3C;type>"</code> or <code>material: "hmc_cosmetics:&#x3C;type>-&#x3C;player name>"</code></td></tr><tr><td>zItems (PAID)</td><td><code>material: "zitems:&#x3C;id>"</code></td></tr><tr><td><a href="https://www.spigotmc.org/resources/head-database.14280/">HeadDatabase (PAID)</a></td><td><code>material: "hdb:&#x3C;id>"</code></td></tr><tr><td><a href="https://www.spigotmc.org/resources/%E2%98%84%EF%B8%8F-oraxen-add-items-blocks-armors-hats-food-furnitures-plants-and-gui-1-18-1-20-1.72448/">Oraxen (PAID)</a></td><td><code>material: "oraxen:&#x3C;item name>"</code></td></tr><tr><td><a href="https://www.spigotmc.org/resources/%E2%9C%A8itemsadder%E2%AD%90emotes-mobs-items-armors-hud-gui-emojis-blocks-wings-hats-liquids.73355/">ItemsAdder (PAID)</a></td><td><code>material: "itemsadder:&#x3C;item name>"</code></td></tr><tr><td><a href="https://github.com/Slimefun/Slimefun4">SlimeFun (FREE)</a></td><td><code>material: "slimefun:&#x3C;item name>"</code></td></tr><tr><td><a href="https://github.com/xenondevs/Nova">Nova (FREE)</a></td><td><code>material: "nova:&#x3C;item/block name>"</code></td></tr><tr><td>Base64</td><td><code>material: "base64:&#x3C;item in base64>"</code></td></tr><tr><td>PlayerHead</td><td><code>material: "playerHead:&#x3C;player name>"</code> or <code>material: "playerHead:%player%"</code></td></tr><tr><td><a href="https://modrinth.com/plugin/craftengine">CraftEngine</a></td><td><code>material: "craftengine:&#x3C;item id>"</code></td></tr><tr><td><a href="https://www.spigotmc.org/resources/%E2%9A%94%EF%B8%8Fexecutableitems-%E2%AD%90-customize-all-items-add-abilities-%E2%AD%90-ai-items-generation-on-the-discord-%E2%9C%85.83070/">Executable Items</a></td><td><code>material: "ei:&#x3C;item id>"</code></td></tr><tr><td><a href="https://www.spigotmc.org/resources/%E2%AD%90-executable-blocks-%E2%AD%90-add-activators-on-your-blocks.94696/">Executable Blocks</a></td><td><code>material: "eb:&#x3C;block id>"</code></td></tr><tr><td><a href="https://mcmodels.net/products/13172/nexo?srsltid=AfmBOoqpsyBpLi6QxRwd1dO8lJ6s-wy4KzFhpYdvVgf6c5Q8Wk1-C_bT">Nexo</a></td><td><code>material: "nexo:&#x3C;item id>"</code></td></tr></tbody></table>

***

## `amount`

```yaml
amount: <amount>
```

The amount of the itemstack. You can use a placeholder to have a dynamic amount.

***

## `data`

```yaml
data: <data, only avaible between 1.8 and 1.12>
```

The material data. By default, it's 0.

{% hint style="warning" %}
Only available for versions between 1.8 and 1.12
{% endhint %}

***

## `durability`

```yaml
durability: <durability>
```

The durability of the item, by default, is 0.

***

## `url`

```yaml
url: <player skin in base64>
```

Allows you to display a head with a URL in base64. You can find the values of the heads on the site [minecraft-head.com](https://minecraft-head.com).

You must take the content in the "Value" field under the "Other" category.

![minecraft-head.com example of value](../.gitbook/assets/base64.png)

Example

```yaml
url: "eyJ0ZXh0dXJlcyI6eyJTS0lOIjp7InVybCI6Imh0dHA6Ly90ZXh0dXJlcy5taW5lY3JhZnQubmV0L3RleHR1cmUvNjM3YjhhMzk4MzdiYzNkNThmMDljOGM2ZTUzOTYyZDMzZjlmYTBiNjUzOThhNzc5MzUzYWRlMWUxNDcxM2VmZiJ9fX0="
```

***

## `name`

```yaml
name: <display name>
```

The name that will be displayed on the item. You can use PlaceholderAPI to make the name dynamic.

{% hint style="info" %}
If your server has Kyori Adventure, you can use the [mini message format](https://docs.adventure.kyori.net/minimessage/format.html).
{% endhint %}

***

## `lore`

```yaml
lore:
  - <line1>
  - <line2>
  - <line3>
  - ...
```

Allows you to display the lore of the item. You can use PlaceholderAPI to make the lore dynamic.

## `lore-type`

```yaml
lore-type: REPLACE
```

Defines how the lore is used.\
`REPLACE`, by default, replaces the item's lore.\
`APPEND`, adds the new lore after the existing lore.\
`PREPEND`, adds the new lore before the existing lore.

***

## `potion`

```yaml
  potion: <potion effect type>
  level: <potion level, 1 or 2> # 1 by default
  splash: <potion splash true or false>
  extended: <potion extended true of flase>
  arrow: <potion arrow true or false> # false by default, true for arrow with potion effect
```

Allows you to create a potion. Check potion effect types [here](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/potion/PotionType.html) for more details.

{% hint style="danger" %}
Warning: A potion cannot be extended and have a level 2 at the same time.
{% endhint %}

{% hint style="info" %}
```yml
# For potions in 1.8 up to 1.12 you have to do like this:
material: POTION
durability: 16454
```
{% endhint %}

***

## `glow`

```yaml
glow: <true of false>
```

Allows the item to shine. Add random enchant and HIDE\_ENCHANT itemflag.

***

## `model-id`

```yaml
model-id: <custom model id>
```

Allows you to put a custom model id on the item.

***

## `enchantments`

```yaml
enchants:
  - <enchantment name>,<enchantment level>
```

Allows you to add enchantments. You need to specify the name of the enchantment followed by the level of the enchantment, in the format: `ENCHANT,ENCHANT_LEVEL`.

#### List of enchantments

<table><thead><tr><th width="237">Enchantment</th><th>Aliases</th></tr></thead><tbody><tr><td>damage_all</td><td>alldamage, alldmg, sharpness, sharp, dal</td></tr><tr><td>damage_arthropods</td><td>ardmg, baneofarthropods, baneofarthropod, arthropod, dar</td></tr><tr><td>damage_undead</td><td>undeaddamage, smite, du</td></tr><tr><td>dig_speed</td><td>digspeed, efficiency, minespeed, cutspeed, ds, eff</td></tr><tr><td>durability</td><td>durability, dura, unbreaking, d</td></tr><tr><td>thorns</td><td>thorns, highcrit, thorn, highercrit, t</td></tr><tr><td>fire_aspect</td><td>fireaspect, fire, meleefire, meleeflame, fa</td></tr><tr><td>knockback</td><td>knockback, kback, kb, k</td></tr><tr><td>loot_bonus_blocks</td><td>blockslootbonus, fortune, fort, lbb</td></tr><tr><td>loot_bonus_mobs</td><td>mobslootbonus, mobloot, looting, lbm</td></tr><tr><td>oxygen</td><td>oxygen, respiration, breathing, breath, o</td></tr><tr><td>protection_environmental</td><td>protection, prot, protect, p</td></tr><tr><td>protection_explosions</td><td>explosionsprotection, explosionprotection, expprot, blastprotection, bprotection, bprotect, blastprotect, pe</td></tr><tr><td>protection_fall</td><td>fallprotection, fallprot, featherfall, featherfalling, pfa</td></tr><tr><td>protection_fire</td><td>fireprotection, flameprotection, fireprotect, flameprotect, fireprot, flameprot, pf</td></tr><tr><td>protection_projectile</td><td>projectileprotection, projprot, pp</td></tr><tr><td>silk_touch</td><td>silktouch, softtouch, st</td></tr><tr><td>water_worker</td><td>waterworker, aquaaffinity, watermine, ww</td></tr><tr><td>arrow_fire</td><td>firearrow, flame, flamearrow, af</td></tr><tr><td>arrow_damage</td><td>arrowdamage, power, arrowpower, ad</td></tr><tr><td>arrow_knockback</td><td>arrowknockback, arrowkb, punch, arrowpunch, ak</td></tr><tr><td>arrow_infinite</td><td>infinitearrows, infarrows, infinity, infinite, unlimited, unlimitedarrows, ai</td></tr><tr><td>luck</td><td>luck, luckofsea, luckofseas, rodluck</td></tr><tr><td>lure</td><td>lure, rodlure</td></tr><tr><td>depth_strider</td><td>depthstrider, depth, strider</td></tr><tr><td>frost_walker</td><td>frostwalker, frost, walker</td></tr><tr><td>mending</td><td>mending</td></tr><tr><td>binding_curse</td><td>bindingcurse, bindcurse, binding, bind</td></tr><tr><td>vanishing_curse</td><td>vanishingcurse, vanishcurse, vanishing, vanish</td></tr><tr><td>sweeping_edge</td><td>sweepingedge, sweepedge, sweeping</td></tr><tr><td>loyalty</td><td>loyalty, loyal, return</td></tr><tr><td>impaling</td><td>impaling, impale, oceandamage, oceandmg</td></tr><tr><td>riptide</td><td>riptide, rip, tide, launch</td></tr><tr><td>channeling</td><td>channelling, chanelling, channeling, chaneling, channel</td></tr><tr><td>multishot</td><td>multishot, tripleshot</td></tr><tr><td>quick_charge</td><td>quickcharge, quickdraw, fastcharge, fastdraw</td></tr><tr><td>piercing</td><td>piercing</td></tr><tr><td>soul_speed</td><td>soulspeed, soilspeed, sandspeed</td></tr><tr><td>swift_sneak</td><td>swiftsneak</td></tr><tr><td>breach</td><td>breach</td></tr><tr><td>density</td><td>density</td></tr><tr><td>wind_burst</td><td>windburst, wind, burst</td></tr></tbody></table>

***

## `flags`

```yaml
flags:
  - <flag 1>
  - <flag 2>
  - ...
```

List of flags: [https://hub.spigotmc.org/javadocs/spigot/org/bukkit/inventory/ItemFlag.html](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/inventory/ItemFlag.html)

***

## `color`

```yaml
type: LEATHER_CHESTPLATE
color: 40,150,40 # RGB color

# Example with ARGB
color: 1,40,150,40 # ARGB color, Alpha, RED, GREEN, BLUE
```

Set the RGB color (Red, Green, Blue) for leather armor. The format is as follows:

`<Red>,<Green>,<Blue>`

For example, to set a color with 255 red, 100 green, and 50 blue, you would use:

`255,100,50`

<pre class="language-yaml"><code class="lang-yaml"><strong>color: &#x3C;red>,&#x3C;green>,&#x3C;blue>
</strong></code></pre>

You can also add an alpha value in the color to have ARGB (Alpha, Red, Green, Blue). The format is as follows:

`<Alpha>,<Red>,<Green>,<Blue>`

For example, to set a color with 128 alpha (semi-transparent), 255 red, 100 green, and 50 blue, you would use:

`128,255,100,50`

<pre class="language-yaml"><code class="lang-yaml"><strong>color: &#x3C;alpha>,&#x3C;red>,&#x3C;green>,blue>
</strong></code></pre>

{% hint style="info" %}
The color format for fireworks, banners, and potions follows the same ARGB format:

`<Alpha>,<Red>,<Green>,<Blue>`

For example:

* **Fireworks**: To set a color with 255 alpha (fully opaque), 200 red, 150 green, and 100 blue, you would use: `255,200,150,100`.
* **Banners**: To set a color with 255 alpha, 100 red, 200 green, and 50 blue, you would use: `255,100,200,50`.
* **Potions**: To set a color with 128 alpha (semi-transparent), 255 red, 50 green, and 50 blue, you would use: `128,255,50,50`.

For further details, check the Javadocs for Color [here](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/Color.html#fromARGB\(int,int,int,int\)).
{% endhint %}

***

## `firework`

```yaml
type: FIREWORK
firework:
  star: true
  flicker: true
  trail: true
  type: BALL_LARGE
  colors:
    - 250,10,10 # RGB and ARGB
  fadeColors:
    - 250,10,250 # RGB and ARGB
```

Firework type: [https://hub.spigotmc.org/javadocs/spigot/org/bukkit/FireworkEffect.Type.html](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/FireworkEffect.Type.html)

***

## `banner`

```yaml
type: BANNER
banner: PINK # Banner color
patterns: # Banner pattern: <color>:<pattern>
  - RED:SQUARE_BOTTOM_LEFT
  - GREEN:STRIPE_LEFT
```

Allows you to create a banner. Pattern list: [https://hub.spigotmc.org/javadocs/spigot/org/bukkit/block/banner/PatternType.html](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/block/banner/PatternType.html)

***

## `translated-name`

Allows to translate the name of the item in several languages

```yaml
items:
  example:
    item:
      material: GRASS_BLOCK
      name: "&aThis is a very nice grass block"
      lore:
        - "" 
        - "&eMy first button with &fzMenu"
        - "&7Congratulations, you will now discover"
        - "&7all the possibilities of zMenu."

      # Translate the item name into multiple languages
      # You must define the language and the country used
      # The vanilla Minecraft client will use lowercase language / country pairs separated by an underscore, but custom resource packs may use any format they wish.
      translated-name:
        - locale: "fr_fr" # Allows to define the language in French
          name: "&aC’est un très beau bloc d’herbe !"
        - locale: "es_es" # Allows to define the language in Spanish
          name: "&a¡Es un hermoso bloque de hierba!"
```

***

## `translated-lore`

Allows to translate the lore of the item in several languages

```yaml
items:
  example:
    item:
      material: GRASS_BLOCK
      name: "&aThis is a very nice grass block"
      lore:
        - "" 
        - "&eMy first button with &fzMenu"
        - "&7Congratulations, you will now discover"
        - "&7all the possibilities of zMenu."

      # Translate the item lore into multiple languages
      # You must define the language and the country used
      # The vanilla Minecraft client will use lowercase language / country pairs separated by an underscore, but custom resource packs may use any format they wish.
      translated-lore:
        - locale: "fr_fr" # Allows to define the language in French
          lore:
            - "" # empty line to put space between name and lore
            - "&eMon premier bouton avec &fzMenu"
            - "&7Félicitations, vous allez maintenant découvrir"
            - "&7toutes les possibilités de zMenu."
        - locale: "es_es" # Allows to define the language in Spanish
          lore:
            - "" # empty line to put space between name and lore
            - "&eMi primer botón con &fzMenu"
            - "&7Felicidades, ahora vas a descubrir"
            - "&7todas las posibilidades de zMenu."
```

***

## `max-stack-size`

```yaml
max-stack-size: 2
```

Overrides the default maximum stack size of this item. Choose a number between 1 and 99. max-stack-size must be 1 if max-damage is set.

{% hint style="danger" %}
Only available for 1.21 and above
{% endhint %}

***

## `max-damage`

```yaml
max-damage: 2567
```

Controls the maximum amount of damage an item can take. If not present, the item cannot be damaged. For this to work, you need to make this item a tool if it is not already and then set it's initial damage (usually 0). max-stack-size must be 1 if max-damage is set.

{% hint style="danger" %}
Only available for 1.21 and above
{% endhint %}

***

## `damage`

```yaml
damage: 20
```

The absolute amount of damage or use this item has taken.

{% hint style="danger" %}
Only available for 1.21 and above
{% endhint %}

***

## `repair-cost`

```yaml
repair-cost: 10
```

Number of enchantment levels to add to the base level cost when repairing, combining, or renaming this item with an Anvil.

{% hint style="danger" %}
Only available for 1.21 and above
{% endhint %}

***

## `unbreakable`

```yaml
unbreakable: false
```

Tools, armor and weapons set with this won't lose durability when used.

{% hint style="danger" %}
Only available for 1.21 and above
{% endhint %}

***

## `unbreakable-show-in-tooltip`

```yaml
unbreakable-show-in-tooltip: false
```

If false, an 'Unbreakable' line will not be included in the tooltip. Default is True.

{% hint style="danger" %}
Only available for 1.21 and above
{% endhint %}

***

## `fire-resistant`

```yaml
fire-resistant: false
```

If true, this item will not burn in fire

{% hint style="danger" %}
Only available for 1.21 and above
{% endhint %}

***

## `item-rarity`

```yaml
item-rarity: COMMON
```

Determines the default color of its name. This enum is ordered from least rare to most rare.

* `COMMON` - White item name.
* `EPIC` - Light purple item name.
* `RARE` - Aqua item name.
* `UNCOMMON` - Yellow item name.

{% hint style="danger" %}
Only available for 1.21 and above
{% endhint %}

***

## `hide-tooltip`

```yaml
hide-tooltip: false
```

If present, it will completely hide whole item tooltip (that includes item name). The tooltip will be still visible and searchable in creative mode.

{% hint style="danger" %}
Only available for 1.21 and above
{% endhint %}

***

## `hide-additional-tooltip`

```yaml
hide-additional-tooltip: false
```

If true, disables 'additional' tooltip part which comes from the item type.

{% hint style="danger" %}
Only available for 1.21 and above
{% endhint %}

***

## `enchantment-glint`

```yaml
enchantment-glint: false
```

If true, the item will glint, even without enchantments; if false, the item will not glint, even with enchantments. If null, the override will be cleared.

{% hint style="danger" %}
Only available for 1.21 and above
{% endhint %}

***

## `enchantment-show-in-tooltip`

```yaml
enchantment-show-in-tooltip: true
```

If false, no enchantments will be shown in the item tooltip. Default is true.

{% hint style="danger" %}
Only available for 1.21 and above
{% endhint %}

***

## attribute-show-in-tooltip

```yaml
attribute-show-in-tooltip: true
```

If false. The attributes will not show on the item tooltip. Default is true.

{% hint style="danger" %}
Only available for 1.21 and above
{% endhint %}

***

## `trim`

```yaml
# Only work for armors!
trim:
  enable: false
  # QUARTZ, IRON, NETHERITE, REDSTONE, COPPER; GOLD; EMERALD, DIAMOND, LAPIS, AMETHYST
  material: QUARTZ
  # SENTRY, DUNE, COAST, WILD, WARD, EYE, VEX, TIDE, SNOUT, RIB, SPIRE, WAYFINDER, SHAPER, SILENCE, RAISER, HOST
  pattern: DUNE
```

Allows to define an armor trim, only usable on armor

{% hint style="danger" %}
Only available for 1.20 and above
{% endhint %}

***

## `center-name`

```yaml
center-name: true #Default: false
```

If true, the item name will be centered in the item tooltip. If false, the item name will be left-aligned.

***

## `center-lore`

```yaml
center-lore: true #Default: false
```

If true, the item lore will be centered in the item tooltip. If false, the item lore will be left-aligned.

***

## `tooltip-style`

```yaml
tooltip-style: "<namespace>:<tooltip name>" #Example "minecraft:default"
```

Allows you to set a custom tooltip style for the item. The tooltip style must be defined in a resource pack and can be used to change the appearance of the tooltip.

{% hint style="danger" %}
Only available for 1.21 and above
{% endhint %}

***

## `item-model`

```yaml
item-model: "<namespace>:<model name>" #Example "minecraft:default"
```

Allows you to set a custom item model for the item. The item model must be defined in a resource pack and can be used to change the appearance of the item. Identical to model-id, but for new minecraft versions.

{% hint style="danger" %}
Only available for 1.21 and above
{% endhint %}

***

## `equipped-model`

```
equipped-model: "<namespace>:<model id>"
```

Allows you to define the **asset\_id** of your item

{% hint style="danger" %}
Only available for 1.21 and above
{% endhint %}

***

## `player-inventory`

```yaml
player-inventory: true
```

If set to `true`, the item was placing in the player inventory slot.

{% hint style="warning" %}
This feature is only available with [zMenu+](../zmenu+.md) !
{% endhint %}

## `attributes`

```yaml
attributes:
  - attribute: ARMOR
    operation: ADD_NUMBER
    amount: 10
    slot: HEAD
```

Allows you to modify the attributes of your items.

You must specify each element. You can find the list of attributes on [Spigot’s javadocs](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/attribute/Attribute.html).

#### Operation:

* `ADD_NUMBER`
* `ADD_SCALAR`
* `MULTIPLY_SCALAR_1`

#### Slot:

* `ANY`
* `MAINHAND`
* `OFFHAND`
* `HAND`
* `FEET`
* `LEGS`
* `CHEST`
* `HEAD`
* `ARMOR`
* `BODY`
* `SADDLE`

## `attribute-merge-strategy`

```yaml
attribute-merge-strategy: SUM
```

Allows you to define the behavior of new attributes with those already existing.

#### `REPLACE`

Replace all existing attribute modifiers with the new ones. Any attributes not specified in the custom attributes will be removed.

#### `ADD`

Add new attribute modifiers while keeping all existing ones. This may result in duplicate modifiers for the same attribute.

#### `KEEP_HIGHEST`

For each attribute, keep the modifier with the highest value. If multiple modifiers exist for the same attribute, only the one with max value is kept. If multiple modifiers exist for the same attribute, only the one with min value is kept.

#### `KEEP_LOWEST`

For each attribute, keep the modifier with the lowest value.

#### `SUM`

For each attribute, sum all modifiers with the same operation. Combines the amounts of modifiers that share the same attribute and operation.

