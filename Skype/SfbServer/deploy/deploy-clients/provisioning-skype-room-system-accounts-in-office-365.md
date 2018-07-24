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
ms.openlocfilehash: 63b195dd2989e6da2d3a2cecdbc76ccff741cd87
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "21010042"
---
# <a name="provisioning-skype-room-system-accounts-in-office-365"></a><span data-ttu-id="7d98a-103">Skype Room System アカウントの Office 365 でのプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="7d98a-103">Provisioning Skype Room System accounts in Office 365</span></span>
 
<span data-ttu-id="7d98a-104">このトピックでは、Office 365 に Skype Room System アカウントをプロビジョニングする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7d98a-104">Read this topic to learn about provisioning Skype Room System accounts in Office 365.</span></span>
  
<span data-ttu-id="7d98a-105">次のセクションでは、Skype の部屋のシステム アカウントが、Office 365 テナントのプロビジョニングについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7d98a-105">The following section covers Skype Room System account provisioning for an Office 365 tenant.</span></span>
  
## <a name="office-365-prerequisites"></a><span data-ttu-id="7d98a-106">Office 365 の前提条件</span><span class="sxs-lookup"><span data-stu-id="7d98a-106">Office 365 prerequisites</span></span>

<span data-ttu-id="7d98a-107">オンライン テナントは、次の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d98a-107">Your online tenant must meet the following requirements:</span></span>
  
- <span data-ttu-id="7d98a-108">Office 365 のプランは、ビジネス オンライン プラン 2、プラン 3、または Office 365 の E1、E3 または E5 の Skype を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d98a-108">The Office 365 plan must include Skype for Business Online Plan 2, Plan 3, or Office 365 E1, E3 or E5.</span></span>
    
- <span data-ttu-id="7d98a-109">テナントには、会議の機能を有効にするビジネスのための Skype が必要です。</span><span class="sxs-lookup"><span data-stu-id="7d98a-109">Your tenant must have the conferencing capability of Skype for Business enabled.</span></span>
    
- <span data-ttu-id="7d98a-110">テナントで、Exchange Online を有効にしていること。</span><span class="sxs-lookup"><span data-stu-id="7d98a-110">Your tenant must have Exchange Online enabled.</span></span> 
    
- <span data-ttu-id="7d98a-111">テナントのリモート管理者に次の PowerShell アクセス権があること。</span><span class="sxs-lookup"><span data-stu-id="7d98a-111">Your tenant remote administrator must have the following PowerShell access:</span></span>
    
  - <span data-ttu-id="7d98a-112">Exchange Remote PowerShell へのアクセス権</span><span class="sxs-lookup"><span data-stu-id="7d98a-112">Exchange Remote PowerShell access</span></span>
    
  - <span data-ttu-id="7d98a-113">Skype ビジネス オンライン リモート PowerShell アクセス</span><span class="sxs-lookup"><span data-stu-id="7d98a-113">Skype for Business Online Remote PowerShell access</span></span>
    
  - <span data-ttu-id="7d98a-114">Windows Azure Active ディレクトリ モジュールの Windows PowerShell に Office 365 のディレクトリ アクセス</span><span class="sxs-lookup"><span data-stu-id="7d98a-114">Windows Azure Active Directory Module for Windows PowerShell to access Office 365 directory access</span></span>
    
<span data-ttu-id="7d98a-115">Skype Room アカウントの場合は、次のライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="7d98a-115">For the Skype Room account, the following licensing is required:</span></span>
  
- <span data-ttu-id="7d98a-116">ビジネス オンライン計画 2 または Office 365 の E1、E3 のライセンスは、Skype は、Skype 会議を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d98a-116">A Skype for Business Online Plan 2 or Office 365 E1 or E3 license is required to enable Skype Meetings.</span></span>
    
- <span data-ttu-id="7d98a-117">電話番号、部屋を有効にすることができますので、エンタープライズ VoIP 機能を備えた部屋を entitle、ビジネス オンライン計画 2 クラウド PBX のアドオンまたは Office 365 の E5 に、Skype は、必要な (1) です。</span><span class="sxs-lookup"><span data-stu-id="7d98a-117">To entitle the room with the Enterprise Voice capability so the room can be enabled with a phone number, a Skype for Business Online Plan 2 with the Cloud PBX Add-on or Office 365 E5 is required (1).</span></span>
    
