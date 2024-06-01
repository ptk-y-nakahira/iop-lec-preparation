# 事前準備資料

## 変更履歴

| 変更日時 | 変更内容 | 担当者 |
| --- | --- | --- |
| 2024/06/01 | 初版 | PTK 中平 |

## 1. 概要

本マニュアルでは講座で使用するアプリケーションと、USBシリアル通信を行うためのUSBドライバのインストールを行う手順を説明します

- Arduino IDE のインストール
- Arduino-ESP32 サポート のインストール
- USBドライバのインストール

<div style="{height: 3em}"></div>

---

## 2. Arduino IDEのインストール

Arduino IDE とはArduinoボード上で動作するソフトウェアを開発するために作られた統合開発環境です。ソースコードの編集、マイコンへの書き込み機能などの機能を有します。C言語とC++をベースとした「Arduino 言語」によってプログラムを作成できます。

> ### Arduino とは
> Arduino ボード（ハードウェア）とArduino IDE（ソフトウェア）から構成されるシステムです。ワンボードマイコンの一種であり、I/Oポートを備えることで拡張性に富んだ装置として使用できます。
> オープンソースのハードウェアとソフトウェアであり、簡単な規定さえ守れば誰でも自由に使用できます。

プログラムを開発し、マイコンに書き込むArduino IDE のインストールを行います。

[Arduino IDE 公式サイト](https://www.arduino.cc/en/software)より、インストールファイルをダウンロードします。

![](/images/0001_arduino.jpg)

> ### ZIPファイルも選択できます
> インストーラー（exe, msi）だけでなく、インストール不要のzip圧縮ファイルも選択できます。社用PCなどインストールできない場合にはこちらを選択してください。
> エクスプローラーでファイルを右クリックし「すべて展開」することで解凍され、実行可能になります。

![](/images/0002_arduino.jpg)

寄付やメール登録を促す画面が表示されます。**Just Download** を選択することでパスできます。

![](/images/0003_arduino.jpg)

![](/images/0004_arduino.jpg)

![](/images/0005_arduino.jpg)

![](/images/0006_arduino.jpg)

---

## 3. Arduino-ESP32 サポートのインストール

講座では[ESP32](https://ja.wikipedia.org/wiki/ESP32)というArduinoと互換性のあるマイクロコントローラを使用します。

Arduino IDE でESP32を開発するためのサポート ([Arduino-ESP32 support](https://docs.espressif.com/projects/arduino-esp32/en/latest/installing.html))をインストールします。

まず、Arduino IDEを起動します。

![](/images/0007_esp32.jpg)

**ファイル** > **基本設定** の順にクリックします

下にある **追加のボードマネージャのURL** に注目してください。ここに下記のURLを貼り付けます

```
https://espressif.github.io/arduino-esp32/package_esp32_index.json
```

![](/images/0008_esp32.jpg)

**OK** ボタンをクリックします。


![](/images/0009_esp32.jpg)

**ツール** > **ボード** > **ボードマネージャ** の順にクリックします。

(左側のメニューの上から2番目のアイコンをクリックしても開けます)

![](/images/0010_esp32.jpg)

検索フォームで `esp32` と検索して `esp32 by Espressif Systems` がヒットします。複数表示された場合は 開発元が ESP32の`Espressif Systems` になっているか確認してください。

![](/images/0011_esp32.jpg)

**インストール** ボタンをクリックしてインストールします。（インストールには時間がかかります）

![](/images/0012_esp32.jpg)

---

## 4. USBドライバのインストール

ArduinoIDEを使用してESP32にプログラムを書き込む際には、USBケーブルで接続して通信します。この際に必要なドライバのインストールです。

[参考](https://docs.espressif.com/projects/esp-idf/en/v4.3.4/esp32/get-started/establish-serial-connection.html)

※ 使用するPCやOSのバージョンによって必要ない場合もあります

> ### UARTとは
> PCとESP32との間の通信に使われるプロトコルです。通信は特定のビットレート（**Baud Rate: ボーレート**）で行われます。
> ESP32にプログラムを書き込んだり、ESP32からのデータをリアルタイムで表示(ArduinoIDEのシリアルモニタ機能)できます。

### インストール

[https://www.silabs.com/developers/usb-to-uart-bridge-vcp-drivers?tab=downloads](https://www.silabs.com/developers/usb-to-uart-bridge-vcp-drivers?tab=downloads) からドライバをダウンロードします。

![](/images/0013_cp210x.jpg)

![](/images/0014_cp210x.jpg)

ダウンロードしたファイルを実行してインストールします。

![](/images/0015_cp210x.jpg)

![](/images/0016_cp210x.jpg)

![](/images/0017_cp210x.jpg)

### デバイスマネージャの確認

**Windowsのスタートボタンを右クリック** し、 **デバイスマネージャ** をクリックして開きます

**ポート（COMとLPT）** をクリックして展開します