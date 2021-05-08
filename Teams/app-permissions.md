---
title: Microsoft Teams アプリのアクセス許可と考慮事項
author: rmw2890
ms.author: rowille
manager: serdars
ms.date: 06/27/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
ms.reviewer: rowille
description: 管理者は、アプリが組織に要求Microsoft Teamsデータとアクセス許可を確認できます。
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ae050080814afe12ce2ba791c6b68058d5e4bc58
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120859"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a><span data-ttu-id="b779d-103">Microsoft Teams アプリのアクセス許可と考慮事項</span><span class="sxs-lookup"><span data-stu-id="b779d-103">Microsoft Teams apps permissions and considerations</span></span>

<span data-ttu-id="b779d-104">Microsoft Teamsは、1 つ以上の機能を、インストール、アップグレード、アンインストールできるアプリ パッケージに集約する方法です。</span><span class="sxs-lookup"><span data-stu-id="b779d-104">Microsoft Teams apps are a way to aggregate one or more capabilities into an _app package_ that can be installed, upgraded, and uninstalled.</span></span> <span data-ttu-id="b779d-105">機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b779d-105">The capabilities include:</span></span>

- <span data-ttu-id="b779d-106">ボット</span><span class="sxs-lookup"><span data-stu-id="b779d-106">Bots</span></span>
- <span data-ttu-id="b779d-107">メッセージング拡張機能</span><span class="sxs-lookup"><span data-stu-id="b779d-107">Messaging extensions</span></span>
- <span data-ttu-id="b779d-108">タブ</span><span class="sxs-lookup"><span data-stu-id="b779d-108">Tabs</span></span>
- <span data-ttu-id="b779d-109">コネクタ</span><span class="sxs-lookup"><span data-stu-id="b779d-109">Connectors</span></span>

<span data-ttu-id="b779d-110">アプリはユーザーによって同意され、ポリシーの観点から IT によって管理されます。</span><span class="sxs-lookup"><span data-stu-id="b779d-110">Apps are consented to by users and managed by IT from a policy perspective.</span></span> <span data-ttu-id="b779d-111">ただし、ほとんどの場合、アプリのアクセス許可とリスク プロファイルは、アプリに含まれる機能のアクセス許可とリスク プロファイルによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="b779d-111">However, for the most part, an app's permissions and risk profile are defined by the permissions and risk profiles of the capabilities that the app contains.</span></span> <span data-ttu-id="b779d-112">そのため、この記事では、機能レベルでのアクセス許可と考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="b779d-112">Therefore, this article focuses on permissions and considerations at the capability level.</span></span>

<span data-ttu-id="b779d-113">以下に示すアクセス許可 (RECEIVE_MESSAGE や REPLYTO_MESSAGE など) は[、Microsoft Teams](/microsoftteams/platform/overview)開発者向けドキュメントや[Microsoft](/graph/permissions-reference)Graph のアクセス許可のどこにも表示されません。</span><span class="sxs-lookup"><span data-stu-id="b779d-113">The permissions listed below in capital letters, for example RECEIVE_MESSAGE and REPLYTO_MESSAGE, don't appear anywhere in the [Microsoft Teams developer documentation](/microsoftteams/platform/overview) or the [permissions for Microsoft Graph](/graph/permissions-reference).</span></span> <span data-ttu-id="b779d-114">これは、この記事の目的に関する簡単な説明です。</span><span class="sxs-lookup"><span data-stu-id="b779d-114">They're simply a descriptive shorthand for the purpose of this article.</span></span>


