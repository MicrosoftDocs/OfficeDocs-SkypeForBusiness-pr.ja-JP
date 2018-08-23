---
title: Skype Room System アカウントの Office 365 でのプロビジョニング
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: このトピックでは、Office 365 に Skype Room System アカウントをプロビジョニングする方法について説明します。
ms.openlocfilehash: 8120fb2fe8db35eb3907128d65f5b55bb5f544ec
ms.sourcegitcommit: a9556a51f7f970fc05ab0acc9998401db3c1aa57
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2018
ms.locfileid: "22601977"
---
# <a name="provisioning-skype-room-system-accounts-in-office-365"></a><span data-ttu-id="300a0-103">Skype Room System アカウントの Office 365 でのプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="300a0-103">Provisioning Skype Room System accounts in Office 365</span></span>
 
<span data-ttu-id="300a0-104">このトピックでは、Office 365 に Skype Room System アカウントをプロビジョニングする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="300a0-104">Read this topic to learn about provisioning Skype Room System accounts in Office 365.</span></span>
  
<span data-ttu-id="300a0-105">次のセクションでは、Skype の部屋のシステム アカウントが、Office 365 テナントのプロビジョニングについて説明します。</span><span class="sxs-lookup"><span data-stu-id="300a0-105">The following section covers Skype Room System account provisioning for an Office 365 tenant.</span></span>
  
## <a name="office-365-prerequisites"></a><span data-ttu-id="300a0-106">Office 365 の前提条件</span><span class="sxs-lookup"><span data-stu-id="300a0-106">Office 365 prerequisites</span></span>

<span data-ttu-id="300a0-107">オンライン テナントは、次の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="300a0-107">Your online tenant must meet the following requirements:</span></span>
  
