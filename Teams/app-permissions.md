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
description: 管理者は、Microsoft Teams アプリが組織から要求しているデータと権限について学習できます。
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e12509f8a8b2bf43b98cb7c0dba387aa1e92383b
ms.sourcegitcommit: 682566e51a9e5f0fc65540535c7dcdcbd38e04c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "45429369"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a><span data-ttu-id="99f62-103">Microsoft Teams アプリのアクセス許可と考慮事項</span><span class="sxs-lookup"><span data-stu-id="99f62-103">Microsoft Teams apps permissions and considerations</span></span>

<span data-ttu-id="99f62-104">Microsoft Teams アプリは、1つ以上の機能をインストール、アップグレード、アンインストールできる_アプリパッケージ_に集約するための手段です。</span><span class="sxs-lookup"><span data-stu-id="99f62-104">Microsoft Teams apps are a way to aggregate one or more capabilities into an _app package_ that can be installed, upgraded, and uninstalled.</span></span> <span data-ttu-id="99f62-105">次のような機能があります。</span><span class="sxs-lookup"><span data-stu-id="99f62-105">The capabilities include:</span></span>

- <span data-ttu-id="99f62-106">ボット</span><span class="sxs-lookup"><span data-stu-id="99f62-106">Bots</span></span>
- <span data-ttu-id="99f62-107">メッセージングの拡張機能</span><span class="sxs-lookup"><span data-stu-id="99f62-107">Messaging extensions</span></span>
- <span data-ttu-id="99f62-108">タブ</span><span class="sxs-lookup"><span data-stu-id="99f62-108">Tabs</span></span>
- <span data-ttu-id="99f62-109">コネクタ</span><span class="sxs-lookup"><span data-stu-id="99f62-109">Connectors</span></span>

<span data-ttu-id="99f62-110">アプリはユーザーによって各人され、ポリシーの観点から管理されます。</span><span class="sxs-lookup"><span data-stu-id="99f62-110">Apps are consented to by users and managed by IT from a policy perspective.</span></span> <span data-ttu-id="99f62-111">ただし、ほとんどの場合、アプリのアクセス許可とリスクプロファイルは、アプリに含まれる機能の権限とリスクのプロファイルによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="99f62-111">However, for the most part, an app's permissions and risk profile are defined by the permissions and risk profiles of the capabilities that the app contains.</span></span> <span data-ttu-id="99f62-112">したがって、この記事では、権限とその機能レベルに関する考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="99f62-112">Therefore, this article focuses on permissions and considerations at the capability level.</span></span>

<span data-ttu-id="99f62-113">RECEIVE_MESSAGE や REPLYTO_MESSAGE などの大文字で示されているアクセス許可は、 [Microsoft Teams の開発者向けドキュメント](https://aka.ms/teamsdevdocs)または[microsoft Graph のアクセス許可](https://developer.microsoft.com/graph/docs/concepts/permissions_reference)のいずれかには表示されません。</span><span class="sxs-lookup"><span data-stu-id="99f62-113">The permissions listed below in capital letters, for example RECEIVE_MESSAGE and REPLYTO_MESSAGE, don't appear anywhere in the [Microsoft Teams developer documentation](https://aka.ms/teamsdevdocs) or the [permissions for Microsoft Graph](https://developer.microsoft.com/graph/docs/concepts/permissions_reference).</span></span> <span data-ttu-id="99f62-114">これらは、この記事の目的について簡単に説明しています。</span><span class="sxs-lookup"><span data-stu-id="99f62-114">They're simply a descriptive shorthand for the purpose of this article.</span></span>


|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](media/audio_conferencing_image7.png) <br/><span data-ttu-id="99f62-116">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="99f62-116">Decision point</span></span>|<ul><li><span data-ttu-id="99f62-117">次の表を参考にして、調査しているアプリで要求されているアクセス許可について理解してください。</span><span class="sxs-lookup"><span data-stu-id="99f62-117">Use the tables below as a guide to understand which permissions the apps you're investigating are requesting.</span></span></li></ul> |
| ![次の手順を示すアイコン](media/audio_conferencing_image9.png)<br/><span data-ttu-id="99f62-119">次の手順</span><span class="sxs-lookup"><span data-stu-id="99f62-119">Next step</span></span>|<ul><li><span data-ttu-id="99f62-120">アプリまたはサービス自体を調査して、組織内でのアクセスを許可するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="99f62-120">Research the app or service itself to decide whether you want to allow access to it within your organization.</span></span> <span data-ttu-id="99f62-121">たとえば、ボットはユーザーからのメッセージを送受信します。また、エンタープライズカスタムボット以外は、コンプライアンスの境界外にあります。</span><span class="sxs-lookup"><span data-stu-id="99f62-121">For example, bots send and receive messages from users, and—except for enterprise custom bots—they're located outside the compliance boundary.</span></span> <span data-ttu-id="99f62-122">そのため、bot を含むすべてのアプリには、これらのアクセス許可が必要であり、少なくともそのリスクのプロファイルが設定されています。</span><span class="sxs-lookup"><span data-stu-id="99f62-122">Therefore, any app that includes a bot requires those permissions and has that risk profile, at a minimum.</span></span> </li></ul>|

