---
title: Skype for Business Server 2015 での常設チャット ルームのアドインの構成
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c1037909-0750-411a-98c1-3a327eed4ae8
description: '概要: Skype for Business Server 2015 で常設チャット サーバーのチャット ルーム用のアドインを構成する方法について学習します。'
ms.openlocfilehash: 1aca54f3db1229527256d1e2801cb057f4f79387
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815083"
---
# <a name="configure-add-ins-for-persistent-chat-rooms-in-skype-for-business-server-2015"></a><span data-ttu-id="a841c-103">Skype for Business Server 2015 での常設チャット ルームのアドインの構成</span><span class="sxs-lookup"><span data-stu-id="a841c-103">Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a841c-104">**概要:** Skype for Business Server 2015 で常設チャット サーバーのチャット ルーム用のアドインを構成する方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="a841c-104">**Summary:** Learn how to configure add-ins for Persistent Chat Server chat rooms in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="a841c-105">アドインは、URL をチャット ルームに関連付け、ルーム内のエクスペリエンスを拡張するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="a841c-105">Add-ins are used to extend the in-room experience by associating URLs with chat rooms.</span></span> <span data-ttu-id="a841c-106">これらの URL は、クライアントの会話機能拡張ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a841c-106">These URLs appear in the client conversation extensibility pane.</span></span> <span data-ttu-id="a841c-107">一般的なアドインには、株価情報がチャット ルームに投稿され、拡張ウィンドウに株価履歴が表示される Silverlight アプリケーションを指す URL が含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a841c-107">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="a841c-108">また、OneNote 2013 の URL をアドインとしてチャット ルームに組み込み、"優先事項" や "今日のトピック" などの共有コンテキストを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="a841c-108">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>
  
 <span data-ttu-id="a841c-109">ユーザーがクライアントでアドインを表示するには、登録されているアドインの一覧にアドインを追加する必要があります。チャット ルームのマネージャーまたは作成者はルームをアドインに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="a841c-109">Before users can see an add-in in the client, you must add the add-in to the list of registered add-ins, and chat room Managers or Creators need to associate rooms with the add-in.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a841c-110">常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="a841c-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="a841c-111">Teams でも同じ機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a841c-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="a841c-112">詳細については、「Microsoft Teams のアップグレード [の開始」を参照してください](/microsoftteams/upgrade-start-here)。</span><span class="sxs-lookup"><span data-stu-id="a841c-112">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="a841c-113">常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、Skype for Business Server 2015 を引き続き使用するかのどちらかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="a841c-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="configure-add-ins-for-chat-rooms-by-using-the-control-panel"></a><span data-ttu-id="a841c-114">コントロール パネルを使用してチャット ルームのアドインを構成する</span><span class="sxs-lookup"><span data-stu-id="a841c-114">Configure add-ins for chat rooms by using the Control Panel</span></span>

<span data-ttu-id="a841c-115">コントロール パネルを使用してチャット ルームのアドインを構成するには:</span><span class="sxs-lookup"><span data-stu-id="a841c-115">To configure add-ins for chat rooms by using the Control Panel:</span></span>
  
