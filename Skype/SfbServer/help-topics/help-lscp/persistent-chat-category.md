---
title: 常設チャットのカテゴリ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatCategory
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6875d930-7502-4e47-bdb3-45eaeb065350
description: '[常設チャット] ページの [カテゴリ] セクションを使用してカテゴリを構成できます。 常設チャットルームカテゴリは、チャットルームを整理するための論理的な構造です。 カテゴリは、チャット ルームの作成やチャット ルームへの参加を許可するユーザーとユーザー グループを制御するアクセス制御リスト (ACL) の既定のセットを定義します。 カテゴリを使用して、組織内の異なる部門間に倫理的境界を設置できます。'
ms.openlocfilehash: fc430c7d61ad4662d28f81594d59bf95d03f84c8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302665"
---
# <a name="persistent-chat-category"></a><span data-ttu-id="d9299-106">常設チャットのカテゴリ</span><span class="sxs-lookup"><span data-stu-id="d9299-106">Persistent Chat Category</span></span>
 
<span data-ttu-id="d9299-107">[**常設チャット**] ページの [**カテゴリ**] セクションを使用してカテゴリを構成できます。</span><span class="sxs-lookup"><span data-stu-id="d9299-107">You can use the **Category** section of the **Persistent Chat** page to configure categories.</span></span> <span data-ttu-id="d9299-108">常設チャットルームカテゴリは、チャットルームを整理するための論理的な構造です。</span><span class="sxs-lookup"><span data-stu-id="d9299-108">A Persistent Chat room category is a logical structure for organizing chat rooms.</span></span> <span data-ttu-id="d9299-109">カテゴリは、チャット ルームの作成やチャット ルームへの参加を許可するユーザーとユーザー グループを制御するアクセス制御リスト (ACL) の既定のセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="d9299-109">A category defines a default set of access control lists (ACLs) for controlling the users and user groups who may create or join the chat rooms.</span></span> <span data-ttu-id="d9299-110">カテゴリを使用して、組織内の異なる部門間に倫理的境界を設置できます。</span><span class="sxs-lookup"><span data-stu-id="d9299-110">You can use categories enforce ethical walls between different subdivisions within their organizations.</span></span>
  
<span data-ttu-id="d9299-111">チャットルームのカテゴリには、チャットルームを含めることができますが、他のカテゴリを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="d9299-111">Chat room categories may contain chat rooms, but not other categories.</span></span> <span data-ttu-id="d9299-112">各カテゴリは、_名前_や_説明_などのメタデータを使ってコンテンツについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d9299-112">Each category describes its contents with metadata, such as  _Name_ and _Description_.</span></span> <span data-ttu-id="d9299-113">さらに、このカテゴリにはプロパティがあり、チャットルームで_招待_または_ファイルのアップロード_が許可されているか、_チャット履歴_が含まれているかなど、チャットルームの動作を制御するために設定できます。</span><span class="sxs-lookup"><span data-stu-id="d9299-113">In addition, the category has properties which can be set to control the behavior of the chat rooms belonging to it, such as if the chat rooms allow  _Invitations_ or _File Uploads_, or contain  _Chat History_.</span></span>
  
