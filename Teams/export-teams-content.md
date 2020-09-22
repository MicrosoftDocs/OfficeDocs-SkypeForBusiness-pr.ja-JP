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
# <a name="export-content-with-the-microsoft-teams-export-apis"></a><span data-ttu-id="4ac54-103">Microsoft Teams のエクスポート Api を使用してコンテンツをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="4ac54-103">Export content with the Microsoft Teams Export APIs</span></span>

<span data-ttu-id="4ac54-104">Teams のエクスポート Api を使用すると、Microsoft Teams から1:1 およびグループチャットメッセージをエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="4ac54-104">Teams Export APIs allow you to export 1:1 and group chat messages from Microsoft Teams.</span></span> <span data-ttu-id="4ac54-105">組織で Microsoft Teams のメッセージをエクスポートする必要がある場合は、Teams のエクスポート Api を使用してそれらを抽出できます。</span><span class="sxs-lookup"><span data-stu-id="4ac54-105">If your organization needs to export Microsoft Teams messages, you can be able to extract them using Teams Export APIs.</span></span> <span data-ttu-id="4ac54-106">*チャットメッセージ* は、 [チャネル](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) または [チャット](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta)内の個々のチャットメッセージを表します。</span><span class="sxs-lookup"><span data-stu-id="4ac54-106">*Chat Message* represents an individual chat message within a [channel](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) or [chat](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta).</span></span> <span data-ttu-id="4ac54-107">チャットメッセージは、チャットメッセージの **replyToId** プロパティで定義されているルートチャットメッセージまたは返信スレッドの一部にすることができます。</span><span class="sxs-lookup"><span data-stu-id="4ac54-107">The chat message can be a root chat message or part of a reply thread that is defined by the **replyToId** property in the chat message.</span></span>

<span data-ttu-id="4ac54-108">これらのエクスポート Api の使用方法については、次の例をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4ac54-108">Here are some examples on how you can use these export APIs:</span></span>

- <span data-ttu-id="4ac54-109">**例 1**: 組織内で microsoft teams を有効にしており、特定のユーザーのデータ範囲を渡すことによって、microsoft teams のすべてのメッセージを日付にエクスポートする必要がある場合。</span><span class="sxs-lookup"><span data-stu-id="4ac54-109">**Example 1**: If you have enabled Microsoft Teams in your organization and want to export all the Microsoft Teams messages to date programmatically by passing the data range for a given user.</span></span>
- <span data-ttu-id="4ac54-110">**例 2**: データ範囲を指定して、すべてのユーザーメッセージを日常的にプログラムでエクスポートする場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="4ac54-110">**Example 2**: If you want to programmatically export all user messages daily by providing a data range.</span></span> <span data-ttu-id="4ac54-111">エクスポート Api は、指定した日付範囲内に作成または更新されたすべてのメッセージを取得できます。</span><span class="sxs-lookup"><span data-stu-id="4ac54-111">Export APIs can retrieve all the messages created or updated during the given date range.</span></span>

## <a name="what-is-supported-by-the-teams-export-apis"></a><span data-ttu-id="4ac54-112">Teams のエクスポート Api でサポートされている機能</span><span class="sxs-lookup"><span data-stu-id="4ac54-112">What is supported by the Teams Export APIs?</span></span>

