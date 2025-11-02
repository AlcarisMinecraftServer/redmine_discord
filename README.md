# Redmine Discord

This plugin sends webhook notifications from Redmine to specified Discord channels
using [Discord’s Webhook API](https://discordapp.com/developers/docs/resources/webhook).

## Installation

1. Clone this repository and install dependencies:

   ```bash
   git clone https://github.com/AlcarisMinecraftServer/redmine_discord plugins/redmine_discord
   cd redmine_discord
   bundle install
   ```

2. Restart Redmine to apply the changes.

## Setting up Webhook URLs

1. Open **Administration > Custom fields** in Redmine.

2. Create a new custom field for **Projects**.

3. Configure it as follows:

   | Property        | Value                                         |
   | --------------- | --------------------------------------------- |
   | Format          | List                                          |
   | Name            | Discord Webhooks *(case-sensitive)*           |
   | Multiple values | Enabled                                       |
   | Visible         | Disabled (recommended)                        |
   | Possible values | Paste your Discord Webhook URLs, one per line |

4. Save the custom field.

5. Go to each project's settings and enable **Discord Webhooks** under the “Custom fields” section.

Once this is done, the plugin can send messages to the specified Discord channels.

## Additional Required Settings

For embedded links in Discord messages to work properly,
configure the following setting in Redmine:

**Administration > Settings > General > Host name and path / Protocol**

* In most cases, you can copy the address shown just below the input field.
* If that does not work, enter the server’s hostname **without** the protocol (e.g., `redmine.example.com` instead of `https://redmine.example.com`).
