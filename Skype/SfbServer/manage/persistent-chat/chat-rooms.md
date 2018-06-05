---
title: Skype for Business Server 2015 での常設チャット サーバーのチャット ルームの管理
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b2e1302-280c-4efe-9ec8-787687b414da
description: '概要: ビジネス サーバー 2015 の Skype で永続的なチャット サーバーのチャット ルームを管理する方法を説明します。'
ms.openlocfilehash: 7febc9736f43f3168d7bc62b0ddf833fa6b5864b
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569401"
---
# <a name="manage-chat-rooms-in-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="d6e83-103">Skype for Business Server 2015 での常設チャット サーバーのチャット ルームの管理</span><span class="sxs-lookup"><span data-stu-id="d6e83-103">Manage chat rooms in Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d6e83-104">**の概要:** ビジネス サーバー 2015 の Skype で永続的なチャット サーバーのチャット ルームを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d6e83-104">**Summary:** Learn how to manage Persistent Chat Server chat rooms in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="d6e83-105">カテゴリを適切に使用すると、チャット ルームの作成と管理が簡単になります。</span><span class="sxs-lookup"><span data-stu-id="d6e83-105">Creating and managing chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="d6e83-106">カテゴリを作成したり、チャット ルームに参加するを定義します。</span><span class="sxs-lookup"><span data-stu-id="d6e83-106">A category defines who can create or join the chat rooms.</span></span> <span data-ttu-id="d6e83-107">チャット ルームを管理しようとすると、前に、[永続的なチャット カテゴリ、チャット ルーム、およびビジネス サーバー 2015 の Skype のユーザーの役割](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md)と[業務サーバー 2015 の Skype での永続的なチャット サーバーの管理カテゴリ](categories.md)を読み取ることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d6e83-107">Before you attempt to manage chat rooms, be sure to read [Persistent chat categories, chat rooms, and user roles in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) and [Manage categories in Persistent Chat Server in Skype for Business Server 2015](categories.md).</span></span>
  
<span data-ttu-id="d6e83-108">構成し、Windows PowerShell のコマンド ライン インターフェイスを使用するか、ビジネス クライアントのチャット ルームのメンバーである場合、Skype を使用して、チャット ルームを管理できます。</span><span class="sxs-lookup"><span data-stu-id="d6e83-108">You can configure and manage chat rooms by using the Windows PowerShell command-line interface, or by using the Skype for Business client if you are a member of the chat room.</span></span> <span data-ttu-id="d6e83-109">ここでは、Windows PowerShell コマンド ライン インターフェイスを使用してチャット ルームを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d6e83-109">This topic describes how to manage chat rooms by using the Windows PowerShell command-line interface.</span></span> <span data-ttu-id="d6e83-110">ビジネス クライアント用の Skype を使用してチャット ルームを管理する場合は、クライアントのヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6e83-110">If you want to manage chat rooms by using the Skype for Business client, see the client help.</span></span> 
  
<span data-ttu-id="d6e83-111">チャット ルームには、次の 2 種類のいずれかを指定できます: 標準および聴衆。</span><span class="sxs-lookup"><span data-stu-id="d6e83-111">Chat rooms can be one of two types: Normal and Auditorium.</span></span> <span data-ttu-id="d6e83-112">標準チャット ルームでは、すべてのメンバーがメッセージを投稿および閲覧できます。</span><span class="sxs-lookup"><span data-stu-id="d6e83-112">A Normal chat room allows all members to post and read messages.</span></span> <span data-ttu-id="d6e83-113">種類が大会議室のチャット ルームでは、投稿できるのは発表者のみですが、すべてのユーザーが閲覧できますす。</span><span class="sxs-lookup"><span data-stu-id="d6e83-113">An Auditorium is a type of chat room where only Presenters can post, but everyone can read.</span></span>
  
<span data-ttu-id="d6e83-114">チャット ルームにアクセスして管理できるユーザーは、次のように、ユーザーの役割に応じて異なります。</span><span class="sxs-lookup"><span data-stu-id="d6e83-114">Who can access and manage chat rooms depends on user roles as follows:</span></span>
  
