---
title: "Linux Gaming"
date: 2021-01-29T20:21:41+02:00
draft: false
toc: false
images:
tags:
  - linux
  - gaming
---

### Gaming on Linux?

For a while there has been a debate going around with regards to gaming on linux. Most PC gamers use Microsoft Windows, however, for those linux enthusiasts who swear by linux but are bound to playing games on windows, you have nothing to fear because there is finally a solution. Thanks to Valve’s ProtonDB and its integration with Steam, you can now finally play all your Steam games on Linux. In the past people have tried to use Wine to run windows games but you were more likely to encounter errors when installing a game or piece of software.

**Please note this will only work if you are using the apt package manger found on Debian based systems**

#### How to Install:

#### Step 1: Install Wine

```bash
sudo dpkg --add-architecture i386
```

**Note that as of Ubuntu 20.04, apt-key will be deprecated and unusable. Please perform the command below in order to add the repository key**

```bash
wget -nc https://dl.winehq.org/wine-builds/winehq.key
gpg --no-default-keyring --keyring ./winehq.gpg --import winehq.key
gpg --no-default-keyring --keyring ./winehq.gpg --export winehq.gpg
mv winehq.gpg /etc/apt/trusted.gpg.d/
sudo apt update
```

Then add the repository (Ubuntu version 21.04)

_Refer to [wiki.winehq.org/Ubuntu](https://wiki.winehq.org/Ubuntu) for older versions of Ubuntu_

```bash
sudo add-apt-repository 'deb https://dl.winehq.org/wine-builds/ubuntu/ hirsute main'
```

Finally install the latest stable branch of wine

```bash
sudo apt install --install-recommends winehq-staging
```

#### Step 2: Install GameMode

```bash
sudo apt install gamemode
```

#### Step 3: Install Steam and Proton

```bash
sudo apt install steam
```

Once Steam has finished installing, navigate over to Steam / Settings / Steam Play / Advanced and tick the Enable Steam Play for all other titles, and restart to apply this setting.

To enable Gamemode for a game, click on the Properties of a game, navigate to SET LAUNCH OPTIONS and type in `“gamemoderun %command%”`

#### Step 4: Install Lutris and enable game mode for other game titles

```bash
sudo add-apt-repository ppa:lutris-team/lutris
sudo apt-get update
sudo apt-get install lutris
```

To enable it to work with Gamemode, then navigate to Preferences / System options / Command prefix and type in gamemoderun, and once done, click Save.

Note that you will need to tick the show advanced options to see the Command prefix option.

#### Conclusion

So you should now be able to run most of your Steam games on linux and with the use of wine installed, you can now also install other windows software such as Office, Notepad etc...
