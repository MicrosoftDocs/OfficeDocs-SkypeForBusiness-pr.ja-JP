---
title: 常設チャットのカテゴリ
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatCategory
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6875d930-7502-4e47-bdb3-45eaeb065350
description: '[常設チャット] ページの [カテゴリ] セクションを使用して、カテゴリを構成できます。 常設チャット ルーム カテゴリは、チャット ルームを整理する論理的な構造です。 カテゴリは、チャット ルームの作成やチャット ルームへの参加を許可するユーザーとユーザー グループを制御するアクセス制御リスト (ACL) の既定のセットを定義します。 カテゴリを使用して、組織内の異なる部門間に倫理的境界を設置できます。'
ms.openlocfilehash: f7718a5d6cc92c0036f28843d21c4c349c0bc38d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803747"
---
# <a name="persistent-chat-category"></a><span data-ttu-id="d8803-106">常設チャットのカテゴリ</span><span class="sxs-lookup"><span data-stu-id="d8803-106">Persistent Chat Category</span></span>
 
<span data-ttu-id="d8803-107">[常設チャット] **ページの** [カテゴリ] セクション **を使用** して、カテゴリを構成できます。</span><span class="sxs-lookup"><span data-stu-id="d8803-107">You can use the **Category** section of the **Persistent Chat** page to configure categories.</span></span> <span data-ttu-id="d8803-108">常設チャット ルーム カテゴリは、チャット ルームを整理する論理的な構造です。</span><span class="sxs-lookup"><span data-stu-id="d8803-108">A Persistent Chat room category is a logical structure for organizing chat rooms.</span></span> <span data-ttu-id="d8803-109">カテゴリは、チャット ルームの作成やチャット ルームへの参加を許可するユーザーとユーザー グループを制御するアクセス制御リスト (ACL) の既定のセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="d8803-109">A category defines a default set of access control lists (ACLs) for controlling the users and user groups who may create or join the chat rooms.</span></span> <span data-ttu-id="d8803-110">カテゴリを使用して、組織内の異なる部門間に倫理的境界を設置できます。</span><span class="sxs-lookup"><span data-stu-id="d8803-110">You can use categories enforce ethical walls between different subdivisions within their organizations.</span></span>
  
<span data-ttu-id="d8803-111">チャット ルーム カテゴリには、チャット ルームを含めることはできますが、それ以外のカテゴリを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="d8803-111">Chat room categories may contain chat rooms, but not other categories.</span></span> <span data-ttu-id="d8803-112">各カテゴリは、Name や Description などのメタデータを使用してコンテンツ _を__記述します_。</span><span class="sxs-lookup"><span data-stu-id="d8803-112">Each category describes its contents with metadata, such as  _Name_ and _Description_.</span></span> <span data-ttu-id="d8803-113">さらに、カテゴリには、チャット ルームで招待またはファイルのアップロードが許可される場合や、チャット履歴が含まれている場合など、カテゴリに属するチャットルームの動作を制御するために設定できるプロパティ _があります。_</span><span class="sxs-lookup"><span data-stu-id="d8803-113">In addition, the category has properties which can be set to control the behavior of the chat rooms belonging to it, such as if the chat rooms allow  _Invitations_ or _File Uploads_, or contain  _Chat History_.</span></span>
  
