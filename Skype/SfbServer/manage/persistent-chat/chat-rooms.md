---
title: Skype for Business Server 2015 での常設チャット サーバーでのチャット ルームの管理
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
ms.assetid: 7b2e1302-280c-4efe-9ec8-787687b414da
description: '概要: Skype for Business Server 2015 で常設チャット サーバーのチャット ルームを管理する方法について学習します。'
ms.openlocfilehash: 2b1b2e3bdc3411a4bacae5f1dc81b626abb92a91
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815107"
---
# <a name="manage-chat-rooms-in-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="7f523-103">Skype for Business Server 2015 での常設チャット サーバーでのチャット ルームの管理</span><span class="sxs-lookup"><span data-stu-id="7f523-103">Manage chat rooms in Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="7f523-104">**概要:** Skype for Business Server 2015 で常設チャット サーバーのチャット ルームを管理する方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="7f523-104">**Summary:** Learn how to manage Persistent Chat Server chat rooms in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="7f523-105">カテゴリを正しく使用すると、チャット ルームの作成と管理がはるかに簡単になります。</span><span class="sxs-lookup"><span data-stu-id="7f523-105">Creating and managing chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="7f523-106">カテゴリは、チャット ルームを作成または参加できるユーザーを定義します。</span><span class="sxs-lookup"><span data-stu-id="7f523-106">A category defines who can create or join the chat rooms.</span></span> <span data-ttu-id="7f523-107">チャット ルームを管理する前に [、Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) の常設チャット カテゴリ、チャット ルーム、およびユーザーの役割と [、Skype for Business Server 2015](categories.md)の常設チャット サーバーのカテゴリの管理を必ずお読みください。</span><span class="sxs-lookup"><span data-stu-id="7f523-107">Before you attempt to manage chat rooms, be sure to read [Persistent chat categories, chat rooms, and user roles in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) and [Manage categories in Persistent Chat Server in Skype for Business Server 2015](categories.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="7f523-108">常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="7f523-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="7f523-109">Teams でも同じ機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7f523-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="7f523-110">詳細については、「Microsoft Teams のアップグレード [の開始」を参照してください](/microsoftteams/upgrade-start-here)。</span><span class="sxs-lookup"><span data-stu-id="7f523-110">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="7f523-111">常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、Skype for Business Server 2015 を引き続き使用するかのどちらかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="7f523-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

<span data-ttu-id="7f523-112">Windows PowerShell コマンドライン インターフェイスを使用するか、チャット ルームのメンバーである場合は Skype for Business クライアントを使用して、チャット ルームを構成および管理できます。</span><span class="sxs-lookup"><span data-stu-id="7f523-112">You can configure and manage chat rooms by using the Windows PowerShell command-line interface, or by using the Skype for Business client if you are a member of the chat room.</span></span> <span data-ttu-id="7f523-113">このトピックでは、カスタム コマンド ライン インターフェイスを使用してチャット ルームをWindows PowerShell方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7f523-113">This topic describes how to manage chat rooms by using the Windows PowerShell command-line interface.</span></span> <span data-ttu-id="7f523-114">Skype for Business クライアントを使用してチャット ルームを管理する場合は、クライアントのヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f523-114">If you want to manage chat rooms by using the Skype for Business client, see the client help.</span></span> 
  
<span data-ttu-id="7f523-115">チャット ルームには、標準と大会議室の 2 種類のいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7f523-115">Chat rooms can be one of two types: Normal and Auditorium.</span></span> <span data-ttu-id="7f523-116">標準チャット ルームでは、すべてのメンバーがメッセージを投稿および読み取りできます。</span><span class="sxs-lookup"><span data-stu-id="7f523-116">A Normal chat room allows all members to post and read messages.</span></span> <span data-ttu-id="7f523-117">大講堂は、発表者だけが投稿できるが、すべてのユーザーが読み取り可能なチャット ルームの一種です。</span><span class="sxs-lookup"><span data-stu-id="7f523-117">An Auditorium is a type of chat room where only Presenters can post, but everyone can read.</span></span>
  
