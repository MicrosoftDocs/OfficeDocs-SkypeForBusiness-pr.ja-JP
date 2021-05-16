---
title: 監視ありチャットを使用する
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
description: Microsoft Teams 会議の監視ありチャットについて説明します。
ms.openlocfilehash: e705120eb2f8b92ea437c78be67c139018f786fc
ms.sourcegitcommit: 50111653f72f6758a3491a4dc3e91160ab75022c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51506686"
---
# <a name="supervised-chats-in-microsoft-teams"></a><span data-ttu-id="6dfbc-103">Microsoft Teams の監視ありチャット</span><span class="sxs-lookup"><span data-stu-id="6dfbc-103">Supervised chats in Microsoft Teams</span></span>

<span data-ttu-id="6dfbc-104">教育機関は、学生に安全で健康的なデジタル空間を提供します。</span><span class="sxs-lookup"><span data-stu-id="6dfbc-104">Education institutions provide a safe and healthy digital space for students.</span></span> <span data-ttu-id="6dfbc-105">デジタル空間には、メール、オンライン会議と通話、および Teams でのメッセージングが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6dfbc-105">The digital space includes emails, online meetings and calls, and messaging in Teams.</span></span> <span data-ttu-id="6dfbc-106">不適切なメッセージング動作を防ぐために、多くの学校は Teams でプライベート チャットを無効にしています。</span><span class="sxs-lookup"><span data-stu-id="6dfbc-106">To prevent inappropriate messaging behavior, many schools disable private chat in Teams.</span></span> <span data-ttu-id="6dfbc-107">残念ながら、チャットを無効にすると、教師が学生の個人的な学習のために学生に個人的に連絡する機会もブロックされます。</span><span class="sxs-lookup"><span data-stu-id="6dfbc-107">Unfortunately, disabling chat also blocks the opportunity for teachers to reach out to students privately for personalized learning.</span></span> <span data-ttu-id="6dfbc-108">チャットが無効になっていると、学生は、クラス チームにメッセージを投稿したくない場合、教師に連絡できなくなります。</span><span class="sxs-lookup"><span data-stu-id="6dfbc-108">With chat disabled, students can't reach out to teachers when they prefer not to post the messages publicly in class teams.</span></span>

<span data-ttu-id="6dfbc-109">監視ありチャットでは、指定された教師が学生とチャットを開始するのを許可し、適切な教師がいない場合は、学生が新しいチャットを開始するのをブロックします。</span><span class="sxs-lookup"><span data-stu-id="6dfbc-109">Supervised chat allows designated educators to initiate chats with students and blocks students from starting new chats unless an appropriate educator is present.</span></span> <span data-ttu-id="6dfbc-110">チャットの監督が有効になっている場合、スーパーバイザーはチャットを離れることができず、他の参加者はチャットを削除することはできません。これにより、学生が関与するチャットが適切に監視されます。</span><span class="sxs-lookup"><span data-stu-id="6dfbc-110">When chat supervision is enabled, supervisors aren't allowed to leave chats and other participants aren't allowed to remove them, ensuring that chats involving students are properly supervised.</span></span>

<span data-ttu-id="6dfbc-111">これらの制限事項は、監視ありチャットが完全に有効になった後に作成される新しいプライベート チャットにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="6dfbc-111">These limitations are only applied to new private chats that are created after supervised chat has been fully enabled.</span></span> <span data-ttu-id="6dfbc-112">既存のプライベート チャット、会議チャット、またはチャネルには適用されません。</span><span class="sxs-lookup"><span data-stu-id="6dfbc-112">They don't apply to existing private chats, meetings chats, or channels.</span></span> <span data-ttu-id="6dfbc-113">チャットの会議、チャネルの安全性、および学生の安全維持のためのベスト プラクティスの詳細については、「[Teams 使用中の学生の安全維持](https://support.microsoft.com/topic/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8?ui=en-us&rs=en-us&ad=us#ID0EBBAAA=For_educators&ID0EDD=For_educators)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6dfbc-113">To learn more about best practices for meeting chat, channel safety, and keeping students safe, view [Keeping students safe while using Teams](https://support.microsoft.com/topic/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8?ui=en-us&rs=en-us&ad=us#ID0EBBAAA=For_educators&ID0EDD=For_educators).</span></span>

> [!Note]
> <span data-ttu-id="6dfbc-114">監視ありチャットは、機能の適用後に作成された新しいチャットを保護します。</span><span class="sxs-lookup"><span data-stu-id="6dfbc-114">Supervised chat protects new chats created after the feature is enforced.</span></span>  <span data-ttu-id="6dfbc-115">既存のチャットは保護されません。</span><span class="sxs-lookup"><span data-stu-id="6dfbc-115">It doesn't protect existing chats.</span></span>

