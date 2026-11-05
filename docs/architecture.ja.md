# アーキテクチャ

[概要](../README.ja.md) · [English](architecture.en.md) · [Português](architecture.pt-BR.md)

問い合わせの内容、確認状況、担当者、回答案の承認を分離する運用設計の資料です。

## 処理の流れ

```text
Inbound report → facts versus allegations → context review → owner assignment → draft → human approval
```

## 不変条件

1. 利用者の申告と独立して確認された事実を区別します。
2. 同じ連絡先を再案内する前に、過去の連絡履歴を確認します。
3. 担当者と確約が確認できない限り、支払日や解決結果を約束しません。
4. 公開例や技術ログに個人の案件情報を含めません。
5. 外部への送信には人による承認を必要とします。

## 実装の境界

この公開版には技術文書と合成サンプルのみを含みます。公開していないソースや運用データを、公開成果物の一部として扱わないでください。