<span data-ttu-id="7f523-118">チャット ルームにアクセスして管理できるユーザーは、次のようにユーザーロールによって異なります。</span><span class="sxs-lookup"><span data-stu-id="7f523-118">Who can access and manage chat rooms depends on user roles as follows:</span></span>
  
- <span data-ttu-id="7f523-119">ユーザーがメッセージを投稿および読み取りするには、チャット ルームのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f523-119">Users must be Members of a chat room to be able to post and read messages.</span></span>
    
- <span data-ttu-id="7f523-120">発表者は大会議室に投稿できます。</span><span class="sxs-lookup"><span data-stu-id="7f523-120">Presenters are allowed to post to Auditorium rooms.</span></span>
    
- <span data-ttu-id="7f523-121">管理者は、データベースが大きくなりすぎないようにチャット ルームから古いコンテンツ (たとえば、特定の日付より前に投稿されたコンテンツ) を削除できます。</span><span class="sxs-lookup"><span data-stu-id="7f523-121">Administrators can delete earlier content (for example, content that was posted before a certain date) from any chat room to keep the database from growing too large.</span></span> <span data-ttu-id="7f523-122">管理者は、特定のチャット ルームに対して不適切と見なされるメッセージを削除または置換することもできます。</span><span class="sxs-lookup"><span data-stu-id="7f523-122">Administrators can also remove or replace messages that are considered inappropriate for a particular chat room.</span></span>
    
- <span data-ttu-id="7f523-123">エンドユーザー (メッセージの作成者を含む) は、チャット ルームのコンテンツを削除できません。</span><span class="sxs-lookup"><span data-stu-id="7f523-123">End users, including message authors, cannot delete content from any chat room.</span></span>
    
- <span data-ttu-id="7f523-124">チャット ルームマネージャーは、ルームの無効化を含め、すべてのチャット ルームのプロパティを変更できます。</span><span class="sxs-lookup"><span data-stu-id="7f523-124">Chat room Managers can make changes to all chat room properties, including disabling rooms.</span></span> <span data-ttu-id="7f523-125">ただし、マネージャーは、ルームを削除したり、ルームのカテゴリを変更したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="7f523-125">Managers cannot, however, delete a room, or change the category of a room.</span></span> 
    
- <span data-ttu-id="7f523-126">チャット ルームの作成後に削除できるのは管理者のみです。</span><span class="sxs-lookup"><span data-stu-id="7f523-126">Only Administrators can delete a chat room after it has been created.</span></span>
    
<span data-ttu-id="7f523-127">次のコマンドレットを使用して、チャット ルームをWindows PowerShellできます。</span><span class="sxs-lookup"><span data-stu-id="7f523-127">You can configure and manage chat rooms by using the following Windows PowerShell cmdlets:</span></span>
  

|<span data-ttu-id="7f523-128">**コマンドレット**</span><span class="sxs-lookup"><span data-stu-id="7f523-128">**Cmdlet**</span></span>|<span data-ttu-id="7f523-129">**説明**</span><span class="sxs-lookup"><span data-stu-id="7f523-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7f523-130">New-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="7f523-130">New-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="7f523-131">新しいチャット ルームを作成する</span><span class="sxs-lookup"><span data-stu-id="7f523-131">Create a new chat room</span></span>  <br/> |
|<span data-ttu-id="7f523-132">Set-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="7f523-132">Set-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="7f523-133">既存のルームの設定を構成します。ユーザーとユーザー グループをルームに割り当てる</span><span class="sxs-lookup"><span data-stu-id="7f523-133">Configure settings for an existing room; assign users and user groups to the room</span></span>  <br/> |
|<span data-ttu-id="7f523-134">Get-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="7f523-134">Get-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="7f523-135">ルームに関する情報を取得する</span><span class="sxs-lookup"><span data-stu-id="7f523-135">Retrieve information about rooms</span></span>  <br/> |
|<span data-ttu-id="7f523-136">Clear-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="7f523-136">Clear-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="7f523-137">ルームまたはメッセージをルームから消去する</span><span class="sxs-lookup"><span data-stu-id="7f523-137">Clear a room or messages from a room</span></span>  <br/> |
|<span data-ttu-id="7f523-138">Remove-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="7f523-138">Remove-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="7f523-139">ルームを削除する</span><span class="sxs-lookup"><span data-stu-id="7f523-139">Remove a room</span></span>  <br/> |
|<span data-ttu-id="7f523-140">Remove-CsPersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="7f523-140">Remove-CsPersistentChatMessage</span></span>  <br/> |<span data-ttu-id="7f523-141">ルームからメッセージを削除する</span><span class="sxs-lookup"><span data-stu-id="7f523-141">Remove messages from a room</span></span>  <br/> |
   
