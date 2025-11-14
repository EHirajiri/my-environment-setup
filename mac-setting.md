# Macの環境設定

## Terminalで起動するシェルを zsh -> bash に変更したい場合

- 現在のシェルを確認
```
$ echo $SHELL
/bin/bash
```

- シェルの一覧を確認
```
$ echo $SHELL
/bin/bash
HirajirinoMacBook-Air:~ hirajiri$ cat /etc/shells 
# List of acceptable shells for chpass(1).
# Ftpd will not allow users to connect who are not using
# one of these shells.

/bin/bash
/bin/csh
/bin/dash
/bin/ksh
/bin/sh
/bin/tcsh
/bin/zsh
```

- bashに変更
```
$ chsh -s /bin/bash
```

- Terminalを再起動すると起動時メッセージが出るので表示されないように環境変数を追加
```
Last login: Fri Nov 14 23:14:35 on ttys003

The default interactive shell is now zsh.
To update your account to use zsh, please run `chsh -s /bin/zsh`.
For more details, please visit https://support.apple.com/kb/HT208050.
```

```
$ echo "export BASH_SILENCE_DEPRECATION_WARNING=1" >> ~/.zprofile 
```
