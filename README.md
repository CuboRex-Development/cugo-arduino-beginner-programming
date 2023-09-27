# クローラロボット開発プラットフォームクイックスタートガイド
## 1. はじめに
本リポジトリはクローラロボット開発プラットフォームを利用するためのサンプルコードです。
クローラロボット開発プラットフォームを使ってラジコン走行や自動走行を実現できます。</br>
![V4メイン](https://github.com/CuboRex-Development/cugo-beginner-programming/assets/22425319/e1b76ade-498c-49db-9c62-2013c0201fa4)

## 2. 準備
クローラロボット開発プラットフォームの利用開始までの手順を説明します。

### 2-1. Arduino IDEのインストール
1. 公式ページ( https://www.arduino.cc/en/software )へ移動
2. DOWNLOAD OPTIONSからご自身のOSのバージョンを選択
3. JUST DOWNLOADかCONTRIBUTE & DOWNLOADを選択
4. ダウンロードされたらファイルを実行して指示に従いインストール
### 2-2. 学習用ソースコードダウンロード→PICO版へ変更
1. ここをクリックしてダウンロード
![image](https://github.com/CuboRex-Development/cugo-beginner-programming/assets/22425319/ea21aa32-1b2e-4d48-852d-678ad300485b)

2. ダウンロードしたファイルを解凍
3. CugoBeginnerProgramming.inoをダブルクリックし、ArduinoIDEを起動

### 2-3. Rasberry Pi Picoの初期設定
Arduino IDE でRaspberryPiPicoに書き込む場合、
Arduino IDE バージョン2系（最新版）の場合

Arduino IDE バージョン1.8.19（レガシー）の場合

### 2-4. Rasberry Pi Picoへの書き込み

1. CugoBeginnerProgramming.inoがArduinoIDEで開かれていることを確認
//★ボードマネージャーの記載https://github.com/earlephilhower/arduino-pico/releases/download/global/package_rp2040_index.json,https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/arduino/package_m5stack_index.json
2. USBケーブルでパソコンとAruduinoを接続
3. ツール ＞ ボード から"Rasberry Pi Pico"を選択　
4. ツール ＞ ポート からRasberry Pi Picoのポートを選択
5. 矢印ボタン " → "を選択し、マイコンボードへ書き込むを実行
6. ボードへの書き込みが完了しましたの記載があれば書き込み完了
## 3. 使用方法
クローラロボット開発プラットフォームでは2つのモードが利用できます
### 3-1. ラジコンモードの利用
ラジコンモードはCugoBeginnerProgramming.inoを書き込み後、付属のコントローラの左スティックを左側に倒すことでラジコンモードが開始します。 <br>
![controller](https://user-images.githubusercontent.com/22425319/208835611-c366764d-4b30-477a-aac8-c848712c4710.png)

ラジコンモードでの操作方法は<br>
- 左スティックの上下操作が左クローラーの前進後進移動
- 右スティックの上下操作が右クローラーの前進後進移動　<br>

になります<br>
![radiocontrol](https://user-images.githubusercontent.com/22425319/208835778-1dd170dc-3de1-4dce-b7ee-83f2c1e0838d.png)
### 3-2. 自動走行モードの利用
CugoBeginnerProgramming内の一番下にあるCMD_EXECUTEの関数内をプログラミングすることで自動走行が可能です。
### コマンド 一覧
CMD_EXECUTE内では以下のコマンドの実行が可能です。<br>

- 基本コマンド 一覧<br>

|  コマンド名  |  動作  |　備考 |
| ---- | ---- | ---- |
|  matsu(1000)  |  1000ミリ秒待機  | 入力した()内の数字ミリ秒だけ待機する。1000ミリ秒＝1秒。 |
|  susumu(1.0)  |  前に1m進む  | ()内の数字を変更することで進む距離が変更できる |
|  modoru(1.0)  |  後ろに1m進む  | ()内の数字を変更することで進む距離が変更できる |
|  migimawari45()  |  右回りに45度回転  |      |
|  hidarimawari45()  |  左回りに45度回転  |      |
|  migimawari90()  |  右回りに90度回転  |      |
|  hidarimawari90()  |  左回りに90度回転  |      |
|  migimawari180()  |  右回りに180度回転  |      |
|  hidarimawari180()  |  左回りに180度回転  |      |
   
- 応用コマンド 一覧<br> 

|  コマンド名  |  動作  |　備考 |
| ---- | ---- | ---- |
| susumu(1.0,90) | 上限速度90rpmで1.0m前に進む  | ()内に移動距離と上限速度を設定。上限速度は最大180rpmで距離が短いと上限速度に到達しない場合も　|
| sagaru(1.0,90) | 上限速度90rpmで1.0m後ろに進む | ()内の設定はsusumu(1.0,90)と同様 |
| migimawari45(90) | 上限速度90rpmで45度右に回転する | ()内に上限速度を設定。上限速度は最大180rpmで距離が短いと上限速度に到達しない場合も　|
| migimawari90(90) | 上限速度90rpmで90度右に回転する | ()内の設定はmigimawari45(90)と同様 |
| migimawari180(90) | 上限速度90rpmで180度右に回転する  | ()内の設定はmigimawari45(90)と同様 |
| hidarimawari45(90) | 上限速度90rpmで45度左に回転する | ()内の設定はmigimawari45(90)と同様 |
| hidarimawari90(90) | 上限速度90rpmで90度左に回転する | ()内の設定はmigimawari45(90)と同様 |
| hidarimawari180(90) | 上限速度90rpmで180度左に回転する | ()内の設定はmigimawari45(90)と同様 |
| turn_clockwise(60,90) | 上限速度90rpmで60度右に回転する | ()内に回転角度と上限速度を設定。上限速度は最大180rpmで距離が短いと上限速度に到達しない場合も |
| turn_counter_clockwise(60,90) | 上限速度90rpmで60度左に回転する | ()内の設定はturn_clockwise(60,90)と同様 |
## 4. サンプルコード解説
### 4-1. サンプルコードの実行
1. ファイル内のプログラミングの一番下にある下のコードを確認してください。
- <details>
  <summary>コードを確認する場合はこちらをクリック</summary>
  
  ```c
  void CMD_EXECUTE()
  {
  cmd_manager();  // おまじない
  // ここから↓を改造していこう！

  susumu(1.0);
  matsu(1000); 
  
  migimawari90();
  matsu(1000); 
  
  susumu(1.0);
  matsu(1000); 
  
  migimawari90();
  matsu(1000); 
  
  susumu(1.0);
  matsu(1000); 
  
  migimawari90();
  matsu(1000);
  
  susumu(1.0);
  matsu(1000); 
  
  migimawari90();
  matsu(1000);  
  // ここから↑を改造していこう！
  cmd_end(motor_controllers);      // おまじない
  }
  ```
</details>

2. コマンドの説明 <br>
こちらのコマンドを実行するとクローラロボットが正方形に移動します。


### 4-2. サンプルコードの変更
#### 4-2-1. 長方形を描くには
- 問題：クローラロボットが長方形を描く方法を考えましょう。
  - ヒント：susumu() のコマンドのカッコ()の中は進む距離を表しています。
  - いろいろ試して確認してみましょう正解は詳細例に記載しています。

- <details>
  <summary>回答はこちらをクリック</summary>
  回答例はこちら<br>

   ```c
  void CMD_EXECUTE()
  {
  cmd_manager();  // おまじない
  // ここから↓を改造していこう！

  susumu(0.5); // ★デモプログラミングからの変更箇所
  matsu(1000); 
  
  migimawari90();
  matsu(1000); 
  
  susumu(1.0);
  matsu(1000); 
  
  migimawari90();
  matsu(1000); 
  
  susumu(0.5); // ★デモプログラミングからの変更箇所
  matsu(1000); 
  
  migimawari90();
  matsu(1000);
  
  susumu(1.0);
  matsu(1000); 
  
  migimawari90();
  matsu(1000);  

  // ここから↑を改造していこう！
  cmd_end(motor_controllers);      // おまじない
  }
  ```
</details>

#### 4-2-2. 速度を変えるには
- 問題：クローラロボットが速度を変えて進む方法を考えましょう。
  - ヒント：susumu() の応用コマンドのカッコ()の中は進む距離と上限速度を表しています。
  - いろいろ試して確認してみましょう正解は詳細例に記載しています。

- <details>
  <summary>回答はこちらをクリック</summary>
  susumuコマンドの中を変更して、向かい合う辺は同じ距離を進むように変更しよう<br>

   ```c
  void CMD_EXECUTE()
  {
  cmd_manager();  // おまじない
  // ここから↓を改造していこう！

  susumu(1.5,60); // ★デモプログラミングからの変更箇所
  matsu(1000); 
  
  migimawari90();
  matsu(1000); 
  
  susumu(1.0,120);// ★デモプログラミングからの変更箇所
  matsu(1000); 
  
  migimawari90();
  matsu(1000); 
  
  susumu(1.5,40); // ★デモプログラミングからの変更箇所
  matsu(1000); 
  
  migimawari90();
  matsu(1000);
  
  susumu(1.0,120);// ★デモプログラミングからの変更箇所
  matsu(1000); 
  
  migimawari90();
  matsu(1000);  
  
  // ここから↑を改造していこう！
  cmd_end(motor_controllers);      // おまじない
  }
  ```
</details>

## 5. お問い合わせ先
- 疑問点、不明点がある場合は issue を立ててください。
  - https://github.com/CuboRex-Development/cugo-arduino-beginner-programming/issues
