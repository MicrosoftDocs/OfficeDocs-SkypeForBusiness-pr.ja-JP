---
title: Microsoft 365 および Microsoft 365 および Office 365 での Skype ルーム システム アカウントのプロビジョニング
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: Microsoft 365 または Office 365 での Skype Room System アカウントのプロビジョニングについて説明します。
ms.openlocfilehash: 94390effb246a37745d797289c1146ed3d347604
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093521"
---
# <a name="provisioning-skype-room-system-accounts-in-microsoft-365-and-office-365"></a><span data-ttu-id="42a71-103">Microsoft 365 および Microsoft 365 および Office 365 での Skype ルーム システム アカウントのプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="42a71-103">Provisioning Skype Room System accounts in Microsoft 365 and Office 365</span></span>
 
<span data-ttu-id="42a71-104">Microsoft 365 または Office 365 での Skype Room System アカウントのプロビジョニングについて説明します。</span><span class="sxs-lookup"><span data-stu-id="42a71-104">Read this topic to learn about provisioning Skype Room System accounts in Microsoft 365 or Office 365.</span></span>
  
<span data-ttu-id="42a71-105">次のセクションでは、Skype Room System アカウントのプロビジョニングについて説明します。</span><span class="sxs-lookup"><span data-stu-id="42a71-105">The following section covers Skype Room System account provisioning.</span></span>
  
## <a name="microsoft-365-and-office-365-prerequisites"></a><span data-ttu-id="42a71-106">Microsoft 365 および Office 365 の前提条件</span><span class="sxs-lookup"><span data-stu-id="42a71-106">Microsoft 365 and Office 365 prerequisites</span></span>

<span data-ttu-id="42a71-107">オンライン テナントは、次の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="42a71-107">Your online tenant must meet the following requirements:</span></span>
  
- <span data-ttu-id="42a71-108">Microsoft 365 または Office 365 プランには、Skype for Business Online プラン 2、または Office 365 E1、E3、E5 が含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="42a71-108">The Microsoft 365 or Office 365 plan must include Skype for Business Online Plan 2, or Office 365 E1, E3 or E5.</span></span> <br/><span data-ttu-id="42a71-109">Skype for Business Online プランの詳細については [、「Skype for Business Online Service Description」を参照してください](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description)。</span><span class="sxs-lookup"><span data-stu-id="42a71-109">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description).</span></span>
    
- <span data-ttu-id="42a71-110">テナントで Skype for Business の会議機能が有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="42a71-110">Your tenant must have the conferencing capability of Skype for Business enabled.</span></span>
    
- <span data-ttu-id="42a71-111">テナントで Exchange Online が有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="42a71-111">Your tenant must have Exchange Online enabled.</span></span> 
    
- <span data-ttu-id="42a71-112">テナントのリモート管理者は、次の PowerShell アクセス権を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="42a71-112">Your tenant remote administrator must have the following PowerShell access:</span></span>
    
  - <span data-ttu-id="42a71-113">Exchange リモート PowerShell アクセス</span><span class="sxs-lookup"><span data-stu-id="42a71-113">Exchange Remote PowerShell access</span></span>
    
  - <span data-ttu-id="42a71-114">Skype for Business Online リモート PowerShell アクセス</span><span class="sxs-lookup"><span data-stu-id="42a71-114">Skype for Business Online Remote PowerShell access</span></span>
    
  - <span data-ttu-id="42a71-115">Microsoft 365 または 365 ディレクトリ アクセスWindows PowerShellアクセスする Windows Azure Active Directory モジュールOffice Windows Azure Active Directory モジュール</span><span class="sxs-lookup"><span data-stu-id="42a71-115">Windows Azure Active Directory Module for Windows PowerShell to access Microsoft 365 or Office 365 directory access</span></span>
    
<span data-ttu-id="42a71-116">Skype Room アカウントでは、次のライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="42a71-116">For the Skype Room account, the following licensing is required:</span></span>
  
