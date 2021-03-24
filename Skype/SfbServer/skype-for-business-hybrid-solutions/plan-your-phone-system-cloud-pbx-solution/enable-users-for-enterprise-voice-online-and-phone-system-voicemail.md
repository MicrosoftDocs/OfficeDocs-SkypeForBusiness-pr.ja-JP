---
title: エンタープライズ VoIP オンラインおよび電話システムのボイスメールのユーザーを有効にする
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
description: Skype for Business ユーザーに対して電話システム音声サービスを有効にする方法について学習します。
ms.openlocfilehash: f1c59505073a7113407f28b7ebbe3a323724782e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098573"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-voicemail"></a><span data-ttu-id="94402-103">エンタープライズ VoIP オンラインおよび電話システムのボイスメールのユーザーを有効にする</span><span class="sxs-lookup"><span data-stu-id="94402-103">Enable users for Enterprise Voice online and Phone System Voicemail</span></span>
 
> [!Important]
> <span data-ttu-id="94402-104">Skype for Business Online は 2021 年 7 月 31 日に廃止され、その後サービスにアクセスできなくなりました。</span><span class="sxs-lookup"><span data-stu-id="94402-104">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="94402-105">さらに、Skype for Business Server または Cloud Connector Edition と Skype for Business Online を介したオンプレミス環境間の PSTN 接続はサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="94402-105">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="94402-106">直接ルーティングを使用してオンプレミスのテレフォニー ネットワークを Teams に接続する方法 [について説明します](/MicrosoftTeams/direct-routing-landing-page)。</span><span class="sxs-lookup"><span data-stu-id="94402-106">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="94402-107">Skype for Business ユーザーに対して電話システム音声サービスを有効にする方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="94402-107">Learn how to enable Phone System voice services for your Skype for Business users.</span></span>
  
<span data-ttu-id="94402-108">オンプレミスの PSTN 接続を使用して電話システムを展開する最後の手順は、ユーザーが電話システムとボイスメールを有効にするための手順です。</span><span class="sxs-lookup"><span data-stu-id="94402-108">The final step in deploying Phone System with on-premises PSTN connectivity is to enable your users for Phone System and voicemail.</span></span> <span data-ttu-id="94402-109">これらの機能を有効にするには、グローバル管理者の役割を持つユーザーであり、リモート PowerShell を実行できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="94402-109">To enable these capabilities, you must be a user with the Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="94402-110">Skype for Business Online で有効になっていないすべてのユーザー アカウントについて、このトピックエンタープライズ VoIPする必要があります。</span><span class="sxs-lookup"><span data-stu-id="94402-110">You need to follow the steps in this topic for all user accounts that do not already have Enterprise Voice enabled for Skype for Business Online.</span></span>
  
## <a name="enable-phone-system-voice-services"></a><span data-ttu-id="94402-111">電話システム音声サービスを有効にする</span><span class="sxs-lookup"><span data-stu-id="94402-111">Enable Phone System voice services</span></span>

<span data-ttu-id="94402-112">ユーザーが電話システムボイスメールとボイスメールを有効にするには、Skype for Business Online Connector がサーバーに展開され、ユーザーがホストされたボイスメールを有効にするための確認など、いくつかの初期手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94402-112">To enable a user for Phone System Voice and voicemail, you'll need to perform some initial steps, like checking to see if the Skype for Business Online Connector is deployed on your servers and enable your users for hosted voicemail.</span></span>
  
### <a name="to-enable-your-users-for-phone-system-voice-and-voicemail"></a><span data-ttu-id="94402-113">ユーザーが電話システムの音声とボイスメールを有効にするには</span><span class="sxs-lookup"><span data-stu-id="94402-113">To enable your users for Phone System voice and voicemail</span></span>

> [!NOTE]
> <span data-ttu-id="94402-114">Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールの一部です。</span><span class="sxs-lookup"><span data-stu-id="94402-114">Skype for Business Online Connector is currently part of latest Teams PowerShell Module.</span></span>
> <span data-ttu-id="94402-115">最新の [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)パブリック リリースを使用している場合は、Skype for Business Online Connector をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="94402-115">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

