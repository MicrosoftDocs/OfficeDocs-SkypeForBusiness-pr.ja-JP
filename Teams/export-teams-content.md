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
# <a name="export-content-with-the-microsoft-teams-export-apis"></a><span data-ttu-id="cff23-103">Microsoft Teams Export API を使用してコンテンツをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="cff23-103">Export content with the Microsoft Teams Export APIs</span></span>

<span data-ttu-id="cff23-104">Teamsエクスポート API を使用すると、1 対 1、グループ チャット、会議チャット、チャネル メッセージを Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="cff23-104">Teams Export APIs allow you to export 1:1, group chat, meeting chats, and channel messages from Microsoft Teams.</span></span> <span data-ttu-id="cff23-105">組織がメッセージをエクスポートするMicrosoft Teams、エクスポート API を使用してTeamsできます。</span><span class="sxs-lookup"><span data-stu-id="cff23-105">If your organization needs to export Microsoft Teams messages, you are able to extract them using Teams Export APIs.</span></span> <span data-ttu-id="cff23-106">*チャット メッセージ* は、チャネルまたはチャット 内の個々の [チャット メッセージを](/graph/api/resources/channel?view=graph-rest-beta)[表します](/graph/api/resources/chat?view=graph-rest-beta)。</span><span class="sxs-lookup"><span data-stu-id="cff23-106">*Chat Message* represents an individual chat message within a [channel](/graph/api/resources/channel?view=graph-rest-beta) or [chat](/graph/api/resources/chat?view=graph-rest-beta).</span></span> <span data-ttu-id="cff23-107">チャット メッセージには、ルート チャット メッセージまたはチャット メッセージの **replyToId** プロパティによって定義される応答スレッドの一部を指定できます。</span><span class="sxs-lookup"><span data-stu-id="cff23-107">The chat message can be a root chat message or part of a reply thread that is defined by the **replyToId** property in the chat message.</span></span>

<span data-ttu-id="cff23-108">これらのエクスポート API を使用する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="cff23-108">Here are some examples on how you can use these export APIs:</span></span>

- <span data-ttu-id="cff23-109">**例 1:** 組織内で Microsoft Teams を有効にし、特定のユーザーまたはチームの日付範囲を渡して、すべての Microsoft Teams メッセージをプログラムで日付にエクスポートする場合。</span><span class="sxs-lookup"><span data-stu-id="cff23-109">**Example 1**: If you have enabled Microsoft Teams in your organization and want to export all the Microsoft Teams messages to date programmatically by passing the date range for a given user or team.</span></span>
- <span data-ttu-id="cff23-110">**例 2:** 日付範囲を指定して、プログラムですべてのユーザーまたはチーム メッセージを毎日エクスポートする場合。</span><span class="sxs-lookup"><span data-stu-id="cff23-110">**Example 2**: If you want to programmatically export all user or team messages daily by providing a date range.</span></span> <span data-ttu-id="cff23-111">エクスポート API は、指定した日付範囲内に作成または更新されたメッセージをすべて取得できます。</span><span class="sxs-lookup"><span data-stu-id="cff23-111">Export APIs can retrieve all the messages created or updated during the given date range.</span></span>

## <a name="what-is-supported-by-the-teams-export-apis"></a><span data-ttu-id="cff23-112">Teams Export API でサポートされる機能</span><span class="sxs-lookup"><span data-stu-id="cff23-112">What is supported by the Teams Export APIs?</span></span>

- <span data-ttu-id="cff23-113">**Teams メッセージの** 一括エクスポート: Teams Export API は、テナントあたり最大 200 RPS、アプリケーションに 600 RPS をサポートします。これらの制限により、Teams メッセージを一括エクスポートできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="cff23-113">**Bulk Export of Teams Message:** Teams Export APIs support up to 200 RPS Per App Per tenant and 600 RPS for an Application, with these limits you should be able to bulk export of Teams messages.</span></span>
- <span data-ttu-id="cff23-114">**アプリケーション コンテキスト**: Microsoft Graph を呼び出す場合、アプリはアプリからアクセス トークンを取得Microsoft ID プラットフォーム。</span><span class="sxs-lookup"><span data-stu-id="cff23-114">**Application Context**: To call Microsoft Graph, your app must acquire an access token from the Microsoft identity platform.</span></span> <span data-ttu-id="cff23-115">アクセス トークンには、アプリに関する情報と、Microsoft Graph で使用できるリソースと API に対するアクセス許可が含まれます。</span><span class="sxs-lookup"><span data-stu-id="cff23-115">The access token contains information about your app and the permissions it has for the resources and APIs available through Microsoft Graph.</span></span> <span data-ttu-id="cff23-116">アクセス トークンを取得するには、アプリを Microsoft ID プラットフォーム に登録し、必要な Microsoft Graph リソースへのアクセスをユーザーまたは管理者が承認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cff23-116">To get an access token, your app must be registered with the Microsoft identity platform and be authorized by either a user or an administrator for access to the Microsoft Graph resources it needs.</span></span>

    <span data-ttu-id="cff23-117">アプリと Microsoft ID プラットフォーム を統合してトークンを取得する方法を既に理解している場合は、「次[](/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps)のステップ」セクションで Microsoft Graph に固有の情報とサンプルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cff23-117">If you are already familiar with integrating an app with the Microsoft identity platform to get tokens, see the [Next Steps](/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) section for information and samples specific to Microsoft Graph.</span></span>
