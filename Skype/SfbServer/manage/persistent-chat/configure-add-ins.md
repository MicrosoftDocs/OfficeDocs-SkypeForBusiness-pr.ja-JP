---
title: Skype for Business Server 2015 での常設チャット ルームのアドインの構成
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1037909-0750-411a-98c1-3a327eed4ae8
description: '概要: は、Skype のビジネス サーバー 2015 の永続的なチャット サーバーのチャット ルームのアドインを構成する方法について説明します。'
ms.openlocfilehash: f96f000c4ac3a78f6ca3ba4972f295e45128ce50
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20967734"
---
# <a name="configure-add-ins-for-persistent-chat-rooms-in-skype-for-business-server-2015"></a><span data-ttu-id="94055-103">Skype for Business Server 2015 での常設チャット ルームのアドインの構成</span><span class="sxs-lookup"><span data-stu-id="94055-103">Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="94055-104">**の概要:** ビジネス サーバー 2015 の Skype での永続的なチャット サーバーのチャット ルームのアドインを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="94055-104">**Summary:** Learn how to configure add-ins for Persistent Chat Server chat rooms in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="94055-105">アドインは、URL をチャット ルームと関連付けることでルーム内でのエクスペリエンスを拡張するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="94055-105">Add-ins are used to extend the in-room experience by associating URLs with chat rooms.</span></span> <span data-ttu-id="94055-106">これらの URL は、クライアントの会話拡張機能ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="94055-106">These URLs appear in the client conversation extensibility pane.</span></span> <span data-ttu-id="94055-107">一般的なアドインでは、株価情報は、チャット ルームがポストされ、拡張機能のウィンドウで株価履歴を表示しますを傍受した Silverlight アプリケーションを指す URL をなどがあります。</span><span class="sxs-lookup"><span data-stu-id="94055-107">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="94055-108">チャット ルームに OneNote 2013 の URL をアドインとして埋め込んで、"優先事項" や "今日のトピック" などの共有コンテキストを組み込むこともできます。</span><span class="sxs-lookup"><span data-stu-id="94055-108">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>
  
 <span data-ttu-id="94055-109">クライアントでアドインを確認できるようにするには、そのアドインを登録済みアドインのリストに追加する必要があります。さらに、チャット ルームのマネージャーまたは作成者がルームとアドインを関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="94055-109">Before users can see an add-in in the client, you must add the add-in to the list of registered add-ins, and chat room Managers or Creators need to associate rooms with the add-in.</span></span>
  
> [!NOTE]
> <span data-ttu-id="94055-110">永続的なチャットですがビジネス サーバー 2015 の Skype で利用可能なビジネス サーバー 2019 の Skype でサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="94055-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="94055-111">同じ機能は、チームで使用できます。</span><span class="sxs-lookup"><span data-stu-id="94055-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="94055-112">詳細については、[マイクロソフトのチームにビジネス用の Skype からの旅](/microsoftteams/journey-skypeforbusiness-teams)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94055-112">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="94055-113">永続的なチャットを使用する場合は、選択肢は、いずれかをチームでは、この機能を必要とするユーザーを移行するまたはビジネス サーバー 2015 の Skype を使用し続ける。</span><span class="sxs-lookup"><span data-stu-id="94055-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="configure-add-ins-for-chat-rooms-by-using-the-control-panel"></a><span data-ttu-id="94055-114">コントロール パネルを使用してチャット ルームのアドインを構成する</span><span class="sxs-lookup"><span data-stu-id="94055-114">Configure add-ins for chat rooms by using the Control Panel</span></span>

<span data-ttu-id="94055-115">コントロール パネルを使用してチャット ルームのアドインを構成するには</span><span class="sxs-lookup"><span data-stu-id="94055-115">To configure add-ins for chat rooms by using the Control Panel:</span></span>
  
