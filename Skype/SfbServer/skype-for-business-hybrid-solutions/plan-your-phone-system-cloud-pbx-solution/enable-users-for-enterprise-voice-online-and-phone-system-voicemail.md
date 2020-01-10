---
title: エンタープライズ VoIP オンラインおよび Office 365 ボイスメールの電話システムでユーザーを有効にする
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 28daebcb-c2dc-4338-b2d1-04345ece9c19
description: Skype for Business ユーザー用に Office 365 voice services で電話システムを有効にする方法について説明します。
ms.openlocfilehash: 902d2e1bad76c8275bfc8f4ce7ec7b4243b8572a
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003467"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-in-office-365-voicemail"></a><span data-ttu-id="48dac-103">エンタープライズ VoIP オンラインおよび Office 365 ボイスメールの電話システムでユーザーを有効にする</span><span class="sxs-lookup"><span data-stu-id="48dac-103">Enable users for Enterprise Voice online and Phone System in Office 365 Voicemail</span></span>
 
<span data-ttu-id="48dac-104">Skype for Business ユーザー用に Office 365 voice services で電話システムを有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="48dac-104">Learn how to enable Phone System in Office 365 voice services for your Skype for Business users.</span></span>
  
<span data-ttu-id="48dac-105">Office 365 でオンプレミスの PSTN 接続を使用して電話システムを展開するための最後の手順は、Office 365 およびボイスメールの電話システムでユーザーを有効にすることです。</span><span class="sxs-lookup"><span data-stu-id="48dac-105">The final step in deploying Phone System in Office 365 with on-premises PSTN connectivity is to enable your users for Phone System in Office 365 and voicemail.</span></span> <span data-ttu-id="48dac-106">これらの機能を有効にするには、Office 365 の全体管理者の役割を持つユーザーであり、リモート PowerShell を実行できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="48dac-106">To enable these capabilities, you must be a user with the Office 365 Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="48dac-107">Skype for Business Online でエンタープライズ VoIP がまだ有効でないユーザー アカウントに対して、このトピックの手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="48dac-107">You need to follow the steps in this topic for all user accounts that do not already have Enterprise Voice enabled for Skype for Business Online.</span></span>
  
## <a name="enable-phone-system-in-office-365-voice-services"></a><span data-ttu-id="48dac-108">Office 365 voice services で電話システムを有効にする</span><span class="sxs-lookup"><span data-stu-id="48dac-108">Enable Phone System in Office 365 voice services</span></span>

<span data-ttu-id="48dac-109">Office 365 ボイスとボイスメールで電話システムのユーザーを有効にするには、最初の手順を実行する必要があります。これは、Skype for Business Online Connector がサーバーに展開されているかどうかの確認や、ユーザーがホスト型ボイスメールを有効にしているかどうかを確認する場合などです。</span><span class="sxs-lookup"><span data-stu-id="48dac-109">To enable a user for Phone System in Office 365 Voice and voicemail, you'll need to perform some initial steps, like checking to see if the Skype for Business Online Connector is deployed on your servers and enable your users for hosted voicemail.</span></span>
  
### <a name="to-enable-your-users-for-phone-system-in-office-365-voice-and-voicemail"></a><span data-ttu-id="48dac-110">Office 365 ボイスメールとボイスメールでユーザーの電話システムを有効にするには</span><span class="sxs-lookup"><span data-stu-id="48dac-110">To enable your users for Phone System in Office 365 voice and voicemail</span></span>

