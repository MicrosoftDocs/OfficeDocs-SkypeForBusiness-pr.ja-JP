---
title: Skype Room Systems バージョン 2 と Office 365 を展開する
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Office 365 で Skype ルーム システム v2 を展開する方法の詳細については、このトピックを参照してください。
ms.openlocfilehash: c623d689f876cfe36c7c8308a7f62526be217ec1
ms.sourcegitcommit: a9556a51f7f970fc05ab0acc9998401db3c1aa57
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2018
ms.locfileid: "22601970"
---
# <a name="deploy-skype-room-systems-v2-with-office-365"></a><span data-ttu-id="e85ec-103">Skype Room Systems バージョン 2 と Office 365 を展開する </span><span class="sxs-lookup"><span data-stu-id="e85ec-103">Deploy Skype Room Systems v2 with Office 365</span></span>
 
<span data-ttu-id="e85ec-104">Skype ビジネスと Exchange の両方がオンラインで、Office 365 で Skype ルーム システム v2 を展開する方法の詳細については、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e85ec-104">Read this topic for information on how to deploy Skype Room Systems v2 with Office 365, where Skype for Business and Exchange are both online.</span></span> 

<span data-ttu-id="e85ec-105">ユーザー アカウントを設定する最も簡単な方法では、リモートの Windows PowerShell を使用してそれらを構成します。</span><span class="sxs-lookup"><span data-stu-id="e85ec-105">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="e85ec-106">マイクロソフトでは、 [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105)、新しいユーザー アカウントを作成または Skype ルーム システム v2 の互換性のあるユーザー アカウントにそれらを有効にするためにある既存のリソース アカウントの検証を支援するスクリプトを提供します。</span><span class="sxs-lookup"><span data-stu-id="e85ec-106">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Skype Room Systems v2 user accounts.</span></span> <span data-ttu-id="e85ec-107">場合は、Skype ルーム システム v2 デバイスを使用してアカウントを構成するのには、次の手順に従うことができます。</span><span class="sxs-lookup"><span data-stu-id="e85ec-107">If you prefer, you can follow the steps below to configure accounts your Skype Room Systems v2 device will use.</span></span>
  
## <a name="deploy-skype-room-systems-v2-with-office-365"></a><span data-ttu-id="e85ec-108">Skype Room Systems バージョン 2 と Office 365 を展開する </span><span class="sxs-lookup"><span data-stu-id="e85ec-108">Deploy Skype Room Systems v2 with Office 365</span></span>