- <span data-ttu-id="d6e83-115">ユーザーがメッセージを投稿および閲覧するには、チャット ルームのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6e83-115">Users must be Members of a chat room to be able to post and read messages.</span></span>
    
- <span data-ttu-id="d6e83-116">発表者は、大会議室ルームに投稿することができます。</span><span class="sxs-lookup"><span data-stu-id="d6e83-116">Presenters are allowed to post to Auditorium rooms.</span></span>
    
- <span data-ttu-id="d6e83-117">管理者は、データベースが大きくなりすぎないようにチャット ルームから古いコンテンツ (たとえば、特定の日付より前に投稿されたコンテンツ) を削除できます。</span><span class="sxs-lookup"><span data-stu-id="d6e83-117">Administrators can delete earlier content (for example, content that was posted before a certain date) from any chat room to keep the database from growing too large.</span></span> <span data-ttu-id="d6e83-118">また、管理者は、特定のチャット ルームにとって不適切と判断されるメッセージを削除または置換することもできます。</span><span class="sxs-lookup"><span data-stu-id="d6e83-118">Administrators can also remove or replace messages that are considered inappropriate for a particular chat room.</span></span>
    
- <span data-ttu-id="d6e83-119">エンド ユーザーは、メッセージの作成者を含めて、チャット ルームからコンテンツを削除できません。</span><span class="sxs-lookup"><span data-stu-id="d6e83-119">End users, including message authors, cannot delete content from any chat room.</span></span>
    
- <span data-ttu-id="d6e83-120">チャット ルームのマネージャーは、ルームの無効化を含む、チャット ルームのすべてのプロパティを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="d6e83-120">Chat room Managers can make changes to all chat room properties, including disabling rooms.</span></span> <span data-ttu-id="d6e83-121">ただし、マネージャーは、ルームの削除や、ルームのカテゴリの変更を行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="d6e83-121">Managers cannot, however, delete a room, or change the category of a room.</span></span> 
    
- <span data-ttu-id="d6e83-122">チャット ルームを削除できるのは管理者のみです。</span><span class="sxs-lookup"><span data-stu-id="d6e83-122">Only Administrators can delete a chat room after it has been created.</span></span>
    
<span data-ttu-id="d6e83-123">次の Windows PowerShell コマンドレットを使用すると、チャット ルームを構成および管理することができます。</span><span class="sxs-lookup"><span data-stu-id="d6e83-123">You can configure and manage chat rooms by using the following Windows PowerShell cmdlets:</span></span>
  

|<span data-ttu-id="d6e83-124">**コマンドレット**</span><span class="sxs-lookup"><span data-stu-id="d6e83-124">**Cmdlet**</span></span>|<span data-ttu-id="d6e83-125">**説明**</span><span class="sxs-lookup"><span data-stu-id="d6e83-125">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d6e83-126">新しい-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="d6e83-126">New-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="d6e83-127">新しいチャット ルームを作成する</span><span class="sxs-lookup"><span data-stu-id="d6e83-127">Create a new chat room</span></span>  <br/> |
|<span data-ttu-id="d6e83-128">セット CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="d6e83-128">Set-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="d6e83-129">既存のルームの設定を構成し、ユーザーおよびユーザー グループをルームに割り当てる</span><span class="sxs-lookup"><span data-stu-id="d6e83-129">Configure settings for an existing room; assign users and user groups to the room</span></span>  <br/> |
|<span data-ttu-id="d6e83-130">Get CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="d6e83-130">Get-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="d6e83-131">ルームに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="d6e83-131">Retrieve information about rooms</span></span>  <br/> |
|<span data-ttu-id="d6e83-132">クリア CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="d6e83-132">Clear-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="d6e83-133">ルームをクリアするか、ルームからメッセージをクリアする</span><span class="sxs-lookup"><span data-stu-id="d6e83-133">Clear a room or messages from a room</span></span>  <br/> |
|<span data-ttu-id="d6e83-134">削除 CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="d6e83-134">Remove-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="d6e83-135">ルームを削除する</span><span class="sxs-lookup"><span data-stu-id="d6e83-135">Remove a room</span></span>  <br/> |
|<span data-ttu-id="d6e83-136">削除 CsPersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="d6e83-136">Remove-CsPersistentChatMessage</span></span>  <br/> |<span data-ttu-id="d6e83-137">ルームからメッセージを削除する</span><span class="sxs-lookup"><span data-stu-id="d6e83-137">Remove messages from a room</span></span>  <br/> |
   
