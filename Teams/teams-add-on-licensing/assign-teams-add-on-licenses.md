---
title: ユーザー Teamsアドオン ライセンスを割り当てる
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
search.appverid: MET150
f1.keywords:
- NOCSH
ms.reviewer: mikedav
description: 電話会議、通話プランTeams機能について、ユーザーにアドオン ライセンスを割り当てる電話システム説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: b30df309412d159b878b4b57655787c9b4b292a8
ms.sourcegitcommit: 5c68298474d1782e69bde8c0940be7150cb93f6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2021
ms.locfileid: "53095581"
---
# <a name="assign-teams-add-on-licenses-to-users"></a><span data-ttu-id="7e01c-103">ユーザー Teamsアドオン ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="7e01c-103">Assign Teams add-on licenses to users</span></span>

<span data-ttu-id="7e01c-104">アドオン ライセンスは、電話会議、電話会議Teams通話プランなどの特定の機能電話システムライセンスです。</span><span class="sxs-lookup"><span data-stu-id="7e01c-104">Add-on licenses are licenses for specific Teams features such as Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="7e01c-105">この記事では、アドオン ライセンスを個々のユーザーと多数のユーザーに一括で割り当てる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7e01c-105">This article describes how to assign add-on licenses to individual users and to large sets of users in bulk.</span></span>

> [!NOTE]
> <span data-ttu-id="7e01c-106">追加[Teamsライセンスで使用できる](./microsoft-teams-add-on-licensing.md)Teams機能については、「追加のアドオン ライセンス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e01c-106">See [Teams add-on licensing](./microsoft-teams-add-on-licensing.md) for Teams features that are available with add-on licenses.</span></span> <span data-ttu-id="7e01c-107">また、購入する必要があるライセンスと購入方法に関する情報も表示されます。そのため、ユーザーは電話会議、無料電話番号、組織外の電話番号に通話する機能などの機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="7e01c-107">You'll also find information about what licenses you need to buy and how to buy them (depending on your plan), so users can get features such as Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your organization.</span></span> <span data-ttu-id="7e01c-108">ユーザーに必要な機能を決定した後、ユーザーにライセンスを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="7e01c-108">After you decide  which features you want for your users, assign the licenses to them.</span></span>

<span data-ttu-id="7e01c-109">Microsoft 365 管理センター または PowerShell を使用して、組織内のユーザーにライセンスを割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="7e01c-109">You can use the Microsoft 365 admin center or PowerShell to assign licenses to users in your organization.</span></span> <span data-ttu-id="7e01c-110">ライセンスを管理するには、グローバル管理者またはユーザー管理管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e01c-110">You must be a Global admin or User management admin to manage licenses.</span></span>

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a><span data-ttu-id="7e01c-111">通話プラン、通信クレジットのライセンスを割り電話システム前に知る必要がある情報</span><span class="sxs-lookup"><span data-stu-id="7e01c-111">What you need to know before you assign Phone System, Calling Plan, and Communication Credits licenses</span></span>

<span data-ttu-id="7e01c-112">開始する前に、次の要件を確認してください。</span><span class="sxs-lookup"><span data-stu-id="7e01c-112">Before you get started, review the following requirements:</span></span>

- <span data-ttu-id="7e01c-113">ハイブリッド ユーザーに対してオンプレミスの公衆交換電話網 (PSTN) 接続を使用している場合は、ネットワーク ライセンスを割り当てる電話システムがあります。</span><span class="sxs-lookup"><span data-stu-id="7e01c-113">If you're using on-premises Public Switched Telephone Network (PSTN) connectivity for hybrid users, you only need to assign a Phone System license.</span></span> <span data-ttu-id="7e01c-114">通話プランライセンスを割り当てない。</span><span class="sxs-lookup"><span data-stu-id="7e01c-114">Do NOT assign a Calling Plan license.</span></span>

