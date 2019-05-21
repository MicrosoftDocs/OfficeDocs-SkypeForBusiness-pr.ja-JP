---
title: Skype for Business Server 2015 での常設チャット ルームのアドインの構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1037909-0750-411a-98c1-3a327eed4ae8
description: '概要: Skype for Business Server 2015 で常設チャットサーバーチャットルーム用のアドインを構成する方法について説明します。'
ms.openlocfilehash: 08e71ab989734572d9d44f0bdb42c01511e47f4c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279327"
---
# <a name="configure-add-ins-for-persistent-chat-rooms-in-skype-for-business-server-2015"></a><span data-ttu-id="6db6a-103">Skype for Business Server 2015 での常設チャット ルームのアドインの構成</span><span class="sxs-lookup"><span data-stu-id="6db6a-103">Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="6db6a-104">**概要:** Skype for Business Server 2015 の常設チャットサーバーチャットルーム用のアドインを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6db6a-104">**Summary:** Learn how to configure add-ins for Persistent Chat Server chat rooms in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="6db6a-105">アドインは、URL をチャット ルームと関連付けることでルーム内でのエクスペリエンスを拡張するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="6db6a-105">Add-ins are used to extend the in-room experience by associating URLs with chat rooms.</span></span> <span data-ttu-id="6db6a-106">これらの URL は、クライアントの会話拡張機能ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="6db6a-106">These URLs appear in the client conversation extensibility pane.</span></span> <span data-ttu-id="6db6a-107">一般的なアドインには、株式のティッカーがチャットルームに投稿されたときに受信する Silverlight アプリケーションを指す URL が含まれている場合があります。また、拡張機能ウィンドウには、株式履歴が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6db6a-107">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="6db6a-108">チャット ルームに OneNote 2013 の URL をアドインとして埋め込んで、"優先事項" や "今日のトピック" などの共有コンテキストを組み込むこともできます。</span><span class="sxs-lookup"><span data-stu-id="6db6a-108">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>
  
 <span data-ttu-id="6db6a-109">クライアントでアドインを確認できるようにするには、そのアドインを登録済みアドインのリストに追加する必要があります。さらに、チャット ルームのマネージャーまたは作成者がルームとアドインを関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="6db6a-109">Before users can see an add-in in the client, you must add the add-in to the list of registered add-ins, and chat room Managers or Creators need to associate rooms with the add-in.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6db6a-110">常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="6db6a-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="6db6a-111">Teams でも同じ機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6db6a-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="6db6a-112">詳細については、「 [Skype For business から Microsoft Teams への旅](/microsoftteams/journey-skypeforbusiness-teams)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6db6a-112">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="6db6a-113">常設チャットを使用する必要がある場合は、この機能が必要なユーザーをチームに移行するか、Skype for Business Server 2015 を使い続けるかのいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="6db6a-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="configure-add-ins-for-chat-rooms-by-using-the-control-panel"></a><span data-ttu-id="6db6a-114">コントロール パネルを使用してチャット ルームのアドインを構成する</span><span class="sxs-lookup"><span data-stu-id="6db6a-114">Configure add-ins for chat rooms by using the Control Panel</span></span>

<span data-ttu-id="6db6a-115">コントロール パネルを使用してチャット ルームのアドインを構成するには</span><span class="sxs-lookup"><span data-stu-id="6db6a-115">To configure add-ins for chat rooms by using the Control Panel:</span></span>
  
