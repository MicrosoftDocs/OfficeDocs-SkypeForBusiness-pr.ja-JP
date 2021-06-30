---
title: 教師ありチャットを非教育機関向けテナントに使用する
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
description: 会議中の非教育機関向けテナント向け教師ありチャットMicrosoft Teamsします。
ms.openlocfilehash: 9d3e7707632a384f82a89a965f6db51f786f9d66
ms.sourcegitcommit: 4d2e1328dee2b6c60ba0022976da8dfe5efba2ef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2021
ms.locfileid: "53203729"
---
# <a name="supervised-chats-for-non-educational-tenants"></a><span data-ttu-id="9e00b-103">非教育機関向けテナント向け教師ありチャット</span><span class="sxs-lookup"><span data-stu-id="9e00b-103">Supervised chats for non-educational tenants</span></span>

<span data-ttu-id="9e00b-104">教師ありチャットを使用すると、指定された監督者は組織内の誰とでもチャットを開始できます。また、適切な監督者が存在しない限り、制限付きのユーザーが新しいチャットを開始するのをブロックできます。</span><span class="sxs-lookup"><span data-stu-id="9e00b-104">Supervised chat allows designated supervisors to initiate chats with anyone in their organization and blocks restricted users from starting new chats unless an appropriate supervisor is present.</span></span> <span data-ttu-id="9e00b-105">チャット監督が有効になっている場合、監督者はチャットを退出できません。また、他の参加者はチャットを削除できません。制限付きユーザーを含むチャットが適切に監督されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9e00b-105">When chat supervision is enabled, supervisors aren't allowed to leave chats and other participants aren't allowed to remove them, ensuring that chats involving restricted users are properly supervised.</span></span>

<span data-ttu-id="9e00b-106">これらの制限事項は、監視ありチャットが完全に有効になった後に作成される新しいプライベート チャットにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="9e00b-106">These limitations are only applied to new private chats that are created after supervised chat has been fully enabled.</span></span> <span data-ttu-id="9e00b-107">既存のプライベート チャット、会議チャット、またはチャネルには適用されません。</span><span class="sxs-lookup"><span data-stu-id="9e00b-107">They don't apply to existing private chats, meetings chats, or channels.</span></span>

<span data-ttu-id="9e00b-108">教師ありチャットは教育機関のニーズに合わせて調整されますが、教育機関以外のテナントでも利用できます。</span><span class="sxs-lookup"><span data-stu-id="9e00b-108">Supervised chat is tailored for educational institution needs, but it is also available to non-educational tenants.</span></span>

> [!NOTE]
> <span data-ttu-id="9e00b-109">監視ありチャットは、機能の適用後に作成された新しいチャットを保護します。</span><span class="sxs-lookup"><span data-stu-id="9e00b-109">Supervised chat protects new chats created after the feature is enforced.</span></span> <span data-ttu-id="9e00b-110">既存のチャットは保護されません。</span><span class="sxs-lookup"><span data-stu-id="9e00b-110">It doesn't protect existing chats.</span></span>

## <a name="enable-supervised-chat"></a><span data-ttu-id="9e00b-111">監視ありチャットを有効にする</span><span class="sxs-lookup"><span data-stu-id="9e00b-111">Enable supervised chat</span></span>

> [!NOTE]
> <span data-ttu-id="9e00b-112">迷惑なチャットへの不要な制限付きユーザー アクセスを回避するために、教育機関のチャットを有効にする前に、チャットのアクセス許可ロールとロールベースのチャットアクセス許可ポリシーを設定してください。</span><span class="sxs-lookup"><span data-stu-id="9e00b-112">Ensure that you set up chat permission roles and the role-based chat permission policies before enabling chat for your institution to avoid unwanted restricted user access to unsupervised chats.</span></span>

<span data-ttu-id="9e00b-113">**環境内の各ユーザーにチャット権限の役割を定義する**</span><span class="sxs-lookup"><span data-stu-id="9e00b-113">**Define chat permission roles for each user in your environment**</span></span>

<span data-ttu-id="9e00b-114">監視ありチャットを期待どおりに機能させるには、環境内の各ユーザーに正しいチャット権限の役割を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e00b-114">For supervised chat to work as expected each user within your environment needs to be assigned the correct chat permission role.</span></span> <span data-ttu-id="9e00b-115">ユーザーが割り当てることができる役割は 3 つあります。</span><span class="sxs-lookup"><span data-stu-id="9e00b-115">There are three roles that a user can have assigned:</span></span>