1. <span data-ttu-id="a841c-116">CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="a841c-116">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="a841c-117">[スタート **] メニューから** Skype for Business Server コントロール パネルを選択するか、ブラウザー ウィンドウを開いて管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="a841c-117">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="a841c-118">左側のナビゲーション バーで [**常設チャット**] をクリックして、[**アドイン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a841c-118">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>
    
    <span data-ttu-id="a841c-119">複数の常設チャット サーバー プール展開の場合は、ドロップダウン リストから適切なプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="a841c-119">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>
    
4. <span data-ttu-id="a841c-120">[**アドイン**] ページで、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a841c-120">On the **Add-in** page, click **New**.</span></span>
    
5. <span data-ttu-id="a841c-121">[ **サービスの選択]** で、アドインを作成する必要がある常設チャット サーバー プールに対応するサービスを選択します。</span><span class="sxs-lookup"><span data-stu-id="a841c-121">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="a841c-122">アドインをプール間で移動したり、複数のプールで共有したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a841c-122">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>
    
6. <span data-ttu-id="a841c-123">[**新規 アドイン**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="a841c-123">In **New Add-in**, do the following:</span></span>
    
   - <span data-ttu-id="a841c-124">[**名前**] に、新しいアドインの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a841c-124">In **Name**, specify a name for the new add-in.</span></span>
    
   - <span data-ttu-id="a841c-125">[**URL**] で、アドインに関連付ける URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="a841c-125">In **URL**, specify the URL to be associated with the add-in.</span></span> <span data-ttu-id="a841c-126">URL は http プロトコルと https プロトコルに制限されます。</span><span class="sxs-lookup"><span data-stu-id="a841c-126">URLs are limited to the http and https protocols.</span></span>
    
7. <span data-ttu-id="a841c-127">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a841c-127">Click **Commit**.</span></span>
    
## <a name="configure-add-ins-by-using-windows-powershell"></a><span data-ttu-id="a841c-128">アドインを使用してアドインを構成Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a841c-128">Configure add-ins by using Windows PowerShell</span></span>

<span data-ttu-id="a841c-129">次のコマンドレットを使用して、チャット ルームのアドインWindows PowerShellできます。</span><span class="sxs-lookup"><span data-stu-id="a841c-129">You can configure add-ins for chat rooms by using the following Windows PowerShell cmdlets.</span></span> <span data-ttu-id="a841c-130">使用可能なすべてのパラメーターを含む構文の詳細については [、Skype for Business Server 2015 管理シェルを参照してください](../management-shell.md)。</span><span class="sxs-lookup"><span data-stu-id="a841c-130">For details about syntax, including all available parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="a841c-131">**コマンドレット**</span><span class="sxs-lookup"><span data-stu-id="a841c-131">**Cmdlet**</span></span>|<span data-ttu-id="a841c-132">**説明**</span><span class="sxs-lookup"><span data-stu-id="a841c-132">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a841c-133">New-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="a841c-133">New-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="a841c-134">新しいアドインを作成する</span><span class="sxs-lookup"><span data-stu-id="a841c-134">Create a new add-in</span></span>  <br/> |
|<span data-ttu-id="a841c-135">Set-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="a841c-135">Set-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="a841c-136">既存のアドインの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="a841c-136">Configure settings for an existing add-in</span></span>  <br/> |
|<span data-ttu-id="a841c-137">Get-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="a841c-137">Get-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="a841c-138">アドインに関する情報を取得する</span><span class="sxs-lookup"><span data-stu-id="a841c-138">Retrieve information about add-ins</span></span>  <br/> |
|<span data-ttu-id="a841c-139">Remove-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="a841c-139">Remove-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="a841c-140">アドインを削除する</span><span class="sxs-lookup"><span data-stu-id="a841c-140">Remove an add-in</span></span>  <br/> |
   
### <a name="create-a-new-add-in"></a><span data-ttu-id="a841c-141">新しいアドインを作成する</span><span class="sxs-lookup"><span data-stu-id="a841c-141">Create a new add-in</span></span>

<span data-ttu-id="a841c-142">**New-CsPersistentChatAddin** コマンドレットを使用して、新しいアドインを作成できます。</span><span class="sxs-lookup"><span data-stu-id="a841c-142">You can create a new Add-in by using the **New-CsPersistentChatAddin** cmdlet.</span></span>
  
<span data-ttu-id="a841c-143">たとえば、次のコマンドを実行すると、プール プールの新しいアドイン (ITPersistentChatAddin という名前) が作成atl-cs-001.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="a841c-143">For example, the following command creates a new add-in (with the name ITPersistentChatAddin) for the pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="a841c-144">URL パラメーターとパラメーター値は http://atl-cs-001.contoso.com/itchat 、アドインの Web ページの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="a841c-144">The URL parameter and the parameter value http://atl-cs-001.contoso.com/itchat specify the location of the add-in's webpage:</span></span>
  
```PowerShell
New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -Url "http://atl-cs-001.contoso.com/itchat"
```

### <a name="configure-settings-for-an-existing-add-in"></a><span data-ttu-id="a841c-145">既存のアドインの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="a841c-145">Configure settings for an existing add-in</span></span>

<span data-ttu-id="a841c-146">**Set-CsPersistentChatAddIn** コマンドレットを使用して、既存のアドインの設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="a841c-146">You can configure settings for an existing add-in by using the **Set-CsPersistentChatAddIn** cmdlet.</span></span> <span data-ttu-id="a841c-147">たとえば、次のコマンドは、常設チャット アドイン ITPersistentChatAddin に割り当てられている URL を変更します。</span><span class="sxs-lookup"><span data-stu-id="a841c-147">For example, the following command modifies the URL assigned to the Persistent Chat add-in ITPersistentChatAddin.</span></span> <span data-ttu-id="a841c-148">この場合、URL は次の値に変更されます。 http://atl-cs-001.contoso.com/itchat2:</span><span class="sxs-lookup"><span data-stu-id="a841c-148">In this case, the URL is changed to http://atl-cs-001.contoso.com/itchat2:</span></span>
  
```PowerShell
Set-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITPersistentChatAddin" -Url "http://atl-cs-001.contoso.com/itchat2"
```

### <a name="retrieve-information-about-add-ins"></a><span data-ttu-id="a841c-149">アドインに関する情報を取得する</span><span class="sxs-lookup"><span data-stu-id="a841c-149">Retrieve information about add-ins</span></span>

<span data-ttu-id="a841c-150">**Get-CsPersistentChatAddin** コマンドレットを使用して、アドインに関する情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="a841c-150">You can get information about add-ins by using the **Get-CsPersistentChatAddin** cmdlet.</span></span> <span data-ttu-id="a841c-151">たとえば、次のコマンドを実行すると、組織で使用するように構成された常設チャット アドインに関する情報が戻されます。</span><span class="sxs-lookup"><span data-stu-id="a841c-151">For example, the following command returns information about all the Persistent Chat add-ins configured for use in the organization:</span></span>
  
```PowerShell
Get-CsPersistentChatAddin
```

### <a name="remove-an-add-in"></a><span data-ttu-id="a841c-152">アドインを削除する</span><span class="sxs-lookup"><span data-stu-id="a841c-152">Remove an add-in</span></span>

<span data-ttu-id="a841c-153">**Remove-CsPersistentChatAddIn** コマンドレットを使用してアドインを削除できます。</span><span class="sxs-lookup"><span data-stu-id="a841c-153">You can remove an Add-in by using the **Remove-CsPersistentChatAddIn** cmdlet.</span></span> <span data-ttu-id="a841c-154">たとえば、次のコマンドを実行すると、プール プールにある常設チャット アドイン ITChatAddin が削除atl-cs-001.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="a841c-154">For example, the following command removes the Persistent Chat add-in ITChatAddin found on the pool atl-cs-001.contoso.com:</span></span>
  
```PowerShell
Remove-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITChatAddin"
```


