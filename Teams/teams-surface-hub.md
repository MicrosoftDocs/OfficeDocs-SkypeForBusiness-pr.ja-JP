---
title: サーフェスのハブのマイクロソフトのチームを配置します。
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 07/02/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: jatpatel
description: サーフェスのハブのマイクロソフトのチームの管理の設定を構成します。
localization_priority: Normal
ms.custom:
- Devices
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 948f9f9ed32f4e5846248dfbcd2b96577a0f34ee
ms.sourcegitcommit: 2b15226723c299fe94f1a012aa21222173fe3af8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2018
ms.locfileid: "20192181"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a><span data-ttu-id="549d0-103">サーフェスのハブのマイクロソフトのチームを配置します。</span><span class="sxs-lookup"><span data-stu-id="549d0-103">Deploy Microsoft Teams for Surface Hub</span></span>
======================================

<span data-ttu-id="549d0-104">Microsoft Surface のハブのマイクロソフトのチームを配置する前に、ハードウェア、オペレーティング システム、およびその他の要件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="549d0-104">Before you deploy Microsoft Teams for Microsoft Surface Hub, be sure you have met the hardware, operating system, and other requirements.</span></span> <span data-ttu-id="549d0-105">詳細については、 [Microsoft Surface ハブ管理者ガイド](https://docs.microsoft.com/en-us/surface-hub/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="549d0-105">For more information, see the [Microsoft Surface Hub admin guide](https://docs.microsoft.com/en-us/surface-hub/).</span></span>

## <a name="set-up-user-accounts"></a><span data-ttu-id="549d0-106">ユーザー アカウントを設定します</span><span class="sxs-lookup"><span data-stu-id="549d0-106">Set up user accounts</span></span>
 
<span data-ttu-id="549d0-107">サーフェスのハブのチームと共同で使用できるユーザー アカウントを設定するには、ビジネスの Skype でのサポートと同様、デバイスのアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="549d0-107">To set up user accounts that can be used with Teams for Surface Hub, create the device account as you would for support with Skype for Business.</span></span> <span data-ttu-id="549d0-108">デバイスのアカウントが必要複数要素の認証が無効になります (自動ログオンを許可する) Office 365 でのチームの次の依存するサービスです。</span><span class="sxs-lookup"><span data-stu-id="549d0-108">The device account needs to have multi-factor authentication disabled (to allow automatic logon) for the following dependent services of Teams in Office 365:</span></span>  
- <span data-ttu-id="549d0-109">Exchange</span><span class="sxs-lookup"><span data-stu-id="549d0-109">Exchange</span></span> 
- <span data-ttu-id="549d0-110">SharePoint</span><span class="sxs-lookup"><span data-stu-id="549d0-110">SharePoint</span></span> 
- <span data-ttu-id="549d0-111">Office アプリケーション</span><span class="sxs-lookup"><span data-stu-id="549d0-111">Office Apps</span></span> 

## <a name="add-a-device-account"></a><span data-ttu-id="549d0-112">デバイス アカウントを追加する</span><span class="sxs-lookup"><span data-stu-id="549d0-112">Add a device account</span></span> 

<span data-ttu-id="549d0-113">1\。</span><span class="sxs-lookup"><span data-stu-id="549d0-113">1\.</span></span> <span data-ttu-id="549d0-114">PC 上でリモートの Windows PowerShell セッションを開始し、Exchange に接続します。</span><span class="sxs-lookup"><span data-stu-id="549d0-114">Start a remote Windows PowerShell session on a PC and connect to Exchange.</span></span> <span data-ttu-id="549d0-115">関連付けられているコマンドレットを実行する適切なアクセス許可があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="549d0-115">Be sure you have the correct permissions set to run the associated cmdlets.</span></span> <span data-ttu-id="549d0-116">環境で使用し、変更できるコマンドレットの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="549d0-116">The following are some examples of cmdlets that can be used and modified in your environment.</span></span>

```
Set-ExecutionPolicy Unrestricted
$org='contoso.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ 
-Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

<span data-ttu-id="549d0-117">2\。</span><span class="sxs-lookup"><span data-stu-id="549d0-117">2\.</span></span> <span data-ttu-id="549d0-118">セッションを確立したら、新しいメールボックスを作成して RoomMailboxAccount として有効にするか、既存の会議室メールボックスの設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="549d0-118">After establishing a session, you’ll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="549d0-119">これにより、チームへの認証にアカウントが許可されます。</span><span class="sxs-lookup"><span data-stu-id="549d0-119">This will allow the account to authenticate to Teams.</span></span>

<span data-ttu-id="549d0-120">既存のリソース メールボックスを変更している場合:</span><span class="sxs-lookup"><span data-stu-id="549d0-120">If you are changing an existing resource mailbox:</span></span>

```
Set-Mailbox -Identity 'TEAMS01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

<span data-ttu-id="549d0-121">新しいリソース メールボックスを作成している場合:</span><span class="sxs-lookup"><span data-stu-id="549d0-121">If you’re creating a new resource mailbox:</span></span>

```
New-Mailbox -MicrosoftOnlineServicesID TEAMS01@contoso.com -Alias TEAMS01 
-Name "Teams-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword
 (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

<span data-ttu-id="549d0-122">3\。</span><span class="sxs-lookup"><span data-stu-id="549d0-122">3\.</span></span> <span data-ttu-id="549d0-123">会議エクスペリエンスを改善するために、さまざまな Exchange プロパティをデバイス アカウントに設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="549d0-123">Various Exchange properties must be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="549d0-124">設定する必要のあるプロパティは、「Exchange のプロパティ」セクションで確認できます。</span><span class="sxs-lookup"><span data-stu-id="549d0-124">You can see which properties need to be set in the Exchange properties section.</span></span>

```
Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false
 -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
```

<span data-ttu-id="549d0-125">4\。</span><span class="sxs-lookup"><span data-stu-id="549d0-125">4\.</span></span> <span data-ttu-id="549d0-126">Azure Active Directory に接続して、アカウント設定をいくつか適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="549d0-126">You will need to connect to Azure Active Directory to apply some account settings.</span></span> <span data-ttu-id="549d0-127">Azure AD に接続するには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="549d0-127">To connect to Azure AD, run the following cmdlet:</span></span>

```
Connect-MsolService -Credential $cred
```

<span data-ttu-id="549d0-128">5\。</span><span class="sxs-lookup"><span data-stu-id="549d0-128">5\.</span></span> <span data-ttu-id="549d0-129">	パスワードを無期限にする場合は、次のように Set-MsolUser コマンドレットに PasswordNeverExpires オプションを付けて実行します。</span><span class="sxs-lookup"><span data-stu-id="549d0-129">If you do not want the password to expire, run the Set-MsolUser cmdlet with the PasswordNeverExpires option as follows:</span></span> 

```
Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
```

<span data-ttu-id="549d0-130">次のように、会議室の電話番号を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="549d0-130">You can also set a phone number for the room as follows:</span></span>

```
Set-MsolUser -UniversalPrincipalName <upn> -PhoneNumber <phone number>
```

<span data-ttu-id="549d0-131">6\。</span><span class="sxs-lookup"><span data-stu-id="549d0-131">6\.</span></span> <span data-ttu-id="549d0-132">デバイスのアカウントは、有効な Office 365 のライセンスでは、する必要があるか、Exchange およびビジネス用の Skype は機能しません。</span><span class="sxs-lookup"><span data-stu-id="549d0-132">The device account needs to have a valid Office 365 license, or Exchange and Skype for Business will not work.</span></span> <span data-ttu-id="549d0-133">ライセンスがあれば、利用場所を割り当てる、デバイスのアカウントにする必要があります-どのようなライセンスは、アカウントの利用可能な決定します。</span><span class="sxs-lookup"><span data-stu-id="549d0-133">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="549d0-134">Get MsolAccountSku を使用して、次のように、Office 365 テナントの使用可能な Sku の一覧を取得できます。</span><span class="sxs-lookup"><span data-stu-id="549d0-134">You can use Get-MsolAccountSku to retrieve a list of available SKUs for your Office 365 tenant as follows:</span></span>
 
```
Get-MsolAccountSku
```

<span data-ttu-id="549d0-p109">次に、Set-MsolUserLicense コマンドレットを使用して、ライセンスを追加することができます。この場合、表示される SKU コードは $strLicense です (たとえば、contoso:STANDARDPACK)。</span><span class="sxs-lookup"><span data-stu-id="549d0-p109">Next, you can add a license using the Set-MsolUserLicense cmdlet. In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

```
Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
Get-MsolAccountSku
Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
```

<span data-ttu-id="549d0-137">7\。</span><span class="sxs-lookup"><span data-stu-id="549d0-137">7\.</span></span> <span data-ttu-id="549d0-138">次に、サーフェスのハブのチームを持つデバイスのアカウントを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="549d0-138">Next, you need to enable the device account with Teams for Surface Hub.</span></span> <span data-ttu-id="549d0-139">お客様の環境は、 [Microsoft Surface ハブ管理者ガイド 』](https://docs.microsoft.com/en-us/surface-hub/)で定義されている要件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="549d0-139">Be sure your environment meets the requirements defined in [Microsoft Surface Hub admin guide](https://docs.microsoft.com/en-us/surface-hub/).</span></span>

<span data-ttu-id="549d0-140">次のように、リモートの Windows PowerShell セッションを開始 (オンライン PowerShell のビジネス コンポーネントの Skype をインストールすることを確認する)。</span><span class="sxs-lookup"><span data-stu-id="549d0-140">Start a remote Windows PowerShell session as follows (be sure to install Skype for Business Online PowerShell components):</span></span>

```
Import-Module LyncOnlineConnector
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

<span data-ttu-id="549d0-141">次に、次のコマンドレットを実行して、サーフェスのハブのアカウントに、チームを有効にします。</span><span class="sxs-lookup"><span data-stu-id="549d0-141">Next, enable your Teams for Surface Hub account by running the following cmdlet:</span></span>

```
Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
```

<span data-ttu-id="549d0-142">次の使用例に示すように、新しいユーザー アカウントのセットアップの中から RegistrarPool 情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="549d0-142">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

```
Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
```

> [!NOTE]
> <span data-ttu-id="549d0-143">テナント内の既存のユーザー アカウントとして同じレジストラー プールに新しいユーザー アカウントを作成できません可能性があります。</span><span class="sxs-lookup"><span data-stu-id="549d0-143">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="549d0-144">上記のコマンドは、このような状況が発生したため、アカウントのセットアップでエラーをできなくなります。</span><span class="sxs-lookup"><span data-stu-id="549d0-144">The command above will prevent errors in account setup due to this situation.</span></span> 

<span data-ttu-id="549d0-145">サーフェスのハブのアカウントに、チームを有効にするのには、上記の手順を完了した後は、サーフェスのハブ v2 デバイスにライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="549d0-145">After you've completed the preceding steps to enable your Teams for Surface Hub account, you need to assign a license to the Surface Hub v2 device.</span></span> <span data-ttu-id="549d0-146">Office 365 管理ポータルを使用して、デバイスに、チームでのサーフェスのハブのライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="549d0-146">Using the Office 365 administrative portal, assign a Teams for Surface Hub license to the device.</span></span>

### <a name="assign-a-license-to-the-account"></a><span data-ttu-id="549d0-147">アカウントにライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="549d0-147">Assign a license to the account</span></span>

1. <span data-ttu-id="549d0-148">テナント管理者としてログオンし、Office 365 管理センターで、開き [管理アプリケーション] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="549d0-148">Log on as a tenant administrator, open the Office 365 admin center, and click on the Admin app.</span></span>
2. <span data-ttu-id="549d0-149">**ユーザーとグループ**をクリックし、**ユーザーの追加、パスワードのリセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="549d0-149">Click **Users and Groups**, and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="549d0-150">サーフェスのハブのアカウント チームを選択しを手段の編集 [ペン] アイコンをタップします。</span><span class="sxs-lookup"><span data-stu-id="549d0-150">Select the Teams for Surface Hub account, and then click or tap the pen icon, which means edit.</span></span>
4. <span data-ttu-id="549d0-151">**ライセンス**オプションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="549d0-151">Click the **Licenses** option.</span></span>
5. <span data-ttu-id="549d0-152">[**ライセンスの割り当て**] セクションで、ライセンスによって、プランを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="549d0-152">In the **Assign licenses** section, you need to select the plan, depending on your licensing.</span></span>
6. <span data-ttu-id="549d0-153">タスクを完了するには、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="549d0-153">Click **Save** to complete the task.</span></span>

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a><span data-ttu-id="549d0-154">Microsoft ストアからのサーフェスのハブのチームをインストールします。</span><span class="sxs-lookup"><span data-stu-id="549d0-154">Install Teams for Surface Hub from the Microsoft Store</span></span> 

<span data-ttu-id="549d0-155">次の手順には、Microsoft ストアからのサーフェスのハブのチームをインストールするための現在の回避策が含まれます。</span><span class="sxs-lookup"><span data-stu-id="549d0-155">These instructions include the current workarounds for installing Teams for Surface Hub from the Microsoft Store.</span></span> 
 
1. <span data-ttu-id="549d0-156">Windows ストアを開始します。</span><span class="sxs-lookup"><span data-stu-id="549d0-156">Start the Windows Store:</span></span><br>
   <span data-ttu-id="549d0-157">a.</span><span class="sxs-lookup"><span data-stu-id="549d0-157">a.</span></span> <span data-ttu-id="549d0-158">**スタート**をタップして > **すべてのアプリケーション** > **の設定**です。</span><span class="sxs-lookup"><span data-stu-id="549d0-158">Tap **Start** > **All Apps** > **Settings**.</span></span><br> <span data-ttu-id="549d0-159">b.</span><span class="sxs-lookup"><span data-stu-id="549d0-159">b.</span></span> <span data-ttu-id="549d0-160">**サーフェス ハブ デバイスのアカウント、管理**をタップします。</span><span class="sxs-lookup"><span data-stu-id="549d0-160">Tap **Surface Hub Device account, management**.</span></span><br>
   <span data-ttu-id="549d0-161">c.</span><span class="sxs-lookup"><span data-stu-id="549d0-161">c.</span></span> <span data-ttu-id="549d0-162">左側の [**アプリケーションと機能**] タブをタップします。</span><span class="sxs-lookup"><span data-stu-id="549d0-162">On the left, tap the **Apps & Features** tab.</span></span><br> <span data-ttu-id="549d0-163">d.</span><span class="sxs-lookup"><span data-stu-id="549d0-163">d.</span></span> <span data-ttu-id="549d0-164">、右側には、**ストアを開く**] ボタンをタップします。</span><span class="sxs-lookup"><span data-stu-id="549d0-164">On the right, tap the **Open Store** button.</span></span> 