- <span data-ttu-id="9e00b-116">フル アクセス許可: このロールは、環境内のチャット スーパーバイザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e00b-116">Full permissions: This role should be assigned to the chat supervisors in your environment.</span></span> <span data-ttu-id="9e00b-117">彼らはあなたの環境内のどのユーザーともチャットを始めることができます。</span><span class="sxs-lookup"><span data-stu-id="9e00b-117">They can start chats with any user within your environment.</span></span> <span data-ttu-id="9e00b-118">完全な権限を持つユーザーは、参加するチャットを監督することが期待されています。</span><span class="sxs-lookup"><span data-stu-id="9e00b-118">Users with full permissions are expected to supervise the chats they participate in.</span></span> <span data-ttu-id="9e00b-119">開始したチャットや、フェデレーション テナントで監視しているチャットを離れたり、削除したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="9e00b-119">They can't leave or be removed from chats that they start or chats that they're supervising in federated tenants.</span></span>

- <span data-ttu-id="9e00b-120">制限付きアクセス許可: このロールは、制限付きユーザーに対する教師ありアクセス権のみを持つスタッフ メンバーに最適です。</span><span class="sxs-lookup"><span data-stu-id="9e00b-120">Limited permissions: This role is ideal for staff members who should only have supervised access to restricted users.</span></span> <span data-ttu-id="9e00b-121">完全なユーザーまたは限定されたユーザーとチャットを開始することはできますが、制限されたユーザーとチャットを開始することはできません。</span><span class="sxs-lookup"><span data-stu-id="9e00b-121">They can start chats with any full or limited users but can't start chats with restricted users.</span></span> <span data-ttu-id="9e00b-122">完全な権限を持つユーザーが制限されたユーザーとチャットを開始すると、限定されたユーザーを会話に参加させることができます。</span><span class="sxs-lookup"><span data-stu-id="9e00b-122">If a user with full permissions begins a chat with a restricted user, limited users can be brought into the conversation.</span></span> <span data-ttu-id="9e00b-123">このアクセスは、限定されたユーザーと制限されたユーザーの間のコラボレーションを監視するのに完全な権限を持つユーザーが存在するため可能です。</span><span class="sxs-lookup"><span data-stu-id="9e00b-123">This access happens because a user with full permissions is present to supervise collaboration between limited and restricted users.</span></span>

- <span data-ttu-id="9e00b-124">制限付きアクセス許可: このロールは、監督が必要なユーザーに最適です。</span><span class="sxs-lookup"><span data-stu-id="9e00b-124">Restricted permissions: This role is ideal for users who need to be supervised.</span></span> <span data-ttu-id="9e00b-125">完全な権限を持つユーザーとのみチャットを開始できます。</span><span class="sxs-lookup"><span data-stu-id="9e00b-125">They can only start chats with users who have full permissions.</span></span> <span data-ttu-id="9e00b-126">完全な権限を持つユーザーが招待する会話に参加できます。</span><span class="sxs-lookup"><span data-stu-id="9e00b-126">They can participate in any conversation that a user with full permissions invites them to.</span></span> <span data-ttu-id="9e00b-127">フェデレーション チャットの場合、制限されたユーザーは、制限されたユーザーのテナントからの完全な権限を持つユーザーによってのみチャットに追加されます。</span><span class="sxs-lookup"><span data-stu-id="9e00b-127">In federated chat cases, restricted users can only be added to chats by a user with full permissions who is from the restricted user’s tenant.</span></span>

