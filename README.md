# Robosys2021_devicedriver
ロボットシステム学課題1で作ったデバイスドライバ

### 実装内容
LEDを用いて、指定した番号のLEDを点灯させるデバイスドライバを作成した。<br>
上田隆一教授が講義で作成したデバイスドライバに変更を加えて作成した。

講義の動画は[こちら](https://youtu.be/xQW8-FNuboo)。

### 準備する物
・Raspberry Pi 4 ModelB<br>
・ブレッドボード<br>
・LED *3<br>
・抵抗　300KΩ *3<br>
・ジャンパー線 オス-メス *6<br>

### 回路
以下のように回路を組み立てた。

| No. | Name | GPIO | PinNumber | GND |
| ----- | ----- | ----- | ----- | ----- |
| 1 | LED | GPIO24 | 18 | 20 |
| 2 | LED | GPIO25 | 22 | 34 |
| 3 | LED | GPIO26 | 37 | 39 |

GPIO・ピン番号については[こちら](https://www.raspberrypi.com/documentation/computers/os.html)で確認してください。<br>
### ビルド方法
```
$ git clone https://github.com/HarukiOgawa1/Robosys2021_devicedriver.git
$ cd Robosys2021_devicedriver/myled
$ make
$ sudo insmod myled.ko
$ sudo chmod 666 /dev/myled0
```

### 実行方法
点灯させたいLED（左：2、中央：1、右：0）
#### 0を入力した場合
```
$ echo 0 > /dev/myled0
```

#### 1を入力した場合
```
$ echo 1 > /dev/myled0
```

#### 2を入力した場合
```
$ echo 2 > /dev/myled0
```

#### それ以外を入力した場合
LEDが右から左に順番に点滅する。

### 動画

### ライセンス
[COPYING](https://github.com/HarukiOgawa1/Robosys2021_devicedriver/blob/main/COPYING)