<span data-ttu-id="7f523-142">**New-CsPersistentChatRoom** コマンドレットを使用してチャット ルームを作成し **、Set-CsPersistentChatRoom** コマンドレットを使用して、チャット ルームへのユーザーの追加など、既存のチャット ルームを構成します。</span><span class="sxs-lookup"><span data-stu-id="7f523-142">You use the **New-CsPersistentChatRoom** cmdlet to create chat rooms and the **Set-CsPersistentChatRoom** cmdlet to configure an existing chat room, including adding users to the chat room.</span></span> <span data-ttu-id="7f523-143">チャット ルームには、次のパラメーターを構成できます。</span><span class="sxs-lookup"><span data-stu-id="7f523-143">You can configure the following parameters for chat rooms:</span></span>
  
- <span data-ttu-id="7f523-144">無効。</span><span class="sxs-lookup"><span data-stu-id="7f523-144">Disabled.</span></span> <span data-ttu-id="7f523-145">チャット ルームを無効または有効にできます。</span><span class="sxs-lookup"><span data-stu-id="7f523-145">Lets you disable or enable a chat room.</span></span> 
    
- <span data-ttu-id="7f523-146">招待。</span><span class="sxs-lookup"><span data-stu-id="7f523-146">Invitations.</span></span> <span data-ttu-id="7f523-147">チャット ルームへの招待を有効または無効にできます。チャット ルームの招待は、チャット ルームのメンバーとして追加されたユーザーに通知するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="7f523-147">Lets you enable or disable chat room invitations, which are used to notify users when they have been added as chat room members.</span></span> <span data-ttu-id="7f523-148">継承された招待の既定の設定。チャット ルームは、所属するカテゴリで構成された招待設定を採用します。</span><span class="sxs-lookup"><span data-stu-id="7f523-148">The default setting for invitations in inherit, which caused the chat room to adopt the invitation setting configured on the category it belongs to.</span></span> <span data-ttu-id="7f523-149">チャット ルーム レベルで招待の設定を false に構成すると、カテゴリ設定を上書きできます。</span><span class="sxs-lookup"><span data-stu-id="7f523-149">Configuring the invitations setting to false at the chat room level allows the category setting to be overridden.</span></span> 
    
- <span data-ttu-id="7f523-150">プライバシー。</span><span class="sxs-lookup"><span data-stu-id="7f523-150">Privacy.</span></span> <span data-ttu-id="7f523-151">チャット ルームを開く、閉じている、またはシークレットにするかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="7f523-151">Lets you specify whether a chat room is Open, Closed, or Secret.</span></span> <span data-ttu-id="7f523-152">オープン ルームは、だれでも検索およびアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="7f523-152">Open rooms can be searched and accessed by anyone.</span></span> <span data-ttu-id="7f523-153">クローズ ルームは、だれでも検索できますが、メンバーだけがアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="7f523-153">Closed rooms can be searched by anyone, but can be accessed only by members.</span></span> <span data-ttu-id="7f523-154">秘密ルームは、ルームのメンバーだけが検索およびアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="7f523-154">Secret rooms can be searched and accessed only by members of the room.</span></span> <span data-ttu-id="7f523-155">既定では、新しい各ルームは最初は Closed として構成されています。</span><span class="sxs-lookup"><span data-stu-id="7f523-155">By default, each new room is initially configured as Closed.</span></span>
    
- <span data-ttu-id="7f523-156">型。</span><span class="sxs-lookup"><span data-stu-id="7f523-156">Type.</span></span> <span data-ttu-id="7f523-157">チャット ルームが、任意のメンバーによって投稿されたメッセージを受け入れる通常のルームか、発表者だけが投稿したメッセージを受け入れる講堂ルームかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="7f523-157">Lets you specify whether a chat room is a Normal room, which accepts messages posted by any member, or an Auditorium room, which accepts messages posted only by a Presenter.</span></span>
    
