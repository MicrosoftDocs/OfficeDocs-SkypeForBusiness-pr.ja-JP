---
title: 監督付きチャットを使用する
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
description: Microsoft Teams 会議での監督付きチャットについて説明します。
ms.openlocfilehash: 125273131ea4de6937b65f15d48469f3039d6aeb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118058"
---
# <a name="supervised-chats-in-microsoft-teams"></a><span data-ttu-id="b6902-103">Microsoft Teams の監督付きチャット</span><span class="sxs-lookup"><span data-stu-id="b6902-103">Supervised chats in Microsoft Teams</span></span>

<span data-ttu-id="b6902-104">教育機関は、学生に安全で健全なデジタル空間を提供します。</span><span class="sxs-lookup"><span data-stu-id="b6902-104">Education institutions provide a safe and healthy digital space for students.</span></span> <span data-ttu-id="b6902-105">デジタル空間には、Teams のメール、オンライン会議と通話、メッセージングが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b6902-105">The digital space includes emails, online meetings and calls, and messaging in Teams.</span></span> <span data-ttu-id="b6902-106">不適切なメッセージング動作を防ぐために、多くの学校では Teams のプライベート チャットを無効にしています。</span><span class="sxs-lookup"><span data-stu-id="b6902-106">To prevent inappropriate messaging behavior, many schools disable private chat in Teams.</span></span> <span data-ttu-id="b6902-107">残念ながら、チャットを無効にすると、教師がパーソナライズされた学習のために学生に個人的に手を差し伸べる機会もブロックされます。</span><span class="sxs-lookup"><span data-stu-id="b6902-107">Unfortunately, disabling chat also blocks the opportunity for teachers to reach out to students privately for personalized learning.</span></span> <span data-ttu-id="b6902-108">チャットが無効になっている場合、学生はクラス チームでメッセージを公開しない場合、教師に通知することはできません。</span><span class="sxs-lookup"><span data-stu-id="b6902-108">With chat disabled, students can't reach out to teachers when they prefer not to post the messages publicly in class teams.</span></span>

<span data-ttu-id="b6902-109">監督付きチャットを使用すると、指定された教師は、適切な教師が存在しない限り、学生とのチャットを開始し、学生が新しいチャットを開始するのをブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="b6902-109">Supervised chat allows designated educators to initiate chats with students and blocks students from starting new chats unless an appropriate educator is present.</span></span> <span data-ttu-id="b6902-110">チャットの監督機能が有効になっている場合、監督者はチャットから退出することはできません。また、他の参加者はチャットを削除できません。学生が関与するチャットが適切に監督されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b6902-110">When chat supervision is enabled, supervisors aren't allowed to leave chats and other participants aren't allowed to remove them, ensuring that chats involving students are properly supervised.</span></span>

<span data-ttu-id="b6902-111">これらの制限は、監督されたチャットが完全に有効にされた後に作成される新しいプライベート チャットにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="b6902-111">These limitations are only applied to new private chats that are created after supervised chat has been fully enabled.</span></span> <span data-ttu-id="b6902-112">既存のプライベート チャット、会議チャット、チャネルには適用されません。</span><span class="sxs-lookup"><span data-stu-id="b6902-112">They don't apply to existing private chats, meetings chats, or channels.</span></span> <span data-ttu-id="b6902-113">会議チャットまたはチャネルの安全性に関するベスト プラクティスの詳細については、学生のセーフティ ガイドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6902-113">To learn more about best practices for meeting chat or channel safety, view student safety guide.</span></span>

> [!Note]
> <span data-ttu-id="b6902-114">監督されたチャットは、機能が適用された後に作成された新しいチャットを保護します。</span><span class="sxs-lookup"><span data-stu-id="b6902-114">Supervised chat protects new chats created after the feature is enforced.</span></span>  <span data-ttu-id="b6902-115">既存のチャットは保護されます。</span><span class="sxs-lookup"><span data-stu-id="b6902-115">It doesn't protect existing chats.</span></span>

## <a name="review-use-cases-for-supervised-chats"></a><span data-ttu-id="b6902-116">監督されたチャットの使用例を確認する</span><span class="sxs-lookup"><span data-stu-id="b6902-116">Review use cases for supervised chats</span></span>