<span data-ttu-id="d6e83-138">**新規 CsPersistentChatRoom**コマンドレットを使用するにはチャット ルームとチャット ルームにユーザーを追加するなど、既存のチャット ルームを構成するのには**一連の CsPersistentChatRoom**コマンドレットを作成します。</span><span class="sxs-lookup"><span data-stu-id="d6e83-138">You use the **New-CsPersistentChatRoom** cmdlet to create chat rooms and the **Set-CsPersistentChatRoom** cmdlet to configure an existing chat room, including adding users to the chat room.</span></span> <span data-ttu-id="d6e83-139">チャット ルームには、次のパラメーターを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="d6e83-139">You can configure the following parameters for chat rooms:</span></span>
  
- <span data-ttu-id="d6e83-140">Disabled。</span><span class="sxs-lookup"><span data-stu-id="d6e83-140">Disabled.</span></span> <span data-ttu-id="d6e83-141">チャット ルームを有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d6e83-141">Lets you disable or enable a chat room.</span></span> 
    
- <span data-ttu-id="d6e83-142">Invitations。</span><span class="sxs-lookup"><span data-stu-id="d6e83-142">Invitations.</span></span> <span data-ttu-id="d6e83-143">チャット ルームのメンバーとして追加されたユーザーに通知するために使用される、チャット ルームへの招待を有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d6e83-143">Lets you enable or disable chat room invitations, which are used to notify users when they have been added as chat room members.</span></span> <span data-ttu-id="d6e83-144">招待の既定の設定は継承され、チャット ルームではそれが属するカテゴリで構成されている招待の設定が適用されます。</span><span class="sxs-lookup"><span data-stu-id="d6e83-144">The default setting for invitations in inherit, which caused the chat room to adopt the invitation setting configured on the category it belongs to.</span></span> <span data-ttu-id="d6e83-145">チャット ルーム レベルで招待の設定を False に構成すると、カテゴリの設定よりも優先させることができます。</span><span class="sxs-lookup"><span data-stu-id="d6e83-145">Configuring the invitations setting to false at the chat room level allows the category setting to be overridden.</span></span> 
    
- <span data-ttu-id="d6e83-146">Privacy。</span><span class="sxs-lookup"><span data-stu-id="d6e83-146">Privacy.</span></span> <span data-ttu-id="d6e83-147">チャット ルームを公開、非公開、秘密のいずれにするかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="d6e83-147">Lets you specify whether a chat room is Open, Closed, or Secret.</span></span> <span data-ttu-id="d6e83-148">公開ルームは、すべてのユーザーが検索およびアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="d6e83-148">Open rooms can be searched and accessed by anyone.</span></span> <span data-ttu-id="d6e83-149">非公開ルームはすべてのユーザーが検索できますが、アクセスできるのはメンバーに限定されます。</span><span class="sxs-lookup"><span data-stu-id="d6e83-149">Closed rooms can be searched by anyone, but can be accessed only by members.</span></span> <span data-ttu-id="d6e83-150">秘密ルームはルームのメンバーのみが検索およびアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="d6e83-150">Secret rooms can be searched and accessed only by members of the room.</span></span> <span data-ttu-id="d6e83-151">既定では、新しいルームはすべて、最初は非公開として構成されます。</span><span class="sxs-lookup"><span data-stu-id="d6e83-151">By default, each new room is initially configured as Closed.</span></span>
    