## <a name="review-use-cases-for-supervised-chats"></a><span data-ttu-id="6dfbc-116">監視ありチャットのユース ケースを確認する</span><span class="sxs-lookup"><span data-stu-id="6dfbc-116">Review use cases for supervised chats</span></span>

<span data-ttu-id="6dfbc-117">次の例は、監視ありチャットが必要な場合の説明です。</span><span class="sxs-lookup"><span data-stu-id="6dfbc-117">The following examples are descriptions of when a supervised chat is necessary.</span></span>

- <span data-ttu-id="6dfbc-118">学生が公に疑問を共有したり質問したりすることに抵抗がある場合の教師による 1 対 1 のフォローアップ。</span><span class="sxs-lookup"><span data-stu-id="6dfbc-118">A 1.1 follow-up with an educator when students aren't comfortable sharing or asking questions publicly.</span></span>

- <span data-ttu-id="6dfbc-119">教師は、課題、最近のクラスの交流 (または欠如)、またはその他のトピックについて学生と 1 対 1 で連絡します。</span><span class="sxs-lookup"><span data-stu-id="6dfbc-119">Educators reaching out 1.1 to a student about an assignment, recent class interaction (or lack of), or other topic.</span></span>

- <span data-ttu-id="6dfbc-120">教師が監視する学生グループのディスカッション。</span><span class="sxs-lookup"><span data-stu-id="6dfbc-120">Student group discussions monitored by an educator.</span></span>

- <span data-ttu-id="6dfbc-121">教師以外のスタッフに監視された環境で学生とのチャットを許可します。</span><span class="sxs-lookup"><span data-stu-id="6dfbc-121">Allow non-teaching staff to chat with student in a supervised environment.</span></span>

## <a name="enable-supervised-chat"></a><span data-ttu-id="6dfbc-122">監視ありチャットを有効にする</span><span class="sxs-lookup"><span data-stu-id="6dfbc-122">Enable supervised chat</span></span>

> [!Note]
> <span data-ttu-id="6dfbc-123">機関でチャットを有効にする前に、チャット権限の役割と役割ベースのチャット権限のポリシーを設定して、監視されていないチャットへの不用意な学生アクセスを回避します。</span><span class="sxs-lookup"><span data-stu-id="6dfbc-123">Ensure that you set up chat permission roles and the role-based chat permission policies before enabling chat for your institution to avoid unwanted student access to unsupervised chats.</span></span>

### <a name="define-chat-permission-roles-for-each-user-in-your-environment"></a><span data-ttu-id="6dfbc-124">環境内の各ユーザーにチャット権限の役割を定義する</span><span class="sxs-lookup"><span data-stu-id="6dfbc-124">Define chat permission roles for each user in your environment</span></span>

<span data-ttu-id="6dfbc-125">監視ありチャットを期待どおりに機能させるには、環境内の各ユーザーに正しいチャット権限の役割を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6dfbc-125">For supervised chat to work as expected each user within your environment needs to be assigned the correct chat permission role.</span></span> <span data-ttu-id="6dfbc-126">ユーザーが割り当てることができる役割は 3 つあります。</span><span class="sxs-lookup"><span data-stu-id="6dfbc-126">There are three roles that a user can have assigned:</span></span>

- <span data-ttu-id="6dfbc-127">*完全な権限* – この役割は、学生や他のスタッフに完全にアクセスできる必要がある教師にとって理想的です。</span><span class="sxs-lookup"><span data-stu-id="6dfbc-127">*Full permissions* – This role is ideal for educators who should have full access to students and other staff members.</span></span> <span data-ttu-id="6dfbc-128">彼らはあなたの環境内のどのユーザーともチャットを始めることができます。</span><span class="sxs-lookup"><span data-stu-id="6dfbc-128">They can start chats with any user within your environment.</span></span> <span data-ttu-id="6dfbc-129">完全な権限を持つユーザーは、参加するチャットを監督することが期待されています。</span><span class="sxs-lookup"><span data-stu-id="6dfbc-129">Users with full permissions are expected to supervise the chats they participate in.</span></span> <span data-ttu-id="6dfbc-130">開始したチャットや、フェデレーション テナントで監視しているチャットを離れたり、削除したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="6dfbc-130">They can't leave or be removed from chats that they start or chats that they're supervising in federated tenants.</span></span>

