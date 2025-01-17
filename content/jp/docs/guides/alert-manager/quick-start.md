---
title: "Quick Start"
linkTitle: "Quick Start"
weight: 1
date: 2022-06-07
description: >
    **アラートマネージャー**サービスを素早く使用するための過程をご紹介します。
---

## アラートを作成する

アラートは、次の2つの方法で作成できます。

- -クラウドフォレコンソールでアラートを手動作成
- **外部モニタリングサービス連携**を利用したアラート自動作成

### コンソールでアラートを手動作成する

(1) [アラートマネージャー > アラート]ページへ移動して[作成]ボタンをクリックします。

![create-alert-step-1](/jp/docs/guides/alert-manager/quick-start-img/create-alert-step-1.png)

(2) [アラート作成]のモダールウィンドウが表示されたら、入力フォームを作成します。

![create-alert-step-2](/jp/docs/guides/alert-manager/quick-start-img/create-alert-step-2.png)

(2-1) [アラートタイトル]を入力して[緊急度]を選択します。

(2-2) アラートが発生するプロジェクトを指定します。

(2-3) 追加説明が必要な場合は、[説明]を作成します。

(3) [確認]ボタンをクリックして、アラート作成を完了します。

### 外部モニタリングサービスに接続してアラートを受信する

外部モニタリングサービスに接続すると、当該サービスで発生するイベントのメッセージがアラートとして自動的に作成されます。
<br>
外部モニタリングで発生したアラートを受信するためには、**ウェブフック作成**と **連携設定**をする必要があります。

{{<alert>}}
**ウェブフック作成**は、クラウドフォレのコンソールで実行されますが、**連携設定**は、外部モニタリングサービスを提供するクラウドサービスのコンソールで直接設定しなければなりません。

外部モニタリングサービスとの連携方法は、[こちら](/jp/docs/guides/plugins/alert-manager-webhook/)をご参考にしてください｡
{{</alert>}}

<br>





#### ウェブフックを作成する

外部モニタリングサービスで発生するイベントメッセージを受信するためには、ウェブフックを作成しなければなりません。
<br>
ウェブフックは、プロジェクト詳細ページで作成できます。


(1) プロジェクト詳細ページの[アラート]タブに移動して、[ウェブフック]タブを選択します。

![create-webhook-step-1](/jp/docs/guides/alert-manager/quick-start-img/create-webhook-step-1,2.png)

(2) [追加]ボタンをクリックします。

(3) [ウェブフック追加]モダールウィンドウで名前を作成して、連携する外部モニタリングサービスのプラグインを選択します。

![create-webhook-step-3](/jp/docs/guides/alert-manager/quick-start-img/create-webhook-step-3.png)

(4) [確認]ボタンをクリックして設定を完了します。


## エスカレーションポリシーを設定する

ウェブフックを通じて受信したアラートがプロジェクトメンバーに通知として送信されるのかは、エスカレーションポリシーによって決定されます。 

(1) プロジェクト詳細ページで[アラート]タブへ移動して、[設定]タブを選択します。

![create-escalation-policy-step-1](/jp/docs/guides/alert-manager/quick-start-img/create-escalation-policy-step-1,2.png)

(2) [エスカレーションポリシー]ゾーンで[変更]ボタンをクリックします。

![create-escalation-policy-step-2](/jp/docs/guides/alert-manager/quick-start-img/create-escalation-policy-step-1,2.png)
{{<alert>}}
グローバルに設定されたエスカレーションポリシーがある場合は、プロジェクトのアラートの初回有効時に当該ポリシーが自動的に割り当てられます。
{{</alert>}}

(3) [新しいポリシー作成]タブを選択して、エスカレーションポリシーを作成するための設定を入力します。

![create-escalation-policy-step-4](/jp/docs/guides/alert-manager/quick-start-img/create-escalation-policy-step-4.png)

| ポリシー                             | 説明                                                                                                  |
|--------------------------------|---------------------------------------------------------------------------------------------------|
| 修了条件(状態)                      | 発生したアラートが中止される条件を定義します。                                                                          |
| スコープ                             | エスカレーションポリシーを使用できる範囲を意味します。グローバルの場合はドメイン内のすべてのプロジェクトで使用でき、プロジェクトの場合は指定されたプロジェクト内でのみ使用できます。  |
| エスカレーションルール                      | レベルLV1～LV5まで追加可能です。<Br/> 設定されたレベルに属する通知チャンネルにアラートを送信して、2段階以上からは段階間のタームを分単位で付与できます。|
| 繰り返し回数                          | アラート通知を繰り返す回数を定義します。最大9回まで繰り返しが可能です。                                                    |
| プロジェクト(エスカレーションルールページで作成する場合) | スコアがプロジェクトの場合は、対象となるプロジェクトを表します。                                                                  |

(4) 設定がすべて完了したら、[確認]ボタンをクリックしてエスカレーションポリシーを作成します。






## 通知を設定する

プロジェクト詳細ページの[通知]タブでは、**通知チャンネル作成と通知チャンネル有効化の可否**を管理できます。
<br>
**通知チャンネル**は、通知送信式やレベルなど体系的な受信者ゾーンを表す単位です。エスカレーションルールで設定したレベルに合わせて送信するようサポートします。
<br>
<br>
(1) プロジェクト詳細ページで[通知]タブを選択後、希望する通知チャンネルの[チャンネル追加]ボタンをクリックします。

![notification-step-1](/jp/docs/guides/alert-manager/quick-start-img/notification-step-1,2.png)

(2) 通知作成ページで通知チャンネルを作成するための設定を入力します。

(2-1) チャンネル名や通知レベルなど、作成したい通知チャンネルに必要な基本情報を入力します。[チャンネル名]と[通知レベル]が基本設定フィールドで、それ以外はチャンネルによって入力情報が異なります。

![notification-step-3-1](/jp/docs/guides/alert-manager/quick-start-img/notification-step-3-1.png)

{{<alert>}}
**通知レベル**は、エスカレーションポリシーのルール設定と関連しています。エスカレーションポリシーで指定された通知レベルを基準に、当該レベルに属する通知チャンネルにアラートを送信します。
{{</alert>}}

(2-2) スケジュールを設定して、特定時間にのみ通知を受信するよう設定できます。

![notification-step-3-2](/jp/docs/guides/alert-manager/quick-start-img/notification-step-3-2.png)

(2-3) 通知は、アラート発生時または予想通知基準に達すると受信できます。[トピック]では、どのような場合に通知を受信するかを設定します。

![notification-step-3-3](/jp/docs/guides/alert-manager/quick-start-img/notification-step-3-3.png)

(3) [保存]ボタンをクリックすると、通知チャンネルの作成が完了します。

(4) 作成が完了した通知チャンネルは、[通知]タブの下で確認できます。

![notification-step-5](/jp/docs/guides/alert-manager/quick-start-img/notification-step-5.png)

画面左上のトグルボタンを利用すると、当該通知チャンネルの有効・無効状態を操作できます。エスカレーションポリシーで設定したレベルがあっても、通知チャンネルが無効状態の場合は通知は発生しません。
