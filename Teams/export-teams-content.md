---
title: Microsoft Teams Export API を使用してコンテンツをエクスポートする
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: vikramju
description: この記事では、エクスポート API を使用してTeamsコンテンツをエクスポートMicrosoft Teams説明します。
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
ms.openlocfilehash: 013cd992619264f875841b1b6bb13aca3943d14e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092451"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a>Microsoft Teams Export API を使用してコンテンツをエクスポートする

Teamsエクスポート API を使用すると、1 対 1、グループ チャット、会議チャット、チャネル メッセージを Microsoft Teams。 組織がメッセージをエクスポートするMicrosoft Teams、エクスポート API を使用してTeamsできます。 *チャット メッセージ* は、チャネルまたはチャット 内の個々の [チャット メッセージを](/graph/api/resources/channel?view=graph-rest-beta)[表します](/graph/api/resources/chat?view=graph-rest-beta)。 チャット メッセージには、ルート チャット メッセージまたはチャット メッセージの **replyToId** プロパティによって定義される応答スレッドの一部を指定できます。

これらのエクスポート API を使用する方法の例を次に示します。

- **例 1:** 組織内で Microsoft Teams を有効にし、特定のユーザーまたはチームの日付範囲を渡して、すべての Microsoft Teams メッセージをプログラムで日付にエクスポートする場合。
- **例 2:** 日付範囲を指定して、プログラムですべてのユーザーまたはチーム メッセージを毎日エクスポートする場合。 エクスポート API は、指定した日付範囲内に作成または更新されたメッセージをすべて取得できます。

## <a name="what-is-supported-by-the-teams-export-apis"></a>Teams Export API でサポートされる機能

- **Teams メッセージの** 一括エクスポート: Teams Export API は、テナントあたり最大 200 RPS、アプリケーションに 600 RPS をサポートします。これらの制限により、Teams メッセージを一括エクスポートできる必要があります。
- **アプリケーション コンテキスト**: Microsoft Graph を呼び出す場合、アプリはアプリからアクセス トークンを取得Microsoft ID プラットフォーム。 アクセス トークンには、アプリに関する情報と、Microsoft Graph で使用できるリソースと API に対するアクセス許可が含まれます。 アクセス トークンを取得するには、アプリを Microsoft ID プラットフォーム に登録し、必要な Microsoft Graph リソースへのアクセスをユーザーまたは管理者が承認する必要があります。

    アプリと Microsoft ID プラットフォーム を統合してトークンを取得する方法を既に理解している場合は、「次[](/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps)のステップ」セクションで Microsoft Graph に固有の情報とサンプルを参照してください。
- **ハイブリッド環境:** エクスポート API は、ハイブリッド環境 (オンプレミスのアプリケーションとクラウド) でプロビジョニングされたユーザーによって送信ExchangeメッセージTeams。 ハイブリッド環境用に構成されているユーザーによって送信されたメッセージには、エクスポート API を使用してアクセスできます。
- **ユーザーが削除したメッセージ:** Teams クライアントからユーザーによって削除されたメッセージには、削除時から最大 21 日後にエクスポート API を使用してアクセスできます。
- **メッセージの添付ファイル:** エクスポート API には、メッセージの一部として送信される添付ファイルへのリンクが含まれます。 Export API を使用すると、メッセージに添付されているファイルを取得できます。
- **チャット メッセージのプロパティ:** Export API でサポートされているプロパティの完全Teamsについては、 を参照 [してください](/graph/api/resources/chatmessage?view=graph-rest-beta#properties)。

## <a name="how-to-access-teams-export-apis"></a>エクスポート API Teamsアクセスする方法

- **例 1 は** 、フィルターなしでユーザーまたはチームのすべてのメッセージを取得する簡単なクエリです。

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/getAllMessages
    ```
     ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/getAllMessages
    ```

- **例 2** は、日時フィルターと上位 50 件のメッセージを指定して、ユーザーまたはチームのすべてのメッセージを取得するサンプル クエリです。

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
    ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
>[!NOTE]
>API は、複数の結果が得られた場合に、次のページ リンクを含む応答を返します。 次の結果セットを取得するには、@odata.nextlink の URL で GET を呼び出します。 @odata.nextlink が存在しない場合、または null の場合は、すべてのメッセージが取得されます。

## <a name="prerequisites-to-access-teams-export-apis"></a>エクスポート API にTeams前提条件 

- Teamsエクスポート API は現在プレビュー中です。 API に必要なライセンスを持つユーザーとテナント [だけが](/graph/teams-licenses) 使用できます。 今後、Microsoft は、API を介してアクセスされるデータの量に基づいて、お客様または顧客に追加料金の支払いを要求する場合があります。
- Microsoft Teams機密データにアクセスGraphする Microsoft Graph API は、保護された API と見なされます。 エクスポート API を使用するには、アクセス許可と同意以外の追加の検証が必要です。 これらの保護された API へのアクセスを要求するには、要求フォーム に [入力します](https://aka.ms/teamsgraph/requestaccess)。
- アプリケーションのアクセス許可は、サインインしているユーザーが存在しない場合に実行されるアプリで使用されます。アプリケーションのアクセス許可は、管理者だけが同意できます。 次のアクセス許可が必要です。

    - *Chat.Read.All*: すべての 1:1 およびグループ チャット メッセージへのアクセスを有効にする 
    - *User.Read.All*: テナントのユーザーの一覧へのアクセスを有効にします。 

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
>chatMessage リソースの詳細については、chatMessage リソースの種類 [に関する記事を参照](/graph/api/resources/chatmessage) してください。