- <span data-ttu-id="7e01c-115">Microsoft 365 と Microsoft Teams の間の待機時間のため、ライセンスを割り当てた後にユーザーに通話プランが割り当てられるまで最大 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7e01c-115">Because of the latency between Microsoft 365 and Microsoft Teams, it can take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="7e01c-116">ユーザーに 24 時間後に通話プランが割り当てられていない場合は、ビジネス製品のサポート ( 管理者向けヘルプ) にお [問い合わせください](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。</span><span class="sxs-lookup"><span data-stu-id="7e01c-116">If the user isn't assigned a Calling Plan after 24 hours, [contact support for business products - admin help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="7e01c-117">正しい数のライセンスを購入していない場合は、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e01c-117">You'll get an error message if you haven't purchased the correct number of licenses.</span></span> <span data-ttu-id="7e01c-118">通話プランのライセンスを追加購入する必要がある場合は、さらに購入するオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="7e01c-118">If you need to buy more Calling Plan licenses, choose the option to buy more.</span></span>

- <span data-ttu-id="7e01c-119">ユーザーに E5 ライセンスが割り当Enterprise場合でも、PSTN から[](../what-are-communications-credits.md)通話を発信または受信する場合は、そのユーザーに通信クレジット ライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e01c-119">Even if your users are assigned Enterprise E5 licenses, you still need to assign [Communications Credits](../what-are-communications-credits.md) licenses to them if they want to make or receive calls from the PSTN.</span></span>

- <span data-ttu-id="7e01c-120">通話プランまたはコミュニケーション クレジットライセンスをユーザーに割り当てると、組織の電話番号を取得し、その番号をユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e01c-120">After you assign Calling Plan or Communication Credits licenses to your users, you'll need to get phone numbers for your organization, and then assign those numbers to users.</span></span> <span data-ttu-id="7e01c-121">詳しい手順については、「[通話プランのセットアップ](../set-up-calling-plans.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7e01c-121">For step-by-step instructions, see [Set up Calling Plans](../set-up-calling-plans.md).</span></span>

## <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="7e01c-122">コマンドを使用Microsoft 365 管理センター</span><span class="sxs-lookup"><span data-stu-id="7e01c-122">Using the Microsoft 365 admin center</span></span>

<span data-ttu-id="7e01c-123">一度Microsoft 365 管理センターユーザーまたは小規模なユーザーにライセンスを割り当てるには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="7e01c-123">Use the Microsoft 365 admin center to assign licenses to individual users or small sets of users at a time.</span></span> <span data-ttu-id="7e01c-124">ライセンスを割り当てる **には、[ライセンス**] ページ (一度に最大 20 人のユーザー) または [アクティブ なユーザー] ページ (最大 40 人のユーザー) を割り当てる必要があります。 </span><span class="sxs-lookup"><span data-stu-id="7e01c-124">You assign licenses on the **Licenses** page (for up to 20 users at a time) or the **Active users** page (for up to 40 users at a time).</span></span> <span data-ttu-id="7e01c-125">選択する方法は、特定のユーザーの製品ライセンスを管理するか、特定の製品のユーザー ライセンスを管理するかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="7e01c-125">The method you choose depends on whether you want to manage product licenses for specific users or manage user licenses for specific products.</span></span>

