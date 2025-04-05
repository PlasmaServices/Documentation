# Custom Commands

## Creating a basic command

* `/command add name:<command_name> response:<text_response>`

`Name`: The command name (2-32 characters, only letters, numbers, and underscores)\
`Response`: The text that the bot will send when the command is used

## Editing a command

* `/command edit name:<command_name> response:<new_response>`&#x20;

## Removing a command

* `/command remove name:<command_name>`&#x20;

## Listing commands

* `/command list`&#x20;

## Command Examples

### Creating a welcome command

* `/command add name:welcome response:Welcome to the server, {user}! We now have {membercount} members!`&#x20;

### Creating a rules command

* `/command add name:rules response:Server Rules:\n1. Be respectful\n2. No spamming\n3. Follow Discord TOS\nRead the full rules in {channel}`



## Troubleshooting

#### Command not appearing

* Ensure the command name only contains letters, numbers, and underscores
* Verify the command name is between 2-32 characters
* Make sure the command doesn't conflict with a built-in command