1. <span data-ttu-id="94055-116">CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="94055-116">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="94055-117">**[スタート**] メニューから、Skype ビジネス サーバーのコントロール パネルのまたはブラウザー ウィンドウを開きし、管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="94055-117">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="94055-118">左側のナビゲーション バーで [**常設チャット**] をクリックして、[**アドイン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94055-118">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>
    
    <span data-ttu-id="94055-119">複数の永続的なチャット サーバー プールの展開には、ドロップ ダウン リストから適切なプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="94055-119">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>
    
4. <span data-ttu-id="94055-120">[**アドイン**] ページで、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94055-120">On the **Add-in** page, click **New**.</span></span>
    
5. <span data-ttu-id="94055-121">[**サービスの選択**] では、アドインを作成する必要がある永続的なチャット サーバー プールに対応するサービスを選択します。</span><span class="sxs-lookup"><span data-stu-id="94055-121">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="94055-122">アドインは、プール間で移動したり、異なるプール間で共有したりできません。</span><span class="sxs-lookup"><span data-stu-id="94055-122">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>
    
6. <span data-ttu-id="94055-123">[**新しいアドイン**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="94055-123">In **New Add-in**, do the following:</span></span>
    
  - <span data-ttu-id="94055-124">[**名前**] に、新しいアドインの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="94055-124">In **Name**, specify a name for the new add-in.</span></span>
    
  - <span data-ttu-id="94055-p104">[**URL**] に、アドインに関連付ける URL を指定します。URL には、http および https プロトコルのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="94055-p104">In **URL**, specify the URL to be associated with the add-in. URLs are limited to the http and https protocols.</span></span>
    
7. <span data-ttu-id="94055-127">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94055-127">Click **Commit**.</span></span>
    
## <a name="configure-add-ins-by-using-windows-powershell"></a><span data-ttu-id="94055-128">Windows PowerShell を使用してアドインを構成する</span><span class="sxs-lookup"><span data-stu-id="94055-128">Configure add-ins by using Windows PowerShell</span></span>

<span data-ttu-id="94055-129">次の Windows PowerShell コマンドレットを使用すると、チャット ルームのアドインを構成できます。</span><span class="sxs-lookup"><span data-stu-id="94055-129">You can configure add-ins for chat rooms by using the following Windows PowerShell cmdlets.</span></span> <span data-ttu-id="94055-130">などのすべての利用可能なパラメーターの構文の詳細については、 [Skype ビジネス サーバー 2015 管理シェルに](../management-shell.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94055-130">For details about syntax, including all available parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="94055-131">**コマンドレット**</span><span class="sxs-lookup"><span data-stu-id="94055-131">**Cmdlet**</span></span>|<span data-ttu-id="94055-132">**説明**</span><span class="sxs-lookup"><span data-stu-id="94055-132">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="94055-133">新しい-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="94055-133">New-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="94055-134">新しいアドインを作成する</span><span class="sxs-lookup"><span data-stu-id="94055-134">Create a new add-in</span></span>  <br/> |
|<span data-ttu-id="94055-135">セット CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="94055-135">Set-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="94055-136">既存のアドインの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="94055-136">Configure settings for an existing add-in</span></span>  <br/> |
|<span data-ttu-id="94055-137">Get CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="94055-137">Get-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="94055-138">アドインに関する情報を取得する</span><span class="sxs-lookup"><span data-stu-id="94055-138">Retrieve information about add-ins</span></span>  <br/> |
|<span data-ttu-id="94055-139">削除 CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="94055-139">Remove-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="94055-140">アドインを削除する</span><span class="sxs-lookup"><span data-stu-id="94055-140">Remove an add-in</span></span>  <br/> |
   
### <a name="create-a-new-add-in"></a><span data-ttu-id="94055-141">新しいアドインを作成する</span><span class="sxs-lookup"><span data-stu-id="94055-141">Create a new add-in</span></span>

<span data-ttu-id="94055-142">**新規 CsPersistentChatAddin**コマンドレットを使用して、新しいアドインを作成できます。</span><span class="sxs-lookup"><span data-stu-id="94055-142">You can create a new Add-in by using the **New-CsPersistentChatAddin** cmdlet.</span></span>
  
<span data-ttu-id="94055-143">など、新しいアドイン (ITPersistentChatAddin 名) に、プール atl の cs-001.contoso.com の次のコマンドを作成します。</span><span class="sxs-lookup"><span data-stu-id="94055-143">For example, the following command creates a new add-in (with the name ITPersistentChatAddin) for the pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="94055-144">URL パラメーターとパラメーター値http://atl-cs-001.contoso.com/itchatアドインの web ページの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="94055-144">The URL parameter and the parameter value http://atl-cs-001.contoso.com/itchat specify the location of the add-in's webpage:</span></span>
  
```
New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -Url "http://atl-cs-001.contoso.com/itchat"
```

### <a name="configure-settings-for-an-existing-add-in"></a><span data-ttu-id="94055-145">既存のアドインの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="94055-145">Configure settings for an existing add-in</span></span>

<span data-ttu-id="94055-146">**Set-CsPersistentChatAddIn** コマンドレットを使用すると、既存のアドインの設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="94055-146">You can configure settings for an existing add-in by using the **Set-CsPersistentChatAddIn** cmdlet.</span></span> <span data-ttu-id="94055-147">たとえば、以下のコマンドを実行すると、常設チャット アドイン ITPersistentChatAddin に割り当てられている URL が変更されます。</span><span class="sxs-lookup"><span data-stu-id="94055-147">For example, the following command modifies the URL assigned to the Persistent Chat add-in ITPersistentChatAddin.</span></span> <span data-ttu-id="94055-148">URL を変更するこの例では、http://atl-cs-001.contoso.com/itchat2:</span><span class="sxs-lookup"><span data-stu-id="94055-148">In this case, the URL is changed to http://atl-cs-001.contoso.com/itchat2:</span></span>
  
```
Set-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITPersistentChatAddin" -Url "http://atl-cs-001.contoso.com/itchat2"
```

### <a name="retrieve-information-about-add-ins"></a><span data-ttu-id="94055-149">アドインに関する情報を取得する</span><span class="sxs-lookup"><span data-stu-id="94055-149">Retrieve information about add-ins</span></span>

<span data-ttu-id="94055-p108">**Get-CsPersistentChatAddin** コマンドレットを使用すると、アドインに関する情報を取得できます。たとえば、以下のコマンドを実行すると、組織で使用するために構成されているすべての常設チャット アドインに関する情報が戻されます。</span><span class="sxs-lookup"><span data-stu-id="94055-p108">You can get information about add-ins by using the **Get-CsPersistentChatAddin** cmdlet. For example, the following command returns information about all the Persistent Chat add-ins configured for use in the organization:</span></span>
  
```
Get-CsPersistentChatAddin
```

### <a name="remove-an-add-in"></a><span data-ttu-id="94055-152">アドインを削除する</span><span class="sxs-lookup"><span data-stu-id="94055-152">Remove an add-in</span></span>

<span data-ttu-id="94055-153">**削除 CsPersistentChatAddIn**コマンドレットを使用してアドインを削除できます。</span><span class="sxs-lookup"><span data-stu-id="94055-153">You can remove an Add-in by using the **Remove-CsPersistentChatAddIn** cmdlet.</span></span> <span data-ttu-id="94055-154">たとえば、以下のコマンドを実行すると、atl-cs-001.contoso.com 上にある常設チャット アドイン ITChatAddin が削除されます。</span><span class="sxs-lookup"><span data-stu-id="94055-154">For example, the following command removes the Persistent Chat add-in ITChatAddin found on the pool atl-cs-001.contoso.com:</span></span>
  
```
Remove-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITChatAddin"
```