- <span data-ttu-id="d6e83-152">入力します。</span><span class="sxs-lookup"><span data-stu-id="d6e83-152">Type.</span></span> <span data-ttu-id="d6e83-153">チャット ルームでは、ルームの通常のことで、任意のメンバーまたは大会議室を持ち、発表者だけが投稿されたメッセージを受け取りますが投稿したメッセージを受け入れるかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="d6e83-153">Lets you specify whether a chat room is a Normal room, which accepts messages posted by any member, or an Auditorium room, which accepts messages posted only by a Presenter.</span></span>
    
- <span data-ttu-id="d6e83-154">アドインです。</span><span class="sxs-lookup"><span data-stu-id="d6e83-154">Addin.</span></span> <span data-ttu-id="d6e83-155">以前に構成された追加のメンバーが参加しているときに表示する表示するコンテンツの URL を使用する、チャット ルームに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="d6e83-155">Lets you associate a previously configured add-in with a chat room, which allows URL content to be viewed by members while participating.</span></span>
    
<span data-ttu-id="d6e83-156">**セット CsPersistentChatRoom**コマンドレットでは、上のパラメーターだけでなく次のようにチャット ルームにユーザーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="d6e83-156">In addition to the above parameters, the **Set-CsPersistentChatRoom** cmdlet lets you assign users to the chat room as follows:</span></span>
  
- <span data-ttu-id="d6e83-157">Members。</span><span class="sxs-lookup"><span data-stu-id="d6e83-157">Members.</span></span> <span data-ttu-id="d6e83-158">チャット ルームのメンバーシップを構成します。</span><span class="sxs-lookup"><span data-stu-id="d6e83-158">Configures membership for the chat room.</span></span> <span data-ttu-id="d6e83-159">ユーザーの SIP アドレスを指定することで、1 つのコマンドレットを使用して個別または複数のメンバーを追加または削除することができます。</span><span class="sxs-lookup"><span data-stu-id="d6e83-159">You can add or remove either the individual or multiple members using a single cmdlet by specifying the SIP address of the users.</span></span> <span data-ttu-id="d6e83-160">ユーザーを一括して追加するために、Active Directory の組織単位や配布グループを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="d6e83-160">To allow users to be added in bulk, Active Directory organizational units or distribution groups can also be specified.</span></span>
    
- <span data-ttu-id="d6e83-161">Managers。</span><span class="sxs-lookup"><span data-stu-id="d6e83-161">Managers.</span></span> <span data-ttu-id="d6e83-162">チャット ルームにマネージャーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="d6e83-162">Lets you assign managers to the chat room.</span></span> <span data-ttu-id="d6e83-163">マネージャーは、他の設定に加えて、チャット ルームのメンバーシップを定義するアクセス許可を持ちます。</span><span class="sxs-lookup"><span data-stu-id="d6e83-163">Managers have the permissions to define membership of a chat room along with other settings.</span></span>
    