- <span data-ttu-id="7f523-158">アドイン。</span><span class="sxs-lookup"><span data-stu-id="7f523-158">Addin.</span></span> <span data-ttu-id="7f523-159">以前に構成したアドインをチャット ルームに関連付け、参加中にメンバーが URL コンテンツを表示できます。</span><span class="sxs-lookup"><span data-stu-id="7f523-159">Lets you associate a previously configured add-in with a chat room, which allows URL content to be viewed by members while participating.</span></span>
    
<span data-ttu-id="7f523-160">上記のパラメーターに加えて **、Set-CsPersistentChatRoom** コマンドレットを使用すると、次のようにチャット ルームにユーザーを割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="7f523-160">In addition to the above parameters, the **Set-CsPersistentChatRoom** cmdlet lets you assign users to the chat room as follows:</span></span>
  
- <span data-ttu-id="7f523-161">メンバー。</span><span class="sxs-lookup"><span data-stu-id="7f523-161">Members.</span></span> <span data-ttu-id="7f523-162">チャット ルームのメンバーシップを構成します。</span><span class="sxs-lookup"><span data-stu-id="7f523-162">Configures membership for the chat room.</span></span> <span data-ttu-id="7f523-163">ユーザーの SIP アドレスを指定することで、1 つのコマンドレットを使用して、個々のメンバーまたは複数のメンバーを追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="7f523-163">You can add or remove either the individual or multiple members using a single cmdlet by specifying the SIP address of the users.</span></span> <span data-ttu-id="7f523-164">ユーザーを一括で追加するために、Active Directory 組織単位または配布グループを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="7f523-164">To allow users to be added in bulk, Active Directory organizational units or distribution groups can also be specified.</span></span>
    
- <span data-ttu-id="7f523-165">マネージャー。</span><span class="sxs-lookup"><span data-stu-id="7f523-165">Managers.</span></span> <span data-ttu-id="7f523-166">チャット ルームにマネージャーを割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="7f523-166">Lets you assign managers to the chat room.</span></span> <span data-ttu-id="7f523-167">マネージャーは、他の設定と共にチャット ルームのメンバーシップを定義するアクセス許可を持っています。</span><span class="sxs-lookup"><span data-stu-id="7f523-167">Managers have the permissions to define membership of a chat room along with other settings.</span></span>
    
- <span data-ttu-id="7f523-168">発表者。</span><span class="sxs-lookup"><span data-stu-id="7f523-168">Presenters.</span></span> <span data-ttu-id="7f523-169">発表者を大室のチャット ルームに割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="7f523-169">Lets you assign presenters to an Auditorium chat room.</span></span> 
    
  <span data-ttu-id="7f523-170">すべてのパラメーターを含む構文の詳細については [、Skype for Business Server 2015 管理シェルを参照してください](../management-shell.md)。</span><span class="sxs-lookup"><span data-stu-id="7f523-170">For details about syntax, including all parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  
## <a name="create-a-new-room"></a><span data-ttu-id="7f523-171">新しいルームを作成する</span><span class="sxs-lookup"><span data-stu-id="7f523-171">Create a new room</span></span>

<span data-ttu-id="7f523-172">**New-CsPersistentChatRoom** コマンドレットを使用して、新しいルームを作成できます。</span><span class="sxs-lookup"><span data-stu-id="7f523-172">You can create a new room by using the **New-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="7f523-173">たとえば、次のコマンドを実行すると、ITChatRoom という名前の新しいチャット ルームがプール に作成atl-cs-001.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="7f523-173">For example, the following command creates a new chat room named ITChatRoom on the pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="7f523-174">この例では、チャット ルームが IT カテゴリに追加されます。</span><span class="sxs-lookup"><span data-stu-id="7f523-174">In this example, the chat room is added to the IT category:</span></span>
  
```PowerShell
New-CsPersistentChatRoom -Name "ITChatRoom" -PersistentChatPoolFqdn "atl-cs-001.contoso.com"-Category "IT"
```

