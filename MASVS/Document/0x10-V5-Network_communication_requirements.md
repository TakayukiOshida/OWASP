# V5: ネットワーク通信要件

## 制御目的

本章で記載された制御の目的は、モバイルアプリとリモートサービスエンドポイントの間でやりとりされた情報の機密性と完全性を確保することである。少なくとも、モバイルアプリは適切な設定のTLSプロトコルを用いるネットワーク通信のための暗号化されたチャネルを安全にセットアップしなければならない。レベル2では、SSLピンニングなどの追加の多層防御装置が記載されている。

## セキュリティ検証要件

| # | 説明 | L1 | L2 |
| --- | --- | --- | --- |
| **5.1** | TLSを用いてネットワーク上で機密データが暗号化されている。アプリを通してセキュアなチャネルが一貫して使用されている | ✓ | ✓ |
| **5.2** | モバイルオペレーティングシステムが推奨される標準をサポートしていない場合、TLS設定が現在のベストプラクティス、もしくは可能な限り近くに一致している | ✓ | ✓ |
| **5.3** | セキュアなチャネルが確立されたとき、アプリがリモートエンドポイントのX.509証明書を検証する。妥当なCAによって署名された証明書のみが受け入れられる | ✓ | ✓ |
| **5.4** | アプリが自身の証明書ストアを使用したり、エンドポイントの証明書や公開鍵をピンニングしたりする。そしてその後、信頼されたCAによって署名されていたとしても異なる証明書や鍵を提供したら、エンドポイントとのコネクションを確立しない |   | ✓ |
| **5.5** | アプリが登録やアカウント回復などの重要操作のためのセキュアでない通信チャネル(たとえば、EメールやSMS)を信頼しない |  | ✓ |
| **5.6** | アプリが接続ライブラリとセキュリティライブラリのみに依存している |  | ✓ |

## 参考文献

OWASP モバイルセキュリティテストガイドは、本セクションに記載されている要件を検証するための詳細な指示を提供する。

- Android - https://github.com/OWASP/owasp-mstg/blob/master/Document/0x05g-Testing-Network-Communication.md
- iOS - https://github.com/OWASP/owasp-mstg/blob/master/Document/0x06g-Testing-Network-Communication.md

詳細は以下参照：

- OWASP Mobile Top 10:  M3 - Insecure Communication(安全でない通信): https://www.owasp.org/index.php/Mobile_Top_10_2016-M3-Insecure_Communication
- CWE: https://cwe.mitre.org/data/definitions/319.html
- CWE: https://cwe.mitre.org/data/definitions/295.html