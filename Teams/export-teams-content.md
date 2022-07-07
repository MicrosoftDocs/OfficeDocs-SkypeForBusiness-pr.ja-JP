---
title: Microsoft Teams Export API を使用してコンテンツをエクスポートする
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: vikramju
description: この記事では、Microsoft Teams Export API を使用して Teams コンテンツをエクスポートする方法について説明します。
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b508b368629ce716a1269380eb1fffe2137620c8
ms.sourcegitcommit: 90f03a841f8ca33092dce65c543357c7c2f7b82a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66647649"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a>Microsoft Teams Export API を使用してコンテンツをエクスポートする

Teams Export API を使用すると、Microsoft Teams から 1:1、グループ チャット、会議チャット、チャネル メッセージをエクスポートできます。 組織で Microsoft Teams メッセージをエクスポートする必要がある場合は、Teams Export API を使用してメッセージを抽出できます。 *チャット メッセージ* は、 [チャネル](/graph/api/resources/channel) またはチャット内の個々のチャット メッセージを表 [します](/graph/api/resources/chat)。 チャット メッセージには、ルート チャット メッセージまたはチャット メッセージの **replyToId** プロパティによって定義される応答スレッドの一部を指定できます。

これらのエクスポート API を使用する方法の例を次に示します。

- **例 1**: 組織内で Microsoft Teams を有効にしていて、特定のユーザーまたはチームの日付範囲を渡すことによって、すべての Microsoft Teams メッセージをプログラムで日付にエクスポートする場合。
- **例 2**: 日付範囲を指定して、すべてのユーザーメッセージまたはチーム メッセージを毎日プログラムでエクスポートする場合。 エクスポート API は、指定された日付範囲の間に作成または更新されたすべてのメッセージを取得できます。

## <a name="what-is-supported-by-the-teams-export-apis"></a>Teams Export API では何がサポートされていますか?

