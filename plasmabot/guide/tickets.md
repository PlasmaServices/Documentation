# Tickets

## Creating a ticket

This configures the basic settings for your ticket system.

* `/ticket setup [category] [transcript_channel] [support_role] [closed_category] [retention_days] [inactivity_enabled] [inactivity_days] [high_volume_threshold]`&#x20;

## Adding ticket types

This creates different ticket types. You can add multiple questions by separating them with the `|` character.

* `/ticket add [id] [name] [description] (emoji) (questions)`&#x20;

## Creating the ticket panel

This sends the ticket creation embed

* `/ticket panel`

## Managing settings

This is how you change various settings for your ticket system

* `/ticket settings [max_tickets] [naming_pattern] [welcome_message]`&#x20;

## Closing a ticket

Close a ticket from within the ticket channel

* `/ticket close (reason)`
