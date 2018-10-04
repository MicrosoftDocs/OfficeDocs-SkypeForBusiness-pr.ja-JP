---
title: 常設チャット カテゴリ メイン ページ
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatCategoryMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b71c6e6f-681c-4230-954d-3e95ab64ca00
description: '[常設チャット] ページの [カテゴリ] セクションを使用してカテゴリを構成できます。 永続的なチャット ルームのカテゴリは、チャット ルームを整理するための論理構造です。 カテゴリは、チャット ルームの作成やチャット ルームへの参加を許可するユーザーとユーザー グループを制御するアクセス制御リスト (ACL) の既定のセットを定義します。 カテゴリを使用して、組織内の異なる部門間に倫理的境界を設置できます。'
ms.openlocfilehash: 3fdc450ee913e20885e8582bff4ba0dbdcc70867
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "25371937"
---
# <a name="persistent-chat-category-main-page"></a><span data-ttu-id="01565-106">常設チャット カテゴリ メイン ページ</span><span class="sxs-lookup"><span data-stu-id="01565-106">Persistent Chat Category Main Page</span></span>
 
<span data-ttu-id="01565-107">[**常設チャット**] ページの [**カテゴリ**] セクションを使用してカテゴリを構成できます。</span><span class="sxs-lookup"><span data-stu-id="01565-107">You can use the **Category** section of the **Persistent Chat** page to configure categories.</span></span> <span data-ttu-id="01565-108">永続的なチャット ルームのカテゴリは、チャット ルームを整理するための論理構造です。</span><span class="sxs-lookup"><span data-stu-id="01565-108">A Persistent Chat room category is a logical structure for organizing chat rooms.</span></span> <span data-ttu-id="01565-109">カテゴリは、チャット ルームの作成やチャット ルームへの参加を許可するユーザーとユーザー グループを制御するアクセス制御リスト (ACL) の既定のセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="01565-109">A category defines a default set of access control lists (ACLs) for controlling the users and user groups who may create or join the chat rooms.</span></span> <span data-ttu-id="01565-110">カテゴリを使用して、組織内の異なる部門間に倫理的境界を設置できます。</span><span class="sxs-lookup"><span data-stu-id="01565-110">You can use categories enforce ethical walls between different subdivisions within their organizations.</span></span>
  
<span data-ttu-id="01565-111">チャット ルームのカテゴリは、チャット ルーム、その他のカテゴリではないに含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="01565-111">Chat room categories may contain chat rooms, but not other categories.</span></span> <span data-ttu-id="01565-112">各カテゴリでは、その_名前_や_説明_などのメタデータの内容について説明します。</span><span class="sxs-lookup"><span data-stu-id="01565-112">Each category describes its contents with metadata, such as  _Name_ and _Description_.</span></span> <span data-ttu-id="01565-113">さらに、カテゴリにはプロパティが所属する、チャット ルームの動作を制御する設定することができる場合などチャット ルーム_への招待_または_ファイルのアップロード_、または_チャットの履歴_が含まれています。</span><span class="sxs-lookup"><span data-stu-id="01565-113">In addition, the category has properties which can be set to control the behavior of the chat rooms belonging to it, such as if the chat rooms allow  _Invitations_ or _File Uploads_, or contain  _Chat History_.</span></span>
  
