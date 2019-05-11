---
title: Skype for Business Server 2015 の常設チャット サーバーでのカテゴリの管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b0c834b9-b5c8-41d5-865b-c8b180e76d13
description: '概要: ビジネス サーバー 2015 の Skype での永続的なチャット サーバー カテゴリを管理する方法を説明します。'
ms.openlocfilehash: 8da4f9233eb301c49d1c3a873194e2c09ebbb031
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910376"
---
# <a name="manage-categories-in-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="ee12e-103">Skype for Business Server 2015 の常設チャット サーバーでのカテゴリの管理</span><span class="sxs-lookup"><span data-stu-id="ee12e-103">Manage categories in Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ee12e-104">**の概要:** ビジネス サーバー 2015 の Skype での永続的なチャット サーバー カテゴリを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ee12e-104">**Summary:** Learn how to manage Persistent Chat Server categories in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="ee12e-105">カテゴリは、チャット ルームを整理するための論理的な構造です。</span><span class="sxs-lookup"><span data-stu-id="ee12e-105">A category is a logical structure for organizing chat rooms.</span></span> <span data-ttu-id="ee12e-106">カテゴリでは、チャット ルームを作成したり、チャット ルームに参加したりできるユーザーおよびユーザー グループを制御するためのアクセス制御リスト (ACL) の既定のセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="ee12e-106">A category defines a default set of access control lists (ACLs) for controlling the users and user groups who can create or join the chat rooms.</span></span> <span data-ttu-id="ee12e-107">チャット ルーム カテゴリには、チャット ルームのカテゴリを含めることができますが、他のカテゴリを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="ee12e-107">Chat room categories contain chat rooms, but not other categories.</span></span> <span data-ttu-id="ee12e-108">各カテゴリでは、[名前]、[説明] などのメタデータを使用してカテゴリの内容が記述されます。</span><span class="sxs-lookup"><span data-stu-id="ee12e-108">Each category describes its contents with metadata, such as Name and Description.</span></span> <span data-ttu-id="ee12e-109">また、カテゴリには、チャット ルームで [招待] や [ファイル アップロード] が許可されるかどうか、チャット ルームに [チャットの履歴] が含まれるかどうかなど、そのカテゴリに属するチャット ルームの動作を制御するプロパティを設定できます。</span><span class="sxs-lookup"><span data-stu-id="ee12e-109">The category has properties that can be set to control the behavior of the chat rooms belonging to it; for example, whether the chat rooms allow Invitations or File Uploads, or contain Chat History.</span></span> 
  
<span data-ttu-id="ee12e-110">カテゴリを適切に使用すると、チャット ルームの作成と管理が簡単になります。</span><span class="sxs-lookup"><span data-stu-id="ee12e-110">Creating and managing chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="ee12e-111">常設チャット サーバーの管理者は、各カテゴリに対して AllowedMembers と Creators を定義でき、そのカテゴリで作成されるすべてのチャット ルームに適用されるチャット ルームの既定の設定と動作を定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="ee12e-111">As a Persistent Chat Server administrator, you can define AllowedMembers and Creators for each category, and also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="ee12e-112">たとえば、contoso.com にカテゴリの AllowedMembers を設定する場合することができます任意のグループまたはユーザー contoso 社でメンバーとして追加そのカテゴリ内のチャット ルームに。</span><span class="sxs-lookup"><span data-stu-id="ee12e-112">For example, if you set the category's AllowedMembers to contoso.com, you can add any group or user at Contoso as a member to chat rooms in that category.</span></span> <span data-ttu-id="ee12e-113">カテゴリの Allowed Members を "営業" に設定した場合は、その配布リスト内のグループとユーザーのみを、カテゴリ内のチャット ルームにメンバーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="ee12e-113">If you set the Allowed Members on a category to Sales, only groups and users in this distribution list can be added as members to chat rooms in that category.</span></span> <span data-ttu-id="ee12e-114">Creators プロパティを使用すると、カテゴリ内にチャット ルームを作成できるユーザーを制御できます。</span><span class="sxs-lookup"><span data-stu-id="ee12e-114">The Creators property enables you to control who can create chat rooms in that category.</span></span> <span data-ttu-id="ee12e-115">チャット ルームが作成されると、AllowedMembers グループのユーザーを、ルームで進行中の管理操作 (メンバーシップの変更や承認など) の管理者として指定できます。</span><span class="sxs-lookup"><span data-stu-id="ee12e-115">After the chat room is created, anyone from the AllowedMembers group can be designated as a Manager for ongoing management operations on the rooms (for example, membership changes and approval).</span></span>
  