| <span data-ttu-id="b779d-115">タイトル</span><span class="sxs-lookup"><span data-stu-id="b779d-115">Title</span></span>   | <span data-ttu-id="b779d-116">説明</span><span class="sxs-lookup"><span data-stu-id="b779d-116">Description</span></span>    |
|-----------|------------|
| ![判断ポイントを表すアイコン](media/audio_conferencing_image7.png) <br/><span data-ttu-id="b779d-118">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="b779d-118">Decision point</span></span>|<ul><li><span data-ttu-id="b779d-119">調査中のアプリが要求しているアクセス許可を理解するには、次の表をガイドとして使用します。</span><span class="sxs-lookup"><span data-stu-id="b779d-119">Use the tables below as a guide to understand which permissions the apps you're investigating are requesting.</span></span></li></ul> |
| ![次の手順を示すアイコン](media/audio_conferencing_image9.png)<br/><span data-ttu-id="b779d-121">次の手順</span><span class="sxs-lookup"><span data-stu-id="b779d-121">Next step</span></span>|<ul><li><span data-ttu-id="b779d-122">アプリまたはサービス自体を調査して、組織内でアクセスを許可するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="b779d-122">Research the app or service itself to decide whether you want to allow access to it within your organization.</span></span> <span data-ttu-id="b779d-123">たとえば、ボットはユーザーからのメッセージを送受信します。エンタープライズ カスタム ボットを除き、ボットはコンプライアンスの境界の外に配置されます。</span><span class="sxs-lookup"><span data-stu-id="b779d-123">For example, bots send and receive messages from users, and—except for enterprise custom bots—they're located outside the compliance boundary.</span></span> <span data-ttu-id="b779d-124">そのため、ボットを含むすべてのアプリでは、これらのアクセス許可が必要であり、少なくともそのリスク プロファイルを持っています。</span><span class="sxs-lookup"><span data-stu-id="b779d-124">Therefore, any app that includes a bot requires those permissions and has that risk profile, at a minimum.</span></span> </li></ul>|

<span data-ttu-id="b779d-125">「デバイスの[アクセス許可を要求する」タブもMicrosoft Teamsしてください](/microsoftteams/platform/concepts/device-capabilities/native-device-permissions)。</span><span class="sxs-lookup"><span data-stu-id="b779d-125">See also [Request device permissions for your Microsoft Teams tab](/microsoftteams/platform/concepts/device-capabilities/native-device-permissions).</span></span>

## <a name="global-app-permissions-and-considerations"></a><span data-ttu-id="b779d-126">グローバル アプリのアクセス許可と考慮事項</span><span class="sxs-lookup"><span data-stu-id="b779d-126">Global app permissions and considerations</span></span>

### <a name="required-permissions"></a><span data-ttu-id="b779d-127">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="b779d-127">Required permissions</span></span>

<span data-ttu-id="b779d-128">なし</span><span class="sxs-lookup"><span data-stu-id="b779d-128">None</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="b779d-129">オプションのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="b779d-129">Optional permissions</span></span>

<span data-ttu-id="b779d-130">なし</span><span class="sxs-lookup"><span data-stu-id="b779d-130">None</span></span>

### <a name="considerations"></a><span data-ttu-id="b779d-131">考慮事項</span><span class="sxs-lookup"><span data-stu-id="b779d-131">Considerations</span></span>

- <span data-ttu-id="b779d-132">アプリは、使用するデータと、その使用条件とプライバシー ポリシーのリンクでデータが使用されるデータを開示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b779d-132">An app must disclose what data it uses and what the data is used for in its terms of use and privacy policy links.</span></span>