<span data-ttu-id="01565-114">新しいカテゴリを作成するには、[ビジネス サーバー 2015 の Skype での永続的なチャット サーバーの管理のカテゴリ](../../manage/persistent-chat/categories.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01565-114">To create a new category, see [Manage categories in Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/categories.md).</span></span> <span data-ttu-id="01565-115">永続的なチャットの管理者は、コントロール パネルまたは Windows PowerShell コマンドレットを使用してカテゴリを作成します。</span><span class="sxs-lookup"><span data-stu-id="01565-115">If you are a Persistent Chat Administrator, you can create categories by using the control panel or Windows PowerShell cmdlets.</span></span>
  
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="01565-116">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="01565-116">Tasks that you can perform</span></span>

<span data-ttu-id="01565-117">[**カテゴリ**] ページでは次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="01565-117">You can perform the following tasks on the **Category** page:</span></span>
  
- <span data-ttu-id="01565-118">新しいカテゴリの作成または編集</span><span class="sxs-lookup"><span data-stu-id="01565-118">Create or edit a new category</span></span>
    
- <span data-ttu-id="01565-119">1 つのカテゴリから他のカテゴリへのチャット ルームの移動</span><span class="sxs-lookup"><span data-stu-id="01565-119">Move a chat room from one category to another</span></span>
    
- <span data-ttu-id="01565-120">チャット ルームまたはカテゴリの削除</span><span class="sxs-lookup"><span data-stu-id="01565-120">Delete a chat room or category</span></span>
    
## <a name="to-configure-categories-for-persistent-chat-rooms"></a><span data-ttu-id="01565-121">永続的なチャット ルームのカテゴリを構成するのには</span><span class="sxs-lookup"><span data-stu-id="01565-121">To configure categories for Persistent Chat rooms</span></span>

1. <span data-ttu-id="01565-122">CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="01565-122">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="01565-123">**[スタート**] メニューから、Skype ビジネス サーバーのコントロール パネルのまたはブラウザー ウィンドウを開きし、管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="01565-123">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="01565-124">.</span><span class="sxs-lookup"><span data-stu-id="01565-124"></span></span>
    
3. <span data-ttu-id="01565-125">左側のナビゲーション バーで [**常設チャット**] をクリックして、[**分類**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="01565-125">In the left navigation bar, click **Persistent Chat**, and then click **Category**.</span></span>
    
    <span data-ttu-id="01565-126">複数の永続的なチャット サーバー プールの展開には、ドロップ ダウン リストから適切なプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="01565-126">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>
    
4. <span data-ttu-id="01565-127">[**カテゴリ**] ページで、[**新規**] または [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="01565-127">On the **Category** page, click **New** or **Edit**.</span></span>
    
5. <span data-ttu-id="01565-128">[**サービスの選択**] で、カテゴリの作成が必要な永続的なチャット サーバー プールに対応するサービスを選択します。</span><span class="sxs-lookup"><span data-stu-id="01565-128">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool on which the category needs to be created.</span></span> <span data-ttu-id="01565-129">サービスは、プールのカテゴリを識別するのには、永続的なチャット (クライアント) を使用するプールが属する永続的なチャット サーバーです。</span><span class="sxs-lookup"><span data-stu-id="01565-129">The service is the Persistent Chat Server pool that the Persistent Chat (client) uses to identify which pool the category belongs to.</span></span> <span data-ttu-id="01565-130">カテゴリを 1 つだけの永続的なチャット サーバー プールに属することができます、別の 1 つに移動またはできません別のプールを共有します。</span><span class="sxs-lookup"><span data-stu-id="01565-130">A category can belong to only one Persistent Chat Server pool, and cannot be moved to another one, or shared with another pool.</span></span>
    
6. <span data-ttu-id="01565-131">[**新しいカテゴリ**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="01565-131">In **New Category**, do the following:</span></span>
    
7. <span data-ttu-id="01565-132">[**名前**] に、新しいルーム カテゴリの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="01565-132">In **Name**, specify a name for the new room category.</span></span>
    
8. <span data-ttu-id="01565-133">[**説明**] に、ルーム カテゴリの詳細を指定します (たとえば「Contoso 用のカテゴリ」と指定します)。</span><span class="sxs-lookup"><span data-stu-id="01565-133">In **Description**, provide a detailed description for the room category (for example, a room category for Contoso).</span></span>
    
9. <span data-ttu-id="01565-134">このカテゴリに属しているチャット ルームに招待状を有効にできるかどうかを制御するには、オンまたは**への招待を有効にする**] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="01565-134">To control whether invitations can be enabled for chat rooms that belong to this category, select or clear the **Enable invitations** check box.</span></span> <span data-ttu-id="01565-135">選択した場合、このカテゴリの部屋があります招待状のオンまたはオフにします。オフの場合、招待状にこのカテゴリのルームを作成できません。</span><span class="sxs-lookup"><span data-stu-id="01565-135">If selected, rooms in this category may have invitations on or off; if cleared, the rooms in this category are not allowed to have invitations.</span></span> <span data-ttu-id="01565-136">ルームにルームに新しいメンバーを追加するときに招待状がある場合、彼または彼女が、永続的なチャット クライアントで新しい部屋の通知を取得します。</span><span class="sxs-lookup"><span data-stu-id="01565-136">If a room has invitations on, when a new member is added to a room, he or she gets a notification of the new room in their Persistent Chat client.</span></span>
    
10. <span data-ttu-id="01565-p108">このカテゴリに属するチャット ルームでファイルのアップロードを制御するには、[**ファイルのアップロードを有効にする**] チェック ボックスをオンまたはオフにします。オンにした場合、このカテゴリのルームでは、ファイルのアップロードを有効または無効にできます。オフにした場合、このカテゴリのルームではファイルのアップロードは許可されません。</span><span class="sxs-lookup"><span data-stu-id="01565-p108">To control file uploads in chat rooms belonging to this category, select or clear the **Enable file upload** check box. If selected, the rooms of this category can enable or disable file uploads; if cleared, the rooms of this category are not allowed to have file uploads.</span></span>
    
11. <span data-ttu-id="01565-139">チャットの履歴を制御するには、オンまたは、[**チャットの履歴を有効にする**] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="01565-139">To control chat history, select or clear the **Enable chat history** check box.</span></span> <span data-ttu-id="01565-140">ルーム チャットが選択されているなる永続的です。それ以外の場合、チャット メッセージは永続化されません。</span><span class="sxs-lookup"><span data-stu-id="01565-140">If selected, room chats become persistent; otherwise, chat messages are not persisted.</span></span> <span data-ttu-id="01565-141">コンプライアンスが有効な場合、ルーム チャットは、コンプライアンスに保存されますが、ユーザーは以前のメッセージにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="01565-141">If compliance is enabled, room chats will be saved in compliance, but users will not be able to access older messages.</span></span> <span data-ttu-id="01565-142">ルームのチャットの履歴を保持する必要はありません、暫定的なリアルタイムのコラボレーション用に指定されたは、このオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="01565-142">This option can be used for rooms designated for real-time, ad hoc collaborations that don't need chat history to be persisted.</span></span>
    
12. <span data-ttu-id="01565-143">[**カテゴリの編集**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="01565-143">In **Edit Category**, do the following:</span></span>
    
    - <span data-ttu-id="01565-144">の**メンバーシップ**、[**許可されたメンバー** ] セクションを追加または削除、ユーザーおよびその他の Active Directory ドメイン サービス プリンシパル (ユーザー、配布グループ、組織単位、およびように) チャット ルームのメンバーとして追加することは許可されません。カテゴリに属しています。</span><span class="sxs-lookup"><span data-stu-id="01565-144">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="01565-145">カテゴリで許可されているプリンシパルは、(ルームが表示されない場合、ルームのメンバーのみ検索できるように、ディレクトリに) しない限り、カテゴリの 2 つの部屋を検索できます。</span><span class="sxs-lookup"><span data-stu-id="01565-145">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>
    
    - <span data-ttu-id="01565-146">の**メンバーシップ**、**拒否メンバー** ] セクションで追加またはユーザーと他の部屋から拒否されているメンバーに関連付けられている Active Directory のプリンシパルを削除します。</span><span class="sxs-lookup"><span data-stu-id="01565-146">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>
    
    - <span data-ttu-id="01565-147">**メンバーシップ**、[**作成者**] セクションで追加またはユーザーとその他のカテゴリの作成者に関連付けられている Active Directory のプリンシパルを削除します。</span><span class="sxs-lookup"><span data-stu-id="01565-147">In **Membership**, in the **Creators** section, add or remove users and other Active Directory principals associated with creators for the category.</span></span> <span data-ttu-id="01565-148">作成者は、チャット ルームを作成し、チャット ルームのマネージャーとメンバーを割り当てることができるアクセス許可を持つユーザーです。</span><span class="sxs-lookup"><span data-stu-id="01565-148">A creator is a user who has permissions to create chat rooms and assign chat room managers and members.</span></span>
    
13. <span data-ttu-id="01565-149">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="01565-149">Click **Commit**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="01565-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="01565-150">See also</span></span>

<span data-ttu-id="01565-151">持続チャット サーバーで永続的なチャット サーバーの機能と機能に関する詳細は、[ビジネス サーバー 2015 の Skype での永続的なチャット サーバーの計画](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)、[ビジネス サーバー 2015 の Skype で永続的なチャット サーバーを展開](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)、および管理を[参照してください。ビジネス サーバー 2015 の Skype で](../../manage/persistent-chat/persistent-chat.md)。</span><span class="sxs-lookup"><span data-stu-id="01565-151">For details about Persistent Chat Server features and capabilities, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md), and [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span></span>
  

