---
title: チームのアドオンライセンスをユーザーに割り当てる
author: LanaChin
ms.author: v-lanac
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
description: 電話会議、電話システム、通話プランなどの機能をユーザーに割り当てる方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9c7c455628f7595e1517fbd0cef8d2edc454ffbb
ms.sourcegitcommit: 09ff11f8e4f6a93cedc34a5d732a133163df79a0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44042777"
---
# <a name="assign-teams-add-on-licenses-to-users"></a><span data-ttu-id="1d0db-103">チームのアドオンライセンスをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="1d0db-103">Assign Teams add-on licenses to users</span></span>

<span data-ttu-id="1d0db-104">アドオンライセンスは、電話会議、電話システム、通話プランなどの特定のチーム機能のライセンスです。</span><span class="sxs-lookup"><span data-stu-id="1d0db-104">Add-on licenses are licenses for specific Teams features such as Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="1d0db-105">この記事では、個々のユーザーと、大量のユーザーにアドオンライセンスを割り当てる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1d0db-105">This article describes how to assign add-on licenses to individual users and to large sets of users in bulk.</span></span>

> [!NOTE]
> <span data-ttu-id="1d0db-106">アドオンライセンスで利用できる Teams の[アドオンライセンス](microsoft-teams-add-on-licensing.md)については、こちらをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1d0db-106">See [Teams add-on licensing](microsoft-teams-add-on-licensing.md) for Teams features that are available with add-on licenses.</span></span> <span data-ttu-id="1d0db-107">また、購入する必要があるライセンスと購入方法 (プランによって異なります) についての情報が表示されるので、ユーザーは電話会議、無料電話番号、組織外の電話番号への通話機能などの機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="1d0db-107">You'll also find information about what licenses you need to buy and how to buy them (depending on your plan), so users can get features such as Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your organization.</span></span> <span data-ttu-id="1d0db-108">ユーザーに必要な機能を決定したら、ライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="1d0db-108">After you decide  which features you want for your users, assign the licenses to them.</span></span>

<span data-ttu-id="1d0db-109">Microsoft 365 管理センターまたは PowerShell を使用して、組織内のユーザーにライセンスを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="1d0db-109">You can use the Microsoft 365 admin center or PowerShell to assign licenses to users in your organization.</span></span> <span data-ttu-id="1d0db-110">ライセンスを管理するには、グローバル管理者またはユーザー管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d0db-110">You must be a Global admin or User management admin to manage licenses.</span></span>

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a><span data-ttu-id="1d0db-111">電話システム、通話プラン、および通信クレジットライセンスを割り当てる前に知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="1d0db-111">What you need to know before you assign Phone System, Calling Plan, and Communication Credits licenses</span></span>

<span data-ttu-id="1d0db-112">始める前に、次のことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="1d0db-112">Before you get started, review the following:</span></span>

- <span data-ttu-id="1d0db-113">ハイブリッドユーザー用にオンプレミスの公衆交換電話網 (PSTN) 接続を使用している場合は、電話システムのライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d0db-113">If you're using on-premises Public Switched Telephone Network (PSTN) connectivity for hybrid users, you only need to assign a Phone System license.</span></span> <span data-ttu-id="1d0db-114">通話プランライセンスを割り当てないでください。</span><span class="sxs-lookup"><span data-stu-id="1d0db-114">Do NOT assign a Calling Plan license.</span></span>