- <span data-ttu-id="6dfbc-131">*限定された権限* – この役割は、学生へ監視付きアクセス権のみを持ち、他のスタッフや教師へ完全なアクセス権を持つ必要があるスタッフにとって理想的です。</span><span class="sxs-lookup"><span data-stu-id="6dfbc-131">*Limited permissions* – This role is ideal for staff members who should only have supervised access to students and have full access to other staff and educators.</span></span> <span data-ttu-id="6dfbc-132">完全なユーザーまたは限定されたユーザーとチャットを開始することはできますが、制限されたユーザーとチャットを開始することはできません。</span><span class="sxs-lookup"><span data-stu-id="6dfbc-132">They can start chats with any full or limited users but can't start chats with restricted users.</span></span> <span data-ttu-id="6dfbc-133">完全な権限を持つユーザーが制限されたユーザーとチャットを開始すると、限定されたユーザーを会話に参加させることができます。</span><span class="sxs-lookup"><span data-stu-id="6dfbc-133">If a user with full permissions begins a chat with a restricted user, limited users can be brought into the conversation.</span></span> <span data-ttu-id="6dfbc-134">このアクセスは、限定されたユーザーと制限されたユーザーの間のコラボレーションを監視するのに完全な権限を持つユーザーが存在するため可能です。</span><span class="sxs-lookup"><span data-stu-id="6dfbc-134">This access happens because a user with full permissions is present to supervise collaboration between limited and restricted users.</span></span>

- <span data-ttu-id="6dfbc-135">*制限された権限* – この役割は、監督が必要な学生にとって理想的です。</span><span class="sxs-lookup"><span data-stu-id="6dfbc-135">*Restricted permissions* – This role is ideal for students who need to be supervised.</span></span> <span data-ttu-id="6dfbc-136">完全な権限を持つユーザーとのみチャットを開始できます。</span><span class="sxs-lookup"><span data-stu-id="6dfbc-136">They can only start chats with users who have full permissions.</span></span> <span data-ttu-id="6dfbc-137">完全な権限を持つユーザーが招待する会話に参加できます。</span><span class="sxs-lookup"><span data-stu-id="6dfbc-137">They can participate in any conversation that a user with full permissions invites them to.</span></span> <span data-ttu-id="6dfbc-138">フェデレーション チャットの場合、制限されたユーザーは、制限されたユーザーのテナントからの完全な権限を持つユーザーによってのみチャットに追加されます。</span><span class="sxs-lookup"><span data-stu-id="6dfbc-138">In federated chat cases, restricted users can only be added to chats by a user with full permissions who is from the restricted user’s tenant.</span></span>

<span data-ttu-id="6dfbc-139">ユーザーのチャット権限の役割を設定するには、Teams 管理ポータルの [メッセージング] ポリシー オプション内にある **[チャット権限** の **役割]** ポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="6dfbc-139">To set your users’ chat permission role, use the **Chat permissions** **role** policy found within your Messaging policy options in the Teams admin portal.</span></span> <span data-ttu-id="6dfbc-140">PowerShell を使用して、値が完全、限定、または制限の ChatPermissionRole ポリシーを使用して役割を定義できます。</span><span class="sxs-lookup"><span data-stu-id="6dfbc-140">You can use PowerShell to define roles using the ChatPermissionRole policy with the values Full, Limited, or Restricted.</span></span> <span data-ttu-id="6dfbc-141">このポリシーは CsTeamsMessagingPolicy の下にあります。</span><span class="sxs-lookup"><span data-stu-id="6dfbc-141">This policy is under CsTeamsMessagingPolicy.</span></span>

<span data-ttu-id="6dfbc-142">設定についての詳細情報。</span><span class="sxs-lookup"><span data-stu-id="6dfbc-142">To learn more about setting.</span></span> <span data-ttu-id="6dfbc-143">Teams ポリシーには、教育機関向け Teams ポリシーおよびポリシー パッケージ、および多数のユーザー セットへのポリシーの割り当てガイドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6dfbc-143">Teams policies see Teams policies and policy packages for Education and Assign policies to large sets of users guides.</span></span>

<span data-ttu-id="6dfbc-144">テナント内のゲストに役割を割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="6dfbc-144">Roles can't be assigned to guests in your tenant.</span></span> <span data-ttu-id="6dfbc-145">ゲストには限定された役割が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="6dfbc-145">Guests are assigned the limited role.</span></span>

### <a name="allow-supervised-chat"></a><span data-ttu-id="6dfbc-146">監視ありチャットを許可する</span><span class="sxs-lookup"><span data-stu-id="6dfbc-146">Allow supervised chat</span></span>

