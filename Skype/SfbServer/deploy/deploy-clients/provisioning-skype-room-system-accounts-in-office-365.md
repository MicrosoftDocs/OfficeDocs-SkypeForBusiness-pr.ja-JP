---
title: Office 365 での Skype Room System アカウントのプロビジョニング
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: Office 365 での Skype Room System アカウントのプロビジョニングの詳細については、このトピックをお読みください。
ms.openlocfilehash: 141c833bcbdd744a7577c0762cb8ba55dd3d5c54
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037727"
---
# <a name="provisioning-skype-room-system-accounts-in-office-365"></a><span data-ttu-id="dd23f-103">Office 365 での Skype Room System アカウントのプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="dd23f-103">Provisioning Skype Room System accounts in Office 365</span></span>
 
<span data-ttu-id="dd23f-104">Office 365 での Skype Room System アカウントのプロビジョニングの詳細については、このトピックをお読みください。</span><span class="sxs-lookup"><span data-stu-id="dd23f-104">Read this topic to learn about provisioning Skype Room System accounts in Office 365.</span></span>
  
<span data-ttu-id="dd23f-105">次のセクションでは、Office 365 テナントの Skype Room System アカウントのプロビジョニングについて説明します。</span><span class="sxs-lookup"><span data-stu-id="dd23f-105">The following section covers Skype Room System account provisioning for an Office 365 tenant.</span></span>
  
## <a name="office-365-prerequisites"></a><span data-ttu-id="dd23f-106">Office 365 の前提条件</span><span class="sxs-lookup"><span data-stu-id="dd23f-106">Office 365 prerequisites</span></span>

<span data-ttu-id="dd23f-107">オンラインテナントは、次の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd23f-107">Your online tenant must meet the following requirements:</span></span>
  
- <span data-ttu-id="dd23f-108">Office 365 プランには、Skype for Business Online プラン2、または Office 365 E1、E3、または E5 を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd23f-108">The Office 365 plan must include Skype for Business Online Plan 2, or Office 365 E1, E3 or E5.</span></span> <br/><span data-ttu-id="dd23f-109">Skype for business Online プランの詳細については、「 [skype For Business Online サービスの説明](https://technet.microsoft.com/library/jj822172.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd23f-109">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>
    
- <span data-ttu-id="dd23f-110">テナントには、Skype for Business が有効になっている会議機能が必要です。</span><span class="sxs-lookup"><span data-stu-id="dd23f-110">Your tenant must have the conferencing capability of Skype for Business enabled.</span></span>
    
- <span data-ttu-id="dd23f-111">テナントでは、Exchange Online が有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd23f-111">Your tenant must have Exchange Online enabled.</span></span> 
    
- <span data-ttu-id="dd23f-112">テナントのリモート管理者は、次の PowerShell アクセス権を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd23f-112">Your tenant remote administrator must have the following PowerShell access:</span></span>
    
  - <span data-ttu-id="dd23f-113">Exchange リモート PowerShell アクセス</span><span class="sxs-lookup"><span data-stu-id="dd23f-113">Exchange Remote PowerShell access</span></span>
    
  - <span data-ttu-id="dd23f-114">Skype for Business Online のリモート PowerShell アクセス</span><span class="sxs-lookup"><span data-stu-id="dd23f-114">Skype for Business Online Remote PowerShell access</span></span>
    
  - <span data-ttu-id="dd23f-115">Office 365 ディレクトリアクセスにアクセスするための windows PowerShell 用 windows Azure Active Directory モジュール</span><span class="sxs-lookup"><span data-stu-id="dd23f-115">Windows Azure Active Directory Module for Windows PowerShell to access Office 365 directory access</span></span>
    
<span data-ttu-id="dd23f-116">Skype Room アカウントの場合は、次のライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="dd23f-116">For the Skype Room account, the following licensing is required:</span></span>
  
