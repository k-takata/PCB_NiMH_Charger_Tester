# NiMH充電器&測定器 (NiMH Charger & Tester)

## 概要

ニッケル水素電池を充電したり、内部抵抗や容量を測定します。

参考文献\[1\]や\[2\]の記事を参考に設計した回路となっています。


## 使用したソフトウェア

KiCad 9.0


## 回路図

[![schema](https://raw.githubusercontent.com/k-takata/PCB_NiMH_Charger_Tester/master/images/schema.png)](https://raw.githubusercontent.com/k-takata/PCB_NiMH_Charger_Tester/master/images/schema.pdf)


## 基板パターン図

![PCB pattern](https://raw.githubusercontent.com/k-takata/PCB_NiMH_Charger_Tester/master/images/pcb-pattern.png)


## 部品表

| Reference                 |個数|値    | 説明 |
|---------------------------|----|------|------|
|BT1                        |   1|      |[単3電池ボックス](https://akizukidenshi.com/catalog/g/g100308/)|
|BT2                        |   1|      |[単4電池ボックス](https://akizukidenshi.com/catalog/g/g102670/)|
|C1, C5, C6, C7, C8, C9, C10|   7|0.1μF|[積層セラミックコンデンサー 2.5mm](https://akizukidenshi.com/catalog/g/g113582/)|
|C2                         |   1|100μF|電解コンデンサー φ6.3|
|C3 (\*1)                   |   1| 10μF|積層セラミックコンデンサー 3225M|
|C4 (\*1)                   |   1| 10μF|[積層セラミックコンデンサー 5mm](https://akizukidenshi.com/catalog/g/g103095/)|
|D1, D2                     |   2|1S2076A|小信号用汎用ダイオード|
|D3                         |   1|[OS5REA51A5A](https://akizukidenshi.com/catalog/g/g114209/)|赤色LED (ミルキーレンズ)|
|D4                         |   1|[OSG5DA51A5A](https://akizukidenshi.com/catalog/g/g114207/)|緑色LED (ミルキーレンズ)|
|D5                         |   1|[TS260S](https://akizukidenshi.com/catalog/g/g115166/)|表面実装用ショットキーバリアダイオードブリッジ 60V 2A|
|F1 (\*2)                   |   1|  0.5A|[ポリヒューズ](https://akizukidenshi.com/catalog/g/g115300/)、表面実装|
|F2 (\*2)                   |   1|  1.1A|[ポリヒューズ](https://akizukidenshi.com/catalog/g/g100507/)|
|J1 (\*3)                   |   1|      |[USB Type-Cコネクター 電源供給用](https://akizukidenshi.com/catalog/g/g116438/)|
|J2 (\*3)                   |   1|      |[USB Type-Cコネクター](https://akizukidenshi.com/catalog/g/g114356/)|
|J3                         |   1|      |ピンヘッダー 1x3、UPDI用|
|J4                         |   1|      |[ロープロファイルピンソケット](https://akizukidenshi.com/catalog/g/g100661/) 1x4、OLED接続用|
|J5                         |   1|      |ピンヘッダー 1x6、シリアル通信用|
|Q1                         |   1|[DTC114EL](https://akizukidenshi.com/catalog/g/g112467/)|抵抗入りNPNトランジスター|
|Q2                         |   1|[DTA114EL](https://akizukidenshi.com/catalog/g/g112464/)|抵抗入りPNPトランジスター|
|Q3                         |   1|[MTB060P06I3](https://akizukidenshi.com/catalog/g/g116095/)|PchパワーMOSFET 60V 16.7A|
|Q4                         |   1|[MTA100N10KRI3](https://akizukidenshi.com/catalog/g/g115847/)|NchパワーMOSFET 100V 10A|
|R1, R2                     |   2|5.1kΩ|1/6Wサイズ|
|R3, R4, R16, R19           |   4| 10kΩ|1/4Wサイズ|
|R5, R6, R7                 |   3|  1kΩ|1/4Wサイズ|
|R8, R9 (\*4)               |   2| 10kΩ|1/4Wサイズ、LED電流制限用 (4.7kΩ～22kΩ)|
|R10, R11                   |   2|4.7kΩ|1/4Wサイズ|
|R12, R15                   |   2| 47kΩ|1/4Wサイズ|
|R13, R14                   |   2| 100Ω|1/4Wサイズ|
|R17                        |   1|  10Ω|[酸化金属皮膜抵抗 3W 10Ω](https://akizukidenshi.com/catalog/g/g111015/)|
|R18                        |   1|   1Ω|[酸化金属皮膜抵抗 3W 1Ω](https://akizukidenshi.com/catalog/g/g111013/)|
|SW1                        |   1|[DTS-63-N-V-RED](https://akizukidenshi.com/catalog/g/g103646/)|タクトスイッチ (赤色)|
|SW2                        |   1|[DTS-63-N-V-WHT](https://akizukidenshi.com/catalog/g/g103648/)|タクトスイッチ (白色)|
|SW3                        |   1|[DTS-63-N-V-BLK](https://akizukidenshi.com/catalog/g/g103647/)|タクトスイッチ (黒色)|
|U1                         |   1|[AVR64DD28-I/SP](https://akizukidenshi.com/catalog/g/g118314/)|AVRマイコン|
|U2                         |   1|[NJU7043](https://akizukidenshi.com/catalog/g/g106840/)|2回路入入出力フルスイングオペアンプ|
|U3, U5                     |   1|[MCP9700BT-E/TT](https://akizukidenshi.com/catalog/g/g130948/)|温度センサーIC|
|U4                         |   1|[TL431](https://akizukidenshi.com/catalog/g/g112018/)|シャントレギュレーター 2.495V|

注:
* (\*1) C3, C4はどちらかを選択します。基板上にはC3の表示のみあります。
* (\*2) F1, F2はどちらかを選択します。基板上にはF1の表示のみあります。
* (\*3) J1, J2は部品の入手状況や実装難易度を考慮してどちらかを選択します。J1を選択した場合は、基板から少しはみ出す状態で取り付けることになります。J2を選択した場合は、J1用のランドとコネクター本体がショートしないようにポリイミドテープ等で絶縁する必要があります。
* (\*4) LEDの明るさを変えたい場合は適宜値を変更してください。


## 作成

T.B.D.


## 使用方法

T.B.D.


## 完成品

<!--
[![完成品](https://raw.githubusercontent.com/k-takata/PCB_NiMH_Charger_Tester/master/images/usb-c-adaptor-thumb.jpg)](https://raw.githubusercontent.com/k-takata/PCB_NiMH_Charger_Tester/master/images/nimh-charger-tester.jpg)
-->


## 参考文献

1. [トランジスタ技術SPECIAL No.135 Liイオン/鉛/NiMH蓄電池の充電&電源技術](https://shop.cqpub.co.jp/hanbai/books/46/46751.html) 「第4章　研究！ ニッケル水素蓄電池の耐久テスト」
2. [トランジスタ技術SPECIAL No.170 教科書付き 小型バッテリ電源回路](https://www.cqpub.co.jp/trs/trsp170.htm) 「Appendix 1　充放電回数の限界…サイクル耐久特性の実測」
3. [電池応用ハンドブック](https://www.cqpub.co.jp/hanbai/books/34/34461.htm)


## License

CC0