<span data-ttu-id="b6902-117">次の例は、監督付きチャットが必要な場合の説明です。</span><span class="sxs-lookup"><span data-stu-id="b6902-117">The following examples are descriptions of when a supervised chat is necessary.</span></span>

- <span data-ttu-id="b6902-118">学生がパブリックで共有や質問を行うのに時間がかからなかった場合の教育者への 1.1 のフォローアップ。</span><span class="sxs-lookup"><span data-stu-id="b6902-118">A 1.1 follow-up with an educator when students aren't comfortable sharing or asking questions publicly.</span></span>

- <span data-ttu-id="b6902-119">課題、最近の授業のやり取り (または不足)、その他のトピックについて学生に 1.1 に到達する教師。</span><span class="sxs-lookup"><span data-stu-id="b6902-119">Educators reaching out 1.1 to a student about an assignment, recent class interaction (or lack of), or other topic.</span></span>

- <span data-ttu-id="b6902-120">教師が監視する学生グループディスカッション。</span><span class="sxs-lookup"><span data-stu-id="b6902-120">Student group discussions monitored by an educator.</span></span>

- <span data-ttu-id="b6902-121">教師付き環境で教師以外のスタッフが学生とチャットできます。</span><span class="sxs-lookup"><span data-stu-id="b6902-121">Allow non-teaching staff to chat with student in a supervised environment.</span></span>

## <a name="enable-supervised-chat"></a><span data-ttu-id="b6902-122">監督されたチャットを有効にする</span><span class="sxs-lookup"><span data-stu-id="b6902-122">Enable supervised chat</span></span>

> [!Note]
> <span data-ttu-id="b6902-123">学校のチャットを有効にする前に、チャットのアクセス許可の役割と役割に基づくチャットのアクセス許可ポリシーを設定して、学生が提供されていないチャットに不要なアクセスを回避することを確認します。</span><span class="sxs-lookup"><span data-stu-id="b6902-123">Ensure that you set up chat permission roles and the role-based chat permission policies before enabling chat for your institution to avoid unwanted student access to unsupervised chats.</span></span>

### <a name="define-chat-permission-roles-for-each-user-in-your-environment"></a><span data-ttu-id="b6902-124">環境内の各ユーザーのチャットアクセス許可の役割を定義する</span><span class="sxs-lookup"><span data-stu-id="b6902-124">Define chat permission roles for each user in your environment</span></span>

<span data-ttu-id="b6902-125">監督されたチャットが期待通り動作するには、環境内の各ユーザーに正しいチャットアクセス許可の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6902-125">For supervised chat to work as expected each user within your environment needs to be assigned the correct chat permission role.</span></span> <span data-ttu-id="b6902-126">ユーザーに割り当て可能な役割は 3 つがあります。</span><span class="sxs-lookup"><span data-stu-id="b6902-126">There are three roles that a user can have assigned:</span></span>

- <span data-ttu-id="b6902-127">*フル アクセス許可* – この役割は、学生や他のスタッフ メンバーにフル アクセスする必要がある教師に最適です。</span><span class="sxs-lookup"><span data-stu-id="b6902-127">*Full permissions* – This role is ideal for educators who should have full access to students and other staff members.</span></span> <span data-ttu-id="b6902-128">お客様の環境内の任意のユーザーとチャットを開始できます。</span><span class="sxs-lookup"><span data-stu-id="b6902-128">They can start chats with any user within your environment.</span></span> <span data-ttu-id="b6902-129">フル アクセス許可を持つユーザーは、参加しているチャットを監督する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6902-129">Users with full permissions are expected to supervise the chats they participate in.</span></span> <span data-ttu-id="b6902-130">自分が開始したチャットや、フェデレーションテナントで監督しているチャットから退出したり削除したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b6902-130">They can't leave or be removed from chats that they start or chats that they're supervising in federated tenants.</span></span>

