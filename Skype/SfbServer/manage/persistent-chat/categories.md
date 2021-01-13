---
title: Skype for Business Server 2015 での常設チャット サーバーのカテゴリの管理
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b0c834b9-b5c8-41d5-865b-c8b180e76d13
description: '概要: Skype for Business Server 2015 で常設チャット サーバーのカテゴリを管理する方法について学習します。'
ms.openlocfilehash: 648629e42994c59f5d6ba5ee5592729f4dff0bbe
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815127"
---
# <a name="manage-categories-in-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="261db-103">Skype for Business Server 2015 での常設チャット サーバーのカテゴリの管理</span><span class="sxs-lookup"><span data-stu-id="261db-103">Manage categories in Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="261db-104">**概要:** Skype for Business Server 2015 で常設チャット サーバーのカテゴリを管理する方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="261db-104">**Summary:** Learn how to manage Persistent Chat Server categories in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="261db-105">カテゴリは、チャット ルームを整理する論理構造です。</span><span class="sxs-lookup"><span data-stu-id="261db-105">A category is a logical structure for organizing chat rooms.</span></span> <span data-ttu-id="261db-106">カテゴリは、チャット ルームを作成またはチャット ルームに参加できるユーザーおよびユーザー グループを制御するためのアクセス制御リスト (ACL) の既定のセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="261db-106">A category defines a default set of access control lists (ACLs) for controlling the users and user groups who can create or join the chat rooms.</span></span> <span data-ttu-id="261db-107">チャット ルームカテゴリにはチャット ルームが含まれますが、他のカテゴリは含めではありません。</span><span class="sxs-lookup"><span data-stu-id="261db-107">Chat room categories contain chat rooms, but not other categories.</span></span> <span data-ttu-id="261db-108">各カテゴリには、名前や説明などのメタデータを使用してカテゴリの内容が記述されます。</span><span class="sxs-lookup"><span data-stu-id="261db-108">Each category describes its contents with metadata, such as Name and Description.</span></span> <span data-ttu-id="261db-109">カテゴリには、カテゴリに属するチャット ルームの動作を制御するために設定できるプロパティがあります。たとえば、チャット ルームで招待またはファイルのアップロードを許可するか、チャット履歴を含めます。</span><span class="sxs-lookup"><span data-stu-id="261db-109">The category has properties that can be set to control the behavior of the chat rooms belonging to it; for example, whether the chat rooms allow Invitations or File Uploads, or contain Chat History.</span></span> 
  
<span data-ttu-id="261db-110">カテゴリを正しく使用すると、チャット ルームの作成と管理がはるかに簡単になります。</span><span class="sxs-lookup"><span data-stu-id="261db-110">Creating and managing chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="261db-111">常設チャット サーバー管理者は、カテゴリごとに AllowedMembers と Creators を定義できます。また、カテゴリで作成されたチャット ルームに適用される既定のチャット ルームの設定と動作も定義できます。</span><span class="sxs-lookup"><span data-stu-id="261db-111">As a Persistent Chat Server administrator, you can define AllowedMembers and Creators for each category, and also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="261db-112">たとえば、カテゴリの AllowedMembers を contoso.com に設定した場合、Contoso の任意のグループまたはユーザーをそのカテゴリのチャット ルームにメンバーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="261db-112">For example, if you set the category's AllowedMembers to contoso.com, you can add any group or user at Contoso as a member to chat rooms in that category.</span></span> <span data-ttu-id="261db-113">カテゴリの許可メンバーを Sales に設定すると、この配布リスト内のグループとユーザーのみをそのカテゴリのチャット ルームにメンバーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="261db-113">If you set the Allowed Members on a category to Sales, only groups and users in this distribution list can be added as members to chat rooms in that category.</span></span> <span data-ttu-id="261db-114">Creators プロパティを使用すると、そのカテゴリにチャット ルームを作成できるユーザーを制御できます。</span><span class="sxs-lookup"><span data-stu-id="261db-114">The Creators property enables you to control who can create chat rooms in that category.</span></span> <span data-ttu-id="261db-115">チャット ルームが作成されると、AllowedMembers グループのユーザーは、ルームで進行中の管理操作 (メンバーシップの変更や承認など) のマネージャーとして指定できます。</span><span class="sxs-lookup"><span data-stu-id="261db-115">After the chat room is created, anyone from the AllowedMembers group can be designated as a Manager for ongoing management operations on the rooms (for example, membership changes and approval).</span></span>
  