<span data-ttu-id="6dfbc-147">監視ありチャットは、テナントに対して既定で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="6dfbc-147">Supervised chat is disabled by default for your tenant.</span></span> <span data-ttu-id="6dfbc-148">ユーザーのチャット権限の役割を設定した後、**[組織全体の設定]** &gt; **[Teams の設定]** に移動し、**[役割ベースのチャット権限]** のポリシー を *[オン]* に設定することで、テナント内で監視ありチャットを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="6dfbc-148">After you've set chat permission roles for your users, you can enable supervised chat within your tenant by going to **Org-wide settings** &gt; **Teams Settings** and setting **Role-based chat permissions** policy to *On.*</span></span> <span data-ttu-id="6dfbc-149">また、PowerShell を使用して、AllowRoleBasedChatPermissions を True に設定することにより、監視ありチャットを有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="6dfbc-149">You can also use PowerShell to enable Supervised Chat by setting AllowRoleBasedChatPermissions to True.</span></span> <span data-ttu-id="6dfbc-150">このコマンドレットは CsTeamsClientConfiguration の下にあります。</span><span class="sxs-lookup"><span data-stu-id="6dfbc-150">This cmdlet is under CsTeamsClientConfiguration.</span></span>

<span data-ttu-id="6dfbc-151">監視ありチャットは、テナント内のすべてのユーザーに対して有効にする必要があり、一部のユーザーに対してのみ有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="6dfbc-151">Supervised chat must be enabled for all users in the tenant and cannot be enabled for only a portion of your users.</span></span>

### <a name="enable-chat"></a><span data-ttu-id="6dfbc-152">チャットを有効にする</span><span class="sxs-lookup"><span data-stu-id="6dfbc-152">Enable chat</span></span>

<span data-ttu-id="6dfbc-153">Teams 管理センターで利用可能な既存のチャット ポリシーを使用して、すべてのユーザーのチャットを有効にします。</span><span class="sxs-lookup"><span data-stu-id="6dfbc-153">Enable chat for all your users using the existing Chat policy available in Teams admin center.</span></span>

## <a name="maintain-supervised-chats"></a><span data-ttu-id="6dfbc-154">監視ありチャットを維持する</span><span class="sxs-lookup"><span data-stu-id="6dfbc-154">Maintain supervised chats</span></span>

<span data-ttu-id="6dfbc-155">監視ありチャットを最初に有効にした後、環境内のチャットが引き続き監視対象になるようにするには、いくつかの操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="6dfbc-155">After supervised chat is initially enabled, you'll need to do a few things to ensure that the chats in your environment remain supervised:</span></span>

- <span data-ttu-id="6dfbc-156">テナントに参加する新しいユーザーに適切な役割を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="6dfbc-156">Assign appropriate roles to any new users that join your tenant.</span></span> <span data-ttu-id="6dfbc-157">既定では、ユーザーには制限された役割が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="6dfbc-157">By default, users will be assigned a restricted role.</span></span>

- <span data-ttu-id="6dfbc-158">完全な権限を持つユーザーがテナントを離れるか、テナントから削除された場合、彼らが監督していたチャットは無人のままになります。</span><span class="sxs-lookup"><span data-stu-id="6dfbc-158">If a user with full permissions leaves or is removed from a tenant, the chats they were supervising will be left unattended.</span></span> <span data-ttu-id="6dfbc-159">元のユーザーを削除する前に、チャットの監視を維持するため、完全な権限を持つ別のユーザーがこれらの会話に追加されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6dfbc-159">Before you remove the original user, ensure that another user with full permissions is added to these conversations so that the chat can remain supervised.</span></span> <span data-ttu-id="6dfbc-160">元のスーパーバイザーが削除されると、新しい参加者を会話に追加することはできませんが、現在の参加者は引き続きコミュニケーションできます。</span><span class="sxs-lookup"><span data-stu-id="6dfbc-160">Once the original supervisor is removed, new participants can't be added to the conversation, but current participants can continue to communicate.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6dfbc-161">関連トピック</span><span class="sxs-lookup"><span data-stu-id="6dfbc-161">Related topics</span></span>

[<span data-ttu-id="6dfbc-162">教育における Teams の監視ありチャット</span><span class="sxs-lookup"><span data-stu-id="6dfbc-162">Supervised chats for Teams in education</span></span>](https://support.microsoft.com/topic/supervised-chats-in-microsoft-teams-for-education-ad3aaafc-c85a-416f-95f9-d691f419cbb8?storagetype=live)
