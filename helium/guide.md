# Guide

Step 1 - Creating a Rank

Type /rank in chat to view the full list of commands.

* &#x20;![image](https://github.com/Plasma-Development-Services/Helium-Docs/assets/97298369/22b80019-6a0e-4a08-a46f-5e44712725a4)

After that is done and you have the list of commands, you can do /rank create . I'm going to use the Test rank for now. After you have created your rank, it will open a GUI where you can edit everything about the rank.

### Step 2 - Edit a Rank

We're going to edit a rank with the command /rank edit

* &#x20;![image](https://github.com/Plasma-Development-Services/Helium-Docs/assets/97298369/739eaac6-6a56-499b-8a2c-e3dacb28b6ab)

Now you will get a GUI with all the stuff you can edit for that rank. I'm going to change the color.&#x20;

* ![image](https://github.com/Plasma-Development-Services/Helium-Docs/assets/97298369/b86bac05-4b52-4090-b7f6-19245d9a9a4c)

In here you can choose every color you want, I'll go for dark red.

Now we're going to change the prefix of the rank.

* &#x20;![image](https://github.com/Plasma-Development-Services/Helium-Docs/assets/97298369/fb5f27b9-4584-411f-ad24-4329d0f6c44f)

Once you have granted you or someone else the rank (/grant), you can type in chat and see the prefix and color.

* &#x20;![image](https://github.com/Plasma-Development-Services/Helium-Docs/assets/97298369/a7c841e7-2142-4016-a503-f70de256614b)

To add a permission to a rank you edit the rank again, and click Permissions. You should see this menu after doing this.

* &#x20;![image](https://github.com/Plasma-Development-Services/Helium-Docs/assets/97298369/2ffdf4db-734a-4799-afb5-ae599868ff7a)

Once you have added the permission, you can view the permissions GUI and see the permission you have added&#x20;

* ![image](https://github.com/Plasma-Development-Services/Helium-Docs/assets/97298369/0b97cbfc-2335-4481-a1f5-e30edd2d46bb)

### Step 3 - Granting a Player

If you are granting a player a rank in game, type /grant

This will pop up a menu where you can grant a player a rank, permission, or tag, as seen below:

* ![image](https://github.com/Plasma-Services/Helium-Docs/assets/97298369/e2fddf33-0c74-4df7-a0ee-ac45ce7573c1)

If you select rank, you will see this:

![](https://github.com/Plasma-Services/Helium-Docs/assets/97298369/5f14cb3a-52ed-4ff9-9183-2138e1e2df9d)

If it comes back and says that you can't grant a rank with a higher priority then your rank, you will need to grant the rank via console.

The command to do so is `cgrant <type> <context> <target> <duration> <reason>`. The types are `rank`, `bungeepermission`, `bukkitpermission`, and `tag`.