- **Teams メッセージの一括エクスポート:** Teams Export API では、テナントあたり最大 200 個の RPS とアプリケーション用の 600 個の RPS がサポートされます。これらの制限により、Teams メッセージを一括エクスポートできます。
- **アプリケーション コンテキスト**: Microsoft Graph を呼び出すには、アプリがMicrosoft ID プラットフォームからアクセス トークンを取得する必要があります。 アクセス トークンには、アプリに関する情報と、Microsoft Graph で使用できるリソースと API に対するアクセス許可が含まれています。 アクセス トークンを取得するには、アプリをMicrosoft ID プラットフォームに登録し、ユーザーまたは管理者が必要な Microsoft Graph リソースへのアクセスを承認する必要があります。

    トークンを取得するためのMicrosoft ID プラットフォームとのアプリの統合について既に理解している場合は、Microsoft Graph に固有の情報とサンプルについては、「[次の手順」](/graph/auth/auth-concepts#next-steps)セクションを参照してください。
- **ハイブリッド環境:** エクスポート API は、ハイブリッド環境 (オンプレミスの Exchange と Teams) でプロビジョニングされたユーザーによって送信されるメッセージをサポートします。 ハイブリッド環境用に構成されているユーザーによって送信されたメッセージには、エクスポート API を使用してアクセスできます。
- **ユーザーが削除したメッセージ:** Teams クライアントからユーザーによって削除されたメッセージには、削除時から最大 21 日間のエクスポート API を使用してアクセスできます。
- **メッセージの添付ファイル:** エクスポート API には、メッセージの一部として送信される添付ファイルへのリンクが含まれます。 エクスポート API を使用すると、メッセージに添付されているファイルを取得できます。
- **反応：** エクスポート API は、Teams メッセージでユーザーによって無効にされた反応をサポートします。 現在サポートされている反応は、心、腹立たしい、悲しい、驚き、笑いなどです。
- **チャット メッセージのプロパティ:** ここでは、Teams Export API でサポートされているプロパティの完全な一覧を参照 [してください](/graph/api/resources/chatmessage#properties)。


## <a name="how-to-access-teams-export-apis"></a>Teams エクスポート API にアクセスする方法

- **例 1** は、フィルターなしでユーザーまたはチームのすべてのメッセージを取得する簡単なクエリです。

  ```HTTP
  GET https://graph.microsoft.com/v1.0/users/{id}/chats/getAllMessages
  ```

  ```HTTP
  GET https://graph.microsoft.com/v1.0/teams/{id}/channels/getAllMessages
  ```

- **例 2** は、日付のフィルターと上位 50 個のメッセージを指定して、ユーザーまたはチームのすべてのメッセージを取得するサンプル クエリです。

  ```HTTP
  GET https://graph.microsoft.com/v1.0/users/{id}/chats/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
  ```

  ```HTTP
  GET https://graph.microsoft.com/v1.0/teams/{id}/channels/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
  ```

> [!NOTE]
> API は、複数の結果が返された場合に、次のページ リンクを含む応答を返します。 次の結果セットを取得するには、@odata.nextlink の URL で GET を呼び出すだけです。 @odata.nextlink が存在しない場合、または null の場合、すべてのメッセージが取得されます。

## <a name="prerequisites-to-access-teams-export-apis"></a>Teams Export API にアクセスするための前提条件

- 機密データにアクセスする Microsoft Graph の Microsoft Teams API は、保護された API と見なされます。 エクスポート API を使用するには、アクセス許可と同意を超えた追加の検証が必要です。 これらの保護された API へのアクセスを要求するには、 [要求フォームに入力します](https://aka.ms/teamsgraph/requestaccess)。
- アプリケーションのアクセス許可は、サインインしているユーザーが存在せずに実行されるアプリによって使用されます。アプリケーションのアクセス許可は管理者のみが同意できます。 次のアクセス許可が必要です。
  - *Chat.Read.All*: すべての 1:1、グループ チャット、会議チャット メッセージへのアクセスを有効にします
  - *ChannelMessage.Read.All*: すべてのチャネル メッセージへのアクセスを有効にします
  - *User.Read.All*: テナントのユーザーの一覧へのアクセスを有効にします

## <a name="license-requirements-for-teams-export-apis"></a>Teams エクスポート API のライセンス要件

Export API は、モデル クエリ パラメーターを使用して、セキュリティとコンプライアンス (S+C) と一般的な使用シナリオをサポートします。 S+ C シナリオ (モデル A) にはシードされた容量が含まれており、E5 サブスクリプションと一般的な使用シナリオ (モデル B) はすべてのサブスクリプションで使用でき、使用のみ可能です。 シードされた容量と消費料金の詳細については、「 [Microsoft Graph Teams API のライセンスと支払いの要件」を](/graph/teams-licenses)参照してください。

### <a name="scmodel-a-scenarios"></a>S+ C/Model A のシナリオ

セキュリティやコンプライアンス機能を実行するアプリケーションに制限されているユーザーは、この機能を使用し、シードされた容量を受け取るために特定の E5 ライセンスを持っている必要があります。 シードされた容量はユーザーごとに計算され、テナント レベルで集計されます。 シードされた容量を超えて使用する場合、アプリ所有者は API の使用に対して課金されます。 モデル A は、E5 ライセンスが割り当てられているユーザーからのみメッセージにアクセスできます。

### <a name="general-usagemodel-b-scenarios"></a>一般的な使用法/モデル B のシナリオ

S+C 以外のすべての関連シナリオで使用でき、ライセンス要件やシード容量はありません。 従量課金制のメーターが利用可能になると、アプリの所有者はすべての毎月の API 呼び出しに対して課金されます。

### <a name="evaluation-mode-default"></a>評価モード (既定)

モデル宣言を使用しない場合は、評価目的で各要求アプリケーションごとに使用が制限された API にアクセスできます。

## <a name="json-representation"></a>JSON 表現

次の例は、リソースの JSON 表現です。

名前空間: microsoft.graph

```JSON
{
"id": "string (identifier)",
"replyToId": "string (identifier)",
"from": {"@odata.type": "microsoft.graph.identitySet"},
"etag": "string",
"messageType": "string",
"createdDateTime": "string (timestamp)",
"lastModifiedDateTime": "string (timestamp)",
"deletedDateTime": "string (timestamp)",
"subject": "string",
"from": {
                "application": null,
                "device": null,
                "conversation": null,
                "user": {

                    "id": \[{"@odata.type": "microsoft.graph.user"}\],
                    "displayName": "User Name",

                    "userIdentityType": "aadUser"                }
            },
"body": {"@odata.type": "microsoft.graph.itemBody"},
"summary": "string",

"chatId": \[{"@odata.type": "microsoft.graph.chat"}\]

"attachments": \[{"@odata.type": "microsoft.graph.chatMessageAttachment"}\],
"mentions": \[{"@odata.type": "microsoft.graph.chatMessageMention"}\],
"importance": "string",
"locale": "string",
}
```

> [!NOTE]
> chatMessage リソースの詳細については、 [chatMessage リソースの種類](/graph/api/resources/chatmessage) に関する記事を参照してください。