1. <span data-ttu-id="94402-116">開始する前に、Teams PowerShell モジュールがフロントエンド サーバーにインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="94402-116">Before you begin, check that the Teams PowerShell module is installed on your Front End Servers.</span></span> <span data-ttu-id="94402-117">インストールされていない場合は、「Teams PowerShell モジュールのインストール」の手順 [に従ってインストールしてください](/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="94402-117">If it's not, please  install using the instructions in [Teams PowerShell Module Installation](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="94402-118">管理者Windows PowerShell開始します。</span><span class="sxs-lookup"><span data-stu-id="94402-118">Start Windows PowerShell as an administrator.</span></span>
    
3. <span data-ttu-id="94402-119">次を入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="94402-119">Type the following and press Enter:</span></span>
    
 ```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

  
4. <span data-ttu-id="94402-120">次のように、Set-CsUserコマンドレットを使用して、$EnterpriseVoiceEnabledプロパティ$HostedVoiceMailをユーザーに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="94402-120">Use the Set-CsUser cmdlet to assign the $EnterpriseVoiceEnabled and $HostedVoiceMail properties to your user as follows:</span></span>
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    <span data-ttu-id="94402-121">例:</span><span class="sxs-lookup"><span data-stu-id="94402-121">For example:</span></span>
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > <span data-ttu-id="94402-122">また、ユーザーを SIP アドレス、ユーザー プリンシパル名 (UPN)、ドメイン名とユーザー名 (domain\username)、および Active Directory の表示名 ("Bob Kelly") で指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="94402-122">You can also specify a user by their SIP address, User Principal name (UPN), domain name and username (domain\username), and display name in Active Directory ("Bob Kelly").</span></span> 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system"></a><span data-ttu-id="94402-123">電話システムで有効になっているユーザーの回線 URI とダイヤル プランを更新する</span><span class="sxs-lookup"><span data-stu-id="94402-123">Update the Line URI and dial plan for users enabled for Phone System</span></span>

<span data-ttu-id="94402-124">このセクションでは、電話システムで有効になっているユーザーの回線 URI とダイヤル プランを更新する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="94402-124">This section describes how to update the Line URI and dial plan for users enabled for Phone System.</span></span> 
  
### <a name="to-update-the-line-uri"></a><span data-ttu-id="94402-125">Line URI を更新するには</span><span class="sxs-lookup"><span data-stu-id="94402-125">To update the Line URI</span></span>

1. <span data-ttu-id="94402-126">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="94402-126">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="94402-127">[スタート] メニューまたはデスクトップ ショートカットを使用して、Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="94402-127">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="94402-128">ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開く方法もできます。</span><span class="sxs-lookup"><span data-stu-id="94402-128">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span> 
  
3. <span data-ttu-id="94402-129">左側のナビゲーション バーで **[ユーザー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94402-129">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="94402-130">**[ユーザーの検索]** ボックスに、有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、**[検索]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94402-130">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="94402-131">表で、回線 URI を変更する Skype for Business ユーザー アカウントをクリックします。</span><span class="sxs-lookup"><span data-stu-id="94402-131">In the table, click the Skype for Business user account that you want to change line URI.</span></span>
    
6. <span data-ttu-id="94402-132">[ **回線 URI]** をクリックし、正規化された一意の電話番号 (tel:+14255550200 など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="94402-132">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200).</span></span> <span data-ttu-id="94402-133">次に、[ **コミット] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="94402-133">Then click **Commit**.</span></span>
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="94402-134">オンプレミスのコマンドレットを使用してダイヤル プランWindows PowerShellする</span><span class="sxs-lookup"><span data-stu-id="94402-134">Update the dial plan using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="94402-135">ユーザー単位のダイヤル プランは、Windows PowerShell [Grant-CsDialPlan コマンドレットを使用して割り当](/powershell/module/skype/grant-csdialplan?view=skype-ps) てできます。</span><span class="sxs-lookup"><span data-stu-id="94402-135">You can assign per-user dial plans with Windows PowerShell and the [Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="94402-136">このコマンドレットは、Skype for Business Server 2015 から実行するか、Skype for Business Server 2015 のリモート セッションから実行Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="94402-136">You can run this cmdlet either from the Skype for Business Server 2015 or from a remote session of Windows PowerShell.</span></span>
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a><span data-ttu-id="94402-137">ユーザー単位のダイヤル プランを 1 人のユーザーに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="94402-137">To assign a per-user dial plan to a single user</span></span>

- <span data-ttu-id="94402-138">[Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps)コマンドレットを使用して、ユーザーごとのダイヤル プラン RedmondDialPlan をユーザー Ken Myer に割り当てる。</span><span class="sxs-lookup"><span data-stu-id="94402-138">Use the [Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to assign the per-user dial plan RedmondDialPlan to the user Ken Myer:</span></span>
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a><span data-ttu-id="94402-139">複数のユーザーにユーザーごとのダイヤル プランを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="94402-139">To assign a per-user dial plan to multiple users</span></span>

- <span data-ttu-id="94402-140">次のコマンドは、ユーザーごとのダイヤル プラン RedmondDialPlan を、Redmond 市で働くすべてのユーザーに割り当てします。</span><span class="sxs-lookup"><span data-stu-id="94402-140">The following command assigns the per-user dial plan RedmondDialPlan to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="94402-141">このコマンドで使用される LdapFilter パラメーターの詳細については [、Get-CsUser](/powershell/module/skype/get-csuser?view=skype-ps) コマンドレットのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="94402-141">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](/powershell/module/skype/get-csuser?view=skype-ps) cmdlet:</span></span>
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> <span data-ttu-id="94402-142">オンライン ユーザーには、グローバル ダイヤル プランまたはユーザー ダイヤル プランを使用できます。</span><span class="sxs-lookup"><span data-stu-id="94402-142">You may use either Global or User dial plans for online users.</span></span> <span data-ttu-id="94402-143">サイト ダイヤル プランは、オンプレミスでホストされ、オンプレミス サイトに割り当てられているユーザーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="94402-143">Site dial plans cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-dial-plan"></a><span data-ttu-id="94402-144">ユーザーごとのダイヤル プランの割り当てを解除するには</span><span class="sxs-lookup"><span data-stu-id="94402-144">To unassign a per-user dial plan</span></span>

- <span data-ttu-id="94402-145">[Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps)コマンドレットを使用して、Ken Myer に以前割り当てられたユーザーごとのダイヤル プランの割り当てを解除します。</span><span class="sxs-lookup"><span data-stu-id="94402-145">Use the [Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to unassign any per-user dial plan previously assigned to Ken Myer.</span></span> <span data-ttu-id="94402-146">ユーザーごとのダイヤル プランが割り当て解除された後、Ken Myer は、自分のレジストラーまたは PSTN ゲートウェイに割り当てられたグローバル ダイヤル プランまたはサービス スコープダイヤル プランを使用して自動的に管理されます。</span><span class="sxs-lookup"><span data-stu-id="94402-146">After the per-user dial plan is unassigned, Ken Myer will automatically be managed by using the global dial plan or the service-scope dial plan assigned to his Registrar or PSTN gateway.</span></span> <span data-ttu-id="94402-147">サービス スコープダイヤル プランは、グローバル ダイヤル プランよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="94402-147">A service scope dial plan takes precedence over the global dial plan:</span></span>
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="94402-148">オンプレミスのコマンドレットを使用して音声ルーティング ポリシー Windows PowerShellする</span><span class="sxs-lookup"><span data-stu-id="94402-148">Update the voice routing policies using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="94402-149">このセクションでは、電話システムで有効になっているユーザーの音声ルーティング ポリシーを更新する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="94402-149">This section describes how to update the voice routing policies for users enabled for Phone System.</span></span>
  
<span data-ttu-id="94402-150">電話システム のユーザーは、通話が正常にルーティングするために、音声ルーティング ポリシーが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="94402-150">Phone System users must have a Voice Routing Policy assigned to them for calls to route successfully.</span></span> <span data-ttu-id="94402-151">これは、通話を正常にルーティングするために音声ポリシーを割り当てる必要があるオンプレミスのビジネス音声ユーザーとは異なります。</span><span class="sxs-lookup"><span data-stu-id="94402-151">This differs from on-premises business voice users who require a Voice Policy to be assigned to them to allow calls to route successfully.</span></span> <span data-ttu-id="94402-152">音声ルーティング ポリシーには、電話システム ユーザーの承認された通話とルートを定義する PSTN 使用法が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="94402-152">The Voice Routing Policy should contain PSTN usages that define authorized calls and routes for Phone System users.</span></span> <span data-ttu-id="94402-153">これらの PSTN 使用法は、既存の音声ポリシーから新しい音声ルーティング ポリシーにコピーできます。</span><span class="sxs-lookup"><span data-stu-id="94402-153">You can copy these PSTN usages from existing Voice Policies to new Voice Routing Policies.</span></span> <span data-ttu-id="94402-154">詳細については [、「New-CsVoiceRoutingPolicy」を参照してください](/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="94402-154">For more information, see [New-CsVoiceRoutingPolicy](/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).</span></span>
  
> [!NOTE]
> <span data-ttu-id="94402-155">すべての電話システム ユーザーには、許可されている通話機能を定義する BusinessVoice という名前の同じオンライン音声ポリシーが割り当てられます。たとえば、同時呼び出しを許可します。</span><span class="sxs-lookup"><span data-stu-id="94402-155">All Phone System users are assigned the same online Voice Policy named BusinessVoice which defines the calling features allowed; for example, Allow Simultaneous Ring.</span></span> 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a><span data-ttu-id="94402-156">ユーザー単位の音声ルーティング ポリシーを 1 人のユーザーに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="94402-156">To assign a per-user voice routing policy to a single user</span></span>

- <span data-ttu-id="94402-157">[Grant-CsVoiceRoutingPolicy](/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps)コマンドレットを使用して、ユーザーごとの音声ルーティング ポリシー RedmondVoiceRoutingPolicy をユーザー Ken Myer に割り当てる。</span><span class="sxs-lookup"><span data-stu-id="94402-157">Use the [Grant-CsVoiceRoutingPolicy](/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) cmdlet to assign the per-user voice routing policy RedmondVoiceRoutingPolicy to the user Ken Myer:</span></span>
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a><span data-ttu-id="94402-158">ユーザー単位の音声ルーティング ポリシーを複数のユーザーに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="94402-158">To assign a per-user voice routing policy to multiple users</span></span>

- <span data-ttu-id="94402-159">次のコマンドは、ユーザーごとの音声ルーティング ポリシー RedmondVoiceRoutingPolicy を、Redmond 市で働くすべてのユーザーに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="94402-159">The next command assigns the per-user voice routing policy RedmondVoiceRoutingPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="94402-160">このコマンドで使用される LdapFilter パラメーターの詳細については [、「Get-CsUser」を参照してください](/powershell/module/skype/get-csuser?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="94402-160">For more information on the LdapFilter parameter used in this command, see [Get-CsUser](/powershell/module/skype/get-csuser?view=skype-ps).</span></span>
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > <span data-ttu-id="94402-161">オンライン ユーザーには、グローバルまたはユーザーの音声ルーティング ポリシーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="94402-161">You may use either Global or User voice routing policies for online users.</span></span> <span data-ttu-id="94402-162">サイト音声ルーティング ポリシーは、オンプレミスでホストされ、オンプレミス サイトに割り当てられているユーザーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="94402-162">Site voice routing policies cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a><span data-ttu-id="94402-163">ユーザーごとの音声ルーティング ポリシーの割り当てを解除するには</span><span class="sxs-lookup"><span data-stu-id="94402-163">To unassign a per-user voice routing policy</span></span>

- <span data-ttu-id="94402-164">Ken Myer に以前Grant-CsVoiceRoutingPolicy割り当てられたユーザーごとの音声ルーティング ポリシーの割り当てを解除するには、このオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="94402-164">Use the Grant-CsVoiceRoutingPolicy to unassign any per-user voice routing policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="94402-165">ユーザーごとの音声ルーティング ポリシーが割り当て解除された後、Ken Myer はグローバル音声ルーティング ポリシーを使用して自動的に管理されます。</span><span class="sxs-lookup"><span data-stu-id="94402-165">After the per-user voice routing policy is unassigned, Ken Myer will automatically be managed by using the global voice routing policy.</span></span>
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    <span data-ttu-id="94402-166">詳細については [、「Grant-CsVoiceRoutingPolicy」を参照してください](/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="94402-166">For more information, see [Grant-CsVoiceRoutingPolicy](/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).</span></span>
