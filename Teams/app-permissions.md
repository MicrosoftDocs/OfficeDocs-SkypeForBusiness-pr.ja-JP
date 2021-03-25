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
description: 管理者は、Microsoft Teams アプリが組織に要求しているデータとアクセス許可について説明します。
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
# <a name="microsoft-teams-apps-permissions-and-considerations"></a><span data-ttu-id="fc6f8-103">Microsoft Teams アプリのアクセス許可と考慮事項</span><span class="sxs-lookup"><span data-stu-id="fc6f8-103">Microsoft Teams apps permissions and considerations</span></span>

<span data-ttu-id="fc6f8-104">Microsoft Teams アプリは、インストール、アップグレード、アンインストールできる 1 つ以上の機能をアプリ パッケージに集約する方法です。 </span><span class="sxs-lookup"><span data-stu-id="fc6f8-104">Microsoft Teams apps are a way to aggregate one or more capabilities into an _app package_ that can be installed, upgraded, and uninstalled.</span></span> <span data-ttu-id="fc6f8-105">次のような機能があります。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-105">The capabilities include:</span></span>

- <span data-ttu-id="fc6f8-106">ボット</span><span class="sxs-lookup"><span data-stu-id="fc6f8-106">Bots</span></span>
- <span data-ttu-id="fc6f8-107">メッセージング拡張機能</span><span class="sxs-lookup"><span data-stu-id="fc6f8-107">Messaging extensions</span></span>
- <span data-ttu-id="fc6f8-108">タブ</span><span class="sxs-lookup"><span data-stu-id="fc6f8-108">Tabs</span></span>
- <span data-ttu-id="fc6f8-109">コネクタ</span><span class="sxs-lookup"><span data-stu-id="fc6f8-109">Connectors</span></span>

<span data-ttu-id="fc6f8-110">アプリはユーザーによって同意され、ポリシーの観点から IT によって管理されます。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-110">Apps are consented to by users and managed by IT from a policy perspective.</span></span> <span data-ttu-id="fc6f8-111">ただし、ほとんどの場合、アプリのアクセス許可とリスク プロファイルは、アプリに含まれる機能の権限とリスク プロファイルによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-111">However, for the most part, an app's permissions and risk profile are defined by the permissions and risk profiles of the capabilities that the app contains.</span></span> <span data-ttu-id="fc6f8-112">そのため、この記事では、機能レベルでのアクセス許可と考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-112">Therefore, this article focuses on permissions and considerations at the capability level.</span></span>

<span data-ttu-id="fc6f8-113">RECEIVE_MESSAGE や REPLYTO_MESSAGE など、大文字で次に示すアクセス許可は [、Microsoft Teams](/microsoftteams/platform/overview) の開発者ドキュメントや [Microsoft Graph](/graph/permissions-reference)のアクセス許可のどこにも表示されません。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-113">The permissions listed below in capital letters, for example RECEIVE_MESSAGE and REPLYTO_MESSAGE, don't appear anywhere in the [Microsoft Teams developer documentation](/microsoftteams/platform/overview) or the [permissions for Microsoft Graph](/graph/permissions-reference).</span></span> <span data-ttu-id="fc6f8-114">これらは、この記事の目的に関する簡単な説明です。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-114">They're simply a descriptive shorthand for the purpose of this article.</span></span>


