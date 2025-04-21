# Reaction Roles

### Creating a reaction role message

This creates a new embedded message that users can react to in order to get roles.

* `/reactionrole create title:<title> description:<description> [channel:<channel>]`\
  `Title`: The title for the reaction role embed\
  `Description`: Description explaining the reaction roles (supports \n for new lines)\
  `Channel`: Optional channel to send the message in (defaults to current channel)

### Adding roles to a message

This adds emoji-role pairs to your reaction role message.

* `/reactionrole add message_id:<message_id> emoji:<emoji> role:<role>`\
  `Message_id`: ID of the reaction role message\
  `Emoji`: Emoji to use for the reaction (unicode or custom)\
  `Role`: Role to give when users react with the emoji

### Removing roles from a message

This removes an emoji-role pair from your reaction role message.

* `/reactionrole remove message_id:<message_id> emoji:<emoji>`\
  `Message_id`: ID of the reaction role message\
  `Emoji`: Emoji of the reaction role to remove

### Listing reaction role messages

This shows all reaction role messages in your server.

* `/reactionrole list`

### Command Examples

#### Creating a reaction role message

```
/reactionrole create title:Choose Your Roles description:React to get roles!\n\n🎮 - Gamer\n💸 - Economy\n🎵 - Music
```

#### Adding a role

```
/reactionrole add message_id:123456789012345678 emoji:🎮 role:@Gamer
```

#### Removing a role

```
/reactionrole remove message_id:123456789012345678 emoji:🎮
```

### Features

* **Role Assignment**: Users receive roles when adding reactions
* **Role Removal**: Roles are removed when reactions are removed
* **Multiple Roles**: Unlimited emoji-role pairs per message
* **Multiple Messages**: Create different reaction role messages for different categories
* **Exclusive Roles**: Option to make roles exclusive (users can only select one from a message)
* **Custom Formatting**: Use \n for new lines in descriptions

### Troubleshooting

#### Roles not being assigned

* Ensure the bot has the "Manage Roles" permission
* Check that the bot's role is higher than the roles it's trying to assign
* Verify the emoji is correctly configured in the database

#### Reactions not working

* Make sure the bot has the "Add Reactions" permission
* Confirm you're using valid emojis (standard Unicode or from your server)
* Check if the message still exists and hasn't been deleted

#### Command errors

* Verify you're using the correct message ID
* Ensure all parameters are properly formatted
* Check that the role exists and is mentionable