<span data-ttu-id="7f523-175">**注:** 次のいずれかの条件に当てはまる場合、PersistentChatPoolFqdn は必要ではありません。</span><span class="sxs-lookup"><span data-stu-id="7f523-175">**Note:** PersistentChatPoolFqdn is not needed if one of the following is true:</span></span> 
  
- <span data-ttu-id="7f523-176">常設チャット サーバー プールは 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="7f523-176">There is only one Persistent Chat Server pool.</span></span>
    
- <span data-ttu-id="7f523-177">カテゴリにプール FQDN を提供する。</span><span class="sxs-lookup"><span data-stu-id="7f523-177">You provide a pool FQDN to the category.</span></span>
    
- <span data-ttu-id="7f523-178">ルームの追加にプール FQDN を提供する。</span><span class="sxs-lookup"><span data-stu-id="7f523-178">You provide a pool FQDN to adding the room.</span></span>
    
## <a name="configure-an-existing-room"></a><span data-ttu-id="7f523-179">既存のルームを構成する</span><span class="sxs-lookup"><span data-stu-id="7f523-179">Configure an existing room</span></span>

<span data-ttu-id="7f523-180">**Set-CsPersistentChatRoom** コマンドレットを使用して、既存のルームを構成できます。</span><span class="sxs-lookup"><span data-stu-id="7f523-180">You can configure an existing room by using the **Set-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="7f523-181">たとえば、次のコマンドは、user1 をメンバーおよび発表者として割り当て、user2 を管理者として testCat 講堂ルームに割り当てるとします。</span><span class="sxs-lookup"><span data-stu-id="7f523-181">For example, the following command assigns user1 as a Member and Presenter, and user2 as a Manager, of the testCat Auditorium room:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}
Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
```

 <span data-ttu-id="7f523-182">次の例では、Active Directory の NorthAmericaUsers OU のすべてのユーザーを NorthAmerica チャット ルームに追加します。</span><span class="sxs-lookup"><span data-stu-id="7f523-182">The next example adds all the users from the NorthAmericaUsers OU in active Directory to the NorthAmerica chat room:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=contoso,DC=com"}
```

<span data-ttu-id="7f523-183">次の例では、Finance 配布グループのすべてのメンバーを同じチャット ルームに追加します。</span><span class="sxs-lookup"><span data-stu-id="7f523-183">The next example adds all the members from the Finance distribution group to the same chat room:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=contoso,DC=com"}
```

## <a name="disable-or-enable-a-room"></a><span data-ttu-id="7f523-184">ルームを無効または有効にする</span><span class="sxs-lookup"><span data-stu-id="7f523-184">Disable or enable a room</span></span>

<span data-ttu-id="7f523-185">常設チャット ルームのトピックが不要になった場合は、チャット ルームを無効にすることで、ユーザーがチャット ルームを使用不能にできます。</span><span class="sxs-lookup"><span data-stu-id="7f523-185">If the topic of a Persistent Chat room is no longer relevant, you can make the chat room unavailable to users by disabling it.</span></span> <span data-ttu-id="7f523-186">チャット ルームが無効になっていると、すべてのメンバーは直ちにルームから切断されます。</span><span class="sxs-lookup"><span data-stu-id="7f523-186">When a chat room is disabled, all members are immediately disconnected from the room.</span></span> <span data-ttu-id="7f523-187">チャット ルームを無効にすると、ユーザーはチャット ルームに再び参加したり、チャット ルームの検索でチャット ルームを見つけたりできなくなります。</span><span class="sxs-lookup"><span data-stu-id="7f523-187">After a chat room is disabled, users cannot rejoin it or find it in chat room searches.</span></span>
  
<span data-ttu-id="7f523-188">チャット ルームの履歴が保持される場合、チャット ルームが無効な場合、コンテンツは保持されます。</span><span class="sxs-lookup"><span data-stu-id="7f523-188">If the chat room's history persists, the content is preserved when the chat room is disabled.</span></span> <span data-ttu-id="7f523-189">ただし、チャット ルームが無効な状態の間、そのコンテンツは検索に表示されません。</span><span class="sxs-lookup"><span data-stu-id="7f523-189">However, that content will not appear in searches during the time that the chat room remains in a disabled state.</span></span> <span data-ttu-id="7f523-190">後でチャット ルームを有効にした場合、ユーザーはチャット ルームが無効にされる前に投稿されたメッセージを検索できます。</span><span class="sxs-lookup"><span data-stu-id="7f523-190">If you later enable the chat room, users can search for messages that were posted before the chat room was disabled.</span></span> <span data-ttu-id="7f523-191">チャット ルーム履歴の構成の詳細については [、「Manage categories in Persistent Chat Server in Skype for Business Server 2015」](categories.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f523-191">For information about configuring chat room history, see [Manage categories in Persistent Chat Server in Skype for Business Server 2015](categories.md).</span></span> 
  
<span data-ttu-id="7f523-192">チャット ルームを無効にすると、メンバーシップ リストとその他の設定が保持されます。</span><span class="sxs-lookup"><span data-stu-id="7f523-192">If a chat room is disabled, its membership list and other settings are preserved.</span></span> <span data-ttu-id="7f523-193">管理者は、無効になっているルームを有効にできます。設定を手動で作成し変える必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7f523-193">As an administrator, you can enable a room that has been disabled, and you do not need to manually re-create the settings.</span></span>
  
<span data-ttu-id="7f523-194">**Set-CsPersistentChatRoom** コマンドレットを使用し、Disabled パラメーターを True に設定することで、ルームを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="7f523-194">You can disable a room by using the **Set-CsPersistentChatRoom** cmdlet and setting the Disabled parameter to True:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $True
```

