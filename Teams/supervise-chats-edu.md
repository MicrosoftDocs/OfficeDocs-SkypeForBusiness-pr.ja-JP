---
title: 教師ありチャットを使用する
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: angch
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 会議中の教師ありチャットについてMicrosoft Teamsします。
ms.openlocfilehash: e705120eb2f8b92ea437c78be67c139018f786fc
ms.sourcegitcommit: 50111653f72f6758a3491a4dc3e91160ab75022c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51506686"
---
# <a name="supervised-chats-in-microsoft-teams"></a><span data-ttu-id="ff246-103">教師ありチャット (Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ff246-103">Supervised chats in Microsoft Teams</span></span>

<span data-ttu-id="ff246-104">教育機関は、学生に安全で正常なデジタル空間を提供します。</span><span class="sxs-lookup"><span data-stu-id="ff246-104">Education institutions provide a safe and healthy digital space for students.</span></span> <span data-ttu-id="ff246-105">デジタル空間には、電子メール、オンライン会議と通話、メッセージが含Teams。</span><span class="sxs-lookup"><span data-stu-id="ff246-105">The digital space includes emails, online meetings and calls, and messaging in Teams.</span></span> <span data-ttu-id="ff246-106">不適切なメッセージング動作を防ぐために、多くの学校では、プライベート チャットを無効Teams。</span><span class="sxs-lookup"><span data-stu-id="ff246-106">To prevent inappropriate messaging behavior, many schools disable private chat in Teams.</span></span> <span data-ttu-id="ff246-107">残念ながら、チャットを無効にすると、教師がパーソナライズされた学習のために学生に個人的に手を差し伸べる機会もブロックされます。</span><span class="sxs-lookup"><span data-stu-id="ff246-107">Unfortunately, disabling chat also blocks the opportunity for teachers to reach out to students privately for personalized learning.</span></span> <span data-ttu-id="ff246-108">チャットを無効にすると、学生はクラス チームで一般にメッセージを投稿しない場合、教師に手を差し伸べできなくなります。</span><span class="sxs-lookup"><span data-stu-id="ff246-108">With chat disabled, students can't reach out to teachers when they prefer not to post the messages publicly in class teams.</span></span>

<span data-ttu-id="ff246-109">教師ありチャットを使用すると、指定された教師は、適切な教師が存在しない限り、学生とのチャットを開始し、学生が新しいチャットを開始できないのをブロックできます。</span><span class="sxs-lookup"><span data-stu-id="ff246-109">Supervised chat allows designated educators to initiate chats with students and blocks students from starting new chats unless an appropriate educator is present.</span></span> <span data-ttu-id="ff246-110">チャット監督が有効になっている場合、監督者はチャットを退出できません。また、他の参加者はチャットを削除できません。学生が関与するチャットが適切に監督されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ff246-110">When chat supervision is enabled, supervisors aren't allowed to leave chats and other participants aren't allowed to remove them, ensuring that chats involving students are properly supervised.</span></span>

<span data-ttu-id="ff246-111">これらの制限は、教師ありチャットが完全に有効にされた後に作成された新しいプライベート チャットにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="ff246-111">These limitations are only applied to new private chats that are created after supervised chat has been fully enabled.</span></span> <span data-ttu-id="ff246-112">既存のプライベート チャット、会議チャット、チャネルには適用されません。</span><span class="sxs-lookup"><span data-stu-id="ff246-112">They don't apply to existing private chats, meetings chats, or channels.</span></span> <span data-ttu-id="ff246-113">会議チャット、チャネルの安全性、学生の安全を確保するためのベスト プラクティスの詳細については、「学生を安全に保管しながら学生を安全に保管する」を[Teams。](https://support.microsoft.com/topic/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8?ui=en-us&rs=en-us&ad=us#ID0EBBAAA=For_educators&ID0EDD=For_educators)</span><span class="sxs-lookup"><span data-stu-id="ff246-113">To learn more about best practices for meeting chat, channel safety, and keeping students safe, view [Keeping students safe while using Teams](https://support.microsoft.com/topic/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8?ui=en-us&rs=en-us&ad=us#ID0EBBAAA=For_educators&ID0EDD=For_educators).</span></span>

