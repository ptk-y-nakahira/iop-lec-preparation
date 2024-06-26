# 事前準備資料

## 変更履歴

<div style="height: 20em;"></div>

| 変更日時   | 変更内容 | 担当者   |
| ---------- | -------- | -------- |
| 2024/06/01 | 初版     | PTK |

<div style="height: 20em;"></div>

## 1. 概要

本マニュアルでは講座で使用するアプリケーションと、USB シリアル通信を行うための USB ドライバのインストールを行う手順を説明します

- Arduino IDE のインストール
- Arduino-ESP32 サポート のインストール
- USB ドライバのインストール

<div style="height: 20em;"></div>

---

## 2. Arduino IDE のインストール

<div style="height: 3em;"></div>

Arduino IDE とは Arduino ボード上で動作するソフトウェアを開発するために作られた統合開発環境です。ソースコードの編集、マイコンへの書き込み機能などの機能を有します。C 言語と C++をベースとした「Arduino 言語」によってプログラムを作成できます。

<div style="height: 3em;"></div>

> ### Arduino とは
>
> Arduino ボード（ハードウェア）と Arduino IDE（ソフトウェア）から構成されるシステムです。ワンボードマイコンの一種であり、I/O ポートを備えることで拡張性に富んだ装置として使用できます。
> オープンソースのハードウェアとソフトウェアであり、簡単な規定さえ守れば誰でも自由に使用できます。

<div style="height: 5em;"></div>

プログラムを開発し、マイコンに書き込む Arduino IDE のインストールを行います。

[Arduino IDE 公式サイト](https://www.arduino.cc/en/software)より、インストールファイルをダウンロードします。

<div style="height: 5em;"></div>

![](/images/0001_arduino.jpg)

<div style="height: 3em;"></div>

> ### ZIP ファイルも選択できます
>
> インストーラー（exe, msi）だけでなく、インストール不要の zip 圧縮ファイルも選択できます。社用 PC などインストールできない場合にはこちらを選択してください。
> エクスプローラーでファイルを右クリックし「すべて展開」することで解凍され、実行可能になります。

<div style="height: 3em;"></div>

![](/images/0002_arduino.jpg)

<div style="height: 3em;"></div>

寄付やメール登録を促す画面が表示されます。**Just Download** を選択することでパスできます。

![](/images/0003_arduino.jpg)

<div style="height: 3em;"></div>

![](/images/0004_arduino.jpg)

<div style="height: 3em;"></div>

![](/images/0005_arduino.jpg)

<div style="height: 3em;"></div>

![](/images/0006_arduino.jpg)

<div style="height: 30em;"></div>

---

## 3. Arduino-ESP32 サポートのインストール

<div style="height: 3em;"></div>

講座では[ESP32](https://ja.wikipedia.org/wiki/ESP32)という Arduino と互換性のあるマイクロコントローラを使用します。

Arduino IDE で ESP32 を開発するためのサポート ([Arduino-ESP32 support](https://docs.espressif.com/projects/arduino-esp32/en/latest/installing.html))をインストールします。

まず、Arduino IDE を起動します。

<div style="height: 3em;"></div>

![](/images/0007_esp32.jpg)

<div style="height: 3em;"></div>

**ファイル** > **基本設定** の順にクリックします

下にある **追加のボードマネージャの URL** に注目してください。ここに下記の URL を貼り付けます

```
https://espressif.github.io/arduino-esp32/package_esp32_index.json
```

<div style="height: 3em;"></div>

![](/images/0008_esp32.jpg)

**OK** ボタンをクリックします。

<div style="height: 3em;"></div>

![](/images/0009_esp32.jpg)

**ツール** > **ボード** > **ボードマネージャ** の順にクリックします。

(左側のメニューの上から 2 番目のアイコンをクリックしても開けます)

<div style="height: 3em;"></div>

![](/images/0010_esp32.jpg)

<div style="height: 3em;"></div>

検索フォームで `esp32` と検索して `esp32 by Espressif Systems` がヒットします。複数表示された場合は 開発元が ESP32 の`Espressif Systems` になっているか確認してください。

<div style="height: 3em;"></div>

![](/images/0011_esp32.jpg)

<div style="height: 3em;"></div>

**インストール** ボタンをクリックしてインストールします。（インストールには時間がかかります）

<div style="height: 3em;"></div>

![](/images/0012_esp32.jpg)

<div style="height: 30em;"></div>

---

## 4. USB ドライバのインストール

ArduinoIDE を使用して ESP32 にプログラムを書き込む際には、USB ケーブルで接続して通信します。この際に必要なドライバのインストールです。

[参考](https://docs.espressif.com/projects/esp-idf/en/v4.3.4/esp32/get-started/establish-serial-connection.html)

※ 使用する PC や OS のバージョンによっては必要ありません。不明でしたら講座当日のインストールでも構いません

<div style="height: 3em;"></div>

> ### UART とは
>
> PC と ESP32 との間の通信に使われるプロトコルです。通信は特定のビットレート（**Baud Rate: ボーレート**）で行われます。
> ESP32 にプログラムを書き込んだり、ESP32 からのデータをリアルタイムで表示(ArduinoIDE のシリアルモニタ機能)できます。

<div style="height: 3em;"></div>

### インストール

[https://www.silabs.com/developers/usb-to-uart-bridge-vcp-drivers?tab=downloads](https://www.silabs.com/developers/usb-to-uart-bridge-vcp-drivers?tab=downloads) からドライバをダウンロードします。

![](/images/0013_cp210x.jpg)

<div style="height: 3em;"></div>

![](/images/0014_cp210x.jpg)

ダウンロードしたファイルを実行してインストールします。

![](/images/0015_cp210x.jpg)

<div style="height: 3em;"></div>

![](/images/0016_cp210x.jpg)

<div style="height: 3em;"></div>

![](/images/0017_cp210x.jpg)

<div style="height: 5em;"></div>

### デバイスマネージャで確認

**Windows のスタートボタンを右クリック** し、 **デバイスマネージャ** をクリックして開きます

<div style="height: 3em;"></div>

![](/images/0018_cp210x.png)

<div style="height: 5em;"></div>

**ポート（COM と LPT）** をクリックして展開します

<div style="height: 3em;"></div>

![](/images/0019_cp210x.png)

