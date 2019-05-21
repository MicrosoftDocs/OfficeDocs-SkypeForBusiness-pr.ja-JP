---
title: Skype for Business 2015 でクライアントエクスペリエンスを構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 66867a96-ff00-497d-889c-2e908cc384ce
description: '概要: このトピックでは、Skype for Business ユーザーのクライアントエクスペリエンスを構成する方法について説明します。'
ms.openlocfilehash: bf6245b5b26875c7437990f09dd101ece01b1b47
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298285"
---
# <a name="configure-the-client-experience-with-skype-for-business-2015"></a><span data-ttu-id="1120d-103">Skype for Business 2015 でクライアントエクスペリエンスを構成する</span><span class="sxs-lookup"><span data-stu-id="1120d-103">Configure the client experience with Skype for Business 2015</span></span>
 
<span data-ttu-id="1120d-104">**概要:** このトピックでは、Skype for Business 2015 ユーザーのクライアントエクスペリエンスを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1120d-104">**Summary:** Read this topic to learn how to configure the client experience for Skype for Business 2015 users.</span></span>
  
<span data-ttu-id="1120d-105">Skype for Business 2015 は、Skype コンシューマーの製品エクスペリエンスに基づいた新しいユーザーエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="1120d-105">Skype for Business 2015 provides a new user experience that is based on the Skype consumer product experience.</span></span> <span data-ttu-id="1120d-106">Skype for Business には、Lync のすべての機能に加えて、簡単なコントロールと使い慣れたアイコンが付いた新機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="1120d-106">In addition to all the features of Lync, Skype for Business provides new features with simplified controls and familiar icons.</span></span> <span data-ttu-id="1120d-107">新しいクライアントエクスペリエンスの詳細については、「 [Skype For business の紹介](https://go.microsoft.com/fwlink/?LinkId=529022)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1120d-107">For detailed information about the new client experience, see [Explore Skype for Business](https://go.microsoft.com/fwlink/?LinkId=529022).</span></span>
  
<span data-ttu-id="1120d-108">Skype for Business Server では、新しい Skype for Business クライアントエクスペリエンスと Lync クライアントエクスペリエンスがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1120d-108">Skype for Business Server supports the new Skype for Business client experience as well as the Lync client experience.</span></span> <span data-ttu-id="1120d-109">管理者は、ユーザー用に優先するクライアント エクスペリエンスを選択できます。</span><span class="sxs-lookup"><span data-stu-id="1120d-109">As an administrator, you can choose the preferred client experience for your users.</span></span> <span data-ttu-id="1120d-110">たとえば、新しい Skype for Business のエクスペリエンスで組織内のユーザーが完全にトレーニングを受けられるまで、Lync クライアントエクスペリエンスを展開することができます。</span><span class="sxs-lookup"><span data-stu-id="1120d-110">For example, you might want to deploy the Lync client experience until users in your organization are fully trained in the new Skype for Business experience.</span></span> <span data-ttu-id="1120d-111">または、すべてのユーザーを Skype for Business Server にアップグレードしていない場合は、すべてのユーザーが新しいサーバーにアップグレードされるまで、すべてのユーザーが同じクライアントエクスペリエンスを使用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1120d-111">Or, if you have not yet upgraded all users to Skype for Business Server, you might want all users to have the same client experience until all are upgraded to the new server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1120d-112">組織に Skype for Business Server と Lync Server の両方が展開されている場合、既定のクライアントエクスペリエンスはサーバーのバージョンと UI の設定によって異なります。</span><span class="sxs-lookup"><span data-stu-id="1120d-112">If your organization has both Skype for Business Server and Lync Server deployed, the default client experience will differ depending on server versions and UI settings.</span></span> <span data-ttu-id="1120d-113">ユーザーが Skype for Business を初めて起動すると、Lync クライアントエクスペリエンスを選んだ場合でも、常に Skype for business のユーザーインターフェイスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1120d-113">When users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience.</span></span> <span data-ttu-id="1120d-114">数分後に、ユーザーは Lync モードに切り替えるように求められます。</span><span class="sxs-lookup"><span data-stu-id="1120d-114">After several minutes, users are asked to switch to Lync mode.</span></span> <span data-ttu-id="1120d-115">詳細については、このトピックの後半にある「**最初の起動クライアントの動作**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1120d-115">For more information, see **First launch client behavior** later in this topic.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1120d-116">Lync 2013 クライアントエクスペリエンスは、Skype for Business 2016 クライアントバージョン以降では使用できません。</span><span class="sxs-lookup"><span data-stu-id="1120d-116">The Lync 2013 client experience is not an option for Skype for Business 2016 client versions or later.</span></span> <span data-ttu-id="1120d-117">Lync 2013 クライアントを使用するようにクライアント環境を構成する前に、クライアント バージョンを調べて、バージョンの先頭が 16 ではない (16.x.x.x などではない) ことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="1120d-117">Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span> 
  
## <a name="configure-the-client-experience"></a><span data-ttu-id="1120d-118">クライアント エクスペリエンスの構成</span><span class="sxs-lookup"><span data-stu-id="1120d-118">Configure the client experience</span></span>

<span data-ttu-id="1120d-119">以下のように、EnableSkypeUI パラメーターを指定して **Set-CSClientPolicy** コマンドレットを使用すると、組織のユーザーに表示されるクライアント エクスペリエンスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="1120d-119">You can specify the client experience the users in your organization will see by using the **Set-CSClientPolicy** cmdlet with the EnableSkypeUI parameter:</span></span>
  
```
Set-CsClientPolicy  [-Identity <XdsIdentity] [-EnableSkypeUI <$true | $false>]
```

<span data-ttu-id="1120d-120">上記の XdsIdentity は、グローバル ポリシーまたは名前付きサイト ポリシーを指します。</span><span class="sxs-lookup"><span data-stu-id="1120d-120">where XdsIdentity refers to the Global policy or a named site policy.</span></span>
  
<span data-ttu-id="1120d-121">次のコマンドは、組織内のすべてのユーザーに対してグローバルポリシーの影響を受ける Skype for Business クライアントのエクスペリエンスを選択します (「サイトまたはユーザー固有のポリシーはグローバルポリシーを上書きします)」を選択します。</span><span class="sxs-lookup"><span data-stu-id="1120d-121">The following command selects the Skype for Business client experience for all users in your organization affected by the Global policy (remember, site or user-specific policies override the Global policy):</span></span> 
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $true
```

<span data-ttu-id="1120d-122">次のコマンドでは、組織内のすべてのユーザーに対して、グローバルポリシーの影響を受ける Lync クライアントエクスペリエンスが選択されます。</span><span class="sxs-lookup"><span data-stu-id="1120d-122">The next command selects the Lync client experience for all users in your organization affected by the Global policy:</span></span>
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $false
```

<span data-ttu-id="1120d-123">次のコマンドは、Redmond サイト内のすべてのユーザーに対して Skype for Business クライアントエクスペリエンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="1120d-123">The next command selects the Skype for Business client experience for all users within the Redmond site:</span></span>
  
```
Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true
```

<span data-ttu-id="1120d-124">組織内の特定のユーザーに対してクライアントエクスペリエンスを構成する場合は、**新しい**ユーザーポリシーを作成して、**グラント clientpolicy**を使用して特定のユーザーにポリシーを割り当てることができます。コマンドレット.</span><span class="sxs-lookup"><span data-stu-id="1120d-124">If you want to configure the client experience for specific users within your organization, you can create a new user policy by using the **New-CsClientPolicy** cmdlet, and then assign the policy to specific users by using the **Grant-CsClientPolicy** cmdlet.</span></span>
  
<span data-ttu-id="1120d-125">たとえば、次のコマンドは、Skype for Business クライアントエクスペリエンスを選択する新しいクライアントポリシー、SalesClientUI を作成します。</span><span class="sxs-lookup"><span data-stu-id="1120d-125">For example, the following command creates a new client policy, SalesClientUI, that selects the Skype for Business client experience:</span></span>
  
```
New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true
```

<span data-ttu-id="1120d-126">次のコマンドを実行すると、Sales 部門のすべてのメンバーにポリシー SalesClientUI が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="1120d-126">The next command assigns the policy, SalesClientUI, to all members of the Sales department:</span></span>
  
```
Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI
```

## <a name="first-launch-client-behaviors"></a><span data-ttu-id="1120d-127">最初の起動クライアントの動作</span><span class="sxs-lookup"><span data-stu-id="1120d-127">First launch client behaviors</span></span>

<span data-ttu-id="1120d-128">既定では、ユーザーが Skype for business 2015 を初めて起動したときに、以下のように、EnableSkypeUI パラメーターの値を $False に設定して、Lync クライアント環境を選択した場合でも、Skype for Business のユーザーインターフェイスが表示されます。先に。</span><span class="sxs-lookup"><span data-stu-id="1120d-128">By default, when users launch Skype for Business 2015 for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the value of the EnableSkypeUI parameter to $False as described previously.</span></span> <span data-ttu-id="1120d-129">起動から数分後に、Lync モードに切り替えるかどうかを確認するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1120d-129">After several minutes, users will then be asked to switch to Lync mode.</span></span>
  
<span data-ttu-id="1120d-130">ユーザーが初めて Skype for Business クライアントを起動したときに、Lync ユーザー インターフェイスを表示したい場合は、クライアントを更新後に初めて開始する前に、以下の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="1120d-130">If you want to display the Lync user interface when users launch the Skype for Business client for the first time, follow these steps before the client is started for the first time after being updated:</span></span>
  
1. <span data-ttu-id="1120d-131">前に説明した`EnableSkypeUI`ように使用しているポリシーで、の値が $False に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1120d-131">Confirm that the value of  `EnableSkypeUI` is set to $False in the policy you are using as described previously.</span></span>
    
2. <span data-ttu-id="1120d-p106">ユーザーのコンピューターで、システム レジストリを更新します。 レジストリの更新は、ユーザーが初めて Skype for Business クライアントを起動する前に 1 回だけ行う必要があります。 ドメインに参加しているコンピューターでレジストリを更新するグループ ポリシー オブジェクトを作成する方法については、このトピックの後半のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1120d-p106">Update the system registry on the user's computer. You should do this before the first time users launch the Skype for Business client, and you should do this only once. For information about how to create a Group Policy Object to update the registry on a domain joined computer, see the section later in the topic.</span></span>
    
    <span data-ttu-id="1120d-135">**[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** キーに新しい [**バイナリ**] 値を作成します。</span><span class="sxs-lookup"><span data-stu-id="1120d-135">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** key, create a new **Binary** value.</span></span>
    
    <span data-ttu-id="1120d-136">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span><span class="sxs-lookup"><span data-stu-id="1120d-136">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span></span>
    
    <span data-ttu-id="1120d-137">キーは、以下のようになります。</span><span class="sxs-lookup"><span data-stu-id="1120d-137">The key should look like the following:</span></span>
    
   <pre>
   [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
   "CanSharePptInCollab"=dword:00000001
   "CanShareOneNoteInCollab"=dword:00000001
   "CanAppShareInCollab"=dword:00000001
   "EnableSkypeUI"=hex:00,00,00,00
   </pre>

<span data-ttu-id="1120d-138">これで、ユーザーが初めて Skype for Business クライアントを起動したときに、Lync ユーザー インターフェイスが表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="1120d-138">The Lync user interface will now be displayed when users launch the Skype for Business client for the first time.</span></span>
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a><span data-ttu-id="1120d-139">ようこそ画面のチュートリアルの表示を制御する</span><span class="sxs-lookup"><span data-stu-id="1120d-139">Control the display of the Welcome screen tutorial</span></span>

<span data-ttu-id="1120d-140">ユーザーが Skype for Business クライアントを開くと、既定の動作では [ようこそ] 画面が表示されます。これには、*ほとんどのユーザーからの質問に対する7つのヒント*が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1120d-140">When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes  *7 Quick tips most people ask for*.</span></span> <span data-ttu-id="1120d-141">You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span><span class="sxs-lookup"><span data-stu-id="1120d-141">You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span></span>
  
<span data-ttu-id="1120d-p108">**[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** キーに新しい [**DWORD (32 ビット) 値**] を作成します。[**値の名前**] に「**IsBasicTutorialSeenByUser**」と入力し、[**値のデータ**] を「**1**」に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1120d-p108">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** key, create a new **DWORD (32-bit) Value**. The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span></span>
  
<span data-ttu-id="1120d-144">キーは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="1120d-144">The key should look like the following:</span></span>
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a><span data-ttu-id="1120d-145">クライアント チュートリアルをオフにする</span><span class="sxs-lookup"><span data-stu-id="1120d-145">Turn off the client tutorial</span></span>

<span data-ttu-id="1120d-146">ユーザーがチュートリアルにアクセスできないようにするには、次のレジストリ値を指定してクライアント チュートリアルを無効にします。</span><span class="sxs-lookup"><span data-stu-id="1120d-146">If you do not want your users to be able to access the tutorial, you can turn off the client tutorial with the following Registry value:</span></span>
  
<span data-ttu-id="1120d-p109">**[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** キーに新しい [**DWORD (32 ビット) 値**] を作成します。[**値の名前**] に「**TutorialFeatureEnabled**」と入力し、[**値データ**] を「**0**」に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1120d-p109">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** key, create a new **DWORD (32-bit) Value**. The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span></span>
  
<span data-ttu-id="1120d-149">Lync</span><span class="sxs-lookup"><span data-stu-id="1120d-149">Lync</span></span>
  
```
"TutorialFeatureEnabled"=dword:00000000
```

<span data-ttu-id="1120d-150">チュートリアルを有効に戻すには、[**値のデータ**] を「**1**」に設定します。</span><span class="sxs-lookup"><span data-stu-id="1120d-150">You can turn the tutorial back on by setting the **Value data** to **1**.</span></span>
  
## <a name="default-client-behaviors"></a><span data-ttu-id="1120d-151">既定のクライアントの動作</span><span class="sxs-lookup"><span data-stu-id="1120d-151">Default client behaviors</span></span>

<span data-ttu-id="1120d-152">組織に Skype for Business Server と Lync Server の両方が展開されている場合、クライアントのエクスペリエンスはサーバーのバージョンと Skype の UI の設定によって異なります。</span><span class="sxs-lookup"><span data-stu-id="1120d-152">If your organization has both Skype for Business Server and Lync Server deployed, the client experience will differ depending on server versions and the Skype UI setting.</span></span> <span data-ttu-id="1120d-153">以下の表に、サーバー バージョンと UI 設定に基づく最初のクライアント エクスペリエンスを示します。</span><span class="sxs-lookup"><span data-stu-id="1120d-153">The following table shows the initial client experience based on server version and the UI setting:</span></span>
  

|<span data-ttu-id="1120d-154">**サーバー バージョン**</span><span class="sxs-lookup"><span data-stu-id="1120d-154">**Server version**</span></span>|<span data-ttu-id="1120d-155">**EnableSkypeUI 設定**</span><span class="sxs-lookup"><span data-stu-id="1120d-155">**EnableSkypeUI setting**</span></span>|<span data-ttu-id="1120d-156">**クライアント エクスペリエンス**</span><span class="sxs-lookup"><span data-stu-id="1120d-156">**Client experience**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1120d-157">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="1120d-157">Skype for Business Server</span></span> |<span data-ttu-id="1120d-158">既定</span><span class="sxs-lookup"><span data-stu-id="1120d-158">Default</span></span>  <br/> |<span data-ttu-id="1120d-159">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="1120d-159">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="1120d-160">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="1120d-160">Skype for Business Server</span></span>  |<span data-ttu-id="1120d-161">True</span><span class="sxs-lookup"><span data-stu-id="1120d-161">True</span></span>  <br/> |<span data-ttu-id="1120d-162">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="1120d-162">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="1120d-163">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="1120d-163">Skype for Business Server</span></span>  |<span data-ttu-id="1120d-164">False</span><span class="sxs-lookup"><span data-stu-id="1120d-164">False</span></span>  <br/> |<span data-ttu-id="1120d-165">ユーザーが Lync モードに切り替えるように求められた (UI 設定を $true) に変更した場合、ユーザーは後で Skype for Business に切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="1120d-165">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="1120d-166">Lync Server 2010 または Lync Server 2013 (適切な更新プログラムが適用されています)</span><span class="sxs-lookup"><span data-stu-id="1120d-166">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="1120d-167">既定</span><span class="sxs-lookup"><span data-stu-id="1120d-167">Default</span></span>  <br/> |<span data-ttu-id="1120d-168">ユーザーが Lync モードに切り替えるように求められた (UI 設定を $true) に変更した場合、ユーザーは後で Skype for Business に切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="1120d-168">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="1120d-169">Lync Server 2010 または Lync Server 2013 (適切な更新プログラムが適用されています)</span><span class="sxs-lookup"><span data-stu-id="1120d-169">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="1120d-170">True</span><span class="sxs-lookup"><span data-stu-id="1120d-170">True</span></span>  <br/> |<span data-ttu-id="1120d-171">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="1120d-171">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="1120d-172">Lync Server 2010 または Lync Server 2013 (適切な更新プログラムが適用されています)</span><span class="sxs-lookup"><span data-stu-id="1120d-172">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="1120d-173">False</span><span class="sxs-lookup"><span data-stu-id="1120d-173">False</span></span>  <br/> |<span data-ttu-id="1120d-174">ユーザーが Lync モードに切り替えるように求められた (UI 設定を $true) に変更した場合、ユーザーは後で Skype for Business に切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="1120d-174">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="1120d-175">Lync Server 2010 または Lync Server 2013 (パッチなし)</span><span class="sxs-lookup"><span data-stu-id="1120d-175">Lync Server 2010 or Lync Server 2013 (without patches)</span></span>  <br/> |<span data-ttu-id="1120d-176">既定</span><span class="sxs-lookup"><span data-stu-id="1120d-176">Default</span></span>  <br/> |<span data-ttu-id="1120d-177">ユーザーが Lync モードに切り替えるように求められた (ユーザーは後で Skype for Business に切り替えることができません)</span><span class="sxs-lookup"><span data-stu-id="1120d-177">User asked to switch to Lync mode (user cannot switch to Skype for Business later)</span></span>  <br/> |
   
<span data-ttu-id="1120d-178">次の表は、管理者が Skype UI エクスペリエンスの初期設定を変更したときのクライアントエクスペリエンスを示しています。</span><span class="sxs-lookup"><span data-stu-id="1120d-178">The next table shows the client experience when the administrator changes the initial setting for the Skype UI experience:</span></span>
  

|<span data-ttu-id="1120d-179">**サーバー バージョン**</span><span class="sxs-lookup"><span data-stu-id="1120d-179">**Server version**</span></span>|<span data-ttu-id="1120d-180">**EnableSkypeUI 設定**</span><span class="sxs-lookup"><span data-stu-id="1120d-180">**EnableSkypeUI setting**</span></span>|<span data-ttu-id="1120d-181">**クライアント UI = Lync**</span><span class="sxs-lookup"><span data-stu-id="1120d-181">**Client UI = Lync**</span></span>|<span data-ttu-id="1120d-182">**クライアント UI = Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="1120d-182">**Client UI = Skype for Business**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1120d-183">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="1120d-183">Skype for Business Server</span></span> |<span data-ttu-id="1120d-184">True</span><span class="sxs-lookup"><span data-stu-id="1120d-184">True</span></span>  <br/> |<span data-ttu-id="1120d-185">Skype for Business に切り替えるように求められたユーザー</span><span class="sxs-lookup"><span data-stu-id="1120d-185">User asked to switch to Skype for Business</span></span>  <br/> |<span data-ttu-id="1120d-186">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="1120d-186">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="1120d-187">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="1120d-187">Skype for Business Server</span></span> |<span data-ttu-id="1120d-188">False</span><span class="sxs-lookup"><span data-stu-id="1120d-188">False</span></span>  <br/> |<span data-ttu-id="1120d-189">Lync モード</span><span class="sxs-lookup"><span data-stu-id="1120d-189">Lync mode</span></span>  <br/> |<span data-ttu-id="1120d-190">Lync モードへの切り替えを求められたユーザー</span><span class="sxs-lookup"><span data-stu-id="1120d-190">User asked to switch to Lync mode</span></span>  <br/> |
|<span data-ttu-id="1120d-191">Lync Server 2010 または Lync Server 2013 (適切な更新プログラムが適用されています)</span><span class="sxs-lookup"><span data-stu-id="1120d-191">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="1120d-192">True</span><span class="sxs-lookup"><span data-stu-id="1120d-192">True</span></span>  <br/> |<span data-ttu-id="1120d-193">Skype for Business に切り替えるように求められたユーザー</span><span class="sxs-lookup"><span data-stu-id="1120d-193">User asked to switch to Skype for Business</span></span>  <br/> |<span data-ttu-id="1120d-194">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="1120d-194">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="1120d-195">Lync Server 2010 または Lync Server 2013 (適切な更新プログラムが適用されています)</span><span class="sxs-lookup"><span data-stu-id="1120d-195">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="1120d-196">False</span><span class="sxs-lookup"><span data-stu-id="1120d-196">False</span></span>  <br/> |<span data-ttu-id="1120d-197">Lync モード</span><span class="sxs-lookup"><span data-stu-id="1120d-197">Lync mode</span></span>  <br/> |<span data-ttu-id="1120d-198">Lync モードへの切り替えを求められたユーザー</span><span class="sxs-lookup"><span data-stu-id="1120d-198">User asked to switch to Lync mode</span></span>  <br/> |
|<span data-ttu-id="1120d-199">Lync Server 2010 または Lync Server 2013 (パッチなし)</span><span class="sxs-lookup"><span data-stu-id="1120d-199">Lync Server 2010 or Lync Server 2013 (without patches)</span></span>  <br/> |<span data-ttu-id="1120d-200">既定</span><span class="sxs-lookup"><span data-stu-id="1120d-200">Default</span></span>  <br/> |<span data-ttu-id="1120d-201">Lync モード (Skype for Business に切り替えることはできません)</span><span class="sxs-lookup"><span data-stu-id="1120d-201">Lync mode (cannot switch to Skype for Business)</span></span>  <br/> |<span data-ttu-id="1120d-202">Lync モード (Skype for Business に切り替えることはできません)</span><span class="sxs-lookup"><span data-stu-id="1120d-202">Lync mode (cannot switch to Skype for Business)</span></span>  <br/> |
   
<span data-ttu-id="1120d-203">Skype for Business クライアントの構成を管理するために必要な更新プログラムのバージョンは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1120d-203">The patch versions required to manage the configuration of the Skype for Business client are:</span></span>
  
- <span data-ttu-id="1120d-204">Lync Server 2010-Lync Server 2010 用の2015年2月の累積更新プログラム (4.0.7577.710)。</span><span class="sxs-lookup"><span data-stu-id="1120d-204">Lync Server 2010 - February 2015 Cumulative Update (4.0.7577.710) for Lync Server 2010.</span></span> <span data-ttu-id="1120d-205">詳細については、「 [Lync Server 2010 の更新プログラム](https://go.microsoft.com/fwlink/p/?LinkId=532771)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1120d-205">For information, see [Updates for Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)</span></span>
    
- <span data-ttu-id="1120d-206">Lync Server 2013-Lync Server 2013 用に2014年12月の累積更新プログラム (5.0.8308.857)。</span><span class="sxs-lookup"><span data-stu-id="1120d-206">Lync Server 2013 - December 2014 Cumulative Update (5.0.8308.857) for Lync Server 2013.</span></span> <span data-ttu-id="1120d-207">詳細については、「 [Lync Server 2013 の更新プログラム](https://go.microsoft.com/fwlink/p/?LinkId=532772)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1120d-207">For information, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).</span></span>
    
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a><span data-ttu-id="1120d-208">ドメインに参加しているコンピューターのレジストリを変更するグループ ポリシー オブジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="1120d-208">Create a Group Policy Object to modify the registry on a domain joined computer</span></span>

<span data-ttu-id="1120d-209">ユーザーが Skype for Business 2015 クライアントを初めて起動したときに Lync クライアントエクスペリエンスを表示するためのレジストリ更新は、1回だけ実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1120d-209">The registry update to display the Lync client experience the first time a user launches the Skype for Business 2015 client should be done only once.</span></span> <span data-ttu-id="1120d-210">グループ ポリシー オブジェクト (GPO) を使ってレジストリを更新する場合は、値のデータを更新するのではなく、新しい値を作成するオブジェクトを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1120d-210">If you use a Group Policy Object (GPO) to update the registry, you need to define the object to create a new value rather than update the Value data.</span></span> <span data-ttu-id="1120d-211">GPO を適用した場合、新しい値が存在しないと、その値が作成され、値のデータに 0 が設定されます。</span><span class="sxs-lookup"><span data-stu-id="1120d-211">When the GPO is applied, if the new value does not exist, the GPO will create it and set the Value data to 0.</span></span> 
  
<span data-ttu-id="1120d-212">次の手順では、ユーザーが Skype for Business 2015 クライアントを初めて起動したときに Lync クライアントエクスペリエンスが表示されるようにレジストリを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1120d-212">The following procedure describes how to modify the registry so that the Lync client experience is displayed the first time a user launches the Skype for Business 2015 client.</span></span> <span data-ttu-id="1120d-213">この手順は、レジストリを更新して前述のようこそ画面のチュートリアルを無効にするためにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="1120d-213">You can also use this procedure to update the registry to disable the Welcome screen tutorial as described earlier.</span></span>
  
### <a name="to-create-the-gpo"></a><span data-ttu-id="1120d-214">GPO を作成するには</span><span class="sxs-lookup"><span data-stu-id="1120d-214">To create the GPO</span></span>

1. <span data-ttu-id="1120d-215">**グループ ポリシー管理コンソール**を起動します。</span><span class="sxs-lookup"><span data-stu-id="1120d-215">Start the **Group Policy Management console**.</span></span>
    
    <span data-ttu-id="1120d-216">グループ ポリシー管理コンソールの使い方については、「[グループ ポリシー管理コンソール](https://go.microsoft.com/fwlink/?LinkId=532759)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1120d-216">For information about how to use the Group Policy Management Console, see [Group Policy Management Console](https://go.microsoft.com/fwlink/?LinkId=532759).</span></span>
    
2. <span data-ttu-id="1120d-217">[ **グループ ポリシー オブジェクト**] ノードを右クリックして、メニューから [ **新規作成**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="1120d-217">Right-click the **Group Policy Objects** node and select **New** on the menu.</span></span>
    
3. <span data-ttu-id="1120d-218">[ **新しい GPO**] ダイアログ ボックスに、「MakeLyncDefaultUI」などの GPO 名を入力して、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1120d-218">In the **New GPO** dialog, enter a name for the GPO, for example,MakeLyncDefaultUI, and then click **OK**.</span></span>
    
4. <span data-ttu-id="1120d-219">作成した新しい GPO を右クリックして、メニューから [ **編集**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="1120d-219">Right-click on the new GPO you just created and then select **Edit** from the menu.</span></span>
    
5. <span data-ttu-id="1120d-220">[ **グループ ポリシー管理エディター**] で、[ **ユーザーの構成**]、[ **ユーザー設定**]、[ **Windows 設定**] の順に展開して、[ **レジストリ**] ノードを選びます。</span><span class="sxs-lookup"><span data-stu-id="1120d-220">In the **Group Policy Management Editor**, expand **User Configuration**, expand **Preferences**, expand **Windows Settings**, and then select the **Registry** node.</span></span>
    
6. <span data-ttu-id="1120d-221">Right-click on the **Registry** node, and then select **New** > **Registry Item**.</span><span class="sxs-lookup"><span data-stu-id="1120d-221">Right-click on the **Registry** node, and then select **New** > **Registry Item**.</span></span>
    
7. <span data-ttu-id="1120d-222">[ **新しいレジストリのプロパティ**] ダイアログ ボックスで、以下のように項目を更新します。</span><span class="sxs-lookup"><span data-stu-id="1120d-222">On the **New Registry Properties** dialog, update the following:</span></span>
    
   |<span data-ttu-id="1120d-223">**フィールド**</span><span class="sxs-lookup"><span data-stu-id="1120d-223">**Field**</span></span>|<span data-ttu-id="1120d-224">**選択または入力する値**</span><span class="sxs-lookup"><span data-stu-id="1120d-224">**Value to select or enter**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="1120d-225">**操作**</span><span class="sxs-lookup"><span data-stu-id="1120d-225">**Action**</span></span> <br/> |<span data-ttu-id="1120d-226">**作成**</span><span class="sxs-lookup"><span data-stu-id="1120d-226">**Create**</span></span> <br/> |
   |<span data-ttu-id="1120d-227">**ハイブ**</span><span class="sxs-lookup"><span data-stu-id="1120d-227">**Hive**</span></span> <br/> | <span data-ttu-id="1120d-228">HKEY_CURRENT_USER</span><span class="sxs-lookup"><span data-stu-id="1120d-228">HKEY_CURRENT_USER</span></span> <br/> |
   |<span data-ttu-id="1120d-229">**キーのパス**</span><span class="sxs-lookup"><span data-stu-id="1120d-229">**Key Path**</span></span> <br/> |<span data-ttu-id="1120d-230">Software\Microsoft\Office\Lync</span><span class="sxs-lookup"><span data-stu-id="1120d-230">Software\Microsoft\Office\Lync</span></span>  <br/> |
   |<span data-ttu-id="1120d-231">**値の名前**</span><span class="sxs-lookup"><span data-stu-id="1120d-231">**Value name**</span></span> <br/> |<span data-ttu-id="1120d-232">EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="1120d-232">EnableSkypeUI</span></span>  <br/> |
   |<span data-ttu-id="1120d-233">**値の種類**</span><span class="sxs-lookup"><span data-stu-id="1120d-233">**Value type**</span></span> <br/> |<span data-ttu-id="1120d-234">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="1120d-234">REG_BINARY</span></span>  <br/> |
   |<span data-ttu-id="1120d-235">**値のデータ**</span><span class="sxs-lookup"><span data-stu-id="1120d-235">**Value data**</span></span> <br/> |<span data-ttu-id="1120d-236">00000000</span><span class="sxs-lookup"><span data-stu-id="1120d-236">00000000</span></span>  <br/> |
   
8. <span data-ttu-id="1120d-237">[ **OK**] をクリックして変更を保存し、GPO を閉じます。</span><span class="sxs-lookup"><span data-stu-id="1120d-237">Click **OK** to save your changes, and then close the GPO.</span></span>
    
<span data-ttu-id="1120d-238">次に、作成した GPO を、ポリシーを割り当てるユーザー グループ (OU など) にリンクする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1120d-238">Next, you'll need to link the GPO you created to the group of users that you want to assign the policy to, such as an OU.</span></span>
  
### <a name="to-use-the-gpo-to-assign-the-policy"></a><span data-ttu-id="1120d-239">GPO を使用してポリシーを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="1120d-239">To use the GPO to assign the policy</span></span>

1. <span data-ttu-id="1120d-240">グループ ポリシー管理コンソールで、ポリシーを割り当てる OU を右クリックし、[**既存の GPO のリンク**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="1120d-240">In the Group Policy Management Console, right-click on the OU you want to assign the policy to, and then select **Link to an existing GPO**.</span></span>
    
2. <span data-ttu-id="1120d-241">[ **GPO の選択**] ダイアログ ボックスで、作成済みの GPO を選んで、[ **OK**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="1120d-241">On the **Select GPO** dialog, select the GPO you created, and then select **OK**.</span></span>
    
3. <span data-ttu-id="1120d-242">ターゲット ユーザーのコンピューターで、コマンド プロンプトを開いて、以下のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="1120d-242">On the target user's computer, open a command prompt and type the following command:</span></span>
       
```
gpupdate /target:user
```

    
    The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.
    
4. <span data-ttu-id="1120d-243">コマンド プロンプトに、以下のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="1120d-243">At the command prompt, type the following command:</span></span>
    
    <span data-ttu-id="1120d-244">**gpresult /r**</span><span class="sxs-lookup"><span data-stu-id="1120d-244">**gpresult /r**</span></span>
    
    <span data-ttu-id="1120d-245">[適用されたグループ ポリシーオブジェクト] と、作成した GPO 名が下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="1120d-245">You should see "Assigned Group Policy Objects" with the name of the GPO you created displayed below.</span></span>
    
<span data-ttu-id="1120d-p115">また、レジストリを確認して、GPO でユーザーのコンピューターのレジストリが正常に更新されたことを確認する方法もあります。レジストリ エディターを開き、**[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** キーに移動します。GPO によってレジストリが正常に更新された場合、値が 0 の EnableSkypeUI が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1120d-p115">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry. Open Registry Editor and navigate to the **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** key. If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span></span>
  