- <span data-ttu-id="42a71-117">Skype 会議を有効にするには、Skype for Business Online プラン 2 または Office 365 E1 または E3 ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="42a71-117">A Skype for Business Online Plan 2 or Office 365 E1 or E3 license is required to enable Skype Meetings.</span></span>
    
- <span data-ttu-id="42a71-118">電話番号で部屋を有効にできるよう、エンタープライズ VoIP 機能を持つ部屋に資格を与えるには、電話システム ライセンスまたは Office 365 E5 を持つ Skype for Business Online プラン 2 が必要です (1)。</span><span class="sxs-lookup"><span data-stu-id="42a71-118">To entitle the room with the Enterprise Voice capability so the room can be enabled with a phone number, a Skype for Business Online Plan 2 with the Phone System license or Office 365 E5 is required (1).</span></span>
    
- <span data-ttu-id="42a71-119">会議からダイヤルイン機能が必要な場合は、電話会議と電話システム ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="42a71-119">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="42a71-120">会議からダイヤルアウト機能が必要な場合は、国内または国内および国際通話プランが必要です。</span><span class="sxs-lookup"><span data-stu-id="42a71-120">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span> 
    
- <span data-ttu-id="42a71-121">アカウントをリソース メールボックス アカウントとして構成する必要がある場合、Exchange Online ライセンスは Skype Room アカウントには必要ありません。</span><span class="sxs-lookup"><span data-stu-id="42a71-121">An Exchange Online license is not required for the Skype Room account because the account should be configured as a resource mailbox account.</span></span>
    
## <a name="provisioning-overview"></a><span data-ttu-id="42a71-122">プロビジョニングの概要</span><span class="sxs-lookup"><span data-stu-id="42a71-122">Provisioning overview</span></span>

<span data-ttu-id="42a71-123">次の図は、Skype Room System アカウントのプロビジョニング フローの概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="42a71-123">The following diagram provides an overview of the Skype Room System account provisioning flow.</span></span>
  