1. <span data-ttu-id="48dac-111">作業を始める前に、Skype for Business Online Connector (Windows PowerShell モジュール) がフロントエンドサーバーに展開されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="48dac-111">Before you begin, check that the Skype for Business Online Connector (Windows PowerShell module) is deployed on your Front End Servers.</span></span> <span data-ttu-id="48dac-112">そうでない場合は、[ダウンロードセンター](https://www.microsoft.com/en-us/download/details.aspx?id=39366)からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="48dac-112">If it's not, you can download it from [the download center](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span></span> <span data-ttu-id="48dac-113">このモジュールの使用方法の詳細については、「 [Skype For Business Online の管理用にコンピューターを構成](https://technet.microsoft.com/en-us/library/dn362839%28v=ocs.15%29.aspx)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48dac-113">You can find more information about using this module at [Configuring your computer for Skype for Business Online management](https://technet.microsoft.com/en-us/library/dn362839%28v=ocs.15%29.aspx).</span></span>
    
2. <span data-ttu-id="48dac-114">管理者として、Windows Powershell を起動します。</span><span class="sxs-lookup"><span data-stu-id="48dac-114">Start Windows PowerShell as an administrator.</span></span>
    
3. <span data-ttu-id="48dac-115">次のコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="48dac-115">Type the following and press Enter:</span></span>
    
   ```powershell
   Import-Module skypeonlineconnector
   ```

4. <span data-ttu-id="48dac-116">次のコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="48dac-116">Type the following and press Enter:</span></span>
    
   ```powershell
   $cred = Get-Credential
   ```

    <span data-ttu-id="48dac-117">Enter キーを押すと、[Windows PowerShell 資格情報の要求] ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="48dac-117">After you press Enter, you should see the Windows PowerShell Credential dialog box.</span></span>
    
5. <span data-ttu-id="48dac-118">テナント管理者のユーザー名とパスワードを入力し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="48dac-118">Type your tenant admin username and password, and click **OK**.</span></span>
    
6. <span data-ttu-id="48dac-119">PowerShell ウィンドウで、次のコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="48dac-119">In the PowerShell window, type the following and press Enter:</span></span>
    
   ```powershell
   $Session = New-CsOnlineSession -Credential $cred -Verbose
   ```

7. <span data-ttu-id="48dac-120">次のコマンドレットを入力して、セッションをインポートします。</span><span class="sxs-lookup"><span data-stu-id="48dac-120">Import the session by typing the following cmdlet:</span></span>
    
   ```powershell
   Import-PSSession $Session -AllowClobber
   ```

    <span data-ttu-id="48dac-121">Skype for Business Server で PowerShell を実行している場合は、PowerShell を開いたときにローカルの Skype for Business コマンドレットが既に読み込まれています。</span><span class="sxs-lookup"><span data-stu-id="48dac-121">When running PowerShell on a Skype for Business Server, the local Skype for Business cmdlets are already loaded when you open PowerShell.</span></span> <span data-ttu-id="48dac-122">-AllowClobber パラメーターを指定して、オンラインのコマンドレットでオンプレミスのコマンドレットを同じ名前で上書きできるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="48dac-122">You must specify the -AllowClobber parameter to allow the online cmdlets to overwrite the on-premises cmdlets with the same name.</span></span>
    
8. <span data-ttu-id="48dac-123">Set-CsUser コマンドレットを使用して、次のように、$EnterpriseVoiceEnabled および $HostedVoiceMail プロパティをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="48dac-123">Use the Set-CsUser cmdlet to assign the $EnterpriseVoiceEnabled and $HostedVoiceMail properties to your user as follows:</span></span>
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    <span data-ttu-id="48dac-124">例:</span><span class="sxs-lookup"><span data-stu-id="48dac-124">For example:</span></span>
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > <span data-ttu-id="48dac-125">SIP アドレス、ユーザー プリンシパル名 (UPN)、ドメイン名とユーザー名 (domain\username)、および Active Directory での表示名 ("小林 良太") でユーザーを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="48dac-125">You can also specify a user by their SIP address, User Principal name (UPN), domain name and username (domain\username), and display name in Active Directory ("Bob Kelly").</span></span> 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system-in-office-365"></a><span data-ttu-id="48dac-126">Office 365 で有効になっている電話システムのユーザーのライン URI とダイヤルプランを更新する</span><span class="sxs-lookup"><span data-stu-id="48dac-126">Update the Line URI and dial plan for users enabled for Phone System in Office 365</span></span>

<span data-ttu-id="48dac-127">このセクションでは、Office 365 の電話システムで有効になっているユーザーのために、行の URI とダイヤルプランを更新する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="48dac-127">This section describes how to update the Line URI and dial plan for users enabled for Phone System in Office 365.</span></span> 
  
### <a name="to-update-the-line-uri"></a><span data-ttu-id="48dac-128">回線 URI を更新するには</span><span class="sxs-lookup"><span data-stu-id="48dac-128">To update the Line URI</span></span>

1. <span data-ttu-id="48dac-129">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="48dac-129">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="48dac-130">スタート メニューかデスクトップ ショートカットを使用して、Skype for Business Server のコントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="48dac-130">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="48dac-131">また、ブラウザー ウィンドウを開いて管理 URL を入力し、Skype for Business Server のコントロール パネルを開くこともできます。</span><span class="sxs-lookup"><span data-stu-id="48dac-131">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span> 
  
3. <span data-ttu-id="48dac-132">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="48dac-132">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="48dac-133">[**ユーザーの検索**] ボックスに、有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全体か先頭の部分の文字列を入力して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="48dac-133">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="48dac-134">表で、回線 URI を変更する Skype for Business ユーザー アカウントをクリックします。</span><span class="sxs-lookup"><span data-stu-id="48dac-134">In the table, click the Skype for Business user account that you want to change line URI.</span></span>
    
6. <span data-ttu-id="48dac-p104">[**回線 URI**] をクリックし、正規化された一意の電話番号 (たとえば、tel:+14255550200) を入力して、[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="48dac-p104">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200). Then click **Commit**.</span></span>
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="48dac-137">オンプレミスの Windows Powershell コマンドレットを使用してダイヤル プランを更新する</span><span class="sxs-lookup"><span data-stu-id="48dac-137">Update the dial plan using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="48dac-138">Windows PowerShell と[Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps)コマンドレットを使用して、ユーザーごとのダイヤルプランを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="48dac-138">You can assign per-user dial plans with Windows PowerShell and the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="48dac-139">このコマンドレットは、Skype for Business Server 2015 または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="48dac-139">You can run this cmdlet either from the Skype for Business Server 2015 or from a remote session of Windows PowerShell.</span></span>
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a><span data-ttu-id="48dac-140">単一のユーザーにユーザー単位のダイヤル プランを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="48dac-140">To assign a per-user dial plan to a single user</span></span>

- <span data-ttu-id="48dac-141">[CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps)コマンドレットを使用して、ユーザーごとのダイヤルプラン RedmondDialPlan をユーザー Ken Myer に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="48dac-141">Use the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to assign the per-user dial plan RedmondDialPlan to the user Ken Myer:</span></span>
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a><span data-ttu-id="48dac-142">複数のユーザーにユーザー単位のダイヤル プランを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="48dac-142">To assign a per-user dial plan to multiple users</span></span>

- <span data-ttu-id="48dac-143">次のコマンドは、ユーザーごとのダイヤル プラン RedmondDialPlan を、Redmond 市で働くすべてのユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="48dac-143">The following command assigns the per-user dial plan RedmondDialPlan to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="48dac-144">このコマンドで使用される LdapFilter パラメーターの詳細については、「[ユーザーの取得](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)」コマンドレットのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="48dac-144">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet:</span></span>
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> <span data-ttu-id="48dac-p107">グローバルまたはユーザーのダイヤル プランを、オンライン ユーザーに対して使用することができます。サイトのダイヤル プランはこれらのユーザーに、オンプレミスでホストされオンプレミス サイトに割り当てられているユーザーに対して適用する目的だけで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="48dac-p107">You may use either Global or User dial plans for online users. Site dial plans cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-dial-plan"></a><span data-ttu-id="48dac-147">ユーザー単位のダイヤル プランの割り当てを解除するには</span><span class="sxs-lookup"><span data-stu-id="48dac-147">To unassign a per-user dial plan</span></span>

- <span data-ttu-id="48dac-148">[CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps)コマンドレットを使用して、以前に Ken Myer に割り当てられていたユーザーごとのダイヤルプランの割り当てを解除します。</span><span class="sxs-lookup"><span data-stu-id="48dac-148">Use the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to unassign any per-user dial plan previously assigned to Ken Myer.</span></span> <span data-ttu-id="48dac-149">ユーザーごとのダイヤル プランの割り当てが解除されると、Ken Myer は自動的にグローバル ダイヤル プランまたはこのユーザーの拡張レジストラーまたは PSTN ゲートウェイに割り当てられたサービス スコープのダイヤル プランを使用して管理されるようになります。</span><span class="sxs-lookup"><span data-stu-id="48dac-149">After the per-user dial plan is unassigned, Ken Myer will automatically be managed by using the global dial plan or the service-scope dial plan assigned to his Registrar or PSTN gateway.</span></span> <span data-ttu-id="48dac-150">サービス スコープのダイヤル プランはグローバル ダイヤル プランより優先されます。</span><span class="sxs-lookup"><span data-stu-id="48dac-150">A service scope dial plan takes precedence over the global dial plan:</span></span>
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="48dac-151">オンプレミスの Windows Powershell コマンドレットを使用して音声ルーティング ポリシーを更新するには</span><span class="sxs-lookup"><span data-stu-id="48dac-151">Update the voice routing policies using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="48dac-152">このセクションでは、Office 365 の電話システムを有効にしているユーザーのボイスルーティングポリシーを更新する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="48dac-152">This section describes how to update the voice routing policies for users enabled for Phone System in Office 365.</span></span>
  
<span data-ttu-id="48dac-153">Office 365 の電話システムユーザーが正常にルーティングするためには、それらにボイスルーティングポリシーが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="48dac-153">Phone System in Office 365 users must have a Voice Routing Policy assigned to them for calls to route successfully.</span></span> <span data-ttu-id="48dac-154">これは、呼び出しを適切にルーティングできるように割り当てる音声ポリシーを必要するオンプレミスの企業音声ユーザーとは異なります。</span><span class="sxs-lookup"><span data-stu-id="48dac-154">This differs from on-premises business voice users who require a Voice Policy to be assigned to them to allow calls to route successfully.</span></span> <span data-ttu-id="48dac-155">ボイスルーティングポリシーには、Office 365 ユーザーの電話システムに対して承認された通話とルートを定義する PSTN の使用状況が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="48dac-155">The Voice Routing Policy should contain PSTN usages that define authorized calls and routes for Phone System in Office 365 users.</span></span> <span data-ttu-id="48dac-156">これらの PSTN 使用法は、既存の音声ポリシーから新しい音声ルーティング ポリシーにコピーできます。</span><span class="sxs-lookup"><span data-stu-id="48dac-156">You can copy these PSTN usages from existing Voice Policies to new Voice Routing Policies.</span></span> <span data-ttu-id="48dac-157">詳細については、「[New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48dac-157">For more information, see [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).</span></span>
  
> [!NOTE]
> <span data-ttu-id="48dac-158">Office 365 ユーザーのすべての電話システムには、利用可能な通話機能を定義するビジネス用ボイスと同じオンラインボイスポリシーが割り当てられています。たとえば、[同時呼び出しを許可する] を選びます。</span><span class="sxs-lookup"><span data-stu-id="48dac-158">All Phone System in Office 365 users are assigned the same online Voice Policy named BusinessVoice which defines the calling features allowed; for example, Allow Simultaneous Ring.</span></span> 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a><span data-ttu-id="48dac-159">単一のユーザーにユーザーごとの音声ルーティング ポリシーを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="48dac-159">To assign a per-user voice routing policy to a single user</span></span>

- <span data-ttu-id="48dac-160">[CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps)コマンドレットを使用して、ユーザーごとのボイスルーティングポリシー RedmondVoiceRoutingPolicy をユーザー Ken Myer に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="48dac-160">Use the [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) cmdlet to assign the per-user voice routing policy RedmondVoiceRoutingPolicy to the user Ken Myer:</span></span>
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a><span data-ttu-id="48dac-161">複数のユーザーにユーザーごとの音声ルーティング ポリシーを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="48dac-161">To assign a per-user voice routing policy to multiple users</span></span>

- <span data-ttu-id="48dac-162">次のコマンドは、ユーザー単位の音声ルーティング ポリシー RedmondVoiceRoutingPolicy を Redmond 市で働くすべてのユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="48dac-162">The next command assigns the per-user voice routing policy RedmondVoiceRoutingPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="48dac-163">このコマンドで使用される LdapFilter パラメーターの詳細については、「[ユーザーの取得](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48dac-163">For more information on the LdapFilter parameter used in this command, see [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span></span>
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > <span data-ttu-id="48dac-p111">グローバルまたはユーザーの音声ルーティング ポリシーを、オンライン ユーザーに対して使用することができます。サイトの音声ルーティング ポリシーはこれらのユーザーに、オンプレミスでホストされオンプレミス サイトに割り当てられているユーザーに対して適用する目的だけで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="48dac-p111">You may use either Global or User voice routing policies for online users. Site voice routing policies cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a><span data-ttu-id="48dac-166">ユーザー単位の音声ルーティング ポリシーを割り当て解除するには</span><span class="sxs-lookup"><span data-stu-id="48dac-166">To unassign a per-user voice routing policy</span></span>

- <span data-ttu-id="48dac-167">CsVoiceRoutingPolicy を使用して、以前に Ken Myer に割り当てられているユーザーごとの音声ルーティングポリシーを割り当て解除します。</span><span class="sxs-lookup"><span data-stu-id="48dac-167">Use the Grant-CsVoiceRoutingPolicy to unassign any per-user voice routing policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="48dac-168">ユーザー単位の音声ルーティング ポリシーが割り当て解除された後、Ken Myer は、グローバル音声ルーティング ポリシーによって、自動的に管理されます。</span><span class="sxs-lookup"><span data-stu-id="48dac-168">After the per-user voice routing policy is unassigned, Ken Myer will automatically be managed by using the global voice routing policy.</span></span>
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    <span data-ttu-id="48dac-169">詳細については、「[Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48dac-169">For more information, see [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).</span></span>
    