<span data-ttu-id="261db-116">カテゴリの AllowedMembers と Creators を定義すると、次の利点が得られます。</span><span class="sxs-lookup"><span data-stu-id="261db-116">Defining AllowedMembers and Creators for a category has the following benefits:</span></span>
  
- <span data-ttu-id="261db-p103">カテゴリ内のすべてのチャット ルームがカテゴリ レベルの制限のセットにバインドされます。これにより、業務ニーズとアクセス ポリシーに基づいてチャット ルームを分離できます。</span><span class="sxs-lookup"><span data-stu-id="261db-p103">All chat rooms in this category are bound by the restrictions set at the category level. You can use this to segregate chat rooms based on business need and access policies.</span></span>
    
- <span data-ttu-id="261db-119">Creators の一覧に含まれるユーザーが、カテゴリ内に新しいチャット ルームを作成できます。</span><span class="sxs-lookup"><span data-stu-id="261db-119">A user who is in the Creators list can create new chat rooms in that category.</span></span> <span data-ttu-id="261db-120">制限された数の組織内の担当者がチャット ルームを作成できるシステムを実装する場合、このコントロールを使用してその要件を満たします。</span><span class="sxs-lookup"><span data-stu-id="261db-120">If you want to implement a system where a restricted number of personnel in the organization can create chat rooms this control can be used to meet that requirements.</span></span> 
    
<span data-ttu-id="261db-121">カテゴリの作成者として識別されるユーザー、組織単位 (US)、およびユーザー グループは、カテゴリにルームを作成できる唯一の個人およびグループです。</span><span class="sxs-lookup"><span data-stu-id="261db-121">Users, Organization Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category.</span></span> <span data-ttu-id="261db-122">カテゴリを作成したら、カテゴリの AllowedMembers リストからユーザー、US、およびユーザー グループをチャット ルームのマネージャーおよびメンバーとして選択し、ルームを管理および参加できます。</span><span class="sxs-lookup"><span data-stu-id="261db-122">After the category is created, you can choose users, OUs, and user groups from the category's AllowedMembers list as chat room managers and members to manage and participate in the room.</span></span> 
  
<span data-ttu-id="261db-123">カテゴリを構成する前に [、Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md)の常設チャットカテゴリ、チャット ルーム、およびユーザーロールを必ずお読みください。</span><span class="sxs-lookup"><span data-stu-id="261db-123">Before you configure categories, be sure to read [Persistent chat categories, chat rooms, and user roles in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md).</span></span>
  
<span data-ttu-id="261db-124">コントロール パネルを使用するか、次のコマンドレットを使用して、カテゴリをWindows PowerShellできます。</span><span class="sxs-lookup"><span data-stu-id="261db-124">You can configure and manage categories by using the Control Panel or by using Windows PowerShell cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="261db-125">常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="261db-125">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="261db-126">Teams でも同じ機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="261db-126">The same functionality is available in Teams.</span></span> <span data-ttu-id="261db-127">詳細については、「Microsoft Teams のアップグレード [の開始」を参照してください](/microsoftteams/upgrade-start-here)。</span><span class="sxs-lookup"><span data-stu-id="261db-127">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="261db-128">常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、Skype for Business Server 2015 を引き続き使用するかのどちらかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="261db-128">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="configure-categories-by-using-the-control-panel"></a><span data-ttu-id="261db-129">コントロール パネルを使用してカテゴリを構成する</span><span class="sxs-lookup"><span data-stu-id="261db-129">Configure categories by using the Control Panel</span></span>

