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
ms.openlocfilehash: f4ea2d747d40c221d9e99b51fc7b15da8e2cdd12
ms.sourcegitcommit: 04eba352d9e203aa9cd1282c4f4c7158a0469678
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2021
ms.locfileid: "49944602"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a>Microsoft Teams エクスポート API を使用してコンテンツをエクスポートする

Teams エクスポート API を使用すると、Microsoft Teams から 1 対 1、グループ チャット、チャネル メッセージをエクスポートできます。 組織で Microsoft Teams メッセージをエクスポートする必要がある場合は、Teams エクスポート API を使用してメッセージを抽出できます。 *チャット メッセージは* 、チャネルまたはチャット内の個々の [チャット メッセージを](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) 表 [します](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta)。 チャット メッセージには、ルート チャット メッセージや、チャット メッセージの **replyToId** プロパティによって定義される返信スレッドの一部を使用できます。

これらのエクスポート API を使用する方法の例を次に示します。

- **例 1:** 組織内で Microsoft Teams を有効にしている場合、特定のユーザーまたはチームの日付範囲を渡して、プログラムを使用してすべての Microsoft Teams メッセージを日付にエクスポートする場合。
- **例 2:** 日付範囲を指定して、プログラムを使用してすべてのユーザーまたはチーム メッセージを毎日エクスポートする場合。 エクスポート API は、指定した日付範囲内に作成または更新されたメッセージをすべて取得できます。

## <a name="what-is-supported-by-the-teams-export-apis"></a>Teams エクスポート API でサポートされる機能

- **Teams メッセージの一括エクスポート:** Teams エクスポート API は、テナントごとに最大 200 RPS、アプリケーションに 600 RPS をサポートします。これらの制限により、Teams メッセージを一括エクスポートできる必要があります。
- **アプリケーション コンテキスト**: Microsoft Graph を呼び出す場合、アプリは Microsoft ID プラットフォームからアクセス トークンを取得する必要があります。 アクセス トークンには、アプリに関する情報と、Microsoft Graph で利用できるリソースと API に対するアクセス許可が含まれます。 アクセス トークンを取得するには、アプリを Microsoft ID プラットフォームに登録し、必要な Microsoft Graph リソースへのアクセスをユーザーまたは管理者が承認する必要があります。

    アプリと Microsoft ID プラットフォームを統合してトークンを取得する方法について既に理解している[](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps)場合は、Microsoft Graph 固有の情報とサンプルについては、「次の手順」セクションを参照してください。
- **ハイブリッド環境:** ハイブリッド環境 (オンプレミスの Exchange と Teams) でプロビジョニングされたユーザーから送信されたエクスポート API サポート メッセージ。 ハイブリッド環境用に構成されているユーザーから送信されたメッセージには、エクスポート API を使用してアクセスできます。
- **ユーザーが削除したメッセージ:** Teams クライアントからユーザーによって削除されたメッセージには、削除から最大 30 日後にエクスポート API を使用してアクセスできます。
- **メッセージの添付ファイル:** エクスポート API には、メッセージの一部として送信される添付ファイルへのリンクが含まれます。 エクスポート API を使用すると、メッセージに添付されているファイルを取得できます。
- **チャット メッセージのプロパティ:** Teams エクスポート API がここでサポートするプロパティの完全な一覧を参照 [してください](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties)。

## <a name="how-to-access-teams-export-apis"></a>Teams エクスポート API にアクセスする方法

- **例 1** は、フィルターなしでユーザーまたはチームのすべてのメッセージを取得する簡単なクエリです。

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/allMessages
    ```
     ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/allMessages
    ```

- **例 2** は、日付時刻フィルターと上位 50 件のメッセージを指定して、ユーザーまたはチームのすべてのメッセージを取得するサンプル クエリです。

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/allMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/allMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
>[!NOTE]
>The API returns response with next page link in case of multiple results. For getting next set of results, simply call GET on the url from @odata.nextlink. If @odata.nextlink is not present or null then all messages are retrieved.

## Prerequisites to access Teams Export APIs 

- Teams Export APIs are currently in preview. It will only be available to users and tenants that have the [required licenses](https://aka.ms/teams-changenotification-licenses) for APIs. In the future, Microsoft may require you or your customers to pay additional fees based on the amount of data accessed through the API.
- Microsoft Teams APIs in Microsoft Graph that access sensitive data are considered protected APIs. Export APIs require that you have additional validation, beyond permissions and consent, before you can use them. To request access to these protected APIs, complete the [request form](https://aka.ms/teamsgraph/requestaccess).
- Application permissions are used by apps that run without a signed-in user present; application permissions can only be consented by an administrator. The following permissions are needed:

    - *Chat.Read.All*: enables access to all 1:1 and Group chat messages 
    - *User.Read.All*: enables access to the list of users for a tenant 

## JSON representation

The following example is a JSON representation of the resource:

Namespace: microsoft.graph

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
                    "id": "string (identifier)",
                    "displayName": "string",
                    "userIdentityType": "aadUser"                }
            },
"body": {"@odata.type": "microsoft.graph.itemBody"},
"summary": "string",
"chatId": "string (identifier)"
"attachments": \[{"@odata.type": "microsoft.graph.chatMessageAttachment"}\],
"mentions": \[{"@odata.type": "microsoft.graph.chatMessageMention"}\],
"importance": "string",
"locale": "string",
}
```

>[!NOTE]
>chatMessage リソースの詳細については [、chatMessage リソースの種類に関する記事を参照](https://docs.microsoft.com/graph/api/resources/chatmessage) してください。