<span data-ttu-id="7e01c-126">詳細な手順については、「ユーザーにライセンスを割り当 [てる」を参照してください](/microsoft-365/admin/manage/assign-licenses-to-users)。</span><span class="sxs-lookup"><span data-stu-id="7e01c-126">For step-by-step instructions, see [Assign licenses to users](/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

<span data-ttu-id="7e01c-127">数百または数千人のユーザーなど、多数のユーザーにライセンスを割り当てる必要がある場合は[、Azure Active Directory (Azure AD)](/azure/active-directory/users-groups-roles/licensing-groups-assign)で PowerShell またはグループベースのライセンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="7e01c-127">If you need to assign licenses for a large number of users, such as hundreds or thousands of users, use Powershell or [group-based licensing in Azure Active Directory (Azure AD)](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>  

## <a name="using-powershell"></a><span data-ttu-id="7e01c-128">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="7e01c-128">Using PowerShell</span></span>

<span data-ttu-id="7e01c-129">PowerShell を使用して、ユーザーにライセンスを一括で割り当てる。</span><span class="sxs-lookup"><span data-stu-id="7e01c-129">Use PowerShell to assign licenses to users in bulk.</span></span>  <span data-ttu-id="7e01c-130">詳細については、「PowerShell を使用して [ユーザー アカウントにライセンスを割り当てる」を参照してください](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="7e01c-130">To learn more, see [Assign licenses to user accounts with PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span></span>

### <a name="example-script"></a><span data-ttu-id="7e01c-131">サンプル スクリプト</span><span class="sxs-lookup"><span data-stu-id="7e01c-131">Example script</span></span>

<span data-ttu-id="7e01c-132">スクリプトを使用してライセンスをユーザーに割り当てる方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="7e01c-132">Here's an example of how to use a script to assign licenses to your users.</span></span>

1. <span data-ttu-id="7e01c-133">IT プロフェッショナル向けサインイン アシスタント RTW Microsoft Online Services 64 ビット [版をインストールします](/collaborate/connect-redirect?DownloadID=59185)。</span><span class="sxs-lookup"><span data-stu-id="7e01c-133">Install the 64-bit version of the [Microsoft Online Services Sign-in Assistant for IT Professionals RTW](/collaborate/connect-redirect?DownloadID=59185).</span></span>
2. <span data-ttu-id="7e01c-134">次の手順にMicrosoft Azure Active Directory モジュールをインストールWindows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="7e01c-134">Install the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    1. <span data-ttu-id="7e01c-135">管理者特権のコマンド Windows PowerShellを開きます (管理者としてWindows PowerShellを実行します)。</span><span class="sxs-lookup"><span data-stu-id="7e01c-135">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an admin).</span></span>
    2. <span data-ttu-id="7e01c-136">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7e01c-136">Run the following command:</span></span>
        ```powershell
        Install-Module MSOnline
        ```
    3. <span data-ttu-id="7e01c-137">プロバイダーをインストールするように求めるメッセージが表示されたら **、「Y」** とNuGet Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="7e01c-137">If you're prompted to install the NuGet provider, type **Y**, and then press Enter.</span></span>
    4. <span data-ttu-id="7e01c-138">PSGallery からモジュールをインストールするように求めるメッセージが表示されたら **、「Y」と入力** し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="7e01c-138">If you're prompted to install the module from PSGallery, type **Y**, and then press Enter.</span></span>
3. <span data-ttu-id="7e01c-139">コマンド プロンプトWindows PowerShell、次のスクリプトを実行してユーザーにライセンスを割り当て、ここで、割り当てるライセンスの組織名と識別子を \<CompanyName:License> 指定します。</span><span class="sxs-lookup"><span data-stu-id="7e01c-139">At the Windows PowerShell command prompt, run the following script to assign licenses to your users, where \<CompanyName:License> is your organization name and the identifier for the license that you want to assign.</span></span> <span data-ttu-id="7e01c-140">たとえば、litwareinc:MCOMEETADV などです。</span><span class="sxs-lookup"><span data-stu-id="7e01c-140">For example, litwareinc:MCOMEETADV.</span></span>

    <span data-ttu-id="7e01c-141">識別子は、ライセンスの表示名とは異なります。</span><span class="sxs-lookup"><span data-stu-id="7e01c-141">The identifier is different than the friendly name of the license.</span></span> <span data-ttu-id="7e01c-142">たとえば、電話会議の識別子は MCOMEETADV です。</span><span class="sxs-lookup"><span data-stu-id="7e01c-142">For example, the identifier for Audio Conferencing is MCOMEETADV.</span></span> <span data-ttu-id="7e01c-143">詳細については、「ライセンスの製品 [名と SKU 識別子」を参照してください](#product-names-and-sku-identifiers-for-licensing)。</span><span class="sxs-lookup"><span data-stu-id="7e01c-143">To learn more, see [Product names and SKU identifiers for licensing](#product-names-and-sku-identifiers-for-licensing).</span></span>

    ```powershell
    #Create a text file with a single column that lists the user principal names (UPNs) of users to assign licenses to. The MSOL service uses the UPN to license user accounts.
    #Example of text file:''
    #user1@domain.com
    #user2@domain.com

    #Import Module
    ipmo MSOnline

    #Authenticate to MSOLservice
    Connect-MSOLService
    #File prompt to select the userlist txt file
    [System.Reflection.Assembly]::LoadWithPartialName("System.windows.forms") | Out-Null
      $OFD = New-Object System.Windows.Forms.OpenFileDialog
      $OFD.filter = "text files (*.*)| *.txt"
      $OFD.ShowDialog() | Out-Null
      $OFD.filename

    If ($OFD.filename -eq '')
    {
    Write-Host "You did not choose a file. Try again" -ForegroundColor White -BackgroundColor Red
    }

    #Create a variable of all users
    $users = Get-Content $OFD.filename

    #License each user in the $users variable
    foreach ($user in $users)
        {
        Write-host "Assigning License: $user"
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:<CompanyName:License>" -ErrorAction SilentlyContinue
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:<CompanyName:License>" -ErrorAction SilentlyContinue
        }
    ```

    <span data-ttu-id="7e01c-144">たとえば、1 と電話Microsoft 365 Enterpriseライセンスを割り当てるには、スクリプトで次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="7e01c-144">For example, to assign Microsoft 365 Enterprise 1 and Audio Conferencing licenses, use the following syntax in the script:</span></span>

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    <span data-ttu-id="7e01c-145">Microsoft Business Voice (通話プランなし) ライセンスを割り当てるには、スクリプトで次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="7e01c-145">To assign a Microsoft Business Voice (without Calling Plan) license, use the following syntax in the script:</span></span>

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:BUSINESS_VOICE_DIRECTROUTING" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a><span data-ttu-id="7e01c-146">ライセンスの製品名と SKU 識別子</span><span class="sxs-lookup"><span data-stu-id="7e01c-146">Product names and SKU identifiers for licensing</span></span>

<span data-ttu-id="7e01c-147">PowerShell を使用して Teams でライセンスを管理するときに参照として使用できる製品名とそれに対応する SKU パーツ名の一部を次に示します。</span><span class="sxs-lookup"><span data-stu-id="7e01c-147">Here's a partial list of product names and their corresponding SKU part names that you can use as a reference when you use PowerShell to manage licenses in Teams.</span></span>

<span data-ttu-id="7e01c-148">詳細については[、「PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)を使用したライセンスとサービスの[](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)表示」、ライセンスの製品名とサービス プラン識別子、および Education SKU リファレンスに関[するページを参照してください](../sku-reference-edu.md)。</span><span class="sxs-lookup"><span data-stu-id="7e01c-148">To learn more, see [View licenses and services with PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell), [Product names and service plan identifiers for licensing](/azure/active-directory/users-groups-roles/licensing-service-plan-reference), and [Education SKU reference](../sku-reference-edu.md).</span></span>

| <span data-ttu-id="7e01c-149">製品名</span><span class="sxs-lookup"><span data-stu-id="7e01c-149">Product name</span></span>| <span data-ttu-id="7e01c-150">SKU 部品名</span><span class="sxs-lookup"><span data-stu-id="7e01c-150">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="7e01c-151">Microsoft Enterprise E5 (電話システム)</span><span class="sxs-lookup"><span data-stu-id="7e01c-151">Microsoft Enterprise E5 (with Phone System)</span></span> | <span data-ttu-id="7e01c-152">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="7e01c-152">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="7e01c-153">Microsoft Enterprise E5 (電話会議なし)</span><span class="sxs-lookup"><span data-stu-id="7e01c-153">Microsoft Enterprise E5 (without Audio Conferencing)</span></span> | <span data-ttu-id="7e01c-154">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="7e01c-154">ENTERPRISEPREMIUM_NOPSTNCONF</span></span> |
| <span data-ttu-id="7e01c-155">Microsoft Enterprise E5 (電話会議を使用)</span><span class="sxs-lookup"><span data-stu-id="7e01c-155">Microsoft Enterprise E5 (with Audio Conferencing)</span></span> | <span data-ttu-id="7e01c-156">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="7e01c-156">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="7e01c-157">Microsoft Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="7e01c-157">Microsoft Enterprise E3</span></span> | <span data-ttu-id="7e01c-158">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="7e01c-158">ENTERPRISEPACK</span></span> |
| <span data-ttu-id="7e01c-159">Microsoft Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="7e01c-159">Microsoft Enterprise E1</span></span> | <span data-ttu-id="7e01c-160">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="7e01c-160">STANDARDPACK</span></span> |
| <span data-ttu-id="7e01c-161">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="7e01c-161">Microsoft 365 Business Basic</span></span> | <span data-ttu-id="7e01c-162">O365_BUSINESS_ESSENTIALS</span><span class="sxs-lookup"><span data-stu-id="7e01c-162">O365_BUSINESS_ESSENTIALS</span></span>|
| <span data-ttu-id="7e01c-163">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="7e01c-163">Microsoft 365 Business Standard</span></span> | <span data-ttu-id="7e01c-164">O365_BUSINESS_PREMIUM</span><span class="sxs-lookup"><span data-stu-id="7e01c-164">O365_BUSINESS_PREMIUM</span></span>|
| <span data-ttu-id="7e01c-165">Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="7e01c-165">Microsoft 365 Business</span></span> | <span data-ttu-id="7e01c-166">SPB</span><span class="sxs-lookup"><span data-stu-id="7e01c-166">SPB</span></span>|
| <span data-ttu-id="7e01c-167">Microsoft Business Voice (カナダ)</span><span class="sxs-lookup"><span data-stu-id="7e01c-167">Microsoft Business Voice (Canada)</span></span>| <span data-ttu-id="7e01c-168">BUSINESS_VOICE_MED</span><span class="sxs-lookup"><span data-stu-id="7e01c-168">BUSINESS_VOICE_MED</span></span>  |
| <span data-ttu-id="7e01c-169">Microsoft Business Voice (英国)</span><span class="sxs-lookup"><span data-stu-id="7e01c-169">Microsoft Business Voice (United Kingdom)</span></span> | <span data-ttu-id="7e01c-170">BUSINESS_VOICE</span><span class="sxs-lookup"><span data-stu-id="7e01c-170">BUSINESS_VOICE</span></span>  |
| <span data-ttu-id="7e01c-171">Microsoft Business Voice (米国)</span><span class="sxs-lookup"><span data-stu-id="7e01c-171">Microsoft Business Voice (United States)</span></span> | <span data-ttu-id="7e01c-172">BUSINESS_VOICE_MED2</span><span class="sxs-lookup"><span data-stu-id="7e01c-172">BUSINESS_VOICE_MED2</span></span>  |
| <span data-ttu-id="7e01c-173">Microsoft Business Voice (通話プランなし)</span><span class="sxs-lookup"><span data-stu-id="7e01c-173">Microsoft Business Voice (without Calling Plan)</span></span> | <span data-ttu-id="7e01c-174">BUSINESS_VOICE_DIRECTROUTING</span><span class="sxs-lookup"><span data-stu-id="7e01c-174">BUSINESS_VOICE_DIRECTROUTING</span></span>  |
| <span data-ttu-id="7e01c-175">米国向け Microsoft Business Voice (通話プランなし)</span><span class="sxs-lookup"><span data-stu-id="7e01c-175">Microsoft Business Voice (without Calling Plan) for the United States</span></span>| <span data-ttu-id="7e01c-176">BUSINESS_VOICE_DIRECTROUTING _MED</span><span class="sxs-lookup"><span data-stu-id="7e01c-176">BUSINESS_VOICE_DIRECTROUTING _MED</span></span> |
| <span data-ttu-id="7e01c-177">電話会議</span><span class="sxs-lookup"><span data-stu-id="7e01c-177">Audio Conferencing</span></span> | <span data-ttu-id="7e01c-178">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="7e01c-178">MCOMEETADV</span></span> | 
| <span data-ttu-id="7e01c-179">電話会議の 1 分あたりの支払い (移動に合った支払い)</span><span class="sxs-lookup"><span data-stu-id="7e01c-179">Audio Conferencing Pay Per Minute (pay as you go)</span></span></br><span data-ttu-id="7e01c-180">*通信クレジットを設定して有効にする必要があります。*</span><span class="sxs-lookup"><span data-stu-id="7e01c-180">*Requires Communications Credits to be set up and enabled.*</span></span> | <span data-ttu-id="7e01c-181">MCOMEETACPEA</span><span class="sxs-lookup"><span data-stu-id="7e01c-181">MCOMEETACPEA</span></span> |
| <span data-ttu-id="7e01c-182">電話システム</span><span class="sxs-lookup"><span data-stu-id="7e01c-182">Phone System</span></span> | <span data-ttu-id="7e01c-183">MCOEV</span><span class="sxs-lookup"><span data-stu-id="7e01c-183">MCOEV</span></span> |
| <span data-ttu-id="7e01c-184">国内通話プランと国際通話プラン</span><span class="sxs-lookup"><span data-stu-id="7e01c-184">Domestic and International Calling Plan</span></span> | <span data-ttu-id="7e01c-185">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="7e01c-185">MCOPSTN2</span></span> |
| <span data-ttu-id="7e01c-186">国内通話プラン (米国/PR/CA の場合はユーザー/月あたり 3000 分、EU 各国の場合はユーザー/月あたり 1200 分)</span><span class="sxs-lookup"><span data-stu-id="7e01c-186">Domestic Calling Plan (3000 minutes per user/month for US/PR/CA, 1200 minutes per user/month for EU countries)</span></span> | <span data-ttu-id="7e01c-187">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="7e01c-187">MCOPSTN1</span></span> |
| <span data-ttu-id="7e01c-188">国内通話プラン (国ごとにユーザー/月あたり 120 分)</span><span class="sxs-lookup"><span data-stu-id="7e01c-188">Domestic Calling Plan (120 minutes per user/month for each country)</span></span> </br><span data-ttu-id="7e01c-189">*このプランは米国では利用できません。*</span><span class="sxs-lookup"><span data-stu-id="7e01c-189">*This plan isn't available in the United States.*</span></span> | <span data-ttu-id="7e01c-190">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="7e01c-190">MCOPSTN5</span></span> |
| <span data-ttu-id="7e01c-191">国内通話プラン (国ごとにユーザー/月あたり 240 分)</span><span class="sxs-lookup"><span data-stu-id="7e01c-191">Domestic Calling Plan (240 minutes per user/month for each country)</span></span> </br><span data-ttu-id="7e01c-192">*このプランは米国では利用できません。*</span><span class="sxs-lookup"><span data-stu-id="7e01c-192">*This plan isn't available in the United States.*</span></span> | <span data-ttu-id="7e01c-193">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="7e01c-193">MCOPSTN6</span></span> |
| <span data-ttu-id="7e01c-194">コミュニケーション クレジット</span><span class="sxs-lookup"><span data-stu-id="7e01c-194">Communications Credits</span></span> | <span data-ttu-id="7e01c-195">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="7e01c-195">MCOPSTNPP</span></span> |

## <a name="related-topics"></a><span data-ttu-id="7e01c-196">関連項目</span><span class="sxs-lookup"><span data-stu-id="7e01c-196">Related topics</span></span>

- [<span data-ttu-id="7e01c-197">Teams アドオンのライセンス</span><span class="sxs-lookup"><span data-stu-id="7e01c-197">Teams add-on licensing</span></span>](./microsoft-teams-add-on-licensing.md)
- [<span data-ttu-id="7e01c-198">Teams へのユーザー アクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="7e01c-198">Manage user access to Teams</span></span>](../user-access.md)
- [<span data-ttu-id="7e01c-199">PowerShell を使用してライセンスとサービスを表示する</span><span class="sxs-lookup"><span data-stu-id="7e01c-199">View licenses and services with PowerShell</span></span>](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [<span data-ttu-id="7e01c-200">ライセンスのための製品名とサービス プラン識別子</span><span class="sxs-lookup"><span data-stu-id="7e01c-200">Product names and service plan identifiers for licensing</span></span>](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [<span data-ttu-id="7e01c-201">Education SKU リファレンス</span><span class="sxs-lookup"><span data-stu-id="7e01c-201">Education SKU reference</span></span>](../sku-reference-edu.md)
