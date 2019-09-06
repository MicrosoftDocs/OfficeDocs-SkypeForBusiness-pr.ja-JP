---
title: Skype Room System アカウントの Office 365 でのプロビジョニング
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: このトピックでは、Office 365 に Skype Room System アカウントをプロビジョニングする方法について説明します。
ms.openlocfilehash: d247983647641c91376c99bed3a13606027a7e11
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "36775391"
---
# <a name="provisioning-skype-room-system-accounts-in-office-365"></a><span data-ttu-id="7f70e-103">Skype Room System アカウントの Office 365 でのプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="7f70e-103">Provisioning Skype Room System accounts in Office 365</span></span>
 
<span data-ttu-id="7f70e-104">このトピックでは、Office 365 に Skype Room System アカウントをプロビジョニングする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7f70e-104">Read this topic to learn about provisioning Skype Room System accounts in Office 365.</span></span>
  
<span data-ttu-id="7f70e-105">以下のセクションでは、Office 365 テナントでの Skype Room System アカウントのプロビジョニングについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7f70e-105">The following section covers Skype Room System account provisioning for an Office 365 tenant.</span></span>
  
## <a name="office-365-prerequisites"></a><span data-ttu-id="7f70e-106">Office 365 の前提条件</span><span class="sxs-lookup"><span data-stu-id="7f70e-106">Office 365 prerequisites</span></span>

<span data-ttu-id="7f70e-107">オンライン テナントは、次の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f70e-107">Your online tenant must meet the following requirements:</span></span>
  
- <span data-ttu-id="7f70e-108">Office 365 プランには、Skype for Business Online Plan 2、または Office 365 E1、E3、または E5 が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f70e-108">The Office 365 plan must include Skype for Business Online Plan 2, or Office 365 E1, E3 or E5.</span></span> <br/><span data-ttu-id="7f70e-109">Skype for Business Online プランの詳細については、「 [skype For Business Online サービスの説明](https://technet.microsoft.com/library/jj822172.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f70e-109">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>
    
- <span data-ttu-id="7f70e-110">テナントには、Skype for Business が有効になっている会議機能が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f70e-110">Your tenant must have the conferencing capability of Skype for Business enabled.</span></span>
    
- <span data-ttu-id="7f70e-111">テナントで、Exchange Online を有効にしていること。</span><span class="sxs-lookup"><span data-stu-id="7f70e-111">Your tenant must have Exchange Online enabled.</span></span> 
    
- <span data-ttu-id="7f70e-112">テナントのリモート管理者に次の PowerShell アクセス権があること。</span><span class="sxs-lookup"><span data-stu-id="7f70e-112">Your tenant remote administrator must have the following PowerShell access:</span></span>
    
  - <span data-ttu-id="7f70e-113">Exchange Remote PowerShell へのアクセス権</span><span class="sxs-lookup"><span data-stu-id="7f70e-113">Exchange Remote PowerShell access</span></span>
    
  - <span data-ttu-id="7f70e-114">Skype for Business Online のリモート PowerShell アクセス</span><span class="sxs-lookup"><span data-stu-id="7f70e-114">Skype for Business Online Remote PowerShell access</span></span>
    
  - <span data-ttu-id="7f70e-115">Office 365 ディレクトリアクセスにアクセスするための windows PowerShell 用 windows Azure Active Directory モジュール</span><span class="sxs-lookup"><span data-stu-id="7f70e-115">Windows Azure Active Directory Module for Windows PowerShell to access Office 365 directory access</span></span>
    
<span data-ttu-id="7f70e-116">Skype Room アカウントの場合は、次のライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="7f70e-116">For the Skype Room account, the following licensing is required:</span></span>
  
- <span data-ttu-id="7f70e-117">Skype 会議を有効にするには、Skype for Business Online プラン2または Office 365 E1 または E3 ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="7f70e-117">A Skype for Business Online Plan 2 or Office 365 E1 or E3 license is required to enable Skype Meetings.</span></span>
    
- <span data-ttu-id="7f70e-118">エンタープライズ Voip 機能を使用して部屋を entitle し、会議室を電話番号で有効にできるようにするには、電話システムライセンスまたは Office 365 E5 が含まれる Skype for Business Online プラン2が必要です (1)。</span><span class="sxs-lookup"><span data-stu-id="7f70e-118">To entitle the room with the Enterprise Voice capability so the room can be enabled with a phone number, a Skype for Business Online Plan 2 with the Phone System license or Office 365 E5 is required (1).</span></span>
    
- <span data-ttu-id="7f70e-119">会議からダイヤルイン機能が必要な場合は、電話会議と電話システムのライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="7f70e-119">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="7f70e-120">会議からダイヤルアウト機能が必要な場合は、国内または国内の通話プランが必要です。</span><span class="sxs-lookup"><span data-stu-id="7f70e-120">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span> 
    
- <span data-ttu-id="7f70e-121">Skype Room アカウントの場合は、リソース メールボックス アカウントとして構成する必要があるため、Exchange Online ライセンスは不要です。</span><span class="sxs-lookup"><span data-stu-id="7f70e-121">An Exchange Online license is not required for the Skype Room account because the account should be configured as a resource mailbox account.</span></span>
    
