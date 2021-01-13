---
title: Skype for Business 2015 でのクライアント エクスペリエンスの構成
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
description: '概要: このトピックでは、Skype for Business ユーザーのクライアント エクスペリエンスを構成する方法について説明します。'
ms.openlocfilehash: 2125f911927bfe1aa8898c89c6ad70439186a8c0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805957"
---
# <a name="configure-the-client-experience-with-skype-for-business-2015"></a><span data-ttu-id="0cb96-103">Skype for Business 2015 でのクライアント エクスペリエンスの構成</span><span class="sxs-lookup"><span data-stu-id="0cb96-103">Configure the client experience with Skype for Business 2015</span></span>
 
<span data-ttu-id="0cb96-104">**概要:** このトピックでは、Skype for Business 2015 ユーザーのクライアント エクスペリエンスを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0cb96-104">**Summary:** Read this topic to learn how to configure the client experience for Skype for Business 2015 users.</span></span>
  
<span data-ttu-id="0cb96-105">Skype for Business 2015 は、Skype コンシューマー製品のエクスペリエンスに基づく新しいユーザー エクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="0cb96-105">Skype for Business 2015 provides a new user experience that is based on the Skype consumer product experience.</span></span> <span data-ttu-id="0cb96-106">Skype for Business は、Lync のすべての機能に加えて、簡素化されたコントロールと使い慣れたアイコンを備え、新機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="0cb96-106">In addition to all the features of Lync, Skype for Business provides new features with simplified controls and familiar icons.</span></span> <span data-ttu-id="0cb96-107">新しいクライアント エクスペリエンスの詳細については、「Skype for Business の探索」 [を参照してください](https://go.microsoft.com/fwlink/?LinkId=529022)。</span><span class="sxs-lookup"><span data-stu-id="0cb96-107">For detailed information about the new client experience, see [Explore Skype for Business](https://go.microsoft.com/fwlink/?LinkId=529022).</span></span>
  
<span data-ttu-id="0cb96-108">Skype for Business Server は、新しい Skype for Business クライアント エクスペリエンスと Lync クライアント エクスペリエンスをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="0cb96-108">Skype for Business Server supports the new Skype for Business client experience as well as the Lync client experience.</span></span> <span data-ttu-id="0cb96-109">管理者は、ユーザーに優先するクライアント エクスペリエンスを選択できます。</span><span class="sxs-lookup"><span data-stu-id="0cb96-109">As an administrator, you can choose the preferred client experience for your users.</span></span> <span data-ttu-id="0cb96-110">たとえば、組織内のユーザーが新しい Skype for Business エクスペリエンスのトレーニングを完全に受け入れるまで、Lync クライアント エクスペリエンスを展開できます。</span><span class="sxs-lookup"><span data-stu-id="0cb96-110">For example, you might want to deploy the Lync client experience until users in your organization are fully trained in the new Skype for Business experience.</span></span> <span data-ttu-id="0cb96-111">または、まだすべてのユーザーを Skype for Business Server にアップグレードしていない場合は、すべてのユーザーが新しいサーバーにアップグレードされるまで、すべてのユーザーに同じクライアント エクスペリエンスを提供できます。</span><span class="sxs-lookup"><span data-stu-id="0cb96-111">Or, if you have not yet upgraded all users to Skype for Business Server, you might want all users to have the same client experience until all are upgraded to the new server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="0cb96-112">組織に Skype for Business Server と Lync Server の両方が展開されている場合、既定のクライアント エクスペリエンスはサーバーのバージョンと UI 設定によって異なります。</span><span class="sxs-lookup"><span data-stu-id="0cb96-112">If your organization has both Skype for Business Server and Lync Server deployed, the default client experience will differ depending on server versions and UI settings.</span></span> <span data-ttu-id="0cb96-113">ユーザーが初めて Skype for Business を起動すると、Lync クライアント エクスペリエンスを選択した場合でも、常に Skype for Business ユーザー インターフェイスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0cb96-113">When users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience.</span></span> <span data-ttu-id="0cb96-114">数分後、ユーザーは Lync モードに切り替える必要があります。</span><span class="sxs-lookup"><span data-stu-id="0cb96-114">After several minutes, users are asked to switch to Lync mode.</span></span> <span data-ttu-id="0cb96-115">詳細については、このトピックの **「最初の起動クライアントの動作** 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0cb96-115">For more information, see **First launch client behavior** later in this topic.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0cb96-116">Lync 2013 クライアント エクスペリエンスは、Skype for Business 2016 クライアント バージョン以降のオプションではありません。</span><span class="sxs-lookup"><span data-stu-id="0cb96-116">The Lync 2013 client experience is not an option for Skype for Business 2016 client versions or later.</span></span> <span data-ttu-id="0cb96-117">Lync 2013 クライアントを使用するためのクライアント環境の構成を試みる前に、クライアントのバージョンを確認して、番号 16 で始まるのではないか確認してください。例: 16.x.x.x。</span><span class="sxs-lookup"><span data-stu-id="0cb96-117">Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span> 
  
## <a name="configure-the-client-experience"></a><span data-ttu-id="0cb96-118">クライアント エクスペリエンスの構成</span><span class="sxs-lookup"><span data-stu-id="0cb96-118">Configure the client experience</span></span>

<span data-ttu-id="0cb96-119">EnableSkypeUI パラメーターで **Set-CSClientPolicy** コマンドレットを使用すると、組織内のユーザーに表示されるクライアント エクスペリエンスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="0cb96-119">You can specify the client experience the users in your organization will see by using the **Set-CSClientPolicy** cmdlet with the EnableSkypeUI parameter:</span></span>
  
```powershell
Set-CsClientPolicy  [-Identity <XdsIdentity] [-EnableSkypeUI <$true | $false>]
```

<span data-ttu-id="0cb96-120">ここで、XdsIdentity はグローバル ポリシーまたは名前付きサイト ポリシーを参照します。</span><span class="sxs-lookup"><span data-stu-id="0cb96-120">where XdsIdentity refers to the Global policy or a named site policy.</span></span>
  
<span data-ttu-id="0cb96-121">次のコマンドは、グローバル ポリシーの影響を受ける組織内のすべてのユーザーの Skype for Business クライアント エクスペリエンスを選択します (サイトまたはユーザー固有のポリシーはグローバル ポリシーより優先されます)。</span><span class="sxs-lookup"><span data-stu-id="0cb96-121">The following command selects the Skype for Business client experience for all users in your organization affected by the Global policy (remember, site or user-specific policies override the Global policy):</span></span> 
  
```powershell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $true
```

<span data-ttu-id="0cb96-122">次のコマンドは、グローバル ポリシーの影響を受ける組織内のすべてのユーザーの Lync クライアント エクスペリエンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="0cb96-122">The next command selects the Lync client experience for all users in your organization affected by the Global policy:</span></span>
  
```powershell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $false
```

<span data-ttu-id="0cb96-123">次のコマンドは、Redmond サイト内のすべてのユーザーの Skype for Business クライアント エクスペリエンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="0cb96-123">The next command selects the Skype for Business client experience for all users within the Redmond site:</span></span>
  
```powershell
Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true
```

<span data-ttu-id="0cb96-124">組織内の特定のユーザーのクライアント エクスペリエンスを構成する場合は **、New-CsClientPolicy** コマンドレットを使用して新しいユーザー ポリシーを作成し **、Grant-CsClientPolicy** コマンドレットを使用してポリシーを特定のユーザーに割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="0cb96-124">If you want to configure the client experience for specific users within your organization, you can create a new user policy by using the **New-CsClientPolicy** cmdlet, and then assign the policy to specific users by using the **Grant-CsClientPolicy** cmdlet.</span></span>
  
<span data-ttu-id="0cb96-125">たとえば、次のコマンドを実行すると、Skype for Business クライアント エクスペリエンスを選択する新しいクライアント ポリシー SalesClientUI が作成されます。</span><span class="sxs-lookup"><span data-stu-id="0cb96-125">For example, the following command creates a new client policy, SalesClientUI, that selects the Skype for Business client experience:</span></span>
  
```powershell
New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true
```

<span data-ttu-id="0cb96-126">次のコマンドでは、Sales 部門のすべてのメンバーにポリシー SalesClientUI を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="0cb96-126">The next command assigns the policy, SalesClientUI, to all members of the Sales department:</span></span>
  
```powershell
Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI
```

## <a name="first-launch-client-behaviors"></a><span data-ttu-id="0cb96-127">最初の起動クライアントの動作</span><span class="sxs-lookup"><span data-stu-id="0cb96-127">First launch client behaviors</span></span>

<span data-ttu-id="0cb96-128">既定では、ユーザーが Skype for Business 2015 を初めて起動すると、前述のように EnableSkypeUI パラメーターの値を $False に設定して Lync クライアント エクスペリエンスを選択した場合でも、Skype for Business ユーザー インターフェイスが常に表示されます。</span><span class="sxs-lookup"><span data-stu-id="0cb96-128">By default, when users launch Skype for Business 2015 for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the value of the EnableSkypeUI parameter to $False as described previously.</span></span> <span data-ttu-id="0cb96-129">数分後、ユーザーは Lync モードに切り替える必要があります。</span><span class="sxs-lookup"><span data-stu-id="0cb96-129">After several minutes, users will then be asked to switch to Lync mode.</span></span>
  
<span data-ttu-id="0cb96-130">ユーザーが初めて Skype for Business クライアントを起動するときに Lync ユーザー インターフェイスを表示する場合は、更新後にクライアントを初めて起動する前に、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0cb96-130">If you want to display the Lync user interface when users launch the Skype for Business client for the first time, follow these steps before the client is started for the first time after being updated:</span></span>
  
1. <span data-ttu-id="0cb96-131">前に説明したように、使用しているポリシー$False値が設定  `EnableSkypeUI` されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0cb96-131">Confirm that the value of  `EnableSkypeUI` is set to $False in the policy you are using as described previously.</span></span>
    
2. <span data-ttu-id="0cb96-132">ユーザーのコンピューターのシステム レジストリを更新します。</span><span class="sxs-lookup"><span data-stu-id="0cb96-132">Update the system registry on the user's computer.</span></span> <span data-ttu-id="0cb96-133">これは、ユーザーが初めて Skype for Business クライアントを起動する前に行う必要があります。この操作は 1 回だけ行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="0cb96-133">You should do this before the first time users launch the Skype for Business client, and you should do this only once.</span></span> <span data-ttu-id="0cb96-134">ドメインに参加しているコンピューターでレジストリを更新するグループ ポリシー オブジェクトを作成する方法については、後のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0cb96-134">For information about how to create a Group Policy Object to update the registry on a domain joined computer, see the section later in the topic.</span></span>
    
    <span data-ttu-id="0cb96-135">**[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync] キーで**、新しい Binary 値を **作成** します。</span><span class="sxs-lookup"><span data-stu-id="0cb96-135">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** key, create a new **Binary** value.</span></span>
    
    <span data-ttu-id="0cb96-136">値 **の名前は** **EnableSkypeUI** にする必要があります。 **また、値** データは **00 00 00 00** に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0cb96-136">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span></span>
    
    <span data-ttu-id="0cb96-137">キーは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="0cb96-137">The key should look like the following:</span></span>
    
   <pre>
   [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
   "CanSharePptInCollab"=dword:00000001
   "CanShareOneNoteInCollab"=dword:00000001
   "CanAppShareInCollab"=dword:00000001
   "EnableSkypeUI"=hex:00,00,00,00
   </pre>

<span data-ttu-id="0cb96-138">ユーザーが初めて Skype for Business クライアントを起動すると、Lync ユーザー インターフェイスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0cb96-138">The Lync user interface will now be displayed when users launch the Skype for Business client for the first time.</span></span>
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a><span data-ttu-id="0cb96-139">ようこそ画面のチュートリアルの表示を制御する</span><span class="sxs-lookup"><span data-stu-id="0cb96-139">Control the display of the Welcome screen tutorial</span></span>

<span data-ttu-id="0cb96-140">ユーザーが Skype for Business クライアントを開いた場合の既定の動作では、ほとんどのユーザーが求める 7 つのクイック ヒントを含むようこそ画面  *が表示されます*。</span><span class="sxs-lookup"><span data-stu-id="0cb96-140">When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes  *7 Quick tips most people ask for*.</span></span> <span data-ttu-id="0cb96-141">[ようこそ] 画面の表示をオフにすることもできますが、クライアント コンピューターで次のレジストリ値を追加することで、ユーザーがチュートリアルにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="0cb96-141">You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span></span>
  
<span data-ttu-id="0cb96-142">**[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** キーで、新しい **DWORD (32 ビット) 値を作成します**。</span><span class="sxs-lookup"><span data-stu-id="0cb96-142">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="0cb96-143">値 **の名前は** **IsBasicTu valuelSeenByUser** で **、Value** データは **1** に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0cb96-143">The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span></span>
  
<span data-ttu-id="0cb96-144">キーは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="0cb96-144">The key should look like the following:</span></span>
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a><span data-ttu-id="0cb96-145">クライアントチュートリアルをオフにする</span><span class="sxs-lookup"><span data-stu-id="0cb96-145">Turn off the client tutorial</span></span>

<span data-ttu-id="0cb96-146">ユーザーがチュートリアルにアクセスできない場合は、次のレジストリ値を使用してクライアント チュートリアルをオフにできます。</span><span class="sxs-lookup"><span data-stu-id="0cb96-146">If you do not want your users to be able to access the tutorial, you can turn off the client tutorial with the following Registry value:</span></span>
  
<span data-ttu-id="0cb96-147">**[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** キーで、新しい **DWORD (32 ビット) 値を作成します**。</span><span class="sxs-lookup"><span data-stu-id="0cb96-147">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="0cb96-148">値 **の名前は** **TutorialFeatureEnabled** で、 **値** データは **0** に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0cb96-148">The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span></span>
  
<span data-ttu-id="0cb96-149">Lync</span><span class="sxs-lookup"><span data-stu-id="0cb96-149">Lync</span></span>
  
```console
"TutorialFeatureEnabled"=dword:00000000
```

<span data-ttu-id="0cb96-150">このチュートリアルを有効に戻すには、値データ **を** **1 に設定します**。</span><span class="sxs-lookup"><span data-stu-id="0cb96-150">You can turn the tutorial back on by setting the **Value data** to **1**.</span></span>
  
## <a name="default-client-behaviors"></a><span data-ttu-id="0cb96-151">既定のクライアント動作</span><span class="sxs-lookup"><span data-stu-id="0cb96-151">Default client behaviors</span></span>

<span data-ttu-id="0cb96-152">組織に Skype for Business Server と Lync Server の両方が展開されている場合、クライアント エクスペリエンスはサーバーのバージョンと Skype UI 設定によって異なります。</span><span class="sxs-lookup"><span data-stu-id="0cb96-152">If your organization has both Skype for Business Server and Lync Server deployed, the client experience will differ depending on server versions and the Skype UI setting.</span></span> <span data-ttu-id="0cb96-153">次の表に、サーバーバージョンと UI 設定に基づく初期クライアント エクスペリエンスを示します。</span><span class="sxs-lookup"><span data-stu-id="0cb96-153">The following table shows the initial client experience based on server version and the UI setting:</span></span>
  

|<span data-ttu-id="0cb96-154">**サーバーのバージョン**</span><span class="sxs-lookup"><span data-stu-id="0cb96-154">**Server version**</span></span>|<span data-ttu-id="0cb96-155">**EnableSkypeUI 設定**</span><span class="sxs-lookup"><span data-stu-id="0cb96-155">**EnableSkypeUI setting**</span></span>|<span data-ttu-id="0cb96-156">**クライアント エクスペリエンス**</span><span class="sxs-lookup"><span data-stu-id="0cb96-156">**Client experience**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0cb96-157">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0cb96-157">Skype for Business Server</span></span> |<span data-ttu-id="0cb96-158">既定値</span><span class="sxs-lookup"><span data-stu-id="0cb96-158">Default</span></span>  <br/> |<span data-ttu-id="0cb96-159">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="0cb96-159">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="0cb96-160">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0cb96-160">Skype for Business Server</span></span>  |<span data-ttu-id="0cb96-161">正</span><span class="sxs-lookup"><span data-stu-id="0cb96-161">True</span></span>  <br/> |<span data-ttu-id="0cb96-162">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="0cb96-162">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="0cb96-163">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0cb96-163">Skype for Business Server</span></span>  |<span data-ttu-id="0cb96-164">False</span><span class="sxs-lookup"><span data-stu-id="0cb96-164">False</span></span>  <br/> |<span data-ttu-id="0cb96-165">ユーザーが Lync モードに切り替える必要があります (UI 設定を [Skype for Business] に変更した場合、ユーザーは後で Skype for Business に$true)</span><span class="sxs-lookup"><span data-stu-id="0cb96-165">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="0cb96-166">Lync Server 2010 または Lync Server 2013 (修正プログラムが正しい場合)</span><span class="sxs-lookup"><span data-stu-id="0cb96-166">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="0cb96-167">既定値</span><span class="sxs-lookup"><span data-stu-id="0cb96-167">Default</span></span>  <br/> |<span data-ttu-id="0cb96-168">ユーザーが Lync モードに切り替える必要があります (UI 設定を [Skype for Business] に変更した場合、ユーザーは後で Skype for Business に$true)</span><span class="sxs-lookup"><span data-stu-id="0cb96-168">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="0cb96-169">Lync Server 2010 または Lync Server 2013 (修正プログラムが正しい場合)</span><span class="sxs-lookup"><span data-stu-id="0cb96-169">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="0cb96-170">正</span><span class="sxs-lookup"><span data-stu-id="0cb96-170">True</span></span>  <br/> |<span data-ttu-id="0cb96-171">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="0cb96-171">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="0cb96-172">Lync Server 2010 または Lync Server 2013 (修正プログラムが正しい場合)</span><span class="sxs-lookup"><span data-stu-id="0cb96-172">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="0cb96-173">False</span><span class="sxs-lookup"><span data-stu-id="0cb96-173">False</span></span>  <br/> |<span data-ttu-id="0cb96-174">ユーザーが Lync モードに切り替える必要があります (UI 設定を [Skype for Business] に変更した場合、ユーザーは後で Skype for Business に$true)</span><span class="sxs-lookup"><span data-stu-id="0cb96-174">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="0cb96-175">Lync Server 2010 または Lync Server 2013 (パッチなし)</span><span class="sxs-lookup"><span data-stu-id="0cb96-175">Lync Server 2010 or Lync Server 2013 (without patches)</span></span>  <br/> |<span data-ttu-id="0cb96-176">既定値</span><span class="sxs-lookup"><span data-stu-id="0cb96-176">Default</span></span>  <br/> |<span data-ttu-id="0cb96-177">ユーザーが Lync モードに切り替える必要があります (ユーザーは後で Skype for Business に切り替えできません)</span><span class="sxs-lookup"><span data-stu-id="0cb96-177">User asked to switch to Lync mode (user cannot switch to Skype for Business later)</span></span>  <br/> |
   
<span data-ttu-id="0cb96-178">次の表に、管理者が Skype UI エクスペリエンスの初期設定を変更した場合のクライアント エクスペリエンスを示します。</span><span class="sxs-lookup"><span data-stu-id="0cb96-178">The next table shows the client experience when the administrator changes the initial setting for the Skype UI experience:</span></span>
  

|<span data-ttu-id="0cb96-179">**サーバーのバージョン**</span><span class="sxs-lookup"><span data-stu-id="0cb96-179">**Server version**</span></span>|<span data-ttu-id="0cb96-180">**EnableSkypeUI 設定**</span><span class="sxs-lookup"><span data-stu-id="0cb96-180">**EnableSkypeUI setting**</span></span>|<span data-ttu-id="0cb96-181">**クライアント UI = Lync**</span><span class="sxs-lookup"><span data-stu-id="0cb96-181">**Client UI = Lync**</span></span>|<span data-ttu-id="0cb96-182">**クライアント UI = Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="0cb96-182">**Client UI = Skype for Business**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0cb96-183">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0cb96-183">Skype for Business Server</span></span> |<span data-ttu-id="0cb96-184">正</span><span class="sxs-lookup"><span data-stu-id="0cb96-184">True</span></span>  <br/> |<span data-ttu-id="0cb96-185">ユーザーが Skype for Business に切り替える必要がありました</span><span class="sxs-lookup"><span data-stu-id="0cb96-185">User asked to switch to Skype for Business</span></span>  <br/> |<span data-ttu-id="0cb96-186">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="0cb96-186">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="0cb96-187">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0cb96-187">Skype for Business Server</span></span> |<span data-ttu-id="0cb96-188">False</span><span class="sxs-lookup"><span data-stu-id="0cb96-188">False</span></span>  <br/> |<span data-ttu-id="0cb96-189">Lync モード</span><span class="sxs-lookup"><span data-stu-id="0cb96-189">Lync mode</span></span>  <br/> |<span data-ttu-id="0cb96-190">ユーザーが Lync モードに切り替える必要がありました</span><span class="sxs-lookup"><span data-stu-id="0cb96-190">User asked to switch to Lync mode</span></span>  <br/> |
|<span data-ttu-id="0cb96-191">Lync Server 2010 または Lync Server 2013 (修正プログラムが正しい場合)</span><span class="sxs-lookup"><span data-stu-id="0cb96-191">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="0cb96-192">正</span><span class="sxs-lookup"><span data-stu-id="0cb96-192">True</span></span>  <br/> |<span data-ttu-id="0cb96-193">ユーザーが Skype for Business に切り替える必要がありました</span><span class="sxs-lookup"><span data-stu-id="0cb96-193">User asked to switch to Skype for Business</span></span>  <br/> |<span data-ttu-id="0cb96-194">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="0cb96-194">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="0cb96-195">Lync Server 2010 または Lync Server 2013 (修正プログラムが正しい場合)</span><span class="sxs-lookup"><span data-stu-id="0cb96-195">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="0cb96-196">False</span><span class="sxs-lookup"><span data-stu-id="0cb96-196">False</span></span>  <br/> |<span data-ttu-id="0cb96-197">Lync モード</span><span class="sxs-lookup"><span data-stu-id="0cb96-197">Lync mode</span></span>  <br/> |<span data-ttu-id="0cb96-198">ユーザーが Lync モードに切り替える</span><span class="sxs-lookup"><span data-stu-id="0cb96-198">User asked to switch to Lync mode</span></span>  <br/> |
|<span data-ttu-id="0cb96-199">Lync Server 2010 または Lync Server 2013 (パッチなし)</span><span class="sxs-lookup"><span data-stu-id="0cb96-199">Lync Server 2010 or Lync Server 2013 (without patches)</span></span>  <br/> |<span data-ttu-id="0cb96-200">既定値</span><span class="sxs-lookup"><span data-stu-id="0cb96-200">Default</span></span>  <br/> |<span data-ttu-id="0cb96-201">Lync モード (Skype for Business に切り替えできない)</span><span class="sxs-lookup"><span data-stu-id="0cb96-201">Lync mode (cannot switch to Skype for Business)</span></span>  <br/> |<span data-ttu-id="0cb96-202">Lync モード (Skype for Business に切り替えできない)</span><span class="sxs-lookup"><span data-stu-id="0cb96-202">Lync mode (cannot switch to Skype for Business)</span></span>  <br/> |
   
<span data-ttu-id="0cb96-203">Skype for Business クライアントの構成を管理するために必要な修正プログラムのバージョンは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0cb96-203">The patch versions required to manage the configuration of the Skype for Business client are:</span></span>
  
- <span data-ttu-id="0cb96-204">Lync Server 2010 - 2015 年 2 月 Lync Server 2010 の累積的な更新プログラム (4.0.7577.710)</span><span class="sxs-lookup"><span data-stu-id="0cb96-204">Lync Server 2010 - February 2015 Cumulative Update (4.0.7577.710) for Lync Server 2010.</span></span> <span data-ttu-id="0cb96-205">詳細については[、「Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)の更新プログラム」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0cb96-205">For information, see [Updates for Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)</span></span>
    
- <span data-ttu-id="0cb96-206">Lync Server 2013 - Lync Server 2013 用の 2014 年 12 月の累積的な更新プログラム (5.0.8308.857)。</span><span class="sxs-lookup"><span data-stu-id="0cb96-206">Lync Server 2013 - December 2014 Cumulative Update (5.0.8308.857) for Lync Server 2013.</span></span> <span data-ttu-id="0cb96-207">詳細については [、「Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772)の更新プログラム」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0cb96-207">For information, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).</span></span>
    
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a><span data-ttu-id="0cb96-208">グループ ポリシー オブジェクトを作成してドメインに参加しているコンピューターのレジストリを変更する</span><span class="sxs-lookup"><span data-stu-id="0cb96-208">Create a Group Policy Object to modify the registry on a domain joined computer</span></span>

<span data-ttu-id="0cb96-209">ユーザーが初めて Skype for Business 2015 クライアントを起動する場合に Lync クライアント エクスペリエンスを表示するレジストリ更新は、1 回だけ行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="0cb96-209">The registry update to display the Lync client experience the first time a user launches the Skype for Business 2015 client should be done only once.</span></span> <span data-ttu-id="0cb96-210">グループ ポリシー オブジェクト (GPO) を使用してレジストリを更新する場合は、値データを更新するのではなく、新しい値を作成するオブジェクトを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0cb96-210">If you use a Group Policy Object (GPO) to update the registry, you need to define the object to create a new value rather than update the Value data.</span></span> <span data-ttu-id="0cb96-211">GPO が適用されると、新しい値が存在しない場合、GPO によって作成され、値データが 0 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="0cb96-211">When the GPO is applied, if the new value does not exist, the GPO will create it and set the Value data to 0.</span></span> 
  
<span data-ttu-id="0cb96-212">次の手順では、ユーザーが初めて Skype for Business 2015 クライアントを起動する場合に Lync クライアント エクスペリエンスが表示されるレジストリを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0cb96-212">The following procedure describes how to modify the registry so that the Lync client experience is displayed the first time a user launches the Skype for Business 2015 client.</span></span> <span data-ttu-id="0cb96-213">この手順を使用してレジストリを更新し、前述のようにようこそ画面のチュートリアルを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="0cb96-213">You can also use this procedure to update the registry to disable the Welcome screen tutorial as described earlier.</span></span>
  
### <a name="to-create-the-gpo"></a><span data-ttu-id="0cb96-214">GPO を作成するには</span><span class="sxs-lookup"><span data-stu-id="0cb96-214">To create the GPO</span></span>

1. <span data-ttu-id="0cb96-215">グループ ポリシー **管理コンソールを起動します**。</span><span class="sxs-lookup"><span data-stu-id="0cb96-215">Start the **Group Policy Management console**.</span></span>
    
    <span data-ttu-id="0cb96-216">グループ ポリシー管理コンソールの使い方については、グループ ポリシー管理コンソール [を参照してください](https://go.microsoft.com/fwlink/?LinkId=532759)。</span><span class="sxs-lookup"><span data-stu-id="0cb96-216">For information about how to use the Group Policy Management Console, see [Group Policy Management Console](https://go.microsoft.com/fwlink/?LinkId=532759).</span></span>
    
2. <span data-ttu-id="0cb96-217">[グループ ポリシー オブジェクト] **ノードを右クリックし** 、メニューの **[新規** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0cb96-217">Right-click the **Group Policy Objects** node and select **New** on the menu.</span></span>
    
3. <span data-ttu-id="0cb96-218">[新 **しい GPO]** ダイアログで、GPO の名前 (MakeLyncDefaultUI など) を入力し **、[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0cb96-218">In the **New GPO** dialog, enter a name for the GPO, for example,MakeLyncDefaultUI, and then click **OK**.</span></span>
    
4. <span data-ttu-id="0cb96-219">作成した新しい GPO を右クリックし、メニューから **[** 編集] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0cb96-219">Right-click on the new GPO you just created and then select **Edit** from the menu.</span></span>
    
5. <span data-ttu-id="0cb96-220">グループ ポリシー **管理エディターで**、[ユーザーの構成]を展開し、[基本設定] を展開し **、[Windows の** 設定] を展開して、[レジストリ] ノード **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="0cb96-220">In the **Group Policy Management Editor**, expand **User Configuration**, expand **Preferences**, expand **Windows Settings**, and then select the **Registry** node.</span></span>
    
6. <span data-ttu-id="0cb96-221">レジストリ ノードを右クリックし **、[** 新しいレジストリ項目]  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0cb96-221">Right-click on the **Registry** node, and then select **New** > **Registry Item**.</span></span>
    
7. <span data-ttu-id="0cb96-222">[新 **しいレジストリのプロパティ] ダイアログ** で、以下を更新します。</span><span class="sxs-lookup"><span data-stu-id="0cb96-222">On the **New Registry Properties** dialog, update the following:</span></span>
    
   |<span data-ttu-id="0cb96-223">**Field**</span><span class="sxs-lookup"><span data-stu-id="0cb96-223">**Field**</span></span>|<span data-ttu-id="0cb96-224">**選択または入力する値**</span><span class="sxs-lookup"><span data-stu-id="0cb96-224">**Value to select or enter**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="0cb96-225">**操作**</span><span class="sxs-lookup"><span data-stu-id="0cb96-225">**Action**</span></span> <br/> |<span data-ttu-id="0cb96-226">**Create**</span><span class="sxs-lookup"><span data-stu-id="0cb96-226">**Create**</span></span> <br/> |
   |<span data-ttu-id="0cb96-227">**ハイブ**</span><span class="sxs-lookup"><span data-stu-id="0cb96-227">**Hive**</span></span> <br/> | <span data-ttu-id="0cb96-228">HKEY_CURRENT_USER</span><span class="sxs-lookup"><span data-stu-id="0cb96-228">HKEY_CURRENT_USER</span></span> <br/> |
   |<span data-ttu-id="0cb96-229">**キー パス**</span><span class="sxs-lookup"><span data-stu-id="0cb96-229">**Key Path**</span></span> <br/> |<span data-ttu-id="0cb96-230">Software\Microsoft\Office\Lync</span><span class="sxs-lookup"><span data-stu-id="0cb96-230">Software\Microsoft\Office\Lync</span></span>  <br/> |
   |<span data-ttu-id="0cb96-231">**値の名前**</span><span class="sxs-lookup"><span data-stu-id="0cb96-231">**Value name**</span></span> <br/> |<span data-ttu-id="0cb96-232">EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="0cb96-232">EnableSkypeUI</span></span>  <br/> |
   |<span data-ttu-id="0cb96-233">**値の型**</span><span class="sxs-lookup"><span data-stu-id="0cb96-233">**Value type**</span></span> <br/> |<span data-ttu-id="0cb96-234">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="0cb96-234">REG_BINARY</span></span>  <br/> |
   |<span data-ttu-id="0cb96-235">**Value data**</span><span class="sxs-lookup"><span data-stu-id="0cb96-235">**Value data**</span></span> <br/> |<span data-ttu-id="0cb96-236">00000000</span><span class="sxs-lookup"><span data-stu-id="0cb96-236">00000000</span></span>  <br/> |
   
8. <span data-ttu-id="0cb96-237">**[OK]** をクリックして変更を保存し、GPO を閉じます。</span><span class="sxs-lookup"><span data-stu-id="0cb96-237">Click **OK** to save your changes, and then close the GPO.</span></span>
    
<span data-ttu-id="0cb96-238">次に、作成した GPO を、ポリシーを割り当てるユーザーのグループ (OU など) にリンクする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0cb96-238">Next, you'll need to link the GPO you created to the group of users that you want to assign the policy to, such as an OU.</span></span>
  
### <a name="to-use-the-gpo-to-assign-the-policy"></a><span data-ttu-id="0cb96-239">GPO を使用してポリシーを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="0cb96-239">To use the GPO to assign the policy</span></span>

1. <span data-ttu-id="0cb96-240">グループ ポリシー管理コンソールで、ポリシーを割り当てる OU を右クリックし、既存の GPO へのリンク **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0cb96-240">In the Group Policy Management Console, right-click on the OU you want to assign the policy to, and then select **Link to an existing GPO**.</span></span>
    
2. <span data-ttu-id="0cb96-241">[GPO **の選択] ダイアログ** で、作成した GPO を選択し **、[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0cb96-241">On the **Select GPO** dialog, select the GPO you created, and then select **OK**.</span></span>
    
3. <span data-ttu-id="0cb96-242">ターゲット ユーザーのコンピューターで、コマンド プロンプトを開き、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="0cb96-242">On the target user's computer, open a command prompt and type the following command:</span></span>
       
```console
gpupdate /target:user
```

    
    The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.
    
4. <span data-ttu-id="0cb96-243">コマンド プロンプトで、以下のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="0cb96-243">At the command prompt, type the following command:</span></span>
    
    <span data-ttu-id="0cb96-244">**gpresult /r**</span><span class="sxs-lookup"><span data-stu-id="0cb96-244">**gpresult /r**</span></span>
    
    <span data-ttu-id="0cb96-245">[割り当てられたグループ ポリシー オブジェクト] が表示され、下に作成した GPO の名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0cb96-245">You should see "Assigned Group Policy Objects" with the name of the GPO you created displayed below.</span></span>
    
<span data-ttu-id="0cb96-246">また、レジストリを調べて、GPO がユーザーのコンピューター上のレジストリを正常に更新したのを確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="0cb96-246">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry.</span></span> <span data-ttu-id="0cb96-247">レジストリ エディターを開き **、[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync] キーに移動** します。</span><span class="sxs-lookup"><span data-stu-id="0cb96-247">Open Registry Editor and navigate to the **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** key.</span></span> <span data-ttu-id="0cb96-248">GPO がレジストリを正常に更新すると、EnableSkypeUI という名前の値が 0 で表示されます。</span><span class="sxs-lookup"><span data-stu-id="0cb96-248">If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span></span>
  

