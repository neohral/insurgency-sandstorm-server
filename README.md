# sandstorm_server

とりあえずmodありでサーバー建てる用

## ここを参考にしてます。
https://mod.io/g/insurgencysandstorm/r/server-admin-guide

## 初期設定
### steamCMDでインストール

https://steamcdn-a.akamaihd.net/client/installer/steamcmd.zip

```
login anonymous
app_update 581330 validate
```

### このプロジェクトはインストール後のディレクトリがルートディレクトリになるので、設定ファイルもろもろを入れる

```
git init
git remote add origin https://github.com/neohral/sandstorm_server.git
git pull origin main
```

### start.batの設定

ポートとか好きにいじる。GameStatsTokenとGSLTTokenは下を見てくれれば

#### GameStatsToken(経験値取得向け)

start.batの設定追加

GameStatsToken

https://gamestats.sandstorm.game/

#### GSLTToken(コミュニティサーバーに表示する向け)

start.batの設定追加

`581320` を指定してトークンを取得。

GSLTToken

https://steamcommunity.com/dev/managegameservers


###  mod.ioのOAuth Accessトークン

[GameUserSettings.ini](Insurgency/Saved/Config/WindowsServer/GameUserSettings.ini)に反映する。

https://mod.io/me/access

```
[/Script/ModKit.ModIOClient]
bHasUserAcceptedTerms=True
AccessToken=ここに取得したトークンを記載
```

### 入れてるmod

2023/10/16時点では使えてそう

[ここにあるやつ](Insurgency/Config/Server/Mods.txt)

* https://mod.io/g/insurgencysandstorm/m/more-ammo-mutator
* https://mod.io/g/insurgencysandstorm/m/medicon
* https://mod.io/g/insurgencysandstorm/m/arbusto
* https://mod.io/g/insurgencysandstorm/m/improvedai
  * https://mod.io/g/insurgencysandstorm/m/zcore
* https://mod.io/g/insurgencysandstorm/m/healthbarplus