1. <span data-ttu-id="261db-130">CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="261db-130">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="261db-131">[スタート **] メニューから** Skype for Business Server コントロール パネルを選択するか、ブラウザー ウィンドウを開いて管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="261db-131">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="261db-132">左側のナビゲーション バーで [**常設チャット**] をクリックして、[**分類**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="261db-132">In the left navigation bar, click **Persistent Chat**, and then click **Category**.</span></span>
    
    <span data-ttu-id="261db-133">複数の常設チャット サーバー プール展開の場合は、ドロップダウン リストから適切なプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="261db-133">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>
    
4. <span data-ttu-id="261db-134">[**分類**] ページで、[**新規**] または [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="261db-134">On the **Category** page, click **New** or **Edit**.</span></span>
    
5. <span data-ttu-id="261db-135">[ **サービスの選択]** で、カテゴリを作成する必要がある常設チャット サーバー プールに対応するサービスを選択します。</span><span class="sxs-lookup"><span data-stu-id="261db-135">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool on which the category needs to be created.</span></span> <span data-ttu-id="261db-136">このサービスは、常設チャット クライアントがカテゴリが属するプールを識別するために使用する常設チャット サーバー プールです。</span><span class="sxs-lookup"><span data-stu-id="261db-136">The service is the Persistent Chat Server pool that the Persistent Chat client uses to identify which pool the category belongs to.</span></span> <span data-ttu-id="261db-137">カテゴリは 1 つの常設チャット サーバー プールにのみ属し、別のプールに移動したり、別のプールと共有したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="261db-137">A category can belong to only one Persistent Chat Server pool, and cannot be moved to, or shared with, another pool.</span></span>
    
6. <span data-ttu-id="261db-138">[**新規 分類**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="261db-138">In **New Category**, do the following:</span></span>
    
   - <span data-ttu-id="261db-139">[**名前**] に、新しいルーム カテゴリの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="261db-139">In **Name**, specify a name for the new room category.</span></span>
    
   - <span data-ttu-id="261db-140">[**説明**] に、ルーム カテゴリの説明 (Contoso 用のルーム カテゴリなど) を詳しく指定します。</span><span class="sxs-lookup"><span data-stu-id="261db-140">In **Description**, provide a detailed description for the room category (for example, a room category for Contoso).</span></span>
    
   - <span data-ttu-id="261db-141">このカテゴリに属するチャット ルームに対して招待を有効にできるかどうかを制御するには、[招待を有効にする] チェック ボックス **をオンまたは** オフにします。</span><span class="sxs-lookup"><span data-stu-id="261db-141">To control whether invitations can be enabled for chat rooms that belong to this category, select or clear the **Enable invitations** check box.</span></span> <span data-ttu-id="261db-142">選択した場合、このカテゴリのルームには招待がオンまたはオフの場合があります。オフにした場合、このカテゴリのルームには招待を許可されません。</span><span class="sxs-lookup"><span data-stu-id="261db-142">If selected, rooms in this category may have invitations on or off; if cleared, the rooms in this category are not allowed to have invitations.</span></span> <span data-ttu-id="261db-143">ルームに招待がある場合、新しいメンバーがルームに追加された場合、常設チャット クライアントで新しいルームの通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="261db-143">If a room has invitations on, when a new member is added to a room, he or she gets a notification of the new room in their Persistent Chat client.</span></span>
    
   - <span data-ttu-id="261db-p109">このカテゴリに属するチャット ルームでのファイルのアップロードを制御するには、[**ファイルのアップロードを有効にする**] チェック ボックスをオンまたはオフにします。オンにした場合は、このカテゴリのルームではファイルのアップロードを有効または無効にできます。オフにした場合は、このカテゴリのルームではファイルのアップロードを有効にできません。</span><span class="sxs-lookup"><span data-stu-id="261db-p109">To control file uploads in chat rooms belonging to this category, select or clear the **Enable file upload** check box. If selected, the rooms of this category can enable or disable file uploads; if cleared, the rooms of this category are not allowed to have file uploads.</span></span>
    
   - <span data-ttu-id="261db-146">チャット履歴を制御するには、[チャット履歴を有効にする] **チェック ボックスをオンまたは** オフにします。</span><span class="sxs-lookup"><span data-stu-id="261db-146">To control chat history, select or clear the **Enable chat history** check box.</span></span> <span data-ttu-id="261db-147">オンにした場合、ルーム チャットは永続的になります。それ以外の場合、チャット メッセージは保持されません。</span><span class="sxs-lookup"><span data-stu-id="261db-147">If selected, room chats become persistent; otherwise, chat messages are not persisted.</span></span> <span data-ttu-id="261db-148">コンプライアンスを有効にすると、ルーム チャットはコンプライアンスに従って保存されますが、ユーザーは古いメッセージにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="261db-148">If compliance is enabled, room chats will be saved in compliance, but users will not be able to access older messages.</span></span> <span data-ttu-id="261db-149">このオプションは、チャット履歴を保持する必要がなされない、リアルタイムのアドホック コラボレーション用に指定されたルームに使用できます。</span><span class="sxs-lookup"><span data-stu-id="261db-149">This option can be used for rooms designated for real-time, ad hoc collaborations that don't need chat history to be persisted.</span></span>
    
7. <span data-ttu-id="261db-150">[**編集 分類**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="261db-150">In **Edit Category**, do the following:</span></span>
    
   - <span data-ttu-id="261db-151">[**メンバーシップ**] の[許可されるメンバー] セクションで、カテゴリに属するチャット ルームのメンバーとして追加できるユーザーおよび他の Active Directory ドメイン サービス プリンシパル (ユーザー、配布グループ、組織単位など) を追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="261db-151">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="261db-152">カテゴリによって許可されるプリンシパルは、カテゴリ内のルームを検索できます (ルームが非表示の場合を指定しない限り、ルームのメンバーだけがディレクトリで検索できます)。</span><span class="sxs-lookup"><span data-stu-id="261db-152">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>
    
   - <span data-ttu-id="261db-153">メンバーシップ **の**[拒否されたメンバー] セクションで、ルームから拒否されているメンバーに関連付けられているユーザーおよび他の Active Directory プリンシパルを追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="261db-153">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>
    
   - <span data-ttu-id="261db-154">[ **メンバーシップ]** の **[Creators]** セクションで、カテゴリの作成者に関連付けられているユーザーおよび他の Active Directory プリンシパルを追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="261db-154">In **Membership**, in the **Creators** section, add or remove users and other Active Directory principals associated with creators for the category.</span></span> <span data-ttu-id="261db-155">作成者は、チャット ルームを作成し、チャット ルームのマネージャーとメンバーを割り当てるためのアクセス許可が与えられているユーザーです。</span><span class="sxs-lookup"><span data-stu-id="261db-155">A creator is a user who has permissions to create chat rooms and assign chat room managers and members.</span></span>
    
8. <span data-ttu-id="261db-156">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="261db-156">Click **Commit**.</span></span>
    
## <a name="configure-categories-by-using-windows-powershell"></a><span data-ttu-id="261db-157">グループを使用してカテゴリをWindows PowerShell</span><span class="sxs-lookup"><span data-stu-id="261db-157">Configure categories by using Windows PowerShell</span></span>

<span data-ttu-id="261db-158">次のコマンドレットを使用して、カテゴリWindows PowerShellできます。</span><span class="sxs-lookup"><span data-stu-id="261db-158">You can configure categories by using the following Windows PowerShell cmdlets:</span></span>
  

|<span data-ttu-id="261db-159">**コマンドレット**</span><span class="sxs-lookup"><span data-stu-id="261db-159">**Cmdlet**</span></span>|<span data-ttu-id="261db-160">**説明**</span><span class="sxs-lookup"><span data-stu-id="261db-160">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="261db-161">New-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="261db-161">New-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="261db-162">新しいカテゴリを作成する</span><span class="sxs-lookup"><span data-stu-id="261db-162">Create a new category</span></span>  <br/> |
|<span data-ttu-id="261db-163">Set-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="261db-163">Set-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="261db-164">既存のカテゴリの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="261db-164">Configure settings for an existing category</span></span>  <br/> |
|<span data-ttu-id="261db-165">Get-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="261db-165">Get-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="261db-166">カテゴリに関する情報を取得する</span><span class="sxs-lookup"><span data-stu-id="261db-166">Retrieve information about categories</span></span>  <br/> |
|<span data-ttu-id="261db-167">Remove-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="261db-167">Remove-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="261db-168">カテゴリを削除する</span><span class="sxs-lookup"><span data-stu-id="261db-168">Remove a category</span></span>  <br/> |
   
<span data-ttu-id="261db-169">カテゴリに対して次のパラメーターを構成できます。</span><span class="sxs-lookup"><span data-stu-id="261db-169">You can configure the following parameters for categories:</span></span>
  
- <span data-ttu-id="261db-170">EnableFileUpload。</span><span class="sxs-lookup"><span data-stu-id="261db-170">EnableFileUpload.</span></span> <span data-ttu-id="261db-171">カテゴリ内のチャット ルームへのファイルのアップロードを許可します。</span><span class="sxs-lookup"><span data-stu-id="261db-171">Allows file uploads to the chat rooms in the category.</span></span>
    
- <span data-ttu-id="261db-172">EnableInvitations。</span><span class="sxs-lookup"><span data-stu-id="261db-172">EnableInvitations.</span></span> <span data-ttu-id="261db-173">カテゴリの招待を有効にする。</span><span class="sxs-lookup"><span data-stu-id="261db-173">Enables invitations for the category.</span></span> <span data-ttu-id="261db-174">AllowedMembers リストのユーザーは、新しいチャット ルームの作成時に、新しいチャット ルームへの参加の招待を自動的に受信します。</span><span class="sxs-lookup"><span data-stu-id="261db-174">Users on the AllowedMembers list will automatically receive an invitation to join a new chat room at the time the new room is created.</span></span>
    
- <span data-ttu-id="261db-175">ChatHistory。</span><span class="sxs-lookup"><span data-stu-id="261db-175">ChatHistory.</span></span> <span data-ttu-id="261db-176">チャット履歴機能を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="261db-176">Enables or disables the chat history feature.</span></span>
    
- <span data-ttu-id="261db-177">作成者。</span><span class="sxs-lookup"><span data-stu-id="261db-177">Creators.</span></span> <span data-ttu-id="261db-178">カテゴリ内でチャット ルームを作成できるユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="261db-178">Specifies the users who are allowed to create chat rooms within the category.</span></span>
    
- <span data-ttu-id="261db-179">AllowedMembers。</span><span class="sxs-lookup"><span data-stu-id="261db-179">AllowedMembers.</span></span> <span data-ttu-id="261db-180">カテゴリ内のチャット ルームへのアクセスを許可するユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="261db-180">Specifies the users who are allowed to access chat rooms within the category.</span></span>
    
- <span data-ttu-id="261db-181">DeniedMembers。</span><span class="sxs-lookup"><span data-stu-id="261db-181">DeniedMembers.</span></span> <span data-ttu-id="261db-182">カテゴリ内のチャット ルームへのアクセスが許可されないユーザーをリストします。</span><span class="sxs-lookup"><span data-stu-id="261db-182">Lists the users who are not allowed to access chat rooms within the category.</span></span>
    
<span data-ttu-id="261db-183">すべてのパラメーターを含むコマンドレット構文の詳細については [、「Skype for Business Server 2015 Management Shell」を参照してください](../management-shell.md)。</span><span class="sxs-lookup"><span data-stu-id="261db-183">For complete information about cmdlet syntax, including all parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  
### <a name="create-a-new-category"></a><span data-ttu-id="261db-184">新しいカテゴリを作成する</span><span class="sxs-lookup"><span data-stu-id="261db-184">Create a new category</span></span>

<span data-ttu-id="261db-185">**New-CsPersistentChatCategory** コマンドレットを使用して、新しいカテゴリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="261db-185">You can create a new category by using the **New-CsPersistentChatCategory** cmdlet.</span></span> <span data-ttu-id="261db-186">たとえば、次のコマンドを実行すると、HelpDesk という名前の新しいカテゴリがプール に作成atl-cs-001.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="261db-186">For example, the following command creates a new category named HelpDesk on the pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="261db-187">この例では、ファイルのアップロードが有効になっています。</span><span class="sxs-lookup"><span data-stu-id="261db-187">In this example, file upload is enabled:</span></span>
  
```PowerShell
New-CsPersistentChatCategory -Name "HelpDesk" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -EnableFileUpload 
```

### <a name="configure-an-existing-category"></a><span data-ttu-id="261db-188">既存のカテゴリを構成する</span><span class="sxs-lookup"><span data-stu-id="261db-188">Configure an existing category</span></span>

<span data-ttu-id="261db-189">**Set-CsPersistentCategory** コマンドレットを使用して、既存のカテゴリを構成できます。</span><span class="sxs-lookup"><span data-stu-id="261db-189">You can configure an existing category by using the **Set-CsPersistentCategory** cmdlet.</span></span>
  
<span data-ttu-id="261db-190">たとえば、次のコマンドは user1 が AllowedMember および Creator であり、user2 はカテゴリ内のルームへのアクセスを拒否されたと指定します。</span><span class="sxs-lookup"><span data-stu-id="261db-190">For example, the following command specifies that user1 is an AllowedMember and a Creator, while user2 is denied access to the rooms in the category:</span></span>
  
```PowerShell
Set-CsPersistentChatCategory -Identity testCat -AllowedMembers @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}  -DeniedMembers @{Add="sip:user2@contoso.com"}
Set-CsPersistentChatCategory -Identity testCat -Creators @{Add="sip:user1@contoso.com"}
```

### <a name="get-information-about-categories"></a><span data-ttu-id="261db-191">カテゴリに関する情報を取得する</span><span class="sxs-lookup"><span data-stu-id="261db-191">Get information about categories</span></span>

<span data-ttu-id="261db-192">**Get-CsPersistentChatCategory** コマンドレットを使用して、カテゴリに関する情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="261db-192">You can get information about categories by using the **Get-CsPersistentChatCategory** cmdlet.</span></span> <span data-ttu-id="261db-193">たとえば、次のコマンドを実行すると、組織内のすべての常設チャット カテゴリに関する情報が戻されます。</span><span class="sxs-lookup"><span data-stu-id="261db-193">For example, the following command returns information for all the Persistent Chat categories in the organization:</span></span>
  
```PowerShell
Get-CsPersistentChatCategory
```

### <a name="remove-a-category"></a><span data-ttu-id="261db-194">カテゴリを削除する</span><span class="sxs-lookup"><span data-stu-id="261db-194">Remove a category</span></span>

<span data-ttu-id="261db-195">**Remove-CsPersistentChatCategory** コマンドレットを使用して、カテゴリを削除できます。</span><span class="sxs-lookup"><span data-stu-id="261db-195">You can remove a category by using the **Remove-CsPersistentChatCategory** cmdlet.</span></span> <span data-ttu-id="261db-196">カテゴリを削除する前に、カテゴリの下のすべてのチャット ルームを削除するか、チャット ルームを新しいカテゴリに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="261db-196">Before removing a category, you must first either delete all chat rooms under it or move the chat rooms to a new category.</span></span> <span data-ttu-id="261db-197">たとえば、次のコマンドを実行すると、Identity が "atl-cs-001.contoso.com\helpdesk" のカテゴリが削除されます。</span><span class="sxs-lookup"><span data-stu-id="261db-197">For example, the following command removes the category that has the Identity "atl-cs-001.contoso.com\helpdesk":</span></span>
  
```PowerShell
Remove-CsPersistentChatCategory -Identity "atl-cs-001.contoso.com\helpdesk"
```