<span data-ttu-id="7f523-195">チャット ルームを有効にするには、Disabled パラメーターを False に設定します。</span><span class="sxs-lookup"><span data-stu-id="7f523-195">To enable a chat room, set the Disabled parameter to False:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $False
```

## <a name="get-information-about-rooms"></a><span data-ttu-id="7f523-196">ルームに関する情報を取得する</span><span class="sxs-lookup"><span data-stu-id="7f523-196">Get information about rooms</span></span>

<span data-ttu-id="7f523-197">組織で使用するように構成されたルームに関する情報を取得するには **、Get-CsPersistentChatRoom コマンドレットを使用** できます。</span><span class="sxs-lookup"><span data-stu-id="7f523-197">To get information about the rooms configured for use in your organization, you can use the **Get-CsPersistentChatRoom** cmdlet.</span></span>
  
<span data-ttu-id="7f523-198">次のコマンドは、組織で使用するように構成されたチャット ルームすべてに関する情報を戻します。</span><span class="sxs-lookup"><span data-stu-id="7f523-198">The following command returns information about all the chat rooms configured for use in the organization:</span></span>
  
```PowerShell
Get-CsPersistentChatRoom
```

## <a name="remove-all-content-from-a-room"></a><span data-ttu-id="7f523-199">ルームからすべてのコンテンツを削除する</span><span class="sxs-lookup"><span data-stu-id="7f523-199">Remove all content from a room</span></span>

<span data-ttu-id="7f523-200">**Clear-CsPersistentChatRoom** コマンドレットを使用して、ルームからコンテンツを削除できます。</span><span class="sxs-lookup"><span data-stu-id="7f523-200">You can remove content from a room by using the **Clear-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="7f523-201">たとえば、次のコマンドは、2015 年 3 月 1 日以前にルームに追加された常設チャット ルーム ITChatRoom からすべてのコンテンツを削除します。</span><span class="sxs-lookup"><span data-stu-id="7f523-201">For example, the following command removes all the content from the Persistent Chat room ITChatRoom that was added to the room on or before March 1, 2015:</span></span>
  
```PowerShell
Clear-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -EndDate "3/1/2015"
```

## <a name="remove-a-message-from-a-room"></a><span data-ttu-id="7f523-202">ルームからメッセージを削除する</span><span class="sxs-lookup"><span data-stu-id="7f523-202">Remove a message from a room</span></span>

<span data-ttu-id="7f523-203">**Remove-CsPersistentChatMessage** コマンドレットを使用して、常設チャット データベース内の 1 つ以上のメッセージを削除し、必要に応じてそのメッセージを既定のメッセージまたは管理者が指定したメッセージに置き換える方法があります。</span><span class="sxs-lookup"><span data-stu-id="7f523-203">You can remove one or more messages in the Persistent Chat database, and optionally replace the message with a default message or with an administrator-provided message, by using the **Remove-CsPersistentChatMessage** cmdlet.</span></span> <span data-ttu-id="7f523-204">たとえば、次のコマンドは、ユーザーが投稿した ITChatRoom チャット ルームからすべてのメッセージを削除kenmyer@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="7f523-204">For example, the following command removes all the messages from the ITChatRoom chat room that were posted by the user kenmyer@contoso.com:</span></span>
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com"
```

