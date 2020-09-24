anime-db
====

## Anime-dbについて
本リポジトリは、日本国内にて放送される深夜アニメ作品の放送日時を記録するデータベースです。

[うずらインフォ](https://uzurainfo.han-be.com/) 様によるアニメ情報のまとめが2020年夏期にて終了するとの告知を受け、今後のアニメ情報を網羅するために作成しました。

## リポジトリ構造について
- README.md
    - 本ドキュメント
- lists.json
    - JSONファイル一覧
- jsonディレクトリ
    - データベース本体を格納するディレクトリ
    - 各データベースはJSON形式にて作成
    - ファイル名は `YYYYQX.json` とする
        - YYYY - 西暦
        - QX   - クォータ
            - 1-3月  : Q1
            - 4-6月  : Q2
            - 7-9月  : Q3
            - 10-12月: Q4

## データ構造について
### JSON本体

| Key | Type | Description |
| --- | ---- | --- |
| data | Array[] | 作品を格納する配列。内容は[data構造](#data構造)を参照。 |

### data構造
| Key | Type | Description |
| --- | ---- | --- |
| title | String | 作品名 |
| url | Strinrg | 公式ウェブサイトURL |
| production | String | アニメーション制作会社 |
| onair | Array[] | 放送局情報を格納する配列。内容は[onair構造](#onair構造)を参照。 |

### onair構造
| Key | Type | Description |
| --- | ---- | --- |
| channel | String \| Array[] | チャンネル名称。系列局で一斉放送の場合は配列として記載する。 |
| dow | Integer | Day of Week。0を日曜、6を土曜とする `0～6` の整数。 |
| start_at | String | 放送開始時間。深夜24時以後は翌日0:00以後に繰り越して記載する。 | 
| start_date | String | 放送開始日時。深夜24時以後は翌日に繰り越して記載する。 |

## ライセンス
本リポジトリは CC0 1.0 (Creative Commons Zero v1.0 Universal)を採用しています。

## Contributing
- 番組情報の誤り等はIssuesにてご報告ください
- 追加等があれば、プルリクエストを送ってください