- <span data-ttu-id="cff23-118">**ハイブリッド環境:** エクスポート API は、ハイブリッド環境 (オンプレミスのアプリケーションとクラウド) でプロビジョニングされたユーザーによって送信ExchangeメッセージTeams。</span><span class="sxs-lookup"><span data-stu-id="cff23-118">**Hybrid Environment:** Export APIs support messages sent by users who are provisioned on Hybrid Environment (on-premises Exchange and Teams).</span></span> <span data-ttu-id="cff23-119">ハイブリッド環境用に構成されているユーザーによって送信されたメッセージには、エクスポート API を使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="cff23-119">Any messages that are sent by users who are configured for hybrid environment will be accessible using Export APIs.</span></span>
- <span data-ttu-id="cff23-120">**ユーザーが削除したメッセージ:** Teams クライアントからユーザーによって削除されたメッセージには、削除時から最大 21 日後にエクスポート API を使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="cff23-120">**User Deleted Messages:** Messages that are deleted by users from the Teams client can be accessed using export APIs up to 21 days from the time of deletion.</span></span>
- <span data-ttu-id="cff23-121">**メッセージの添付ファイル:** エクスポート API には、メッセージの一部として送信される添付ファイルへのリンクが含まれます。</span><span class="sxs-lookup"><span data-stu-id="cff23-121">**Message Attachments:** Export APIs include the links to the attachments that are sent as part of messages.</span></span> <span data-ttu-id="cff23-122">Export API を使用すると、メッセージに添付されているファイルを取得できます。</span><span class="sxs-lookup"><span data-stu-id="cff23-122">Using Export APIs you can retrieve the files attached in the messages.</span></span>
- <span data-ttu-id="cff23-123">**チャット メッセージのプロパティ:** Export API でサポートされているプロパティの完全Teamsについては、 を参照 [してください](/graph/api/resources/chatmessage?view=graph-rest-beta#properties)。</span><span class="sxs-lookup"><span data-stu-id="cff23-123">**Chat Message Properties:** Refer to the complete list of properties that Teams Export APIs support [here](/graph/api/resources/chatmessage?view=graph-rest-beta#properties).</span></span>

## <a name="how-to-access-teams-export-apis"></a><span data-ttu-id="cff23-124">エクスポート API Teamsアクセスする方法</span><span class="sxs-lookup"><span data-stu-id="cff23-124">How to access Teams Export APIs</span></span>

- <span data-ttu-id="cff23-125">**例 1 は** 、フィルターなしでユーザーまたはチームのすべてのメッセージを取得する簡単なクエリです。</span><span class="sxs-lookup"><span data-stu-id="cff23-125">**Example 1** is a simple query to retrieve all the messages of a user or team without any filters:</span></span>

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/getAllMessages
    ```
     ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/getAllMessages
    ```

- <span data-ttu-id="cff23-126">**例 2** は、日時フィルターと上位 50 件のメッセージを指定して、ユーザーまたはチームのすべてのメッセージを取得するサンプル クエリです。</span><span class="sxs-lookup"><span data-stu-id="cff23-126">**Example 2** is a sample query to retrieve all the messages of a user or team by specifying date time filters and top 50 messages:</span></span>

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
    ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
>[!NOTE]
><span data-ttu-id="cff23-127">API は、複数の結果が得られた場合に、次のページ リンクを含む応答を返します。</span><span class="sxs-lookup"><span data-stu-id="cff23-127">The API returns response with next page link in case of multiple results.</span></span> <span data-ttu-id="cff23-128">次の結果セットを取得するには、@odata.nextlink の URL で GET を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="cff23-128">For getting next set of results, simply call GET on the url from @odata.nextlink.</span></span> <span data-ttu-id="cff23-129">@odata.nextlink が存在しない場合、または null の場合は、すべてのメッセージが取得されます。</span><span class="sxs-lookup"><span data-stu-id="cff23-129">If @odata.nextlink is not present or null then all messages are retrieved.</span></span>

## <a name="prerequisites-to-access-teams-export-apis"></a><span data-ttu-id="cff23-130">エクスポート API にTeams前提条件</span><span class="sxs-lookup"><span data-stu-id="cff23-130">Prerequisites to access Teams Export APIs</span></span> 

- <span data-ttu-id="cff23-131">Teamsエクスポート API は現在プレビュー中です。</span><span class="sxs-lookup"><span data-stu-id="cff23-131">Teams Export APIs are currently in preview.</span></span> <span data-ttu-id="cff23-132">API に必要なライセンスを持つユーザーとテナント [だけが](/graph/teams-licenses) 使用できます。</span><span class="sxs-lookup"><span data-stu-id="cff23-132">It will only be available to users and tenants that have the [required licenses](/graph/teams-licenses) for APIs.</span></span> <span data-ttu-id="cff23-133">今後、Microsoft は、API を介してアクセスされるデータの量に基づいて、お客様または顧客に追加料金の支払いを要求する場合があります。</span><span class="sxs-lookup"><span data-stu-id="cff23-133">In the future, Microsoft may require you or your customers to pay additional fees based on the amount of data accessed through the API.</span></span>
- <span data-ttu-id="cff23-134">Microsoft Teams機密データにアクセスGraphする Microsoft Graph API は、保護された API と見なされます。</span><span class="sxs-lookup"><span data-stu-id="cff23-134">Microsoft Teams APIs in Microsoft Graph that access sensitive data are considered protected APIs.</span></span> <span data-ttu-id="cff23-135">エクスポート API を使用するには、アクセス許可と同意以外の追加の検証が必要です。</span><span class="sxs-lookup"><span data-stu-id="cff23-135">Export APIs require that you have additional validation, beyond permissions and consent, before you can use them.</span></span> <span data-ttu-id="cff23-136">これらの保護された API へのアクセスを要求するには、要求フォーム に [入力します](https://aka.ms/teamsgraph/requestaccess)。</span><span class="sxs-lookup"><span data-stu-id="cff23-136">To request access to these protected APIs, complete the [request form](https://aka.ms/teamsgraph/requestaccess).</span></span>
- <span data-ttu-id="cff23-137">アプリケーションのアクセス許可は、サインインしているユーザーが存在しない場合に実行されるアプリで使用されます。アプリケーションのアクセス許可は、管理者だけが同意できます。</span><span class="sxs-lookup"><span data-stu-id="cff23-137">Application permissions are used by apps that run without a signed-in user present; application permissions can only be consented by an administrator.</span></span> <span data-ttu-id="cff23-138">次のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="cff23-138">The following permissions are needed:</span></span>

    - <span data-ttu-id="cff23-139">*Chat.Read.All*: すべての 1:1 およびグループ チャット メッセージへのアクセスを有効にする</span><span class="sxs-lookup"><span data-stu-id="cff23-139">*Chat.Read.All*: enables access to all 1:1 and Group chat messages</span></span> 
    - <span data-ttu-id="cff23-140">*User.Read.All*: テナントのユーザーの一覧へのアクセスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="cff23-140">*User.Read.All*: enables access to the list of users for a tenant</span></span> 

## <a name="json-representation"></a><span data-ttu-id="cff23-141">JSON 表現</span><span class="sxs-lookup"><span data-stu-id="cff23-141">JSON representation</span></span>

<span data-ttu-id="cff23-142">次の例は、リソースの JSON 表現です。</span><span class="sxs-lookup"><span data-stu-id="cff23-142">The following example is a JSON representation of the resource:</span></span>

<span data-ttu-id="cff23-143">名前空間: microsoft.graph</span><span class="sxs-lookup"><span data-stu-id="cff23-143">Namespace: microsoft.graph</span></span>

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
><span data-ttu-id="cff23-144">chatMessage リソースの詳細については、chatMessage リソースの種類 [に関する記事を参照](/graph/api/resources/chatmessage) してください。</span><span class="sxs-lookup"><span data-stu-id="cff23-144">For more details on chatMessage resource, see the [chatMessage resource type](/graph/api/resources/chatmessage) article.</span></span>