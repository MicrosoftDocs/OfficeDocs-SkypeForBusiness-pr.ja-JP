---
title: エンタープライズ Voip オンラインおよび電話システムのボイスメールでユーザーを有効にする
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 28daebcb-c2dc-4338-b2d1-04345ece9c19
description: Skype for Business ユーザーの電話システム音声サービスを有効にする方法について説明します。
ms.openlocfilehash: 522da56969f851280812670692a27d94e4df09a8
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221107"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-voicemail"></a><span data-ttu-id="fe486-103">エンタープライズ Voip オンラインおよび電話システムのボイスメールでユーザーを有効にする</span><span class="sxs-lookup"><span data-stu-id="fe486-103">Enable users for Enterprise Voice online and Phone System Voicemail</span></span>
 
<span data-ttu-id="fe486-104">Skype for Business ユーザーの電話システム音声サービスを有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fe486-104">Learn how to enable Phone System voice services for your Skype for Business users.</span></span>
  
<span data-ttu-id="fe486-105">オンプレミスの PSTN 接続を備えた電話システムを展開するための最後の手順は、ユーザーが電話システムとボイスメールを使用できるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="fe486-105">The final step in deploying Phone System with on-premises PSTN connectivity is to enable your users for Phone System and voicemail.</span></span> <span data-ttu-id="fe486-106">これらの機能を有効にするには、グローバル管理者の役割を持つユーザーである必要があり、リモート PowerShell を実行できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe486-106">To enable these capabilities, you must be a user with the Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="fe486-107">Skype for Business Online でエンタープライズ Voip が有効になっていないすべてのユーザーアカウントについて、このトピックの手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe486-107">You need to follow the steps in this topic for all user accounts that do not already have Enterprise Voice enabled for Skype for Business Online.</span></span>
  
## <a name="enable-phone-system-voice-services"></a><span data-ttu-id="fe486-108">電話システムの音声サービスを有効にする</span><span class="sxs-lookup"><span data-stu-id="fe486-108">Enable Phone System voice services</span></span>

<span data-ttu-id="fe486-109">ユーザーの電話システム音声とボイスメールを有効にするには、最初の手順を実行する必要があります。これには、Skype for Business Online Connector がサーバーに展開されているかどうかを確認し、ユーザーがホストボイスメールを使用できるようにすることがあります。</span><span class="sxs-lookup"><span data-stu-id="fe486-109">To enable a user for Phone System Voice and voicemail, you'll need to perform some initial steps, like checking to see if the Skype for Business Online Connector is deployed on your servers and enable your users for hosted voicemail.</span></span>
  
### <a name="to-enable-your-users-for-phone-system-voice-and-voicemail"></a><span data-ttu-id="fe486-110">ユーザーが電話システムの音声とボイスメールを有効にするには</span><span class="sxs-lookup"><span data-stu-id="fe486-110">To enable your users for Phone System voice and voicemail</span></span>