- <span data-ttu-id="b6902-131">*制限付きアクセス許可* – この役割は、教師による学生へのアクセスのみを許可し、他のスタッフや教師にフル アクセスできるスタッフ メンバーに最適です。</span><span class="sxs-lookup"><span data-stu-id="b6902-131">*Limited permissions* – This role is ideal for staff members who should only have supervised access to students and have full access to other staff and educators.</span></span> <span data-ttu-id="b6902-132">完全ユーザーまたは制限付きユーザーとのチャットを開始できますが、制限付きユーザーとのチャットは開始されません。</span><span class="sxs-lookup"><span data-stu-id="b6902-132">They can start chats with any full or limited users but can't start chats with restricted users.</span></span> <span data-ttu-id="b6902-133">フル アクセス許可を持つユーザーが制限されたユーザーとのチャットを開始した場合、制限されたユーザーを会話に取り込む可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b6902-133">If a user with full permissions begins a chat with a restricted user, limited users can be brought into the conversation.</span></span> <span data-ttu-id="b6902-134">このアクセスは、制限付きユーザーと制限されたユーザー間のコラボレーションを監督するために、フル アクセス許可を持つユーザーが存在するために発生します。</span><span class="sxs-lookup"><span data-stu-id="b6902-134">This access happens because a user with full permissions is present to supervise collaboration between limited and restricted users.</span></span>

- <span data-ttu-id="b6902-135">*アクセス許可の制限* – この役割は、監督が必要な学生に最適です。</span><span class="sxs-lookup"><span data-stu-id="b6902-135">*Restricted permissions* – This role is ideal for students who need to be supervised.</span></span> <span data-ttu-id="b6902-136">フル アクセス許可を持つユーザーとのチャットのみを開始できます。</span><span class="sxs-lookup"><span data-stu-id="b6902-136">They can only start chats with users who have full permissions.</span></span> <span data-ttu-id="b6902-137">フル アクセス許可を持つユーザーが招待した会話に参加できます。</span><span class="sxs-lookup"><span data-stu-id="b6902-137">They can participate in any conversation that a user with full permissions invites them to.</span></span> <span data-ttu-id="b6902-138">フェデレーション チャット の場合、制限されたユーザーは、制限されたユーザーのテナントからのフル アクセス許可を持つユーザーだけがチャットに追加できます。</span><span class="sxs-lookup"><span data-stu-id="b6902-138">In federated chat cases, restricted users can only be added to chats by a user with full permissions who is from the restricted user’s tenant.</span></span>

<span data-ttu-id="b6902-139">ユーザーのチャットアクセス許可の役割を設定するには、Teams 管理ポータルのメッセージング ポリシー オプションにあるチャットアクセス許可の役割ポリシーを使用します。  </span><span class="sxs-lookup"><span data-stu-id="b6902-139">To set your users’ chat permission role, use the **Chat permissions** **role** policy found within your Messaging policy options in the Teams admin portal.</span></span> <span data-ttu-id="b6902-140">値が Full、Limited、または Restricted の ChatPermissionRole ポリシーを使用して、PowerShell を使用してロールを定義できます。</span><span class="sxs-lookup"><span data-stu-id="b6902-140">You can use PowerShell to define roles using the ChatPermissionRole policy with the values Full, Limited, or Restricted.</span></span> <span data-ttu-id="b6902-141">このポリシーは CsTeamsMessagingPolicy に適用されます。</span><span class="sxs-lookup"><span data-stu-id="b6902-141">This policy is under CsTeamsMessagingPolicy.</span></span>

<span data-ttu-id="b6902-142">設定の詳細については、次のリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6902-142">To learn more about setting.</span></span> <span data-ttu-id="b6902-143">Teams ポリシーには、Teams のポリシーと Education のポリシー パッケージが表示され、多数のユーザー ガイドにポリシーが割り当てされます。</span><span class="sxs-lookup"><span data-stu-id="b6902-143">Teams policies see Teams policies and policy packages for Education and Assign policies to large sets of users guides.</span></span>

<span data-ttu-id="b6902-144">テナントのゲストにロールを割り当てできません。</span><span class="sxs-lookup"><span data-stu-id="b6902-144">Roles can't be assigned to guests in your tenant.</span></span> <span data-ttu-id="b6902-145">ゲストには、制限付きロールが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="b6902-145">Guests are assigned the limited role.</span></span>

### <a name="allow-supervised-chat"></a><span data-ttu-id="b6902-146">監督されたチャットを許可する</span><span class="sxs-lookup"><span data-stu-id="b6902-146">Allow supervised chat</span></span>

