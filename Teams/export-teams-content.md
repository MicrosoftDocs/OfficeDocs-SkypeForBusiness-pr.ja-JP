---
title: Microsoft Teams Export API を使用してコンテンツをエクスポートする
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: vikramju
description: この記事では、Microsoft Teams Export API を使用してTeamsコンテンツをエクスポートする方法について説明します。
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
ms.openlocfilehash: 84f53b5c75c9e99e3a3bfc2877c096b32fe3b9c0
ms.sourcegitcommit: 26ce61afcb743c8b9e06b4fa048ad93ab70c31c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2021
ms.locfileid: "60082867"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a>Microsoft Teams Export API を使用してコンテンツをエクスポートする

Teamsエクスポート API を使用すると、1:1、グループ チャット、会議チャット、チャネル メッセージをMicrosoft Teamsからエクスポートできます。 組織でMicrosoft Teamsメッセージをエクスポートする必要がある場合は、Teams Export API を使用してメッセージを抽出できます。 *チャット メッセージ* は、 [チャネル](/graph/api/resources/channel?view=graph-rest-beta) またはチャット内の個々のチャット メッセージを表 [します](/graph/api/resources/chat?view=graph-rest-beta)。 チャット メッセージには、ルート チャット メッセージまたはチャット メッセージの **replyToId** プロパティによって定義される応答スレッドの一部を指定できます。

これらのエクスポート API を使用する方法の例を次に示します。

- **例 1**: 組織内のMicrosoft Teamsを有効にしていて、特定のユーザーまたはチームの日付範囲を渡すことによって、すべてのMicrosoft Teams メッセージをプログラムで日付にエクスポートする場合。
- **例 2**: 日付範囲を指定して、すべてのユーザーメッセージまたはチーム メッセージを毎日プログラムでエクスポートする場合。 エクスポート API は、指定された日付範囲の間に作成または更新されたすべてのメッセージを取得できます。

## <a name="what-is-supported-by-the-teams-export-apis"></a>Teams エクスポート API では何がサポートされていますか?

- **Teams メッセージの一括エクスポート:** Teamsエクスポート API では、テナントあたり最大 200 RPS、アプリケーションに対して 600 RPS がサポートされます。これらの制限により、Teams メッセージを一括エクスポートできる必要があります。
- **アプリケーション コンテキスト**: Microsoft Graphを呼び出すには、アプリがMicrosoft ID プラットフォームからアクセス トークンを取得する必要があります。 アクセス トークンには、アプリに関する情報と、Microsoft Graphで使用できるリソースと API に対するアクセス許可が含まれています。 アクセス トークンを取得するには、アプリをMicrosoft ID プラットフォームに登録し、ユーザーまたは管理者が必要な Microsoft Graph リソースへのアクセスを承認する必要があります。

    トークンを取得するためのアプリとMicrosoft ID プラットフォームの統合について既に理解している場合は、Microsoft Graphに固有の情報とサンプルについては、「[次の手順」](/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps)セクションを参照してください。
- **ハイブリッド環境:** エクスポート API は、ハイブリッド環境 (オンプレミスのExchangeとTeams) でプロビジョニングされたユーザーによって送信されるメッセージをサポートします。 ハイブリッド環境用に構成されているユーザーによって送信されたメッセージには、エクスポート API を使用してアクセスできます。
- **ユーザーが削除したメッセージ:** Teams クライアントからユーザーによって削除されたメッセージには、削除後最大 21 日間のエクスポート API を使用してアクセスできます。
- **メッセージの添付ファイル:** エクスポート API には、メッセージの一部として送信される添付ファイルへのリンクが含まれます。 エクスポート API を使用すると、メッセージに添付されているファイルを取得できます。
- **チャット メッセージのプロパティ:** エクスポート API でサポートされているプロパティの完全な一覧Teamsこちらを参照 [してください](/graph/api/resources/chatmessage?view=graph-rest-beta#properties)。

>[!NOTE]
>エクスポート API では *、リアクションは* サポートされません。

## <a name="how-to-access-teams-export-apis"></a>Teamsエクスポート API にアクセスする方法

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
>[!NOTE]
>API は、複数の結果が返された場合に、次のページ リンクを含む応答を返します。 次の結果セットを取得するには、@odata.nextlink の URL で GET を呼び出すだけです。 @odata.nextlink が存在しない場合、または null の場合、すべてのメッセージが取得されます。

## <a name="prerequisites-to-access-teams-export-apis"></a>Teamsエクスポート API にアクセスするための前提条件 

- 機密データにアクセスする Microsoft GraphのMicrosoft Teams API は、保護された API と見なされます。 エクスポート API を使用するには、アクセス許可と同意を超えた追加の検証が必要です。 これらの保護された API へのアクセスを要求するには、 [要求フォームに入力します](https://aka.ms/teamsgraph/requestaccess)。
- アプリケーションのアクセス許可は、サインインしているユーザーが存在せずに実行されるアプリによって使用されます。アプリケーションのアクセス許可は管理者のみが同意できます。 次のアクセス許可が必要です。

    - *Chat.Read.All*: すべての 1:1、グループ チャット、会議チャット メッセージへのアクセスを有効にします 
    - *ChannelMessage.Read.All*: すべてのチャネル メッセージへのアクセスを有効にします  
    - *User.Read.All*: テナントのユーザーの一覧へのアクセスを有効にします

## <a name="license-requirements-for-teams-export-apis"></a>Teams エクスポート API のライセンス要件

Export API は、モデル クエリ パラメーターを使用して、セキュリティとコンプライアンス (S+C) と一般的な使用シナリオをサポートします。 S+ C シナリオ (モデル A) にはシードされた容量が含まれており、E5 サブスクリプションと一般的な使用シナリオ (モデル B) はすべてのサブスクリプションで使用でき、使用のみ可能です。 シードされた容量と消費料金の詳細については、「[Microsoft Graph Teams API のライセンスと支払いの要件」を参照](/graph/teams-licenses)してください。

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

>[!NOTE]
>chatMessage リソースの詳細については、 [chatMessage リソースの種類](/graph/api/resources/chatmessage) に関する記事を参照してください。