![Skype Room System Provisioning の手順](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a><span data-ttu-id="42a71-125">新しい会議室を特定する</span><span class="sxs-lookup"><span data-stu-id="42a71-125">Identify a new conference room</span></span>

<span data-ttu-id="42a71-126">スケジュール機能を提供するリソース ルーム メールボックスが Exchange に既に存在している場合や、Skype Room System の展開を容易にするためにリソース メールボックスを初めて作成する場合があります。</span><span class="sxs-lookup"><span data-stu-id="42a71-126">You may already have a resource room mailbox in Exchange that provides the scheduling feature, or you may be creating a resource mailbox for the first time to facilitate Skype Room System deployment.</span></span> <span data-ttu-id="42a71-127">いずれにしても、テナントで使用するルーム アカウントを特定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="42a71-127">In any case, you must identify a room account to be used in your tenant.</span></span> <span data-ttu-id="42a71-128">Exchange Online Provision セクションと Skype for Business Provision セクションでは、両方の種類のアカウントに関するガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="42a71-128">The Exchange Online Provision and Skype for Business Provision sections provide guidance for both kinds of accounts.</span></span> <span data-ttu-id="42a71-129">たとえば、次の 2 つのルームがある場合、両方に Skype Room System を展開するとします。</span><span class="sxs-lookup"><span data-stu-id="42a71-129">For example, let's say you have the following two rooms, and you would like to deploy Skype Room System for both of them:</span></span>
  
- <span data-ttu-id="42a71-130">既存のリソース メールボックス アカウント: confrm1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="42a71-130">Existing Resource Mailbox Account: confrm1@contoso.onmicrosoft.com</span></span>
    
- <span data-ttu-id="42a71-131">新しいリソース メールボックス アカウント: confrm2@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="42a71-131">New Resource Mailbox Account: confrm2@contoso.onmicrosoft.com</span></span>
    
## <a name="exchange-online-provisioning"></a><span data-ttu-id="42a71-132">Exchange Online プロビジョニング</span><span class="sxs-lookup"><span data-stu-id="42a71-132">Exchange Online provisioning</span></span>

<span data-ttu-id="42a71-133">最初に、「Exchange Online PowerShell に接続する」の手順に従って [Exchange Online PowerShell に接続します](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="42a71-133">First, connect to Exchange Online PowerShell by following the instructions in the topic, [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>
  
<span data-ttu-id="42a71-134">Skype Room System の既存のリソース ルーム メールボックス アカウントを設定するには、Exchange Online PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="42a71-134">To set an existing resource room mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```powershell
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="42a71-135">Skype Room System 用の新しい Exchange リソース メールボックス アカウントを作成するには、Exchange Online PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="42a71-135">To create a new Exchange resource mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```powershell
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="42a71-136">前のコマンドでは、アカウントを有効にすることで、Skype Room System の使用状況に合った新しい Exchange リソース メールボックス アカウントを設定または作成します。</span><span class="sxs-lookup"><span data-stu-id="42a71-136">The previous commands set up or create a new Exchange resource mailbox account for Skype Room System usage by enabling the account.</span></span>
  
<span data-ttu-id="42a71-137">メールボックスを作成した後、Exchange Online PowerShell の Set-CalendarProcessingコマンドレットを使用してメールボックスを構成できます。</span><span class="sxs-lookup"><span data-stu-id="42a71-137">After creating the mailbox, you can use the Set-CalendarProcessing cmdlet in Exchange Online PowerShell to configure the mailbox.</span></span> <span data-ttu-id="42a71-138">詳細については、「単一フォレストのオンプレミス展開」の手順 3 ~ 6 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42a71-138">Refer to steps 3 through 6 under Single forest on-premises deployments for more details</span></span>

## <a name="assigning-a-skype-for-business-online-license"></a><span data-ttu-id="42a71-139">Skype for Business Online ライセンスの割り当て</span><span class="sxs-lookup"><span data-stu-id="42a71-139">Assigning a Skype for Business Online license</span></span>

<span data-ttu-id="42a71-140">これで、「ビジネス向け Microsoft 365 または Skype for Business アドオン ライセンスのライセンスの割り当てまたは削除」の説明に従って [、Microsoft 365](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) 管理ポータルを使用して、Skype for Business Online (プラン 2) または [Skype for Business](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)Online (プラン 3) ライセンスを割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="42a71-140">Now you can assign a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license by using the Microsoft 365 administrative portal as described in [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) or in [Skype for Business add-on licensing](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span></span> 
  
<span data-ttu-id="42a71-141">Skype for Business Online のライセンスを割り当てると、Skype for Business クライアントを使用してアカウントがアクティブな状態でログインして検証できます。</span><span class="sxs-lookup"><span data-stu-id="42a71-141">After you assign a license for Skype for Business Online, you will be able to log in and validate that the account is active using any Skype for Business client.</span></span>
  
## <a name="skype-for-business-online-provisioning"></a><span data-ttu-id="42a71-142">Skype for Business Online プロビジョニング</span><span class="sxs-lookup"><span data-stu-id="42a71-142">Skype for Business Online provisioning</span></span>

<span data-ttu-id="42a71-143">前に示すようにリソース ルーム メールボックス アカウントを作成して有効にし、Skype For Business Online のアカウントをライセンスした後、アカウントは Windows Azure Active Directory フォレストを使用して Exchange Online フォレストから Skype for Business Online フォレストに同期します。</span><span class="sxs-lookup"><span data-stu-id="42a71-143">After a resource room mailbox account has been created and enabled as shown previously, and you have licensed the account for Skype For Business Online the account will synchronize from the Exchange Online forest to Skype for Business Online forest by using the Windows Azure Active Directory forest.</span></span> <span data-ttu-id="42a71-144">Skype for Business Online プールで Skype Room System アカウントをプロビジョニングするには、次の手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="42a71-144">The following steps are required to provision the Skype Room System account in the Skype for Business Online pool.</span></span> <span data-ttu-id="42a71-145">これらの手順は、既存のリソース メールボックス アカウントまたは新しく作成されたアカウント (confrm1 または confrm2) の両方で同じです。Exchange Online で有効にすると、両方のアカウントが同じ方法で Skype for Business Online に同期されます。</span><span class="sxs-lookup"><span data-stu-id="42a71-145">These steps are the same for both an existing resource mailbox account or a newly created account (confrm1 or confrm2), because once they are enabled in Exchange Online, both of these accounts will be synchronized to Skype for Business Online in the same way:</span></span>
  
1. <span data-ttu-id="42a71-146">リモート PowerShell セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="42a71-146">Create a Remote PowerShell session.</span></span> <span data-ttu-id="42a71-147">Teams [PowerShell](/microsoftteams/teams-powershell-install)モジュールをダウンロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="42a71-147">Note that you will need to download [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
  ```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
  ```

2. <span data-ttu-id="42a71-148">Skype for Business の Skype Room System アカウントを有効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="42a71-148">To enable an Skype Room System account for Skype for Business, run the following command:</span></span>
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    <span data-ttu-id="42a71-149">次のコマンドを使用して、Skype for Business ユーザーが既存のアカウントの 1 つからホームである RegistrarPool アドレスを取得するには、次のコマンドを使用してこのプロパティを返します。</span><span class="sxs-lookup"><span data-stu-id="42a71-149">You can obtain the RegistrarPool address where your Skype for Business users are homed from one of your existing accounts by using the following command to returns this property:</span></span>
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
><span data-ttu-id="42a71-150">多要素認証 (MFA) は、Skype Room System アカウントではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="42a71-150">Multi-Factor Authentication (MFA) isn't supported for Skype Room System accounts.</span></span> 

## <a name="password-expiration"></a><span data-ttu-id="42a71-151">パスワードの期限切れ</span><span class="sxs-lookup"><span data-stu-id="42a71-151">Password expiration</span></span>

<span data-ttu-id="42a71-152">Microsoft 365 または Office 365 では、異なるパスワード有効期限ポリシーを構成しない限り、すべてのユーザー アカウントの既定のパスワード有効期限ポリシーは 90 日間です。</span><span class="sxs-lookup"><span data-stu-id="42a71-152">In Microsoft 365 or Office 365, the default password expiration policy for all of your user accounts is 90 days unless you configure a different password expiration policy.</span></span> <span data-ttu-id="42a71-153">Skype Room System アカウントの場合は、次の手順で [パスワードの有効期限が切れることはありません] 設定を選択できます。</span><span class="sxs-lookup"><span data-stu-id="42a71-153">For Skype Room System accounts, you can select the Password never expires setting with the following steps.</span></span>
  
1. <span data-ttu-id="42a71-154">テナントのグローバル管理者資格情報を使用して、Windows Azure Active Directory セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="42a71-154">Create a Windows Azure Active Directory session by using your tenant global administrator credentials.</span></span>
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. <span data-ttu-id="42a71-155">次のコマンドを使用して、以前に作成した Skype Room System ルーム アカウントの [パスワードの有効期限が切れることはありません] 設定を設定します。</span><span class="sxs-lookup"><span data-stu-id="42a71-155">Set the Password never expires setting for the Skype Room System room account created previously by using the following command:</span></span>
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

<span data-ttu-id="42a71-156">詳細については、「コンピューターの[セットアップ」を参照Windows PowerShell。](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="42a71-156">For more information, see [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="validate"></a><span data-ttu-id="42a71-157">検証</span><span class="sxs-lookup"><span data-stu-id="42a71-157">Validate</span></span>

<span data-ttu-id="42a71-158">検証のために、Skype for Business クライアントを使用して、作成したアカウントにサインインできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="42a71-158">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>