- <span data-ttu-id="1d0db-115">Microsoft 365 と Microsoft Teams の間の待機時間のため、ライセンスを割り当てた後にユーザーが通話プランを割り当てられるまでに最大24時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="1d0db-115">Because of the latency between Microsoft 365 and Microsoft Teams, it can take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="1d0db-116">24時間経過してもユーザーが通話プランを割り当てられていない場合は、[ビジネス製品のサポートにお問い合わせください。管理者向けヘルプ](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。</span><span class="sxs-lookup"><span data-stu-id="1d0db-116">If the user isn't assigned a Calling Plan after 24 hours, [contact support for business products - admin help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="1d0db-117">適切な数のライセンスを購入していない場合は、エラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1d0db-117">You'll get an error message if you haven't purchased the correct number of licenses.</span></span> <span data-ttu-id="1d0db-118">追加の通話プランライセンスを購入する必要がある場合は、[追加購入] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="1d0db-118">If you need to buy more Calling Plan licenses, choose the option to buy more.</span></span>

- <span data-ttu-id="1d0db-119">ユーザーに Enterprise E5 ライセンスが割り当てられている場合でも、PSTN から通話を発信または受信する場合は、そのユーザーに[通信クレジット](../what-are-communications-credits.md)ライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d0db-119">Even if your users are assigned Enterprise E5 licenses, you still need to assign [Communications Credits](../what-are-communications-credits.md) licenses to them if they want make or receive calls from the PSTN.</span></span>

- <span data-ttu-id="1d0db-120">通話プランまたは通信クレジットのライセンスをユーザーに割り当てた後、組織の電話番号を取得して、それらの電話番号をユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d0db-120">After you assign Calling Plan or Communication Credits licenses to your users, you'll need to get phone numbers for your organization, and then assign those numbers to users.</span></span> <span data-ttu-id="1d0db-121">詳しい手順については、「[通話プランのセットアップ](../set-up-calling-plans.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1d0db-121">For step-by-step instructions, see [Set up Calling Plans](../set-up-calling-plans.md).</span></span>

## <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="1d0db-122">Microsoft 365 管理センターを使用する</span><span class="sxs-lookup"><span data-stu-id="1d0db-122">Using the Microsoft 365 admin center</span></span>

<span data-ttu-id="1d0db-123">Microsoft 365 管理センターを使用して、個々のユーザーまたは少数のユーザーのライセンスを一度に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="1d0db-123">Use the Microsoft 365 admin center to assign licenses to individual users or small sets of users at a time.</span></span> <span data-ttu-id="1d0db-124">[**ライセンス**] ページ (一度に最大20人) または [**アクティブなユーザー** ] ページでライセンスを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="1d0db-124">You can assign licenses on the **Licenses** page (for up to 20 users at a time) or the **Active users** page.</span></span> <span data-ttu-id="1d0db-125">選択する方法は、特定のユーザーの製品ライセンスを管理するか、特定の製品のユーザーライセンスを管理するかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="1d0db-125">The method you choose depends on whether you want to manage product licenses for specific users or manage user licenses for specific products.</span></span> 

<span data-ttu-id="1d0db-126">詳細な手順については、「[ユーザーにライセンスを割り当てる](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d0db-126">For step-by-step instructions, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

<span data-ttu-id="1d0db-127">数百または数千のユーザーなどの多数のユーザーのライセンスを割り当てる必要がある場合は、 [Azure Active Directory (AZURE AD) で Powershell またはグループベースのライセンス](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)を使用します。</span><span class="sxs-lookup"><span data-stu-id="1d0db-127">If you need to assign licenses for a large number of users, such as hundreds or thousands of users, use Powershell or [group-based licensing in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>  

## <a name="using-powershell"></a><span data-ttu-id="1d0db-128">PowerShell を使用する場合</span><span class="sxs-lookup"><span data-stu-id="1d0db-128">Using PowerShell</span></span>

<span data-ttu-id="1d0db-129">PowerShell を使用して、ユーザーにライセンスをまとめて割り当てます。</span><span class="sxs-lookup"><span data-stu-id="1d0db-129">Use PowerShell to assign licenses to users in bulk.</span></span>  <span data-ttu-id="1d0db-130">詳細については、「 [PowerShell を使用してライセンスをユーザーアカウントに割り当てる](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d0db-130">To learn more, see [Assign licenses to user accounts with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span></span>

### <a name="example-script"></a><span data-ttu-id="1d0db-131">スクリプトの例</span><span class="sxs-lookup"><span data-stu-id="1d0db-131">Example script</span></span>

<span data-ttu-id="1d0db-132">スクリプトを使用してユーザーにライセンスを割り当てる方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="1d0db-132">Here's an example of how to use a script to assign licenses to your users.</span></span>

1. <span data-ttu-id="1d0db-133">IT プロフェッショナル向けの64ビットバージョンの[Microsoft Online Services サインインアシスタントプロフェッショナル用 rtwhttp://go.microsoft.com/fwlink/?linkid=625123](https://go.microsoft.com/fwlink/p/?LinkId=286152)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="1d0db-133">Install the 64-bit version of the [Microsoft Online Services Sign-in Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/p/?LinkId=286152).</span></span>
2. <span data-ttu-id="1d0db-134">Microsoft Azure Active Directory Module for Windows PowerShell をインストールします。</span><span class="sxs-lookup"><span data-stu-id="1d0db-134">Install the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    1. <span data-ttu-id="1d0db-135">昇格した Windows PowerShell コマンドプロンプトを開きます (管理者として Windows PowerShell を実行します)。</span><span class="sxs-lookup"><span data-stu-id="1d0db-135">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an admin).</span></span>
    2. <span data-ttu-id="1d0db-136">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1d0db-136">Run the following command:</span></span>
        ```powershell
        Install-Module MSOnline
        ```
    3. <span data-ttu-id="1d0db-137">NuGet プロバイダーをインストールするかどうかを確認するメッセージが表示されたら、「 **Y**」と入力して、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="1d0db-137">If you're prompted to install the NuGet provider, type **Y**, and then press Enter.</span></span>
    4. <span data-ttu-id="1d0db-138">PSGallery からモジュールをインストールするかどうかを確認するメッセージが表示されたら、「 **Y**」と入力して、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="1d0db-138">If you're prompted to install the module from PSGallery, type **Y**, and then press Enter.</span></span>
3. <span data-ttu-id="1d0db-139">Windows PowerShell コマンドプロンプトで、次のスクリプトを実行してライセンスをユーザーに割り当てます\<。ここで、CompanyName: License> は組織名と、割り当てるライセンスの識別子です。</span><span class="sxs-lookup"><span data-stu-id="1d0db-139">At the Windows PowerShell command prompt, run the following script to assign licenses to your users, where \<CompanyName:License> is your organization name and the identifier for the license that you want to assign.</span></span> <span data-ttu-id="1d0db-140">たとえば、litwareinc: MCOMEETADV のようになります。</span><span class="sxs-lookup"><span data-stu-id="1d0db-140">For example, litwareinc:MCOMEETADV.</span></span>

    <span data-ttu-id="1d0db-141">この識別子は、ライセンスのフレンドリ名とは異なります。</span><span class="sxs-lookup"><span data-stu-id="1d0db-141">The identifier is different than the friendly name of the license.</span></span> <span data-ttu-id="1d0db-142">たとえば、電話会議の識別子は MCOMEETADV です。</span><span class="sxs-lookup"><span data-stu-id="1d0db-142">For example, the identifier for Audio Conferencing is MCOMEETADV.</span></span> <span data-ttu-id="1d0db-143">詳細については、「[ライセンスの製品名と SKU 識別子](#product-names-and-sku-identifiers-for-licensing)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d0db-143">To learn more, see [Product names and SKU identifiers for licensing](#product-names-and-sku-identifiers-for-licensing).</span></span>

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

    <span data-ttu-id="1d0db-144">たとえば、Microsoft 365 のエンタープライズ1ライセンスと電話会議ライセンスを割り当てるには、スクリプトで次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="1d0db-144">For example, to assign Microsoft 365 Enterprise 1 and Audio Conferencing licenses, use the following syntax in the script:</span></span>

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    <span data-ttu-id="1d0db-145">Microsoft ビジネスボイス (通話プランなし) ライセンスを割り当てるには、スクリプトで次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="1d0db-145">To assign a Microsoft Business Voice (without Calling Plan) license, use the following syntax in the script:</span></span>

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:BUSINESS_VOICE_DIRECTROUTING" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a><span data-ttu-id="1d0db-146">ライセンスの製品名と SKU 識別子</span><span class="sxs-lookup"><span data-stu-id="1d0db-146">Product names and SKU identifiers for licensing</span></span>

<span data-ttu-id="1d0db-147">PowerShell を使用して Teams でライセンスを管理する場合に参照として使用できる製品名と、それに対応する SKU 部分名の一部を次に示します。</span><span class="sxs-lookup"><span data-stu-id="1d0db-147">Here's a partial list of product names and their corresponding SKU part names that you can use as a reference when you use PowerShell to manage licenses in Teams.</span></span>

<span data-ttu-id="1d0db-148">詳細については、「 [PowerShell を使用したライセンスとサービスの表示](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)、[製品名とライセンスのサービス計画識別子](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)、および[教育 SKU リファレンス](../sku-reference-edu.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d0db-148">To learn more, see [View licenses and services with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell), [Product names and service plan identifiers for licensing](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference), and [Education SKU reference](../sku-reference-edu.md).</span></span>

| <span data-ttu-id="1d0db-149">製品名</span><span class="sxs-lookup"><span data-stu-id="1d0db-149">Product name</span></span>| <span data-ttu-id="1d0db-150">SKU 部品名</span><span class="sxs-lookup"><span data-stu-id="1d0db-150">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="1d0db-151">Microsoft Enterprise E5 (電話システムあり)</span><span class="sxs-lookup"><span data-stu-id="1d0db-151">Microsoft Enterprise E5 (with Phone System)</span></span> | <span data-ttu-id="1d0db-152">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="1d0db-152">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="1d0db-153">Microsoft Enterprise E5 (電話会議なし)</span><span class="sxs-lookup"><span data-stu-id="1d0db-153">Microsoft Enterprise E5 (without Audio Conferencing)</span></span> | <span data-ttu-id="1d0db-154">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="1d0db-154">ENTERPRISEPREMIUM_NOPSTNCONF</span></span> |
| <span data-ttu-id="1d0db-155">Microsoft Enterprise E5 (電話会議あり)</span><span class="sxs-lookup"><span data-stu-id="1d0db-155">Microsoft Enterprise E5 (with Audio Conferencing)</span></span> | <span data-ttu-id="1d0db-156">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="1d0db-156">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="1d0db-157">Microsoft Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="1d0db-157">Microsoft Enterprise E3</span></span> | <span data-ttu-id="1d0db-158">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="1d0db-158">ENTERPRISEPACK</span></span> |
| <span data-ttu-id="1d0db-159">Microsoft Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="1d0db-159">Microsoft Enterprise E1</span></span> | <span data-ttu-id="1d0db-160">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="1d0db-160">STANDARDPACK</span></span> |
| <span data-ttu-id="1d0db-161">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="1d0db-161">Microsoft 365 Business Basic</span></span> | <span data-ttu-id="1d0db-162">O365_BUSINESS_ESSENTIALS</span><span class="sxs-lookup"><span data-stu-id="1d0db-162">O365_BUSINESS_ESSENTIALS</span></span>|
| <span data-ttu-id="1d0db-163">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="1d0db-163">Microsoft 365 Business Standard</span></span> | <span data-ttu-id="1d0db-164">O365_BUSINESS_PREMIUM</span><span class="sxs-lookup"><span data-stu-id="1d0db-164">O365_BUSINESS_PREMIUM</span></span>|
| <span data-ttu-id="1d0db-165">Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="1d0db-165">Microsoft 365 Business</span></span> | <span data-ttu-id="1d0db-166">リード</span><span class="sxs-lookup"><span data-stu-id="1d0db-166">SPB</span></span>|
| <span data-ttu-id="1d0db-167">Microsoft ビジネス Voip (カナダ)</span><span class="sxs-lookup"><span data-stu-id="1d0db-167">Microsoft Business Voice (Canada)</span></span>| <span data-ttu-id="1d0db-168">BUSINESS_VOICE_MED</span><span class="sxs-lookup"><span data-stu-id="1d0db-168">BUSINESS_VOICE_MED</span></span>  |
| <span data-ttu-id="1d0db-169">Microsoft ビジネス Voip (英国)</span><span class="sxs-lookup"><span data-stu-id="1d0db-169">Microsoft Business Voice (United Kingdom)</span></span> | <span data-ttu-id="1d0db-170">BUSINESS_VOICE</span><span class="sxs-lookup"><span data-stu-id="1d0db-170">BUSINESS_VOICE</span></span>  |
| <span data-ttu-id="1d0db-171">Microsoft ビジネス Voip (米国)</span><span class="sxs-lookup"><span data-stu-id="1d0db-171">Microsoft Business Voice (United States)</span></span> | <span data-ttu-id="1d0db-172">BUSINESS_VOICE_MED2</span><span class="sxs-lookup"><span data-stu-id="1d0db-172">BUSINESS_VOICE_MED2</span></span>  |
| <span data-ttu-id="1d0db-173">Microsoft ビジネスボイス (通話プランなし)</span><span class="sxs-lookup"><span data-stu-id="1d0db-173">Microsoft Business Voice (without Calling Plan)</span></span> | <span data-ttu-id="1d0db-174">BUSINESS_VOICE_DIRECTROUTING</span><span class="sxs-lookup"><span data-stu-id="1d0db-174">BUSINESS_VOICE_DIRECTROUTING</span></span>  |
| <span data-ttu-id="1d0db-175">米国の Microsoft ビジネス Voip (通話プランなし)</span><span class="sxs-lookup"><span data-stu-id="1d0db-175">Microsoft Business Voice (without Calling Plan) for the United States</span></span>| <span data-ttu-id="1d0db-176">BUSINESS_VOICE_DIRECTROUTING _MED</span><span class="sxs-lookup"><span data-stu-id="1d0db-176">BUSINESS_VOICE_DIRECTROUTING _MED</span></span> |
| <span data-ttu-id="1d0db-177">電話会議</span><span class="sxs-lookup"><span data-stu-id="1d0db-177">Audio Conferencing</span></span> | <span data-ttu-id="1d0db-178">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="1d0db-178">MCOMEETADV</span></span> | 
| <span data-ttu-id="1d0db-179">電話会議の1分あたりの料金 (プリペイド)</span><span class="sxs-lookup"><span data-stu-id="1d0db-179">Audio Conferencing Pay Per Minute (pay as you go)</span></span></br><span data-ttu-id="1d0db-180">*通信クレジットを設定して有効にする必要があります。*</span><span class="sxs-lookup"><span data-stu-id="1d0db-180">*Requires Communications Credits to be set up and enabled.*</span></span> | <span data-ttu-id="1d0db-181">MCOMEETACPEA</span><span class="sxs-lookup"><span data-stu-id="1d0db-181">MCOMEETACPEA</span></span> |
| <span data-ttu-id="1d0db-182">電話システム</span><span class="sxs-lookup"><span data-stu-id="1d0db-182">Phone System</span></span> | <span data-ttu-id="1d0db-183">MCOEV</span><span class="sxs-lookup"><span data-stu-id="1d0db-183">MCOEV</span></span> |
| <span data-ttu-id="1d0db-184">国内および国際通話プラン</span><span class="sxs-lookup"><span data-stu-id="1d0db-184">Domestic and International Calling Plan</span></span> | <span data-ttu-id="1d0db-185">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="1d0db-185">MCOPSTN2</span></span> |
| <span data-ttu-id="1d0db-186">国内通話プラン (米国/PR/月額プランの場合はユーザーあたり、1ヶ月あたり3000分、EU 諸国の場合はユーザー/月あたり1200分)</span><span class="sxs-lookup"><span data-stu-id="1d0db-186">Domestic Calling Plan (3000 minutes per user/month for US/PR/CA, 1200 minutes per user/month for EU countries)</span></span> | <span data-ttu-id="1d0db-187">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="1d0db-187">MCOPSTN1</span></span> |
| <span data-ttu-id="1d0db-188">国内通話プラン (各国のユーザー/月あたり120分)</span><span class="sxs-lookup"><span data-stu-id="1d0db-188">Domestic Calling Plan (120 minutes per user/month for each country)</span></span> </br><span data-ttu-id="1d0db-189">*このプランは、米国では利用できません。*</span><span class="sxs-lookup"><span data-stu-id="1d0db-189">*This plan isn't available in the United States.*</span></span> | <span data-ttu-id="1d0db-190">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="1d0db-190">MCOPSTN5</span></span> |
| <span data-ttu-id="1d0db-191">国内通話プラン (各国のユーザー/月あたり240分)</span><span class="sxs-lookup"><span data-stu-id="1d0db-191">Domestic Calling Plan (240 minutes per user/month for each country)</span></span> </br><span data-ttu-id="1d0db-192">*このプランは、米国では利用できません。*</span><span class="sxs-lookup"><span data-stu-id="1d0db-192">*This plan isn't available in the United States.*</span></span> | <span data-ttu-id="1d0db-193">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="1d0db-193">MCOPSTN6</span></span> |
| <span data-ttu-id="1d0db-194">コミュニケーション クレジット</span><span class="sxs-lookup"><span data-stu-id="1d0db-194">Communications Credits</span></span> | <span data-ttu-id="1d0db-195">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="1d0db-195">MCOPSTNPP</span></span> |

## <a name="related-topics"></a><span data-ttu-id="1d0db-196">関連項目</span><span class="sxs-lookup"><span data-stu-id="1d0db-196">Related topics</span></span>

- [<span data-ttu-id="1d0db-197">Teams アドオンのライセンス</span><span class="sxs-lookup"><span data-stu-id="1d0db-197">Teams add-on licensing</span></span>](microsoft-teams-add-on-licensing.md)
- [<span data-ttu-id="1d0db-198">Teams へのユーザー アクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="1d0db-198">Manage user access to Teams</span></span>](../user-access.md)
- [<span data-ttu-id="1d0db-199">PowerShell でライセンスとサービスを表示する</span><span class="sxs-lookup"><span data-stu-id="1d0db-199">View licenses and services with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [<span data-ttu-id="1d0db-200">ライセンスのための製品名とサービス プラン識別子</span><span class="sxs-lookup"><span data-stu-id="1d0db-200">Product names and service plan identifiers for licensing</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [<span data-ttu-id="1d0db-201">エデュケーション SKU リファレンス</span><span class="sxs-lookup"><span data-stu-id="1d0db-201">Education SKU reference</span></span>](../sku-reference-edu.md)