<span data-ttu-id="ee12e-116">カテゴリの AllowedMembers と Creators を定義すると、次の利点が得られます。</span><span class="sxs-lookup"><span data-stu-id="ee12e-116">Defining AllowedMembers and Creators for a category has the following benefits:</span></span>
  
- <span data-ttu-id="ee12e-117">カテゴリ内のすべてのチャット ルームがカテゴリ レベルの制限のセットにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="ee12e-117">All chat rooms in this category are bound by the restrictions set at the category level.</span></span> <span data-ttu-id="ee12e-118">これにより、業務ニーズとアクセス ポリシーに基づいてチャット ルームを分離できます。</span><span class="sxs-lookup"><span data-stu-id="ee12e-118">You can use this to segregate chat rooms based on business need and access policies.</span></span>
    
- <span data-ttu-id="ee12e-p104">Creators の一覧に含まれるユーザーが、カテゴリ内に新しいチャット ルームを作成できます。チャット ルームを作成できる組織内の担当者の数が制限されているシステムを実装する場合は、この制御を使用して要件を満たすことができます。</span><span class="sxs-lookup"><span data-stu-id="ee12e-p104">A user who is in the Creators list can create new chat rooms in that category. If you want to implement a system where a restricted number of personnel in the organization can create chat rooms this control can be used to meet that requirements.</span></span> 
    
<span data-ttu-id="ee12e-121">カテゴリの Creators として特定されるユーザー、組織単位 (OU)、ユーザー グループは、そのカテゴリのチャット ルームの作成を許可されている個人およびグループです。</span><span class="sxs-lookup"><span data-stu-id="ee12e-121">Users, Organization Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category.</span></span> <span data-ttu-id="ee12e-122">カテゴリを作成した後は、カテゴリの AllowedMembers リストからユーザー、OU、ユーザー グループをチャット ルームの管理と参加が可能なマネージャーおよびメンバーとして選択できます。</span><span class="sxs-lookup"><span data-stu-id="ee12e-122">After the category is created, you can choose users, OUs, and user groups from the category's AllowedMembers list as chat room managers and members to manage and participate in the room.</span></span> 
  