<span data-ttu-id="d9299-114">新しいカテゴリを作成するには、「 [Skype For Business server 2015 の常設チャットサーバーでカテゴリを管理](../../manage/persistent-chat/categories.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9299-114">To create a new category, see [Manage categories in Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/categories.md).</span></span> <span data-ttu-id="d9299-115">常設チャットの管理者である場合は、コントロールパネルまたは Windows PowerShell コマンドレットを使用してカテゴリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d9299-115">If you are a Persistent Chat Administrator, you can create categories by using the control panel or Windows PowerShell cmdlets.</span></span>
  
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="d9299-116">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="d9299-116">Tasks that you can perform</span></span>

<span data-ttu-id="d9299-117">[**カテゴリ**] ページでは次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="d9299-117">You can perform the following tasks on the **Category** page:</span></span>
  
- <span data-ttu-id="d9299-118">新しいカテゴリの作成または編集</span><span class="sxs-lookup"><span data-stu-id="d9299-118">Create or edit a new category</span></span>
    
- <span data-ttu-id="d9299-119">1 つのカテゴリから他のカテゴリへのチャット ルームの移動</span><span class="sxs-lookup"><span data-stu-id="d9299-119">Move a chat room from one category to another</span></span>
    
- <span data-ttu-id="d9299-120">チャット ルームまたはカテゴリの削除</span><span class="sxs-lookup"><span data-stu-id="d9299-120">Delete a chat room or category</span></span>
    
## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="d9299-121">チャット ルームのカテゴリを構成するには</span><span class="sxs-lookup"><span data-stu-id="d9299-121">To configure categories for chat rooms</span></span>

1. <span data-ttu-id="d9299-122">CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="d9299-122">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d9299-123">[**スタート**] メニューで、[Skype For business Server] コントロールパネルを選択するか、ブラウザーウィンドウを開き、管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="d9299-123">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="d9299-124">左側のナビゲーション バーで [**常設チャット**] をクリックして、[**分類**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9299-124">In the left navigation bar, click **Persistent Chat**, and then click **Category**.</span></span>
    
    <span data-ttu-id="d9299-125">複数の常設チャットサーバープールの展開の場合、ドロップダウンリストから適切なプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="d9299-125">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>
    
4. <span data-ttu-id="d9299-126">[**カテゴリ**] ページで、[**新規**] または [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9299-126">On the **Category** page, click **New** or **Edit**.</span></span>
    
5. <span data-ttu-id="d9299-127">[**サービスの選択**] で、カテゴリの作成が必要な常設チャットサーバープールに対応するサービスを選びます。</span><span class="sxs-lookup"><span data-stu-id="d9299-127">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool on which the category needs to be created.</span></span> <span data-ttu-id="d9299-128">[サービス] は、カテゴリが属しているプールを特定するために常設チャット (クライアント) で使用される常設チャットサーバープールです。</span><span class="sxs-lookup"><span data-stu-id="d9299-128">The service is the Persistent Chat Server pool that the Persistent Chat (client) uses to identify which pool the category belongs to.</span></span> <span data-ttu-id="d9299-129">カテゴリは、1つの常設チャットサーバープールにのみ属すことができ、別のプールに移動したり、別のプールで共有したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="d9299-129">A category can belong to only one Persistent Chat Server pool, and cannot be moved to another one, or shared with another pool.</span></span>
    
6. <span data-ttu-id="d9299-130">[**新しいカテゴリ**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="d9299-130">In **New Category**, do the following:</span></span>
    
7. <span data-ttu-id="d9299-131">[**名前**] に、新しいルーム カテゴリの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="d9299-131">In **Name**, specify a name for the new room category.</span></span>
    
8. <span data-ttu-id="d9299-132">[**説明**] に、ルーム カテゴリの詳細を指定します (たとえば「Contoso 用のカテゴリ」と指定します)。</span><span class="sxs-lookup"><span data-stu-id="d9299-132">In **Description**, provide a detailed description for the room category (for example, a room category for Contoso).</span></span>
    
9. <span data-ttu-id="d9299-133">このカテゴリに属するチャットルームに対して招待を有効にできるかどうかを制御するには、[**招待を有効に**する] チェックボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="d9299-133">To control whether invitations can be enabled for chat rooms that belong to this category, select or clear the **Enable invitations** check box.</span></span> <span data-ttu-id="d9299-134">選択されている場合、このカテゴリの会議室の出席依頼のオンとオフを切り替えることができます。この設定をオフにすると、このカテゴリのルームに招待状は許可されません。</span><span class="sxs-lookup"><span data-stu-id="d9299-134">If selected, rooms in this category may have invitations on or off; if cleared, the rooms in this category are not allowed to have invitations.</span></span> <span data-ttu-id="d9299-135">会議室が招待されている場合、会議室に新しいメンバーが追加されると、そのユーザーは、常設チャットクライアントで新しい会議室の通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="d9299-135">If a room has invitations on, when a new member is added to a room, he or she gets a notification of the new room in their Persistent Chat client.</span></span>
    
10. <span data-ttu-id="d9299-p107">このカテゴリに属するチャット ルームでファイルのアップロードを制御するには、[**ファイルのアップロードを有効にする**] チェック ボックスをオンまたはオフにします。オンにした場合、このカテゴリのルームでは、ファイルのアップロードを有効または無効にできます。オフにした場合、このカテゴリのルームではファイルのアップロードは許可されません。</span><span class="sxs-lookup"><span data-stu-id="d9299-p107">To control file uploads in chat rooms belonging to this category, select or clear the **Enable file upload** check box. If selected, the rooms of this category can enable or disable file uploads; if cleared, the rooms of this category are not allowed to have file uploads.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="d9299-138">この設定は、Office Communications Server 2007 R2 グループチャットサーバーまたは Lync Server 2010 を使っているカスタムアプリケーションまたは以前のグループチャットクライアントで、グループチャットで会議室にファイルを投稿できます。</span><span class="sxs-lookup"><span data-stu-id="d9299-138">This setting is enforced on the server because custom applications or previous Group Chat clients that use Office Communications Server 2007 R2 Group Chat Server or Lync Server 2010, Group Chat can post files to a room.</span></span> <span data-ttu-id="d9299-139">Lync 2013 クライアントには、ファイルのアップロード/ダウンロード機能がありません。そのため、Lync 2013 の展開または Lync 2013 クライアントが純粋にインストールされている場合は、常設チャットサーバーのチャットルームにファイルを投稿することはできません。</span><span class="sxs-lookup"><span data-stu-id="d9299-139">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span> 
  
11. <span data-ttu-id="d9299-140">チャット履歴を管理するには、[**チャット履歴を有効に**する] チェックボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="d9299-140">To control chat history, select or clear the **Enable chat history** check box.</span></span> <span data-ttu-id="d9299-141">選択されている場合、ルームチャットは永続的になります。それ以外の場合は、チャットメッセージは保持されません。</span><span class="sxs-lookup"><span data-stu-id="d9299-141">If selected, room chats become persistent; otherwise, chat messages are not persisted.</span></span> <span data-ttu-id="d9299-142">コンプライアンスが有効になっている場合、ルームのチャットはコンプライアンスに保存されますが、ユーザーは古いメッセージにアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="d9299-142">If compliance is enabled, room chats will be saved in compliance, but users will not be able to access older messages.</span></span> <span data-ttu-id="d9299-143">このオプションは、チャット履歴を保持する必要のないリアルタイムの共同作業用に指定された会議室に使用できます。</span><span class="sxs-lookup"><span data-stu-id="d9299-143">This option can be used for rooms designated for real-time, ad hoc collaborations that don't need chat history to be persisted.</span></span>
    
12. <span data-ttu-id="d9299-144">[**カテゴリの編集**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="d9299-144">In **Edit Category**, do the following:</span></span>
    
    - <span data-ttu-id="d9299-145">[許可された**メンバー** ] セクションの [**メンバーシップ**] で、チャットルームのメンバーとして追加することを許可されているユーザーおよびその他の Active Directory ドメインサービスプリンシパル (ユーザー、配布グループ、組織単位など) を追加または削除します。カテゴリに属している。</span><span class="sxs-lookup"><span data-stu-id="d9299-145">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="d9299-146">カテゴリで許可されているプリンシパルは、カテゴリ内のルームを検索することができます (ルームが非表示になっている場合を除き、ルームのメンバーだけがディレクトリ内で検索できます)。</span><span class="sxs-lookup"><span data-stu-id="d9299-146">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>
    
    - <span data-ttu-id="d9299-147">[**メンバーシップ**] の [**拒否するメンバー** ] セクションで、会議室から拒否されているメンバーに関連付けられているユーザーおよびその他の Active Directory プリンシパルを追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="d9299-147">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>
    
    - <span data-ttu-id="d9299-148">[**メンバーシップ**] の [ \*\*\*\* 作成者] セクションで、カテゴリの作成者に関連付けられているユーザーおよびその他の Active Directory プリンシパルを追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="d9299-148">In **Membership**, in the **Creators** section, add or remove users and other Active Directory principals associated with creators for the category.</span></span> <span data-ttu-id="d9299-149">作成者は、チャット ルームを作成し、チャット ルームのマネージャーとメンバーを割り当てることができるアクセス許可を持つユーザーです。</span><span class="sxs-lookup"><span data-stu-id="d9299-149">A creator is a user who has permissions to create chat rooms and assign chat room managers and members.</span></span>
    
13. <span data-ttu-id="d9299-150">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9299-150">Click **Commit**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d9299-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="d9299-151">See also</span></span>

<span data-ttu-id="d9299-152">常設チャットサーバーの機能と機能について詳しくは、「 [skype For Business server 2015 での常設チャットサーバーの計画](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)」、「 [Skype for business server 2015 での常設](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)チャットサーバーの展開」、「[常設チャットサーバーの管理」をご覧ください。Skype for Business Server 2015 の場合](../../manage/persistent-chat/persistent-chat.md)</span><span class="sxs-lookup"><span data-stu-id="d9299-152">For details about Persistent Chat Server features and capabilities, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md), and [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span></span>
  