> [!Note]
> <span data-ttu-id="ff246-114">教師ありチャットは、機能が適用された後に作成された新しいチャットを保護します。</span><span class="sxs-lookup"><span data-stu-id="ff246-114">Supervised chat protects new chats created after the feature is enforced.</span></span>  <span data-ttu-id="ff246-115">既存のチャットは保護されます。</span><span class="sxs-lookup"><span data-stu-id="ff246-115">It doesn't protect existing chats.</span></span>

## <a name="review-use-cases-for-supervised-chats"></a><span data-ttu-id="ff246-116">教師ありチャットの使用例を確認する</span><span class="sxs-lookup"><span data-stu-id="ff246-116">Review use cases for supervised chats</span></span>

<span data-ttu-id="ff246-117">次の例は、教師ありチャットが必要な場合の説明です。</span><span class="sxs-lookup"><span data-stu-id="ff246-117">The following examples are descriptions of when a supervised chat is necessary.</span></span>

- <span data-ttu-id="ff246-118">学生がパブリックに共有したり質問したりできない場合の教師への 1.1 フォローアップ。</span><span class="sxs-lookup"><span data-stu-id="ff246-118">A 1.1 follow-up with an educator when students aren't comfortable sharing or asking questions publicly.</span></span>

- <span data-ttu-id="ff246-119">課題、最近の授業のやり取り (または不足)、その他のトピックについて 1.1 を学生に提供する教師。</span><span class="sxs-lookup"><span data-stu-id="ff246-119">Educators reaching out 1.1 to a student about an assignment, recent class interaction (or lack of), or other topic.</span></span>

- <span data-ttu-id="ff246-120">教師が監視する学生グループディスカッション。</span><span class="sxs-lookup"><span data-stu-id="ff246-120">Student group discussions monitored by an educator.</span></span>

- <span data-ttu-id="ff246-121">教師あり環境で教師ありのスタッフが学生とチャットできます。</span><span class="sxs-lookup"><span data-stu-id="ff246-121">Allow non-teaching staff to chat with student in a supervised environment.</span></span>

## <a name="enable-supervised-chat"></a><span data-ttu-id="ff246-122">教師ありチャットを有効にする</span><span class="sxs-lookup"><span data-stu-id="ff246-122">Enable supervised chat</span></span>

> [!Note]
> <span data-ttu-id="ff246-123">教育機関のチャットを有効にする前に、チャットのアクセス許可ロールとロールベースのチャットアクセス許可ポリシーを設定して、学生が管理されていないチャットに望ましくないアクセスを許可しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="ff246-123">Ensure that you set up chat permission roles and the role-based chat permission policies before enabling chat for your institution to avoid unwanted student access to unsupervised chats.</span></span>

### <a name="define-chat-permission-roles-for-each-user-in-your-environment"></a><span data-ttu-id="ff246-124">環境内の各ユーザーのチャットアクセス許可ロールを定義する</span><span class="sxs-lookup"><span data-stu-id="ff246-124">Define chat permission roles for each user in your environment</span></span>

<span data-ttu-id="ff246-125">教師ありチャットを想定した方法で動作するには、環境内の各ユーザーに適切なチャットアクセス許可ロールを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff246-125">For supervised chat to work as expected each user within your environment needs to be assigned the correct chat permission role.</span></span> <span data-ttu-id="ff246-126">ユーザーが割り当て可能なロールは次の 3 つがあります。</span><span class="sxs-lookup"><span data-stu-id="ff246-126">There are three roles that a user can have assigned:</span></span>

- <span data-ttu-id="ff246-127">*フル アクセス許可* – このロールは、学生や他のスタッフ メンバーへのフル アクセス権を持つ教師に最適です。</span><span class="sxs-lookup"><span data-stu-id="ff246-127">*Full permissions* – This role is ideal for educators who should have full access to students and other staff members.</span></span> <span data-ttu-id="ff246-128">ユーザーは、環境内の任意のユーザーとチャットを開始できます。</span><span class="sxs-lookup"><span data-stu-id="ff246-128">They can start chats with any user within your environment.</span></span> <span data-ttu-id="ff246-129">フル アクセス許可を持つユーザーは、参加しているチャットを監督する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff246-129">Users with full permissions are expected to supervise the chats they participate in.</span></span> <span data-ttu-id="ff246-130">自分が開始したチャットやフェデレーション テナントで監督しているチャットから退出したり、削除したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="ff246-130">They can't leave or be removed from chats that they start or chats that they're supervising in federated tenants.</span></span>