## <a name="provisioning-overview"></a><span data-ttu-id="7f70e-122">プロビジョニングの概要</span><span class="sxs-lookup"><span data-stu-id="7f70e-122">Provisioning overview</span></span>

<span data-ttu-id="7f70e-123">次の図は、Office 365 での Skype Room System アカウントのプロビジョニングフローの概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="7f70e-123">The following diagram provides an overview of the Skype Room System account provisioning flow in Office 365.</span></span>
  
![O365 の Skype Room System のプロビジョニング手順](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a><span data-ttu-id="7f70e-125">新しい会議ルームを特定する</span><span class="sxs-lookup"><span data-stu-id="7f70e-125">Identify a new conference room</span></span>

<span data-ttu-id="7f70e-126">スケジュール機能を提供している Exchange のリソースルームメールボックスが既に存在する可能性があります。または、Skype Room System の展開を容易にするために初めてリソースメールボックスを作成している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7f70e-126">You may already have a resource room mailbox in Exchange that provides the scheduling feature, or you may be creating a resource mailbox for the first time to facilitate Skype Room System deployment.</span></span> <span data-ttu-id="7f70e-127">いずれの場合も、テナントで使用するルーム アカウントを特定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f70e-127">In any case, you must identify a room account to be used in your tenant.</span></span> <span data-ttu-id="7f70e-128">Exchange Online のプロビジョニングと Skype for Business のプロビジョニングのセクションでは、両方のアカウントのガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="7f70e-128">The Exchange Online Provision and Skype for Business Provision sections provide guidance for both kinds of accounts.</span></span> <span data-ttu-id="7f70e-129">たとえば、次の2つのルームを持っていて、両方の部屋の Skype Room System を展開したいとします。</span><span class="sxs-lookup"><span data-stu-id="7f70e-129">For example, let's say you have the following two rooms, and you would like to deploy Skype Room System for both of them:</span></span>
  
- <span data-ttu-id="7f70e-130">既存のリソース メールボックス アカウント: confrm1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="7f70e-130">Existing Resource Mailbox Account: confrm1@contoso.onmicrosoft.com</span></span>
    
- <span data-ttu-id="7f70e-131">新しいリソース メールボックス アカウント: confrm2@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="7f70e-131">New Resource Mailbox Account: confrm2@contoso.onmicrosoft.com</span></span>
    
## <a name="exchange-online-provisioning"></a><span data-ttu-id="7f70e-132">Exchange Online のプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="7f70e-132">Exchange Online provisioning</span></span>

<span data-ttu-id="7f70e-133">まず、「 [Exchange Online powershell に接続する](https://go.microsoft.com/fwlink/p/?LinkId=396554)」の手順に従って、Exchange online powershell に接続します。</span><span class="sxs-lookup"><span data-stu-id="7f70e-133">First, connect to Exchange Online PowerShell by following the instructions in the topic, [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
  
<span data-ttu-id="7f70e-134">Skype Room System の既存のリソースルームメールボックスアカウントを設定するには、Exchange Online PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7f70e-134">To set an existing resource room mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="7f70e-135">Skype Room System の新しい Exchange リソースメールボックスアカウントを作成するには、Exchange Online PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7f70e-135">To create a new Exchange resource mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="7f70e-136">前のコマンドでは、アカウントを有効にすることによって、Skype Room システムの使用を目的とした新しい Exchange リソースメールボックスアカウントのセットアップまたは作成を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="7f70e-136">The previous commands set up or create a new Exchange resource mailbox account for Skype Room System usage by enabling the account.</span></span>
  
<span data-ttu-id="7f70e-137">メールボックスを作成した後で、Exchange Online PowerShell の設定-CalendarProcessing コマンドレットを使用して、メールボックスを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="7f70e-137">After creating the mailbox, you can use the Set-CalendarProcessing cmdlet in Exchange Online PowerShell to configure the mailbox.</span></span> <span data-ttu-id="7f70e-138">詳細については、単一フォレストのオンプレミス展開の手順 3 ～ 6 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f70e-138">Refer to steps 3 through 6 under Single forest on-premises deployments for more details</span></span>

## <a name="assigning-a-skype-for-business-online-license"></a><span data-ttu-id="7f70e-139">Skype for Business Online ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="7f70e-139">Assigning a Skype for Business Online license</span></span>

<span data-ttu-id="7f70e-140">「一般法人向け Office 365 または Skype for Business アドオン[のライセンスの割り当てまたは削除](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US)」の説明に従って、office 365 管理ポータルを使用して、Skype For business Online (プラン 2) または Skype For business Online (プラン 3) ライセンスを割り当てることができます。 [ライセンス](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)。</span><span class="sxs-lookup"><span data-stu-id="7f70e-140">Now you can assign a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license by using the Office 365 administrative portal as described in [Assign or remove licenses for Office 365 for business](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) or in [Skype for Business add-on licensing](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span></span> 
  
<span data-ttu-id="7f70e-141">Skype for Business Online のライセンスを割り当てると、ログインして、Skype for Business クライアントを使ってアカウントがアクティブであることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="7f70e-141">After you assign a license for Skype for Business Online, you will be able to log in and validate that the account is active using any Skype for Business client.</span></span>
  
## <a name="skype-for-business-online-provisioning"></a><span data-ttu-id="7f70e-142">Skype for Business Online のプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="7f70e-142">Skype for Business Online provisioning</span></span>

<span data-ttu-id="7f70e-143">前に説明したように、リソースルームメールボックスアカウントを作成して有効にした後、Skype for business Online のアカウントのライセンスが付与されている場合、アカウントは Exchange Online フォレストから Skype for Business Online フォレストに同期します。Windows Azure Active Directory フォレスト。</span><span class="sxs-lookup"><span data-stu-id="7f70e-143">After a resource room mailbox account has been created and enabled as shown previously, and you have licensed the account for Skype For Business Online the account will synchronize from the Exchange Online forest to Skype for Business Online forest by using the Windows Azure Active Directory forest.</span></span> <span data-ttu-id="7f70e-144">Skype for Business Online プールで Skype Room System アカウントをプロビジョニングするには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f70e-144">The following steps are required to provision the Skype Room System account in the Skype for Business Online pool.</span></span> <span data-ttu-id="7f70e-145">この手順は、既存のリソースメールボックスアカウントと新しく作成されたアカウント (confrm1 または confrm2) のどちらにも同じです。 Exchange Online で有効にすると、これらの両方のアカウントが同じ方法で Skype for Business Online と同期されるため、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="7f70e-145">These steps are the same for both an existing resource mailbox account or a newly created account (confrm1 or confrm2), because once they are enabled in Exchange Online, both of these accounts will be synchronized to Skype for Business Online in the same way:</span></span>
  
1. <span data-ttu-id="7f70e-146">リモート PowerShell セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="7f70e-146">Create a Remote PowerShell session.</span></span> <span data-ttu-id="7f70e-147">Skype for Business Online Connector モジュールと Microsoft Online Services サインインアシスタントをダウンロードして、コンピューターが構成されていることを確認する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7f70e-147">Note that you will need to download Skype for Business Online Connector Module and Microsoft Online Services Sign-In Assistant and make sure that your computer is configured.</span></span> <span data-ttu-id="7f70e-148">詳細については、「 [Windows PowerShell 用にコンピューターをセットアップする](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f70e-148">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
    
   ```
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="7f70e-149">Skype for Business の Skype Room System アカウントを有効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7f70e-149">To enable an Skype Room System account for Skype for Business, run the following command:</span></span>
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    <span data-ttu-id="7f70e-150">このプロパティを返すには、次のコマンドを使用して、Skype for Business ユーザーが既存のアカウントのいずれかに所属している RegistrarPool アドレスを取得できます。</span><span class="sxs-lookup"><span data-stu-id="7f70e-150">You can obtain the RegistrarPool address where your Skype for Business users are homed from one of your existing accounts by using the following command to returns this property:</span></span>
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

  
## <a name="password-expiration"></a><span data-ttu-id="7f70e-151">パスワードの有効期限</span><span class="sxs-lookup"><span data-stu-id="7f70e-151">Password expiration</span></span>

<span data-ttu-id="7f70e-152">Office 365 では、別のパスワードの有効期限ポリシーを構成しない限り、すべてのユーザー アカウントのパスワードの有効期限ポリシーは、既定で 90 日間です。</span><span class="sxs-lookup"><span data-stu-id="7f70e-152">In Office 365, the default password expiration policy for all of your user accounts is 90 days unless you configure a different password expiration policy.</span></span> <span data-ttu-id="7f70e-153">Skype Room System アカウントの場合は、次の手順に従って [無期限パスワード] 設定を選択できます。</span><span class="sxs-lookup"><span data-stu-id="7f70e-153">For Skype Room System accounts, you can select the Password never expires setting with the following steps.</span></span>
  
1. <span data-ttu-id="7f70e-154">管理者のグローバル資格情報を使用して、Windows Azure Active Directory セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="7f70e-154">Create a Windows Azure Active Directory session by using your tenant global administrator credentials.</span></span>
    
    ```
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. <span data-ttu-id="7f70e-155">次のコマンドを使用して、以前に作成した Skype Room System room アカウントのパスワードを無期限に設定します。</span><span class="sxs-lookup"><span data-stu-id="7f70e-155">Set the Password never expires setting for the Skype Room System room account created previously by using the following command:</span></span>
    
   ```
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

<span data-ttu-id="7f70e-156">詳細については、「 [Windows PowerShell 用にコンピューターをセットアップする](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f70e-156">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  
## <a name="validate"></a><span data-ttu-id="7f70e-157">有効性</span><span class="sxs-lookup"><span data-stu-id="7f70e-157">Validate</span></span>

<span data-ttu-id="7f70e-158">検証のために、Skype for Business クライアントを使って、作成したアカウントにサインインできるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f70e-158">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

