# cmd-msg-capture

Demo solution for https://www.spigotmc.org/threads/how-to-set-to-variable-output-of-executed-command.314410

I thought that this problem was interesting enough to have a project of its own. Oftentimes, a player might execute a command, and the messages that get sent to the player need to be recorded by the plugin either for logging purposes or other. There isn't already existing built-in functionality for this, but by providing our own sender for the command and intercepting the command pre-processor, we can make it look like our own player sent the command rather than the actual player.

Everything then gets delegated back to the original player, but we now have access to Player#sendMessage(String), which can be used to record whatever gets sent to the player. This is actually a surprisingly elegant solution in spite of the length of the delegation overrides.