<span data-ttu-id="e85ec-109">Office 365 で Skype ルーム システム v2 を展開する前に、要件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e85ec-109">Before you deploy Skype Room Systems v2 with Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="e85ec-110">詳細については、 [Skype ルーム システム v2 の要件](../../plan-your-deployment/clients-and-devices/requirements.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e85ec-110">For more information, see [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>
  
<span data-ttu-id="e85ec-111">ビジネス用の Skype を有効にするには、以下が必要です。</span><span class="sxs-lookup"><span data-stu-id="e85ec-111">To enable Skype for Business, you must have the following:</span></span>
  
- <span data-ttu-id="e85ec-112">(プラン 2 の場合、または企業レベルの計画)、オンライン ビジネスの Skype 以降、Office 365 のプランで。</span><span class="sxs-lookup"><span data-stu-id="e85ec-112">Skype for Business Online (Plan 2, or an Enterprise-based plan) or higher in your Office 365 plan.</span></span> <span data-ttu-id="e85ec-113">計画では、ダイヤルイン会議機能を許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e85ec-113">The plan needs to allow dial-in conferencing capabilities.</span></span>
    
- <span data-ttu-id="e85ec-114">会議にダイヤルイン機能が必要な場合は、音声会議や電話システムのライセンスを必要があります。</span><span class="sxs-lookup"><span data-stu-id="e85ec-114">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="e85ec-115">会議からのダイヤル ・ アウト機能が必要な場合、国内または国内および海外を呼び出すことを計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e85ec-115">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span> 
    
- <span data-ttu-id="e85ec-116">テナント ユーザーは、Exchange のメールボックスが必要です。</span><span class="sxs-lookup"><span data-stu-id="e85ec-116">Your tenant users must have Exchange mailboxes.</span></span>
    
- <span data-ttu-id="e85ec-117">Skype ルーム システム v2 アカウントにする必要が、最小値で、Skype ビジネス オンライン (プラン 2) のライセンスが、Exchange Online のライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="e85ec-117">Your Skype Room Systems v2 account does require at a minumum a Skype for Business Online (Plan 2) license, but it does not require an Exchange Online license.</span></span>

<span data-ttu-id="e85ec-118">Skype のビジネスのオンラインの計画の詳細については、 [Skype](https://technet.microsoft.com/library/jj822172.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e85ec-118">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>

### <a name="add-a-device-account"></a><span data-ttu-id="e85ec-119">デバイス アカウントを追加する</span><span class="sxs-lookup"><span data-stu-id="e85ec-119">Add a device account</span></span>

1. <span data-ttu-id="e85ec-120">PC 上でリモートの Windows PowerShell セッションを開始し、Exchange に接続します。</span><span class="sxs-lookup"><span data-stu-id="e85ec-120">Start a remote Windows PowerShell session on a PC and connect to Exchange.</span></span> <span data-ttu-id="e85ec-121">関連するコマンドレットを実行するために適切な権限が設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e85ec-121">Be sure you have the right permissions set to run the associated cmdlets.</span></span> <span data-ttu-id="e85ec-122">環境で使用し、変更できるコマンドレットの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e85ec-122">The following are some examples of cmdlets that can be used and modified in your environment.</span></span>
    
   ```
   Set-ExecutionPolicy Unrestricted
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential 
   $cred -Authentication Basic -AllowRedirection
   Import-PSSession $sess
   ```

2. <span data-ttu-id="e85ec-123">セッションを確立するには後、するが新しいメールボックスを作成して、RoomMailboxAccount、として有効にか既存の会議室メールボックスの設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="e85ec-123">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="e85ec-124">これにより、Skype ルーム システム v2 を認証するためにアカウントが許可されます。</span><span class="sxs-lookup"><span data-stu-id="e85ec-124">This will allow the account to authenticate to Skype Room Systems v2.</span></span>
    
  <span data-ttu-id="e85ec-125">既存のリソース メールボックスを変更している場合:</span><span class="sxs-lookup"><span data-stu-id="e85ec-125">If you are changing an existing resource mailbox:</span></span>
    
```
Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

  <span data-ttu-id="e85ec-126">: 新しいリソース メールボックスを作成する場合</span><span class="sxs-lookup"><span data-stu-id="e85ec-126">If you're creating a new resource mailbox:</span></span>
    
   ```
   New-Mailbox -MicrosoftOnlineServicesID PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 
-Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword
 (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="e85ec-p107">会議エクスペリエンスを改善するために、さまざまな Exchange プロパティをデバイス アカウントに設定する必要があります。設定する必要のあるプロパティは、「Exchange のプロパティ」セクションで確認できます。</span><span class="sxs-lookup"><span data-stu-id="e85ec-p107">Various Exchange properties must be set on the device account to improve the meeting experience. You can see which properties need to be set in the Exchange properties section.</span></span>
    
   ```
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false
   -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"

   ```

4. <span data-ttu-id="e85ec-129">Azure Active Directory に接続して、アカウント設定をいくつか適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e85ec-129">You will need to connect to Azure Active Directory to apply some account settings.</span></span> <span data-ttu-id="e85ec-130">Azure AD に接続するには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e85ec-130">To connect to Azure AD, run the following cmdlet:</span></span>
    
   ```
   Connect-MsolService -Credential $cred
   ```

5. <span data-ttu-id="e85ec-131">	パスワードを無期限にする場合は、次のように Set-MsolUser コマンドレットに PasswordNeverExpires オプションを付けて実行します。</span><span class="sxs-lookup"><span data-stu-id="e85ec-131">If you do not want the password to expire, run the Set-MsolUser cmdlet with the PasswordNeverExpires option as follows:</span></span> 
    
   ```
   Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
   ```

   <span data-ttu-id="e85ec-132">次のように、会議室の電話番号を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="e85ec-132">You can also set a phone number for the room as follows:</span></span>
    
   ```
   Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
   ```

6. <span data-ttu-id="e85ec-133">デバイスのアカウントは、有効な Office 365 のライセンスでは、する必要があるか、Exchange およびビジネス用の Skype は機能しません。</span><span class="sxs-lookup"><span data-stu-id="e85ec-133">The device account needs to have a valid Office 365 license, or Exchange and Skype for Business will not work.</span></span> <span data-ttu-id="e85ec-134">ライセンスがあれば、利用場所を割り当てる、デバイスのアカウントにする必要があります-どのようなライセンスは、アカウントの利用可能な決定します。</span><span class="sxs-lookup"><span data-stu-id="e85ec-134">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="e85ec-135">Get MsolAccountSku を使用して、次のように、Office 365 テナントの使用可能な Sku の一覧を取得できます。</span><span class="sxs-lookup"><span data-stu-id="e85ec-135">You can use Get-MsolAccountSku to retrieve a list of available SKUs for your Office 365 tenant as follows:</span></span>
    
   ```
   Get-MsolAccountSku
   ```

   <span data-ttu-id="e85ec-p110">次に、Set-MsolUserLicense コマンドレットを使用して、ライセンスを追加することができます。この場合、表示される SKU コードは $strLicense です (たとえば、contoso:STANDARDPACK)。</span><span class="sxs-lookup"><span data-stu-id="e85ec-p110">Next, you can add a license using the Set-MsolUserLicense cmdlet. In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>
    
   ```
   Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```

7. <span data-ttu-id="e85ec-138">次に、ビジネスの Skype でデバイスのアカウントを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e85ec-138">Next, you need to enable the device account with Skype for Business.</span></span> <span data-ttu-id="e85ec-139">お客様の環境は、 [Skype ルーム システム v2 の要件](../../plan-your-deployment/clients-and-devices/requirements.md)で定義されている要件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e85ec-139">Be sure your environment meets the requirements defined in [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>
    
   <span data-ttu-id="e85ec-140">次のように、リモートの Windows PowerShell セッションを開始 (オンライン PowerShell のビジネス コンポーネントの Skype をインストールすることを確認する)。</span><span class="sxs-lookup"><span data-stu-id="e85ec-140">Start a remote Windows PowerShell session as follows (be sure to install Skype for Business Online PowerShell components):</span></span>
    
   ```
   Import-Module LyncOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   <span data-ttu-id="e85ec-141">次に、アカウント有効にする、Skype ルーム システム v2 Skype のビジネス サーバーの次のコマンドレットを実行することによって。</span><span class="sxs-lookup"><span data-stu-id="e85ec-141">Next, enable your Skype Room Systems v2 account for Skype for Business Server by running the following cmdlet:</span></span>
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   <span data-ttu-id="e85ec-142">次の使用例に示すように、新しいユーザー アカウントのセットアップの中から RegistrarPool 情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="e85ec-142">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>
    
    ```
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > <span data-ttu-id="e85ec-143">テナント内の既存のユーザー アカウントとして同じレジストラー プールに新しいユーザー アカウントを作成できません可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e85ec-143">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="e85ec-144">上記のコマンドは、このような状況が発生したため、アカウントのセットアップでエラーをできなくなります。</span><span class="sxs-lookup"><span data-stu-id="e85ec-144">The command above will prevent errors in account setup due to this situation.</span></span> 
  
<span data-ttu-id="e85ec-145">オンライン ビジネスの Skype の Skype ルーム システム v2 アカウントを有効にするのには、上記の手順を完了した後は、Skype の部屋のシステムのバージョン 2 のデバイスにライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e85ec-145">After you've completed the preceding steps to enable your Skype Room Systems v2 account in Skype for Business Online, you need to assign a license to Skype Room Systems v2 device.</span></span> <span data-ttu-id="e85ec-146">Office 365 管理ポータルを使用して、オンライン ビジネス (プラン 2) またはデバイスにライセンスをオンライン ビジネス (3 の計画)、Skype のいずれか、Skype を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e85ec-146">Using the Office 365 administrative portal, assign either a Skype for Business Online (Plan 2) or a Skype for Business Online (Plan 3) license to the device.</span></span>
  
### <a name="assign-a-license-to-your-account"></a><span data-ttu-id="e85ec-147">ライセンスをアカウントに割り当てる</span><span class="sxs-lookup"><span data-stu-id="e85ec-147">Assign a license to your account</span></span>

1. <span data-ttu-id="e85ec-148">ログイン テナント管理者は、Office 365 管理ポータルを開くし、管理アプリケーションでをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e85ec-148">Login as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
    
2. <span data-ttu-id="e85ec-149">[**ユーザーとグループ**] をクリックしてから [**ユーザーの追加、パスワードのリセットなど**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e85ec-149">Click **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
    
3. <span data-ttu-id="e85ec-150">Skype ルーム システム v2 アカウントを選択] をクリックするか、手段の編集 [ペン] アイコンをタップします。</span><span class="sxs-lookup"><span data-stu-id="e85ec-150">Select the Skype Room Systems v2 account, and then click or tap the pen icon, which means edit.</span></span>
    
4. <span data-ttu-id="e85ec-151">[**ライセンス**] オプションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e85ec-151">Click on the **Licenses** option.</span></span>
    
5. <span data-ttu-id="e85ec-152">[**ライセンスの割り当て**] セクションではビジネス オンライン (3 の計画)、によっては、ライセンスおよびエンタープライズ VoIP を必要とする点で決めたものは、ビジネス オンライン (プラン 2) または Skype の Skype を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e85ec-152">In the **Assign licenses** section, you need to select Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3), depending on your licensing and what you've decided in terms of needing Enterprise Voice.</span></span> <span data-ttu-id="e85ec-153">Skype ルーム システム v2 のクラウド PBX を使用する場合は、計画の 3 ライセンスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e85ec-153">You'll have to use a Plan 3 license if you want to use Cloud PBX on Skype Room Systems v2.</span></span> <span data-ttu-id="e85ec-154">最低でも、音声接続用に CloudPBX が必要です。</span><span class="sxs-lookup"><span data-stu-id="e85ec-154">Minimally you will need CloudPBX for voice connectivity.</span></span> <span data-ttu-id="e85ec-155">次に、PSTN の接続方法に基づきハイブリッド音声または PSTN 通話を構成します。</span><span class="sxs-lookup"><span data-stu-id="e85ec-155">Then configure hybrid voice or PSTN calling based on the PSTN connectivity method.</span></span>
    
6. <span data-ttu-id="e85ec-156">タスクを完了するには、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e85ec-156">Click **Save** to complete the task.</span></span>
    
## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="e85ec-157">サンプル: ルームのアカウント セットアップの Exchange オンラインと Skype のオンライン ビジネス</span><span class="sxs-lookup"><span data-stu-id="e85ec-157">Sample: Room account setup in Exchange Online and Skype for Business Online</span></span>

```
New-Mailbox -MicrosoftOnlineServicesID Rigel1@contoso.com
 -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true
 -RoomMailboxPassword (ConvertTo-SecureString -String "" -AsPlainText -Force)
 
Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept 
-AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments 
$false -DeleteSubject $false -RemovePrivateProperty $false
 
Set-CalendarProcessing -Identity rigel1 -AddAdditionalResponse $true 
-AdditionalResponse "This is a Rigel room!"
 
Set-MsolUser -UserPrincipalName rigel1@contoso.com -PasswordNeverExpires $true -UsageLocation "US"
 
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOEV"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOPSTN2"
 
Enable-CsMeetingRoom -Identity rigel1@contoso.onmicrosoft.com -RegistrarPool sippooldm21a05.infra.lync.com
-SipAddressType EmailAddress

```

> [!NOTE]
> <span data-ttu-id="e85ec-p115">この操作によって、CloudPBX および PSTNCallingDomesticAndInternational が追加されます。さらに、管理者インターフェースを使用して、電話番号を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e85ec-p115">This adds CloudPBX and PSTNCallingDomesticAndInternational. Addtionally, you will need to use the Admin interface to assign a phone number.</span></span> 
  
## <a name="validate"></a><span data-ttu-id="e85ec-160">検証</span><span class="sxs-lookup"><span data-stu-id="e85ec-160">Validate</span></span>

<span data-ttu-id="e85ec-161">検証、ビジネス クライアント用の Skype を使用して作成したアカウントにサインインできるように。</span><span class="sxs-lookup"><span data-stu-id="e85ec-161">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>


## <a name="see-also"></a><span data-ttu-id="e85ec-162">関連項目</span><span class="sxs-lookup"><span data-stu-id="e85ec-162">See also</span></span>

[<span data-ttu-id="e85ec-163">Skype ルーム システム v2 用のアカウントを構成します。</span><span class="sxs-lookup"><span data-stu-id="e85ec-163">Configure accounts for Skype Room Systems v2</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="e85ec-164">Skype Room Systems バージョン 2 の計画</span><span class="sxs-lookup"><span data-stu-id="e85ec-164">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="e85ec-165">Skype Room System バージョン 2 を展開する</span><span class="sxs-lookup"><span data-stu-id="e85ec-165">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="e85ec-166">Skype Room Systems バージョン 2 コンソールを構成する</span><span class="sxs-lookup"><span data-stu-id="e85ec-166">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="e85ec-167">Skype Room Systems バージョン 2 を管理する</span><span class="sxs-lookup"><span data-stu-id="e85ec-167">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

