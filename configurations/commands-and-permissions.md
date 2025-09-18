# 📜 Commands and Permissions

## Commands

<table data-full-width="true"><thead><tr><th>Command</th><th>Permission</th><th>Description</th></tr></thead><tbody><tr><td><code>/zm</code> (aliases: <code>/zmenu</code>)</td><td><code>zmenu.use</code></td><td>Display the list of commands.</td></tr><tr><td><code>/zm open &#x3C;menu> [&#x3C;player>] [&#x3C;display message>] [&#x3C;args>]</code></td><td><code>zmenu.open</code></td><td>Opens the specified inventory.</td></tr><tr><td><code>/zm reload</code></td><td><code>zmenu.reload</code></td><td>Reload configurations.</td></tr><tr><td><code>/zm reload config</code></td><td><code>zmenu.reload</code></td><td>Reload <code>config.json</code> and <code>messages.yml</code> files.</td></tr><tr><td><code>/zm reload inventory [&#x3C;inventory name>]</code></td><td><code>zmenu.reload</code></td><td>Reload inventory files.</td></tr><tr><td><code>/zm reload command [&#x3C;command name>]</code></td><td><code>zmenu.reload</code></td><td>Reload command files.</td></tr><tr><td><code>/zm version</code></td><td>-</td><td>Show plugin version.</td></tr><tr><td><code>/zm convert</code></td><td><code>zmenu.convert</code></td><td>Convert DeluxeMenu to zMenu.</td></tr><tr><td><code>/zm list</code></td><td><code>zmenu.list</code></td><td>Display the list of inventories.</td></tr><tr><td><code>/zm create &#x3C;file name> &#x3C;inventory size> &#x3C;inventory name></code></td><td><code>zmenu.create</code></td><td>Create a new inventory file. You can add items afterward.</td></tr><tr><td><code>/zm save &#x3C;item name></code></td><td><code>zmenu.save</code></td><td>Save the item you have in hand in the plugin configuration format.</td></tr><tr><td><code>/zm giveopenitem &#x3C;inventory> [&#x3C;player>]</code></td><td><code>zmenu.open.item</code></td><td>Retrieve the item used to open the inventory during a click.</td></tr><tr><td><code>/&#x3C;command></code></td><td>Custom permission</td><td>Open a specific file.</td></tr><tr><td><code>/zm contributors</code></td><td><code>zmenu.contributors</code></td><td>Display contributors name</td></tr><tr><td><code>/zm dumplog</code></td><td><code>zmenu.dumplog</code></td><td>Create mclog with your lastest logs</td></tr><tr><td><code>/zm addons</code></td><td><code>zmenu.addons</code></td><td>Display zmenu's addons</td></tr><tr><td><code>/zm dialog</code></td><td><code>zmenu.dialogs</code></td><td>Display dialogs commands</td></tr><tr><td>              </td><td></td><td></td></tr></tbody></table>

List of commands for the player data system can be found [here](player-data.md).

### Open Command with Arguments

You can use the `/zm open` command with arguments (more details [here](commands.md#informations)).

For example, with the default inventory `example_punish`, you can define two arguments to be used. You can do this in two ways:

* **Specify Argument Names**: Use `<argument name>:<argument value>` format.
  * Example: `/zm open zmenu:example_punish Maxlego08 false target:Maxlego09 reason:test`
  * Result: `%zmenu_argument_target%` and `%zmenu_argument_reason%`
  * You can also add more arguments: `/zm open zmenu:example_punish Maxlego08 false target:Maxlego09 reason:"this is a really long reason"`
* **Use Values Directly**: The argument names will be indexed as 0, 1, etc.
  * Example: `/zm open zmenu:example_punish Maxlego08 false Maxlego09 test`
  * Result: `%zmenu_argument_0%` and `%zmenu_argument_1%`
