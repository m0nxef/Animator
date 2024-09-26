# Animator

Animator is a powerful and flexible Spigot plugin that allows server administrators to create dynamic, animated placeholders for use with PlaceholderAPI.

## Table of Contents

1. [Installation](#installation)
2. [Configuration](#configuration)
3. [Usage](#usage)
4. [Commands and Permissions](#commands-and-permissions)
5. [Placeholder Types](#placeholder-types)
6. [Troubleshooting](#troubleshooting)
7. [FAQ](#faq)

## Installation

1. Ensure you have [PlaceholderAPI](https://www.spigotmc.org/resources/placeholderapi.6245/) installed on your server.
2. Download the latest version of Animator from the [releases page](https://github.com/YourUsername/Animator/releases).
3. Place the downloaded JAR file in your server's `plugins` folder.
4. Restart your server or run the command `/reload confirm` if you have PlugMan installed.
5. The plugin will generate a default configuration file. You can customize this in the next step.

## Configuration

The plugin's configuration is stored in `plugins/Animator/config.yml`. Here's an example configuration with explanations:

```yaml
placeholders:
  admin:
    speed: 50 # Update speed in milliseconds
    type: cycle # Animation type: cycle, random, or blink
    permission: "group.admin" # Permission required to see this placeholder
    text:
      - "&cAdmin"
      - "&bAdmin"
      - "&eAdmin"
  vip:
    speed: 100
    type: random
    permission: "group.vip"
    text:
      - "&6VIP"
      - "&eV&6I&eP"
      - "&#FFD700VIP" # Gold color using hex code
  announcement:
    speed: 5000
    type: cycle
    text:
      - "&aWelcome to our server!"
      - "&bDon't forget to vote!"
      - "&eCheck out our store for cool perks!"
  alert:
    speed: 500
    type: blink
    text:
      - "&c&lALERT"
      - ""
```

Each placeholder is defined by a unique key (e.g., `admin`, `vip`) and has the following properties:
- `speed`: The update interval in milliseconds.
- `type`: The animation type (cycle, random, or blink).
- `permission`: (Optional) The permission required to see the placeholder.
- `text`: A list of text strings to animate through.

## Usage

Once configured, you can use the placeholders anywhere PlaceholderAPI is supported. The format is:

```
%animator_<placeholder_name>%
```

For example:
- `%animator_admin%` would display the animated admin tag.
- `%animator_announcement%` would cycle through your server announcements.

You can use these in plugins like TAB, chat formatting plugins, scoreboard plugins, or any other place that supports PlaceholderAPI.

## Commands and Permissions

| Command | Permission | Description |
|---------|------------|-------------|
| `/Animatorreload` | `Animator.reload` | Reloads the plugin configuration |

## Placeholder Types

Animator supports three types of animations:

1. **Cycle**: Rotates through the list of texts in order, looping back to the start when it reaches the end.
2. **Random**: Randomly selects a text from the list each time the placeholder updates.
3. **Blink**: Alternates between the first text in the list and an empty string, creating a blinking effect.

Choose the type that best fits your needs for each placeholder.

## Troubleshooting

If you're experiencing issues with Animator, try these steps:

1. Ensure PlaceholderAPI is installed and up to date.
2. Check the server console for any error messages related to Animator.
3. Verify that your `config.yml` is correctly formatted.
4. Try reloading the plugin with `/ap reload`.
5. If issues persist, check the [FAQ](#faq) or reach out for support.

## FAQ

Q: How do I use RGB colors?
A: Use the hex color format: `&#RRGGBB`. For example, `&#FF0000` for red.

Q: Can I use multiple placeholders in one message?
A: Yes, you can use as many placeholders as you need in a single message.

Q: How often do placeholders update?
A: Each placeholder updates based on its configured `speed` in milliseconds.

Q: Can I add more placeholder types?
A: The current version supports cycle, random, and blink. For additional types, please suggest them as a feature request on our GitHub issues page.

---

We hope you find Animator useful for your server! If you have any questions or suggestions, please don't hesitate to open an issue on our GitHub repository.