<span data-ttu-id="ee12e-123">カテゴリを構成する前に、[永続的なチャット カテゴリ、チャット ルーム、およびビジネス サーバー 2015 の Skype のユーザー ロール](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee12e-123">Before you configure categories, be sure to read [Persistent chat categories, chat rooms, and user roles in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md).</span></span>
  
<span data-ttu-id="ee12e-124">コントロール パネルを使用するか Windows PowerShell コマンドレットを使用すると、カテゴリを構成して管理することができます。</span><span class="sxs-lookup"><span data-stu-id="ee12e-124">You can configure and manage categories by using the Control Panel or by using Windows PowerShell cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="ee12e-125">永続的なチャットですがビジネス サーバー 2015 の Skype で利用可能なビジネス サーバー 2019 の Skype でサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ee12e-125">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="ee12e-126">同じ機能は、チームで使用できます。</span><span class="sxs-lookup"><span data-stu-id="ee12e-126">The same functionality is available in Teams.</span></span> <span data-ttu-id="ee12e-127">詳細については、[マイクロソフトのチームにビジネス用の Skype からの旅](/microsoftteams/journey-skypeforbusiness-teams)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee12e-127">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="ee12e-128">永続的なチャットを使用する場合は、選択肢は、いずれかをチームでは、この機能を必要とするユーザーを移行するまたはビジネス サーバー 2015 の Skype を使用し続ける。</span><span class="sxs-lookup"><span data-stu-id="ee12e-128">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="configure-categories-by-using-the-control-panel"></a><span data-ttu-id="ee12e-129">コントロール パネルを使用してカテゴリを構成する</span><span class="sxs-lookup"><span data-stu-id="ee12e-129">Configure categories by using the Control Panel</span></span>

1. <span data-ttu-id="ee12e-130">CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="ee12e-130">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="ee12e-131">**[スタート**] メニューから、Skype ビジネス サーバーのコントロール パネルのまたはブラウザー ウィンドウを開きし、管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="ee12e-131">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="ee12e-132">左側のナビゲーション バーで [**常設チャット**] をクリックして、[**分類**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ee12e-132">In the left navigation bar, click **Persistent Chat**, and then click **Category**.</span></span>
    
    <span data-ttu-id="ee12e-133">複数の永続的なチャット サーバー プールの展開には、ドロップ ダウン リストから適切なプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="ee12e-133">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>
    
4. <span data-ttu-id="ee12e-134">[**カテゴリ**] ページで、[**新規**] または [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ee12e-134">On the **Category** page, click **New** or **Edit**.</span></span>
    
5. <span data-ttu-id="ee12e-135">[**サービスの選択**] で、カテゴリの作成が必要な永続的なチャット サーバー プールに対応するサービスを選択します。</span><span class="sxs-lookup"><span data-stu-id="ee12e-135">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool on which the category needs to be created.</span></span> <span data-ttu-id="ee12e-136">サービスは、プールのカテゴリを識別するのには永続的なチャット クライアントを使用するプールが属する永続的なチャット サーバーです。</span><span class="sxs-lookup"><span data-stu-id="ee12e-136">The service is the Persistent Chat Server pool that the Persistent Chat client uses to identify which pool the category belongs to.</span></span> <span data-ttu-id="ee12e-137">カテゴリのみ 1 つの永続的なチャット サーバー プールに属することができます、移動先またはできません、別のプールを共有します。</span><span class="sxs-lookup"><span data-stu-id="ee12e-137">A category can belong to only one Persistent Chat Server pool, and cannot be moved to, or shared with, another pool.</span></span>
    
6. <span data-ttu-id="ee12e-138">[**新しいカテゴリ**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="ee12e-138">In **New Category**, do the following:</span></span>
    
   - <span data-ttu-id="ee12e-139">[**名前**] に、新しいルーム カテゴリの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ee12e-139">In **Name**, specify a name for the new room category.</span></span>
    
   - <span data-ttu-id="ee12e-140">[**説明**] に、ルーム カテゴリの詳細を指定します (たとえば「Contoso 用のカテゴリ」と指定します)。</span><span class="sxs-lookup"><span data-stu-id="ee12e-140">In **Description**, provide a detailed description for the room category (for example, a room category for Contoso).</span></span>
    
   - <span data-ttu-id="ee12e-141">このカテゴリに属しているチャット ルームに招待状を有効にできるかどうかを制御するには、オンまたは**への招待を有効にする**] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="ee12e-141">To control whether invitations can be enabled for chat rooms that belong to this category, select or clear the **Enable invitations** check box.</span></span> <span data-ttu-id="ee12e-142">選択した場合、このカテゴリの部屋があります招待状のオンまたはオフにします。オフの場合、招待状にこのカテゴリのルームを作成できません。</span><span class="sxs-lookup"><span data-stu-id="ee12e-142">If selected, rooms in this category may have invitations on or off; if cleared, the rooms in this category are not allowed to have invitations.</span></span> <span data-ttu-id="ee12e-143">ルームにルームに新しいメンバーを追加するときに招待状がある場合、彼または彼女が、永続的なチャット クライアントで新しい部屋の通知を取得します。</span><span class="sxs-lookup"><span data-stu-id="ee12e-143">If a room has invitations on, when a new member is added to a room, he or she gets a notification of the new room in their Persistent Chat client.</span></span>
    
   - <span data-ttu-id="ee12e-p109">このカテゴリに属するチャット ルームでファイルのアップロードを制御するには、[**ファイルのアップロードを有効にする**] チェック ボックスをオンまたはオフにします。オンにした場合、このカテゴリのルームでは、ファイルのアップロードを有効または無効にできます。オフにした場合、このカテゴリのルームではファイルのアップロードは許可されません。</span><span class="sxs-lookup"><span data-stu-id="ee12e-p109">To control file uploads in chat rooms belonging to this category, select or clear the **Enable file upload** check box. If selected, the rooms of this category can enable or disable file uploads; if cleared, the rooms of this category are not allowed to have file uploads.</span></span>
    
   - <span data-ttu-id="ee12e-146">チャットの履歴を制御するには、オンまたは、[**チャットの履歴を有効にする**] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="ee12e-146">To control chat history, select or clear the **Enable chat history** check box.</span></span> <span data-ttu-id="ee12e-147">ルーム チャットが選択されているなる永続的です。それ以外の場合、チャット メッセージは永続化されません。</span><span class="sxs-lookup"><span data-stu-id="ee12e-147">If selected, room chats become persistent; otherwise, chat messages are not persisted.</span></span> <span data-ttu-id="ee12e-148">コンプライアンスが有効な場合、ルーム チャットは、コンプライアンスに保存されますが、ユーザーは以前のメッセージにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="ee12e-148">If compliance is enabled, room chats will be saved in compliance, but users will not be able to access older messages.</span></span> <span data-ttu-id="ee12e-149">ルームのチャットの履歴を保持する必要はありません、暫定的なリアルタイムのコラボレーション用に指定されたは、このオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ee12e-149">This option can be used for rooms designated for real-time, ad hoc collaborations that don't need chat history to be persisted.</span></span>
    
7. <span data-ttu-id="ee12e-150">[**カテゴリの編集**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="ee12e-150">In **Edit Category**, do the following:</span></span>
    
   - <span data-ttu-id="ee12e-151">の**メンバーシップ**、[**許可されたメンバー** ] セクションを追加または削除、ユーザーおよびその他の Active Directory ドメイン サービス プリンシパル (ユーザー、配布グループ、組織単位、およびように) チャット ルームのメンバーとして追加することは許可されません。カテゴリに属しています。</span><span class="sxs-lookup"><span data-stu-id="ee12e-151">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="ee12e-152">カテゴリで許可されているプリンシパルは、(ルームが表示されない場合、ルームのメンバーのみ検索できるように、ディレクトリに) しない限り、カテゴリの 2 つの部屋を検索できます。</span><span class="sxs-lookup"><span data-stu-id="ee12e-152">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>
    
   - <span data-ttu-id="ee12e-153">の**メンバーシップ**、**拒否メンバー** ] セクションで追加またはユーザーと他の部屋から拒否されているメンバーに関連付けられている Active Directory のプリンシパルを削除します。</span><span class="sxs-lookup"><span data-stu-id="ee12e-153">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>
    
   - <span data-ttu-id="ee12e-154">**メンバーシップ**、[**作成者**] セクションで追加またはユーザーとその他のカテゴリの作成者に関連付けられている Active Directory のプリンシパルを削除します。</span><span class="sxs-lookup"><span data-stu-id="ee12e-154">In **Membership**, in the **Creators** section, add or remove users and other Active Directory principals associated with creators for the category.</span></span> <span data-ttu-id="ee12e-155">作成者は、チャット ルームを作成し、チャット ルームのマネージャーとメンバーを割り当てることができるアクセス許可を持つユーザーです。</span><span class="sxs-lookup"><span data-stu-id="ee12e-155">A creator is a user who has permissions to create chat rooms and assign chat room managers and members.</span></span>
    
8. <span data-ttu-id="ee12e-156">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ee12e-156">Click **Commit**.</span></span>
    
## <a name="configure-categories-by-using-windows-powershell"></a><span data-ttu-id="ee12e-157">Windows PowerShell を使用してカテゴリを構成する</span><span class="sxs-lookup"><span data-stu-id="ee12e-157">Configure categories by using Windows PowerShell</span></span>

<span data-ttu-id="ee12e-158">次の Windows PowerShell コマンドレットを使用すると、カテゴリを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="ee12e-158">You can configure categories by using the following Windows PowerShell cmdlets:</span></span>
  

|<span data-ttu-id="ee12e-159">**コマンドレット**</span><span class="sxs-lookup"><span data-stu-id="ee12e-159">**Cmdlet**</span></span>|<span data-ttu-id="ee12e-160">**説明**</span><span class="sxs-lookup"><span data-stu-id="ee12e-160">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ee12e-161">New-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="ee12e-161">New-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="ee12e-162">新しいカテゴリを作成する</span><span class="sxs-lookup"><span data-stu-id="ee12e-162">Create a new category</span></span>  <br/> |
|<span data-ttu-id="ee12e-163">Set-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="ee12e-163">Set-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="ee12e-164">既存のカテゴリの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="ee12e-164">Configure settings for an existing category</span></span>  <br/> |
|<span data-ttu-id="ee12e-165">Get-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="ee12e-165">Get-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="ee12e-166">カテゴリに関する情報を取得する</span><span class="sxs-lookup"><span data-stu-id="ee12e-166">Retrieve information about categories</span></span>  <br/> |
|<span data-ttu-id="ee12e-167">Remove-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="ee12e-167">Remove-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="ee12e-168">カテゴリを削除する</span><span class="sxs-lookup"><span data-stu-id="ee12e-168">Remove a category</span></span>  <br/> |
   
<span data-ttu-id="ee12e-169">カテゴリには、次のパラメーターを構成できます。</span><span class="sxs-lookup"><span data-stu-id="ee12e-169">You can configure the following parameters for categories:</span></span>
  
- <span data-ttu-id="ee12e-p113">EnableFileUpload。カテゴリ内のチャット ルームにファイルをアップロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="ee12e-p113">EnableFileUpload. Allows file uploads to the chat rooms in the category.</span></span>
    
- <span data-ttu-id="ee12e-172">EnableInvitations。</span><span class="sxs-lookup"><span data-stu-id="ee12e-172">EnableInvitations.</span></span> <span data-ttu-id="ee12e-173">カテゴリの招待を有効にします。</span><span class="sxs-lookup"><span data-stu-id="ee12e-173">Enables invitations for the category.</span></span> <span data-ttu-id="ee12e-174">AllowedMembers リストに登録されているユーザーは、新しいチャット ルームが作成されると、そのチャット ルームへの参加を促す招待状を自動的に受信します。</span><span class="sxs-lookup"><span data-stu-id="ee12e-174">Users on the AllowedMembers list will automatically receive an invitation to join a new chat room at the time the new room is created.</span></span>
    
- <span data-ttu-id="ee12e-175">ChatHistory。</span><span class="sxs-lookup"><span data-stu-id="ee12e-175">ChatHistory.</span></span> <span data-ttu-id="ee12e-176">チャット履歴機能を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="ee12e-176">Enables or disables the chat history feature.</span></span>
    
- <span data-ttu-id="ee12e-177">Creators。</span><span class="sxs-lookup"><span data-stu-id="ee12e-177">Creators.</span></span> <span data-ttu-id="ee12e-178">カテゴリ内でのチャット ルームの作成が許可されるユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="ee12e-178">Specifies the users who are allowed to create chat rooms within the category.</span></span>
    
- <span data-ttu-id="ee12e-179">AllowedMembers。</span><span class="sxs-lookup"><span data-stu-id="ee12e-179">AllowedMembers.</span></span> <span data-ttu-id="ee12e-180">カテゴリ内のチャット ルームへのアクセスが許可されるユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="ee12e-180">Specifies the users who are allowed to access chat rooms within the category.</span></span>
    
- <span data-ttu-id="ee12e-p118">DeniedMembers。カテゴリ内のチャット ルームへのアクセスが許可されないユーザーをリストします。</span><span class="sxs-lookup"><span data-stu-id="ee12e-p118">DeniedMembers. Lists the users who are not allowed to access chat rooms within the category.</span></span>
    
<span data-ttu-id="ee12e-183">すべてのパラメーターを含む、コマンドレットの構文の詳細については、「[Skype for Business Server 2015 Management Shell](../management-shell.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee12e-183">For complete information about cmdlet syntax, including all parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  
### <a name="create-a-new-category"></a><span data-ttu-id="ee12e-184">新しいカテゴリを作成する</span><span class="sxs-lookup"><span data-stu-id="ee12e-184">Create a new category</span></span>

<span data-ttu-id="ee12e-185">**New-CsPersistentChatCategory** コマンドレットを使用すると、新しいカテゴリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ee12e-185">You can create a new category by using the **New-CsPersistentChatCategory** cmdlet.</span></span> <span data-ttu-id="ee12e-186">たとえば、以下のコマンドを実行すると、プール atl-cs-001.contoso.com に HelpDesk という名前の新しいカテゴリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="ee12e-186">For example, the following command creates a new category named HelpDesk on the pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="ee12e-187">この例では、ファイル アップロードが有効になります。</span><span class="sxs-lookup"><span data-stu-id="ee12e-187">In this example, file upload is enabled:</span></span>
  
```
New-CsPersistentChatCategory -Name "HelpDesk" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -EnableFileUpload 
```

### <a name="configure-an-existing-category"></a><span data-ttu-id="ee12e-188">既存のカテゴリを構成する</span><span class="sxs-lookup"><span data-stu-id="ee12e-188">Configure an existing category</span></span>

<span data-ttu-id="ee12e-189">**Set-CsPersistentCategory** コマンドレットを使用すると、既存のカテゴリを構成できます。</span><span class="sxs-lookup"><span data-stu-id="ee12e-189">You can configure an existing category by using the **Set-CsPersistentCategory** cmdlet.</span></span>
  
<span data-ttu-id="ee12e-190">たとえば、次のコマンドでは、user2 がカテゴリの会議室へのアクセスを拒否されたときに、user1 は、AllowedMember と、作成者を指定します。</span><span class="sxs-lookup"><span data-stu-id="ee12e-190">For example, the following command specifies that user1 is an AllowedMember and a Creator, while user2 is denied access to the rooms in the category:</span></span>
  
```
Set-CsPersistentChatCategory -Identity testCat -AllowedMembers @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}  -DeniedMembers @{Add="sip:user2@contoso.com"}
Set-CsPersistentChatCategory -Identity testCat -Creators @{Add="sip:user1@contoso.com"}
```

### <a name="get-information-about-categories"></a><span data-ttu-id="ee12e-191">カテゴリに関する情報を取得する</span><span class="sxs-lookup"><span data-stu-id="ee12e-191">Get information about categories</span></span>

<span data-ttu-id="ee12e-p120">**Get-CsPersistentChatCategory** コマンドレットを使用すると、カテゴリに関する情報を取得できます。たとえば、以下のコマンドを実行すると、組織内のすべての常設チャット カテゴリに関する情報が戻されます。</span><span class="sxs-lookup"><span data-stu-id="ee12e-p120">You can get information about categories by using the **Get-CsPersistentChatCategory** cmdlet. For example, the following command returns information for all the Persistent Chat categories in the organization:</span></span>
  
```
Get-CsPersistentChatCategory
```

### <a name="remove-a-category"></a><span data-ttu-id="ee12e-194">カテゴリを削除する</span><span class="sxs-lookup"><span data-stu-id="ee12e-194">Remove a category</span></span>

<span data-ttu-id="ee12e-p121">**Remove-CsPersistentChatCategory** コマンドレットを使用すると、カテゴリを削除できます。カテゴリを削除する前に、そのカテゴリの下にあるすべてのチャット ルームを削除するか、それらのチャット ルームを新しいカテゴリに移動する必要があります。たとえば、以下のコマンドを実行すると、ID "atl-cs-001.contoso.com\helpdesk" が含まれるカテゴリが削除されます。</span><span class="sxs-lookup"><span data-stu-id="ee12e-p121">You can remove a category by using the **Remove-CsPersistentChatCategory** cmdlet. Before removing a category, you must first either delete all chat rooms under it or move the chat rooms to a new category. For example, the following command removes the category that has the Identity "atl-cs-001.contoso.com\helpdesk":</span></span>
  
```
Remove-CsPersistentChatCategory -Identity "atl-cs-001.contoso.com\helpdesk"
```