2. <span data-ttu-id="549d0-165">マイクロソフト ストアからには、*マイクロソフトのチーム*を検索します。</span><span class="sxs-lookup"><span data-stu-id="549d0-165">From the Microsoft Store, search for *Microsoft Teams*.</span></span> <span data-ttu-id="549d0-166">**サーフェスのハブ (プレビュー) のマイクロソフトのチーム**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="549d0-166">The **Microsoft Teams for Surface Hub (Preview)** will be displayed.</span></span> <span data-ttu-id="549d0-167">インストールする**アプリケーションを取得する**ボタンをタップします。</span><span class="sxs-lookup"><span data-stu-id="549d0-167">Tap the **Get the app** button to install.</span></span>  
3. <span data-ttu-id="549d0-168">インストールが完了すると、サーフェスのハブを再起動します。</span><span class="sxs-lookup"><span data-stu-id="549d0-168">When the installation is complete, restart the Surface Hub.</span></span> 
4. <span data-ttu-id="549d0-169">サーフェスのハブを再起動した後は、 **[スタート**] メニューから、チームのアプリケーションを起動し、予定表から会議に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="549d0-169">After the Surface Hub restarts, you should be able to start the Teams app from the **Start** menu and join a meeting from the calendar.</span></span> 

## <a name="make-teams-the-default-vtc-application"></a><span data-ttu-id="549d0-170">VTC の既定のアプリケーションをチームに加える</span><span class="sxs-lookup"><span data-stu-id="549d0-170">Make Teams the default VTC application</span></span>