<span data-ttu-id="b6902-147">監督されたチャットは、テナントの既定では無効になっています。</span><span class="sxs-lookup"><span data-stu-id="b6902-147">Supervised chat is disabled by default for your tenant.</span></span> <span data-ttu-id="b6902-148">ユーザーのチャットアクセス許可の役割を設定した後は、組織全体の設定 &gt; **の [Teams** の設定] に移動し、[ロールベースのチャットのアクセス許可ポリシー] を *[* オン] に設定することで、テナント内で監督対象のチャットを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="b6902-148">After you've set chat permission roles for your users, you can enable supervised chat within your tenant by going to **Org-wide settings** &gt; **Teams Settings** and setting **Role-based chat permissions** policy to *On.*</span></span> <span data-ttu-id="b6902-149">AllowRoleBasedChatPermissions を True に設定することで、PowerShell を使用して監督チャットを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="b6902-149">You can also use PowerShell to enable Supervised Chat by setting AllowRoleBasedChatPermissions to True.</span></span> <span data-ttu-id="b6902-150">このコマンドレットは CsTeamsClientConfiguration の下です。</span><span class="sxs-lookup"><span data-stu-id="b6902-150">This cmdlet is under CsTeamsClientConfiguration.</span></span>

<span data-ttu-id="b6902-151">監督されたチャットは、テナント内のすべてのユーザーに対して有効にする必要があります。また、ユーザーの一部に対してだけ有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b6902-151">Supervised chat must be enabled for all users in the tenant and cannot be enabled for only a portion of your users.</span></span>

### <a name="enable-chat"></a><span data-ttu-id="b6902-152">チャットを有効にする</span><span class="sxs-lookup"><span data-stu-id="b6902-152">Enable chat</span></span>

<span data-ttu-id="b6902-153">Teams 管理センターで利用可能な既存のチャット ポリシーを使用して、すべてのユーザーのチャットを有効にする。</span><span class="sxs-lookup"><span data-stu-id="b6902-153">Enable chat for all your users using the existing Chat policy available in Teams admin center.</span></span>

## <a name="maintain-supervised-chats"></a><span data-ttu-id="b6902-154">監督付きチャットを管理する</span><span class="sxs-lookup"><span data-stu-id="b6902-154">Maintain supervised chats</span></span>

<span data-ttu-id="b6902-155">監督されたチャットを最初に有効にした後、環境内のチャットが監督された状態を維持するには、次のいくつかの操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6902-155">After supervised chat is initially enabled, you'll need to do a few things to ensure that the chats in your environment remain supervised:</span></span>

- <span data-ttu-id="b6902-156">テナントに参加する新しいユーザーに適切なロールを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b6902-156">Assign appropriate roles to any new users that join your tenant.</span></span> <span data-ttu-id="b6902-157">既定では、ユーザーには制限付きの役割が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="b6902-157">By default, users will be assigned a restricted role.</span></span>

- <span data-ttu-id="b6902-158">フル アクセス許可を持つユーザーがテナントから離れた場合、またはテナントから削除された場合、監督対象のチャットは無人になります。</span><span class="sxs-lookup"><span data-stu-id="b6902-158">If a user with full permissions leaves or is removed from a tenant, the chats they were supervising will be left unattended.</span></span> <span data-ttu-id="b6902-159">元のユーザーを削除する前に、チャットが監督された状態を維持するために、フル アクセス許可を持つ別のユーザーがこれらの会話に追加されます。</span><span class="sxs-lookup"><span data-stu-id="b6902-159">Before you remove the original user, ensure that another user with full permissions is added to these conversations so that the chat can remain supervised.</span></span> <span data-ttu-id="b6902-160">元の監督者が削除されると、新しい参加者を会話に追加することはできませんが、現在の参加者は通信を続けできます。</span><span class="sxs-lookup"><span data-stu-id="b6902-160">Once the original supervisor is removed, new participants can't be added to the conversation, but current participants can continue to communicate.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b6902-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="b6902-161">Related topics</span></span>

[<span data-ttu-id="b6902-162">教育用 Teams の監督付きチャット</span><span class="sxs-lookup"><span data-stu-id="b6902-162">Supervised chats for Teams in education</span></span>](https://support.microsoft.com/topic/supervised-chats-in-microsoft-teams-for-education-ad3aaafc-c85a-416f-95f9-d691f419cbb8?storagetype=live)