- <span data-ttu-id="300a0-108">Office 365 のプランは、プラン 2 のオンライン ビジネス、または Office 365 の E1、E3 E5 の Skype を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="300a0-108">The Office 365 plan must include Skype for Business Online Plan 2, or Office 365 E1, E3 or E5.</span></span> <br/><span data-ttu-id="300a0-109">Skype のビジネスのオンラインの計画の詳細については、 [Skype](https://technet.microsoft.com/library/jj822172.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="300a0-109">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>
    
- <span data-ttu-id="300a0-110">テナントには、会議の機能を有効にするビジネスのための Skype が必要です。</span><span class="sxs-lookup"><span data-stu-id="300a0-110">Your tenant must have the conferencing capability of Skype for Business enabled.</span></span>
    
- <span data-ttu-id="300a0-111">テナントで、Exchange Online を有効にしていること。</span><span class="sxs-lookup"><span data-stu-id="300a0-111">Your tenant must have Exchange Online enabled.</span></span> 
    
- <span data-ttu-id="300a0-112">テナントのリモート管理者に次の PowerShell アクセス権があること。</span><span class="sxs-lookup"><span data-stu-id="300a0-112">Your tenant remote administrator must have the following PowerShell access:</span></span>
    
  - <span data-ttu-id="300a0-113">Exchange Remote PowerShell へのアクセス権</span><span class="sxs-lookup"><span data-stu-id="300a0-113">Exchange Remote PowerShell access</span></span>
    
  - <span data-ttu-id="300a0-114">Skype ビジネス オンライン リモート PowerShell アクセス</span><span class="sxs-lookup"><span data-stu-id="300a0-114">Skype for Business Online Remote PowerShell access</span></span>
    
  - <span data-ttu-id="300a0-115">Windows Azure Active ディレクトリ モジュールの Windows PowerShell に Office 365 のディレクトリ アクセス</span><span class="sxs-lookup"><span data-stu-id="300a0-115">Windows Azure Active Directory Module for Windows PowerShell to access Office 365 directory access</span></span>
    
<span data-ttu-id="300a0-116">Skype Room アカウントの場合は、次のライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="300a0-116">For the Skype Room account, the following licensing is required:</span></span>
  
- <span data-ttu-id="300a0-117">ビジネス オンライン計画 2 または Office 365 の E1、E3 のライセンスは、Skype は、Skype 会議を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="300a0-117">A Skype for Business Online Plan 2 or Office 365 E1 or E3 license is required to enable Skype Meetings.</span></span>
    
- <span data-ttu-id="300a0-118">電話番号、部屋を有効にすることができますので、エンタープライズ VoIP 機能を備えた部屋を entitle、ビジネス オンライン プラン 2 には、電話システムのライセンスの Office 365 の E5、Skype は、必要な (1) です。</span><span class="sxs-lookup"><span data-stu-id="300a0-118">To entitle the room with the Enterprise Voice capability so the room can be enabled with a phone number, a Skype for Business Online Plan 2 with the Phone System license or Office 365 E5 is required (1).</span></span>
    
- <span data-ttu-id="300a0-119">会議にダイヤルイン機能が必要な場合は、音声会議や電話システムのライセンスを必要があります。</span><span class="sxs-lookup"><span data-stu-id="300a0-119">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="300a0-120">会議からのダイヤル ・ アウト機能が必要な場合、国内または国内および海外を呼び出すことを計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="300a0-120">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span> 
    
- <span data-ttu-id="300a0-121">Skype Room アカウントの場合は、リソース メールボックス アカウントとして構成する必要があるため、Exchange Online ライセンスは不要です。</span><span class="sxs-lookup"><span data-stu-id="300a0-121">An Exchange Online license is not required for the Skype Room account because the account should be configured as a resource mailbox account.</span></span>
    
## <a name="provisioning-overview"></a><span data-ttu-id="300a0-122">プロビジョニングの概要</span><span class="sxs-lookup"><span data-stu-id="300a0-122">Provisioning overview</span></span>

<span data-ttu-id="300a0-123">次の図は、Office 365 のフローを提供する Skype の部屋のシステム アカウントの概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="300a0-123">The following diagram provides an overview of the Skype Room System account provisioning flow in Office 365.</span></span>
  
![O365 の Skype Room System のプロビジョニング手順](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a><span data-ttu-id="300a0-125">新しい会議ルームを特定する</span><span class="sxs-lookup"><span data-stu-id="300a0-125">Identify a new conference room</span></span>

<span data-ttu-id="300a0-126">すでにリソースの会議室メールボックス Exchange スケジュールの機能を提供するか、Skype ルーム システムの展開を容易にするために最初にリソース メールボックスを作成することがあります。</span><span class="sxs-lookup"><span data-stu-id="300a0-126">You may already have a resource room mailbox in Exchange that provides the scheduling feature, or you may be creating a resource mailbox for the first time to facilitate Skype Room System deployment.</span></span> <span data-ttu-id="300a0-127">いずれの場合も、テナントで使用するルーム アカウントを特定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="300a0-127">In any case, you must identify a room account to be used in your tenant.</span></span> <span data-ttu-id="300a0-128">Exchange のオンライン提供とビジネスの準備セクションの Skype は、両方の種類のアカウントのためのガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="300a0-128">The Exchange Online Provision and Skype for Business Provision sections provide guidance for both kinds of accounts.</span></span> <span data-ttu-id="300a0-129">、たとえば次の 2 つの部屋があり、それらの両方に対して Skype ルームのシステムを導入したいと思います。</span><span class="sxs-lookup"><span data-stu-id="300a0-129">For example, let's say you have the following two rooms, and you would like to deploy Skype Room System for both of them:</span></span>
  
- <span data-ttu-id="300a0-130">既存のリソース メールボックス アカウント: confrm1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="300a0-130">Existing Resource Mailbox Account: confrm1@contoso.onmicrosoft.com</span></span>
    
- <span data-ttu-id="300a0-131">新しいリソース メールボックス アカウント: confrm2@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="300a0-131">New Resource Mailbox Account: confrm2@contoso.onmicrosoft.com</span></span>
    
## <a name="exchange-online-provisioning"></a><span data-ttu-id="300a0-132">Exchange Online のプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="300a0-132">Exchange Online provisioning</span></span>

<span data-ttu-id="300a0-133">最初に、 [Exchange オンライン PowerShell への接続](https://go.microsoft.com/fwlink/p/?LinkId=396554)」の手順に従って、Exchange オンライン PowerShell に接続します。</span><span class="sxs-lookup"><span data-stu-id="300a0-133">First, connect to Exchange Online PowerShell by following the instructions in the topic, [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
  
<span data-ttu-id="300a0-134">Skype ルーム システムの既存のリソース ルーム メールボックス アカウントを設定するには、Exchange オンライン PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="300a0-134">To set an existing resource room mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="300a0-135">Skype ルーム システムの新しい Exchange リソース メールボックスのアカウントを作成するには、Exchange オンライン PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="300a0-135">To create a new Exchange resource mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="300a0-136">上記のコマンドは、設定または Skype ルームのシステムを使用するためには、新しい Exchange リソース メールボックス アカウントを作成するには、アカウントを有効にするとします。</span><span class="sxs-lookup"><span data-stu-id="300a0-136">The previous commands set up or create a new Exchange resource mailbox account for Skype Room System usage by enabling the account.</span></span>
  
<span data-ttu-id="300a0-137">メールボックスを作成するは、メールボックスを構成するのには Exchange のオンライン PowerShell でセット CalendarProcessing コマンドレットを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="300a0-137">After creating the mailbox, you can use the Set-CalendarProcessing cmdlet in Exchange Online PowerShell to configure the mailbox.</span></span> <span data-ttu-id="300a0-138">詳細については、単一フォレストのオンプレミス展開の手順 3 ～ 6 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="300a0-138">Refer to steps 3 through 6 under Single forest on-premises deployments for more details</span></span>

## <a name="assigning-a-skype-for-business-online-license"></a><span data-ttu-id="300a0-139">Skype for Business Online ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="300a0-139">Assigning a Skype for Business Online license</span></span>

<span data-ttu-id="300a0-140">割り当てるには、Skype または Skype のオンライン ビジネス (プラン 2) のオンライン ビジネス (プラン 3) のライセンスの[割り当てまたはビジネス向けの Office 365 のライセンスを削除](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US)またはビジネスのアドオンの[Skype で説明したように Office 365 管理ポータルを使用して、ライセンス](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)。</span><span class="sxs-lookup"><span data-stu-id="300a0-140">Now you can assign a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license by using the Office 365 administrative portal as described in [Assign or remove licenses for Office 365 for business](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) or in [Skype for Business add-on licensing](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span></span> 
  
<span data-ttu-id="300a0-141">ビジネス オンラインの Skype のライセンスを割り当てた後は、ログインして、Skype を使用してビジネスのクライアントのアクティブなアカウントであることを検証することができます。</span><span class="sxs-lookup"><span data-stu-id="300a0-141">After you assign a license for Skype for Business Online, you will be able to log in and validate that the account is active using any Skype for Business client.</span></span>
  
## <a name="skype-for-business-online-provisioning"></a><span data-ttu-id="300a0-142">Skype for Business Online のプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="300a0-142">Skype for Business Online provisioning</span></span>

<span data-ttu-id="300a0-143">Skype のビジネス オンライン アカウントはオンラインの Exchange フォレストから Skype をオンライン ビジネスのフォレストを使用して同期のアカウントに制限があるとリソース ルーム後メールボックス アカウントが作成され、以前に示すように、有効になっている、Windows Azure Active Directory フォレストです。</span><span class="sxs-lookup"><span data-stu-id="300a0-143">After a resource room mailbox account has been created and enabled as shown previously, and you have licensed the account for Skype For Business Online the account will synchronize from the Exchange Online forest to Skype for Business Online forest by using the Windows Azure Active Directory forest.</span></span> <span data-ttu-id="300a0-144">次の手順は、オンライン ビジネスのプールの Skype の Skype ルームのシステム アカウントを準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="300a0-144">The following steps are required to provision the Skype Room System account in the Skype for Business Online pool.</span></span> <span data-ttu-id="300a0-145">この手順は、それらが有効な Exchange オンラインと両方のこれらのアカウントと同期されます Skype オンライン ビジネスのと同じ方法であるため既存のリソース メールボックスのアカウントまたは (confrm1 または confrm2) に、新しく作成したアカウントの両方に対して同じです。</span><span class="sxs-lookup"><span data-stu-id="300a0-145">These steps are the same for both an existing resource mailbox account or a newly created account (confrm1 or confrm2), because once they are enabled in Exchange Online, both of these accounts will be synchronized to Skype for Business Online in the same way:</span></span>
  
1. <span data-ttu-id="300a0-146">リモート PowerShell セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="300a0-146">Create a Remote PowerShell session.</span></span> <span data-ttu-id="300a0-147">コネクタ モジュールのオンライン ビジネスおよび Microsoft オンライン サービス サインイン アシスタントの Skype をダウンロードし、コンピューターが構成されているかどうかを確認する必要があります注意してください。</span><span class="sxs-lookup"><span data-stu-id="300a0-147">Note that you will need to download Skype for Business Online Connector Module and Microsoft Online Services Sign-In Assistant and make sure that your computer is configured.</span></span> <span data-ttu-id="300a0-148">詳細については、 [Windows PowerShell には、コンピューターの設定](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="300a0-148">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
    
   ```
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="300a0-149">ビジネス用の Skype で Skype ルームのシステム アカウントを有効にするのには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="300a0-149">To enable an Skype Room System account for Skype for Business, run the following command:</span></span>
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    <span data-ttu-id="300a0-150">ビジネス ユーザー向けに、Skype が置かれている既存のアカウントのいずれかから次のコマンドを使用してアドレスを取得する RegistrarPool にこのプロパティを取得できます。</span><span class="sxs-lookup"><span data-stu-id="300a0-150">You can obtain the RegistrarPool address where your Skype for Business users are homed from one of your existing accounts by using the following command to returns this property:</span></span>
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

  
## <a name="password-expiration"></a><span data-ttu-id="300a0-151">パスワードの有効期限</span><span class="sxs-lookup"><span data-stu-id="300a0-151">Password expiration</span></span>

<span data-ttu-id="300a0-152">Office 365 では、別のパスワードの有効期限ポリシーを構成しない限り、すべてのユーザー アカウントのパスワードの有効期限ポリシーは、既定で 90 日間です。</span><span class="sxs-lookup"><span data-stu-id="300a0-152">In Office 365, the default password expiration policy for all of your user accounts is 90 days unless you configure a different password expiration policy.</span></span> <span data-ttu-id="300a0-153">Skype ルームのシステム アカウント、パスワードを選択できます次の手順で設定を有効期限はありません。</span><span class="sxs-lookup"><span data-stu-id="300a0-153">For Skype Room System accounts, you can select the Password never expires setting with the following steps.</span></span>
  
1. <span data-ttu-id="300a0-154">管理者のグローバル資格情報を使用して、Windows Azure Active Directory セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="300a0-154">Create a Windows Azure Active Directory session by using your tenant global administrator credentials.</span></span>
    
    ```
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. <span data-ttu-id="300a0-155">パスワードの設定は、次のコマンドを使用して、以前作成した Skype ルーム システム ルームのアカウントの設定を有効期限なし。</span><span class="sxs-lookup"><span data-stu-id="300a0-155">Set the Password never expires setting for the Skype Room System room account created previously by using the following command:</span></span>
    
   ```
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

<span data-ttu-id="300a0-156">詳細については、 [Windows PowerShell には、コンピューターの設定](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="300a0-156">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  
## <a name="validate"></a><span data-ttu-id="300a0-157">検証</span><span class="sxs-lookup"><span data-stu-id="300a0-157">Validate</span></span>

<span data-ttu-id="300a0-158">検証、ビジネス クライアント用の Skype を使用して作成したアカウントにサインインできるように。</span><span class="sxs-lookup"><span data-stu-id="300a0-158">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