1. <span data-ttu-id="fe486-111">開始する前に、Skype for Business Online Connector (Windows PowerShell モジュール) がフロントエンドサーバーに展開されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="fe486-111">Before you begin, check that the Skype for Business Online Connector (Windows PowerShell module) is deployed on your Front End Servers.</span></span> <span data-ttu-id="fe486-112">そうでない場合は、[ダウンロードセンター](https://www.microsoft.com/download/details.aspx?id=39366)からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="fe486-112">If it's not, you can download it from [the download center](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> <span data-ttu-id="fe486-113">このモジュールの使用の詳細については[、「Skype For Business Online 管理用のコンピューターの構成](https://technet.microsoft.com/library/dn362839%28v=ocs.15%29.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe486-113">You can find more information about using this module at [Configuring your computer for Skype for Business Online management](https://technet.microsoft.com/library/dn362839%28v=ocs.15%29.aspx).</span></span>
    
2. <span data-ttu-id="fe486-114">管理者として Windows PowerShell を開始します。</span><span class="sxs-lookup"><span data-stu-id="fe486-114">Start Windows PowerShell as an administrator.</span></span>
    
3. <span data-ttu-id="fe486-115">次のように入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="fe486-115">Type the following and press Enter:</span></span>
    
   ```powershell
   Import-Module skypeonlineconnector
   ```

4. <span data-ttu-id="fe486-116">次のように入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="fe486-116">Type the following and press Enter:</span></span>
    
   ```powershell
   $cred = Get-Credential
   ```

    <span data-ttu-id="fe486-117">Enter キーを押すと、[Windows PowerShell 資格情報] ダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fe486-117">After you press Enter, you should see the Windows PowerShell Credential dialog box.</span></span>
    
5. <span data-ttu-id="fe486-118">テナント管理者のユーザー名とパスワードを入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe486-118">Type your tenant admin username and password, and click **OK**.</span></span>
    
6. <span data-ttu-id="fe486-119">PowerShell ウィンドウで、次のように入力して enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="fe486-119">In the PowerShell window, type the following and press Enter:</span></span>
    
   ```powershell
   $Session = New-CsOnlineSession -Credential $cred -Verbose
   ```

7. <span data-ttu-id="fe486-120">次のコマンドレットを入力して、セッションをインポートします。</span><span class="sxs-lookup"><span data-stu-id="fe486-120">Import the session by typing the following cmdlet:</span></span>
    
   ```powershell
   Import-PSSession $Session -AllowClobber
   ```

    <span data-ttu-id="fe486-121">Skype for Business Server で PowerShell を実行している場合は、PowerShell を開いたときにローカルの Skype for Business コマンドレットが既に読み込まれています。</span><span class="sxs-lookup"><span data-stu-id="fe486-121">When running PowerShell on a Skype for Business Server, the local Skype for Business cmdlets are already loaded when you open PowerShell.</span></span> <span data-ttu-id="fe486-122">-AllowClobber パラメーターを指定して、オンラインコマンドレットが同じ名前でオンプレミスのコマンドレットを上書きできるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe486-122">You must specify the -AllowClobber parameter to allow the online cmdlets to overwrite the on-premises cmdlets with the same name.</span></span>
    
8. <span data-ttu-id="fe486-123">次のように、$EnterpriseVoiceEnabled コマンドレットを使用して、ユーザーに $HostedVoiceMail プロパティを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="fe486-123">Use the Set-CsUser cmdlet to assign the $EnterpriseVoiceEnabled and $HostedVoiceMail properties to your user as follows:</span></span>
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    <span data-ttu-id="fe486-124">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="fe486-124">For example:</span></span>
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > <span data-ttu-id="fe486-125">ユーザーの SIP アドレス、ユーザープリンシパル名 (UPN)、ドメイン名とユーザー名 (domain\username)、および Active Directory の表示名 ("Bob 友野") を使用して、ユーザーを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="fe486-125">You can also specify a user by their SIP address, User Principal name (UPN), domain name and username (domain\username), and display name in Active Directory ("Bob Kelly").</span></span> 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system"></a><span data-ttu-id="fe486-126">電話システムが有効なユーザーの回線 URI とダイヤルプランを更新する</span><span class="sxs-lookup"><span data-stu-id="fe486-126">Update the Line URI and dial plan for users enabled for Phone System</span></span>

<span data-ttu-id="fe486-127">このセクションでは、電話システムが有効なユーザーの回線 URI とダイヤルプランを更新する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fe486-127">This section describes how to update the Line URI and dial plan for users enabled for Phone System.</span></span> 
  
### <a name="to-update-the-line-uri"></a><span data-ttu-id="fe486-128">行 URI を更新するには</span><span class="sxs-lookup"><span data-stu-id="fe486-128">To update the Line URI</span></span>

1. <span data-ttu-id="fe486-129">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="fe486-129">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="fe486-130">[スタート] メニューまたはデスクトップショートカットを使用して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="fe486-130">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fe486-131">ブラウザーウィンドウを開き、管理者の URL を入力して Skype for Business Server コントロールパネルを開くこともできます。</span><span class="sxs-lookup"><span data-stu-id="fe486-131">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span> 
  
3. <span data-ttu-id="fe486-132">左側のナビゲーション バーで **[ユーザー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe486-132">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="fe486-133">**[ユーザーの検索]** ボックスに、有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、**[検索]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe486-133">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="fe486-134">表で、回線 URI を変更する Skype for Business ユーザーアカウントをクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe486-134">In the table, click the Skype for Business user account that you want to change line URI.</span></span>
    
6. <span data-ttu-id="fe486-135">[**回線 URI**] をクリックし、正規化された一意の電話番号 (たとえば、tel: + 14255550200) を入力します。</span><span class="sxs-lookup"><span data-stu-id="fe486-135">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200).</span></span> <span data-ttu-id="fe486-136">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe486-136">Then click **Commit**.</span></span>
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="fe486-137">オンプレミスの Windows PowerShell コマンドレットを使用してダイヤルプランを更新する</span><span class="sxs-lookup"><span data-stu-id="fe486-137">Update the dial plan using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="fe486-138">Windows PowerShell と[get-csdialplan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps)コマンドレットを使用して、ユーザーごとのダイヤルプランを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="fe486-138">You can assign per-user dial plans with Windows PowerShell and the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="fe486-139">このコマンドレットは、Skype for Business Server 2015 または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="fe486-139">You can run this cmdlet either from the Skype for Business Server 2015 or from a remote session of Windows PowerShell.</span></span>
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a><span data-ttu-id="fe486-140">ユーザー単位のダイヤルプランを1人のユーザーに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="fe486-140">To assign a per-user dial plan to a single user</span></span>

- <span data-ttu-id="fe486-141">ユーザーごとのダイヤルプラン RedmondDialPlan をユーザー Ken Myer に割り当てるには、 [get-csdialplan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps)コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="fe486-141">Use the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to assign the per-user dial plan RedmondDialPlan to the user Ken Myer:</span></span>
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a><span data-ttu-id="fe486-142">複数のユーザーにユーザー単位のダイヤルプランを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="fe486-142">To assign a per-user dial plan to multiple users</span></span>

- <span data-ttu-id="fe486-143">次のコマンドは、Redmond の市区町村で働くすべてのユーザーに、ユーザーごとのダイヤルプラン RedmondDialPlan を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="fe486-143">The following command assigns the per-user dial plan RedmondDialPlan to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="fe486-144">このコマンドで使用されている LdapFilter パラメーターの詳細については、「 [Get-help user](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)コマンドレットのドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe486-144">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet:</span></span>
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> <span data-ttu-id="fe486-145">オンラインユーザーには、グローバルまたはユーザーダイヤルプランのいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="fe486-145">You may use either Global or User dial plans for online users.</span></span> <span data-ttu-id="fe486-146">サイトダイヤルプランは、社内でホストされ、オンプレミスサイトに割り当てられているユーザーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="fe486-146">Site dial plans cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-dial-plan"></a><span data-ttu-id="fe486-147">ユーザーごとのダイヤルプランの割り当てを解除するには</span><span class="sxs-lookup"><span data-stu-id="fe486-147">To unassign a per-user dial plan</span></span>

- <span data-ttu-id="fe486-148">以前に Ken Myer に割り当てられたユーザーごとのダイヤルプランの割り当てを解除するには、 [get-csdialplan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps)コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="fe486-148">Use the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to unassign any per-user dial plan previously assigned to Ken Myer.</span></span> <span data-ttu-id="fe486-149">ユーザーごとのダイヤルプランの割り当てが解除されると、Ken Myer は、そのレジストラーまたは PSTN ゲートウェイに割り当てられたグローバルダイヤルプランまたはサービススコープのダイヤルプランを使用して、自動的に管理されます。</span><span class="sxs-lookup"><span data-stu-id="fe486-149">After the per-user dial plan is unassigned, Ken Myer will automatically be managed by using the global dial plan or the service-scope dial plan assigned to his Registrar or PSTN gateway.</span></span> <span data-ttu-id="fe486-150">サービススコープのダイヤルプランは、グローバルダイヤルプランより優先されます。</span><span class="sxs-lookup"><span data-stu-id="fe486-150">A service scope dial plan takes precedence over the global dial plan:</span></span>
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="fe486-151">オンプレミスの Windows PowerShell コマンドレットを使用して音声ルーティングポリシーを更新する</span><span class="sxs-lookup"><span data-stu-id="fe486-151">Update the voice routing policies using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="fe486-152">このセクションでは、電話システムが有効なユーザーの音声ルーティングポリシーを更新する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fe486-152">This section describes how to update the voice routing policies for users enabled for Phone System.</span></span>
  
<span data-ttu-id="fe486-153">呼び出しが正常に行われるようにするには、電話システムのユーザーに音声ルーティングポリシーが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe486-153">Phone System users must have a Voice Routing Policy assigned to them for calls to route successfully.</span></span> <span data-ttu-id="fe486-154">これは、通話を正常にルーティングできるようにするために、音声ポリシーが割り当てられているオンプレミスのビジネスボイスユーザーとは異なります。</span><span class="sxs-lookup"><span data-stu-id="fe486-154">This differs from on-premises business voice users who require a Voice Policy to be assigned to them to allow calls to route successfully.</span></span> <span data-ttu-id="fe486-155">音声ルーティングポリシーには、電話システムユーザーの承認済み呼び出しとルートを定義する PSTN 使用法を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe486-155">The Voice Routing Policy should contain PSTN usages that define authorized calls and routes for Phone System users.</span></span> <span data-ttu-id="fe486-156">これらの PSTN 使用法は、既存の音声ポリシーから新しい音声ルーティングポリシーにコピーできます。</span><span class="sxs-lookup"><span data-stu-id="fe486-156">You can copy these PSTN usages from existing Voice Policies to new Voice Routing Policies.</span></span> <span data-ttu-id="fe486-157">詳細については、「 [grant-csvoiceroutingpolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe486-157">For more information, see [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).</span></span>
  
> [!NOTE]
> <span data-ttu-id="fe486-158">すべての電話システムのユーザーには、許可される通話機能を定義する BusinessVoice という名前の同じオンライン音声ポリシーが割り当てられています。たとえば、同時呼び出しを許可します。</span><span class="sxs-lookup"><span data-stu-id="fe486-158">All Phone System users are assigned the same online Voice Policy named BusinessVoice which defines the calling features allowed; for example, Allow Simultaneous Ring.</span></span> 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a><span data-ttu-id="fe486-159">ユーザー単位の音声ルーティングポリシーを単一のユーザーに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="fe486-159">To assign a per-user voice routing policy to a single user</span></span>

- <span data-ttu-id="fe486-160">ユーザーごとの音声ルーティングポリシー RedmondVoiceRoutingPolicy をユーザー Ken Myer に割り当てるには、 [grant-csvoiceroutingpolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps)コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="fe486-160">Use the [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) cmdlet to assign the per-user voice routing policy RedmondVoiceRoutingPolicy to the user Ken Myer:</span></span>
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a><span data-ttu-id="fe486-161">ユーザー単位の音声ルーティングポリシーを複数のユーザーに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="fe486-161">To assign a per-user voice routing policy to multiple users</span></span>

- <span data-ttu-id="fe486-162">次のコマンドは、ユーザーごとの音声ルーティングポリシー RedmondVoiceRoutingPolicy を Redmond の市区町村で働くすべてのユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="fe486-162">The next command assigns the per-user voice routing policy RedmondVoiceRoutingPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="fe486-163">このコマンドで使用する LdapFilter パラメーターの詳細については、「 [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe486-163">For more information on the LdapFilter parameter used in this command, see [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span></span>
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > <span data-ttu-id="fe486-164">オンラインユーザーには、グローバルまたはユーザーの音声ルーティングポリシーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="fe486-164">You may use either Global or User voice routing policies for online users.</span></span> <span data-ttu-id="fe486-165">サイトの音声ルーティングポリシーは、社内でホストされ、オンプレミスサイトに割り当てられているユーザーにのみ適用されるため、使用できません。</span><span class="sxs-lookup"><span data-stu-id="fe486-165">Site voice routing policies cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a><span data-ttu-id="fe486-166">ユーザー単位の音声ルーティングポリシーの割り当てを解除するには</span><span class="sxs-lookup"><span data-stu-id="fe486-166">To unassign a per-user voice routing policy</span></span>

- <span data-ttu-id="fe486-167">Grant-csvoiceroutingpolicy を使用して、以前に Ken Myer に割り当てられたユーザーごとの音声ルーティングポリシーを割り当てを解除します。</span><span class="sxs-lookup"><span data-stu-id="fe486-167">Use the Grant-CsVoiceRoutingPolicy to unassign any per-user voice routing policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="fe486-168">ユーザー単位の音声ルーティングポリシーが割り当て解除されると、Ken Myer はグローバル音声ルーティングポリシーを使用して自動的に管理されます。</span><span class="sxs-lookup"><span data-stu-id="fe486-168">After the per-user voice routing policy is unassigned, Ken Myer will automatically be managed by using the global voice routing policy.</span></span>
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    <span data-ttu-id="fe486-169">詳細については、「 [grant-csvoiceroutingpolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe486-169">For more information, see [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).</span></span>
    