<span data-ttu-id="549d0-171">チームは、ビジネスの Skype ではなく既定の VTC のアプリケーションであるように設定できます。</span><span class="sxs-lookup"><span data-stu-id="549d0-171">Teams can be set up to be the default VTC application instead of Skype for Business.</span></span> <span data-ttu-id="549d0-172">モバイル デバイス管理 (MDM) ポリシーでは、サーフェスのハブ デバイスに適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="549d0-172">A Mobile Device Management (MDM) policy needs to be applied to the Surface Hub device.</span></span> 
 
<span data-ttu-id="549d0-173">MDM のポリシーを構成するための 2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="549d0-173">There are two options for configuring MDM policies:</span></span> 

- <span data-ttu-id="549d0-174">構成されたポリシーがある場合は、デバイス管理アプリケーションを使用して追加します。</span><span class="sxs-lookup"><span data-stu-id="549d0-174">If you have a policy configured, add it via the Device management app.</span></span> 
- <span data-ttu-id="549d0-175">リモート ポリシーを構成しない場合、USB キーを読み込むことができますが準備されたパッケージ ファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="549d0-175">If you do not have a remote policy configured, we have a provisioned package file that you can load onto an USB key.</span></span>

### <a name="device-management-configuration"></a><span data-ttu-id="549d0-176">デバイス管理の構成</span><span class="sxs-lookup"><span data-stu-id="549d0-176">Device management configuration</span></span>