1. <span data-ttu-id="6db6a-116">CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="6db6a-116">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="6db6a-117">[**スタート**] メニューで、[Skype For business Server] コントロールパネルを選択するか、ブラウザーウィンドウを開き、管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="6db6a-117">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="6db6a-118">左側のナビゲーション バーで [**常設チャット**] をクリックして、[**アドイン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6db6a-118">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>
    
    <span data-ttu-id="6db6a-119">複数の常設チャットサーバープールの展開の場合、ドロップダウンリストから適切なプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="6db6a-119">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>
    
4. <span data-ttu-id="6db6a-120">[**アドイン**] ページで、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6db6a-120">On the **Add-in** page, click **New**.</span></span>
    
5. <span data-ttu-id="6db6a-121">[**サービスの選択**] で、アドインを作成する必要がある常設チャットサーバープールに対応するサービスを選びます。</span><span class="sxs-lookup"><span data-stu-id="6db6a-121">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="6db6a-122">アドインは、プール間で移動したり、異なるプール間で共有したりできません。</span><span class="sxs-lookup"><span data-stu-id="6db6a-122">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>
    
6. <span data-ttu-id="6db6a-123">[**新しいアドイン**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="6db6a-123">In **New Add-in**, do the following:</span></span>
    
   - <span data-ttu-id="6db6a-124">[**名前**] に、新しいアドインの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="6db6a-124">In **Name**, specify a name for the new add-in.</span></span>
    
   - <span data-ttu-id="6db6a-p104">[**URL**] に、アドインに関連付ける URL を指定します。URL には、http および https プロトコルのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6db6a-p104">In **URL**, specify the URL to be associated with the add-in. URLs are limited to the http and https protocols.</span></span>
    
7. <span data-ttu-id="6db6a-127">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6db6a-127">Click **Commit**.</span></span>
    
## <a name="configure-add-ins-by-using-windows-powershell"></a><span data-ttu-id="6db6a-128">Windows PowerShell を使用してアドインを構成する</span><span class="sxs-lookup"><span data-stu-id="6db6a-128">Configure add-ins by using Windows PowerShell</span></span>

<span data-ttu-id="6db6a-p105">次の Windows PowerShell コマンドレットを使用すると、チャット ルームのアドインを構成できます。使用できるすべてのパラメーターを含む構文の詳細については、「[Skype for Business Server 2015 Management Shell](../management-shell.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6db6a-p105">You can configure add-ins for chat rooms by using the following Windows PowerShell cmdlets. For details about syntax, including all available parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="6db6a-131">**コマンドレット**</span><span class="sxs-lookup"><span data-stu-id="6db6a-131">**Cmdlet**</span></span>|<span data-ttu-id="6db6a-132">**説明**</span><span class="sxs-lookup"><span data-stu-id="6db6a-132">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6db6a-133">New-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="6db6a-133">New-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="6db6a-134">新しいアドインを作成する</span><span class="sxs-lookup"><span data-stu-id="6db6a-134">Create a new add-in</span></span>  <br/> |
|<span data-ttu-id="6db6a-135">Set-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="6db6a-135">Set-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="6db6a-136">既存のアドインの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="6db6a-136">Configure settings for an existing add-in</span></span>  <br/> |
|<span data-ttu-id="6db6a-137">Get-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="6db6a-137">Get-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="6db6a-138">アドインに関する情報を取得する</span><span class="sxs-lookup"><span data-stu-id="6db6a-138">Retrieve information about add-ins</span></span>  <br/> |
|<span data-ttu-id="6db6a-139">Remove-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="6db6a-139">Remove-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="6db6a-140">アドインを削除する</span><span class="sxs-lookup"><span data-stu-id="6db6a-140">Remove an add-in</span></span>  <br/> |
   
### <a name="create-a-new-add-in"></a><span data-ttu-id="6db6a-141">新しいアドインを作成する</span><span class="sxs-lookup"><span data-stu-id="6db6a-141">Create a new add-in</span></span>

<span data-ttu-id="6db6a-142">新しいアドインを作成するには、 **CsPersistentChatAddin**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="6db6a-142">You can create a new Add-in by using the **New-CsPersistentChatAddin** cmdlet.</span></span>
  
<span data-ttu-id="6db6a-143">たとえば、次のコマンドは、プール atl-cs-001.contoso.com の新しいアドイン (name ITPersistentChatAddin) を作成します。</span><span class="sxs-lookup"><span data-stu-id="6db6a-143">For example, the following command creates a new add-in (with the name ITPersistentChatAddin) for the pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="6db6a-144">URL パラメーターとパラメーター値http://atl-cs-001.contoso.com/itchatは、アドインの web ページの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="6db6a-144">The URL parameter and the parameter value http://atl-cs-001.contoso.com/itchat specify the location of the add-in's webpage:</span></span>
  
```
New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -Url "http://atl-cs-001.contoso.com/itchat"
```

### <a name="configure-settings-for-an-existing-add-in"></a><span data-ttu-id="6db6a-145">既存のアドインの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="6db6a-145">Configure settings for an existing add-in</span></span>

<span data-ttu-id="6db6a-146">**Set-CsPersistentChatAddIn** コマンドレットを使用すると、既存のアドインの設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="6db6a-146">You can configure settings for an existing add-in by using the **Set-CsPersistentChatAddIn** cmdlet.</span></span> <span data-ttu-id="6db6a-147">たとえば、以下のコマンドを実行すると、常設チャット アドイン ITPersistentChatAddin に割り当てられている URL が変更されます。</span><span class="sxs-lookup"><span data-stu-id="6db6a-147">For example, the following command modifies the URL assigned to the Persistent Chat add-in ITPersistentChatAddin.</span></span> <span data-ttu-id="6db6a-148">この場合、URL は次のように変更されます。http://atl-cs-001.contoso.com/itchat2:</span><span class="sxs-lookup"><span data-stu-id="6db6a-148">In this case, the URL is changed to http://atl-cs-001.contoso.com/itchat2:</span></span>
  
```
Set-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITPersistentChatAddin" -Url "http://atl-cs-001.contoso.com/itchat2"
```

### <a name="retrieve-information-about-add-ins"></a><span data-ttu-id="6db6a-149">アドインに関する情報を取得する</span><span class="sxs-lookup"><span data-stu-id="6db6a-149">Retrieve information about add-ins</span></span>

<span data-ttu-id="6db6a-p108">**Get-CsPersistentChatAddin** コマンドレットを使用すると、アドインに関する情報を取得できます。たとえば、以下のコマンドを実行すると、組織で使用するために構成されているすべての常設チャット アドインに関する情報が戻されます。</span><span class="sxs-lookup"><span data-stu-id="6db6a-p108">You can get information about add-ins by using the **Get-CsPersistentChatAddin** cmdlet. For example, the following command returns information about all the Persistent Chat add-ins configured for use in the organization:</span></span>
  
```
Get-CsPersistentChatAddin
```

### <a name="remove-an-add-in"></a><span data-ttu-id="6db6a-152">アドインを削除する</span><span class="sxs-lookup"><span data-stu-id="6db6a-152">Remove an add-in</span></span>

<span data-ttu-id="6db6a-153">アドインを削除するには、 **CsPersistentChatAddIn**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="6db6a-153">You can remove an Add-in by using the **Remove-CsPersistentChatAddIn** cmdlet.</span></span> <span data-ttu-id="6db6a-154">たとえば、以下のコマンドを実行すると、atl-cs-001.contoso.com 上にある常設チャット アドイン ITChatAddin が削除されます。</span><span class="sxs-lookup"><span data-stu-id="6db6a-154">For example, the following command removes the Persistent Chat add-in ITChatAddin found on the pool atl-cs-001.contoso.com:</span></span>
  
```
Remove-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITChatAddin"
```


