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
ms.openlocfilehash: 295bee65120e3c349efe1aa5fbc1e7b42c8da87a
ms.sourcegitcommit: 1db39fde090809d9abc6d7346dda55814d88993a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2020
ms.locfileid: "48739385"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a><span data-ttu-id="66b3d-103">Microsoft Teams アプリのアクセス許可と考慮事項</span><span class="sxs-lookup"><span data-stu-id="66b3d-103">Microsoft Teams apps permissions and considerations</span></span>

<span data-ttu-id="66b3d-104">Microsoft Teams アプリは、1つ以上の機能をインストール、アップグレード、アンインストールできる _アプリパッケージ_ に集約するための手段です。</span><span class="sxs-lookup"><span data-stu-id="66b3d-104">Microsoft Teams apps are a way to aggregate one or more capabilities into an _app package_ that can be installed, upgraded, and uninstalled.</span></span> <span data-ttu-id="66b3d-105">次のような機能があります。</span><span class="sxs-lookup"><span data-stu-id="66b3d-105">The capabilities include:</span></span>

- <span data-ttu-id="66b3d-106">ボット</span><span class="sxs-lookup"><span data-stu-id="66b3d-106">Bots</span></span>
- <span data-ttu-id="66b3d-107">メッセージングの拡張機能</span><span class="sxs-lookup"><span data-stu-id="66b3d-107">Messaging extensions</span></span>
- <span data-ttu-id="66b3d-108">タブ</span><span class="sxs-lookup"><span data-stu-id="66b3d-108">Tabs</span></span>
- <span data-ttu-id="66b3d-109">コネクタ</span><span class="sxs-lookup"><span data-stu-id="66b3d-109">Connectors</span></span>

<span data-ttu-id="66b3d-110">アプリはユーザーによって各人され、ポリシーの観点から管理されます。</span><span class="sxs-lookup"><span data-stu-id="66b3d-110">Apps are consented to by users and managed by IT from a policy perspective.</span></span> <span data-ttu-id="66b3d-111">ただし、ほとんどの場合、アプリのアクセス許可とリスクプロファイルは、アプリに含まれる機能の権限とリスクのプロファイルによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="66b3d-111">However, for the most part, an app's permissions and risk profile are defined by the permissions and risk profiles of the capabilities that the app contains.</span></span> <span data-ttu-id="66b3d-112">したがって、この記事では、権限とその機能レベルに関する考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="66b3d-112">Therefore, this article focuses on permissions and considerations at the capability level.</span></span>