- <span data-ttu-id="ff246-131">*制限付きアクセス* 許可 – このロールは、教師による学生へのアクセス権のみを持ち、他のスタッフや教師にフル アクセスできるスタッフ メンバーに最適です。</span><span class="sxs-lookup"><span data-stu-id="ff246-131">*Limited permissions* – This role is ideal for staff members who should only have supervised access to students and have full access to other staff and educators.</span></span> <span data-ttu-id="ff246-132">フル ユーザーまたは制限付きユーザーとのチャットを開始できますが、制限付きユーザーとのチャットを開始できない。</span><span class="sxs-lookup"><span data-stu-id="ff246-132">They can start chats with any full or limited users but can't start chats with restricted users.</span></span> <span data-ttu-id="ff246-133">フル アクセス許可を持つユーザーが制限付きユーザーとのチャットを開始した場合、制限付きのユーザーを会話に取り込む可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ff246-133">If a user with full permissions begins a chat with a restricted user, limited users can be brought into the conversation.</span></span> <span data-ttu-id="ff246-134">このアクセスは、制限付きユーザーと制限されたユーザー間のコラボレーションを監督するための完全なアクセス許可を持つユーザーが存在する場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="ff246-134">This access happens because a user with full permissions is present to supervise collaboration between limited and restricted users.</span></span>

- <span data-ttu-id="ff246-135">*制限付きアクセス* 許可 – このロールは、教師を必要とする学生に最適です。</span><span class="sxs-lookup"><span data-stu-id="ff246-135">*Restricted permissions* – This role is ideal for students who need to be supervised.</span></span> <span data-ttu-id="ff246-136">フル アクセス許可を持つユーザーとのチャットのみを開始できます。</span><span class="sxs-lookup"><span data-stu-id="ff246-136">They can only start chats with users who have full permissions.</span></span> <span data-ttu-id="ff246-137">フル アクセス許可を持つユーザーが招待した会話に参加できます。</span><span class="sxs-lookup"><span data-stu-id="ff246-137">They can participate in any conversation that a user with full permissions invites them to.</span></span> <span data-ttu-id="ff246-138">フェデレーション チャット の場合、制限付きユーザーは、制限されたユーザーのテナントからのすべてのアクセス許可を持つユーザーだけがチャットに追加できます。</span><span class="sxs-lookup"><span data-stu-id="ff246-138">In federated chat cases, restricted users can only be added to chats by a user with full permissions who is from the restricted user’s tenant.</span></span>