<span data-ttu-id="7f523-205">次の例では、削除されたメッセージを、メッセージが使用できなくなったというメモに置き換える。</span><span class="sxs-lookup"><span data-stu-id="7f523-205">The next example replaces any removed messages with the note that the message is no longer available:</span></span>
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com" -ReplaceMessage "This message is no longer available."
```

## <a name="remove-a-room"></a><span data-ttu-id="7f523-206">ルームを削除する</span><span class="sxs-lookup"><span data-stu-id="7f523-206">Remove a room</span></span>

<span data-ttu-id="7f523-207">**Remove-CsPersistentChatRoom** コマンドレットを使用して、ルームを削除できます。</span><span class="sxs-lookup"><span data-stu-id="7f523-207">You can remove a room by using the **Remove-CsPersistentChatRoom** cmdlet.</span></span>
  
<span data-ttu-id="7f523-208">たとえば、次のコマンドを実行すると、チャット ルーム RedmondChatRoom が削除されます。</span><span class="sxs-lookup"><span data-stu-id="7f523-208">For example, the following command removes the chat room RedmondChatRoom:</span></span>
  
```PowerShell
Remove-CsPersistentChatRoom -Identity "atl-gc-001.contoso.com\RedmondChatRoom"
```

## <a name="move-a-room-from-one-category-to-another"></a><span data-ttu-id="7f523-209">あるカテゴリから別のカテゴリにルームを移動する</span><span class="sxs-lookup"><span data-stu-id="7f523-209">Move a room from one category to another</span></span>

<span data-ttu-id="7f523-210">チャット ルーム マネージャーが別のカテゴリの作成者特権を持っている場合、ルームをカテゴリ間で移動できます。</span><span class="sxs-lookup"><span data-stu-id="7f523-210">If a chat room manager has **Creator** privileges in another category, he or she can move the room from one category to another.</span></span> <span data-ttu-id="7f523-211">ルームは削除されるのではなく、再作成されます。</span><span class="sxs-lookup"><span data-stu-id="7f523-211">The room is not deleted and recreated.</span></span> <span data-ttu-id="7f523-212">データベース内での関連付けの変更です。</span><span class="sxs-lookup"><span data-stu-id="7f523-212">It is a change of association within the database.</span></span>
  
<span data-ttu-id="7f523-213">チャット ルームのカテゴリの変更は、ほとんど行わず、慎重に行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f523-213">Changing a chat room category should be done rarely and with caution.</span></span> <span data-ttu-id="7f523-214">カテゴリはチャット ルームの許可されるメンバーシップを決定するので、チャット ルームを別のカテゴリに移動すると、新しいカテゴリでサポートされなくなったシステム アクセス制御リスト (SACL) は削除されます。</span><span class="sxs-lookup"><span data-stu-id="7f523-214">A category determines the allowed membership for the chat room, so when a chat room is moved to another category, all the system access control lists (SACLs) that are no longer supported by the new category are purged.</span></span> <span data-ttu-id="7f523-215">たとえば、ユーザーがルームのメンバーであり、新しいカテゴリで許可されなくなったメンバーである場合、ルームのメンバーシップが変更され、ユーザーはルームから削除されます。</span><span class="sxs-lookup"><span data-stu-id="7f523-215">For example, if a user was a member of the room and is no longer an allowed member in the new category, the room membership will be modified and the user will be removed from the room.</span></span>
  

