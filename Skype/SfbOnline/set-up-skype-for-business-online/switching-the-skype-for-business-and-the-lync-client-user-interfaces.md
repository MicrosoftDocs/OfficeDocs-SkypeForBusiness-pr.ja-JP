---
title: "Skype for Business と Lync クライアントのユーザー インターフェイスを切り替える"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: a2394a4c-7522-484c-a047-7b3289742be0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords: None
ms.custom:
- Setup
description: "Skype for Business と Lync クライアントのユーザー インターフェイス PowerShell を使用して、Office 365 の間の切り替え方法を学習します。 "
ms.openlocfilehash: ded1fbf0825fd03645aa2862cc4f51cc10374fbc
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="switching-between-the-skype-for-business-and-the-lync-client-user-interfaces"></a><span data-ttu-id="b0abe-103">Skype for Business と Lync クライアントのユーザー インターフェイスを切り替える</span><span class="sxs-lookup"><span data-stu-id="b0abe-103">Switching between the Skype for Business and the Lync client user interfaces</span></span>

<span data-ttu-id="b0abe-p101">Business Online 組織の skype のビジネス ユーザーの Skype for Business クライアント、Skype を使用するのにか、Skype for Business (Lync) クライアントのユーザー インターフェイスを有効にするのに Office 365 で、リモート PowerShell を使用することができます。既定の設定では、ユーザーは、Skype for Business クライアントのユーザー インターフェイスを使用します。Lync クライアント エクスペリエンスを使用する場合は、このトピックの後半で説明の手順に従って、Lync ユーザー インターフェイスを表示するのには、最初の起動クライアント動作を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="b0abe-p101">For Skype for Business Online organizations, you can use the Remote PowerShell in Office 365 to enable your Skype for Business users to use the Skype for Business client or the Skype for Business (Lync) client user interface. The default setting is for users to use the Skype for Business client user interface. If you'd prefer to use the Lync client experience, you can manage the first launch client behavior to display the Lync user interface by following the steps later in this topic.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b0abe-p102">Lync 2013 のクライアント エクスペリエンスは、Skype for Business 2016 クライアント版オプションです。Lync 2013 クライアントを使用するクライアント環境を構成するしようとすると、前に 16 には、番号に開始しないことを確認するクライアントのバージョンを確認してください。例: 16.x.x.x します。</span><span class="sxs-lookup"><span data-stu-id="b0abe-p102">The Lync 2013 client experience isn't an option for Skype for Business 2016 client versions. Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span> 
  