<span data-ttu-id="549d0-177">次に、MDM の中枢から構成されている、MDM のポリシーを追加する例を示します。</span><span class="sxs-lookup"><span data-stu-id="549d0-177">The following is an example of adding an MDM policy configured from a central MDM authority.</span></span> <span data-ttu-id="549d0-178">企業ネットワークの場合は、ユーザー アカウントを含むをそのまま次の手順を使用できます。</span><span class="sxs-lookup"><span data-stu-id="549d0-178">If you are on the corporate network, you can use the following instructions verbatim, including user account.</span></span> 
 
1. <span data-ttu-id="549d0-179">**デバイスの管理**] セクションで、をタップ**+**。</span><span class="sxs-lookup"><span data-stu-id="549d0-179">Under the **Device Management** section, tap **+**.</span></span><br>
   <span data-ttu-id="549d0-180">**作業や、学校への接続**] ダイアログ ボックスが開きます。</span><span class="sxs-lookup"><span data-stu-id="549d0-180">The **Connect to work or school** dialog box will open.</span></span> 
2. <span data-ttu-id="549d0-181">ポリシーの電子メール アドレスとパスワードが表示されたら入力します。</span><span class="sxs-lookup"><span data-stu-id="549d0-181">Enter the policy e-mail address and password when prompted.</span></span><br>
   <span data-ttu-id="549d0-182">**注:** バグがあり、OS、デバイスの管理アカウントを入力した後に、UI を自動的に更新しないことにします。</span><span class="sxs-lookup"><span data-stu-id="549d0-182">**NOTE:**  There's a bug in the OS that doesn't automatically refresh the UI after you've entered your device management account.</span></span> <span data-ttu-id="549d0-183">閉じるし、表示されているアカウントを確認するために設定を再度開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="549d0-183">You'll need to close and re-open settings in order to see the account listed.</span></span> 
