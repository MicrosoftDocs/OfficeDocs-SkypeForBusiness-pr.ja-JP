---
title: Skype for Business Server で Microsoft Teams Rooms を展開する
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: このトピックでは、Skype for Business Server を使用して Microsoft Teams Rooms を展開する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9ee33ec1ded7e8461f629c4552236ee60828a168
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662262"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a><span data-ttu-id="db1b0-103">Skype for Business Server で Microsoft Teams Rooms を展開する</span><span class="sxs-lookup"><span data-stu-id="db1b0-103">Deploy Microsoft Teams Rooms with Skype for Business Server</span></span>
  
<span data-ttu-id="db1b0-104">このトピックでは、単一フォレストのオンプレミス展開がある場合に Microsoft Teams Rooms のデバイス アカウントを追加する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="db1b0-104">This topic explains how you add a device account for Microsoft Teams Rooms when you have a single-forest, on-premises deployment.</span></span>
  
<span data-ttu-id="db1b0-105">単一つのフォレスト、Exchange 2013 SP1 以降のオンプレミス展開、および Skype for Business Server 2015 以降を使用している場合、提供されている Windows PowerShell スクリプトを使用してデバイスアカウントを作成できます。</span><span class="sxs-lookup"><span data-stu-id="db1b0-105">If you have a single-forest, on-premises deployment with Exchange 2013 SP1 or later and Skype for Business Server 2015 or later, then you can use the provided Windows PowerShell scripts to create device accounts.</span></span> <span data-ttu-id="db1b0-106">複数のフォレストを使用している場合は、同じ結果を生成する同じコマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="db1b0-106">If you're using a multi-forest deployment, you can use equivalent cmdlets that will produce the same results.</span></span> <span data-ttu-id="db1b0-107">ここでは、これらのツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="db1b0-107">Those cmdlets are described in this section.</span></span>

  
<span data-ttu-id="db1b0-108">Microsoft Teams Rooms の展開を開始する前に、関連するコマンドレットを実行するための適切な権限があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="db1b0-108">Before you begin to deploy Microsoft Teams Rooms, be sure you have the right permissions to run the associated cmdlets.</span></span>
  

   ``` Powershell
   Set-ExecutionPolicy Unrestricted
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sessExchange = New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication Kerberos -ConnectionUri
   "http://$strExchangeServer/powershell" -WarningAction SilentlyContinue
   $sessLync = New-PSSession -Credential $cred -ConnectionURI "https://$strLyncFQDN/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
   Import-PSSession $sessExchange
   Import-PSSession $sessLync
   ```

   <span data-ttu-id="db1b0-109">$strExchangeServer は Exchangeサーバー の完全修飾ドメイン名 (FQDN) で、$strLyncFQDN は Skype for Business Server展開のFQDNです。</span><span class="sxs-lookup"><span data-stu-id="db1b0-109">Note that $strExchangeServer is the fully qualified domain name (FQDN) of your Exchange server, and $strLyncFQDN is the FQDN of your Skype for Business Server deployment.</span></span>