| <span data-ttu-id="fc6f8-115">タイトル</span><span class="sxs-lookup"><span data-stu-id="fc6f8-115">Title</span></span>   | <span data-ttu-id="fc6f8-116">説明</span><span class="sxs-lookup"><span data-stu-id="fc6f8-116">Description</span></span>    |
|-----------|------------|
| ![判断ポイントを表すアイコン](media/audio_conferencing_image7.png) <br/><span data-ttu-id="fc6f8-118">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="fc6f8-118">Decision point</span></span>|<ul><li><span data-ttu-id="fc6f8-119">調査中のアプリが要求しているアクセス許可を理解するには、次の表をガイドとして使用します。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-119">Use the tables below as a guide to understand which permissions the apps you're investigating are requesting.</span></span></li></ul> |
| ![次の手順を示すアイコン](media/audio_conferencing_image9.png)<br/><span data-ttu-id="fc6f8-121">次の手順</span><span class="sxs-lookup"><span data-stu-id="fc6f8-121">Next step</span></span>|<ul><li><span data-ttu-id="fc6f8-122">アプリまたはサービス自体を調査して、組織内でアクセスを許可するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-122">Research the app or service itself to decide whether you want to allow access to it within your organization.</span></span> <span data-ttu-id="fc6f8-123">たとえば、ボットはユーザーからメッセージを送受信し、エンタープライズ カスタム ボットを除き、コンプライアンスの境界の外に配置されます。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-123">For example, bots send and receive messages from users, and—except for enterprise custom bots—they're located outside the compliance boundary.</span></span> <span data-ttu-id="fc6f8-124">そのため、ボットを含むアプリには、これらのアクセス許可が必要であり、少なくともそのリスク プロファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-124">Therefore, any app that includes a bot requires those permissions and has that risk profile, at a minimum.</span></span> </li></ul>|

<span data-ttu-id="fc6f8-125">「Microsoft [Teams タブのデバイスアクセス許可を要求する」も参照してください](/microsoftteams/platform/concepts/device-capabilities/native-device-permissions)。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-125">See also [Request device permissions for your Microsoft Teams tab](/microsoftteams/platform/concepts/device-capabilities/native-device-permissions).</span></span>

## <a name="global-app-permissions-and-considerations"></a><span data-ttu-id="fc6f8-126">グローバル アプリのアクセス許可と考慮事項</span><span class="sxs-lookup"><span data-stu-id="fc6f8-126">Global app permissions and considerations</span></span>

### <a name="required-permissions"></a><span data-ttu-id="fc6f8-127">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="fc6f8-127">Required permissions</span></span>

<span data-ttu-id="fc6f8-128">なし</span><span class="sxs-lookup"><span data-stu-id="fc6f8-128">None</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="fc6f8-129">オプションのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="fc6f8-129">Optional permissions</span></span>

<span data-ttu-id="fc6f8-130">なし</span><span class="sxs-lookup"><span data-stu-id="fc6f8-130">None</span></span>

### <a name="considerations"></a><span data-ttu-id="fc6f8-131">考慮事項</span><span class="sxs-lookup"><span data-stu-id="fc6f8-131">Considerations</span></span>

- <span data-ttu-id="fc6f8-132">アプリは、使用するデータと、その使用条件とプライバシー ポリシーのリンクでデータが使用される内容を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-132">An app must disclose what data it uses and what the data is used for in its terms of use and privacy policy links.</span></span>