- <span data-ttu-id="7d98a-118">ある会議内で PSTN 会議を利用できるかどうかは、会議開催者のライセンスによって決まります。</span><span class="sxs-lookup"><span data-stu-id="7d98a-118">The availability of PSTN Conferencing entitlement within any given meeting is determined by the license of the meeting organizer.</span></span>
    
- <span data-ttu-id="7d98a-119">Skype Room アカウントの場合は、リソース メールボックス アカウントとして構成する必要があるため、Exchange Online ライセンスは不要です。</span><span class="sxs-lookup"><span data-stu-id="7d98a-119">An Exchange Online license is not required for the Skype Room account because the account should be configured as a resource mailbox account.</span></span>
    
## <a name="provisioning-overview"></a><span data-ttu-id="7d98a-120">プロビジョニングの概要</span><span class="sxs-lookup"><span data-stu-id="7d98a-120">Provisioning overview</span></span>

<span data-ttu-id="7d98a-121">次の図は、Office 365 のフローを提供する Skype の部屋のシステム アカウントの概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="7d98a-121">The following diagram provides an overview of the Skype Room System account provisioning flow in Office 365.</span></span>
  
![O365 の Skype Room System のプロビジョニング手順](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a><span data-ttu-id="7d98a-123">新しい会議ルームを特定する</span><span class="sxs-lookup"><span data-stu-id="7d98a-123">Identify a new conference room</span></span>

<span data-ttu-id="7d98a-124">すでにリソースの会議室メールボックス Exchange スケジュールの機能を提供するか、Skype ルーム システムの展開を容易にするために最初にリソース メールボックスを作成することがあります。</span><span class="sxs-lookup"><span data-stu-id="7d98a-124">You may already have a resource room mailbox in Exchange that provides the scheduling feature, or you may be creating a resource mailbox for the first time to facilitate Skype Room System deployment.</span></span> <span data-ttu-id="7d98a-125">いずれの場合も、テナントで使用するルーム アカウントを特定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d98a-125">In any case, you must identify a room account to be used in your tenant.</span></span> <span data-ttu-id="7d98a-126">Exchange のオンライン提供とビジネスの準備セクションの Skype は、両方の種類のアカウントのためのガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="7d98a-126">The Exchange Online Provision and Skype for Business Provision sections provide guidance for both kinds of accounts.</span></span> <span data-ttu-id="7d98a-127">、たとえば次の 2 つの部屋があり、それらの両方に対して Skype ルームのシステムを導入したいと思います。</span><span class="sxs-lookup"><span data-stu-id="7d98a-127">For example, let's say you have the following two rooms, and you would like to deploy Skype Room System for both of them:</span></span>
  
- <span data-ttu-id="7d98a-128">既存のリソース メールボックス アカウント: confrm1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="7d98a-128">Existing Resource Mailbox Account: confrm1@contoso.onmicrosoft.com</span></span>
    
- <span data-ttu-id="7d98a-129">新しいリソース メールボックス アカウント: confrm2@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="7d98a-129">New Resource Mailbox Account: confrm2@contoso.onmicrosoft.com</span></span>
    
## <a name="exchange-online-provisioning"></a><span data-ttu-id="7d98a-130">Exchange Online のプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="7d98a-130">Exchange Online provisioning</span></span>

<span data-ttu-id="7d98a-131">最初に、 [Exchange オンライン PowerShell への接続](https://go.microsoft.com/fwlink/p/?LinkId=396554)」の手順に従って、Exchange オンライン PowerShell に接続します。</span><span class="sxs-lookup"><span data-stu-id="7d98a-131">First, connect to Exchange Online PowerShell by following the instructions in the topic, [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
  
<span data-ttu-id="7d98a-132">Skype ルーム システムの既存のリソース ルーム メールボックス アカウントを設定するには、Exchange オンライン PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7d98a-132">To set an existing resource room mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="7d98a-133">Skype ルーム システムの新しい Exchange リソース メールボックスのアカウントを作成するには、Exchange オンライン PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7d98a-133">To create a new Exchange resource mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="7d98a-134">上記のコマンドは、設定または Skype ルームのシステムを使用するためには、新しい Exchange リソース メールボックス アカウントを作成するには、アカウントを有効にするとします。</span><span class="sxs-lookup"><span data-stu-id="7d98a-134">The previous commands set up or create a new Exchange resource mailbox account for Skype Room System usage by enabling the account.</span></span>
  
<span data-ttu-id="7d98a-135">メールボックスを作成するは、メールボックスを構成するのには Exchange のオンライン PowerShell でセット CalendarProcessing コマンドレットを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="7d98a-135">After creating the mailbox, you can use the Set-CalendarProcessing cmdlet in Exchange Online PowerShell to configure the mailbox.</span></span> <span data-ttu-id="7d98a-136">詳細については、単一フォレストのオンプレミス展開の手順 3 ～ 6 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d98a-136">Refer to steps 3 through 6 under Single forest on-premises deployments for more details</span></span>

## <a name="assigning-a-skype-for-business-online-license"></a><span data-ttu-id="7d98a-137">Skype for Business Online ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="7d98a-137">Assigning a Skype for Business Online license</span></span>

<span data-ttu-id="7d98a-138">割り当てるには、Skype または Skype のオンライン ビジネス (プラン 2) のオンライン ビジネス (プラン 3) のライセンスの[割り当てまたはビジネス向けの Office 365 のライセンスを削除](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US)またはビジネスのアドオンの[Skype で説明したように Office 365 管理ポータルを使用して、ライセンス](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)。</span><span class="sxs-lookup"><span data-stu-id="7d98a-138">Now you can assign a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license by using the Office 365 administrative portal as described in [Assign or remove licenses for Office 365 for business](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) or in [Skype for Business add-on licensing](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span></span> 
  
<span data-ttu-id="7d98a-139">ビジネス オンラインの Skype のライセンスを割り当てた後は、ログインして、Skype を使用してビジネスのクライアントのアクティブなアカウントであることを検証することができます。</span><span class="sxs-lookup"><span data-stu-id="7d98a-139">After you assign a license for Skype for Business Online, you will be able to log in and validate that the account is active using any Skype for Business client.</span></span>
  
## <a name="skype-for-business-online-provisioning"></a><span data-ttu-id="7d98a-140">Skype for Business Online のプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="7d98a-140">Skype for Business Online provisioning</span></span>

<span data-ttu-id="7d98a-141">Skype のビジネス オンライン アカウントはオンラインの Exchange フォレストから Skype をオンライン ビジネスのフォレストを使用して同期のアカウントに制限があるとリソース ルーム後メールボックス アカウントが作成され、以前に示すように、有効になっている、Windows Azure Active Directory フォレストです。</span><span class="sxs-lookup"><span data-stu-id="7d98a-141">After a resource room mailbox account has been created and enabled as shown previously, and you have licensed the account for Skype For Business Online the account will synchronize from the Exchange Online forest to Skype for Business Online forest by using the Windows Azure Active Directory forest.</span></span> <span data-ttu-id="7d98a-142">次の手順は、オンライン ビジネスのプールの Skype の Skype ルームのシステム アカウントを準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d98a-142">The following steps are required to provision the Skype Room System account in the Skype for Business Online pool.</span></span> <span data-ttu-id="7d98a-143">この手順は、それらが有効な Exchange オンラインと両方のこれらのアカウントと同期されます Skype オンライン ビジネスのと同じ方法であるため既存のリソース メールボックスのアカウントまたは (confrm1 または confrm2) に、新しく作成したアカウントの両方に対して同じです。</span><span class="sxs-lookup"><span data-stu-id="7d98a-143">These steps are the same for both an existing resource mailbox account or a newly created account (confrm1 or confrm2), because once they are enabled in Exchange Online, both of these accounts will be synchronized to Skype for Business Online in the same way:</span></span>
  
<span data-ttu-id="7d98a-144"><<<<<<< 見出し</span><span class="sxs-lookup"><span data-stu-id="7d98a-144"><<<<<<< HEAD</span></span>
1. <span data-ttu-id="7d98a-145">リモート PowerShell セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="7d98a-145">Create a Remote PowerShell session.</span></span> <span data-ttu-id="7d98a-146">コネクタ モジュールのオンライン ビジネスおよび Microsoft オンライン サービス サインイン アシスタントの Skype をダウンロードし、コンピューターが構成されているかどうかを確認する必要があります注意してください。</span><span class="sxs-lookup"><span data-stu-id="7d98a-146">Note that you will need to download Skype for Business Online Connector Module and Microsoft Online Services Sign-In Assistant and make sure that your computer is configured.</span></span> <span data-ttu-id="7d98a-147">詳細については、 [Windows PowerShell には、コンピューターの設定](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d98a-147">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
=======
1. <span data-ttu-id="7d98a-148">リモート PowerShell セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="7d98a-148">Create a Remote PowerShell session.</span></span> <span data-ttu-id="7d98a-149">コネクタ モジュールのオンライン ビジネスおよび Microsoft オンライン サービス サインイン アシスタントの Skype をダウンロードし、コンピューターが構成されているかどうかを確認する必要があります注意してください。</span><span class="sxs-lookup"><span data-stu-id="7d98a-149">Note that you will need to download Skype for Business Online Connector Module and Microsoft Online Services Sign-In Assistant and make sure that your computer is configured.</span></span> <span data-ttu-id="7d98a-150">詳細については、 [Windows PowerShell には、コンピューターの設定](http://technet.microsoft.com/library/bca143e2-659a-4161-9220-59ffd9fc2874.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d98a-150">For more information, see [Set up your computer for Windows PowerShell](http://technet.microsoft.com/library/bca143e2-659a-4161-9220-59ffd9fc2874.aspx).</span></span>
>>>>>>> <span data-ttu-id="7d98a-151">0a230b02c47ae4de6638a638b76ed38243c71ab9</span><span class="sxs-lookup"><span data-stu-id="7d98a-151">0a230b02c47ae4de6638a638b76ed38243c71ab9</span></span>
    
   ```
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="7d98a-152">ビジネス用の Skype で Skype ルームのシステム アカウントを有効にするのには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7d98a-152">To enable an Skype Room System account for Skype for Business, run the following command:</span></span>
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    <span data-ttu-id="7d98a-153">ビジネス ユーザー向けに、Skype が置かれている既存のアカウントのいずれかから次のコマンドを使用してアドレスを取得する RegistrarPool にこのプロパティを取得できます。</span><span class="sxs-lookup"><span data-stu-id="7d98a-153">You can obtain the RegistrarPool address where your Skype for Business users are homed from one of your existing accounts by using the following command to returns this property:</span></span>
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

  
## <a name="password-expiration"></a><span data-ttu-id="7d98a-154">パスワードの有効期限</span><span class="sxs-lookup"><span data-stu-id="7d98a-154">Password expiration</span></span>

<span data-ttu-id="7d98a-155">Office 365 では、別のパスワードの有効期限ポリシーを構成しない限り、すべてのユーザー アカウントのパスワードの有効期限ポリシーは、既定で 90 日間です。</span><span class="sxs-lookup"><span data-stu-id="7d98a-155">In Office 365, the default password expiration policy for all of your user accounts is 90 days unless you configure a different password expiration policy.</span></span> <span data-ttu-id="7d98a-156">Skype ルームのシステム アカウント、パスワードを選択できます次の手順で設定を有効期限はありません。</span><span class="sxs-lookup"><span data-stu-id="7d98a-156">For Skype Room System accounts, you can select the Password never expires setting with the following steps.</span></span>
  
1. <span data-ttu-id="7d98a-157">管理者のグローバル資格情報を使用して、Windows Azure Active Directory セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="7d98a-157">Create a Windows Azure Active Directory session by using your tenant global administrator credentials.</span></span>
    
    ```
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. <span data-ttu-id="7d98a-158">パスワードの設定は、次のコマンドを使用して、以前作成した Skype ルーム システム ルームのアカウントの設定を有効期限なし。</span><span class="sxs-lookup"><span data-stu-id="7d98a-158">Set the Password never expires setting for the Skype Room System room account created previously by using the following command:</span></span>
    
   ```
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

<span data-ttu-id="7d98a-159">詳細については、 [Windows PowerShell には、コンピューターの設定](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d98a-159">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  