<span data-ttu-id="ff246-139">ユーザーのチャットアクセス許可ロールを設定するには、管理ポータルの [メッセージング ポリシー] オプションにある [チャットのアクセス許可Teams使用します。</span><span class="sxs-lookup"><span data-stu-id="ff246-139">To set your users’ chat permission role, use the **Chat permissions** **role** policy found within your Messaging policy options in the Teams admin portal.</span></span> <span data-ttu-id="ff246-140">PowerShell を使用して、ChatPermissionRole ポリシーを使用して、値が Full、Limited、または Restricted のロールを定義できます。</span><span class="sxs-lookup"><span data-stu-id="ff246-140">You can use PowerShell to define roles using the ChatPermissionRole policy with the values Full, Limited, or Restricted.</span></span> <span data-ttu-id="ff246-141">このポリシーは CsTeamsMessagingPolicy の下に置かされます。</span><span class="sxs-lookup"><span data-stu-id="ff246-141">This policy is under CsTeamsMessagingPolicy.</span></span>

<span data-ttu-id="ff246-142">設定の詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff246-142">To learn more about setting.</span></span> <span data-ttu-id="ff246-143">Teamsについては、「Education Teamsポリシーとポリシー パッケージ」と「大規模なユーザー セットにポリシーを割り当てる」のガイドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff246-143">Teams policies see Teams policies and policy packages for Education and Assign policies to large sets of users guides.</span></span>

<span data-ttu-id="ff246-144">ロールは、テナントのゲストに割り当てできません。</span><span class="sxs-lookup"><span data-stu-id="ff246-144">Roles can't be assigned to guests in your tenant.</span></span> <span data-ttu-id="ff246-145">ゲストには、制限付きロールが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="ff246-145">Guests are assigned the limited role.</span></span>

### <a name="allow-supervised-chat"></a><span data-ttu-id="ff246-146">教師ありチャットを許可する</span><span class="sxs-lookup"><span data-stu-id="ff246-146">Allow supervised chat</span></span>

<span data-ttu-id="ff246-147">教師ありチャットは、テナントに対して既定で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="ff246-147">Supervised chat is disabled by default for your tenant.</span></span> <span data-ttu-id="ff246-148">ユーザーのチャットアクセス許可ロールを設定した後、組織全体の設定 Teams 設定 に移動し、[ロールベースのチャットのアクセス許可] ポリシーを &gt; **[** オン] に設定することで、テナント内で教師ありチャットを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="ff246-148">After you've set chat permission roles for your users, you can enable supervised chat within your tenant by going to **Org-wide settings** &gt; **Teams Settings** and setting **Role-based chat permissions** policy to *On.*</span></span> <span data-ttu-id="ff246-149">また、PowerShell を使用して、AllowRoleBasedChatPermissions を True に設定することで、教師ありチャットを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="ff246-149">You can also use PowerShell to enable Supervised Chat by setting AllowRoleBasedChatPermissions to True.</span></span> <span data-ttu-id="ff246-150">このコマンドレットは CsTeamsClientConfiguration の下に置かされています。</span><span class="sxs-lookup"><span data-stu-id="ff246-150">This cmdlet is under CsTeamsClientConfiguration.</span></span>

<span data-ttu-id="ff246-151">教師ありチャットは、テナント内のすべてのユーザーに対して有効にする必要があります。また、ユーザーの一部に対してのみ有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="ff246-151">Supervised chat must be enabled for all users in the tenant and cannot be enabled for only a portion of your users.</span></span>

### <a name="enable-chat"></a><span data-ttu-id="ff246-152">チャットを有効にする</span><span class="sxs-lookup"><span data-stu-id="ff246-152">Enable chat</span></span>

<span data-ttu-id="ff246-153">管理センターで使用できる既存のチャット ポリシーを使用して、すべてのユーザー Teams有効にする。</span><span class="sxs-lookup"><span data-stu-id="ff246-153">Enable chat for all your users using the existing Chat policy available in Teams admin center.</span></span>

## <a name="maintain-supervised-chats"></a><span data-ttu-id="ff246-154">教師ありチャットを維持する</span><span class="sxs-lookup"><span data-stu-id="ff246-154">Maintain supervised chats</span></span>

<span data-ttu-id="ff246-155">教師ありチャットが最初に有効になると、環境内のチャットが教師ありの状態を維持するために、いくつかの操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff246-155">After supervised chat is initially enabled, you'll need to do a few things to ensure that the chats in your environment remain supervised:</span></span>

- <span data-ttu-id="ff246-156">テナントに参加する新しいユーザーに適切なロールを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ff246-156">Assign appropriate roles to any new users that join your tenant.</span></span> <span data-ttu-id="ff246-157">既定では、ユーザーには制限付きロールが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="ff246-157">By default, users will be assigned a restricted role.</span></span>

- <span data-ttu-id="ff246-158">フル アクセス許可を持つユーザーがテナントから離れるか、テナントから削除された場合、監督していたチャットは無人で残されます。</span><span class="sxs-lookup"><span data-stu-id="ff246-158">If a user with full permissions leaves or is removed from a tenant, the chats they were supervising will be left unattended.</span></span> <span data-ttu-id="ff246-159">元のユーザーを削除する前に、チャットが監督された状態を維持できるよう、フル アクセス許可を持つ別のユーザーがこれらの会話に追加されます。</span><span class="sxs-lookup"><span data-stu-id="ff246-159">Before you remove the original user, ensure that another user with full permissions is added to these conversations so that the chat can remain supervised.</span></span> <span data-ttu-id="ff246-160">元のスーパーバイザーが削除されると、新しい参加者を会話に追加することはできませんが、現在の参加者は引き続き通信できます。</span><span class="sxs-lookup"><span data-stu-id="ff246-160">Once the original supervisor is removed, new participants can't be added to the conversation, but current participants can continue to communicate.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ff246-161">関連トピック</span><span class="sxs-lookup"><span data-stu-id="ff246-161">Related topics</span></span>

[<span data-ttu-id="ff246-162">教育における教師ありTeamsチャット</span><span class="sxs-lookup"><span data-stu-id="ff246-162">Supervised chats for Teams in education</span></span>](https://support.microsoft.com/topic/supervised-chats-in-microsoft-teams-for-education-ad3aaafc-c85a-416f-95f9-d691f419cbb8?storagetype=live)
