---
title: サーフェスのハブのマイクロソフトのチームを配置します。
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 08/29/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: jatpatel
description: サーフェスのハブのマイクロソフトのチームの管理の設定を構成します。
localization_priority: Normal
search.appverid: MET150
ms.custom:
- Devices
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 93cc0195f5b8ed0ccbf89315b44fda62d91b60cb
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "25013636"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a><span data-ttu-id="0d6dc-103">サーフェスのハブのマイクロソフトのチームを配置します。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-103">Deploy Microsoft Teams for Surface Hub</span></span>
======================================

<span data-ttu-id="0d6dc-104">Microsoft Surface のハブのマイクロソフトのチームを配置する前に、ハードウェア、オペレーティング システム、およびその他の要件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-104">Before you deploy Microsoft Teams for Microsoft Surface Hub, be sure you have met the hardware, operating system, and other requirements.</span></span> <span data-ttu-id="0d6dc-105">詳細については、 [Microsoft Surface ハブ管理者ガイド](https://docs.microsoft.com/surface-hub/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-105">For more information, see the [Microsoft Surface Hub admin guide](https://docs.microsoft.com/surface-hub/).</span></span>

## <a name="set-up-user-accounts"></a><span data-ttu-id="0d6dc-106">ユーザー アカウントを設定します</span><span class="sxs-lookup"><span data-stu-id="0d6dc-106">Set up user accounts</span></span>
 
<span data-ttu-id="0d6dc-107">サーフェスのハブのチームと共同で使用できるユーザー アカウントを設定するには、ビジネスの Skype でのサポートと同様、デバイスのアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-107">To set up user accounts that can be used with Teams for Surface Hub, create the device account as you would for support with Skype for Business.</span></span> <span data-ttu-id="0d6dc-108">デバイスのアカウントが必要複数要素の認証が無効になります (自動ログオンを許可する) Office 365 でのチームの次の依存するサービスです。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-108">The device account needs to have multi-factor authentication disabled (to allow automatic logon) for the following dependent services of Teams in Office 365:</span></span>  
- <span data-ttu-id="0d6dc-109">Exchange</span><span class="sxs-lookup"><span data-stu-id="0d6dc-109">Exchange</span></span> 
- <span data-ttu-id="0d6dc-110">SharePoint</span><span class="sxs-lookup"><span data-stu-id="0d6dc-110">SharePoint</span></span> 
- <span data-ttu-id="0d6dc-111">Office アプリケーション</span><span class="sxs-lookup"><span data-stu-id="0d6dc-111">Office Apps</span></span> 

## <a name="add-a-device-account"></a><span data-ttu-id="0d6dc-112">デバイス アカウントを追加する</span><span class="sxs-lookup"><span data-stu-id="0d6dc-112">Add a device account</span></span> 

<span data-ttu-id="0d6dc-113">1\。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-113">1\.</span></span> <span data-ttu-id="0d6dc-114">PC 上でリモートの Windows PowerShell セッションを開始し、Exchange に接続します。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-114">Start a remote Windows PowerShell session on a PC and connect to Exchange.</span></span> <span data-ttu-id="0d6dc-115">関連付けられているコマンドレットを実行する適切なアクセス許可があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-115">Be sure you have the correct permissions set to run the associated cmdlets.</span></span> <span data-ttu-id="0d6dc-116">環境で使用し、変更できるコマンドレットの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-116">The following are some examples of cmdlets that can be used and modified in your environment.</span></span>

```
Set-ExecutionPolicy Unrestricted
$org='contoso.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ 
-Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

<span data-ttu-id="0d6dc-117">2\。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-117">2\.</span></span> <span data-ttu-id="0d6dc-118">セッションを確立したら、新しいメールボックスを作成して RoomMailboxAccount として有効にするか、既存の会議室メールボックスの設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-118">After establishing a session, you’ll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="0d6dc-119">これにより、チームへの認証にアカウントが許可されます。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-119">This will allow the account to authenticate to Teams.</span></span>

<span data-ttu-id="0d6dc-120">既存のリソース メールボックスを変更している場合:</span><span class="sxs-lookup"><span data-stu-id="0d6dc-120">If you are changing an existing resource mailbox:</span></span>

```
Set-Mailbox -Identity 'TEAMS01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

<span data-ttu-id="0d6dc-121">新しいリソース メールボックスを作成している場合:</span><span class="sxs-lookup"><span data-stu-id="0d6dc-121">If you’re creating a new resource mailbox:</span></span>

```
New-Mailbox -MicrosoftOnlineServicesID TEAMS01@contoso.com -Alias TEAMS01 
-Name "Teams-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword
 (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

<span data-ttu-id="0d6dc-122">3\。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-122">3\.</span></span> <span data-ttu-id="0d6dc-123">会議エクスペリエンスを改善するために、さまざまな Exchange プロパティをデバイス アカウントに設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-123">Various Exchange properties must be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="0d6dc-124">設定する必要のあるプロパティは、「Exchange のプロパティ」セクションで確認できます。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-124">You can see which properties need to be set in the Exchange properties section.</span></span>

```
Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false
 -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
```

<span data-ttu-id="0d6dc-125">4\。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-125">4\.</span></span> <span data-ttu-id="0d6dc-126">Azure Active Directory に接続して、アカウント設定をいくつか適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-126">You will need to connect to Azure Active Directory to apply some account settings.</span></span> <span data-ttu-id="0d6dc-127">Azure AD に接続するには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-127">To connect to Azure AD, run the following cmdlet:</span></span>

```
Connect-MsolService -Credential $cred
```

<span data-ttu-id="0d6dc-128">5\。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-128">5\.</span></span> <span data-ttu-id="0d6dc-129">	パスワードを無期限にする場合は、次のように Set-MsolUser コマンドレットに PasswordNeverExpires オプションを付けて実行します。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-129">If you do not want the password to expire, run the Set-MsolUser cmdlet with the PasswordNeverExpires option as follows:</span></span> 

```
Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
```

<span data-ttu-id="0d6dc-130">次のように、会議室の電話番号を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-130">You can also set a phone number for the room as follows:</span></span>

```
Set-MsolUser -UniversalPrincipalName <upn> -PhoneNumber <phone number>
```

<span data-ttu-id="0d6dc-131">6\。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-131">6\.</span></span> <span data-ttu-id="0d6dc-132">デバイスのアカウントは、有効な Office 365 のライセンスでは、する必要があるか、Exchange およびビジネス用の Skype は機能しません。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-132">The device account needs to have a valid Office 365 license, or Exchange and Skype for Business will not work.</span></span> <span data-ttu-id="0d6dc-133">ライセンスがあれば、利用場所を割り当てる、デバイスのアカウントにする必要があります-どのようなライセンスは、アカウントの利用可能な決定します。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-133">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="0d6dc-134">Get MsolAccountSku を使用して、次のように、Office 365 テナントの使用可能な Sku の一覧を取得できます。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-134">You can use Get-MsolAccountSku to retrieve a list of available SKUs for your Office 365 tenant as follows:</span></span>
 
```
Get-MsolAccountSku
```

<span data-ttu-id="0d6dc-p109">次に、Set-MsolUserLicense コマンドレットを使用して、ライセンスを追加することができます。この場合、表示される SKU コードは $strLicense です (たとえば、contoso:STANDARDPACK)。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-p109">Next, you can add a license using the Set-MsolUserLicense cmdlet. In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

```
Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
Get-MsolAccountSku
Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
```

<span data-ttu-id="0d6dc-137">7\。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-137">7\.</span></span> <span data-ttu-id="0d6dc-138">次に、サーフェスのハブのチームを持つデバイスのアカウントを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-138">Next, you need to enable the device account with Teams for Surface Hub.</span></span> <span data-ttu-id="0d6dc-139">お客様の環境は、 [Microsoft Surface ハブ管理者ガイド 』](https://docs.microsoft.com/surface-hub/)で定義されている要件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-139">Be sure your environment meets the requirements defined in [Microsoft Surface Hub admin guide](https://docs.microsoft.com/surface-hub/).</span></span>

<span data-ttu-id="0d6dc-140">次のように、リモートの Windows PowerShell セッションを開始 (オンライン PowerShell のビジネス コンポーネントの Skype をインストールすることを確認する)。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-140">Start a remote Windows PowerShell session as follows (be sure to install Skype for Business Online PowerShell components):</span></span>

```
Import-Module LyncOnlineConnector
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

<span data-ttu-id="0d6dc-141">次に、次のコマンドレットを実行して、サーフェスのハブのアカウントに、チームを有効にします。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-141">Next, enable your Teams for Surface Hub account by running the following cmdlet:</span></span>

```
Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
```

<span data-ttu-id="0d6dc-142">次の使用例に示すように、新しいユーザー アカウントのセットアップの中から RegistrarPool 情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-142">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

```
Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
```

> [!NOTE]
> <span data-ttu-id="0d6dc-143">テナント内の既存のユーザー アカウントとして同じレジストラー プールに新しいユーザー アカウントを作成できません可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-143">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="0d6dc-144">上記のコマンドは、このような状況が発生したため、アカウントのセットアップでエラーをできなくなります。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-144">The command above will prevent errors in account setup due to this situation.</span></span> 

<span data-ttu-id="0d6dc-145">サーフェスのハブのアカウントに、チームを有効にするのには、上記の手順を完了した後は、サーフェスのハブ v2 デバイスにライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-145">After you've completed the preceding steps to enable your Teams for Surface Hub account, you need to assign a license to the Surface Hub v2 device.</span></span> <span data-ttu-id="0d6dc-146">Office 365 管理ポータルを使用して、デバイスに、チームでのサーフェスのハブのライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-146">Using the Office 365 administrative portal, assign a Teams for Surface Hub license to the device.</span></span>

### <a name="assign-a-license-to-the-account"></a><span data-ttu-id="0d6dc-147">アカウントにライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-147">Assign a license to the account</span></span>

1. <span data-ttu-id="0d6dc-148">テナント管理者としてログオンし、Office 365 管理センターで、開き [管理アプリケーション] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-148">Log on as a tenant administrator, open the Office 365 admin center, and click on the Admin app.</span></span>
2. <span data-ttu-id="0d6dc-149">**ユーザーとグループ**をクリックし、**ユーザーの追加、パスワードのリセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-149">Click **Users and Groups**, and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="0d6dc-150">サーフェスのハブのアカウント チームを選択しを手段の編集 [ペン] アイコンをタップします。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-150">Select the Teams for Surface Hub account, and then click or tap the pen icon, which means edit.</span></span>
4. <span data-ttu-id="0d6dc-151">**ライセンス**オプションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-151">Click the **Licenses** option.</span></span>
5. <span data-ttu-id="0d6dc-152">[**ライセンスの割り当て**] セクションで、ライセンスによって、プランを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-152">In the **Assign licenses** section, you need to select the plan, depending on your licensing.</span></span>
6. <span data-ttu-id="0d6dc-153">タスクを完了するには、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-153">Click **Save** to complete the task.</span></span>

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a><span data-ttu-id="0d6dc-154">Microsoft ストアからのサーフェスのハブのチームをインストールします。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-154">Install Teams for Surface Hub from the Microsoft Store</span></span> 

<span data-ttu-id="0d6dc-155">これらは、Microsoft ストアからのサーフェスのハブのチームをインストールします。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-155">These instructions are for installing Teams for Surface Hub from the Microsoft Store.</span></span> 
 
1. <span data-ttu-id="0d6dc-156">マイクロソフトのストアを開始します。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-156">Start the Microsoft Store:</span></span><br>
   <span data-ttu-id="0d6dc-157">a.</span><span class="sxs-lookup"><span data-stu-id="0d6dc-157">a.</span></span> <span data-ttu-id="0d6dc-158">**スタート**をタップして > **すべてのアプリケーション** > **の設定**です。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-158">Tap **Start** > **All Apps** > **Settings**.</span></span><br> <span data-ttu-id="0d6dc-159">b.</span><span class="sxs-lookup"><span data-stu-id="0d6dc-159">b.</span></span> <span data-ttu-id="0d6dc-160">**サーフェス ハブ デバイスのアカウント、管理**をタップします。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-160">Tap **Surface Hub Device account, management**.</span></span><br>
   <span data-ttu-id="0d6dc-161">c.</span><span class="sxs-lookup"><span data-stu-id="0d6dc-161">c.</span></span> <span data-ttu-id="0d6dc-162">左側の [**アプリケーションと機能**] タブをタップします。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-162">On the left, tap the **Apps & Features** tab.</span></span><br> <span data-ttu-id="0d6dc-163">d.</span><span class="sxs-lookup"><span data-stu-id="0d6dc-163">d.</span></span> <span data-ttu-id="0d6dc-164">、右側には、**ストアを開く**] ボタンをタップします。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-164">On the right, tap the **Open Store** button.</span></span> 
2. <span data-ttu-id="0d6dc-165">マイクロソフト ストアからには、*マイクロソフトのチーム*を検索します。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-165">From the Microsoft Store, search for *Microsoft Teams*.</span></span> <span data-ttu-id="0d6dc-166">**サーフェスのハブのマイクロソフトのチーム**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-166">The **Microsoft Teams for Surface Hub** will be displayed.</span></span> <span data-ttu-id="0d6dc-167">インストールする**アプリケーションを取得する**ボタンをタップします。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-167">Tap the **Get the app** button to install.</span></span>  
3. <span data-ttu-id="0d6dc-168">インストールが完了すると、サーフェスのハブを再起動します。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-168">When the installation is complete, restart the Surface Hub.</span></span> 

> [!NOTE]
> <span data-ttu-id="0d6dc-169">ページを一覧表示するストアからの**起動**をタップしないようにします。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-169">Do not tap on **Launch** from the Store listing page.</span></span>

## <a name="make-teams-the-default-calling-and-meetings-application"></a><span data-ttu-id="0d6dc-170">デフォルトの通話や会議アプリケーションは、チームを作成します。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-170">Make Teams the default calling and meetings application</span></span>
 
<span data-ttu-id="0d6dc-171">通話や会議アプリケーションの既定ポリシーを構成するための 2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-171">There are two options for configuring the default calling and meetings application policy:</span></span> 

- <span data-ttu-id="0d6dc-172">**オプション 1**: USB キーを使用して構成します。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-172">**Option 1**: Configure via USB key.</span></span> 
- <span data-ttu-id="0d6dc-173">**オプション 2**: Intune などの MDM を使用して構成します。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-173">**Option 2**: Configure via MDM such as Intune.</span></span>
 
### <a name="option-1-configure-via-usb-key"></a><span data-ttu-id="0d6dc-174">オプション 1: は、USB キーを使用して構成します。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-174">Option 1: Configure via USB key</span></span> 
 
<span data-ttu-id="0d6dc-175">この[ダウンロード ページ](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g)で、パッケージをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-175">The packages can be found on this [download page](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g).</span></span> <span data-ttu-id="0d6dc-176">適切なパッケージをインストールし、USB キーにコピーする予定しているを選択します。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-176">Pick the appropriate one for the package that you're planning to install and copy it to a USB key.</span></span> <span data-ttu-id="0d6dc-177">正しい .ppkg ファイルを使用するのには、次のように適用するにはアプリケーションの既定のポリシーによって異なります。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-177">The correct .ppkg file to use depends on the default application policy you'd like to apply as follows:</span></span> 

|<span data-ttu-id="0d6dc-178">数値</span><span class="sxs-lookup"><span data-stu-id="0d6dc-178">Number</span></span>  |<span data-ttu-id="0d6dc-179">説明</span><span class="sxs-lookup"><span data-stu-id="0d6dc-179">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="0d6dc-180">0</span><span class="sxs-lookup"><span data-stu-id="0d6dc-180">0</span></span>     | <span data-ttu-id="0d6dc-181">[開始] 画面で [チームの会議が利用可能な Skype 優先のアプリケーション</span><span class="sxs-lookup"><span data-stu-id="0d6dc-181">Skype preferred app on the Start Screen, Teams Meetings available</span></span>        |
|<span data-ttu-id="0d6dc-182">1</span><span class="sxs-lookup"><span data-stu-id="0d6dc-182">1</span></span>     | <span data-ttu-id="0d6dc-183">チーム優先のアプリケーション起動画面で、利用可能な Skype の会議</span><span class="sxs-lookup"><span data-stu-id="0d6dc-183">Teams preferred app on the Start Screen, Skype Meetings available</span></span>        |
|<span data-ttu-id="0d6dc-184">2</span><span class="sxs-lookup"><span data-stu-id="0d6dc-184">2</span></span>     | <span data-ttu-id="0d6dc-185">チームの排他的なアプリケーション (Skype アプリが利用できない) の開始画面</span><span class="sxs-lookup"><span data-stu-id="0d6dc-185">Teams exclusive app on the Start screen (Skype app not available)</span></span>        |
 
1. <span data-ttu-id="0d6dc-186">サーフェス ハブ デバイスに USB キーを接続します。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-186">Attach the USB key to the Surface Hub device.</span></span> 
2. <span data-ttu-id="0d6dc-187">サーフェス ハブ デバイスの**設定**アプリを開きます。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-187">Open the **Settings** app on a Surface Hub device.</span></span> 
3. <span data-ttu-id="0d6dc-188">**表面ハブ デバイスのアカウントの管理**を開きます。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-188">Open **Surface Hub Device Account Management**.</span></span>
4. <span data-ttu-id="0d6dc-189">**デバイスの管理**を開きます。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-189">Open **Device Management**.</span></span> 
5. <span data-ttu-id="0d6dc-190">**追加またはプロビジョニング ・ パッケージを削除する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-190">Click **Add or Remove a provisioning package**.</span></span> 
6. <span data-ttu-id="0d6dc-191">**パッケージの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-191">Click **Add Package**.</span></span>
7. <span data-ttu-id="0d6dc-192">ドロップ ダウン メニューから、[**リムーバブル メディア**] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-192">Select the **Removable Media** option from the drop-down menu.</span></span> 
8. <span data-ttu-id="0d6dc-193">以前、USB キーにコピーされた適切な**TeamsRTMMode\*.ppkg**パッケージを追加します。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-193">Add the appropriate **TeamsRTMMode\*.ppkg** package that was previously copied to the USB key.</span></span> 
9. <span data-ttu-id="0d6dc-194">サーフェス ハブ デバイスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-194">Restart the Surface Hub device.</span></span> 
10. <span data-ttu-id="0d6dc-195">デバイスを再起動した後は、開始画面から、チームのアプリケーションを起動し、カレンダーから会議に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-195">After the device restarts, you should be able to start the Teams app from the Start screen and join a meeting from the calendar.</span></span> 

### <a name="option-2-configure-via-mdm-such-as-intune"></a><span data-ttu-id="0d6dc-196">Intune などの MDM を使用してオプション 2: を構成します。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-196">Option 2: Configure via MDM such as Intune</span></span> 

<span data-ttu-id="0d6dc-197">Intune を使用して既定の通話や会議のアプリケーション ポリシーを構成するのにには、次を使用します。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-197">Use the following to configure the default calling and meetings application policy via Intune.</span></span>

|<span data-ttu-id="0d6dc-198">設定</span><span class="sxs-lookup"><span data-stu-id="0d6dc-198">Setting</span></span>   |<span data-ttu-id="0d6dc-199">値</span><span class="sxs-lookup"><span data-stu-id="0d6dc-199">Value</span></span>    |<span data-ttu-id="0d6dc-200">説明</span><span class="sxs-lookup"><span data-stu-id="0d6dc-200">Description</span></span>    |
|----------|---------|---------|
|<span data-ttu-id="0d6dc-201"> Path</span><span class="sxs-lookup"><span data-stu-id="0d6dc-201">Path</span></span>      | <span data-ttu-id="0d6dc-202">./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode</span><span class="sxs-lookup"><span data-stu-id="0d6dc-202">./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode</span></span>        |
|<span data-ttu-id="0d6dc-203">データ型</span><span class="sxs-lookup"><span data-stu-id="0d6dc-203">Data Type</span></span> | <span data-ttu-id="0d6dc-204">整数 (0-2)</span><span class="sxs-lookup"><span data-stu-id="0d6dc-204">integer (0-2)</span></span>   |<span data-ttu-id="0d6dc-205">0 - [開始] 画面で [チームの会議が利用可能な Skype 優先のアプリケーション</span><span class="sxs-lookup"><span data-stu-id="0d6dc-205">0 - Skype preferred app on the Start Screen, Teams Meetings available</span></span><br><span data-ttu-id="0d6dc-206">1 のチーム開始画面で、Skype の会議が利用可能なアプリケーションを優先します。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-206">1 - Teams preferred app on the Start Screen, Skype Meetings available</span></span><br><span data-ttu-id="0d6dc-207">2-チームは、開始画面 (Skype アプリケーションではありません排他的なアプリケーション</span><span class="sxs-lookup"><span data-stu-id="0d6dc-207">2 - Teams exclusive app on the Start screen (Skype app not available)</span></span> |
|<span data-ttu-id="0d6dc-208">運用</span><span class="sxs-lookup"><span data-stu-id="0d6dc-208">Operations</span></span>| <span data-ttu-id="0d6dc-209">取得、設定</span><span class="sxs-lookup"><span data-stu-id="0d6dc-209">Get, Set</span></span>        |

|<span data-ttu-id="0d6dc-210">設定</span><span class="sxs-lookup"><span data-stu-id="0d6dc-210">Setting</span></span>   |<span data-ttu-id="0d6dc-211">値</span><span class="sxs-lookup"><span data-stu-id="0d6dc-211">Value</span></span>    |
|----------|---------|
|<span data-ttu-id="0d6dc-212"> Path</span><span class="sxs-lookup"><span data-stu-id="0d6dc-212">Path</span></span>      | <span data-ttu-id="0d6dc-213">./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId</span><span class="sxs-lookup"><span data-stu-id="0d6dc-213">./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId</span></span>        |
|<span data-ttu-id="0d6dc-214">データ型</span><span class="sxs-lookup"><span data-stu-id="0d6dc-214">Data Type</span></span> | <span data-ttu-id="0d6dc-215">文字列 - **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe としてチームのアプリケーション パッケージ ID に文字列を設定します。チーム**</span><span class="sxs-lookup"><span data-stu-id="0d6dc-215">string - set string to Teams application package ID as **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams**</span></span> |
|<span data-ttu-id="0d6dc-216">運用</span><span class="sxs-lookup"><span data-stu-id="0d6dc-216">Operations</span></span>| <span data-ttu-id="0d6dc-217">取得、設定</span><span class="sxs-lookup"><span data-stu-id="0d6dc-217">Get, Set</span></span>        |

<span data-ttu-id="0d6dc-218">サーフェス ハブ デバイスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-218">Restart the Surface Hub device.</span></span> <span data-ttu-id="0d6dc-219">デバイスを再起動した後は、開始画面から、チームのアプリケーションを起動し、カレンダーから会議に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-219">After the device restarts, you should be able to start the Teams app from the Start screen and join a meeting from the calendar.</span></span>

> [!NOTE]
> <span data-ttu-id="0d6dc-220">デバイスや、組織のデバイスは、現在 Windows 内部からのプログラムの一部と全般的なデータ保護規制 (GDPR) で対象となる国では (または基本の遠隔測定の設定を手動で変更がある) 場合は、チェックする必要があります再します。有効に完全な遠隔測定を内部からプログラムに参加する前にします。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-220">If your device or your organization's devices are not currently part of the Windows Insider Program and you are in countries covered by General Data Protection Regulation (GDPR) (or you have manually changed your telemetry settings to Basic), then you must re-check that you have permitted full telemetry before you join the Insider Program.</span></span> <span data-ttu-id="0d6dc-221">GDPR は、基本的な遠隔測定を設定するのには、EU 内のサーフェスのハブ デバイスの既定の動作を変更します。</span><span class="sxs-lookup"><span data-stu-id="0d6dc-221">GDPR changed the default behavior of Surface Hub devices in the EU to set telemetry to Basic.</span></span>
