# insurgency-sandstorm-host-local-server

## Resources

- [Setup Guide](https://mod.io/g/insurgencysandstorm/r/server-admin-guide)
- [Video Tutorial](https://www.youtube.com/watch?v=zeVC99ZqqTg)

## Steps

Note that this is just an abridged of the Setup Guide above. For more information, check out that link.

### Server Setup

- [Download SteamCMD](https://steamcdn-a.akamaihd.net/client/installer/steamcmd.zip)
	- Unzip SteamCMD and place the uzipped folder in the location where you would like to install the server.
- Open `SteamCMD` and wait for it to update. This can take a few minutes.
- Type `login anonymous` and hit Enter. This will log you in anonymously, allowing you to download most game servers.
- Type `app_update 581330 validate` and hit Enter. This will install and validate the Insurgency: Sandstorm dedicated server.
- Type `quit` and hit Enter once you have received a message stating that the app was fully installed.

After install, a folder called `sandstorm_server` is created located inside `<steamcmd-root-directory>/steamapps/common`

- Navigate to `sandstorm_server` and create a file there called `start.bat`. Paste in these contents:

```txt
InsurgencyServer.exe Oilfield?Scenario=Scenario_Refinery_Checkpoint_Security?MaxPlayers=8 -mutators=AllYouCanEat -motd="i love chips" -Port=27102 -QueryPort=27131 -log -hostname="joostins server" -EnableCheats

```

### Adding Server Admins

Making someone admin is necessary if you want to be able to select different levels. You must first be added to `Admins.txt`:

- Navigate to `sandstorm_server/Insurgency/Config/Server/Admins.txt`. If the path/file do not exist, create them.
- Open `Admins.txt` and paste in your Steam ID. To get this, open Steam and go to your Steam profile. Your steam ID can be found at the end of URL at the page top. It will look something like: `https://steamcommunity.com/profiles/<your-steam-id>/`

The admin panel can be opened in game by pressing `-` on the numpad.

### Game Configuration

To make changes to the rounds (round duration, bot difficulty, bot amount, etc.) you need to add another file:

- Navigate to `Insurgency/Saved/Config/WindowsServer/Game.ini`. Again create the path/file if they do not exist. Paste in the contents of [Game.ini](Game.ini)

## Network

Once complete, run `start.bat` to start the server. Once its up and running you can connect to it.

### Radmin

Anyone who wants to connect will need to install [Radmin VPN](https://www.radmin-vpn.com/).

The person hosting the server will need to open Radmin VPN, and select `Create Network`. Give it a name, password, etc. Have the other people who you want to join connect to your Radmin network.

### Connecting to the Server

Open up Insurgency Sandstorm go to Play > Community Servers > Connect To IP.

If you are hosting, you can enter in: `127.0.0.1:27102` (if no password was provided during server creating, leave the password field blank when prompted)

Other people connecting to the server should connect to the Radmin VPN IP address at the top of the Radmin window, followed by `xxx.xxx.xxx.xxx:27102`