> [!TIP]
> <span data-ttu-id="b0abe-109">ユーザー インターフェイスを簡単に移動するしてに手動で操作したくない場合は、 [Microsoft ダウンロード センター](https://go.microsoft.com/fwlink/?LinkId=532431)で、PowerShell スクリプトを簡単を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0abe-109">If you want to easily switch the user interface and don't want to do the manual steps, see the [Microsoft Download Center ](https://go.microsoft.com/fwlink/?LinkId=532431) for a PowerShell script to make it easier.</span></span>
  
## <a name="switching-the-skype-for-business-user-interface-for-users"></a><span data-ttu-id="b0abe-110">Skype for Business ユーザーのユーザー インターフェイスの切り替え</span><span class="sxs-lookup"><span data-stu-id="b0abe-110">Switching the Skype for Business user interface for users</span></span>

<span data-ttu-id="b0abe-p103">Skype for Business Online 用の Windows PowerShell モジュールを使用すると、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成することができます。64 ビット版コンピューターでのみサポートされますが、このモジュールは、 [Skype for Business Online 用の Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)では、Microsoft ダウンロード センターからダウンロードできます。その他の情報は、「 [Skype for Business Online 管理コンピューターを構成する](https://go.microsoft.com/fwlink/?LinkId=534539)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0abe-p103">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). For other information, see [Configuring your computer for Skype for Business Online management](https://go.microsoft.com/fwlink/?LinkId=534539).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b0abe-p104">既にカスタム ポリシーが適用されているユーザーに、ユーザー インターフェイスの切り替えの_グローバル_ポリシー設定は適用されません。ユーザー インターフェイスを変更できるようにするには、カスタム ポリシーが適用されている各ユーザーは、次を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0abe-p104">The  _Global_ policy setting for switching the user interface won't be applied to a user that already has a custom policy applied. To be able to change the user interface, you will need to run the following for each user that has a custom policy applied:</span></span>
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

> [!CAUTION]
> <span data-ttu-id="b0abe-116">_ClientPolicyEnableSkypeUI_ポリシーは、ユーザーの既存のカスタム ポリシー設定で置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="b0abe-116">The  _ClientPolicyEnableSkypeUI_ policy will replace the existing custom policy setting for the user.</span></span>
  
<span data-ttu-id="b0abe-117">すべての Skype for Business クライアントの使い方、組織のユーザーを有効にするには、リモート PowerShell を開いてし、次の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="b0abe-117">To enable all of the users in your organization to use the Skype for Business client, open the Remote PowerShell and type the following:</span></span>
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

<span data-ttu-id="b0abe-118">ポリシーを正しくを設定すると表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0abe-118">If you set the policy right, you will see:</span></span>
  
![PowerShell: SkypeUIEnabled](../images/b6b9d2e1-1a37-46df-9757-f81c6054e93b.png)
  
<span data-ttu-id="b0abe-120">Skype for Business (Lync) クライアントを使用する組織のユーザーのすべてを有効にするには、リモート PowerShell を開いてし、次の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="b0abe-120">To enable all of the users in your organization to use the Skype for Business (Lync) client, open the Remote PowerShell and type the following:</span></span> 
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

<span data-ttu-id="b0abe-121">ポリシーを正しくを設定すると表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0abe-121">If you set the policy right, you will see:</span></span>
  
![PowerShell: SkypeUIDisabled](../images/f14ec3ce-4eb8-4a11-826e-6029043ed054.png)
  
<span data-ttu-id="b0abe-123">Skype for Business クライアントを使用する組織内で 1 人のユーザーは、リモート PowerShell を開いてし、次の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="b0abe-123">To allow a single user in your organization to use the Skype for Business client, open the Remote PowerShell and type the following:</span></span>
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

<span data-ttu-id="b0abe-124">ポリシーを正しくを設定すると表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0abe-124">If you set the policy right, you will see:</span></span>
  
![Skype for Business Online - UI を有効にします。](../images/596aef69-41dc-4e1e-b689-2b7009ae58a1.png)
  
<span data-ttu-id="b0abe-126">Skype for Business (Lync) クライアントを使用する組織内で 1 人のユーザーは、リモート PowerShell を開いてし、次の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="b0abe-126">To allow a single user in your organization to use the Skype for Business (Lync) client, open the Remote PowerShell and type the following:</span></span>
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI -Identity <username>
```

<span data-ttu-id="b0abe-127">ポリシーを正しくを設定すると表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0abe-127">If you set the policy right, you will see:</span></span>
  
![Skype for Business Online - UI 無効にします。](../images/61c645e0-67fc-4e03-803c-b7028a47dae3.png)
  
<span data-ttu-id="b0abe-129">Skype for Business クライアントを使用する組織で複数のユーザーは、リモート PowerShell を開いてし、次の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="b0abe-129">To allow multiple users in your organization to use the Skype for Business client, open the Remote PowerShell and type the following:</span></span>
  

```
$users = @("sip:bob@contoso.com","sip:fred@contoso.com") 

$users | Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

<span data-ttu-id="b0abe-130">Skype for Business (Lync) クライアントを使用する組織で複数のユーザーは、リモート PowerShell を開いてし、次の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="b0abe-130">To allow multiple users in your organization to use the Skype for Business (Lync) client, open the Remote PowerShell and type the following:</span></span>
  
```
$users = @("sip:bob@contoso.com","sip:fred@contoso.com")

$users | Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

<span data-ttu-id="b0abe-131">Skype for Business クライアントの使い方、組織内のユーザーのグループは、リモート PowerShell を開いてし、次の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="b0abe-131">To allow a group of users in your organization to use the Skype for Business client, open the Remote PowerShell and type the following:</span></span>
  
```
Get-CsOnlineUser -Filter {Department -eq "Sales"} | Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

<span data-ttu-id="b0abe-132">Skype for Business (Lync) クライアントを使用、組織内のユーザーのグループは、リモート PowerShell を開いてし、次の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="b0abe-132">To allow a group of users in your organization to use the Skype for Business (Lync) client, open the Remote PowerShell and type the following:</span></span>
  
```
Get-CsOnlineUser -Filter {Department -eq "Sales"} | Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

> [!NOTE]
>  <span data-ttu-id="b0abe-p105">ユーザーの名前は、ポリシーを割り当てる必要がありますユーザーのアカウントの名前です。次の形式のいずれかで、ユーザーのアカウント名を入力することができます: > ユーザーの SIP アドレス > ユーザーのユーザー プリンシパル名 (UPN) > ドメイン\\ユーザーのユーザー名 > のユーザーの Active Directory 表示名</span><span class="sxs-lookup"><span data-stu-id="b0abe-p105">The user's name is the name of the user's account that the policy should be assigned to. The user's account name can be entered in one of the following formats:>  SIP address of the user>  User Principal name (UPN) of the user>  Domain\\username of the user>  Active Directory display name of the user</span></span>
  
[<span data-ttu-id="b0abe-135">Windows PowerShell による Lync Online の管理</span><span class="sxs-lookup"><span data-stu-id="b0abe-135">Using Windows PowerShell to manage Lync Online</span></span>](https://go.microsoft.com/fwlink/?LinkID=525453)
  
## <a name="skype-for-business-online-policy-settings"></a><span data-ttu-id="b0abe-136">Skype for Business Online のポリシー設定</span><span class="sxs-lookup"><span data-stu-id="b0abe-136">Skype for Business Online policy settings</span></span>

<span data-ttu-id="b0abe-137">次の表は、ユーザーに適用されるポリシーが最初に、ユーザー エクスペリエンスを示しています。</span><span class="sxs-lookup"><span data-stu-id="b0abe-137">This table shows the user experience when the policy is first applied to users:</span></span>
  
|<span data-ttu-id="b0abe-138">**管理ポリシーの設定**</span><span class="sxs-lookup"><span data-stu-id="b0abe-138">**Admin policy setting**</span></span>|<span data-ttu-id="b0abe-139">**表示されるユーザー インターフェイス**</span><span class="sxs-lookup"><span data-stu-id="b0abe-139">**User interface displayed**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0abe-140">ポリシーが設定されていません。</span><span class="sxs-lookup"><span data-stu-id="b0abe-140">The policy isn't set.</span></span> |<span data-ttu-id="b0abe-141">ユーザーを引き続き for Business クライアントのユーザー インターフェイスの Skype を使用します。</span><span class="sxs-lookup"><span data-stu-id="b0abe-141">The user will continue using the Skype for Business client user interface.</span></span>|
|```Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI```<br/>|<span data-ttu-id="b0abe-142">ユーザーを引き続き for Business クライアントのユーザー インターフェイスの Skype を使用します。</span><span class="sxs-lookup"><span data-stu-id="b0abe-142">The user will continue using the Skype for Business client user interface.</span></span>|
|```Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI```<br/>|<span data-ttu-id="b0abe-p106">ユーザーは、Skype for Business (Lync) クライアントのユーザー インターフェイスに切り替えるように求められます。後で、切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="b0abe-p106">The user will be asked to switch to the Skype for Business (Lync) client user interface. They can switch later.</span></span>|
|```Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>```|<span data-ttu-id="b0abe-145">[ユーザーが使用する、Skype for Business クライアントのユーザー インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="b0abe-145">The user will be using the Skype for Business client user interface.</span></span> |
```Grant-CsClientPolicy-PolicyName ClientPolicyDisableSkypeUI -Identity <username>```|<span data-ttu-id="b0abe-p107">ユーザーは、Skype for Business (Lync) クライアントのユーザー インターフェイスに切り替えるように求められます。管理者が、Skype for Business クライアントのユーザー インターフェイスに切り替えるを将来の設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="b0abe-p107">The user will be asked to switch to the Skype for Business (Lync) client user interface. An admin can change the setting in the future that will switch them to the Skype for Business client user interface.</span></span> |
   
<span data-ttu-id="b0abe-148">次の表は、ポリシーが変更されたときに、ユーザー エクスペリエンスを示しています。</span><span class="sxs-lookup"><span data-stu-id="b0abe-148">This table shows the user experience when the policy is changed:</span></span>
  
|<span data-ttu-id="b0abe-149">**管理ポリシーの設定**</span><span class="sxs-lookup"><span data-stu-id="b0abe-149">**Admin policy setting**</span></span>|<span data-ttu-id="b0abe-150">**Skype for Business (Lync) ユーザー インターフェイス**</span><span class="sxs-lookup"><span data-stu-id="b0abe-150">**Skype for Business (Lync) user interface**</span></span>|<span data-ttu-id="b0abe-151">**Skype for Business ユーザー インターフェイス**</span><span class="sxs-lookup"><span data-stu-id="b0abe-151">**Skype for Business user interface**</span></span>|
|:-----|:-----|:-----|
|```Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI```|<span data-ttu-id="b0abe-152">ユーザーは、Skype for Business クライアントのユーザー インターフェイスに切り替えるように求められます。</span><span class="sxs-lookup"><span data-stu-id="b0abe-152">The user will be asked to switch to the Skype for Business client user interface.</span></span>  <br/> |<span data-ttu-id="b0abe-153">ユーザーは引き続きの Skype for Business クライアントのユーザー インターフェイスを使用します。</span><span class="sxs-lookup"><span data-stu-id="b0abe-153">The user will continue to use the Skype for Business client user interface.</span></span>  <br/> |
|```Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI```|<span data-ttu-id="b0abe-154">ユーザーは引き続きの Skype for Business (Lync) のインターフェイスを使用します。</span><span class="sxs-lookup"><span data-stu-id="b0abe-154">The user will continue to use the Skype for Business (Lync) interface.</span></span>  <br/> |<span data-ttu-id="b0abe-155">ユーザーは、Skype for Business (Lync) クライアントのユーザー インターフェイスに切り替えるように求められます。</span><span class="sxs-lookup"><span data-stu-id="b0abe-155">The user will be asked to switch to the Skype for Business (Lync) client user interface.</span></span>  <br/> |
|<span data-ttu-id="b0abe-156">ポリシーが設定されていません。</span><span class="sxs-lookup"><span data-stu-id="b0abe-156">The policy isn't set.</span></span>  <br/> |<span data-ttu-id="b0abe-p108">ポリシーが設定されていない場合、ユーザーは Skype for Business (Lync) クライアントのユーザー インターフェイスを表示しません。Skype for Business クライアントのユーザー インターフェイス常に使用します。</span><span class="sxs-lookup"><span data-stu-id="b0abe-p108">Users will never see the Skype for Business (Lync) client user interface if the policy is not set. They will always use the Skype for Business client user interface.</span></span>  <br/> |<span data-ttu-id="b0abe-159">ユーザーは引き続きの Skype for Business クライアントのユーザー インターフェイスを使用します。</span><span class="sxs-lookup"><span data-stu-id="b0abe-159">The user will continue to use the Skype for Business client user interface.</span></span>  <br/> |
   
<span data-ttu-id="b0abe-p109">次の表は、すべてのオンライン カスタム ポリシー利用可能なを示します。古いカスタム ポリシー EnableSkypeUI 旗の間の切り替え中に保存することに柔軟に管理者を作成した新しいポリシーがあります。上のコマンドレットを使用してくださいのいずれかを付与、ポリシーをユーザーに以下します。</span><span class="sxs-lookup"><span data-stu-id="b0abe-p109">This table shows all the Online custom policies available. There are new policies created to give admins flexibility in retaining the old custom policy while switching between the EnableSkypeUI flags. Please use the cmdlets from above to grant one of the below policies to your users.</span></span>
  
|<span data-ttu-id="b0abe-163">**ポリシーの名前**</span><span class="sxs-lookup"><span data-stu-id="b0abe-163">**Policy name**</span></span>|<span data-ttu-id="b0abe-164">**EnableSkypeUI**</span><span class="sxs-lookup"><span data-stu-id="b0abe-164">**EnableSkypeUI**</span></span>|
|:-----|:-----|
```ClientPolicyDefaultPhoto```||
```ClientPolicyDefaultPhotoDisableSkypeUI``` |<span data-ttu-id="b0abe-165">False</span><span class="sxs-lookup"><span data-stu-id="b0abe-165">False</span></span>|
```ClientPolicyNoIMURL```||
```ClientPolicyNoIMURLDisableSkypeUI``` |<span data-ttu-id="b0abe-166">False</span><span class="sxs-lookup"><span data-stu-id="b0abe-166">False</span></span>|
```ClientPolicyNoIMURLPhoto```||
```ClientPolicyNoIMURLPhotoDisableSkypeUI``` |<span data-ttu-id="b0abe-167">False</span><span class="sxs-lookup"><span data-stu-id="b0abe-167">False</span></span>|
```ClientPolicyNoSaveIMNoArchivingI```||
```ClientPolicyNoSaveIMNoArchivingDisableSkypeUI``` |<span data-ttu-id="b0abe-168">False</span><span class="sxs-lookup"><span data-stu-id="b0abe-168">False</span></span>|
```ClientPolicyNoSaveIMNoArchivingNoIMURL```||
```ClientPolicyNoSaveIMNoArchivingNoIMURLDisableSkypeUI``` |<span data-ttu-id="b0abe-169">False</span><span class="sxs-lookup"><span data-stu-id="b0abe-169">False</span></span>|
```ClientPolicyNoSaveIMNoArchivingNoIMURLPhoto``` ||
```ClientPolicyNoSaveIMNoArchivingNoIMURLPhotoDisableSkypeUI```|<span data-ttu-id="b0abe-170">False</span><span class="sxs-lookup"><span data-stu-id="b0abe-170">False</span></span>|
```ClientPolicyNoSaveIMNoArchivingPhoto```||
```ClientPolicyNoSaveIMNoArchivingPhotoDisableSkypeUI``` |<span data-ttu-id="b0abe-171">False</span><span class="sxs-lookup"><span data-stu-id="b0abe-171">False</span></span>|

   
<span data-ttu-id="b0abe-172">Windows PowerShell で開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0abe-172">To get started with Windows PowerShell, see these topics:</span></span>
  
- [<span data-ttu-id="b0abe-173">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="b0abe-173">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- [<span data-ttu-id="b0abe-174">Windows PowerShell で Office 365 を管理する最善の方法</span><span class="sxs-lookup"><span data-stu-id="b0abe-174">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
## <a name="first-launch-client-behaviors"></a><span data-ttu-id="b0abe-175">最初の起動クライアントの動作</span><span class="sxs-lookup"><span data-stu-id="b0abe-175">First launch client behaviors</span></span>

<span data-ttu-id="b0abe-p110">既定では、ユーザーを初めて、Skype for Business を起動すると、常に表示されますが Skype for Business ユーザー インターフェイス - Lync クライアントの操作環境のクライアントのポリシーを設定して、Lync のクライアント エクスペリエンスを選択した場合でも (`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`) に従って先に。分後に、いくつか、ユーザーは、[ように求められます Lync モードに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="b0abe-p110">By default, when users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the client policy to the Lync client experience (`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`) as described previously. After several minutes, users will then be asked to switch to Lync mode.</span></span>
  
<span data-ttu-id="b0abe-178">ユーザーを初めて Skype for Business クライアントを起動すると、Lync ユーザー インターフェイスを表示する場合は、クライアントが更新される後に初めて開始する前にこれらの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="b0abe-178">If you want to display the Lync user interface when users launch the Skype for Business client for the first time, follow these steps before the client is started for the first time after being updated:</span></span>
  
1. <span data-ttu-id="b0abe-179">このトピックの前の手順を実行し、クライアントのポリシーが Skype for Business ユーザー インターフェイスを無効に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b0abe-179">Follow the steps earlier in this topic and confirm that the client policy is set to disable the Skype for Business user interface.</span></span>
    
2. <span data-ttu-id="b0abe-p111">ユーザーのコンピューター システムのレジストリを更新します。これは、ユーザーが初めてが Skype for Business クライアントを起動して、1 回だけ行います前に行う必要があります。ドメインのレジストリを更新するグループ ポリシー オブジェクトを作成する方法については、結合されたコンピューターでは、トピックの後半の「を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0abe-p111">Update the system registry on the user's computer. You should do this before the first time users launch the Skype for Business client, and you should do this only once. For information about how to create a Group Policy Object to update the registry on a domain joined computer, see the section later in the topic.</span></span>
    
    <span data-ttu-id="b0abe-183">**[HKEY_CURRENT_USER\\ソフトウェア\\Microsoft\\Office\\Lync]**キーは、新しい**バイナリ**値を作成します。</span><span class="sxs-lookup"><span data-stu-id="b0abe-183">In the **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]** key, create a new **Binary** value.</span></span>
    
    <span data-ttu-id="b0abe-184">[**値の名前**でなければ**EnableSkypeUI**と**00 00 00**00**値のデータ**を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0abe-184">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span></span>
    
    <span data-ttu-id="b0abe-185">キーは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="b0abe-185">The key should look like the following:</span></span>
    
    <span data-ttu-id="b0abe-186">[HKEY_CURRENT_USER\\ソフトウェア\\Microsoft\\Office\\Lync]</span><span class="sxs-lookup"><span data-stu-id="b0abe-186">[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]</span></span>
    
    <span data-ttu-id="b0abe-187">"CanSharePptInCollab"= dword:00000001</span><span class="sxs-lookup"><span data-stu-id="b0abe-187">"CanSharePptInCollab"=dword:00000001</span></span>
    
    <span data-ttu-id="b0abe-188">"CanShareOneNoteInCollab"= dword:00000001</span><span class="sxs-lookup"><span data-stu-id="b0abe-188">"CanShareOneNoteInCollab"=dword:00000001</span></span>
    
    <span data-ttu-id="b0abe-189">"CanAppShareInCollab"= dword:00000001</span><span class="sxs-lookup"><span data-stu-id="b0abe-189">"CanAppShareInCollab"=dword:00000001</span></span>
    
    <span data-ttu-id="b0abe-190">"EnableSkypeUI"= 16 進数: 00、00, 00, 00</span><span class="sxs-lookup"><span data-stu-id="b0abe-190">"EnableSkypeUI"=hex:00,00,00,00</span></span>
    
<span data-ttu-id="b0abe-191">ユーザーを初めて Skype for Business クライアントを起動すると、Lync ユーザー インターフェイスは表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0abe-191">The Lync user interface will now be displayed when users launch the Skype for Business client for the first time.</span></span>
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a><span data-ttu-id="b0abe-192">[ようこそ] 画面のチュートリアルの表示を制御します。</span><span class="sxs-lookup"><span data-stu-id="b0abe-192">Control the display of the Welcome screen tutorial</span></span>

<span data-ttu-id="b0abe-p112">ユーザーが Skype for Business クライアントを開いたときの既定の動作が、*ほとんどのユーザーが求める 7 つのクイック ヒント*を含む [ようこそ] 画面を表示します。[ようこそ] 画面の表示をオフにするが、ユーザーは、クライアント コンピューターで次のレジストリ値を追加してチュートリアルにアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="b0abe-p112">When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes *7 Quick tips most people ask for*. You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span></span>
  
<span data-ttu-id="b0abe-p113">**[HKEY_CURRENT_USER\\ソフトウェア\\Microsoft\\Office\\15.0\\Lync]**キーは、「新しい**DWORD (32 ビット) の値**を作成します。**値の名前** **IsBasicTutorialSeenByUser**] は、**値のデータ**を**1**に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0abe-p113">In the **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync]** key, create a new **DWORD (32-bit) Value**. The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span></span>
  
<span data-ttu-id="b0abe-197">キーは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="b0abe-197">The key should look like the following:</span></span>
  
```
"IsBasicTutorialSeenByUser"=dword:00000001
```

### <a name="turn-off-the-client-tutorial"></a><span data-ttu-id="b0abe-198">クライアントのチュートリアルをオフにします。</span><span class="sxs-lookup"><span data-stu-id="b0abe-198">Turn off the client tutorial</span></span>

<span data-ttu-id="b0abe-199">チュートリアルにアクセスできるユーザーしたくない場合は、クライアントのチュートリアルでは、次のレジストリ値をオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="b0abe-199">If you do not want your users to be able to access the tutorial, you can turn off the client tutorial with the following Registry value:</span></span>
  
<span data-ttu-id="b0abe-p114">**[HKEY_CURRENT_USER\\ソフトウェア\\Microsoft\\Office\\15.0\\Lync]**キーは、「新しい**DWORD (32 ビット) の値**を作成します。**値の名前** **TutorialFeatureEnabled**] は、**値のデータ**を**0**に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0abe-p114">In the **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync]** key, create a new **DWORD (32-bit) Value**. The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span></span>
  
```
"TutorialFeatureEnabled"=dword:00000000
```

<span data-ttu-id="b0abe-202">**値のデータ**を**1**に設定して後でチュートリアルを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="b0abe-202">You can turn the tutorial back on by setting the **Value data** to **1**.</span></span>
  
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a><span data-ttu-id="b0abe-203">ドメインの結合されるコンピューターでレジストリを変更するグループ ポリシー オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="b0abe-203">Create a Group Policy Object to modify the registry on a domain joined computer</span></span>

<span data-ttu-id="b0abe-p115">1 回だけ表示 Lync クライアント エクスペリエンスの初めてのユーザーが Skype for Business クライアントを起動するレジストリの更新を行う必要があります。レジストリを更新するグループ ポリシー オブジェクト (GPO) を使用している場合は、値のデータを更新するのではなく、新しい値を作成するオブジェクトを定義する必要があります。GPO を適用すると、新しい値が存在しない場合は、GPO を作成し、値のデータを 0 に設定します。</span><span class="sxs-lookup"><span data-stu-id="b0abe-p115">The registry update to display the Lync client experience the first time a user launches the Skype for Business client should be done only once. If you use a Group Policy Object (GPO) to update the registry, you need to define the object to create a new value rather than update the Value data. When the GPO is applied, if the new value does not exist, the GPO will create it and set the Value data to 0.</span></span>
  
<span data-ttu-id="b0abe-p116">次の手順では、Lync クライアント エクスペリエンスのユーザーが Skype for Business を起動 2 回目が表示されるように、レジストリを変更する方法について説明します。前述のように [ようこそ] 画面のチュートリアルを無効にするのにレジストリを更新するのに、この手順を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="b0abe-p116">The following procedure describes how to modify the registry so that the Lync client experience is displayed the first time a user launches the Skype for Business. You can also use this procedure to update the registry to disable the Welcome screen tutorial as described earlier.</span></span>
  
 <span data-ttu-id="b0abe-209">**GPO を作成するには**</span><span class="sxs-lookup"><span data-stu-id="b0abe-209">**To create the GPO**</span></span>
  
1. <span data-ttu-id="b0abe-210">**グループ ポリシーの管理コンソール**を起動します。</span><span class="sxs-lookup"><span data-stu-id="b0abe-210">Start the **Group Policy Management console**.</span></span>
    
    <span data-ttu-id="b0abe-211">グループ ポリシーの管理コンソールを使用する方法については、[グループ ポリシー管理コンソール](https://go.microsoft.com/fwlink/?LinkId=532759)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0abe-211">For information about how to use the Group Policy Management Console, see [Group Policy Management Console](https://go.microsoft.com/fwlink/?LinkId=532759).</span></span>
    
2. <span data-ttu-id="b0abe-212">**グループ ポリシー オブジェクト**ノードを右クリックし、メニューの [**新規作成**します。</span><span class="sxs-lookup"><span data-stu-id="b0abe-212">Right-click the **Group Policy Objects** node and select **New** on the menu.</span></span>
    
3. <span data-ttu-id="b0abe-213">**新しい GPO** ] ダイアログ ボックスで、たとえば、MakeLyncDefaultUI、GPO の名前を入力し、し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0abe-213">In the **New GPO** dialog, enter a name for the GPO, for example,MakeLyncDefaultUI, and then click **OK**.</span></span>
    
4. <span data-ttu-id="b0abe-214">作成した新しい GPO で右クリックし、[メニューから [**編集**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b0abe-214">Right-click on the new GPO you just created and then select **Edit** from the menu.</span></span>
    
5. <span data-ttu-id="b0abe-215">**グループ ポリシー管理エディター**] で**ユーザー**の構成、**環境設定**を展開する**Windows の設定**] を展開し、**レジストリ**] ノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="b0abe-215">In the **Group Policy Management Editor**, expand **User Configuration**, expand **Preferences**, expand **Windows Settings**, and then select the **Registry** node.</span></span>
    
6. <span data-ttu-id="b0abe-216">**レジストリ**] ノードを右クリックし、[**新規作成**] を選びます > **レジストリ アイテム**。</span><span class="sxs-lookup"><span data-stu-id="b0abe-216">Right-click on the **Registry** node, and then select **New** > **Registry Item**.</span></span>
    
7. <span data-ttu-id="b0abe-217">[**新しいレジストリのプロパティ**] ダイアログ ボックスで、次のように更新します。</span><span class="sxs-lookup"><span data-stu-id="b0abe-217">On the **New Registry Properties** dialog, update the following:</span></span>
    
|<span data-ttu-id="b0abe-218">**フィールド**</span><span class="sxs-lookup"><span data-stu-id="b0abe-218">**Field**</span></span>|<span data-ttu-id="b0abe-219">**値を入力するか選びます**</span><span class="sxs-lookup"><span data-stu-id="b0abe-219">**Value to select or enter**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0abe-220">**アクション**</span><span class="sxs-lookup"><span data-stu-id="b0abe-220">**Action**</span></span> <br/> |<span data-ttu-id="b0abe-221">**作成します。**</span><span class="sxs-lookup"><span data-stu-id="b0abe-221">**Create**</span></span> <br/> |
|<span data-ttu-id="b0abe-222">**ハイブ**</span><span class="sxs-lookup"><span data-stu-id="b0abe-222">**Hive**</span></span> <br/> | <span data-ttu-id="b0abe-223">HKEY_CURRENT_USER</span><span class="sxs-lookup"><span data-stu-id="b0abe-223">HKEY_CURRENT_USER</span></span> <br/> |
|<span data-ttu-id="b0abe-224">**キーのパス**</span><span class="sxs-lookup"><span data-stu-id="b0abe-224">**Key Path**</span></span> <br/> |<span data-ttu-id="b0abe-225">ソフトウェア\\Microsoft\\Office\\Lync</span><span class="sxs-lookup"><span data-stu-id="b0abe-225">Software\\Microsoft\\Office\\Lync</span></span>  <br/> |
|<span data-ttu-id="b0abe-226">**値の名前**</span><span class="sxs-lookup"><span data-stu-id="b0abe-226">**Value name**</span></span> <br/> |<span data-ttu-id="b0abe-227">EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="b0abe-227">EnableSkypeUI</span></span>  <br/> |
|<span data-ttu-id="b0abe-228">**値の種類**</span><span class="sxs-lookup"><span data-stu-id="b0abe-228">**Value type**</span></span> <br/> |<span data-ttu-id="b0abe-229">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="b0abe-229">REG_BINARY</span></span>  <br/> |
|<span data-ttu-id="b0abe-230">**値のデータ**</span><span class="sxs-lookup"><span data-stu-id="b0abe-230">**Value data**</span></span> <br/> |<span data-ttu-id="b0abe-231">00000000</span><span class="sxs-lookup"><span data-stu-id="b0abe-231">00000000</span></span>  <br/> |
   
<span data-ttu-id="b0abe-232">変更内容を保存して**[OK** ] をクリックし、GPO を閉じます。</span><span class="sxs-lookup"><span data-stu-id="b0abe-232">Click **OK** to save your changes, and then close the GPO.</span></span>
    
<span data-ttu-id="b0abe-233">次に、OU など、ポリシーを割り当てるユーザーのグループを作成する GPO をリンクする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0abe-233">Next, you'll need to link the GPO you created to the group of users that you want to assign the policy to, such as an OU.</span></span>
  
 <span data-ttu-id="b0abe-234">**GPO を使用して、ポリシーを割り当てる**</span><span class="sxs-lookup"><span data-stu-id="b0abe-234">**To use the GPO to assign the policy**</span></span>
  
1. <span data-ttu-id="b0abe-235">グループ ポリシーの管理コンソールでは、ポリシーを割り当てる OU で右クリックし、[**既存の GPO へのリンク**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b0abe-235">In the Group Policy Management Console, right-click on the OU you want to assign the policy to, and then select **Link to an existing GPO**.</span></span>
    
2. <span data-ttu-id="b0abe-236">[ **GPO の選択**] ダイアログ ボックスで、作成した GPO を選択し、[、[ **ok]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0abe-236">On the **Select GPO** dialog, select the GPO you created, and then select **OK**.</span></span>
    
3. <span data-ttu-id="b0abe-237">対象ユーザーのコンピューターでは、コマンド プロンプトを開きます。 し、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="b0abe-237">On the target user's computer, open a command prompt and type the following command:</span></span>
    
    <span data-ttu-id="b0abe-238">**gpupdate/target:user**</span><span class="sxs-lookup"><span data-stu-id="b0abe-238">**gpupdate /target:user**</span></span>
    
    <span data-ttu-id="b0abe-p117">メッセージの「更新ポリシー...」GPO が適用されて表示されます。完了すると、「ユーザー ポリシーの更新プログラムが正常に完了しました」メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0abe-p117">The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.</span></span>
    
4. <span data-ttu-id="b0abe-241">コマンド プロンプトで、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="b0abe-241">At the command prompt, type the following command:</span></span>
    
    <span data-ttu-id="b0abe-242">**gpresult/r**</span><span class="sxs-lookup"><span data-stu-id="b0abe-242">**gpresult /r**</span></span>
    
    <span data-ttu-id="b0abe-243">作成した GPO の名前での「グループ ポリシー オブジェクトの割り当てられている」の下に表示するが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0abe-243">You should see "Assigned Group Policy Objects" with the name of the GPO you created displayed below.</span></span>
    
<span data-ttu-id="b0abe-p118">GPO 正常に更新したユーザーのコンピューター上のレジストリでレジストリを調べることを確認することもできます。レジストリ エディターを開きに移動、 **[HKEY_CURRENT_USER\\ソフトウェア\\Microsoft\\Office\\Lync]**キーです。GPO レジストリを正常に更新する場合は、0 の値を含む EnableSkypeUI をという名前の値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0abe-p118">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry. Open Registry Editor and navigate to the **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]** key. If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="b0abe-247">関連トピック</span><span class="sxs-lookup"><span data-stu-id="b0abe-247">Related topics</span></span>
[<span data-ttu-id="b0abe-248">Skype for Business Online をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="b0abe-248">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="b0abe-249">ビジネス ユーザー向けの Skype Skype の連絡先を追加できるようにします。</span><span class="sxs-lookup"><span data-stu-id="b0abe-249">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