3. <span data-ttu-id="549d0-184">MDM ポリシーの設定を同期するまでに数分かかるでしょう。強制的に同期する場合は、 **MDM のアカウント**] ボタンをタップし、**情報**] の順にタップします。</span><span class="sxs-lookup"><span data-stu-id="549d0-184">It'll take a few minutes for the MDM policy settings to sync. If you want to force a sync, tap the **MDM account** button, and then tap the **Info** button.</span></span> <span data-ttu-id="549d0-185">**同期**をし、タップした場所の情報] ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="549d0-185">This will bring up the Info window where you can then tap **Sync**.</span></span> 
4. <span data-ttu-id="549d0-186">必要があることを確認するには、レジストリをチェックできます。</span><span class="sxs-lookup"><span data-stu-id="549d0-186">To verify that you have what you need, you can check the registry.</span></span> <span data-ttu-id="549d0-187">**HKLM\Software\Microsoft\Windows\CurrentVersion\PPI\VtcCallSettings**の下の 2 つのキーを参照してくださいする必要があります。</span><span class="sxs-lookup"><span data-stu-id="549d0-187">You should see two keys under **HKLM\Software\Microsoft\Windows\CurrentVersion\PPI\VtcCallSettings**.</span></span> <br><br>
   <span data-ttu-id="549d0-188">**VtcAppMeetingHandlingMode**の DWORD 値は、チームが既定のアプリケーションであることを示します。</span><span class="sxs-lookup"><span data-stu-id="549d0-188">The **VtcAppMeetingHandlingMode** DWORD value indicates that Teams is the default app.</span></span> <span data-ttu-id="549d0-189">次の値が認識されます。</span><span class="sxs-lookup"><span data-stu-id="549d0-189">The following values are recognized.</span></span> <br><br>
    |<span data-ttu-id="549d0-190">数値</span><span class="sxs-lookup"><span data-stu-id="549d0-190">Number</span></span> | <span data-ttu-id="549d0-191">値</span><span class="sxs-lookup"><span data-stu-id="549d0-191">Value</span></span>   |
    |-------|---------|
    |<span data-ttu-id="549d0-192">0</span><span class="sxs-lookup"><span data-stu-id="549d0-192">0</span></span>      | <span data-ttu-id="549d0-193">SkypePreferred</span><span class="sxs-lookup"><span data-stu-id="549d0-193">SkypePreferred</span></span>            |
    |<span data-ttu-id="549d0-194">1</span><span class="sxs-lookup"><span data-stu-id="549d0-194">1</span></span>      | <span data-ttu-id="549d0-195">VtcPreferred (チーム)</span><span class="sxs-lookup"><span data-stu-id="549d0-195">VtcPreferred (Teams)</span></span>      |
    |<span data-ttu-id="549d0-196">2</span><span class="sxs-lookup"><span data-stu-id="549d0-196">2</span></span>      | <span data-ttu-id="549d0-197">VtcExclusive (チームのみ)</span><span class="sxs-lookup"><span data-stu-id="549d0-197">VtcExclusive (Teams only)</span></span> |

    <span data-ttu-id="549d0-198">**VtcCallAppPackageId**は、インストールされているチームのパッケージの名前です。</span><span class="sxs-lookup"><span data-stu-id="549d0-198">The **VtcCallAppPackageId** is the name of the installed Teams package.</span></span> <span data-ttu-id="549d0-199">これに表示されていない場合、チームのパッケージをインストールしたかどうかを確認し、再同期します。</span><span class="sxs-lookup"><span data-stu-id="549d0-199">If this doesn't show up, make sure you've installed the Teams package, and re-sync.</span></span> 
 