- <span data-ttu-id="dd23f-117">Skype 会議を有効にするには、Skype for Business Online プラン2または Office 365 E1 または E3 ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="dd23f-117">A Skype for Business Online Plan 2 or Office 365 E1 or E3 license is required to enable Skype Meetings.</span></span>
    
- <span data-ttu-id="dd23f-118">電話番号で会議室を有効にできるように、エンタープライズ Voip 機能を使用して会議室を entitle するために、電話システムライセンスまたは Office 365 E5 がある Skype for Business Online プラン2が必要です (1)。</span><span class="sxs-lookup"><span data-stu-id="dd23f-118">To entitle the room with the Enterprise Voice capability so the room can be enabled with a phone number, a Skype for Business Online Plan 2 with the Phone System license or Office 365 E5 is required (1).</span></span>
    
- <span data-ttu-id="dd23f-119">会議からダイヤルイン機能が必要な場合は、電話会議と電話システムのライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="dd23f-119">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="dd23f-120">会議からのダイヤルアウト機能が必要な場合は、国内または国内および国際通話プランが必要です。</span><span class="sxs-lookup"><span data-stu-id="dd23f-120">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span> 
    
- <span data-ttu-id="dd23f-121">アカウントは、リソースメールボックスアカウントとして構成する必要があるため、Skype Room アカウントには Exchange Online ライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="dd23f-121">An Exchange Online license is not required for the Skype Room account because the account should be configured as a resource mailbox account.</span></span>
    
## <a name="provisioning-overview"></a><span data-ttu-id="dd23f-122">プロビジョニングの概要</span><span class="sxs-lookup"><span data-stu-id="dd23f-122">Provisioning overview</span></span>

<span data-ttu-id="dd23f-123">次の図は、Office 365 の Skype Room System アカウントのプロビジョニングフローの概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="dd23f-123">The following diagram provides an overview of the Skype Room System account provisioning flow in Office 365.</span></span>
  
