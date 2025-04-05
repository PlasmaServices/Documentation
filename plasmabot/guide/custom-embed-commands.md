# Custom Embed Commands

## Creating a command

* `/embedcommand create id:<command_name> name:<display_name> description: embed_json:<json_structure> [emoji:] [questions:]`&#x20;

`ID`: Unique identifier for the command (2-32 characters, letters, numbers, and underscores only)\
`Name`: Display name for the command\
`Description`: Brief description of what the command does\
`Embed_json`: JSON structure for the embed - [Example](custom-embed-commands.md#json-structure)\
`Response`: Optional text message to accompany the embed\
`Emoji`: Emoji to display with the command

## Editing a command

* `/embedcommand edit name:<command_name> [response:<new_response>] [embed_json:<new_json>]`

## Previewing an Embed

* `/embedcommand preview embed_json:<json_structure>`&#x20;

## JSON Structure

```json
{
  "title": "Your Title",
  "description": "Your description",
  "color": "#3498db",
  "footer": "Footer text",
  "thumbnail": "https://example.com/image.png",
  "image": "https://example.com/image.png",
  "timestamp": true,
  "fields": [
    {
      "name": "Field Name",
      "value": "Field Value",
      "inline": true
    }
  ]
}
```

### Available Embed Elements

* `title`: The title of the embed
* `description`: The main text content
* `color`: Hex color code (e.g., "`#3498db`")
* `footer`: Text to display at the bottom of the embed
* `footer_icon`: URL for the footer icon (optional)
* `thumbnail`: Small image displayed in the top right
* `image`: Large image displayed in the embed
* `timestamp`: Set to `true` to display the current time
* `author_name`: Name of the author
* `author_icon`: URL for the author icon (optional)
* `author_url`: URL for the author name (optional)
* `fields`: Array of field objects with:
  * `name`: Field title
  * `value`: Field content
  * `inline`: Whether fields should display in-line (true/false)

### Placeholders

| Placeholder     | Description                                     |
| --------------- | ----------------------------------------------- |
| `{user}`        | Mentions the user who used the command          |
| `{username}`    | The user's display name                         |
| `{usertag}`     | The user's tag (e.g., Username#1234)            |
| `{server}`      | The server name                                 |
| `{membercount}` | Total member count in the server                |
| `{channel}`     | Mentions the channel where the command was used |
| `{randomuser}`  | Mentions a random user from the server          |

### Command Examples

#### Creating a server info embed

```json
/embedcommand create id:serverinfo name:"Server Info" description:"Displays information about the server" embed_json:{
  "title": "Welcome to {server}!",
  "description": "Hello {user}, welcome to our community!",
  "color": "#2ecc71",
  "footer": "Member #{membercount}",
  "timestamp": true,
  "fields": [
    {
      "name": "Members",
      "value": "{membercount}",
      "inline": true
    },
    {
      "name": "Rules",
      "value": "Check out the rules channel",
      "inline": true
    }
  ]
}
```

### Troubleshooting

#### Command not appearing

* Ensure the command name only contains letters, numbers, and underscores
* Verify the command name is between 2-32 characters
* Make sure the command doesn't conflict with a built-in command

#### Embed is incorrect

* Validate your JSON formatting
* Ensure all URLs are properly formatted and accessible
* Use the `/embedcommand preview` feature to test before creating
* Check if any field values exceed Discord's character limits

#### Placeholder not working

* Verify the placeholder is typed correctly with proper case
* Some placeholders may not work in certain contexts