<span data-ttu-id="9e00b-128">ユーザーのチャットアクセス許可ロールを設定するには、管理ポータルの [メッセージング ポリシー] オプションにある [チャットのアクセス許可Teams使用します。</span><span class="sxs-lookup"><span data-stu-id="9e00b-128">To set your users’ chat permission role, use the **Chat permissions role** policy found within your Messaging policy options in the Teams admin portal.</span></span> <span data-ttu-id="9e00b-129">PowerShell を使用して、値が完全、限定、または制限の ChatPermissionRole ポリシーを使用して役割を定義できます。</span><span class="sxs-lookup"><span data-stu-id="9e00b-129">You can use PowerShell to define roles using the ChatPermissionRole policy with the values Full, Limited, or Restricted.</span></span> <span data-ttu-id="9e00b-130">このポリシーは [CsTeamsMessagingPolicy の下に置かされています](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="9e00b-130">This policy is under [CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps).</span></span>

<span data-ttu-id="9e00b-131">テナント内のゲストに役割を割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="9e00b-131">Roles can't be assigned to guests in your tenant.</span></span> <span data-ttu-id="9e00b-132">ゲストには限定された役割が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="9e00b-132">Guests are assigned the limited role.</span></span>

## <a name="allow-supervised-chat"></a><span data-ttu-id="9e00b-133">監視ありチャットを許可する</span><span class="sxs-lookup"><span data-stu-id="9e00b-133">Allow supervised chat</span></span>

<span data-ttu-id="9e00b-134">監視ありチャットは、テナントに対して既定で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="9e00b-134">Supervised chat is disabled by default for your tenant.</span></span> <span data-ttu-id="9e00b-135">ユーザーのチャットアクセス許可ロールを設定した後、組織全体の設定 Teams 設定 に移動し、[ロールベースのチャットアクセス許可ポリシー] を [オン] に設定することで、テナント内で教師ありチャットを  >  有効 **にできます**。 </span><span class="sxs-lookup"><span data-stu-id="9e00b-135">After you've set chat permission roles for your users, you can enable supervised chat within your tenant by going to **Org-wide settings** > **Teams Settings** and setting **Role-based chat permissions** policy to **On**.</span></span> <span data-ttu-id="9e00b-136">また、PowerShell を使用して、AllowRoleBasedChatPermissions を True に設定することにより、監視ありチャットを有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="9e00b-136">You can also use PowerShell to enable Supervised Chat by setting AllowRoleBasedChatPermissions to True.</span></span> <span data-ttu-id="9e00b-137">このコマンドレットは [CsTeamsClientConfiguration の下に置かされています](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="9e00b-137">This cmdlet is under [CsTeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps).</span></span>

<span data-ttu-id="9e00b-138">監視ありチャットは、テナント内のすべてのユーザーに対して有効にする必要があり、一部のユーザーに対してのみ有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="9e00b-138">Supervised chat must be enabled for all users in the tenant and cannot be enabled for only a portion of your users.</span></span>

<span data-ttu-id="9e00b-139">**チャットを有効にする**</span><span class="sxs-lookup"><span data-stu-id="9e00b-139">**Enable chat**</span></span>

<span data-ttu-id="9e00b-140">Teams 管理センターで利用可能な既存のチャット ポリシーを使用して、すべてのユーザーのチャットを有効にします。</span><span class="sxs-lookup"><span data-stu-id="9e00b-140">Enable chat for all your users using the existing Chat policy available in Teams admin center.</span></span>

<span data-ttu-id="9e00b-141">**監視ありチャットを維持する**</span><span class="sxs-lookup"><span data-stu-id="9e00b-141">**Maintain supervised chats**</span></span>

<span data-ttu-id="9e00b-142">監視ありチャットを最初に有効にした後、環境内のチャットが引き続き監視対象になるようにするには、いくつかの操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e00b-142">After supervised chat is initially enabled, you'll need to do a few things to ensure that the chats in your environment remain supervised:</span></span>

- <span data-ttu-id="9e00b-143">テナントに参加する新しいユーザーに適切な役割を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="9e00b-143">Assign appropriate roles to any new users that join your tenant.</span></span> <span data-ttu-id="9e00b-144">既定では、ユーザーには制限された役割が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="9e00b-144">By default, users will be assigned a restricted role.</span></span>

- <span data-ttu-id="9e00b-145">完全な権限を持つユーザーがテナントを離れるか、テナントから削除された場合、彼らが監督していたチャットは無人のままになります。</span><span class="sxs-lookup"><span data-stu-id="9e00b-145">If a user with full permissions leaves or is removed from a tenant, the chats they were supervising will be left unattended.</span></span> <span data-ttu-id="9e00b-146">元のユーザーを削除する前に、チャットの監視を維持するため、完全な権限を持つ別のユーザーがこれらの会話に追加されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9e00b-146">Before you remove the original user, ensure that another user with full permissions is added to these conversations so that the chat can remain supervised.</span></span> <span data-ttu-id="9e00b-147">元のスーパーバイザーが削除されると、新しい参加者を会話に追加することはできませんが、現在の参加者は引き続きコミュニケーションできます。</span><span class="sxs-lookup"><span data-stu-id="9e00b-147">Once the original supervisor is removed, new participants can't be added to the conversation, but current participants can continue to communicate.</span></span>