<span data-ttu-id="d8803-114">新しいカテゴリを作成するには [、「Manage categories in Persistent Chat Server in Skype for Business Server 2015」](../../manage/persistent-chat/categories.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8803-114">To create a new category, see [Manage categories in Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/categories.md).</span></span> <span data-ttu-id="d8803-115">常設チャット管理者の場合は、コントロール パネルまたはカスタム コマンドレットを使用してWindows PowerShellできます。</span><span class="sxs-lookup"><span data-stu-id="d8803-115">If you are a Persistent Chat Administrator, you can create categories by using the control panel or Windows PowerShell cmdlets.</span></span>
  
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="d8803-116">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="d8803-116">Tasks that you can perform</span></span>

<span data-ttu-id="d8803-117">[**カテゴリ**] ページでは次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="d8803-117">You can perform the following tasks on the **Category** page:</span></span>
  
- <span data-ttu-id="d8803-118">新しいカテゴリを作成または編集する</span><span class="sxs-lookup"><span data-stu-id="d8803-118">Create or edit a new category</span></span>
    
- <span data-ttu-id="d8803-119">あるカテゴリから別のカテゴリにチャット ルームを移動する</span><span class="sxs-lookup"><span data-stu-id="d8803-119">Move a chat room from one category to another</span></span>
    
- <span data-ttu-id="d8803-120">チャット ルームまたはカテゴリを削除する</span><span class="sxs-lookup"><span data-stu-id="d8803-120">Delete a chat room or category</span></span>
    
## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="d8803-121">チャット ルームのカテゴリを構成するには</span><span class="sxs-lookup"><span data-stu-id="d8803-121">To configure categories for chat rooms</span></span>

1. <span data-ttu-id="d8803-122">CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="d8803-122">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d8803-123">[スタート **] メニュー** から Skype for Business Server コントロール パネルを選択するか、ブラウザー ウィンドウを開いて管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="d8803-123">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="d8803-124">左側のナビゲーション バーで [**常設チャット**] をクリックして、[**分類**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8803-124">In the left navigation bar, click **Persistent Chat**, and then click **Category**.</span></span>
    
    <span data-ttu-id="d8803-125">複数の常設チャット サーバー プール展開の場合は、ドロップダウン リストから適切なプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="d8803-125">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>
    
4. <span data-ttu-id="d8803-126">[**分類**] ページで、[**新規**] または [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8803-126">On the **Category** page, click **New** or **Edit**.</span></span>
    
5. <span data-ttu-id="d8803-127">[ **サービスの選択]** で、カテゴリを作成する必要がある常設チャット サーバー プールに対応するサービスを選択します。</span><span class="sxs-lookup"><span data-stu-id="d8803-127">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool on which the category needs to be created.</span></span> <span data-ttu-id="d8803-128">このサービスは、常設チャット (クライアント) がカテゴリが属するプールを識別するために使用する常設チャット サーバー プールです。</span><span class="sxs-lookup"><span data-stu-id="d8803-128">The service is the Persistent Chat Server pool that the Persistent Chat (client) uses to identify which pool the category belongs to.</span></span> <span data-ttu-id="d8803-129">カテゴリは、1 つの常設チャット サーバー プールにのみ属し、別の常設チャット サーバー プールに移動したり、別のプールと共有したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="d8803-129">A category can belong to only one Persistent Chat Server pool, and cannot be moved to another one, or shared with another pool.</span></span>
    
6. <span data-ttu-id="d8803-130">[**新規 分類**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="d8803-130">In **New Category**, do the following:</span></span>
    
7. <span data-ttu-id="d8803-131">[**名前**] に、新しいルーム カテゴリの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="d8803-131">In **Name**, specify a name for the new room category.</span></span>
    
8. <span data-ttu-id="d8803-132">[**説明**] に、ルーム カテゴリの説明 (Contoso 用のルーム カテゴリなど) を詳しく指定します。</span><span class="sxs-lookup"><span data-stu-id="d8803-132">In **Description**, provide a detailed description for the room category (for example, a room category for Contoso).</span></span>
    
9. <span data-ttu-id="d8803-133">このカテゴリに属するチャット ルームに対して招待を有効にできるかどうかを制御するには、[招待を有効にする] チェック ボックス **をオンまたは** オフにします。</span><span class="sxs-lookup"><span data-stu-id="d8803-133">To control whether invitations can be enabled for chat rooms that belong to this category, select or clear the **Enable invitations** check box.</span></span> <span data-ttu-id="d8803-134">選択した場合、このカテゴリのルームには招待がオンまたはオフの場合があります。オフにした場合、このカテゴリのルームには招待を許可されません。</span><span class="sxs-lookup"><span data-stu-id="d8803-134">If selected, rooms in this category may have invitations on or off; if cleared, the rooms in this category are not allowed to have invitations.</span></span> <span data-ttu-id="d8803-135">ルームに招待がある場合、新しいメンバーがルームに追加された場合、常設チャット クライアントで新しいルームの通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="d8803-135">If a room has invitations on, when a new member is added to a room, he or she gets a notification of the new room in their Persistent Chat client.</span></span>
    
10. <span data-ttu-id="d8803-p107">このカテゴリに属するチャット ルームでのファイルのアップロードを制御するには、[**ファイルのアップロードを有効にする**] チェック ボックスをオンまたはオフにします。オンにした場合は、このカテゴリのルームではファイルのアップロードを有効または無効にできます。オフにした場合は、このカテゴリのルームではファイルのアップロードを有効にできません。</span><span class="sxs-lookup"><span data-stu-id="d8803-p107">To control file uploads in chat rooms belonging to this category, select or clear the **Enable file upload** check box. If selected, the rooms of this category can enable or disable file uploads; if cleared, the rooms of this category are not allowed to have file uploads.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="d8803-138">この設定は、カスタム アプリケーションまたは Office Communications Server 2007 R2 グループ チャット サーバーまたは Lync Server 2010 を使用する以前のグループ チャット クライアントがファイルをルームに投稿できる場合に、サーバーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="d8803-138">This setting is enforced on the server because custom applications or previous Group Chat clients that use Office Communications Server 2007 R2 Group Chat Server or Lync Server 2010, Group Chat can post files to a room.</span></span> <span data-ttu-id="d8803-139">Lync 2013 クライアントにはファイルのアップロード/ダウンロード機能はないので、純粋な Lync 2013 展開または Lync 2013 クライアントを使用している場合は、常設チャット サーバーのチャット ルームにファイルを投稿できません。</span><span class="sxs-lookup"><span data-stu-id="d8803-139">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span> 
  
11. <span data-ttu-id="d8803-140">チャット履歴を制御するには、[チャット履歴を有効にする] **チェック ボックスをオンまたは** オフにします。</span><span class="sxs-lookup"><span data-stu-id="d8803-140">To control chat history, select or clear the **Enable chat history** check box.</span></span> <span data-ttu-id="d8803-141">オンにした場合、ルーム チャットは永続的になります。それ以外の場合、チャット メッセージは保持されません。</span><span class="sxs-lookup"><span data-stu-id="d8803-141">If selected, room chats become persistent; otherwise, chat messages are not persisted.</span></span> <span data-ttu-id="d8803-142">コンプライアンスを有効にすると、ルーム チャットはコンプライアンスに従って保存されますが、ユーザーは古いメッセージにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="d8803-142">If compliance is enabled, room chats will be saved in compliance, but users will not be able to access older messages.</span></span> <span data-ttu-id="d8803-143">このオプションは、チャット履歴を保持する必要がなされない、リアルタイムのアドホック コラボレーション用に指定されたルームに使用できます。</span><span class="sxs-lookup"><span data-stu-id="d8803-143">This option can be used for rooms designated for real-time, ad hoc collaborations that don't need chat history to be persisted.</span></span>
    
12. <span data-ttu-id="d8803-144">[**編集 分類**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="d8803-144">In **Edit Category**, do the following:</span></span>
    
    - <span data-ttu-id="d8803-145">[**メンバーシップ**] の[許可されるメンバー] セクションで、カテゴリに属するチャット ルームのメンバーとして追加できるユーザーおよび他の Active Directory ドメイン サービス プリンシパル (ユーザー、配布グループ、組織単位など) を追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="d8803-145">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="d8803-146">カテゴリによって許可されるプリンシパルは、カテゴリ内のルームを検索できます (ルームが非表示の場合を指定しない限り、ルームのメンバーだけがディレクトリで検索できます)。</span><span class="sxs-lookup"><span data-stu-id="d8803-146">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>
    
    - <span data-ttu-id="d8803-147">メンバーシップ **の**[拒否されたメンバー] セクションで、ルームから拒否されているメンバーに関連付けられているユーザーおよび他の Active Directory プリンシパルを追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="d8803-147">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>
    
    - <span data-ttu-id="d8803-148">[ **メンバーシップ]** の **[Creators]** セクションで、カテゴリの作成者に関連付けられているユーザーおよび他の Active Directory プリンシパルを追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="d8803-148">In **Membership**, in the **Creators** section, add or remove users and other Active Directory principals associated with creators for the category.</span></span> <span data-ttu-id="d8803-149">作成者は、チャット ルームを作成し、チャット ルームのマネージャーとメンバーを割り当てるためのアクセス許可が与えられているユーザーです。</span><span class="sxs-lookup"><span data-stu-id="d8803-149">A creator is a user who has permissions to create chat rooms and assign chat room managers and members.</span></span>
    
13. <span data-ttu-id="d8803-150">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8803-150">Click **Commit**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d8803-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="d8803-151">See also</span></span>

<span data-ttu-id="d8803-152">常設チャット サーバーの機能の詳細については [、「Plan for Persistent Chat Server in Skype for Business Server 2015,](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md) [Deploy Persistent Chat Server in Skype for Business Server 2015,](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)and [Manage Persistent Chat Server in Skype for Business Server 2015」](../../manage/persistent-chat/persistent-chat.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8803-152">For details about Persistent Chat Server features and capabilities, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md), and [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span></span>
  