<span data-ttu-id="66b3d-113">RECEIVE_MESSAGE や REPLYTO_MESSAGE などの大文字で示されているアクセス許可は、 [Microsoft Teams の開発者向けドキュメント](https://aka.ms/teamsdevdocs) または [microsoft Graph のアクセス許可](https://developer.microsoft.com/graph/docs/concepts/permissions_reference)のいずれかには表示されません。</span><span class="sxs-lookup"><span data-stu-id="66b3d-113">The permissions listed below in capital letters, for example RECEIVE_MESSAGE and REPLYTO_MESSAGE, don't appear anywhere in the [Microsoft Teams developer documentation](https://aka.ms/teamsdevdocs) or the [permissions for Microsoft Graph](https://developer.microsoft.com/graph/docs/concepts/permissions_reference).</span></span> <span data-ttu-id="66b3d-114">これらは、この記事の目的について簡単に説明しています。</span><span class="sxs-lookup"><span data-stu-id="66b3d-114">They're simply a descriptive shorthand for the purpose of this article.</span></span>


| <span data-ttu-id="66b3d-115">タイトル</span><span class="sxs-lookup"><span data-stu-id="66b3d-115">Title</span></span>   | <span data-ttu-id="66b3d-116">説明</span><span class="sxs-lookup"><span data-stu-id="66b3d-116">Description</span></span>    |
|-----------|------------|
| ![判断ポイントを表すアイコン](media/audio_conferencing_image7.png) <br/><span data-ttu-id="66b3d-118">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="66b3d-118">Decision point</span></span>|<ul><li><span data-ttu-id="66b3d-119">次の表を参考にして、調査しているアプリで要求されているアクセス許可について理解してください。</span><span class="sxs-lookup"><span data-stu-id="66b3d-119">Use the tables below as a guide to understand which permissions the apps you're investigating are requesting.</span></span></li></ul> |
| ![次の手順を示すアイコン](media/audio_conferencing_image9.png)<br/><span data-ttu-id="66b3d-121">次の手順</span><span class="sxs-lookup"><span data-stu-id="66b3d-121">Next step</span></span>|<ul><li><span data-ttu-id="66b3d-122">アプリまたはサービス自体を調査して、組織内でのアクセスを許可するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="66b3d-122">Research the app or service itself to decide whether you want to allow access to it within your organization.</span></span> <span data-ttu-id="66b3d-123">たとえば、ボットはユーザーからのメッセージを送受信します。また、エンタープライズカスタムボット以外は、コンプライアンスの境界外にあります。</span><span class="sxs-lookup"><span data-stu-id="66b3d-123">For example, bots send and receive messages from users, and—except for enterprise custom bots—they're located outside the compliance boundary.</span></span> <span data-ttu-id="66b3d-124">そのため、bot を含むすべてのアプリには、これらのアクセス許可が必要であり、少なくともそのリスクのプロファイルが設定されています。</span><span class="sxs-lookup"><span data-stu-id="66b3d-124">Therefore, any app that includes a bot requires those permissions and has that risk profile, at a minimum.</span></span> </li></ul>|

## <a name="global-app-permissions-and-considerations"></a><span data-ttu-id="66b3d-125">グローバルアプリのアクセス許可と考慮事項</span><span class="sxs-lookup"><span data-stu-id="66b3d-125">Global app permissions and considerations</span></span>

### <a name="required-permissions"></a><span data-ttu-id="66b3d-126">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="66b3d-126">Required permissions</span></span>

<span data-ttu-id="66b3d-127">なし</span><span class="sxs-lookup"><span data-stu-id="66b3d-127">None</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="66b3d-128">オプションの権限</span><span class="sxs-lookup"><span data-stu-id="66b3d-128">Optional permissions</span></span>

<span data-ttu-id="66b3d-129">なし</span><span class="sxs-lookup"><span data-stu-id="66b3d-129">None</span></span>

### <a name="considerations"></a><span data-ttu-id="66b3d-130">考慮事項</span><span class="sxs-lookup"><span data-stu-id="66b3d-130">Considerations</span></span>

- <span data-ttu-id="66b3d-131">アプリは、使用するデータと、利用規約およびプライバシーポリシーへのリンクでデータがどのように使用されているかを公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="66b3d-131">An app must disclose what data it uses and what the data is used for in its terms of use and privacy policy links.</span></span>

- <span data-ttu-id="66b3d-132">[リソース固有の同意](resource-specific-consent.md) は、アプリのインストール画面に表示される、アプリが要求できる一連のアクセス許可を提供します。</span><span class="sxs-lookup"><span data-stu-id="66b3d-132">[Resource-specific consent](resource-specific-consent.md) provides a set of permissions that apps can request, which appears on the installation screen of the app.</span></span> <span data-ttu-id="66b3d-133">リソース固有の同意権限の詳細については、「 [Graph 権限リファレンス](https://docs.microsoft.com/graph/permissions-reference#teams-resource-specific-consent-permissions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66b3d-133">To learn more about resource-specific consent permissions, see [Graph permissions reference](https://docs.microsoft.com/graph/permissions-reference#teams-resource-specific-consent-permissions).</span></span>

- <span data-ttu-id="66b3d-134">アプリでは、リソース固有の同意権限以外の権限が必要になる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="66b3d-134">Apps may also need permissions other than resource-specific consent permissions.</span></span> <span data-ttu-id="66b3d-135">アプリがインストールされると、アプリは同意プロンプトを通じてグラフのアクセス許可を要求できます。</span><span class="sxs-lookup"><span data-stu-id="66b3d-135">After an app is installed, the app may request Graph permissions through a consent prompt.</span></span> <span data-ttu-id="66b3d-136">詳細については、「 [AZURE AD アプリケーションの同意のエクスペリエンスについ](https://docs.microsoft.com/azure/active-directory/develop/application-consent-experience)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66b3d-136">To learn more, see [Understanding Azure AD application consent experiences](https://docs.microsoft.com/azure/active-directory/develop/application-consent-experience).</span></span> <span data-ttu-id="66b3d-137">Azure ポータルで API の権限と承認を構成できます。</span><span class="sxs-lookup"><span data-stu-id="66b3d-137">You can configure API permissions and consent in the Azure portal.</span></span> <span data-ttu-id="66b3d-138">詳細については、「 [Azure Active Directory の承認フレームワーク](https://docs.microsoft.com/azure/active-directory/develop/consent-framework)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66b3d-138">To learn more, see [Azure Active Directory consent framework](https://docs.microsoft.com/azure/active-directory/develop/consent-framework).</span></span>

## <a name="bots-and-messaging-extensions"></a><span data-ttu-id="66b3d-139">ボットとメッセージングの拡張機能</span><span class="sxs-lookup"><span data-stu-id="66b3d-139">Bots and messaging extensions</span></span>

### <a name="required-permissions"></a><span data-ttu-id="66b3d-140">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="66b3d-140">Required permissions</span></span>

- <span data-ttu-id="66b3d-141">RECEIVE_MESSAGE、REPLYTO_MESSAGE。</span><span class="sxs-lookup"><span data-stu-id="66b3d-141">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span></span> <span data-ttu-id="66b3d-142">ボットは、ユーザーからのメッセージを受信して返信することができます。<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="66b3d-142">The bot can receive messages from users and reply to them.<sup>1</sup></span></span>

- <span data-ttu-id="66b3d-143">POST_MESSAGE_USER。</span><span class="sxs-lookup"><span data-stu-id="66b3d-143">POST_MESSAGE_USER.</span></span> <span data-ttu-id="66b3d-144">ユーザーがボットにメッセージを送信した後、ボットはユーザーのダイレクトメッセージ ( *予防的なメッセージ* とも呼ばれます) をいつでも送信できます。</span><span class="sxs-lookup"><span data-stu-id="66b3d-144">After a user has sent a message to a bot, the bot can send the user direct messages (also called *proactive messages* at any time.</span></span>

- <span data-ttu-id="66b3d-145">GET_CHANNEL_LIST。</span><span class="sxs-lookup"><span data-stu-id="66b3d-145">GET_CHANNEL_LIST.</span></span> <span data-ttu-id="66b3d-146">Teams に追加されたボットは、チーム内のチャネルの名前と Id の一覧を取得できます。</span><span class="sxs-lookup"><span data-stu-id="66b3d-146">Bots added to teams can get a list of names and IDs of the channels in a team.</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="66b3d-147">オプションの権限</span><span class="sxs-lookup"><span data-stu-id="66b3d-147">Optional permissions</span></span>

- <span data-ttu-id="66b3d-148">身分.</span><span class="sxs-lookup"><span data-stu-id="66b3d-148">IDENTITY.</span></span> <span data-ttu-id="66b3d-149">チャネルで使用されている場合、アプリのボットは、チームメンバー (名、姓、ユーザープリンシパル名 [UPN]、メールアドレス) の基本的な id 情報にアクセスできます。個人またはグループチャットで使用されている場合、bot は、それらのユーザーに対して同じ情報にアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="66b3d-149">When it's used in a channel, the app's bots can access basic identity information of team members (first name, last name, user principal name [UPN], email address); when it's used in a personal or group chat, the bot can access the same information for those users.</span></span>

- <span data-ttu-id="66b3d-150">POST_MESSAGE_TEAM。</span><span class="sxs-lookup"><span data-stu-id="66b3d-150">POST_MESSAGE_TEAM.</span></span> <span data-ttu-id="66b3d-151">ユーザーが以前に bot に話したことがない場合でも、アプリのボットが、任意の時点で任意のチームメンバーに対して直接 (予防的) メッセージを送信することを許可します。</span><span class="sxs-lookup"><span data-stu-id="66b3d-151">Allows an app's bots to send direct (proactive) messages to any team member at any time, even if the user has never talked to the bot before.</span></span>

- <span data-ttu-id="66b3d-152">次のようなアクセス許可は明示的ではありませんが、マニフェストで宣言された RECEIVE_MESSAGE と REPLYTO_MESSAGE と、ボットを使うことができるスコープによって暗黙的に指定されています。</span><span class="sxs-lookup"><span data-stu-id="66b3d-152">The following are not explicit permissions, but are implied by RECEIVE_MESSAGE and REPLYTO_MESSAGE and the scopes into which the bots can be used, declared in the manifest:</span></span>
 
    - <span data-ttu-id="66b3d-153">RECEIVE_MESSAGE_PERSONAL、REPLYTO_MESSAGE_PERSONAL</span><span class="sxs-lookup"><span data-stu-id="66b3d-153">RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL</span></span>
    - <span data-ttu-id="66b3d-154">RECEIVE_MESSAGE_GROUPCHAT、REPLYTO_MESSAGE_GROUPCHAT</span><span class="sxs-lookup"><span data-stu-id="66b3d-154">RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT</span></span>
    - <span data-ttu-id="66b3d-155">RECEIVE_MESSAGE_TEAM、REPLYTO_MESSAGE_TEAM</span><span class="sxs-lookup"><span data-stu-id="66b3d-155">RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM</span></span>

- <span data-ttu-id="66b3d-156">SEND_FILES、RECEIVE_FILES。<sup>2</sup> bot が個人的なチャットでファイルを送受信できるかどうかを制御します (グループチャットまたはチャネルではまだサポートされていません)。</span><span class="sxs-lookup"><span data-stu-id="66b3d-156">SEND_FILES, RECEIVE_FILES.<sup>2</sup> Controls whether a bot can send and receive files in personal chat (not yet supported for group chat or channels).</span></span>

### <a name="considerations"></a><span data-ttu-id="66b3d-157">考慮事項</span><span class="sxs-lookup"><span data-stu-id="66b3d-157">Considerations</span></span>

- <span data-ttu-id="66b3d-158">ボットは、それらが追加されたチーム、またはインストールしたユーザーにのみアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="66b3d-158">Bots only have access to teams to which they've been added or to users who have installed them.</span></span>

- <span data-ttu-id="66b3d-159">ボットは、ユーザーによって明示的にメンションされたメッセージのみを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="66b3d-159">Bots only receive messages in which they're explicitly mentioned by users.</span></span> <span data-ttu-id="66b3d-160">このデータは企業ネットワークから離れています。</span><span class="sxs-lookup"><span data-stu-id="66b3d-160">This data leaves the corporate network.</span></span>

- <span data-ttu-id="66b3d-161">ボットは、メンションされた会話にのみ返信できます。</span><span class="sxs-lookup"><span data-stu-id="66b3d-161">Bots can only reply to conversations in which they're mentioned.</span></span>

- <span data-ttu-id="66b3d-162">ユーザーがボットを使用している場合、ボットにそのユーザーの ID が保存されている場合は、いつでもそのユーザーのダイレクトメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="66b3d-162">After a user has conversed with a bot, if the bot stores that user's ID, it can send that user direct messages at any time.</span></span>

- <span data-ttu-id="66b3d-163">ボットメッセージには、フィッシングまたはマルウェアサイトへのリンクが含まれていても、ユーザー、テナント管理者、または Microsoft によってグローバルにブロックされている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="66b3d-163">It is theoretically possible for bot messages to contain links to phishing or malware sites, but bots can be blocked by the user, the tenant admin, or globally by Microsoft.</span></span>

- <span data-ttu-id="66b3d-164">Bot は、アプリが追加されたチームメンバー、または個人またはグループチャットの個々のユーザーに対して、非常に基本的な id 情報を取得 (および保存する可能性があります) することができます。</span><span class="sxs-lookup"><span data-stu-id="66b3d-164">A bot can retrieve (and might store) very basic identity information for the team members the app has been added to, or for individual users in personal or group chats.</span></span> <span data-ttu-id="66b3d-165">これらのユーザーについての詳細情報を入手するには、ボットが Azure Active Directory (Azure AD) にサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="66b3d-165">To get further information about these users, the bot must require them to sign in to Azure Active Directory (Azure AD).</span></span>

- <span data-ttu-id="66b3d-166">Bot は、チーム内のチャネルの一覧を取得 (および保存する可能性があります) することができます。このデータは企業ネットワークから離れています。</span><span class="sxs-lookup"><span data-stu-id="66b3d-166">Bots can retrieve (and might store) the list of channels in a team; this data leaves the corporate network.</span></span>

- <span data-ttu-id="66b3d-167">ボットにファイルが送信されると、ファイルは企業ネットワークから脱退します。</span><span class="sxs-lookup"><span data-stu-id="66b3d-167">When a file is sent to a bot, the file leaves the corporate network.</span></span> <span data-ttu-id="66b3d-168">ファイルを送受信するには、各ファイルに対してユーザーの承認が必要です。</span><span class="sxs-lookup"><span data-stu-id="66b3d-168">Sending and receiving files requires user approval for each file.</span></span> 

- <span data-ttu-id="66b3d-169">既定では、bot はユーザーの代わりに操作することはできませんが、ユーザーにサインインを求めることができます。ユーザーがサインインするとすぐに、ボットには追加の項目を実行できるアクセストークンがあります。</span><span class="sxs-lookup"><span data-stu-id="66b3d-169">By default, bots don't have the ability to act on behalf of the user, but bots can ask users to sign in; as soon as the user signs in, the bot will have an access token with which it can do additional things.</span></span> <span data-ttu-id="66b3d-170">このような追加事項は、ボットとユーザがサインインする場所によって異なります。ボットは、に登録されている Azure AD アプリで https://apps.dev.microsoft.com/ あり、独自の権限を設定できます。</span><span class="sxs-lookup"><span data-stu-id="66b3d-170">Exactly what those additional things are depends on the bot and where the user signs in: a bot is an Azure AD app registered at https://apps.dev.microsoft.com/ and can have its own set of permissions.</span></span>

- <span data-ttu-id="66b3d-171">ユーザーがチームに追加または削除されるたびに、ボットに通知されます。</span><span class="sxs-lookup"><span data-stu-id="66b3d-171">Bots are informed whenever users are added to or deleted from a team.</span></span>

- <span data-ttu-id="66b3d-172">ユーザーの IP アドレスまたはその他の参照情報は表示されません。</span><span class="sxs-lookup"><span data-stu-id="66b3d-172">Bots don't see users' IP addresses or other referrer information.</span></span> <span data-ttu-id="66b3d-173">すべての情報は Microsoft から取得されます。</span><span class="sxs-lookup"><span data-stu-id="66b3d-173">All information comes from Microsoft.</span></span> <span data-ttu-id="66b3d-174">(例外は1つしかありません。ボットが独自のサインインエクスペリエンスを実装している場合、サインイン UI にユーザーの IP アドレスと参照元情報が表示されます)。</span><span class="sxs-lookup"><span data-stu-id="66b3d-174">(There is one exception: if a bot implements its own sign-in experience, the sign-in UI will see users' IP addresses and referrer information.)</span></span>

- <span data-ttu-id="66b3d-175">メッセージングの内線番号には、ユーザーの IP アドレスと参照元情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="66b3d-175">Messaging extensions, on the other hand, do see users' IP addresses and referrer information.</span></span>

- <span data-ttu-id="66b3d-176">アプリのガイドライン (およびその AppSource review プロセス) では、有効な目的のために、ユーザーに (POST_MESSAGE_TEAM アクセス許可を使用して) 個人のチャットメッセージを送信するための判断が必要です。</span><span class="sxs-lookup"><span data-stu-id="66b3d-176">App guidelines (and our AppSource review process) require discretion in posting personal chat messages to users (via the POST_MESSAGE_TEAM permission) for valid purposes.</span></span> <span data-ttu-id="66b3d-177">不正使用の場合は、ユーザーがボットをブロックできるため、テナント管理者はアプリをブロックすることができます。また、必要に応じて、ボットを一元的にブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="66b3d-177">In the event of abuse, users can block the bot, tenant admins can block the app, and Microsoft can block bots centrally if necessary.</span></span>

<span data-ttu-id="66b3d-178"><sup>1</sup> 一部のボットはメッセージのみを送信します (POST_MESSAGE_USER)。</span><span class="sxs-lookup"><span data-stu-id="66b3d-178"><sup>1</sup> Some bots only send messages (POST_MESSAGE_USER).</span></span> <span data-ttu-id="66b3d-179">"通知のみ" と呼ばれますが、ボットが許可されているものや、許可されていないものを指しているわけではないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="66b3d-179">They're called "notification-only" bots, but the term doesn't refer to what a bot is allowed or not allowed to do, it means that the bot doesn't want to expose a conversational experience.</span></span> <span data-ttu-id="66b3d-180">このフィールドは、通常は有効になる UI の機能を無効にするために使用されます。このボットは、会話体験を公開しているボットと比較した場合に制限されていません。</span><span class="sxs-lookup"><span data-stu-id="66b3d-180">Teams uses this field to disable functionality in the UI that would ordinarily be enabled; the bot isn't restricted in what it's allowed to do compared to bots that do expose a conversational experience.</span></span>

<span data-ttu-id="66b3d-181"><sup>2</sup> アプリの manifest.jsファイルの bot オブジェクトの Supportsfiles ブールプロパティによって制御されます。</span><span class="sxs-lookup"><span data-stu-id="66b3d-181"><sup>2</sup> Governed by the supportsFiles Boolean property on the bot object in the manifest.json file for the app.</span></span>

> [!NOTE]
> <span data-ttu-id="66b3d-182">ボットに独自のサインインがある場合は、ユーザーが初めてサインインするときに、2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="66b3d-182">If a bot has its own sign-in, there's a second—different—consent experience the first time the user signs in.</span></span>
>
><span data-ttu-id="66b3d-183">現時点では、Teams アプリ内のいずれかの機能に関連付けられた Azure AD 権限 (ボット、タブ、コネクタ、またはメッセージング拡張機能) は、ここに記載されている Teams の権限から完全に分離されます。</span><span class="sxs-lookup"><span data-stu-id="66b3d-183">Currently, the Azure AD permissions associated with any of the capabilities inside a Teams app (bot, tab, connector, or messaging extension) are completely separate from the Teams permissions listed here.</span></span>

## <a name="tabs"></a><span data-ttu-id="66b3d-184">タブ</span><span class="sxs-lookup"><span data-stu-id="66b3d-184">Tabs</span></span>

<span data-ttu-id="66b3d-185">タブは、Teams 内で実行されている web サイトです。</span><span class="sxs-lookup"><span data-stu-id="66b3d-185">A tab is a website running inside Teams.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="66b3d-186">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="66b3d-186">Required permissions</span></span>

<span data-ttu-id="66b3d-187">SEND_AND_RECEIVE_WEB_DATA</span><span class="sxs-lookup"><span data-stu-id="66b3d-187">SEND_AND_RECEIVE_WEB_DATA</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="66b3d-188">オプションの権限</span><span class="sxs-lookup"><span data-stu-id="66b3d-188">Optional permissions</span></span>

<span data-ttu-id="66b3d-189">なし (現在)</span><span class="sxs-lookup"><span data-stu-id="66b3d-189">None (currently)</span></span>

### <a name="considerations"></a><span data-ttu-id="66b3d-190">考慮事項</span><span class="sxs-lookup"><span data-stu-id="66b3d-190">Considerations</span></span>

- <span data-ttu-id="66b3d-191">タブのリスクプロファイルは、ブラウザータブで実行されている同じ web サイトとほぼ同じです。</span><span class="sxs-lookup"><span data-stu-id="66b3d-191">The risk profile for a tab is almost identical to that same website running in a browser tab.</span></span> 

- <span data-ttu-id="66b3d-192">また、タブには、現在のユーザーのサインイン名と UPN、現在のユーザーの Azure AD オブジェクト ID、所属する Microsoft 365 グループの ID (チームの場合)、テナント ID、ユーザーの現在のロケールなど、タブで実行されているコンテキストが取得されます。</span><span class="sxs-lookup"><span data-stu-id="66b3d-192">A tab also gets the context in which it's running, including the sign-in name and UPN of the current user, the Azure AD Object ID for the current user, the ID of the Microsoft 365 Group in which it resides (if it's a team), the tenant ID, and the current locale of the user.</span></span> <span data-ttu-id="66b3d-193">ただし、これらの Id をユーザーの情報に対応付けるには、ユーザーが Azure AD にサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="66b3d-193">However, to map these IDs to a user's information, the tab would have to make the user sign in to Azure AD.</span></span>

## <a name="connectors"></a><span data-ttu-id="66b3d-194">コネクタ</span><span class="sxs-lookup"><span data-stu-id="66b3d-194">Connectors</span></span>

<span data-ttu-id="66b3d-195">外部システムのイベントが発生すると、コネクタはチャネルにメッセージを投稿します。</span><span class="sxs-lookup"><span data-stu-id="66b3d-195">A connector posts messages to a channel when events in an external system occur.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="66b3d-196">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="66b3d-196">Required permissions</span></span>

<span data-ttu-id="66b3d-197">POST_MESSAGE_CHANNEL</span><span class="sxs-lookup"><span data-stu-id="66b3d-197">POST_MESSAGE_CHANNEL</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="66b3d-198">オプションの権限</span><span class="sxs-lookup"><span data-stu-id="66b3d-198">Optional permissions</span></span>

<span data-ttu-id="66b3d-199">REPLYTO_CONNECTOR_MESSAGE。</span><span class="sxs-lookup"><span data-stu-id="66b3d-199">REPLYTO_CONNECTOR_MESSAGE.</span></span> <span data-ttu-id="66b3d-200">一部のコネクタは、操作可能なメッセージをサポートします。これにより、ユーザーは GitHub の問題への応答の追加や、Trello カードへの日付の追加などを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="66b3d-200">Certain connectors support actionable messages, which allow users to post targeted replies to the connector message, for example by adding a response to a GitHub issue or adding a date to a Trello card.</span></span>

### <a name="considerations"></a><span data-ttu-id="66b3d-201">考慮事項</span><span class="sxs-lookup"><span data-stu-id="66b3d-201">Considerations</span></span>

- <span data-ttu-id="66b3d-202">コネクタメッセージを投稿するシステムでは、メッセージの投稿先または受信者がわからない場合、受信者に関する情報は公開されません。</span><span class="sxs-lookup"><span data-stu-id="66b3d-202">The system that posts connector messages doesn't know who it's posting to or who receives the messages: no information about the recipient is disclosed.</span></span> <span data-ttu-id="66b3d-203">(Microsoft は、テナントではなく実際の受信者です。Microsoft はチャネルに実際に投稿します。)</span><span class="sxs-lookup"><span data-stu-id="66b3d-203">(Microsoft is the actual recipient, not the tenant; Microsoft does the actual post to the channel.)</span></span>

- <span data-ttu-id="66b3d-204">コネクタメッセージがチャネルに投稿されると、データは企業ネットワークから脱退します。</span><span class="sxs-lookup"><span data-stu-id="66b3d-204">No data leaves the corporate network when connector messages are posted to a channel.</span></span>

- <span data-ttu-id="66b3d-205">操作できるメッセージ (REPLYTO_CONNECTOR_MESSAGE アクセス許可) をサポートするコネクタにも、IP アドレスと参照情報は表示されません。この情報は、Microsoft に送信され、connector ポータルで Microsoft に以前登録されていた HTTP エンドポイントにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="66b3d-205">Connectors that support actionable messages (REPLYTO_CONNECTOR_MESSAGE permission) also don't see IP address and referrer information; this information is sent to Microsoft and then routed to HTTP endpoints that were previously registered with Microsoft in the Connectors portal.</span></span>

- <span data-ttu-id="66b3d-206">チャネル用にコネクタを構成するたびに、そのコネクタインスタンスの一意の URL が作成されます。</span><span class="sxs-lookup"><span data-stu-id="66b3d-206">Each time a connector is configured for a channel, a unique URL for that connector instance is created.</span></span> <span data-ttu-id="66b3d-207">このコネクタインスタンスが削除されると、URL を使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="66b3d-207">If that connector instance is deleted, the URL can no longer be used.</span></span>

- <span data-ttu-id="66b3d-208">コネクタメッセージに添付ファイルを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="66b3d-208">Connector messages can't contain file attachments.</span></span>

- <span data-ttu-id="66b3d-209">コネクタインスタンス URL は、秘密/機密として扱う必要があります。この URL は、メールアドレスなど、その URL を持つすべてのユーザーが投稿できます。</span><span class="sxs-lookup"><span data-stu-id="66b3d-209">The connector instance URL should be treated as secret/confidential: anyone who has that URL can post to it, like an email address.</span></span> <span data-ttu-id="66b3d-210">そのため、迷惑メールやフィッシングまたはマルウェアのサイトへのリンクについては、いくつかのリスクがあります。</span><span class="sxs-lookup"><span data-stu-id="66b3d-210">Therefore, there's some risk of spam or links to phishing or malware sites.</span></span> <span data-ttu-id="66b3d-211">この問題が発生した場合は、チーム所有者がコネクタインスタンスを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="66b3d-211">If that were to happen, team owners can delete the connector instance.</span></span>

- <span data-ttu-id="66b3d-212">コネクタメッセージを送信するサービスが侵害され、スパム/フィッシングまたはマルウェアリンクの送信を開始した場合、テナント管理者は、新しいコネクタインスタンスが作成されないようにして、Microsoft がそれらを中央でブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="66b3d-212">If the service that sends connector messages were to become compromised and start sending spam/phishing/malware links, a tenant administrator can prevent new connector instances from being created and Microsoft can block them centrally.</span></span>

> [!NOTE]
> <span data-ttu-id="66b3d-213">現在、操作できるメッセージ (REPLYTO_CONNECTOR_MESSAGE アクセス許可) をサポートしているコネクタを特定することはできません。</span><span class="sxs-lookup"><span data-stu-id="66b3d-213">It's not currently possible to know which connectors support actionable messages (REPLYTO_CONNECTOR_MESSAGE permission).</span></span>

## <a name="outgoing-webhooks"></a><span data-ttu-id="66b3d-214">発信 web フック</span><span class="sxs-lookup"><span data-stu-id="66b3d-214">Outgoing webhooks</span></span>

<span data-ttu-id="66b3d-215">*発信 web フック* は、チーム所有者またはチームメンバーごとに作成されます。</span><span class="sxs-lookup"><span data-stu-id="66b3d-215">*Outgoing webhooks* are created on the fly by team owners or team members.</span></span> <span data-ttu-id="66b3d-216">チームアプリの機能ではありません。この情報は、完全性のために含まれています。</span><span class="sxs-lookup"><span data-stu-id="66b3d-216">They aren't capabilities of Teams apps; this information is included for completeness.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="66b3d-217">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="66b3d-217">Required permissions</span></span>

<span data-ttu-id="66b3d-218">RECEIVE_MESSAGE、REPLYTO_MESSAGE。</span><span class="sxs-lookup"><span data-stu-id="66b3d-218">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span></span> <span data-ttu-id="66b3d-219">ユーザーからのメッセージを受信して返信することができます。</span><span class="sxs-lookup"><span data-stu-id="66b3d-219">Can receive messages from users and reply to them.</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="66b3d-220">オプションの権限</span><span class="sxs-lookup"><span data-stu-id="66b3d-220">Optional permissions</span></span>

<span data-ttu-id="66b3d-221">なし</span><span class="sxs-lookup"><span data-stu-id="66b3d-221">None</span></span>

### <a name="considerations"></a><span data-ttu-id="66b3d-222">考慮事項</span><span class="sxs-lookup"><span data-stu-id="66b3d-222">Considerations</span></span>

- <span data-ttu-id="66b3d-223">発信 web フックはボットに似ていますが、権限が少なくなっています。</span><span class="sxs-lookup"><span data-stu-id="66b3d-223">Outgoing webhooks are similar to bots but have fewer privileges.</span></span> <span data-ttu-id="66b3d-224">ボットと同じように、明示的にメンションする必要があります。</span><span class="sxs-lookup"><span data-stu-id="66b3d-224">They must be explicitly mentioned, just like bots.</span></span>

- <span data-ttu-id="66b3d-225">送信 webhook が登録されると、秘密が生成されます。これにより、送信の webhook は、悪意のある攻撃者とは異なり、送信者が Microsoft Teams であることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="66b3d-225">When an outgoing webhook is registered, a secret is generated, which allows the outgoing webhook to verify that the sender is Microsoft Teams as opposed to a malicious attacker.</span></span> <span data-ttu-id="66b3d-226">このシークレットは、秘密のままにしておく必要があります。このアプリにアクセスできるすべてのユーザーが、Microsoft Teams を偽装できます。</span><span class="sxs-lookup"><span data-stu-id="66b3d-226">This secret should remain a secret; anyone who has access to it can impersonate Microsoft Teams.</span></span> <span data-ttu-id="66b3d-227">秘密が侵害された場合は、送信された webhook を削除して再作成することができます。これにより、新しいシークレットが生成されます。</span><span class="sxs-lookup"><span data-stu-id="66b3d-227">If the secret is compromised, the outgoing webhook can be deleted and re-created, and a new secret will be generated.</span></span>

- <span data-ttu-id="66b3d-228">機密情報を検証しない送信 webhook を作成することもできますが、それに対してはお勧めします。</span><span class="sxs-lookup"><span data-stu-id="66b3d-228">Although it's possible to create an outgoing webhook that doesn't validate the secret, we recommend against it.</span></span>

- <span data-ttu-id="66b3d-229">送信 web フックでは、メッセージの受信と返信以外に、メッセージを事前に送信したり、ファイルを送受信したりすることはできません。また、ボットがメッセージの受信と返信以外の操作を実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="66b3d-229">Other than receiving and replying to messages, outgoing webhooks can't do much: they can't proactively send messages, they can't send or receive files, they can't do anything else that bots can do except receive and reply to messages.</span></span>
