# IamAuth
IamAuth is a simple 1.8.9+ Authentication plugin made by @IamDig (me) with some help from @ItalianG0urmet and @Just1Diaxx (check out their projects!). Of course it's not the best authentication plugin you can find out there, and it's better to use it on small servers instead of big ones. You should also consider the fact that I'm still learning to make plugins, so I ask you not to insult me for how this plugin is made. You should instead give me suggestions to make it better, and of course, since it is open source, you're free to make upgraded versions of the plugin. Don't hesitate to contact me on Discord, both privately (@iamdig_) or by joining my ![Discord Server](https://discord.gg/MzaMYZXtg2)

## Features
- ```Registration and Login```: When a player joins, if he hasn't got one already, he must register himself by creating a password that he'll have to use to log into the server when joining again. This feature protects from eventual account thefts, especially in SP servers. If a player wanna change is password, he can, but he has to remember the old one. Otherwise, a Staff Member can unregister the player.
- ```Passwords File```: Passwords are stored in a "password.yml" file (that can be found in the "IamAuth" folder) by the player's UUID, so that the password doesn't change if the server is premium, while in SP servers there's no difference by doing it by the player's name, since the UUID is generated by the name. Its main function is to store passwords, but it can be used to recover them, but it's not reccomended since you should do a name-UUID convertion and there's already the possibility to unregister a player. You can reload it by the /auth reload command.
- ```Full plugin configuration```: The plugin is completely customizable by the "config.yml" file (once again, it can be found in the "IamAuth" folder).

## Commands
- ```/register [password] [confirm password]```
- ```/login [password]```
- ```/changepass [old password] [new password]```
- ```/unregister [player]```
- ```/auth reload```
- ```/auth help```

## Permissions
- ```iamauth.unregister```: required to use the /unregister command
- ```iamauth.reloadconfig```: required to use /auth reload
- ```iamauth.help```: required to use /auth help

## Configuration file
```yml
#   ---    /\    |\  /|    /\    |   | ----- |   |
#    |    /  \   | \/ |   /  \   |   |   |   |---|
#    |   /----\  |    |  /----\  |   |   |   |   |
#   --- /      \ |    | /      \ |___|   |   |   |


login-timer: 60 # Seconds
timer-expired-kick-reason: "&8[&e&l!&8] &cYou took too much time to log in! &8[&e&l!&8]"
register-auth-message:
  - "&cYou have to register to log into the server!"
  - "&4&l-> &7Use &c/register [password] [confirmpassword]&7 to register"
login-auth-message:
  - "&cLog into the server with your password!"
  - "&4&l-> &7Use &c/login [password] &7to log in"
register-command-message:
  - "&aYou successfully registered your account!"
  - "&4&l-> &7Change password with &c/changepass [old-pw] [new-pw]"
login-command-message:
  - "&aYou successfully logged into the server!"
  - "&4&l-> &7Change password with &c/changepass [old-pw] [new-pw]"
already-registered-message:
  - "&cYou cannot do that! You are already registered!"
already-logged-message:
  - "&cYou cannot do that! You are already logged in!"
wrong-password-message:
  - "&8[&e&l!&8] &4Wrong password!"
  - "&7Try again: &c/login [password]"
different-passwords-message:
  - "&8[&e&l!&8] &4Different passwords!"
  - "&7Try again: &c/register [password] [confirmpassword]"
invalid-command-usage:
  - "&cInvalid command usage!"
  - "&eCorrect usage &8-> &c%usage%"
missing-permission-message:
  - "&cYou do not have permission to execute this command"
  - "&eRequired permission &8-> %permission%"
player-not-found-message:
  - "&cPlayer is offline or does not exist."
  - "&4-> &7You can see the list of online players by pressing &cTAB &7while typing the command"
login-command-usage: "/login [password]"
register-command-usage: "/register [password] [confirmpassword]"
unregister-command-usage: "/unregister [player]"
auth-command-usage: "/auth reload, /auth help"
changepassword-command-usage: "/changepass [old-pw] [new-pw]"
changepassword-kick-reason: "&aPassword changed! Reconnect to log in with the new password!"
unregister-kick-reason: "&4You have been unregistered! Reconnect to register again!"
unregister-command-message:
  - "&aSuccessfully unregistered %target%!"
  - "&4-> &7The player now has to register again."
config-reload-message:
  - "&aConfiguration file reloaded successfully!"
  - "&4-> &7Server/plugins/IamAuth/config.yml"
help-message:
  - "&lIam&4&lAuth &8- &3&lHelp"
  - "- &b/register [password] [confirmpassword] &8-> &7Register your account by setting your login password"
  - "- &b/login [password] &8-> &7Log into the server by using the password you set when registering"
  - "- &b/changepass [old-pw] [new-pw] &8-> &7Change your login password."
  - "- &b/unregister [player] &8-> &7Unregister a player so they can set a new password in case they have lost the old one"
  - "&eRequires permission &8-> &ciamauth.unregister"
  - "- &b/auth help &8-> &7Makes you visualize this message"
  - "&eRequires permission &8-> &ciamauth.help"
  - "- &b/auth reload &8-> &7 Reload config.yml"
  - "&eRequires permission &8-> &ciamauth.reloadconfig"
chatting-before-login-message:
  - "&cYou have to log into the server to chat!"
  - "&4-> &7Use &c/register &7 or &c/login"
command-before-login-message:
  - "&cYou have to log into the server to use this command!"
  - "&4-> &7Use &c/register &7 or &c/login"
accepted-commands-before-login:
  - "/login"
  - "/register"