2. <span data-ttu-id="db1b0-110">セッションを確立したら、新しいメールボックスを作成して RoomMailboxAccount として有効にするか、既存の会議室メールボックスの設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="db1b0-110">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="db1b0-111">これにより、アカウントは、Microsoft Teams Rooms に認証されます。</span><span class="sxs-lookup"><span data-stu-id="db1b0-111">This will allow the account to authenticate to Microsoft Teams Rooms.</span></span>

    <span data-ttu-id="db1b0-112">既存のリソースメールボックスを変更する場合：</span><span class="sxs-lookup"><span data-stu-id="db1b0-112">If you're changing an existing resource mailbox:</span></span>

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   <span data-ttu-id="db1b0-113">新しいリソース メールボックスを作成している場合:</span><span class="sxs-lookup"><span data-stu-id="db1b0-113">If you're creating a new resource mailbox:</span></span>

   ``` Powershell
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="db1b0-114">ユーザーの会議エクスペリエンスを改善するために、デバイス アカウントに対してさまざまなExchangeプロパティを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="db1b0-114">You can set various Exchange properties on the device account to improve the meeting experience for people.</span></span> <span data-ttu-id="db1b0-115">[Exchange プロパティ] セクションで設定する必要があるプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="db1b0-115">You can see which properties need to be set in the Exchange properties section.</span></span>

   ``` Powershell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. <span data-ttu-id="db1b0-116">パスワードを無期限にする場合は、Windows PowerShellコマンドレットでその設定を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="db1b0-116">If you decide to have the password not expire, you can set that with Windows PowerShell cmdlets too.</span></span> <span data-ttu-id="db1b0-117">詳細については、「パスワードの管理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db1b0-117">See Password management for more information.</span></span>

   ``` Powershell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. <span data-ttu-id="db1b0-118">Active Directory でアカウントを有効にし、Microsoft Teams Rooms に対して認証できるようにします。</span><span class="sxs-lookup"><span data-stu-id="db1b0-118">Enable the account in Active Directory so it will authenticate to Microsoft Teams Rooms.</span></span>

   ``` Powershell
   Set-AdUser $acctUpn -Enabled $true
   ```

6. <span data-ttu-id="db1b0-119">Skype for Business Server のプールで、Microsoft Teams Rooms Active Directoryアカウントを有効にしてから、Skype for Business Server を使用して、でデバイスアカウントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="db1b0-119">Enable the device account with Skype for Business Server by enabling your Microsoft Teams Rooms Active Directory account on a Skype for Business Server pool:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    <span data-ttu-id="db1b0-120">プロジェクトのセッション開始プロトコル (SIP) アドレスとドメインコントローラーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="db1b0-120">You'll need to use the Session Initiation Protocol (SIP) address and domain controller for the Project</span></span>

7. <span data-ttu-id="db1b0-121">**オプション。**</span><span class="sxs-lookup"><span data-stu-id="db1b0-121">**Optional.**</span></span> <span data-ttu-id="db1b0-122">アカウントのEnterprise Voice を有効にすることで、Microsoft Teams Rooms を使用して、公衆交換電話網 (PSTN) 通話を発着信することもできます。</span><span class="sxs-lookup"><span data-stu-id="db1b0-122">You can also allow Microsoft Teams Rooms to make and receive public switched telephone network (PSTN) phone calls by enabling Enterprise Voice for your account.</span></span> <span data-ttu-id="db1b0-123">Enterprise Voice は、Microsoft Teams Rooms では必要ありませんが、Microsoft Teams Rooms クライアントにPSTNダイアル機能を持たせたい場合は、次のようにしてください。</span><span class="sxs-lookup"><span data-stu-id="db1b0-123">Enterprise Voice isn't a requirement for Microsoft Teams Rooms, but if you want PSTN dialing functionality for the Microsoft Teams Rooms client, here's how to enable it:</span></span>

   ``` Powershell
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   <span data-ttu-id="db1b0-p106">繰り返しますが、提供されるドメイン コントローラーと電話番号の例は、実際に使用する情報に置き換える必要があります。パラメータ値 $true は同じままです。</span><span class="sxs-lookup"><span data-stu-id="db1b0-p106">Again, you'll need to replace the provided domain controller and phone number examples with your own information. The parameter value $true stays the same.</span></span>

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a><span data-ttu-id="db1b0-126">サンプル: Exchange およびオンプレミスの Skype for Business Serverの会議室アカウントのセットアップ</span><span class="sxs-lookup"><span data-stu-id="db1b0-126">Sample: room account setup in Exchange and Skype for Business Server on premises</span></span>

``` Powershell
New-Mailbox -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String "" -AsPlainText -Force)
-UserPrincipalName rigel1@contoso.com

Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false
-RemovePrivateProperty $false
Set-CalendarProcessing -Identity rigel1 -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"

Enable-CsMeetingRoom -Identity rigel1@contoso.com -RegistrarPool cs3.contoso.com -SipAddressType EmailAddress
Set-CsMeetingRoom -Identity rigel1 -EnterpriseVoiceEnabled $true -LineURI tel:+155555555555
Grant-CsVoicePolicy -PolicyName dk -Identity rigel1
Grant-CsDialPlan -PolicyName e15dp2.contoso.com -Identity rigel1
```

## <a name="related-topics"></a><span data-ttu-id="db1b0-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="db1b0-127">Related topics</span></span>

[<span data-ttu-id="db1b0-128">Microsoft Teams Rooms のアカウントを構成する</span><span class="sxs-lookup"><span data-stu-id="db1b0-128">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="db1b0-129">Microsoft Teams Rooms を計画する</span><span class="sxs-lookup"><span data-stu-id="db1b0-129">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="db1b0-130">Microsoft Teams Rooms をデプロイする</span><span class="sxs-lookup"><span data-stu-id="db1b0-130">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="db1b0-131">Microsoft Teams Rooms コンソールを構成する</span><span class="sxs-lookup"><span data-stu-id="db1b0-131">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="db1b0-132">Microsoft Teams Rooms を管理する</span><span class="sxs-lookup"><span data-stu-id="db1b0-132">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)
