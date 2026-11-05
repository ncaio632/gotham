# モジュールと状態 — gotham

[英語完全版](architecture.en.md)の要約です。論理コンポーネントは単一アプリや手動運用で実現でき、モデル事業者は前提ではありません。役割仕様はバックグラウンド処理を起動しません。

| モジュール | 責務と禁止事項 |
| --- | --- |
| 受付 | 帰属付き申告と過去連絡を記録し、自動で事実認定しない。 |
| 証拠台帳 | 資料、審査、主張との関係、矛盾を保つ。反復を証明にしない。 |
| 担当調整 | 担当と確認済み約束を管理し、担当不明の約束をしない。 |
| 下書き | 参照付き文章と版を作り、承認・送信しない。 |
| 審査 | 正確な版を承認・差戻しし、承認本文を黙って編集しない。 |
| 監査 | 安全な遷移・理由コードを記録し、私的本文や個人情報を除く。 |

基本遷移は`intake → investigating → drafting → review_pending → approved`です。差戻しは`revision_required`、事実不足なら`investigating`、表現不足なら`drafting`へ戻します。承認後の変更は承認を失効させます。`approved`は下書き準備の完了で、送信・解決ではありません。調査中のまま待機でき、`sent`状態はありません。

文脈・主張・証拠・担当・約束の内容変更で`case_revision`、本文編集ではそれと`draft_revision`を増やします。審査判断や状態投影は別イベントとして記録し、内容版を変更しません。承認は両版を保存し、現状態との比較を原子的に行います。過去判断は将来の内部履歴に追記保存しますが、公開例には架空の現在状態のみを含めます。

[Schema](../contracts/case-review.schema.json)は元の例より厳格な内部提案で、チケットAPIではありません。コマンドを`recordReport/reviewEvidence/assignOwner/recordCommitment/saveDraft/reviewDraft`に制限し、全状態の上書きによる自己承認を許しません。

`intake`と`investigating`では`owner_role`と`draft`を省略できます。下書き・審査状態では両方が必須で、初期判断は`not_reviewed`です。

参照解決、証拠と主張の対応、作者と審査役の分離、版比較は意味検証です。参照があるだけで文章の忠実さは証明できません。`confirmed`の約束には権限ある担当の同意を示す審査済み証拠が必要です。デモの`due_text`は合意の原文を保持し、期限自動化の暦・時間帯は未定です。

エラー例は`CONTEXT_INCOMPLETE`、`REFERENCE_MISSING`、`EVIDENCE_UNREVIEWED`、`COMMITMENT_UNCONFIRMED`、`SELF_REVIEW`、`STALE_REVIEW`です。競合時は再読込し、キャッシュから承認を復元しません。送信アダプターは対象外です。


[Engineering index](index.ja.md)
