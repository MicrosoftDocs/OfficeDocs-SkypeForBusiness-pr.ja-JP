---
title: Microsoft Teams のエクスポート Api を使用してコンテンツをエクスポートする
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: vikramju
description: この記事では、Microsoft Teams のエクスポート Api を使用してチームコンテンツをエクスポートする方法について説明します。
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
ms.openlocfilehash: 7849892870f54f43f0fda16564ad472426d46cd2
ms.sourcegitcommit: af9f96010460f9323db84912fe143aa0750ac798
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/21/2020
ms.locfileid: "48171445"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a>Microsoft Teams のエクスポート Api を使用してコンテンツをエクスポートする

Teams のエクスポート Api を使用すると、Microsoft Teams から1:1 およびグループチャットメッセージをエクスポートすることができます。 組織で Microsoft Teams のメッセージをエクスポートする必要がある場合は、Teams のエクスポート Api を使用してそれらを抽出できます。 *チャットメッセージ* は、 [チャネル](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) または [チャット](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta)内の個々のチャットメッセージを表します。 チャットメッセージは、チャットメッセージの **replyToId** プロパティで定義されているルートチャットメッセージまたは返信スレッドの一部にすることができます。

これらのエクスポート Api の使用方法については、次の例をご覧ください。

- **例 1**: 組織内で microsoft teams を有効にしており、特定のユーザーのデータ範囲を渡すことによって、microsoft teams のすべてのメッセージを日付にエクスポートする必要がある場合。
- **例 2**: データ範囲を指定して、すべてのユーザーメッセージを日常的にプログラムでエクスポートする場合は、次の操作を行います。 エクスポート Api は、指定した日付範囲内に作成または更新されたすべてのメッセージを取得できます。

## <a name="what-is-supported-by-the-teams-export-apis"></a>Teams のエクスポート Api でサポートされている機能

- **Teams メッセージの一括エクスポート:** Teams のエクスポート Api では、テナントと 600 RPS あたり最大200の RPS がアプリケーションに対してサポートされますが、これらの制限により、Teams メッセージの一括エクスポートが可能になります。
- **アプリケーションコンテキスト**: microsoft Graph を呼び出すには、アプリが microsoft identity platform からアクセストークンを取得する必要があります。 アクセストークンには、アプリと、Microsoft Graph で利用可能なリソースと Api に対するアクセス許可に関する情報が含まれています。 アクセストークンを取得するには、アプリが Microsoft identity platform に登録され、ユーザーまたは管理者によって、必要な Microsoft Graph リソースへのアクセスが許可されている必要があります。

    アプリを Microsoft identity platform と統合してトークンを取得することに慣れている場合は、Microsoft Graph に固有の情報とサンプルについては、 [次の手順](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) のセクションを参照してください。
- **ハイブリッド環境:** エクスポート Api は、ハイブリッド環境 (オンプレミスの Exchange および Teams) でプロビジョニングされているユーザーによって送信されたメッセージをサポートします。 ハイブリッド環境向けに構成されているユーザーによって送信されたすべてのメッセージには、エクスポート Api を使用してアクセスできます。
- **ユーザーが削除したメッセージ:** ユーザーが Teams クライアントから削除したメッセージにアクセスするには、削除時から最長で30日以内のエクスポート Api を使用します。
- **メッセージの添付ファイル:** エクスポート Api には、メッセージの一部として送信される添付ファイルへのリンクが含まれます。 エクスポート Api を使用すると、メッセージに添付されているファイルを取得できます。
- **チャットメッセージのプロパティ:**[ここで](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties)は、Teams でエクスポートする api がサポートするプロパティの完全な一覧を参照してください。

## <a name="how-to-access-teams-export-apis"></a>Teams のエクスポート Api にアクセスする方法

- **例 1** は、フィルターを使わずに、ユーザーのすべてのメッセージを取得する単純なクエリです。

    ```HTTP
    GET [https://graph.microsoft.com/beta/users/{id}/chats/allMessages](https://graph.microsoft.com/beta/users/%7bid%7d/chats/allMessages)
    ```

- **例 2** は、日付時刻フィルターと上位の50メッセージを指定して、ユーザーのすべてのメッセージを取得するサンプルクエリです。

    ```HTTP
    https://graph.microsoft.com/beta/users/{id}/chats/allMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```

>[!NOTE]
>API は、複数の結果がある場合に、次のページリンクによって応答を返します。 次の一連の結果を取得するには、url の GET @odata から GET を呼び出します。 @Odata のリンクが存在しないか null の場合は、すべてのメッセージが取得されます。

## <a name="prerequisites-to-access-teams-export-apis"></a>Teams のエクスポート Api にアクセスするための前提条件 

- Teams のエクスポート Api は、現在、Microsoft Api 利用規約の対象となるプレビューに含まれています。  この機能は、必要なライセンスを持っているユーザーとテナントでのみ利用可能です。 適切なライセンスを持たない Api にアクセスしようとすると、403エラーが発生します。
- 機密データにアクセスする microsoft Graph の microsoft Teams Api は、保護された Api と見なされます。 エクスポート Api を使用するには、権限と同意を超えた追加の検証が必要です。 これらの保護された Api へのアクセスを要求するには、 [要求フォーム](https://aka.ms/teamsgraph/requestaccess)に入力します。
- アプリケーションのアクセス許可は、サインインしたユーザーが存在しない状態で実行されるアプリで使われます。アプリケーションのアクセス許可は、管理者のみが各人することができます。 次の権限が必要です。

    - *チャット。 [すべて*]: すべての1:1 およびグループチャットメッセージへのアクセスを有効にします。 
    - *ユーザー。 [すべて*]: テナントのユーザーの一覧へのアクセスを有効にします。 

## <a name="json-representation"></a>JSON 表現

次の例は、リソースの JSON 表現です。

名前空間: microsoft graph

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
"body": {"@odata.type": "microsoft.graph.itemBody"},
"summary": "string",
"attachments": \[{"@odata.type": "microsoft.graph.chatMessageAttachment"}\],
"mentions": \[{"@odata.type": "microsoft.graph.chatMessageMention"}\],
"importance": "string",
"locale": "string",
}
```

>[!NOTE]
>ChatMessage リソースの詳細については、「 [chatmessage リソースの種類](https://docs.microsoft.com/graph/api/resources/chatmessage) 」を参照してください。