![O365 の Skype Room System のプロビジョニング手順](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a><span data-ttu-id="dd23f-125">新しい会議室を識別する</span><span class="sxs-lookup"><span data-stu-id="dd23f-125">Identify a new conference room</span></span>

<span data-ttu-id="dd23f-126">スケジュール機能を提供する Exchange のリソースルームメールボックスが既にあるか、Skype Room System の展開を容易にするために初めてリソースメールボックスを作成している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dd23f-126">You may already have a resource room mailbox in Exchange that provides the scheduling feature, or you may be creating a resource mailbox for the first time to facilitate Skype Room System deployment.</span></span> <span data-ttu-id="dd23f-127">いずれの場合も、テナントで使用する会議室のアカウントを特定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd23f-127">In any case, you must identify a room account to be used in your tenant.</span></span> <span data-ttu-id="dd23f-128">「Exchange Online のプロビジョニング」および「Skype for Business のプロビジョニング」セクションでは、両方の種類のアカウントについてのガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="dd23f-128">The Exchange Online Provision and Skype for Business Provision sections provide guidance for both kinds of accounts.</span></span> <span data-ttu-id="dd23f-129">たとえば、次の2つのルームがあり、両方に対して Skype Room System を展開したいとします。</span><span class="sxs-lookup"><span data-stu-id="dd23f-129">For example, let's say you have the following two rooms, and you would like to deploy Skype Room System for both of them:</span></span>
  
- <span data-ttu-id="dd23f-130">既存のリソースメールボックスアカウント: confrm1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="dd23f-130">Existing Resource Mailbox Account: confrm1@contoso.onmicrosoft.com</span></span>
    
- <span data-ttu-id="dd23f-131">新しいリソースメールボックスアカウント: confrm2@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="dd23f-131">New Resource Mailbox Account: confrm2@contoso.onmicrosoft.com</span></span>
    
## <a name="exchange-online-provisioning"></a><span data-ttu-id="dd23f-132">Exchange Online のプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="dd23f-132">Exchange Online provisioning</span></span>

<span data-ttu-id="dd23f-133">最初に、トピック「 [Exchange Online powershell に接続する](https://go.microsoft.com/fwlink/p/?LinkId=396554)」の手順に従って Exchange online powershell に接続します。</span><span class="sxs-lookup"><span data-stu-id="dd23f-133">First, connect to Exchange Online PowerShell by following the instructions in the topic, [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
  
<span data-ttu-id="dd23f-134">Skype Room System の既存のリソース会議のメールボックスアカウントを設定するには、Exchange Online PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="dd23f-134">To set an existing resource room mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```powershell
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="dd23f-135">Skype Room System の新しい Exchange リソースメールボックスアカウントを作成するには、Exchange Online PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="dd23f-135">To create a new Exchange resource mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```powershell
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="dd23f-136">上記のコマンドは、アカウントを有効にすることによって、Skype Room System の使用のための新しい Exchange リソースメールボックスアカウントをセットアップまたは作成します。</span><span class="sxs-lookup"><span data-stu-id="dd23f-136">The previous commands set up or create a new Exchange resource mailbox account for Skype Room System usage by enabling the account.</span></span>
  
<span data-ttu-id="dd23f-137">メールボックスを作成したら、Exchange Online PowerShell で、CalendarProcessing コマンドレットを使用してメールボックスを構成できます。</span><span class="sxs-lookup"><span data-stu-id="dd23f-137">After creating the mailbox, you can use the Set-CalendarProcessing cmdlet in Exchange Online PowerShell to configure the mailbox.</span></span> <span data-ttu-id="dd23f-138">詳細については、単一フォレストのオンプレミス展開の手順 3 ~ 6 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd23f-138">Refer to steps 3 through 6 under Single forest on-premises deployments for more details</span></span>

## <a name="assigning-a-skype-for-business-online-license"></a><span data-ttu-id="dd23f-139">Skype for Business Online ライセンスの割り当て</span><span class="sxs-lookup"><span data-stu-id="dd23f-139">Assigning a Skype for Business Online license</span></span>

<span data-ttu-id="dd23f-140">「Office 365 for business または[skype For business アドオンライセンス](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)[のライセンスを割り当てるまたは削除](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US)する」に記載されているように、office 365 管理ポータルを使用して skype For business online (プラン 2) または skype For business online (プラン 3) ライセンスを割り当てることができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="dd23f-140">Now you can assign a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license by using the Office 365 administrative portal as described in [Assign or remove licenses for Office 365 for business](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) or in [Skype for Business add-on licensing](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span></span> 
  
<span data-ttu-id="dd23f-141">Skype for business Online のライセンスを割り当てた後は、Skype for Business クライアントを使用してログインし、アカウントがアクティブであることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="dd23f-141">After you assign a license for Skype for Business Online, you will be able to log in and validate that the account is active using any Skype for Business client.</span></span>
  
## <a name="skype-for-business-online-provisioning"></a><span data-ttu-id="dd23f-142">Skype for Business Online のプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="dd23f-142">Skype for Business Online provisioning</span></span>

<span data-ttu-id="dd23f-143">前に示したように、リソース会議のメールボックスアカウントを作成して有効にした後、Skype For Business Online のアカウントのライセンスを取得すると、このアカウントは、Exchange Online フォレストから Skype for business Online フォレストに同期されます。Windows Azure Active Directory フォレスト。</span><span class="sxs-lookup"><span data-stu-id="dd23f-143">After a resource room mailbox account has been created and enabled as shown previously, and you have licensed the account for Skype For Business Online the account will synchronize from the Exchange Online forest to Skype for Business Online forest by using the Windows Azure Active Directory forest.</span></span> <span data-ttu-id="dd23f-144">Skype for Business Online プールで Skype Room System アカウントをプロビジョニングするには、次の手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="dd23f-144">The following steps are required to provision the Skype Room System account in the Skype for Business Online pool.</span></span> <span data-ttu-id="dd23f-145">これらの手順は、既存のリソースメールボックスアカウントまたは新しく作成されたアカウント (confrm1 または confrm2) の両方で同じです。これらのアカウントは、Exchange Online で有効になると、同じ方法で Skype for Business Online と同期されます。</span><span class="sxs-lookup"><span data-stu-id="dd23f-145">These steps are the same for both an existing resource mailbox account or a newly created account (confrm1 or confrm2), because once they are enabled in Exchange Online, both of these accounts will be synchronized to Skype for Business Online in the same way:</span></span>
  
1. <span data-ttu-id="dd23f-146">リモート PowerShell セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="dd23f-146">Create a Remote PowerShell session.</span></span> <span data-ttu-id="dd23f-147">Skype for Business Online Connector モジュールと Microsoft Online Services サインインアシスタントをダウンロードして、コンピューターが構成されていることを確認する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="dd23f-147">Note that you will need to download Skype for Business Online Connector Module and Microsoft Online Services Sign-In Assistant and make sure that your computer is configured.</span></span> <span data-ttu-id="dd23f-148">詳細については、「 [Windows PowerShell 用にコンピューター](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)をセットアップする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd23f-148">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
    
   ```powershell
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="dd23f-149">Skype for business の Skype Room System アカウントを有効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="dd23f-149">To enable an Skype Room System account for Skype for Business, run the following command:</span></span>
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    <span data-ttu-id="dd23f-150">このプロパティを取得するには、次のコマンドを使用して、Skype for Business ユーザーが既存のアカウントのいずれかに所属している RegistrarPool アドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="dd23f-150">You can obtain the RegistrarPool address where your Skype for Business users are homed from one of your existing accounts by using the following command to returns this property:</span></span>
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
><span data-ttu-id="dd23f-151">Skype Room System アカウントでは、多要素認証 (MFA) はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="dd23f-151">Multi-Factor Authentication (MFA) isn't supported for Skype Room System accounts.</span></span> 

## <a name="password-expiration"></a><span data-ttu-id="dd23f-152">パスワードの期限切れ</span><span class="sxs-lookup"><span data-stu-id="dd23f-152">Password expiration</span></span>

<span data-ttu-id="dd23f-153">Office 365 では、別のパスワードの有効期限ポリシーを構成しない限り、すべてのユーザーアカウントの既定のパスワードの有効期限ポリシーは90日になります。</span><span class="sxs-lookup"><span data-stu-id="dd23f-153">In Office 365, the default password expiration policy for all of your user accounts is 90 days unless you configure a different password expiration policy.</span></span> <span data-ttu-id="dd23f-154">Skype Room System アカウントの場合は、次の手順を使用してパスワードを無期限に設定することができます。</span><span class="sxs-lookup"><span data-stu-id="dd23f-154">For Skype Room System accounts, you can select the Password never expires setting with the following steps.</span></span>
  
1. <span data-ttu-id="dd23f-155">テナント全体管理者の資格情報を使用して、Windows Azure Active Directory セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="dd23f-155">Create a Windows Azure Active Directory session by using your tenant global administrator credentials.</span></span>
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. <span data-ttu-id="dd23f-156">次のコマンドを使用して、以前に作成した Skype Room System room アカウントのパスワードを無期限に設定します。</span><span class="sxs-lookup"><span data-stu-id="dd23f-156">Set the Password never expires setting for the Skype Room System room account created previously by using the following command:</span></span>
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

<span data-ttu-id="dd23f-157">詳細については、「 [Windows PowerShell 用にコンピューター](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)をセットアップする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd23f-157">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  
## <a name="validate"></a><span data-ttu-id="dd23f-158">検証</span><span class="sxs-lookup"><span data-stu-id="dd23f-158">Validate</span></span>

<span data-ttu-id="dd23f-159">検証のために、任意の Skype for Business クライアントを使用して、作成したアカウントにサインインできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd23f-159">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