- <span data-ttu-id="4ac54-113">**Teams メッセージの一括エクスポート:** Teams のエクスポート Api では、テナントと 600 RPS あたり最大200の RPS がアプリケーションに対してサポートされますが、これらの制限により、Teams メッセージの一括エクスポートが可能になります。</span><span class="sxs-lookup"><span data-stu-id="4ac54-113">**Bulk Export of Teams Message:** Teams Export APIs support up to 200 RPS Per App Per tenant and 600 RPS for an Application, with these limits you should be able to bulk export of Teams messages.</span></span>
- <span data-ttu-id="4ac54-114">**アプリケーションコンテキスト**: microsoft Graph を呼び出すには、アプリが microsoft identity platform からアクセストークンを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ac54-114">**Application Context**: To call Microsoft Graph, your app must acquire an access token from the Microsoft identity platform.</span></span> <span data-ttu-id="4ac54-115">アクセストークンには、アプリと、Microsoft Graph で利用可能なリソースと Api に対するアクセス許可に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4ac54-115">The access token contains information about your app and the permissions it has for the resources and APIs available through Microsoft Graph.</span></span> <span data-ttu-id="4ac54-116">アクセストークンを取得するには、アプリが Microsoft identity platform に登録され、ユーザーまたは管理者によって、必要な Microsoft Graph リソースへのアクセスが許可されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ac54-116">To get an access token, your app must be registered with the Microsoft identity platform and be authorized by either a user or an administrator for access to the Microsoft Graph resources it needs.</span></span>

    <span data-ttu-id="4ac54-117">アプリを Microsoft identity platform と統合してトークンを取得することに慣れている場合は、Microsoft Graph に固有の情報とサンプルについては、 [次の手順](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ac54-117">If you are already familiar with integrating an app with the Microsoft identity platform to get tokens, see the [Next Steps](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) section for information and samples specific to Microsoft Graph.</span></span>
- <span data-ttu-id="4ac54-118">**ハイブリッド環境:** エクスポート Api は、ハイブリッド環境 (オンプレミスの Exchange および Teams) でプロビジョニングされているユーザーによって送信されたメッセージをサポートします。</span><span class="sxs-lookup"><span data-stu-id="4ac54-118">**Hybrid Environment:** Export APIs support messages sent by users who are provisioned on Hybrid Environment (on-premises Exchange and Teams).</span></span> <span data-ttu-id="4ac54-119">ハイブリッド環境向けに構成されているユーザーによって送信されたすべてのメッセージには、エクスポート Api を使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4ac54-119">Any messages that are sent by users who are configured for hybrid environment will be accessible using Export APIs.</span></span>
- <span data-ttu-id="4ac54-120">**ユーザーが削除したメッセージ:** ユーザーが Teams クライアントから削除したメッセージにアクセスするには、削除時から最長で30日以内のエクスポート Api を使用します。</span><span class="sxs-lookup"><span data-stu-id="4ac54-120">**User Deleted Messages:** Messages that are deleted by user from Teams client can be accessed using export APIs up to 30 days from the time of deletion.</span></span>
- <span data-ttu-id="4ac54-121">**メッセージの添付ファイル:** エクスポート Api には、メッセージの一部として送信される添付ファイルへのリンクが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4ac54-121">**Message Attachments:** Export APIs include the links to the attachments that are sent as part of messages.</span></span> <span data-ttu-id="4ac54-122">エクスポート Api を使用すると、メッセージに添付されているファイルを取得できます。</span><span class="sxs-lookup"><span data-stu-id="4ac54-122">Using Export APIs you can retrieve the files attached in the messages.</span></span>
- <span data-ttu-id="4ac54-123">**チャットメッセージのプロパティ:**[ここで](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties)は、Teams でエクスポートする api がサポートするプロパティの完全な一覧を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ac54-123">**Chat Message Properties:** Refer to the complete list of properties that Teams Export APIs support [here](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties).</span></span>

## <a name="how-to-access-teams-export-apis"></a><span data-ttu-id="4ac54-124">Teams のエクスポート Api にアクセスする方法</span><span class="sxs-lookup"><span data-stu-id="4ac54-124">How to access Teams Export APIs</span></span>

- <span data-ttu-id="4ac54-125">**例 1** は、フィルターを使わずに、ユーザーのすべてのメッセージを取得する単純なクエリです。</span><span class="sxs-lookup"><span data-stu-id="4ac54-125">**Example 1** is a simple query to retrieve all the messages of a user without any filters:</span></span>

    ```HTTP
    GET [https://graph.microsoft.com/beta/users/{id}/chats/allMessages](https://graph.microsoft.com/beta/users/%7bid%7d/chats/allMessages)
    ```

- <span data-ttu-id="4ac54-126">**例 2** は、日付時刻フィルターと上位の50メッセージを指定して、ユーザーのすべてのメッセージを取得するサンプルクエリです。</span><span class="sxs-lookup"><span data-stu-id="4ac54-126">**Example 2** is a sample query to retrieve all the messages of a user by specifying date time filters and top 50 messages:</span></span>

    ```HTTP
    https://graph.microsoft.com/beta/users/{id}/chats/allMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```

>[!NOTE]
><span data-ttu-id="4ac54-127">API は、複数の結果がある場合に、次のページリンクによって応答を返します。</span><span class="sxs-lookup"><span data-stu-id="4ac54-127">The API returns response with next page link in case of multiple results.</span></span> <span data-ttu-id="4ac54-128">次の一連の結果を取得するには、url の GET @odata から GET を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4ac54-128">For getting next set of results, simply call GET on the url from @odata.nextlink.</span></span> <span data-ttu-id="4ac54-129">@Odata のリンクが存在しないか null の場合は、すべてのメッセージが取得されます。</span><span class="sxs-lookup"><span data-stu-id="4ac54-129">If @odata.nextlink is not present or null then all messages are retrieved.</span></span>

## <a name="prerequisites-to-access-teams-export-apis"></a><span data-ttu-id="4ac54-130">Teams のエクスポート Api にアクセスするための前提条件</span><span class="sxs-lookup"><span data-stu-id="4ac54-130">Prerequisites to access Teams Export APIs</span></span> 

- <span data-ttu-id="4ac54-131">Teams のエクスポート Api は、現在、Microsoft Api 利用規約の対象となるプレビューに含まれています。</span><span class="sxs-lookup"><span data-stu-id="4ac54-131">Teams Export APIs are currently in preview, subject to the Microsoft APIs Terms of Use.</span></span>  <span data-ttu-id="4ac54-132">この機能は、必要なライセンスを持っているユーザーとテナントでのみ利用可能です。</span><span class="sxs-lookup"><span data-stu-id="4ac54-132">It will only be available to users and tenants that have the required licenses.</span></span> <span data-ttu-id="4ac54-133">適切なライセンスを持たない Api にアクセスしようとすると、403エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="4ac54-133">Attempts to access APIs without the proper licenses will result in a 403 error.</span></span>
- <span data-ttu-id="4ac54-134">機密データにアクセスする microsoft Graph の microsoft Teams Api は、保護された Api と見なされます。</span><span class="sxs-lookup"><span data-stu-id="4ac54-134">Microsoft Teams APIs in Microsoft Graph that access sensitive data are considered protected APIs.</span></span> <span data-ttu-id="4ac54-135">エクスポート Api を使用するには、権限と同意を超えた追加の検証が必要です。</span><span class="sxs-lookup"><span data-stu-id="4ac54-135">Export APIs require that you have additional validation, beyond permissions and consent, before you can use them.</span></span> <span data-ttu-id="4ac54-136">これらの保護された Api へのアクセスを要求するには、 [要求フォーム](https://aka.ms/teamsgraph/requestaccess)に入力します。</span><span class="sxs-lookup"><span data-stu-id="4ac54-136">To request access to these protected APIs, complete the [request form](https://aka.ms/teamsgraph/requestaccess).</span></span>
- <span data-ttu-id="4ac54-137">アプリケーションのアクセス許可は、サインインしたユーザーが存在しない状態で実行されるアプリで使われます。アプリケーションのアクセス許可は、管理者のみが各人することができます。</span><span class="sxs-lookup"><span data-stu-id="4ac54-137">Application permissions are used by apps that run without a signed-in user present; application permissions can only be consented by an administrator.</span></span> <span data-ttu-id="4ac54-138">次の権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="4ac54-138">The following permissions are needed:</span></span>

    - <span data-ttu-id="4ac54-139">*チャット。 [すべて*]: すべての1:1 およびグループチャットメッセージへのアクセスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="4ac54-139">*Chat.Read.All*: enables access to all 1:1 and Group chat messages</span></span> 
    - <span data-ttu-id="4ac54-140">*ユーザー。 [すべて*]: テナントのユーザーの一覧へのアクセスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="4ac54-140">*User.Read.All*: enables access to the list of users for a tenant</span></span> 

## <a name="json-representation"></a><span data-ttu-id="4ac54-141">JSON 表現</span><span class="sxs-lookup"><span data-stu-id="4ac54-141">JSON representation</span></span>

<span data-ttu-id="4ac54-142">次の例は、リソースの JSON 表現です。</span><span class="sxs-lookup"><span data-stu-id="4ac54-142">The following example is a JSON representation of the resource:</span></span>

<span data-ttu-id="4ac54-143">名前空間: microsoft graph</span><span class="sxs-lookup"><span data-stu-id="4ac54-143">Namespace: microsoft.graph</span></span>

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
><span data-ttu-id="4ac54-144">ChatMessage リソースの詳細については、「 [chatmessage リソースの種類](https://docs.microsoft.com/graph/api/resources/chatmessage) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ac54-144">For more details on chatMessage resource, see the [chatMessage resource type](https://docs.microsoft.com/graph/api/resources/chatmessage) article.</span></span>
