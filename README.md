# bicycle-study

[過去の発表一覧]](https://github.com/orgs/bicycle-study-group/projects/1/views/1?groupedBy%5BcolumnId%5D=Milestone&sortedBy%5Bdirection%5D=desc&sortedBy%5BcolumnId%5D=Title)

## 🚲 Bicycle勉強会とは

![Bicycle勉強会概要](./assets/about.png)

* [Bicycle式勉強会 \- Speaker Deck](https://speakerdeck.com/tpircs/bicycleshi-mian-qiang-hui)
* [「Bicycle式勉強会」を組織に取り込んだら心理的安全性向上にとても役立ちそうだと感じた話\(前編\)｜ykmfc｜note](https://note.com/ykmfc/n/ne3ec411a56c6)

## 📝 運営概要

- **Slack**: メインのコミュニケーション基盤
- **Zoom**: 発表用
- **GitHub**: 発表資産の管理
- **Google Spreadsheet**: スケジュール管理と各種スクリプト実行基盤

![](./assets/services.dio.png)

### 定期投稿

勉強会が開催される日にBotからSlackへ投稿が行われる。スケジュール管理等も基本はBotに任せれば大丈夫(なはず)。 

#### 参加表明

![](./assets/bot_attendee.png)

* **火曜日 09:00頃**に投稿される
* 勉強会の参加者数を把握するための投稿
  * 勉強会を開催するかどうかの明確な指標は無いですが、今までの傾向だと発表者以外に2,3人集まれば開催しちゃう感じ

#### スケジュール更新

![](./assets/bot_done.png)

* **火曜日 19:00頃**に投稿される
* 勉強会が開催されたかを確認する投稿
* 回答に応じてスケジュールを組みなおしてくれる

## 各役割の作業

### 🧑‍🏫 発表者

1. 発表資料を作成する
2. Zoomで発表する
3. 以下のリンクから、発表概要・発表資料を記載したIssueを立てる
   - [Create an issue from template](https://github.com/bicycle-study-group/bicycle-study/issues/new?assignees=&labels=presentation&template=----.md&title=%5BYYYY-MM-DD%5D+Summary)

### 👩‍💻 参加者
1. Slack、Zoom、GitHubでやんややんやする

### 👷‍♀️ 運営者
(明確に運営者という役割がある訳ではないので誰でも)

#### スケジュール管理
* Google Spreadsheetの **Schedule** シートで発表スケジュールを管理する
  * Google SpreadsheetにはSlackのヘッダからアクセスできる
* スケジュール管理はスクリプト化されており、必要な情報を編集してSlack上で `/update-schedule` コマンドを実行すると更新される
* 祝日・休日や、年末年始の休暇等、勉強会が開催されない日がある場合、Google Spreadsheetの **excluded_date**シート に `YYYY/MM/DD` 形式で追加する。  
  * **excluded_date** の情報を使って今後のスケジュールが生成されるため、過去の日付の情報は削除しても良い。

#### 参加者を管理する

新たな参加者を追加したい場合は、以下の作業を行う。

1. Slackワークスペースに参加者を招待する
2. GitHub [study-member](https://github.com/orgs/bicycle-study-group/teams/study-member)グループに参加者を招待する
3. Google Spreadsheetの**Schedule**シートメンバー一覧に参加者を追加する

参加者を除外する場合は、逆の操作をする。  
基本的にはGoogle Spreadsheetから名前を削除し、スケジュールの再生成をするだけで良いはず。
