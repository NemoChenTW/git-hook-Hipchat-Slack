# git-hook-Hipchat-Slack
Combine two git hook hipchat &amp; slack together.

This repository reference from [Git HipChat Hook](https://github.com/eirc/git-hipchat-hook) and [Git post-receive hook for Slack](https://github.com/chriseldredge/git-slack-hook).

#Prepare
To use this hook, you need the following items.

1. git-hook-Hipchat-Slack (Modify from [Git post-receive hook for Slack](https://github.com/chriseldredge/git-slack-hook).
2. git-hipchat-hook (Package under [git-hook-Hipchat-Slack](https://github.com/NemoChenTW/git-hook-Hipchat-Slack.git) as submodule. 
or you can download from the [origianl repo.](https://github.com/eirc/git-hipchat-hook))
3. [hipchat-cli](https://github.com/hipchat/hipchat-cli)


#How to Install.

Clone git-hook-Hipchat-Slack.
```
git clone https://github.com/NemoChenTW/git-hook-Hipchat-Slack.git
```
Rename `git-hook-Hipchat-Slack` to `post-receive`, and put it under your git repository's `hooks` folder.

* Bare repository
```
cd git-hook-Hipchat-Slack
cp git-hook-Hipchat-Slack /path/to/your/repo/hooks/post-receive
```
* Normal repository
```
cd git-hook-Hipchat-Slack
cp git-hook-Hipchat-Slack /path/to/your/repo/.git/hooks/post-receive
```

Download git-hipchat-hook
```
cd git-hook-Hipchat-Slack
git submodule init
git submodule update
```

Clone hipchat-cli 
```
git clone git://github.com/hipchat/hipchat-cli.git
```

Modify HipChat related info in post-receive.
```
HIPCHAT_SCRIPT="/path/to/hipchat_room_message"
HIPCHAT_ROOM="HipChat room name or room_id"
HIPCHAT_TOKEN="1234567890"
HIPCHAT_FROM="GIT"

. /path/to/git-hipchat-hook/hipchat-post-receive
```

Set post-receive allow executed.
```
chmod +x post-receiv
```

You can find more detial from origianl authors.
* [Git HipChat Hook](https://github.com/eirc/git-hipchat-hook)
* [Git post-receive hook for Slack](https://github.com/chriseldredge/git-slack-hook)