- <span data-ttu-id="fc6f8-133">[リソース固有の同意では](resource-specific-consent.md) 、アプリが要求できる一連のアクセス許可が提供され、アプリのインストール画面に表示されます。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-133">[Resource-specific consent](resource-specific-consent.md) provides a set of permissions that apps can request, which appears on the installation screen of the app.</span></span> <span data-ttu-id="fc6f8-134">リソース固有の同意アクセス許可の詳細については、Graph のアクセス許可 [のリファレンスを参照してください](/graph/permissions-reference#teams-resource-specific-consent-permissions)。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-134">To learn more about resource-specific consent permissions, see [Graph permissions reference](/graph/permissions-reference#teams-resource-specific-consent-permissions).</span></span>

- <span data-ttu-id="fc6f8-135">また、アプリには、リソース固有の同意アクセス許可以外のアクセス許可が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-135">Apps may also need permissions other than resource-specific consent permissions.</span></span> <span data-ttu-id="fc6f8-136">アプリがインストールされた後、アプリは同意のプロンプトで Graph のアクセス許可を要求する場合があります。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-136">After an app is installed, the app may request Graph permissions through a consent prompt.</span></span> <span data-ttu-id="fc6f8-137">詳細については、「Azure とアプリケーションの同意 [のADを参照してください](/azure/active-directory/develop/application-consent-experience)。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-137">To learn more, see [Understanding Azure AD application consent experiences](/azure/active-directory/develop/application-consent-experience).</span></span> <span data-ttu-id="fc6f8-138">Azure Portal で API のアクセス許可と同意を構成できます。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-138">You can configure API permissions and consent in the Azure portal.</span></span> <span data-ttu-id="fc6f8-139">詳細については [、Azure Active Directory 同意フレームワークを参照してください](/azure/active-directory/develop/consent-framework)。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-139">To learn more, see [Azure Active Directory consent framework](/azure/active-directory/develop/consent-framework).</span></span>

## <a name="bots-and-messaging-extensions"></a><span data-ttu-id="fc6f8-140">ボットとメッセージング拡張機能</span><span class="sxs-lookup"><span data-stu-id="fc6f8-140">Bots and messaging extensions</span></span>

### <a name="required-permissions"></a><span data-ttu-id="fc6f8-141">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="fc6f8-141">Required permissions</span></span>

- <span data-ttu-id="fc6f8-142">RECEIVE_MESSAGE、REPLYTO_MESSAGE。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-142">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span></span> <span data-ttu-id="fc6f8-143">ボットはユーザーからのメッセージを受信して、返信することができます。<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="fc6f8-143">The bot can receive messages from users and reply to them.<sup>1</sup></span></span>

- <span data-ttu-id="fc6f8-144">POST_MESSAGE_USER。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-144">POST_MESSAGE_USER.</span></span> <span data-ttu-id="fc6f8-145">ユーザーがボットにメッセージを送信すると、ボットはユーザーのダイレクト メッセージ (いつでもプロアクティブ メッセージとも呼 *ばれる)* を送信できます。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-145">After a user has sent a message to a bot, the bot can send the user direct messages (also called *proactive messages* at any time.</span></span>

- <span data-ttu-id="fc6f8-146">GET_CHANNEL_LIST。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-146">GET_CHANNEL_LIST.</span></span> <span data-ttu-id="fc6f8-147">チームに追加されたボットは、チーム内のチャネルの名前と ID のリストを取得できます。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-147">Bots added to teams can get a list of names and IDs of the channels in a team.</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="fc6f8-148">オプションのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="fc6f8-148">Optional permissions</span></span>

- <span data-ttu-id="fc6f8-149">IDENTITY。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-149">IDENTITY.</span></span> <span data-ttu-id="fc6f8-150">チャネルで使用される場合、アプリのボットは、チーム メンバーの基本的な ID 情報 (名、名、ユーザー プリンシパル名 [UPN]、メール アドレス) にアクセスできます。ボットは、個人チャットまたはグループ チャットで使用される場合、それらのユーザーの同じ情報にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-150">When it's used in a channel, the app's bots can access basic identity information of team members (first name, last name, user principal name [UPN], email address); when it's used in a personal or group chat, the bot can access the same information for those users.</span></span>

- <span data-ttu-id="fc6f8-151">POST_MESSAGE_TEAM。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-151">POST_MESSAGE_TEAM.</span></span> <span data-ttu-id="fc6f8-152">ユーザーがボットと話したことがない場合でも、アプリのボットがチーム メンバーに直接 (積極的に) メッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-152">Allows an app's bots to send direct (proactive) messages to any team member at any time, even if the user has never talked to the bot before.</span></span>

- <span data-ttu-id="fc6f8-153">以下は明示的なアクセス許可ではありません。ただし、RECEIVE_MESSAGE と REPLYTO_MESSAGE およびボットを使用できる範囲 (マニフェストで宣言) によって暗黙的に示されています。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-153">The following are not explicit permissions, but are implied by RECEIVE_MESSAGE and REPLYTO_MESSAGE and the scopes into which the bots can be used, declared in the manifest:</span></span>
 
    - <span data-ttu-id="fc6f8-154">RECEIVE_MESSAGE_PERSONAL、REPLYTO_MESSAGE_PERSONAL</span><span class="sxs-lookup"><span data-stu-id="fc6f8-154">RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL</span></span>
    - <span data-ttu-id="fc6f8-155">RECEIVE_MESSAGE_GROUPCHAT、REPLYTO_MESSAGE_GROUPCHAT</span><span class="sxs-lookup"><span data-stu-id="fc6f8-155">RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT</span></span>
    - <span data-ttu-id="fc6f8-156">RECEIVE_MESSAGE_TEAM、REPLYTO_MESSAGE_TEAM</span><span class="sxs-lookup"><span data-stu-id="fc6f8-156">RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM</span></span>

- <span data-ttu-id="fc6f8-157">SEND_FILES、RECEIVE_FILES。<sup>2</sup> ボットが個人チャットでファイルを送受信できるかどうかを制御します (グループ チャットまたはチャネルではまだサポートされていません)。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-157">SEND_FILES, RECEIVE_FILES.<sup>2</sup> Controls whether a bot can send and receive files in personal chat (not yet supported for group chat or channels).</span></span>

### <a name="considerations"></a><span data-ttu-id="fc6f8-158">考慮事項</span><span class="sxs-lookup"><span data-stu-id="fc6f8-158">Considerations</span></span>

- <span data-ttu-id="fc6f8-159">ボットは、追加されたチーム、またはボットをインストールしたユーザーにのみアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-159">Bots only have access to teams to which they've been added or to users who have installed them.</span></span>

- <span data-ttu-id="fc6f8-160">ボットは、ユーザーが明示的に言及したメッセージのみを受信します。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-160">Bots only receive messages in which they're explicitly mentioned by users.</span></span> <span data-ttu-id="fc6f8-161">このデータは企業ネットワークから離れ、</span><span class="sxs-lookup"><span data-stu-id="fc6f8-161">This data leaves the corporate network.</span></span>

- <span data-ttu-id="fc6f8-162">ボットは、自分が言及されている会話にのみ返信できます。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-162">Bots can only reply to conversations in which they're mentioned.</span></span>

- <span data-ttu-id="fc6f8-163">ユーザーがボットと会話した後、ボットがユーザーの ID を保存している場合、いつでもそのユーザーのダイレクト メッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-163">After a user has conversed with a bot, if the bot stores that user's ID, it can send that user direct messages at any time.</span></span>

- <span data-ttu-id="fc6f8-164">理論上は、ボット メッセージにフィッシング詐欺サイトやマルウェア サイトへのリンクを含め込む可能性がありますが、ボットはユーザー、テナント管理者、または Microsoft がグローバルにブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-164">It is theoretically possible for bot messages to contain links to phishing or malware sites, but bots can be blocked by the user, the tenant admin, or globally by Microsoft.</span></span>

- <span data-ttu-id="fc6f8-165">ボットは、アプリが追加されたチーム メンバー、または個人またはグループ チャットの個々のユーザーに対して、非常に基本的な ID 情報を取得 (および保存できる場合があります) できます。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-165">A bot can retrieve (and might store) very basic identity information for the team members the app has been added to, or for individual users in personal or group chats.</span></span> <span data-ttu-id="fc6f8-166">これらのユーザーに関する詳細を取得するには、ボットが Azure Active Directory (Azure Active Directory) へのサインインを要求AD。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-166">To get further information about these users, the bot must require them to sign in to Azure Active Directory (Azure AD).</span></span>

- <span data-ttu-id="fc6f8-167">ボットはチーム内のチャネルのリストを取得 (および保存) できます。このデータは企業ネットワークから離れ、</span><span class="sxs-lookup"><span data-stu-id="fc6f8-167">Bots can retrieve (and might store) the list of channels in a team; this data leaves the corporate network.</span></span>

- <span data-ttu-id="fc6f8-168">ファイルがボットに送信された場合、ファイルは企業ネットワークから離れ、</span><span class="sxs-lookup"><span data-stu-id="fc6f8-168">When a file is sent to a bot, the file leaves the corporate network.</span></span> <span data-ttu-id="fc6f8-169">ファイルの送受信には、ファイルごとにユーザーの承認が必要です。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-169">Sending and receiving files requires user approval for each file.</span></span> 

- <span data-ttu-id="fc6f8-170">既定では、ボットにはユーザーの代わりに行動する機能が与えらされませんが、ボットはユーザーにサインインを要求できます。ユーザーがサインインするとすぐに、ボットはアクセス トークンを持ち、追加の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-170">By default, bots don't have the ability to act on behalf of the user, but bots can ask users to sign in; as soon as the user signs in, the bot will have an access token with which it can do additional things.</span></span> <span data-ttu-id="fc6f8-171">これらの追加の内容は、ボットとユーザーがサインインする場所によって正確に異なります。ボットは Azure AD アプリで登録され、独自のアクセス許可セットを持つ可能性があります https://apps.dev.microsoft.com/ 。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-171">Exactly what those additional things are depends on the bot and where the user signs in: a bot is an Azure AD app registered at https://apps.dev.microsoft.com/ and can have its own set of permissions.</span></span>

- <span data-ttu-id="fc6f8-172">ボットは、ユーザーがチームに追加またはチームから削除されるたびに通知されます。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-172">Bots are informed whenever users are added to or deleted from a team.</span></span>

- <span data-ttu-id="fc6f8-173">ボットには、ユーザーの IP アドレスや他の参照先情報は表示できません。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-173">Bots don't see users' IP addresses or other referrer information.</span></span> <span data-ttu-id="fc6f8-174">すべての情報は Microsoft から提供されます。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-174">All information comes from Microsoft.</span></span> <span data-ttu-id="fc6f8-175">(1 つの例外があります。ボットが独自のサインイン エクスペリエンスを実装している場合、サインイン UI にはユーザーの IP アドレスと参照先情報が表示されます)。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-175">(There is one exception: if a bot implements its own sign-in experience, the sign-in UI will see users' IP addresses and referrer information.)</span></span>

- <span data-ttu-id="fc6f8-176">一方、メッセージング拡張機能では、ユーザーの IP アドレスと参照元情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-176">Messaging extensions, on the other hand, do see users' IP addresses and referrer information.</span></span>

- <span data-ttu-id="fc6f8-177">アプリのガイドライン (および AppSource のレビュー プロセス) では、有効な目的のために (POST_MESSAGE_TEAM アクセス許可を使用して) 個人のチャット メッセージをユーザーに投稿する際に、任意の裁量が必要です。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-177">App guidelines (and our AppSource review process) require discretion in posting personal chat messages to users (via the POST_MESSAGE_TEAM permission) for valid purposes.</span></span> <span data-ttu-id="fc6f8-178">悪用が発生した場合、ユーザーはボットをブロックし、テナント管理者はアプリをブロックし、必要に応じて Microsoft がボットを一中心にブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-178">In the event of abuse, users can block the bot, tenant admins can block the app, and Microsoft can block bots centrally if necessary.</span></span>

<span data-ttu-id="fc6f8-179"><sup>1 一</sup> 部のボットはメッセージのみを送信します (POST_MESSAGE_USER)。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-179"><sup>1</sup> Some bots only send messages (POST_MESSAGE_USER).</span></span> <span data-ttu-id="fc6f8-180">ボットは "通知専用" ボットと呼ばれるが、この用語はボットが許可または許可されていない操作を参照しているのではなく、ボットが会話エクスペリエンスを公開したくないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-180">They're called "notification-only" bots, but the term doesn't refer to what a bot is allowed or not allowed to do, it means that the bot doesn't want to expose a conversational experience.</span></span> <span data-ttu-id="fc6f8-181">Teams では、通常は有効になる UI の機能を無効にするには、このフィールドを使用します。ボットは、会話エクスペリエンスを公開するボットと比べて、許可される操作に制限されません。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-181">Teams uses this field to disable functionality in the UI that would ordinarily be enabled; the bot isn't restricted in what it's allowed to do compared to bots that do expose a conversational experience.</span></span>

<span data-ttu-id="fc6f8-182"><sup>2</sup> アプリのファイル上のボット オブジェクトの supportsFiles Boolean manifest.jsによって制御されます。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-182"><sup>2</sup> Governed by the supportsFiles Boolean property on the bot object in the manifest.json file for the app.</span></span>

> [!NOTE]
> <span data-ttu-id="fc6f8-183">ボットが独自のサインインを持っている場合、ユーザーが初めてサインインする場合は、別の同意エクスペリエンスがあります。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-183">If a bot has its own sign-in, there's a second—different—consent experience the first time the user signs in.</span></span>
>
><span data-ttu-id="fc6f8-184">現時点では、Teams アプリ (ボット、タブ、コネクタ、メッセージング拡張機能) 内の任意の機能に関連付けられている Azure AD のアクセス許可は、ここに記載されている Teams のアクセス許可とは完全に分離されています。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-184">Currently, the Azure AD permissions associated with any of the capabilities inside a Teams app (bot, tab, connector, or messaging extension) are completely separate from the Teams permissions listed here.</span></span>

## <a name="tabs"></a><span data-ttu-id="fc6f8-185">タブ</span><span class="sxs-lookup"><span data-stu-id="fc6f8-185">Tabs</span></span>

<span data-ttu-id="fc6f8-186">タブは、Teams 内で実行されている Web サイトです。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-186">A tab is a website running inside Teams.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="fc6f8-187">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="fc6f8-187">Required permissions</span></span>

<span data-ttu-id="fc6f8-188">SEND_AND_RECEIVE_WEB_DATA</span><span class="sxs-lookup"><span data-stu-id="fc6f8-188">SEND_AND_RECEIVE_WEB_DATA</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="fc6f8-189">オプションのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="fc6f8-189">Optional permissions</span></span>

<span data-ttu-id="fc6f8-190">なし (現在)</span><span class="sxs-lookup"><span data-stu-id="fc6f8-190">None (currently)</span></span>

### <a name="considerations"></a><span data-ttu-id="fc6f8-191">考慮事項</span><span class="sxs-lookup"><span data-stu-id="fc6f8-191">Considerations</span></span>

- <span data-ttu-id="fc6f8-192">タブのリスク プロファイルは、ブラウザー タブで実行されている同じ Web サイトとほぼ同じです。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-192">The risk profile for a tab is almost identical to that same website running in a browser tab.</span></span> 

- <span data-ttu-id="fc6f8-193">タブには、現在のユーザーのサインイン名と UPN、現在のユーザーの Azure AD オブジェクト ID、存在する Microsoft 365 グループの ID (チームの場合)、テナント ID、ユーザーの現在のロケールなど、実行されているコンテキストも取得されます。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-193">A tab also gets the context in which it's running, including the sign-in name and UPN of the current user, the Azure AD Object ID for the current user, the ID of the Microsoft 365 Group in which it resides (if it's a team), the tenant ID, and the current locale of the user.</span></span> <span data-ttu-id="fc6f8-194">ただし、これらの ID をユーザーの情報にマップするには、タブでユーザーが Azure AD にサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-194">However, to map these IDs to a user's information, the tab would have to make the user sign in to Azure AD.</span></span>

## <a name="connectors"></a><span data-ttu-id="fc6f8-195">コネクタ</span><span class="sxs-lookup"><span data-stu-id="fc6f8-195">Connectors</span></span>

<span data-ttu-id="fc6f8-196">コネクタは、外部システムでイベントが発生した場合にメッセージをチャネルに投稿します。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-196">A connector posts messages to a channel when events in an external system occur.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="fc6f8-197">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="fc6f8-197">Required permissions</span></span>

<span data-ttu-id="fc6f8-198">POST_MESSAGE_CHANNEL</span><span class="sxs-lookup"><span data-stu-id="fc6f8-198">POST_MESSAGE_CHANNEL</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="fc6f8-199">オプションのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="fc6f8-199">Optional permissions</span></span>

<span data-ttu-id="fc6f8-200">REPLYTO_CONNECTOR_MESSAGE。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-200">REPLYTO_CONNECTOR_MESSAGE.</span></span> <span data-ttu-id="fc6f8-201">特定のコネクタは、GitHub の問題への応答を追加したり、Trello カードに日付を追加したりして、ユーザーがコネクタ メッセージに対象指定の返信を投稿できる、アクション可能なメッセージをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-201">Certain connectors support actionable messages, which allow users to post targeted replies to the connector message, for example by adding a response to a GitHub issue or adding a date to a Trello card.</span></span>

### <a name="considerations"></a><span data-ttu-id="fc6f8-202">考慮事項</span><span class="sxs-lookup"><span data-stu-id="fc6f8-202">Considerations</span></span>

- <span data-ttu-id="fc6f8-203">コネクタ メッセージを投稿するシステムは、メッセージを投稿しているユーザーやメッセージを受信したユーザーを知りません。受信者に関する情報は公開されません。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-203">The system that posts connector messages doesn't know who it's posting to or who receives the messages: no information about the recipient is disclosed.</span></span> <span data-ttu-id="fc6f8-204">(Microsoft はテナントではなく、実際の受信者です。Microsoft は、チャネルへの実際の投稿を行います)。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-204">(Microsoft is the actual recipient, not the tenant; Microsoft does the actual post to the channel.)</span></span>

- <span data-ttu-id="fc6f8-205">コネクタ メッセージがチャネルに投稿された場合、企業ネットワークからデータが削除されません。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-205">No data leaves the corporate network when connector messages are posted to a channel.</span></span>

- <span data-ttu-id="fc6f8-206">アクション可能なメッセージ (REPLYTO_CONNECTOR_MESSAGEアクセス許可) をサポートするコネクタには、IP アドレスと参照元の情報も表示されません。この情報は Microsoft に送信され、コネクタ ポータルで以前に Microsoft に登録された HTTP エンドポイントにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-206">Connectors that support actionable messages (REPLYTO_CONNECTOR_MESSAGE permission) also don't see IP address and referrer information; this information is sent to Microsoft and then routed to HTTP endpoints that were previously registered with Microsoft in the Connectors portal.</span></span>

- <span data-ttu-id="fc6f8-207">チャネルに対してコネクタが構成されるたび、そのコネクタ インスタンスの一意の URL が作成されます。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-207">Each time a connector is configured for a channel, a unique URL for that connector instance is created.</span></span> <span data-ttu-id="fc6f8-208">そのコネクタ インスタンスが削除された場合、URL は使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-208">If that connector instance is deleted, the URL can no longer be used.</span></span>

- <span data-ttu-id="fc6f8-209">コネクタ メッセージに添付ファイルを含めできません。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-209">Connector messages can't contain file attachments.</span></span>

- <span data-ttu-id="fc6f8-210">コネクタ インスタンスの URL は秘密/機密として扱う必要があります。その URL を持つすべてのユーザーは、メール アドレスのようにその URL に投稿できます。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-210">The connector instance URL should be treated as secret/confidential: anyone who has that URL can post to it, like an email address.</span></span> <span data-ttu-id="fc6f8-211">そのため、スパムやフィッシングやマルウェア サイトへのリンクが発生するリスクがあります。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-211">Therefore, there's some risk of spam or links to phishing or malware sites.</span></span> <span data-ttu-id="fc6f8-212">その場合、チーム所有者はコネクタ インスタンスを削除できます。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-212">If that were to happen, team owners can delete the connector instance.</span></span>

- <span data-ttu-id="fc6f8-213">コネクタ メッセージを送信するサービスが侵害され、スパム/フィッシング詐欺/マルウェア リンクの送信を開始した場合、テナント管理者は新しいコネクタ インスタンスの作成を防止し、Microsoft がそれらを一本的にブロックできます。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-213">If the service that sends connector messages were to become compromised and start sending spam/phishing/malware links, a tenant administrator can prevent new connector instances from being created and Microsoft can block them centrally.</span></span>

> [!NOTE]
> <span data-ttu-id="fc6f8-214">現在のところ、どのコネクタがアクション可能なメッセージ (アクセス許可を持つ) をサポートREPLYTO_CONNECTOR_MESSAGEできません。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-214">It's not currently possible to know which connectors support actionable messages (REPLYTO_CONNECTOR_MESSAGE permission).</span></span>

## <a name="outgoing-webhooks"></a><span data-ttu-id="fc6f8-215">送信 Webhooks</span><span class="sxs-lookup"><span data-stu-id="fc6f8-215">Outgoing webhooks</span></span>

<span data-ttu-id="fc6f8-216">*送信 Webhook は* 、チームの所有者またはチーム メンバーがその他の方法で作成します。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-216">*Outgoing webhooks* are created on the fly by team owners or team members.</span></span> <span data-ttu-id="fc6f8-217">Teams アプリの機能ではない。この情報は、完了のために含まれています。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-217">They aren't capabilities of Teams apps; this information is included for completeness.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="fc6f8-218">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="fc6f8-218">Required permissions</span></span>

<span data-ttu-id="fc6f8-219">RECEIVE_MESSAGE、REPLYTO_MESSAGE。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-219">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span></span> <span data-ttu-id="fc6f8-220">ユーザーからのメッセージを受信して返信できます。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-220">Can receive messages from users and reply to them.</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="fc6f8-221">オプションのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="fc6f8-221">Optional permissions</span></span>

<span data-ttu-id="fc6f8-222">なし</span><span class="sxs-lookup"><span data-stu-id="fc6f8-222">None</span></span>

### <a name="considerations"></a><span data-ttu-id="fc6f8-223">考慮事項</span><span class="sxs-lookup"><span data-stu-id="fc6f8-223">Considerations</span></span>

- <span data-ttu-id="fc6f8-224">送信 Webhook はボットに似ていますが、権限は少なめです。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-224">Outgoing webhooks are similar to bots but have fewer privileges.</span></span> <span data-ttu-id="fc6f8-225">ボットと同様に、明示的に言及する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-225">They must be explicitly mentioned, just like bots.</span></span>

- <span data-ttu-id="fc6f8-226">送信 Webhook が登録されると、秘密情報が生成されます。これにより、送信 Webhook は悪意のある攻撃者とは対照的に、送信者が Microsoft Teams である確認を行います。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-226">When an outgoing webhook is registered, a secret is generated, which allows the outgoing webhook to verify that the sender is Microsoft Teams as opposed to a malicious attacker.</span></span> <span data-ttu-id="fc6f8-227">この秘密は秘密のままです。アクセス権を持つユーザーは誰でも Microsoft Teams を偽装できます。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-227">This secret should remain a secret; anyone who has access to it can impersonate Microsoft Teams.</span></span> <span data-ttu-id="fc6f8-228">シークレットが侵害された場合、送信 Webhook を削除して再び作成すると、新しいシークレットが生成されます。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-228">If the secret is compromised, the outgoing webhook can be deleted and re-created, and a new secret will be generated.</span></span>

- <span data-ttu-id="fc6f8-229">秘密を検証しない送信 Webhook を作成することができますが、その場合はお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-229">Although it's possible to create an outgoing webhook that doesn't validate the secret, we recommend against it.</span></span>

- <span data-ttu-id="fc6f8-230">送信 Webhook は、メッセージの送受信以外に、メッセージを積極的に送信できない、ファイルを送受信できない、ボットが実行できるその他の操作 (メッセージの受信と返信を除く) など、多くのことを行えません。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-230">Other than receiving and replying to messages, outgoing webhooks can't do much: they can't proactively send messages, they can't send or receive files, they can't do anything else that bots can do except receive and reply to messages.</span></span>