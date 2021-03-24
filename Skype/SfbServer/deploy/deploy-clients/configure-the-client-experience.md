---
title: Skype for Business 2015 でクライアント エクスペリエンスを構成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 66867a96-ff00-497d-889c-2e908cc384ce
description: '概要: Skype for Business ユーザーのクライアント エクスペリエンスを構成する方法については、このトピックを参照してください。'
ms.openlocfilehash: 1816ff9af6c8c6e28ca72420f843d224587b2c70
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096011"
---
# <a name="configure-the-client-experience-with-skype-for-business-2015"></a><span data-ttu-id="80763-103">Skype for Business 2015 でクライアント エクスペリエンスを構成する</span><span class="sxs-lookup"><span data-stu-id="80763-103">Configure the client experience with Skype for Business 2015</span></span>
 
<span data-ttu-id="80763-104">**概要:** このトピックでは、Skype for Business 2015 ユーザーのクライアント エクスペリエンスを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="80763-104">**Summary:** Read this topic to learn how to configure the client experience for Skype for Business 2015 users.</span></span>
  
<span data-ttu-id="80763-105">Skype for Business 2015 は、Skype コンシューマー製品エクスペリエンスに基づく新しいユーザー エクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="80763-105">Skype for Business 2015 provides a new user experience that is based on the Skype consumer product experience.</span></span> <span data-ttu-id="80763-106">Lync のすべての機能に加えて、Skype for Business は、簡略化されたコントロールと使い慣れたアイコンを備えて新機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="80763-106">In addition to all the features of Lync, Skype for Business provides new features with simplified controls and familiar icons.</span></span> <span data-ttu-id="80763-107">新しいクライアント エクスペリエンスの詳細については [、「Explore Skype for Business」を参照してください](https://go.microsoft.com/fwlink/?LinkId=529022)。</span><span class="sxs-lookup"><span data-stu-id="80763-107">For detailed information about the new client experience, see [Explore Skype for Business](https://go.microsoft.com/fwlink/?LinkId=529022).</span></span>
  
<span data-ttu-id="80763-108">Skype for Business Server は、新しい Skype for Business クライアント エクスペリエンスと Lync クライアント エクスペリエンスをサポートします。</span><span class="sxs-lookup"><span data-stu-id="80763-108">Skype for Business Server supports the new Skype for Business client experience as well as the Lync client experience.</span></span> <span data-ttu-id="80763-109">管理者は、ユーザーに優先するクライアント エクスペリエンスを選択できます。</span><span class="sxs-lookup"><span data-stu-id="80763-109">As an administrator, you can choose the preferred client experience for your users.</span></span> <span data-ttu-id="80763-110">たとえば、組織内のユーザーが新しい Skype for Business エクスペリエンスで完全にトレーニングされるまで、Lync クライアント エクスペリエンスを展開できます。</span><span class="sxs-lookup"><span data-stu-id="80763-110">For example, you might want to deploy the Lync client experience until users in your organization are fully trained in the new Skype for Business experience.</span></span> <span data-ttu-id="80763-111">または、すべてのユーザーを Skype for Business Server にまだアップグレードしていない場合は、すべてのユーザーが新しいサーバーにアップグレードされるまで、すべてのユーザーに同じクライアント エクスペリエンスを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80763-111">Or, if you have not yet upgraded all users to Skype for Business Server, you might want all users to have the same client experience until all are upgraded to the new server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="80763-112">組織で Skype for Business Server と Lync Server の両方が展開されている場合、既定のクライアント エクスペリエンスはサーバーのバージョンと UI 設定によって異なります。</span><span class="sxs-lookup"><span data-stu-id="80763-112">If your organization has both Skype for Business Server and Lync Server deployed, the default client experience will differ depending on server versions and UI settings.</span></span> <span data-ttu-id="80763-113">ユーザーが初めて Skype for Business を起動すると、Lync クライアント エクスペリエンスを選択した場合でも、Skype for Business ユーザー インターフェイスが常に表示されます。</span><span class="sxs-lookup"><span data-stu-id="80763-113">When users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience.</span></span> <span data-ttu-id="80763-114">数分後、ユーザーは Lync モードに切り替える必要があります。</span><span class="sxs-lookup"><span data-stu-id="80763-114">After several minutes, users are asked to switch to Lync mode.</span></span> <span data-ttu-id="80763-115">詳細については、このトピックの「 **クライアントの動作を最初に起動する** 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80763-115">For more information, see **First launch client behavior** later in this topic.</span></span>
  
> [!NOTE]
> <span data-ttu-id="80763-116">Lync 2013 クライアント エクスペリエンスは、Skype for Business 2016 クライアント バージョン以降のオプションではありません。</span><span class="sxs-lookup"><span data-stu-id="80763-116">The Lync 2013 client experience is not an option for Skype for Business 2016 client versions or later.</span></span> <span data-ttu-id="80763-117">Lync 2013 クライアントを使用するクライアント環境を構成する前に、クライアントのバージョンを確認して、番号 16 で始まるのを確認してください。たとえば、16.x.x.x.</span><span class="sxs-lookup"><span data-stu-id="80763-117">Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span> 
  
## <a name="configure-the-client-experience"></a><span data-ttu-id="80763-118">クライアント エクスペリエンスの構成</span><span class="sxs-lookup"><span data-stu-id="80763-118">Configure the client experience</span></span>

<span data-ttu-id="80763-119">EnableSkypeUI パラメーターを使用して **Set-CSClientPolicy** コマンドレットを使用して、組織内のユーザーに表示されるクライアント エクスペリエンスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="80763-119">You can specify the client experience the users in your organization will see by using the **Set-CSClientPolicy** cmdlet with the EnableSkypeUI parameter:</span></span>
  
```powershell
Set-CsClientPolicy  [-Identity <XdsIdentity] [-EnableSkypeUI <$true | $false>]
```

<span data-ttu-id="80763-120">ここで、XdsIdentity はグローバル ポリシーまたは名前付きサイト ポリシーを参照します。</span><span class="sxs-lookup"><span data-stu-id="80763-120">where XdsIdentity refers to the Global policy or a named site policy.</span></span>
  
<span data-ttu-id="80763-121">次のコマンドは、グローバル ポリシーの影響を受ける組織内のすべてのユーザーの Skype for Business クライアント エクスペリエンスを選択します (グローバル ポリシーは、サイトまたはユーザー固有のポリシーによって上書きされます)。</span><span class="sxs-lookup"><span data-stu-id="80763-121">The following command selects the Skype for Business client experience for all users in your organization affected by the Global policy (remember, site or user-specific policies override the Global policy):</span></span> 
  
```powershell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $true
```

<span data-ttu-id="80763-122">次のコマンドは、グローバル ポリシーの影響を受ける組織内のすべてのユーザーの Lync クライアント エクスペリエンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="80763-122">The next command selects the Lync client experience for all users in your organization affected by the Global policy:</span></span>
  
```powershell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $false
```

<span data-ttu-id="80763-123">次のコマンドは、Redmond サイト内のすべてのユーザーの Skype for Business クライアント エクスペリエンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="80763-123">The next command selects the Skype for Business client experience for all users within the Redmond site:</span></span>
  
```powershell
Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true
```

<span data-ttu-id="80763-124">組織内の特定のユーザーに対してクライアント エクスペリエンスを構成する場合は **、New-CsClientPolicy** コマンドレットを使用して新しいユーザー ポリシーを作成し **、Grant-CsClientPolicy** コマンドレットを使用してポリシーを特定のユーザーに割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="80763-124">If you want to configure the client experience for specific users within your organization, you can create a new user policy by using the **New-CsClientPolicy** cmdlet, and then assign the policy to specific users by using the **Grant-CsClientPolicy** cmdlet.</span></span>
  
<span data-ttu-id="80763-125">たとえば、次のコマンドは、Skype for Business クライアント エクスペリエンスを選択する新しいクライアント ポリシー SalesClientUI を作成します。</span><span class="sxs-lookup"><span data-stu-id="80763-125">For example, the following command creates a new client policy, SalesClientUI, that selects the Skype for Business client experience:</span></span>
  
```powershell
New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true
```

<span data-ttu-id="80763-126">次のコマンドは、Sales 部門のすべてのメンバーにポリシー SalesClientUI を割り当てる。</span><span class="sxs-lookup"><span data-stu-id="80763-126">The next command assigns the policy, SalesClientUI, to all members of the Sales department:</span></span>
  
```powershell
Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI
```

## <a name="first-launch-client-behaviors"></a><span data-ttu-id="80763-127">最初の起動クライアントの動作</span><span class="sxs-lookup"><span data-stu-id="80763-127">First launch client behaviors</span></span>

<span data-ttu-id="80763-128">既定では、ユーザーが Skype for Business 2015 を初めて起動すると、前述のように EnableSkypeUI パラメーターの値を $False に設定して Lync クライアント エクスペリエンスを選択した場合でも、Skype for Business ユーザー インターフェイスが常に表示されます。</span><span class="sxs-lookup"><span data-stu-id="80763-128">By default, when users launch Skype for Business 2015 for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the value of the EnableSkypeUI parameter to $False as described previously.</span></span> <span data-ttu-id="80763-129">数分後、ユーザーは Lync モードに切り替える必要があります。</span><span class="sxs-lookup"><span data-stu-id="80763-129">After several minutes, users will then be asked to switch to Lync mode.</span></span>
  
<span data-ttu-id="80763-130">ユーザーが Skype for Business クライアントを初めて起動するときに Lync ユーザー インターフェイスを表示する場合は、更新後にクライアントを初めて開始する前に、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="80763-130">If you want to display the Lync user interface when users launch the Skype for Business client for the first time, follow these steps before the client is started for the first time after being updated:</span></span>
  
1. <span data-ttu-id="80763-131">前に説明したように、使用しているポリシー$Falseの値が設定  `EnableSkypeUI` されているのを確認します。</span><span class="sxs-lookup"><span data-stu-id="80763-131">Confirm that the value of  `EnableSkypeUI` is set to $False in the policy you are using as described previously.</span></span>
    
2. <span data-ttu-id="80763-132">ユーザーのコンピューター上のシステム レジストリを更新します。</span><span class="sxs-lookup"><span data-stu-id="80763-132">Update the system registry on the user's computer.</span></span> <span data-ttu-id="80763-133">これは、ユーザーが初めて Skype for Business クライアントを起動する前に行う必要があります。この操作は 1 回だけ行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="80763-133">You should do this before the first time users launch the Skype for Business client, and you should do this only once.</span></span> <span data-ttu-id="80763-134">ドメインに参加しているコンピューターでレジストリを更新するグループ ポリシー オブジェクトを作成する方法については、後のトピックのセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="80763-134">For information about how to create a Group Policy Object to update the registry on a domain joined computer, see the section later in the topic.</span></span>
    
    <span data-ttu-id="80763-135">**[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync] キーで**、新しい Binary 値を **作成** します。</span><span class="sxs-lookup"><span data-stu-id="80763-135">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** key, create a new **Binary** value.</span></span>
    
    <span data-ttu-id="80763-136">値 **名は** **EnableSkypeUI** で **、Value** データは **00 00 00 00 に設定する必要があります**。</span><span class="sxs-lookup"><span data-stu-id="80763-136">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span></span>
    
    <span data-ttu-id="80763-137">キーは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="80763-137">The key should look like the following:</span></span>
    
   <pre>
   [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
   "CanSharePptInCollab"=dword:00000001
   "CanShareOneNoteInCollab"=dword:00000001
   "CanAppShareInCollab"=dword:00000001
   "EnableSkypeUI"=hex:00,00,00,00
   </pre>

<span data-ttu-id="80763-138">ユーザーが Skype for Business クライアントを初めて起動すると、Lync ユーザー インターフェイスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="80763-138">The Lync user interface will now be displayed when users launch the Skype for Business client for the first time.</span></span>
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a><span data-ttu-id="80763-139">ようこそ画面のチュートリアルの表示を制御する</span><span class="sxs-lookup"><span data-stu-id="80763-139">Control the display of the Welcome screen tutorial</span></span>

<span data-ttu-id="80763-140">ユーザーが Skype for Business クライアントを開く場合、既定の動作は、ほとんどのユーザーが求める 7 つのクイック ヒントを含むようこそ  *画面を表示します*。</span><span class="sxs-lookup"><span data-stu-id="80763-140">When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes  *7 Quick tips most people ask for*.</span></span> <span data-ttu-id="80763-141">[ようこそ] 画面の表示をオフにできますが、クライアント コンピューターに次のレジストリ値を追加することで、ユーザーがチュートリアルにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="80763-141">You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span></span>
  
<span data-ttu-id="80763-142">**[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync] キーで**、新しい **DWORD (32 ビット) の値を作成します**。</span><span class="sxs-lookup"><span data-stu-id="80763-142">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="80763-143">値 **名は** **IsBasicTutorialSeenByUser** である必要があります。 **値** データは **1 に設定する必要があります**。</span><span class="sxs-lookup"><span data-stu-id="80763-143">The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span></span>
  
<span data-ttu-id="80763-144">キーは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="80763-144">The key should look like the following:</span></span>
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a><span data-ttu-id="80763-145">クライアントのチュートリアルをオフにする</span><span class="sxs-lookup"><span data-stu-id="80763-145">Turn off the client tutorial</span></span>

<span data-ttu-id="80763-146">ユーザーがチュートリアルにアクセスできない場合は、次のレジストリ値を使用してクライアント チュートリアルをオフにできます。</span><span class="sxs-lookup"><span data-stu-id="80763-146">If you do not want your users to be able to access the tutorial, you can turn off the client tutorial with the following Registry value:</span></span>
  
<span data-ttu-id="80763-147">**[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync] キーで**、新しい **DWORD (32 ビット) の値を作成します**。</span><span class="sxs-lookup"><span data-stu-id="80763-147">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="80763-148">値 **名は** **TutorialFeatureEnabled** で **、Value** データは **0** に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80763-148">The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span></span>
  
<span data-ttu-id="80763-149">Lync</span><span class="sxs-lookup"><span data-stu-id="80763-149">Lync</span></span>
  
```console
"TutorialFeatureEnabled"=dword:00000000
```

<span data-ttu-id="80763-150">値データを 1 に設定すると、チュートリアル **をオンに\*\*\*\*戻します**。</span><span class="sxs-lookup"><span data-stu-id="80763-150">You can turn the tutorial back on by setting the **Value data** to **1**.</span></span>
  
## <a name="default-client-behaviors"></a><span data-ttu-id="80763-151">既定のクライアント動作</span><span class="sxs-lookup"><span data-stu-id="80763-151">Default client behaviors</span></span>

<span data-ttu-id="80763-152">組織で Skype for Business Server と Lync Server の両方が展開されている場合、クライアント エクスペリエンスはサーバーのバージョンと Skype UI 設定によって異なります。</span><span class="sxs-lookup"><span data-stu-id="80763-152">If your organization has both Skype for Business Server and Lync Server deployed, the client experience will differ depending on server versions and the Skype UI setting.</span></span> <span data-ttu-id="80763-153">次の表に、サーバーのバージョンと UI 設定に基づく初期クライアント エクスペリエンスを示します。</span><span class="sxs-lookup"><span data-stu-id="80763-153">The following table shows the initial client experience based on server version and the UI setting:</span></span>
  

|<span data-ttu-id="80763-154">**サーバーのバージョン**</span><span class="sxs-lookup"><span data-stu-id="80763-154">**Server version**</span></span>|<span data-ttu-id="80763-155">**EnableSkypeUI の設定**</span><span class="sxs-lookup"><span data-stu-id="80763-155">**EnableSkypeUI setting**</span></span>|<span data-ttu-id="80763-156">**クライアント エクスペリエンス**</span><span class="sxs-lookup"><span data-stu-id="80763-156">**Client experience**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="80763-157">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="80763-157">Skype for Business Server</span></span> |<span data-ttu-id="80763-158">既定値</span><span class="sxs-lookup"><span data-stu-id="80763-158">Default</span></span>  <br/> |<span data-ttu-id="80763-159">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="80763-159">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="80763-160">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="80763-160">Skype for Business Server</span></span>  |<span data-ttu-id="80763-161">True</span><span class="sxs-lookup"><span data-stu-id="80763-161">True</span></span>  <br/> |<span data-ttu-id="80763-162">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="80763-162">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="80763-163">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="80763-163">Skype for Business Server</span></span>  |<span data-ttu-id="80763-164">False</span><span class="sxs-lookup"><span data-stu-id="80763-164">False</span></span>  <br/> |<span data-ttu-id="80763-165">Lync モードへの切り替えを求めるユーザー (UI 設定を [Skype for Business] に変更した場合は、後で Skype for Business に切り$true)</span><span class="sxs-lookup"><span data-stu-id="80763-165">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="80763-166">Lync Server 2010 または Lync Server 2013 (正しいパッチ付き)</span><span class="sxs-lookup"><span data-stu-id="80763-166">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="80763-167">既定値</span><span class="sxs-lookup"><span data-stu-id="80763-167">Default</span></span>  <br/> |<span data-ttu-id="80763-168">Lync モードへの切り替えを求めるユーザー (UI 設定を [Skype for Business] に変更した場合は、後で Skype for Business に切り$true)</span><span class="sxs-lookup"><span data-stu-id="80763-168">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="80763-169">Lync Server 2010 または Lync Server 2013 (正しいパッチ付き)</span><span class="sxs-lookup"><span data-stu-id="80763-169">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="80763-170">True</span><span class="sxs-lookup"><span data-stu-id="80763-170">True</span></span>  <br/> |<span data-ttu-id="80763-171">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="80763-171">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="80763-172">Lync Server 2010 または Lync Server 2013 (正しいパッチ付き)</span><span class="sxs-lookup"><span data-stu-id="80763-172">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="80763-173">False</span><span class="sxs-lookup"><span data-stu-id="80763-173">False</span></span>  <br/> |<span data-ttu-id="80763-174">Lync モードへの切り替えを求めるユーザー (UI 設定を [Skype for Business] に変更した場合は、後で Skype for Business に切り$true)</span><span class="sxs-lookup"><span data-stu-id="80763-174">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="80763-175">Lync Server 2010 または Lync Server 2013 (パッチなし)</span><span class="sxs-lookup"><span data-stu-id="80763-175">Lync Server 2010 or Lync Server 2013 (without patches)</span></span>  <br/> |<span data-ttu-id="80763-176">既定値</span><span class="sxs-lookup"><span data-stu-id="80763-176">Default</span></span>  <br/> |<span data-ttu-id="80763-177">Lync モードへの切り替えを求めるユーザー (ユーザーは後で Skype for Business に切り替えできません)</span><span class="sxs-lookup"><span data-stu-id="80763-177">User asked to switch to Lync mode (user cannot switch to Skype for Business later)</span></span>  <br/> |
   
<span data-ttu-id="80763-178">次の表は、管理者が Skype UI エクスペリエンスの初期設定を変更した場合のクライアント エクスペリエンスを示しています。</span><span class="sxs-lookup"><span data-stu-id="80763-178">The next table shows the client experience when the administrator changes the initial setting for the Skype UI experience:</span></span>
  

|<span data-ttu-id="80763-179">**サーバーのバージョン**</span><span class="sxs-lookup"><span data-stu-id="80763-179">**Server version**</span></span>|<span data-ttu-id="80763-180">**EnableSkypeUI の設定**</span><span class="sxs-lookup"><span data-stu-id="80763-180">**EnableSkypeUI setting**</span></span>|<span data-ttu-id="80763-181">**クライアント UI = Lync**</span><span class="sxs-lookup"><span data-stu-id="80763-181">**Client UI = Lync**</span></span>|<span data-ttu-id="80763-182">**クライアント UI = Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="80763-182">**Client UI = Skype for Business**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="80763-183">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="80763-183">Skype for Business Server</span></span> |<span data-ttu-id="80763-184">True</span><span class="sxs-lookup"><span data-stu-id="80763-184">True</span></span>  <br/> |<span data-ttu-id="80763-185">Skype for Business への切り替えを求めるユーザー</span><span class="sxs-lookup"><span data-stu-id="80763-185">User asked to switch to Skype for Business</span></span>  <br/> |<span data-ttu-id="80763-186">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="80763-186">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="80763-187">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="80763-187">Skype for Business Server</span></span> |<span data-ttu-id="80763-188">False</span><span class="sxs-lookup"><span data-stu-id="80763-188">False</span></span>  <br/> |<span data-ttu-id="80763-189">Lync モード</span><span class="sxs-lookup"><span data-stu-id="80763-189">Lync mode</span></span>  <br/> |<span data-ttu-id="80763-190">Lync モードへの切り替えを求めるユーザー</span><span class="sxs-lookup"><span data-stu-id="80763-190">User asked to switch to Lync mode</span></span>  <br/> |
|<span data-ttu-id="80763-191">Lync Server 2010 または Lync Server 2013 (正しいパッチ付き)</span><span class="sxs-lookup"><span data-stu-id="80763-191">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="80763-192">True</span><span class="sxs-lookup"><span data-stu-id="80763-192">True</span></span>  <br/> |<span data-ttu-id="80763-193">Skype for Business への切り替えを求めるユーザー</span><span class="sxs-lookup"><span data-stu-id="80763-193">User asked to switch to Skype for Business</span></span>  <br/> |<span data-ttu-id="80763-194">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="80763-194">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="80763-195">Lync Server 2010 または Lync Server 2013 (正しいパッチ付き)</span><span class="sxs-lookup"><span data-stu-id="80763-195">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="80763-196">False</span><span class="sxs-lookup"><span data-stu-id="80763-196">False</span></span>  <br/> |<span data-ttu-id="80763-197">Lync モード</span><span class="sxs-lookup"><span data-stu-id="80763-197">Lync mode</span></span>  <br/> |<span data-ttu-id="80763-198">Lync モードへの切り替えを求めるユーザー</span><span class="sxs-lookup"><span data-stu-id="80763-198">User asked to switch to Lync mode</span></span>  <br/> |
|<span data-ttu-id="80763-199">Lync Server 2010 または Lync Server 2013 (パッチなし)</span><span class="sxs-lookup"><span data-stu-id="80763-199">Lync Server 2010 or Lync Server 2013 (without patches)</span></span>  <br/> |<span data-ttu-id="80763-200">既定値</span><span class="sxs-lookup"><span data-stu-id="80763-200">Default</span></span>  <br/> |<span data-ttu-id="80763-201">Lync モード (Skype for Business に切り替えできない)</span><span class="sxs-lookup"><span data-stu-id="80763-201">Lync mode (cannot switch to Skype for Business)</span></span>  <br/> |<span data-ttu-id="80763-202">Lync モード (Skype for Business に切り替えできない)</span><span class="sxs-lookup"><span data-stu-id="80763-202">Lync mode (cannot switch to Skype for Business)</span></span>  <br/> |
   
<span data-ttu-id="80763-203">Skype for Business クライアントの構成を管理するために必要なパッチ バージョンは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="80763-203">The patch versions required to manage the configuration of the Skype for Business client are:</span></span>
  
- <span data-ttu-id="80763-204">Lync Server 2010 - 2015 年 2 月 Lync Server 2010 の累積的な更新プログラム (4.0.7577.710)</span><span class="sxs-lookup"><span data-stu-id="80763-204">Lync Server 2010 - February 2015 Cumulative Update (4.0.7577.710) for Lync Server 2010.</span></span> <span data-ttu-id="80763-205">詳細については [、「Updates for Lync Server 2010」を参照してください。](https://go.microsoft.com/fwlink/p/?LinkId=532771)</span><span class="sxs-lookup"><span data-stu-id="80763-205">For information, see [Updates for Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)</span></span>
    
- <span data-ttu-id="80763-206">Lync Server 2013 - 2014 年 12 月 Lync Server 2013 の累積的な更新プログラム (5.0.8308.857)</span><span class="sxs-lookup"><span data-stu-id="80763-206">Lync Server 2013 - December 2014 Cumulative Update (5.0.8308.857) for Lync Server 2013.</span></span> <span data-ttu-id="80763-207">詳細については [、「Updates for Lync Server 2013」を参照してください](https://go.microsoft.com/fwlink/p/?LinkId=532772)。</span><span class="sxs-lookup"><span data-stu-id="80763-207">For information, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).</span></span>
    
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a><span data-ttu-id="80763-208">ドメインに参加しているコンピューター上のレジストリを変更するグループ ポリシー オブジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="80763-208">Create a Group Policy Object to modify the registry on a domain joined computer</span></span>

<span data-ttu-id="80763-209">ユーザーが Skype for Business 2015 クライアントを初めて起動した場合に Lync クライアント エクスペリエンスを表示するレジストリ更新プログラムは、1 回だけ実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80763-209">The registry update to display the Lync client experience the first time a user launches the Skype for Business 2015 client should be done only once.</span></span> <span data-ttu-id="80763-210">グループ ポリシー オブジェクト (GPO) を使用してレジストリを更新する場合は、Value データを更新するのではなく、新しい値を作成するオブジェクトを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80763-210">If you use a Group Policy Object (GPO) to update the registry, you need to define the object to create a new value rather than update the Value data.</span></span> <span data-ttu-id="80763-211">GPO が適用されると、新しい値が存在しない場合、GPO は GPO を作成し、Value データを 0 に設定します。</span><span class="sxs-lookup"><span data-stu-id="80763-211">When the GPO is applied, if the new value does not exist, the GPO will create it and set the Value data to 0.</span></span> 
  
<span data-ttu-id="80763-212">次の手順では、ユーザーが Skype for Business 2015 クライアントを初めて起動した場合に Lync クライアント エクスペリエンスが表示されるレジストリを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="80763-212">The following procedure describes how to modify the registry so that the Lync client experience is displayed the first time a user launches the Skype for Business 2015 client.</span></span> <span data-ttu-id="80763-213">前述のように、この手順を使用してレジストリを更新して、ようこそ画面のチュートリアルを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="80763-213">You can also use this procedure to update the registry to disable the Welcome screen tutorial as described earlier.</span></span>
  
### <a name="to-create-the-gpo"></a><span data-ttu-id="80763-214">GPO を作成するには</span><span class="sxs-lookup"><span data-stu-id="80763-214">To create the GPO</span></span>

1. <span data-ttu-id="80763-215">グループ ポリシー管理 **コンソールを起動します**。</span><span class="sxs-lookup"><span data-stu-id="80763-215">Start the **Group Policy Management console**.</span></span>
    
    <span data-ttu-id="80763-216">グループ ポリシー管理コンソールの使用方法については、「グループ ポリシー管理コンソール [」を参照してください](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn265969(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="80763-216">For information about how to use the Group Policy Management Console, see [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn265969(v=ws.11)).</span></span>
    
2. <span data-ttu-id="80763-217">[グループ ポリシー オブジェクト] ノード **を右クリックし** 、メニューの **[新規]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="80763-217">Right-click the **Group Policy Objects** node and select **New** on the menu.</span></span>
    
3. <span data-ttu-id="80763-218">[新 **しい GPO]** ダイアログで、GPO の名前 (MakeLyncDefaultUI など) を入力し **、[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="80763-218">In the **New GPO** dialog, enter a name for the GPO, for example,MakeLyncDefaultUI, and then click **OK**.</span></span>
    
4. <span data-ttu-id="80763-219">作成した新しい GPO を右クリックし、メニューから **[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="80763-219">Right-click on the new GPO you just created and then select **Edit** from the menu.</span></span>
    
5. <span data-ttu-id="80763-220">グループ ポリシー **管理エディターで**、[ユーザー構成] を展開し、[基本設定] を展開し **、[Windows 設定**] を展開し、[レジストリ]**ノードを選択** します。</span><span class="sxs-lookup"><span data-stu-id="80763-220">In the **Group Policy Management Editor**, expand **User Configuration**, expand **Preferences**, expand **Windows Settings**, and then select the **Registry** node.</span></span>
    
6. <span data-ttu-id="80763-221">[レジストリ] ノードを **右** クリックし、[新しい **レジストリ** アイテム]  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="80763-221">Right-click on the **Registry** node, and then select **New** > **Registry Item**.</span></span>
    
7. <span data-ttu-id="80763-222">[新しい **レジストリのプロパティ] ダイアログで** 、次の項目を更新します。</span><span class="sxs-lookup"><span data-stu-id="80763-222">On the **New Registry Properties** dialog, update the following:</span></span>
    
   |<span data-ttu-id="80763-223">**Field**</span><span class="sxs-lookup"><span data-stu-id="80763-223">**Field**</span></span>|<span data-ttu-id="80763-224">**選択または入力する値**</span><span class="sxs-lookup"><span data-stu-id="80763-224">**Value to select or enter**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="80763-225">**Action**</span><span class="sxs-lookup"><span data-stu-id="80763-225">**Action**</span></span> <br/> |<span data-ttu-id="80763-226">**Create**</span><span class="sxs-lookup"><span data-stu-id="80763-226">**Create**</span></span> <br/> |
   |<span data-ttu-id="80763-227">**ハイブ**</span><span class="sxs-lookup"><span data-stu-id="80763-227">**Hive**</span></span> <br/> | <span data-ttu-id="80763-228">HKEY_CURRENT_USER</span><span class="sxs-lookup"><span data-stu-id="80763-228">HKEY_CURRENT_USER</span></span> <br/> |
   |<span data-ttu-id="80763-229">**キー パス**</span><span class="sxs-lookup"><span data-stu-id="80763-229">**Key Path**</span></span> <br/> |<span data-ttu-id="80763-230">Software\Microsoft\Office\Lync</span><span class="sxs-lookup"><span data-stu-id="80763-230">Software\Microsoft\Office\Lync</span></span>  <br/> |
   |<span data-ttu-id="80763-231">**値の名前**</span><span class="sxs-lookup"><span data-stu-id="80763-231">**Value name**</span></span> <br/> |<span data-ttu-id="80763-232">EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="80763-232">EnableSkypeUI</span></span>  <br/> |
   |<span data-ttu-id="80763-233">**値の型**</span><span class="sxs-lookup"><span data-stu-id="80763-233">**Value type**</span></span> <br/> |<span data-ttu-id="80763-234">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="80763-234">REG_BINARY</span></span>  <br/> |
   |<span data-ttu-id="80763-235">**Value data**</span><span class="sxs-lookup"><span data-stu-id="80763-235">**Value data**</span></span> <br/> |<span data-ttu-id="80763-236">00000000</span><span class="sxs-lookup"><span data-stu-id="80763-236">00000000</span></span>  <br/> |
   
8. <span data-ttu-id="80763-237">**[OK]** をクリックして変更を保存し、GPO を閉じます。</span><span class="sxs-lookup"><span data-stu-id="80763-237">Click **OK** to save your changes, and then close the GPO.</span></span>
    
<span data-ttu-id="80763-238">次に、作成した GPO を、ポリシーを割り当てるユーザーのグループ (OU など) にリンクする必要があります。</span><span class="sxs-lookup"><span data-stu-id="80763-238">Next, you'll need to link the GPO you created to the group of users that you want to assign the policy to, such as an OU.</span></span>
  
### <a name="to-use-the-gpo-to-assign-the-policy"></a><span data-ttu-id="80763-239">GPO を使用してポリシーを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="80763-239">To use the GPO to assign the policy</span></span>

1. <span data-ttu-id="80763-240">グループ ポリシー管理コンソールで、ポリシーを割り当てる OU を右クリックし、[既存の GPO へのリンク **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="80763-240">In the Group Policy Management Console, right-click on the OU you want to assign the policy to, and then select **Link to an existing GPO**.</span></span>
    
2. <span data-ttu-id="80763-241">[GPO **の選択]** ダイアログで、作成した GPO を選択し **、[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="80763-241">On the **Select GPO** dialog, select the GPO you created, and then select **OK**.</span></span>
    
3. <span data-ttu-id="80763-242">ターゲット ユーザーのコンピューターで、コマンド プロンプトを開き、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="80763-242">On the target user's computer, open a command prompt and type the following command:</span></span>
       
```console
gpupdate /target:user
```

    
    The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.
    
4. <span data-ttu-id="80763-243">コマンド プロンプトで、以下のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="80763-243">At the command prompt, type the following command:</span></span>
    
    <span data-ttu-id="80763-244">**gpresult /r**</span><span class="sxs-lookup"><span data-stu-id="80763-244">**gpresult /r**</span></span>
    
    <span data-ttu-id="80763-245">[割り当てられたグループ ポリシー オブジェクト] が表示され、作成した GPO の名前が下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="80763-245">You should see "Assigned Group Policy Objects" with the name of the GPO you created displayed below.</span></span>
    
<span data-ttu-id="80763-246">また、レジストリを調べることによって、GPO がユーザーのコンピューター上のレジストリを正常に更新されたことを確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="80763-246">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry.</span></span> <span data-ttu-id="80763-247">[レジストリ エディター] を開き **、[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync] キーに移動** します。</span><span class="sxs-lookup"><span data-stu-id="80763-247">Open Registry Editor and navigate to the **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** key.</span></span> <span data-ttu-id="80763-248">GPO がレジストリを正常に更新すると、値 0 の EnableSkypeUI という名前の値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="80763-248">If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span></span>