## <a name="global-app-permissions-and-considerations"></a><span data-ttu-id="99f62-123">グローバルアプリのアクセス許可と考慮事項</span><span class="sxs-lookup"><span data-stu-id="99f62-123">Global app permissions and considerations</span></span>

### <a name="required-permissions"></a><span data-ttu-id="99f62-124">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="99f62-124">Required permissions</span></span>

<span data-ttu-id="99f62-125">なし</span><span class="sxs-lookup"><span data-stu-id="99f62-125">None</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="99f62-126">オプションの権限</span><span class="sxs-lookup"><span data-stu-id="99f62-126">Optional permissions</span></span>

<span data-ttu-id="99f62-127">なし</span><span class="sxs-lookup"><span data-stu-id="99f62-127">None</span></span>

### <a name="considerations"></a><span data-ttu-id="99f62-128">考慮事項</span><span class="sxs-lookup"><span data-stu-id="99f62-128">Considerations</span></span>

- <span data-ttu-id="99f62-129">アプリは、使用するデータと、利用規約およびプライバシーポリシーへのリンクでデータがどのように使用されているかを公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99f62-129">An app must disclose what data it uses and what the data is used for in its terms of use and privacy policy links.</span></span>

- <span data-ttu-id="99f62-130">[リソース固有の同意](resource-specific-consent.md)は、アプリのインストール画面に表示される、アプリが要求できる一連のアクセス許可を提供します。</span><span class="sxs-lookup"><span data-stu-id="99f62-130">[Resource-specific consent](resource-specific-consent.md) provides a set of permissions that apps can request, which appears on the installation screen of the app.</span></span> <span data-ttu-id="99f62-131">リソース固有の同意権限の詳細については、「 [Graph 権限リファレンス](https://docs.microsoft.com/graph/permissions-reference#teams-resource-specific-consent-permissions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99f62-131">To learn more about resource-specific consent permissions, see [Graph permissions reference](https://docs.microsoft.com/graph/permissions-reference#teams-resource-specific-consent-permissions).</span></span>

- <span data-ttu-id="99f62-132">アプリでは、リソース固有の同意権限以外の権限が必要になる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="99f62-132">Apps may also need permissions other than resource-specific consent permissions.</span></span> <span data-ttu-id="99f62-133">アプリがインストールされると、アプリは同意プロンプトを通じてグラフのアクセス許可を要求できます。</span><span class="sxs-lookup"><span data-stu-id="99f62-133">After an app is installed, the app may request Graph permissions through a consent prompt.</span></span> <span data-ttu-id="99f62-134">詳細については、「 [AZURE AD アプリケーションの同意のエクスペリエンスについ](https://docs.microsoft.com/azure/active-directory/develop/application-consent-experience)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99f62-134">To learn more, see [Understanding Azure AD application consent experiences](https://docs.microsoft.com/azure/active-directory/develop/application-consent-experience).</span></span> <span data-ttu-id="99f62-135">Azure ポータルで API の権限と承認を構成できます。</span><span class="sxs-lookup"><span data-stu-id="99f62-135">You can configure API permissions and consent in the Azure portal.</span></span> <span data-ttu-id="99f62-136">詳細については、「 [Azure Active Directory の承認フレームワーク](https://docs.microsoft.com/azure/active-directory/develop/consent-framework)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99f62-136">To learn more, see [Azure Active Directory consent framework](https://docs.microsoft.com/azure/active-directory/develop/consent-framework).</span></span>

## <a name="bots-and-messaging-extensions"></a><span data-ttu-id="99f62-137">ボットとメッセージングの拡張機能</span><span class="sxs-lookup"><span data-stu-id="99f62-137">Bots and messaging extensions</span></span>

### <a name="required-permissions"></a><span data-ttu-id="99f62-138">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="99f62-138">Required permissions</span></span>

- <span data-ttu-id="99f62-139">RECEIVE_MESSAGE、REPLYTO_MESSAGE。</span><span class="sxs-lookup"><span data-stu-id="99f62-139">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span></span> <span data-ttu-id="99f62-140">ボットは、ユーザーからのメッセージを受信して返信することができます。<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="99f62-140">The bot can receive messages from users and reply to them.<sup>1</sup></span></span>

- <span data-ttu-id="99f62-141">POST_MESSAGE_USER。</span><span class="sxs-lookup"><span data-stu-id="99f62-141">POST_MESSAGE_USER.</span></span> <span data-ttu-id="99f62-142">ユーザーがボットにメッセージを送信した後、ボットはユーザーのダイレクトメッセージ (*予防的なメッセージ*とも呼ばれます) をいつでも送信できます。</span><span class="sxs-lookup"><span data-stu-id="99f62-142">After a user has sent a message to a bot, the bot can send the user direct messages (also called *proactive messages* at any time.</span></span>

- <span data-ttu-id="99f62-143">GET_CHANNEL_LIST。</span><span class="sxs-lookup"><span data-stu-id="99f62-143">GET_CHANNEL_LIST.</span></span> <span data-ttu-id="99f62-144">Teams に追加されたボットは、チーム内のチャネルの名前と Id の一覧を取得できます。</span><span class="sxs-lookup"><span data-stu-id="99f62-144">Bots added to teams can get a list of names and IDs of the channels in a team.</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="99f62-145">オプションの権限</span><span class="sxs-lookup"><span data-stu-id="99f62-145">Optional permissions</span></span>

- <span data-ttu-id="99f62-146">身分.</span><span class="sxs-lookup"><span data-stu-id="99f62-146">IDENTITY.</span></span> <span data-ttu-id="99f62-147">チャネルで使用されている場合、アプリのボットは、チームメンバー (名、姓、ユーザープリンシパル名 [UPN]、メールアドレス) の基本的な id 情報にアクセスできます。個人またはグループチャットで使用されている場合、bot は、それらのユーザーに対して同じ情報にアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="99f62-147">When it's used in a channel, the app's bots can access basic identity information of team members (first name, last name, user principal name [UPN], email address); when it's used in a personal or group chat, the bot can access the same information for those users.</span></span>

- <span data-ttu-id="99f62-148">POST_MESSAGE_TEAM。</span><span class="sxs-lookup"><span data-stu-id="99f62-148">POST_MESSAGE_TEAM.</span></span> <span data-ttu-id="99f62-149">ユーザーが以前に bot に話したことがない場合でも、アプリのボットが、任意の時点で任意のチームメンバーに対して直接 (予防的) メッセージを送信することを許可します。</span><span class="sxs-lookup"><span data-stu-id="99f62-149">Allows an app's bots to send direct (proactive) messages to any team member at any time, even if the user has never talked to the bot before.</span></span>

- <span data-ttu-id="99f62-150">次のようなアクセス許可は明示的ではありませんが、マニフェストで宣言された RECEIVE_MESSAGE と REPLYTO_MESSAGE と、ボットを使うことができるスコープによって暗黙的に指定されています。</span><span class="sxs-lookup"><span data-stu-id="99f62-150">The following are not explicit permissions, but are implied by RECEIVE_MESSAGE and REPLYTO_MESSAGE and the scopes into which the bots can be used, declared in the manifest:</span></span>
 
    - <span data-ttu-id="99f62-151">RECEIVE_MESSAGE_PERSONAL、REPLYTO_MESSAGE_PERSONAL</span><span class="sxs-lookup"><span data-stu-id="99f62-151">RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL</span></span>
    - <span data-ttu-id="99f62-152">RECEIVE_MESSAGE_GROUPCHAT、REPLYTO_MESSAGE_GROUPCHAT</span><span class="sxs-lookup"><span data-stu-id="99f62-152">RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT</span></span>
    - <span data-ttu-id="99f62-153">RECEIVE_MESSAGE_TEAM、REPLYTO_MESSAGE_TEAM</span><span class="sxs-lookup"><span data-stu-id="99f62-153">RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM</span></span>

- <span data-ttu-id="99f62-154">SEND_FILES、RECEIVE_FILES。<sup>2</sup> bot が個人的なチャットでファイルを送受信できるかどうかを制御します (グループチャットまたはチャネルではまだサポートされていません)。</span><span class="sxs-lookup"><span data-stu-id="99f62-154">SEND_FILES, RECEIVE_FILES.<sup>2</sup> Controls whether a bot can send and receive files in personal chat (not yet supported for group chat or channels).</span></span>

### <a name="considerations"></a><span data-ttu-id="99f62-155">考慮事項</span><span class="sxs-lookup"><span data-stu-id="99f62-155">Considerations</span></span>

- <span data-ttu-id="99f62-156">ボットは、それらが追加されたチーム、またはインストールしたユーザーにのみアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="99f62-156">Bots only have access to teams to which they've been added or to users who have installed them.</span></span>

- <span data-ttu-id="99f62-157">ボットは、ユーザーによって明示的にメンションされたメッセージのみを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="99f62-157">Bots only receive messages in which they're explicitly mentioned by users.</span></span> <span data-ttu-id="99f62-158">このデータは企業ネットワークから離れています。</span><span class="sxs-lookup"><span data-stu-id="99f62-158">This data leaves the corporate network.</span></span>

- <span data-ttu-id="99f62-159">ボットは、メンションされた会話にのみ返信できます。</span><span class="sxs-lookup"><span data-stu-id="99f62-159">Bots can only reply to conversations in which they're mentioned.</span></span>

- <span data-ttu-id="99f62-160">ユーザーがボットを使用している場合、ボットにそのユーザーの ID が保存されている場合は、いつでもそのユーザーのダイレクトメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="99f62-160">After a user has conversed with a bot, if the bot stores that user's ID, it can send that user direct messages at any time.</span></span>

- <span data-ttu-id="99f62-161">ボットメッセージには、フィッシングまたはマルウェアサイトへのリンクが含まれていても、ユーザー、テナント管理者、または Microsoft によってグローバルにブロックされている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="99f62-161">It is theoretically possible for bot messages to contain links to phishing or malware sites, but bots can be blocked by the user, the tenant admin, or globally by Microsoft.</span></span>

- <span data-ttu-id="99f62-162">Bot は、アプリが追加されたチームメンバー、または個人またはグループチャットの個々のユーザーに対して、非常に基本的な id 情報を取得 (および保存する可能性があります) することができます。</span><span class="sxs-lookup"><span data-stu-id="99f62-162">A bot can retrieve (and might store) very basic identity information for the team members the app has been added to, or for individual users in personal or group chats.</span></span> <span data-ttu-id="99f62-163">これらのユーザーについての詳細情報を入手するには、ボットが Azure Active Directory (Azure AD) にサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="99f62-163">To get further information about these users, the bot must require them to sign in to Azure Active Directory (Azure AD).</span></span>

- <span data-ttu-id="99f62-164">Bot は、チーム内のチャネルの一覧を取得 (および保存する可能性があります) することができます。このデータは企業ネットワークから離れています。</span><span class="sxs-lookup"><span data-stu-id="99f62-164">Bots can retrieve (and might store) the list of channels in a team; this data leaves the corporate network.</span></span>

- <span data-ttu-id="99f62-165">ボットにファイルが送信されると、ファイルは企業ネットワークから脱退します。</span><span class="sxs-lookup"><span data-stu-id="99f62-165">When a file is sent to a bot, the file leaves the corporate network.</span></span> <span data-ttu-id="99f62-166">ファイルを送受信するには、各ファイルに対してユーザーの承認が必要です。</span><span class="sxs-lookup"><span data-stu-id="99f62-166">Sending and receiving files requires user approval for each file.</span></span> 

- <span data-ttu-id="99f62-167">既定では、bot はユーザーの代わりに操作することはできませんが、ユーザーにサインインを求めることができます。ユーザーがサインインするとすぐに、ボットには追加の項目を実行できるアクセストークンがあります。</span><span class="sxs-lookup"><span data-stu-id="99f62-167">By default, bots don't have the ability to act on behalf of the user, but bots can ask users to sign in; as soon as the user signs in, the bot will have an access token with which it can do additional things.</span></span> <span data-ttu-id="99f62-168">このような追加事項は、ボットとユーザがサインインする場所によって異なります。ボットは、に登録されている Azure AD アプリで https://apps.dev.microsoft.com/ あり、独自の権限を設定できます。</span><span class="sxs-lookup"><span data-stu-id="99f62-168">Exactly what those additional things are depends on the bot and where the user signs in: a bot is an Azure AD app registered at https://apps.dev.microsoft.com/ and can have its own set of permissions.</span></span>

- <span data-ttu-id="99f62-169">ユーザーがチームに追加または削除されるたびに、ボットに通知されます。</span><span class="sxs-lookup"><span data-stu-id="99f62-169">Bots are informed whenever users are added to or deleted from a team.</span></span>

- <span data-ttu-id="99f62-170">ユーザーの IP アドレスまたはその他の参照情報は表示されません。</span><span class="sxs-lookup"><span data-stu-id="99f62-170">Bots don't see users' IP addresses or other referrer information.</span></span> <span data-ttu-id="99f62-171">すべての情報は Microsoft から取得されます。</span><span class="sxs-lookup"><span data-stu-id="99f62-171">All information comes from Microsoft.</span></span> <span data-ttu-id="99f62-172">(例外は1つしかありません。ボットが独自のサインインエクスペリエンスを実装している場合、サインイン UI にユーザーの IP アドレスと参照元情報が表示されます)。</span><span class="sxs-lookup"><span data-stu-id="99f62-172">(There is one exception: if a bot implements its own sign-in experience, the sign-in UI will see users' IP addresses and referrer information.)</span></span>

- <span data-ttu-id="99f62-173">メッセージングの内線番号には、ユーザーの IP アドレスと参照元情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="99f62-173">Messaging extensions, on the other hand, do see users' IP addresses and referrer information.</span></span>

- <span data-ttu-id="99f62-174">アプリのガイドライン (およびその AppSource review プロセス) では、有効な目的のために、ユーザーに (POST_MESSAGE_TEAM アクセス許可を使用して) 個人のチャットメッセージを送信するための判断が必要です。</span><span class="sxs-lookup"><span data-stu-id="99f62-174">App guidelines (and our AppSource review process) require discretion in posting personal chat messages to users (via the POST_MESSAGE_TEAM permission) for valid purposes.</span></span> <span data-ttu-id="99f62-175">不正使用の場合は、ユーザーがボットをブロックできるため、テナント管理者はアプリをブロックすることができます。また、必要に応じて、ボットを一元的にブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="99f62-175">In the event of abuse, users can block the bot, tenant admins can block the app, and Microsoft can block bots centrally if necessary.</span></span>

<span data-ttu-id="99f62-176"><sup>1</sup>一部のボットはメッセージのみを送信します (POST_MESSAGE_USER)。</span><span class="sxs-lookup"><span data-stu-id="99f62-176"><sup>1</sup> Some bots only send messages (POST_MESSAGE_USER).</span></span> <span data-ttu-id="99f62-177">"通知のみ" と呼ばれますが、ボットが許可されているものや、許可されていないものを指しているわけではないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="99f62-177">They're called "notification-only" bots, but the term doesn't refer to what a bot is allowed or not allowed to do, it means that the bot doesn't want to expose a conversational experience.</span></span> <span data-ttu-id="99f62-178">このフィールドは、通常は有効になる UI の機能を無効にするために使用されます。このボットは、会話体験を公開しているボットと比較した場合に制限されていません。</span><span class="sxs-lookup"><span data-stu-id="99f62-178">Teams uses this field to disable functionality in the UI that would ordinarily be enabled; the bot isn't restricted in what it's allowed to do compared to bots that do expose a conversational experience.</span></span>

<span data-ttu-id="99f62-179"><sup>2</sup>アプリの manifest.jsファイルの bot オブジェクトの Supportsfiles ブールプロパティによって制御されます。</span><span class="sxs-lookup"><span data-stu-id="99f62-179"><sup>2</sup> Governed by the supportsFiles Boolean property on the bot object in the manifest.json file for the app.</span></span>

> [!NOTE]
> <span data-ttu-id="99f62-180">ボットに独自のサインインがある場合は、ユーザーが初めてサインインするときに、2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="99f62-180">If a bot has its own sign-in, there's a second—different—consent experience the first time the user signs in.</span></span>
>
><span data-ttu-id="99f62-181">現時点では、Teams アプリ内のいずれかの機能に関連付けられた Azure AD 権限 (ボット、タブ、コネクタ、またはメッセージング拡張機能) は、ここに記載されている Teams の権限から完全に分離されます。</span><span class="sxs-lookup"><span data-stu-id="99f62-181">Currently, the Azure AD permissions associated with any of the capabilities inside a Teams app (bot, tab, connector, or messaging extension) are completely separate from the Teams permissions listed here.</span></span>

## <a name="tabs"></a><span data-ttu-id="99f62-182">タブ</span><span class="sxs-lookup"><span data-stu-id="99f62-182">Tabs</span></span>

<span data-ttu-id="99f62-183">タブは、Teams 内で実行されている web サイトです。</span><span class="sxs-lookup"><span data-stu-id="99f62-183">A tab is a website running inside Teams.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="99f62-184">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="99f62-184">Required permissions</span></span>

<span data-ttu-id="99f62-185">SEND_AND_RECEIVE_WEB_DATA</span><span class="sxs-lookup"><span data-stu-id="99f62-185">SEND_AND_RECEIVE_WEB_DATA</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="99f62-186">オプションの権限</span><span class="sxs-lookup"><span data-stu-id="99f62-186">Optional permissions</span></span>

<span data-ttu-id="99f62-187">なし (現在)</span><span class="sxs-lookup"><span data-stu-id="99f62-187">None (currently)</span></span>

### <a name="considerations"></a><span data-ttu-id="99f62-188">考慮事項</span><span class="sxs-lookup"><span data-stu-id="99f62-188">Considerations</span></span>

- <span data-ttu-id="99f62-189">タブのリスクプロファイルは、ブラウザータブで実行されている同じ web サイトとほぼ同じです。</span><span class="sxs-lookup"><span data-stu-id="99f62-189">The risk profile for a tab is almost identical to that same website running in a browser tab.</span></span> 

- <span data-ttu-id="99f62-190">また、タブには、現在のユーザーのサインイン名と UPN、現在のユーザーの Azure AD オブジェクト ID、所属する Microsoft 365 グループの ID (チームの場合)、テナント ID、ユーザーの現在のロケールなど、タブで実行されているコンテキストが取得されます。</span><span class="sxs-lookup"><span data-stu-id="99f62-190">A tab also gets the context in which it's running, including the sign-in name and UPN of the current user, the Azure AD Object ID for the current user, the ID of the Microsoft 365 Group in which it resides (if it's a team), the tenant ID, and the current locale of the user.</span></span> <span data-ttu-id="99f62-191">ただし、これらの Id をユーザーの情報に対応付けるには、ユーザーが Azure AD にサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="99f62-191">However, to map these IDs to a user's information, the tab would have to make the user sign in to Azure AD.</span></span>

## <a name="connectors"></a><span data-ttu-id="99f62-192">コネクタ</span><span class="sxs-lookup"><span data-stu-id="99f62-192">Connectors</span></span>

<span data-ttu-id="99f62-193">外部システムのイベントが発生すると、コネクタはチャネルにメッセージを投稿します。</span><span class="sxs-lookup"><span data-stu-id="99f62-193">A connector posts messages to a channel when events in an external system occur.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="99f62-194">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="99f62-194">Required permissions</span></span>

<span data-ttu-id="99f62-195">POST_MESSAGE_CHANNEL</span><span class="sxs-lookup"><span data-stu-id="99f62-195">POST_MESSAGE_CHANNEL</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="99f62-196">オプションの権限</span><span class="sxs-lookup"><span data-stu-id="99f62-196">Optional permissions</span></span>

<span data-ttu-id="99f62-197">REPLYTO_CONNECTOR_MESSAGE。</span><span class="sxs-lookup"><span data-stu-id="99f62-197">REPLYTO_CONNECTOR_MESSAGE.</span></span> <span data-ttu-id="99f62-198">一部のコネクタは、操作可能なメッセージをサポートします。これにより、ユーザーは GitHub の問題への応答の追加や、Trello カードへの日付の追加などを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="99f62-198">Certain connectors support actionable messages, which allow users to post targeted replies to the connector message, for example by adding a response to a GitHub issue or adding a date to a Trello card.</span></span>

### <a name="considerations"></a><span data-ttu-id="99f62-199">考慮事項</span><span class="sxs-lookup"><span data-stu-id="99f62-199">Considerations</span></span>

- <span data-ttu-id="99f62-200">コネクタメッセージを投稿するシステムでは、メッセージの投稿先または受信者がわからない場合、受信者に関する情報は公開されません。</span><span class="sxs-lookup"><span data-stu-id="99f62-200">The system that posts connector messages doesn't know who it's posting to or who receives the messages: no information about the recipient is disclosed.</span></span> <span data-ttu-id="99f62-201">(Microsoft は、テナントではなく実際の受信者です。Microsoft はチャネルに実際に投稿します。)</span><span class="sxs-lookup"><span data-stu-id="99f62-201">(Microsoft is the actual recipient, not the tenant; Microsoft does the actual post to the channel.)</span></span>

- <span data-ttu-id="99f62-202">コネクタメッセージがチャネルに投稿されると、データは企業ネットワークから脱退します。</span><span class="sxs-lookup"><span data-stu-id="99f62-202">No data leaves the corporate network when connector messages are posted to a channel.</span></span>

- <span data-ttu-id="99f62-203">操作できるメッセージ (REPLYTO_CONNECTOR_MESSAGE アクセス許可) をサポートするコネクタにも、IP アドレスと参照情報は表示されません。この情報は、Microsoft に送信され、connector ポータルで Microsoft に以前登録されていた HTTP エンドポイントにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="99f62-203">Connectors that support actionable messages (REPLYTO_CONNECTOR_MESSAGE permission) also don't see IP address and referrer information; this information is sent to Microsoft and then routed to HTTP endpoints that were previously registered with Microsoft in the Connectors portal.</span></span>

- <span data-ttu-id="99f62-204">チャネル用にコネクタを構成するたびに、そのコネクタインスタンスの一意の URL が作成されます。</span><span class="sxs-lookup"><span data-stu-id="99f62-204">Each time a connector is configured for a channel, a unique URL for that connector instance is created.</span></span> <span data-ttu-id="99f62-205">このコネクタインスタンスが削除されると、URL を使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="99f62-205">If that connector instance is deleted, the URL can no longer be used.</span></span>

- <span data-ttu-id="99f62-206">コネクタメッセージに添付ファイルを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="99f62-206">Connector messages can't contain file attachments.</span></span>

- <span data-ttu-id="99f62-207">コネクタインスタンス URL は、秘密/機密として扱う必要があります。この URL は、メールアドレスなど、その URL を持つすべてのユーザーが投稿できます。</span><span class="sxs-lookup"><span data-stu-id="99f62-207">The connector instance URL should be treated as secret/confidential: anyone who has that URL can post to it, like an email address.</span></span> <span data-ttu-id="99f62-208">そのため、迷惑メールやフィッシングまたはマルウェアのサイトへのリンクについては、いくつかのリスクがあります。</span><span class="sxs-lookup"><span data-stu-id="99f62-208">Therefore, there's some risk of spam or links to phishing or malware sites.</span></span> <span data-ttu-id="99f62-209">この問題が発生した場合は、チーム所有者がコネクタインスタンスを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="99f62-209">If that were to happen, team owners can delete the connector instance.</span></span>

- <span data-ttu-id="99f62-210">コネクタメッセージを送信するサービスが侵害され、スパム/フィッシングまたはマルウェアリンクの送信を開始した場合、テナント管理者は、新しいコネクタインスタンスが作成されないようにして、Microsoft がそれらを中央でブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="99f62-210">If the service that sends connector messages were to become compromised and start sending spam/phishing/malware links, a tenant administrator can prevent new connector instances from being created and Microsoft can block them centrally.</span></span>

> [!NOTE]
> <span data-ttu-id="99f62-211">現在、操作できるメッセージ (REPLYTO_CONNECTOR_MESSAGE アクセス許可) をサポートしているコネクタを特定することはできません。</span><span class="sxs-lookup"><span data-stu-id="99f62-211">It's not currently possible to know which connectors support actionable messages (REPLYTO_CONNECTOR_MESSAGE permission).</span></span>

## <a name="outgoing-webhooks"></a><span data-ttu-id="99f62-212">発信 web フック</span><span class="sxs-lookup"><span data-stu-id="99f62-212">Outgoing webhooks</span></span>

<span data-ttu-id="99f62-213">*発信 web フック*は、チーム所有者またはチームメンバーごとに作成されます。</span><span class="sxs-lookup"><span data-stu-id="99f62-213">*Outgoing webhooks* are created on the fly by team owners or team members.</span></span> <span data-ttu-id="99f62-214">チームアプリの機能ではありません。この情報は、完全性のために含まれています。</span><span class="sxs-lookup"><span data-stu-id="99f62-214">They aren't capabilities of Teams apps; this information is included for completeness.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="99f62-215">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="99f62-215">Required permissions</span></span>

<span data-ttu-id="99f62-216">RECEIVE_MESSAGE、REPLYTO_MESSAGE。</span><span class="sxs-lookup"><span data-stu-id="99f62-216">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span></span> <span data-ttu-id="99f62-217">ユーザーからのメッセージを受信して返信することができます。</span><span class="sxs-lookup"><span data-stu-id="99f62-217">Can receive messages from users and reply to them.</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="99f62-218">オプションの権限</span><span class="sxs-lookup"><span data-stu-id="99f62-218">Optional permissions</span></span>

<span data-ttu-id="99f62-219">なし</span><span class="sxs-lookup"><span data-stu-id="99f62-219">None</span></span>

### <a name="considerations"></a><span data-ttu-id="99f62-220">考慮事項</span><span class="sxs-lookup"><span data-stu-id="99f62-220">Considerations</span></span>

- <span data-ttu-id="99f62-221">発信 web フックはボットに似ていますが、権限が少なくなっています。</span><span class="sxs-lookup"><span data-stu-id="99f62-221">Outgoing webhooks are similar to bots but have fewer privileges.</span></span> <span data-ttu-id="99f62-222">ボットと同じように、明示的にメンションする必要があります。</span><span class="sxs-lookup"><span data-stu-id="99f62-222">They must be explicitly mentioned, just like bots.</span></span>

- <span data-ttu-id="99f62-223">送信 webhook が登録されると、秘密が生成されます。これにより、送信の webhook は、悪意のある攻撃者とは異なり、送信者が Microsoft Teams であることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="99f62-223">When an outgoing webhook is registered, a secret is generated, which allows the outgoing webhook to verify that the sender is Microsoft Teams as opposed to a malicious attacker.</span></span> <span data-ttu-id="99f62-224">このシークレットは、秘密のままにしておく必要があります。このアプリにアクセスできるすべてのユーザーが、Microsoft Teams を偽装できます。</span><span class="sxs-lookup"><span data-stu-id="99f62-224">This secret should remain a secret; anyone who has access to it can impersonate Microsoft Teams.</span></span> <span data-ttu-id="99f62-225">秘密が侵害された場合は、送信された webhook を削除して再作成することができます。これにより、新しいシークレットが生成されます。</span><span class="sxs-lookup"><span data-stu-id="99f62-225">If the secret is compromised, the outgoing webhook can be deleted and re-created, and a new secret will be generated.</span></span>

- <span data-ttu-id="99f62-226">機密情報を検証しない送信 webhook を作成することもできますが、それに対してはお勧めします。</span><span class="sxs-lookup"><span data-stu-id="99f62-226">Although it's possible to create an outgoing webhook that doesn't validate the secret, we recommend against it.</span></span>

- <span data-ttu-id="99f62-227">送信 web フックでは、メッセージの受信と返信以外に、メッセージを事前に送信したり、ファイルを送受信したりすることはできません。また、ボットがメッセージの受信と返信以外の操作を実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="99f62-227">Other than receiving and replying to messages, outgoing webhooks can't do much: they can't proactively send messages, they can't send or receive files, they can't do anything else that bots can do except receive and reply to messages.</span></span>