- <span data-ttu-id="b779d-133">[リソース固有の同意は](resource-specific-consent.md) 、アプリが要求できる一連のアクセス許可を提供します。このアクセス許可は、アプリのインストール画面に表示されます。</span><span class="sxs-lookup"><span data-stu-id="b779d-133">[Resource-specific consent](resource-specific-consent.md) provides a set of permissions that apps can request, which appears on the installation screen of the app.</span></span> <span data-ttu-id="b779d-134">リソース固有の同意アクセス許可の詳細については、「アクセス許可の参照Graph[参照してください](/graph/permissions-reference#teams-resource-specific-consent-permissions)。</span><span class="sxs-lookup"><span data-stu-id="b779d-134">To learn more about resource-specific consent permissions, see [Graph permissions reference](/graph/permissions-reference#teams-resource-specific-consent-permissions).</span></span>

- <span data-ttu-id="b779d-135">アプリには、リソース固有の同意アクセス許可以外のアクセス許可が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="b779d-135">Apps may also need permissions other than resource-specific consent permissions.</span></span> <span data-ttu-id="b779d-136">アプリがインストールされた後、アプリは同意プロンプトをGraphアクセス許可を要求できます。</span><span class="sxs-lookup"><span data-stu-id="b779d-136">After an app is installed, the app may request Graph permissions through a consent prompt.</span></span> <span data-ttu-id="b779d-137">詳細については、「アプリケーションの同意エクスペリエンス [について」AD参照してください](/azure/active-directory/develop/application-consent-experience)。</span><span class="sxs-lookup"><span data-stu-id="b779d-137">To learn more, see [Understanding Azure AD application consent experiences](/azure/active-directory/develop/application-consent-experience).</span></span> <span data-ttu-id="b779d-138">API のアクセス許可と同意は、Azure Portal で構成できます。</span><span class="sxs-lookup"><span data-stu-id="b779d-138">You can configure API permissions and consent in the Azure portal.</span></span> <span data-ttu-id="b779d-139">詳細については、「同意フレームワーク[のAzure Active Directory参照してください](/azure/active-directory/develop/consent-framework)。</span><span class="sxs-lookup"><span data-stu-id="b779d-139">To learn more, see [Azure Active Directory consent framework](/azure/active-directory/develop/consent-framework).</span></span>

## <a name="bots-and-messaging-extensions"></a><span data-ttu-id="b779d-140">ボットとメッセージング拡張機能</span><span class="sxs-lookup"><span data-stu-id="b779d-140">Bots and messaging extensions</span></span>

### <a name="required-permissions"></a><span data-ttu-id="b779d-141">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="b779d-141">Required permissions</span></span>

- <span data-ttu-id="b779d-142">RECEIVE_MESSAGE、REPLYTO_MESSAGE。</span><span class="sxs-lookup"><span data-stu-id="b779d-142">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span></span> <span data-ttu-id="b779d-143">ボットは、ユーザーからメッセージを受信して返信できます。<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b779d-143">The bot can receive messages from users and reply to them.<sup>1</sup></span></span>

- <span data-ttu-id="b779d-144">POST_MESSAGE_USER。</span><span class="sxs-lookup"><span data-stu-id="b779d-144">POST_MESSAGE_USER.</span></span> <span data-ttu-id="b779d-145">ユーザーがボットにメッセージを送信すると、ボットはユーザーダイレクト メッセージ (プロアクティブ メッセージとも呼ばれる) *をいつでも* 送信できます。</span><span class="sxs-lookup"><span data-stu-id="b779d-145">After a user has sent a message to a bot, the bot can send the user direct messages (also called *proactive messages* at any time.</span></span>

- <span data-ttu-id="b779d-146">GET_CHANNEL_LIST。</span><span class="sxs-lookup"><span data-stu-id="b779d-146">GET_CHANNEL_LIST.</span></span> <span data-ttu-id="b779d-147">チームに追加されたボットは、チーム内のチャネルの名前と ID の一覧を取得できます。</span><span class="sxs-lookup"><span data-stu-id="b779d-147">Bots added to teams can get a list of names and IDs of the channels in a team.</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="b779d-148">オプションのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="b779d-148">Optional permissions</span></span>

- <span data-ttu-id="b779d-149">IDENTITY。</span><span class="sxs-lookup"><span data-stu-id="b779d-149">IDENTITY.</span></span> <span data-ttu-id="b779d-150">チャネルで使用すると、アプリのボットは、チーム メンバーの基本的な ID 情報 (名、名、ユーザー プリンシパル名 [UPN]、電子メール アドレス) にアクセスできます。個人チャットまたはグループ チャットで使用されている場合、ボットはそれらのユーザーに対して同じ情報にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b779d-150">When it's used in a channel, the app's bots can access basic identity information of team members (first name, last name, user principal name [UPN], email address); when it's used in a personal or group chat, the bot can access the same information for those users.</span></span>

- <span data-ttu-id="b779d-151">POST_MESSAGE_TEAM。</span><span class="sxs-lookup"><span data-stu-id="b779d-151">POST_MESSAGE_TEAM.</span></span> <span data-ttu-id="b779d-152">ユーザーがボットと話したことがない場合でも、アプリのボットがいつでも任意のチーム メンバーに直接 (プロアクティブ) メッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="b779d-152">Allows an app's bots to send direct (proactive) messages to any team member at any time, even if the user has never talked to the bot before.</span></span>

- <span data-ttu-id="b779d-153">明示的なアクセス許可は次のとおりですが、RECEIVE_MESSAGE と REPLYTO_MESSAGE とボットを使用できるスコープ (マニフェストで宣言) によって暗黙的に示されます。</span><span class="sxs-lookup"><span data-stu-id="b779d-153">The following are not explicit permissions, but are implied by RECEIVE_MESSAGE and REPLYTO_MESSAGE and the scopes into which the bots can be used, declared in the manifest:</span></span>
 
    - <span data-ttu-id="b779d-154">RECEIVE_MESSAGE_PERSONAL、REPLYTO_MESSAGE_PERSONAL</span><span class="sxs-lookup"><span data-stu-id="b779d-154">RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL</span></span>
    - <span data-ttu-id="b779d-155">RECEIVE_MESSAGE_GROUPCHAT、REPLYTO_MESSAGE_GROUPCHAT</span><span class="sxs-lookup"><span data-stu-id="b779d-155">RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT</span></span>
    - <span data-ttu-id="b779d-156">RECEIVE_MESSAGE_TEAM、REPLYTO_MESSAGE_TEAM</span><span class="sxs-lookup"><span data-stu-id="b779d-156">RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM</span></span>

- <span data-ttu-id="b779d-157">SEND_FILES、RECEIVE_FILES。<sup>2</sup> ボットが個人チャットでファイルを送受信できるかどうかを制御します (グループ チャットまたはチャネルではまだサポートされていません)。</span><span class="sxs-lookup"><span data-stu-id="b779d-157">SEND_FILES, RECEIVE_FILES.<sup>2</sup> Controls whether a bot can send and receive files in personal chat (not yet supported for group chat or channels).</span></span>

### <a name="considerations"></a><span data-ttu-id="b779d-158">考慮事項</span><span class="sxs-lookup"><span data-stu-id="b779d-158">Considerations</span></span>

- <span data-ttu-id="b779d-159">ボットは、追加されたチーム、またはボットをインストールしたユーザーにのみアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b779d-159">Bots only have access to teams to which they've been added or to users who have installed them.</span></span>

- <span data-ttu-id="b779d-160">ボットは、ユーザーによって明示的に言及されたメッセージのみを受信します。</span><span class="sxs-lookup"><span data-stu-id="b779d-160">Bots only receive messages in which they're explicitly mentioned by users.</span></span> <span data-ttu-id="b779d-161">このデータは、企業ネットワークから出て行く。</span><span class="sxs-lookup"><span data-stu-id="b779d-161">This data leaves the corporate network.</span></span>

- <span data-ttu-id="b779d-162">ボットは、自分が言及されている会話にのみ返信できます。</span><span class="sxs-lookup"><span data-stu-id="b779d-162">Bots can only reply to conversations in which they're mentioned.</span></span>

- <span data-ttu-id="b779d-163">ユーザーがボットと会話した後、ボットがユーザーの ID を格納している場合は、いつでもそのユーザーのダイレクト メッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="b779d-163">After a user has conversed with a bot, if the bot stores that user's ID, it can send that user direct messages at any time.</span></span>

- <span data-ttu-id="b779d-164">ボット メッセージにフィッシング詐欺サイトまたはマルウェア サイトへのリンクを含め、理論上は可能ですが、ボットはユーザー、テナント管理者、または Microsoft によってグローバルにブロックできます。</span><span class="sxs-lookup"><span data-stu-id="b779d-164">It is theoretically possible for bot messages to contain links to phishing or malware sites, but bots can be blocked by the user, the tenant admin, or globally by Microsoft.</span></span>

- <span data-ttu-id="b779d-165">ボットは、アプリが追加されたチーム メンバー、または個人チャットまたはグループ チャットの個々のユーザーの非常に基本的な ID 情報を取得 (および保存する可能性があります) できます。</span><span class="sxs-lookup"><span data-stu-id="b779d-165">A bot can retrieve (and might store) very basic identity information for the team members the app has been added to, or for individual users in personal or group chats.</span></span> <span data-ttu-id="b779d-166">これらのユーザーに関する詳細な情報を取得するには、ボットがユーザーにサインインを要求する必要があります (AD Azure Azure Active Directory)。</span><span class="sxs-lookup"><span data-stu-id="b779d-166">To get further information about these users, the bot must require them to sign in to Azure Active Directory (Azure AD).</span></span>

- <span data-ttu-id="b779d-167">ボットは、チーム内のチャネルの一覧を取得 (および格納できる場合があります) できます。このデータは企業ネットワークから出て行く。</span><span class="sxs-lookup"><span data-stu-id="b779d-167">Bots can retrieve (and might store) the list of channels in a team; this data leaves the corporate network.</span></span>

- <span data-ttu-id="b779d-168">ファイルがボットに送信された場合、ファイルは企業ネットワークから出て行く。</span><span class="sxs-lookup"><span data-stu-id="b779d-168">When a file is sent to a bot, the file leaves the corporate network.</span></span> <span data-ttu-id="b779d-169">ファイルの送受信には、ファイルごとにユーザーの承認が必要です。</span><span class="sxs-lookup"><span data-stu-id="b779d-169">Sending and receiving files requires user approval for each file.</span></span> 

- <span data-ttu-id="b779d-170">既定では、ボットはユーザーに代わって行動する機能を持つ必要がありますが、ボットはユーザーにサインインを要求できます。ユーザーがサインインするとすぐに、ボットはアクセス トークンを持ち、追加の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="b779d-170">By default, bots don't have the ability to act on behalf of the user, but bots can ask users to sign in; as soon as the user signs in, the bot will have an access token with which it can do additional things.</span></span> <span data-ttu-id="b779d-171">これらの追加の内容は、ボットとユーザーのサインイン場所によって正確に異なります。ボットはに登録されている Azure AD アプリであり、独自のアクセス許可セットを持つ可能性 https://apps.dev.microsoft.com/ があります。</span><span class="sxs-lookup"><span data-stu-id="b779d-171">Exactly what those additional things are depends on the bot and where the user signs in: a bot is an Azure AD app registered at https://apps.dev.microsoft.com/ and can have its own set of permissions.</span></span>

- <span data-ttu-id="b779d-172">ボットは、ユーザーがチームに追加またはチームから削除されるたびに通知されます。</span><span class="sxs-lookup"><span data-stu-id="b779d-172">Bots are informed whenever users are added to or deleted from a team.</span></span>

- <span data-ttu-id="b779d-173">ボットは、ユーザーの IP アドレスや他の参照元情報を表示しません。</span><span class="sxs-lookup"><span data-stu-id="b779d-173">Bots don't see users' IP addresses or other referrer information.</span></span> <span data-ttu-id="b779d-174">すべての情報は Microsoft から提供されます。</span><span class="sxs-lookup"><span data-stu-id="b779d-174">All information comes from Microsoft.</span></span> <span data-ttu-id="b779d-175">(1 つの例外があります。ボットが独自のサインイン エクスペリエンスを実装している場合、サインイン UI にはユーザーの IP アドレスと参照元情報が表示されます)。</span><span class="sxs-lookup"><span data-stu-id="b779d-175">(There is one exception: if a bot implements its own sign-in experience, the sign-in UI will see users' IP addresses and referrer information.)</span></span>

- <span data-ttu-id="b779d-176">一方、メッセージング拡張機能には、ユーザーの IP アドレスと参照元情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b779d-176">Messaging extensions, on the other hand, do see users' IP addresses and referrer information.</span></span>

- <span data-ttu-id="b779d-177">アプリ のガイドライン (および AppSource レビュー プロセス) では、有効な目的のために(POST_MESSAGE_TEAM アクセス許可を使用して) 個人のチャット メッセージをユーザーに投稿する際に判断する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b779d-177">App guidelines (and our AppSource review process) require discretion in posting personal chat messages to users (via the POST_MESSAGE_TEAM permission) for valid purposes.</span></span> <span data-ttu-id="b779d-178">不正使用が発生した場合、ユーザーはボットをブロックし、テナント管理者はアプリをブロックできます。また、必要に応じて Microsoft がボットを一中心にブロックできます。</span><span class="sxs-lookup"><span data-stu-id="b779d-178">In the event of abuse, users can block the bot, tenant admins can block the app, and Microsoft can block bots centrally if necessary.</span></span>

<span data-ttu-id="b779d-179"><sup>1 一</sup> 部のボットはメッセージのみを送信します (POST_MESSAGE_USER)。</span><span class="sxs-lookup"><span data-stu-id="b779d-179"><sup>1</sup> Some bots only send messages (POST_MESSAGE_USER).</span></span> <span data-ttu-id="b779d-180">これらは "通知のみ" ボットと呼ばれるが、この用語はボットが許可または許可されていない操作を参照しているのではなく、ボットが会話エクスペリエンスを公開したくないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="b779d-180">They're called "notification-only" bots, but the term doesn't refer to what a bot is allowed or not allowed to do, it means that the bot doesn't want to expose a conversational experience.</span></span> <span data-ttu-id="b779d-181">Teamsこのフィールドを使用して、通常は有効になる UI の機能を無効にします。会話エクスペリエンスを公開するボットに比べて、ボットの実行が許可される操作は制限されません。</span><span class="sxs-lookup"><span data-stu-id="b779d-181">Teams uses this field to disable functionality in the UI that would ordinarily be enabled; the bot isn't restricted in what it's allowed to do compared to bots that do expose a conversational experience.</span></span>

<span data-ttu-id="b779d-182"><sup>2</sup> アプリのファイルに基manifest.jsボット オブジェクトの supportsFiles ブールプロパティによって管理されます。</span><span class="sxs-lookup"><span data-stu-id="b779d-182"><sup>2</sup> Governed by the supportsFiles Boolean property on the bot object in the manifest.json file for the app.</span></span>

> [!NOTE]
> <span data-ttu-id="b779d-183">ボットに独自のサインインがある場合、ユーザーが初めてサインインする場合は、2 つ目の異なる同意エクスペリエンスがあります。</span><span class="sxs-lookup"><span data-stu-id="b779d-183">If a bot has its own sign-in, there's a second—different—consent experience the first time the user signs in.</span></span>
>
><span data-ttu-id="b779d-184">現時点では、Teams アプリ (ボット、タブ、コネクタ、またはメッセージング拡張機能) 内の機能に関連付けられている Azure AD のアクセス許可は、ここに示されている Teams アクセス許可とは完全に分離されています。</span><span class="sxs-lookup"><span data-stu-id="b779d-184">Currently, the Azure AD permissions associated with any of the capabilities inside a Teams app (bot, tab, connector, or messaging extension) are completely separate from the Teams permissions listed here.</span></span>

## <a name="tabs"></a><span data-ttu-id="b779d-185">タブ</span><span class="sxs-lookup"><span data-stu-id="b779d-185">Tabs</span></span>

<span data-ttu-id="b779d-186">タブは、Web サイト内で実行Teams。</span><span class="sxs-lookup"><span data-stu-id="b779d-186">A tab is a website running inside Teams.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="b779d-187">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="b779d-187">Required permissions</span></span>

<span data-ttu-id="b779d-188">SEND_AND_RECEIVE_WEB_DATA</span><span class="sxs-lookup"><span data-stu-id="b779d-188">SEND_AND_RECEIVE_WEB_DATA</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="b779d-189">オプションのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="b779d-189">Optional permissions</span></span>

<span data-ttu-id="b779d-190">なし (現在)</span><span class="sxs-lookup"><span data-stu-id="b779d-190">None (currently)</span></span>

### <a name="considerations"></a><span data-ttu-id="b779d-191">考慮事項</span><span class="sxs-lookup"><span data-stu-id="b779d-191">Considerations</span></span>

- <span data-ttu-id="b779d-192">タブのリスク プロファイルは、ブラウザー タブで実行されている同じ Web サイトとほぼ同じです。</span><span class="sxs-lookup"><span data-stu-id="b779d-192">The risk profile for a tab is almost identical to that same website running in a browser tab.</span></span> 

- <span data-ttu-id="b779d-193">タブには、現在のユーザーのサインイン名と UPN、現在のユーザーの Azure AD オブジェクト ID、それが存在する Microsoft 365 グループの ID (チームの場合)、テナント ID、ユーザーの現在のロケールなど、実行されているコンテキストも取得されます。</span><span class="sxs-lookup"><span data-stu-id="b779d-193">A tab also gets the context in which it's running, including the sign-in name and UPN of the current user, the Azure AD Object ID for the current user, the ID of the Microsoft 365 Group in which it resides (if it's a team), the tenant ID, and the current locale of the user.</span></span> <span data-ttu-id="b779d-194">ただし、これらの ID をユーザーの情報にマップするには、タブでユーザーが Azure アカウントにサインインAD。</span><span class="sxs-lookup"><span data-stu-id="b779d-194">However, to map these IDs to a user's information, the tab would have to make the user sign in to Azure AD.</span></span>

## <a name="connectors"></a><span data-ttu-id="b779d-195">コネクタ</span><span class="sxs-lookup"><span data-stu-id="b779d-195">Connectors</span></span>

<span data-ttu-id="b779d-196">外部システムのイベントが発生すると、コネクタはチャネルにメッセージを投稿します。</span><span class="sxs-lookup"><span data-stu-id="b779d-196">A connector posts messages to a channel when events in an external system occur.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="b779d-197">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="b779d-197">Required permissions</span></span>

<span data-ttu-id="b779d-198">POST_MESSAGE_CHANNEL</span><span class="sxs-lookup"><span data-stu-id="b779d-198">POST_MESSAGE_CHANNEL</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="b779d-199">オプションのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="b779d-199">Optional permissions</span></span>

<span data-ttu-id="b779d-200">REPLYTO_CONNECTOR_MESSAGE。</span><span class="sxs-lookup"><span data-stu-id="b779d-200">REPLYTO_CONNECTOR_MESSAGE.</span></span> <span data-ttu-id="b779d-201">特定のコネクタでは、アクション可能なメッセージがサポートされています。このメッセージを使用すると、GitHub の問題に応答を追加したり、Trello カードに日付を追加したりして、ユーザーはコネクタ メッセージに対して対象指定の応答を投稿できます。</span><span class="sxs-lookup"><span data-stu-id="b779d-201">Certain connectors support actionable messages, which allow users to post targeted replies to the connector message, for example by adding a response to a GitHub issue or adding a date to a Trello card.</span></span>

### <a name="considerations"></a><span data-ttu-id="b779d-202">考慮事項</span><span class="sxs-lookup"><span data-stu-id="b779d-202">Considerations</span></span>

- <span data-ttu-id="b779d-203">コネクタ メッセージを投稿するシステムは、メッセージを投稿しているユーザーまたはメッセージを受信したユーザーを知りません。受信者に関する情報は開示されません。</span><span class="sxs-lookup"><span data-stu-id="b779d-203">The system that posts connector messages doesn't know who it's posting to or who receives the messages: no information about the recipient is disclosed.</span></span> <span data-ttu-id="b779d-204">(Microsoft はテナントではなく、実際の受信者です。Microsoft は、チャネルへの実際の投稿を行います)。</span><span class="sxs-lookup"><span data-stu-id="b779d-204">(Microsoft is the actual recipient, not the tenant; Microsoft does the actual post to the channel.)</span></span>

- <span data-ttu-id="b779d-205">コネクタ メッセージがチャネルに投稿された場合、企業ネットワークからデータが送信されません。</span><span class="sxs-lookup"><span data-stu-id="b779d-205">No data leaves the corporate network when connector messages are posted to a channel.</span></span>

- <span data-ttu-id="b779d-206">アクション可能なメッセージ (REPLYTO_CONNECTOR_MESSAGE) をサポートするコネクタには、IP アドレスと参照元情報も表示されません。この情報は Microsoft に送信され、コネクタ ポータルで以前に Microsoft に登録された HTTP エンドポイントにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="b779d-206">Connectors that support actionable messages (REPLYTO_CONNECTOR_MESSAGE permission) also don't see IP address and referrer information; this information is sent to Microsoft and then routed to HTTP endpoints that were previously registered with Microsoft in the Connectors portal.</span></span>

- <span data-ttu-id="b779d-207">チャネルに対してコネクタが構成されるたび、そのコネクタ インスタンスの一意の URL が作成されます。</span><span class="sxs-lookup"><span data-stu-id="b779d-207">Each time a connector is configured for a channel, a unique URL for that connector instance is created.</span></span> <span data-ttu-id="b779d-208">そのコネクタ インスタンスが削除された場合、URL は使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="b779d-208">If that connector instance is deleted, the URL can no longer be used.</span></span>

- <span data-ttu-id="b779d-209">コネクタ メッセージには添付ファイルを含めできません。</span><span class="sxs-lookup"><span data-stu-id="b779d-209">Connector messages can't contain file attachments.</span></span>

- <span data-ttu-id="b779d-210">コネクタ インスタンスの URL はシークレット/機密として扱う必要があります。その URL を持つすべてのユーザーは、電子メール アドレスのようにその URL に投稿できます。</span><span class="sxs-lookup"><span data-stu-id="b779d-210">The connector instance URL should be treated as secret/confidential: anyone who has that URL can post to it, like an email address.</span></span> <span data-ttu-id="b779d-211">そのため、スパムやフィッシングサイトやマルウェア サイトへのリンクが発生するリスクがあります。</span><span class="sxs-lookup"><span data-stu-id="b779d-211">Therefore, there's some risk of spam or links to phishing or malware sites.</span></span> <span data-ttu-id="b779d-212">その場合、チーム所有者はコネクタ インスタンスを削除できます。</span><span class="sxs-lookup"><span data-stu-id="b779d-212">If that were to happen, team owners can delete the connector instance.</span></span>

- <span data-ttu-id="b779d-213">コネクタ メッセージを送信するサービスが侵害され、スパム/フィッシング/マルウェア リンクの送信が開始された場合、テナント管理者は新しいコネクタ インスタンスの作成を妨げる可能性があります。また、Microsoft はそれらを一本的にブロックできます。</span><span class="sxs-lookup"><span data-stu-id="b779d-213">If the service that sends connector messages were to become compromised and start sending spam/phishing/malware links, a tenant administrator can prevent new connector instances from being created and Microsoft can block them centrally.</span></span>

> [!NOTE]
> <span data-ttu-id="b779d-214">現在、アクション可能なメッセージをサポートしているコネクタを確認することはできません (REPLYTO_CONNECTOR_MESSAGEアクセス許可)。</span><span class="sxs-lookup"><span data-stu-id="b779d-214">It's not currently possible to know which connectors support actionable messages (REPLYTO_CONNECTOR_MESSAGE permission).</span></span>

## <a name="outgoing-webhooks"></a><span data-ttu-id="b779d-215">送信 webhook</span><span class="sxs-lookup"><span data-stu-id="b779d-215">Outgoing webhooks</span></span>

<span data-ttu-id="b779d-216">*送信 webhook は* 、チーム所有者またはチーム メンバーによって、その他の方法で作成されます。</span><span class="sxs-lookup"><span data-stu-id="b779d-216">*Outgoing webhooks* are created on the fly by team owners or team members.</span></span> <span data-ttu-id="b779d-217">これらは、アプリのTeams機能ではない。この情報は完全に含まれています。</span><span class="sxs-lookup"><span data-stu-id="b779d-217">They aren't capabilities of Teams apps; this information is included for completeness.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="b779d-218">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="b779d-218">Required permissions</span></span>

<span data-ttu-id="b779d-219">RECEIVE_MESSAGE、REPLYTO_MESSAGE。</span><span class="sxs-lookup"><span data-stu-id="b779d-219">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span></span> <span data-ttu-id="b779d-220">ユーザーからメッセージを受信して返信できます。</span><span class="sxs-lookup"><span data-stu-id="b779d-220">Can receive messages from users and reply to them.</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="b779d-221">オプションのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="b779d-221">Optional permissions</span></span>

<span data-ttu-id="b779d-222">なし</span><span class="sxs-lookup"><span data-stu-id="b779d-222">None</span></span>

### <a name="considerations"></a><span data-ttu-id="b779d-223">考慮事項</span><span class="sxs-lookup"><span data-stu-id="b779d-223">Considerations</span></span>

- <span data-ttu-id="b779d-224">送信 webhook はボットに似ていますが、権限は少なめです。</span><span class="sxs-lookup"><span data-stu-id="b779d-224">Outgoing webhooks are similar to bots but have fewer privileges.</span></span> <span data-ttu-id="b779d-225">ボットと同様に、明示的に言及する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b779d-225">They must be explicitly mentioned, just like bots.</span></span>

- <span data-ttu-id="b779d-226">送信 Webhook が登録されると、シークレットが生成されます。これにより、送信 webhook は、悪意のある攻撃者ではなく、送信者がMicrosoft Teamsを確認できます。</span><span class="sxs-lookup"><span data-stu-id="b779d-226">When an outgoing webhook is registered, a secret is generated, which allows the outgoing webhook to verify that the sender is Microsoft Teams as opposed to a malicious attacker.</span></span> <span data-ttu-id="b779d-227">このシークレットはシークレットのままである必要があります。アクセス権を持つユーザーは、ユーザーを偽装Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="b779d-227">This secret should remain a secret; anyone who has access to it can impersonate Microsoft Teams.</span></span> <span data-ttu-id="b779d-228">シークレットが侵害された場合、送信 webhook を削除して再作成し、新しいシークレットが生成されます。</span><span class="sxs-lookup"><span data-stu-id="b779d-228">If the secret is compromised, the outgoing webhook can be deleted and re-created, and a new secret will be generated.</span></span>

- <span data-ttu-id="b779d-229">シークレットを検証しない送信 webhook を作成することができますが、その場合は、その Webhook に対して実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b779d-229">Although it's possible to create an outgoing webhook that doesn't validate the secret, we recommend against it.</span></span>

- <span data-ttu-id="b779d-230">メッセージの送受信以外に、送信 Webhook は多くのことを行えません。メッセージを事前に送信できない、ファイルを送受信できない、ボットが実行できる他の操作は、メッセージの受信と返信を除いて実行できます。</span><span class="sxs-lookup"><span data-stu-id="b779d-230">Other than receiving and replying to messages, outgoing webhooks can't do much: they can't proactively send messages, they can't send or receive files, they can't do anything else that bots can do except receive and reply to messages.</span></span>