### <a name="configure-mdm-via-usb-key"></a><span data-ttu-id="549d0-200">MDM を USB キーを使用して構成します。</span><span class="sxs-lookup"><span data-stu-id="549d0-200">Configure MDM via USB key</span></span> 
 
<span data-ttu-id="549d0-201">この[ダウンロード ページ](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g)で、パッケージをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="549d0-201">The packages can be found on this [download page](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g).</span></span> <span data-ttu-id="549d0-202">適切なパッケージをインストールし、USB キーにコピーする予定しているを選択します。</span><span class="sxs-lookup"><span data-stu-id="549d0-202">Pick the appropriate one for the package that you're planning to install and copy it to a USB key.</span></span> <span data-ttu-id="549d0-203">正しい .ppkg ファイルを使用するのには、ストアからインストールされているチームのパッケージと (排他的な Skype、Skype を優先する、チームが優先すると、チームの排他的) を適用したいポリシーによって異なります。</span><span class="sxs-lookup"><span data-stu-id="549d0-203">The correct .ppkg file to use depends on the Teams package that has been installed from the store, and the policy you'd like to apply (Skype exclusive, Skype preferred, Teams preferred, Teams exclusive).</span></span> 
 
1. <span data-ttu-id="549d0-204">サーフェス ハブ デバイスに USB キーを接続します。</span><span class="sxs-lookup"><span data-stu-id="549d0-204">Attach the USB key to the Surface Hub device.</span></span> 
2. <span data-ttu-id="549d0-205">サーフェス ハブ デバイスの**設定**アプリを開きます。</span><span class="sxs-lookup"><span data-stu-id="549d0-205">Open the **Settings** app on a Surface Hub device.</span></span> 
3. <span data-ttu-id="549d0-206">**表面ハブ デバイスのアカウントの管理**を開きます。</span><span class="sxs-lookup"><span data-stu-id="549d0-206">Open **Surface Hub Device Account Management**.</span></span>
4. <span data-ttu-id="549d0-207">**デバイスの管理**を開きます。</span><span class="sxs-lookup"><span data-stu-id="549d0-207">Open **Device Management**.</span></span> 
5. <span data-ttu-id="549d0-208">**追加またはプロビジョニング ・ パッケージを削除する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="549d0-208">Click **Add or Remove a provisioning package**.</span></span> 
6. <span data-ttu-id="549d0-209">**パッケージの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="549d0-209">Click **Add Package**.</span></span>
7. <span data-ttu-id="549d0-210">ドロップ ダウン メニューから、[**リムーバブル メディア**] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="549d0-210">Select the **Removable Media** option from the drop-down menu.</span></span> 
8. <span data-ttu-id="549d0-211">**Allowbuildspreview.ppkg**を追加し、追加するサーフェスのハブのパッケージを選択します。</span><span class="sxs-lookup"><span data-stu-id="549d0-211">Add the **Allowbuildspreview.ppkg**, and then select the Surface Hub package you want to add.</span></span> 
9. <span data-ttu-id="549d0-212">サーフェス ハブ デバイスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="549d0-212">Restart the Surface Hub device.</span></span> 

> [!NOTE]
> <span data-ttu-id="549d0-213">デバイスや、組織のデバイスは、現在 Windows 内部からのプログラムの一部と全般的なデータ保護規制 (GDPR) で対象となる国では (または基本の遠隔測定の設定を手動で変更がある) 場合は、チェックする必要があります再します。有効に完全な遠隔測定を内部からプログラムに参加する前にします。</span><span class="sxs-lookup"><span data-stu-id="549d0-213">If your device or your organization's devices are not currently part of the Windows Insider Program and you are in countries covered by General Data Protection Regulation (GDPR) (or you have manually changed your telemetry settings to Basic), then you must re-check that you have permitted full telemetry before you join the Insider Program.</span></span> <span data-ttu-id="549d0-214">GDPR は、基本的な遠隔測定を設定するのには、EU 内のサーフェスのハブ デバイスの既定の動作を変更します。</span><span class="sxs-lookup"><span data-stu-id="549d0-214">GDPR changed the default behavior of Surface Hub devices in the EU to set telemetry to Basic.</span></span>