- <span data-ttu-id="d6e83-p114">Presenters。大会議室チャット ルームに発表者を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="d6e83-p114">Presenters. Lets you assign presenters to an Auditorium chat room.</span></span> 
    
 <span data-ttu-id="d6e83-166">など、他のすべてのパラメーターの構文の詳細については、 [Skype ビジネス サーバー 2015 管理シェルに](../management-shell.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6e83-166">For details about syntax, including all parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  
## <a name="create-a-new-room"></a><span data-ttu-id="d6e83-167">新しいルームを作成する</span><span class="sxs-lookup"><span data-stu-id="d6e83-167">Create a new room</span></span>

<span data-ttu-id="d6e83-168">**New-CsPersistentChatRoom** コマンドレットを使用すると、新しいルームを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d6e83-168">You can create a new room by using the **New-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="d6e83-169">たとえば、以下のコマンドを実行すると、プール atl-cs-001.contoso.com に ITChatRoom という名前の新しいチャット ルームが作成されます。</span><span class="sxs-lookup"><span data-stu-id="d6e83-169">For example, the following command creates a new chat room named ITChatRoom on the pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="d6e83-170">この例では、チャット ルームは IT カテゴリに追加されます。</span><span class="sxs-lookup"><span data-stu-id="d6e83-170">In this example, the chat room is added to the IT category:</span></span>
  
```
New-CsPersistentChatRoom -Name "ITChatRoom" -PersistentChatPoolFqdn "atl-cs-001.contoso.com"-Category "IT"
```

<span data-ttu-id="d6e83-171">**注:** 次のいずれかが true の場合、PersistentChatPoolFqdn は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="d6e83-171">**Note:** PersistentChatPoolFqdn is not needed if one of the following is true:</span></span> 
  
- <span data-ttu-id="d6e83-172">1 つのみの永続的なチャット サーバー プールがあります。</span><span class="sxs-lookup"><span data-stu-id="d6e83-172">There is only one Persistent Chat Server pool.</span></span>
    
- <span data-ttu-id="d6e83-173">カテゴリにプール FQDN を提供する。</span><span class="sxs-lookup"><span data-stu-id="d6e83-173">You provide a pool FQDN to the category.</span></span>
    
- <span data-ttu-id="d6e83-174">ルームの追加にプール FQDN を提供する。</span><span class="sxs-lookup"><span data-stu-id="d6e83-174">You provide a pool FQDN to adding the room.</span></span>
    
## <a name="configure-an-existing-room"></a><span data-ttu-id="d6e83-175">既存のルームを構成する</span><span class="sxs-lookup"><span data-stu-id="d6e83-175">Configure an existing room</span></span>

<span data-ttu-id="d6e83-176">**セット CsPersistentChatRoom**コマンドレットを使用して、既存の領域を設定できます。</span><span class="sxs-lookup"><span data-stu-id="d6e83-176">You can configure an existing room by using the **Set-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="d6e83-177">たとえば、メンバー、発表者としての user1 と user2 を testCat 大会議室の管理者は、次のコマンドを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d6e83-177">For example, the following command assigns user1 as a Member and Presenter, and user2 as a Manager, of the testCat Auditorium room:</span></span>
  
```
Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}
Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
```

 <span data-ttu-id="d6e83-178">次の例では、Active Directory の NorthAmericaUsers OU のすべてのユーザーを NorthAmerica チャット ルームに追加します。</span><span class="sxs-lookup"><span data-stu-id="d6e83-178">The next example adds all the users from the NorthAmericaUsers OU in active Directory to the NorthAmerica chat room:</span></span>
  
```
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=contoso,DC=com"}
```

<span data-ttu-id="d6e83-179">次の例では、Finance 配布グループのすべてのメンバーを同じチャット ルームに追加します。</span><span class="sxs-lookup"><span data-stu-id="d6e83-179">The next example adds all the members from the Finance distribution group to the same chat room:</span></span>
  
```
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=contoso,DC=com"}
```

## <a name="disable-or-enable-a-room"></a><span data-ttu-id="d6e83-180">ルームを無効または有効にする</span><span class="sxs-lookup"><span data-stu-id="d6e83-180">Disable or enable a room</span></span>

<span data-ttu-id="d6e83-181">永続的なチャット ルームのトピックが関連する不要になった場合は、行うことができますチャット ルーム使用できないユーザーを無効にすることによって。</span><span class="sxs-lookup"><span data-stu-id="d6e83-181">If the topic of a Persistent Chat room is no longer relevant, you can make the chat room unavailable to users by disabling it.</span></span> <span data-ttu-id="d6e83-182">チャット ルームを無効にすると、すべてのメンバーがチャット ルームから即座に切断されます。</span><span class="sxs-lookup"><span data-stu-id="d6e83-182">When a chat room is disabled, all members are immediately disconnected from the room.</span></span> <span data-ttu-id="d6e83-183">チャット ルームを無効にした後、ユーザーは、そのチャット ルームに再び参加することも、チャット ルームを検索することもできません。</span><span class="sxs-lookup"><span data-stu-id="d6e83-183">After a chat room is disabled, users cannot rejoin it or find it in chat room searches.</span></span>
  
<span data-ttu-id="d6e83-184">チャット ルームの履歴が解決しない場合は、チャット ルームが無効になっているコンテンツが保持されます。</span><span class="sxs-lookup"><span data-stu-id="d6e83-184">If the chat room's history persists, the content is preserved when the chat room is disabled.</span></span> <span data-ttu-id="d6e83-185">ただし、チャット ルームが無効になっている間、コンテンツは検索に表示されません。</span><span class="sxs-lookup"><span data-stu-id="d6e83-185">However, that content will not appear in searches during the time that the chat room remains in a disabled state.</span></span> <span data-ttu-id="d6e83-186">チャット ルームを後で有効にすると、ユーザーは、チャット ルームが無効になる前に投稿されたメッセージを検索できます。</span><span class="sxs-lookup"><span data-stu-id="d6e83-186">If you later enable the chat room, users can search for messages that were posted before the chat room was disabled.</span></span> <span data-ttu-id="d6e83-187">チャットの履歴の構成方法の詳細については、[ビジネス サーバー 2015 の Skype での永続的なチャット サーバーの管理のカテゴリ](categories.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6e83-187">For information about configuring chat room history, see [Manage categories in Persistent Chat Server in Skype for Business Server 2015](categories.md).</span></span> 
  
<span data-ttu-id="d6e83-188">チャット ルームを無効にした場合、[メンバーシップ] ボックスの一覧とその他の設定は保持されます。</span><span class="sxs-lookup"><span data-stu-id="d6e83-188">If a chat room is disabled, its membership list and other settings are preserved.</span></span> <span data-ttu-id="d6e83-189">、管理者として、無効になっている部屋を有効にすることができ、設定を手動で再作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d6e83-189">As an administrator, you can enable a room that has been disabled, and you do not need to manually re-create the settings.</span></span>
  
<span data-ttu-id="d6e83-190">**セット CsPersistentChatRoom**コマンドレットを使用して、無効なパラメーターを True に設定してルームを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d6e83-190">You can disable a room by using the **Set-CsPersistentChatRoom** cmdlet and setting the Disabled parameter to True:</span></span>
  
```
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $True
```

<span data-ttu-id="d6e83-191">チャット ルームを有効にするには、Disabled パラメーターを False に設定します。</span><span class="sxs-lookup"><span data-stu-id="d6e83-191">To enable a chat room, set the Disabled parameter to False:</span></span>
  
```
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $False
```

## <a name="get-information-about-rooms"></a><span data-ttu-id="d6e83-192">ルームについての情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="d6e83-192">Get information about rooms</span></span>

<span data-ttu-id="d6e83-193">組織内で使用するように構成されているルームに関する情報を取得するには、**Get-CsPersistentChatRoom** コマンドレットを使用する方法があります。</span><span class="sxs-lookup"><span data-stu-id="d6e83-193">To get information about the rooms configured for use in your organization, you can use the **Get-CsPersistentChatRoom** cmdlet.</span></span>
  
<span data-ttu-id="d6e83-194">次のコマンドを実行すると、組織で使用するように構成されたすべてのチャット ルームに関する情報を戻します。</span><span class="sxs-lookup"><span data-stu-id="d6e83-194">The following command returns information about all the chat rooms configured for use in the organization:</span></span>
  
```
Get-CsPersistentChatRoom
```

## <a name="remove-all-content-from-a-room"></a><span data-ttu-id="d6e83-195">ルームからすべてのコンテンツを削除する</span><span class="sxs-lookup"><span data-stu-id="d6e83-195">Remove all content from a room</span></span>

<span data-ttu-id="d6e83-p120">**Clear-CsPersistentChatRoom** コマンドレットを使用すると、ルームからコンテンツを削除できます。たとえば、以下のコマンドを実行すると、常設チャット ルーム ITChatRoom から、2015 年 3 月 1 日以前にそのルームに追加されたコンテンツがすべて削除されます。</span><span class="sxs-lookup"><span data-stu-id="d6e83-p120">You can remove content from a room by using the **Clear-CsPersistentChatRoom** cmdlet. For example, the following command removes all the content from the Persistent Chat room ITChatRoom that was added to the room on or before March 1, 2015:</span></span>
  
```
Clear-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -EndDate "3/1/2015"
```

## <a name="remove-a-message-from-a-room"></a><span data-ttu-id="d6e83-198">ルームからメッセージを削除する</span><span class="sxs-lookup"><span data-stu-id="d6e83-198">Remove a message from a room</span></span>

<span data-ttu-id="d6e83-p121">**Remove-CsPersistentChatMessage** コマンドレットを使用すると、常設チャット データベース内の 1 つ以上のメッセージを削除し、オプションで既定のメッセージまたは管理者が指定したメッセージに置き換えることができます。たとえば、次のコマンドを実行すると、ITChatRoom チャット ルームから、ユーザー kenmyer@contoso.com によって投稿されたすべてのメッセージが削除されます。</span><span class="sxs-lookup"><span data-stu-id="d6e83-p121">You can remove one or more messages in the Persistent Chat database, and optionally replace the message with a default message or with an administrator-provided message, by using the **Remove-CsPersistentChatMessage** cmdlet. For example, the following command removes all the messages from the ITChatRoom chat room that were posted by the user kenmyer@contoso.com:</span></span>
  
```
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com"
```

<span data-ttu-id="d6e83-201">次の例では、その削除されたすべてのメッセージが「削除されました」という通知で置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="d6e83-201">The next example replaces any removed messages with the note that the message is no longer available:</span></span>
  
```
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com" -ReplaceMessage "This message is no longer available."
```

## <a name="remove-a-room"></a><span data-ttu-id="d6e83-202">ルームを削除する</span><span class="sxs-lookup"><span data-stu-id="d6e83-202">Remove a room</span></span>

<span data-ttu-id="d6e83-203">**Remove-CsPersistentChatRoom** コマンドレットを使用すると、ルームを削除できます。</span><span class="sxs-lookup"><span data-stu-id="d6e83-203">You can remove a room by using the **Remove-CsPersistentChatRoom** cmdlet.</span></span>
  
<span data-ttu-id="d6e83-204">たとえば、次のコマンドを実行すると、チャット ルーム RedmondChatRoom が削除されます。</span><span class="sxs-lookup"><span data-stu-id="d6e83-204">For example, the following command removes the chat room RedmondChatRoom:</span></span>
  
```
Remove-CsPersistentChatRoom -Identity "atl-gc-001.contoso.com\RedmondChatRoom"
```

## <a name="move-a-room-from-one-category-to-another"></a><span data-ttu-id="d6e83-205">あるカテゴリから別のカテゴリにチャット ルームを移動する</span><span class="sxs-lookup"><span data-stu-id="d6e83-205">Move a room from one category to another</span></span>

<span data-ttu-id="d6e83-p122">チャット ルーム マネージャーが別のカテゴリの**作成者**特権を持っている場合、あるカテゴリから別のカテゴリにルームを移動できます。ルームは削除と再作成が行われるのではなく、データベース内で関連付けが変更されます。</span><span class="sxs-lookup"><span data-stu-id="d6e83-p122">If a chat room manager has **Creator** privileges in another category, he or she can move the room from one category to another. The room is not deleted and recreated. It is a change of association within the database.</span></span>
  
<span data-ttu-id="d6e83-p123">チャット ルームのカテゴリの変更は、できるだけ行わないようにする必要があり、変更する場合も注意が必要です。カテゴリはチャット ルームの許可されるメンバーシップを決定するので、チャット ルームを別のカテゴリに移動すると、新しいカテゴリでサポートされなくなったシステム アクセス制御リスト (SACL) は削除されます。たとえば、移動前のルームのメンバーが、新しいカテゴリに移動することにより許可されるメンバーではなくなると、ルームのメンバーシップが変更されて、そのユーザーはルームから削除されます。</span><span class="sxs-lookup"><span data-stu-id="d6e83-p123">Changing a chat room category should be done rarely and with caution. A category determines the allowed membership for the chat room, so when a chat room is moved to another category, all the system access control lists (SACLs) that are no longer supported by the new category are purged. For example, if a user was a member of the room and is no longer an allowed member in the new category, the room membership will be modified and the user will be removed from the room.</span></span>
  

