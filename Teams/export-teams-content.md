---
title: Microsoft Teams エクスポート API を使用してコンテンツをエクスポートする
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: vikramju
description: この記事では、Microsoft Teams エクスポート API を使用して Teams コンテンツをエクスポートする方法について説明します。
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f1bca4eb70bff07e809630e1b997f377064b5e0e
ms.sourcegitcommit: b4b2c7e79679cce6cf5f863ddf708e50164f9a9d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2021
ms.locfileid: "50861411"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a>Microsoft Teams エクスポート API を使用してコンテンツをエクスポートする

Teams エクスポート API を使用すると、Microsoft Teams から 1 対 1、グループ チャット、チャネル メッセージをエクスポートできます。 組織で Microsoft Teams メッセージをエクスポートする必要がある場合は、Teams エクスポート API を使用してメッセージを抽出できます。 *チャット メッセージは* 、チャネルまたはチャット内の個々の [チャット メッセージを](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) 表 [します](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta)。 チャット メッセージには、ルート チャット メッセージや、チャット メッセージの **replyToId** プロパティによって定義される返信スレッドの一部を使用できます。

これらのエクスポート API を使用する方法の例を次に示します。

- **例 1:** 組織内で Microsoft Teams を有効にし、プログラムを使用してすべての Microsoft Teams メッセージを日付にエクスポートする場合は、特定のユーザーまたはチームの日付範囲を渡します。
- **例 2:** 日付範囲を指定して、プログラムですべてのユーザーまたはチーム メッセージを毎日エクスポートする場合。 エクスポート API は、指定した日付範囲内に作成または更新されたメッセージをすべて取得できます。

## <a name="what-is-supported-by-the-teams-export-apis"></a>Teams エクスポート API でサポートされる機能

- **Teams メッセージの一括エクスポート:** Teams エクスポート API は、テナントあたり最大 200 RPS、アプリケーションでは 600 RPS をサポートします。これらの制限により、Teams メッセージを一括エクスポートできる必要があります。
- **アプリケーション コンテキスト**: Microsoft Graph を呼び出す場合、アプリは Microsoft ID プラットフォームからアクセス トークンを取得する必要があります。 アクセス トークンには、Microsoft Graph で利用できるリソースと API に対するアプリとアクセス許可に関する情報が含まれます。 アクセス トークンを取得するには、アプリを Microsoft ID プラットフォームに登録し、必要な Microsoft Graph リソースへのアクセスをユーザーまたは管理者が承認する必要があります。

    アプリと Microsoft ID プラットフォームを統合してトークンを取得する方法について既に理解している[](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps)場合は、Microsoft Graph 固有の情報とサンプルについては、「次の手順」セクションを参照してください。
- **ハイブリッド環境:** ハイブリッド環境 (オンプレミスの Exchange と Teams) でプロビジョニングされたユーザーから送信されたエクスポート API サポート メッセージ。 ハイブリッド環境用に構成されているユーザーから送信されたメッセージには、エクスポート API を使用してアクセスできます。
- **ユーザーが削除したメッセージ:** Teams クライアントからユーザーによって削除されたメッセージには、削除から最大 30 日後にエクスポート API を使用してアクセスできます。
- **メッセージの添付ファイル:** エクスポート API には、メッセージの一部として送信される添付ファイルへのリンクが含まれます。 エクスポート API を使用すると、メッセージに添付されているファイルを取得できます。
- **チャット メッセージのプロパティ:** Teams エクスポート API がここでサポートするプロパティの完全な一覧を参照 [してください](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties)。

## <a name="how-to-access-teams-export-apis"></a>Teams エクスポート API にアクセスする方法

- **例 1** は、フィルターなしでユーザーまたはチームのすべてのメッセージを取得する簡単なクエリです。

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/getallMessages
    ```
     ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/getallMessages
    ```

- **例 2** は、日付時刻フィルターと上位 50 件のメッセージを指定して、ユーザーまたはチームのすべてのメッセージを取得するサンプル クエリです。

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/getallMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
    ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/getallMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
>[!NOTE]
>API は、複数の結果が得られた場合に、次のページ リンクを含む応答を返します。 次の結果セットを取得するには、@odata.nextlink の URL で GET を呼び出します。 @odata.nextlink が存在しないか null の場合は、すべてのメッセージが取得されます。

## <a name="prerequisites-to-access-teams-export-apis"></a>Teams エクスポート API にアクセスするための前提条件 

- Teams エクスポート API は現在プレビュー中です。 API に必要なライセンスを持つユーザーと [テナントだけが](https://aka.ms/teams-changenotification-licenses) 利用できます。 今後、Microsoft は、API を通じてアクセスされるデータの量に基づいて、お客様またはお客様に追加料金の支払いを要求する場合があります。
- 機密データにアクセスする Microsoft Graph の Microsoft Teams API は、保護された API と見なされます。 エクスポート API を使用するには、アクセス許可と同意を超えた追加の検証が必要です。 これらの保護された API へのアクセスを要求するには、要求フォームに [入力します](https://aka.ms/teamsgraph/requestaccess)。
- アプリケーションのアクセス許可は、サインインしているユーザーが存在せずに実行されるアプリで使用されます。アプリケーションのアクセス許可は管理者しか同意することはできません。 次のアクセス許可が必要です。

    - *Chat.Read.All*: すべての 1 対 1 およびグループ チャット メッセージへのアクセスを有効にする 
    - *User.Read.All*: テナントのユーザーリストへのアクセスを有効にする 

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

>[!NOTE]
>chatMessage リソースの詳細については [、chatMessage リソースの種類に関する記事を参照](https://docs.microsoft.com/graph/api/resources/chatmessage) してください。
