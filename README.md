# mypkg  [![test](https://github.com/AkutsuShun/mypkg/actions/workflows/test.yml/badge.svg)](https://github.com/AkutsuShun/mypkg/actions/workflows/test.yml)

このリポジトリは、ロボットシステム学２０２３にて、ROS 2の練習をするためのリポジトリである

# インストール方法
ROS 2をインストールしたのち、下記のコードを実行する
```
$ mkdir -p ros2_ws/src
$ cd ros2_ws/src
$ git clone https://github.com/AkutsuShun/mypkg.git
```

# 機能
本パッケージにはtalkerとlisaterという2つのノードと、countupというトピックが存在し、それぞれの機能は以下のようになっている。

# countup
* 本パッケージのトピック
* talkerからパブリッシュされたint16型符号付き整数のメッセージをlistenerに繋いでいる

# taker
  * 本パッケージのパブリッシャ
  * 0.5秒おきに整数(int16型)を1ずつ増加し、"countup"トピックにパブリッシュする

### 実行例

```
$ ros2 run mypkg talker
（実行後表示なし）
```

# listener
  * 本パッケージのサブスクライバ
  * "countup"トピックよりtalkerがパブリッシュしたデータを受け取り、ターミナル上に表示する

### 実行例と実行結果
taler実行後に実行する

```
$ ros2 run mypkg listener
[INFO] [1703536808.998594218] [listener]: Listen: 0
[INFO] [1703536809.491642769] [listener]: Listen: 1
[INFO] [1703536809.990990862] [listener]: Listen: 2
[INFO] [1703536810.491337279] [listener]: Listen: 3
[INFO] [1703536810.991452616] [listener]: Listen: 4
[INFO] [1703536811.490957362] [listener]: Listen: 5
```

# 2つを同時に実行する方法について
* talk_listen.launchを用いて、2つを同時に実行することも可能

### 実行例と実行結果

```
$ ros2 launch mypkg talk_listen.launch.py
[INFO] [launch]: All log files can be found below /home/"your ID"/.ros/log/2023-12-26-05-49-46-925527-"your PC model number"-24032
[INFO] [launch]: Default logging verbosity is set to INFO
[INFO] [talker-1]: process started with pid [24034]
[INFO] [listener-2]: process started with pid [24036]
[listener-2] [INFO] [1703537387.701038369] [listener]: Listen: 0
[listener-2] [INFO] [1703537388.193531126] [listener]: Listen: 1
[listener-2] [INFO] [1703537388.694028752] [listener]: Listen: 2
[listener-2] [INFO] [1703537389.193988126] [listener]: Listen: 3
[listener-2] [INFO] [1703537389.694004156] [listener]: Listen: 4
[listener-2] [INFO] [1703537390.194048614] [listener]: Listen: 5
```

## 必用なソフトウェア
* Python
* ROS 2

## テスト環境
* Ubuntu 22.04 on windows
  * ROS 2 humble

# 著作権及びライセンスについて
* このソフトウェアパッケージは、３条項ＢＳＤライセンスの下、再頒布及び使用が許可されます。
* このパッケージのコードは，下記のスライド（CC-BY-SA 4.0 by Ryuichi Ueda）のものを，本人の許可を得て自身の著作としたものです．
  * [ryuichiueda/my_slides robosys_2022/lesson8.md](https://ryuichiueda.github.io/my_slides/robosys_2022/lesson8.html#/)
  * [ryuichiueda/my_slides robosys_2022/lesson9.md](https://ryuichiueda.github.io/my_slides/robosys_2022/lesson9.html#/)
  * [ryuichiueda/my_slides robosys_2022/lesson11.md](https://ryuichiueda.github.io/my_slides/robosys_2022/lesson11.html#/)

* © 2023 Akutsu Shun


