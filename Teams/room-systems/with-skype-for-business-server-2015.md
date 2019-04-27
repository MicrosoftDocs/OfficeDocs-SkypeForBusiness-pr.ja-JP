---
title: Skype でマイクロソフトのチームの会議室をビジネス サーバーの展開します。
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: ビジネス サーバー用 Skype でマイクロソフト チームの会議室を展開する方法の詳細については、このトピックを参照してください。
ms.openlocfilehash: f047eceedba698d186490aa80646aa21b44c1e2d
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2019
ms.locfileid: "33362904"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a><span data-ttu-id="813b5-103">Skype でマイクロソフトのチームの会議室をビジネス サーバーの展開します。</span><span class="sxs-lookup"><span data-stu-id="813b5-103">Deploy Microsoft Teams Rooms with Skype for Business Server</span></span>
  
<span data-ttu-id="813b5-104">このトピックでは、マイクロソフト チームの会議室のデバイスのアカウントを追加する方法、単一フォレストでは、設置型の展開がある場合について説明します。</span><span class="sxs-lookup"><span data-stu-id="813b5-104">This topic explains how you add a device account for Microsoft Teams Rooms when you have a single-forest, on-premises deployment.</span></span>
  
<span data-ttu-id="813b5-105">単一フォレスト、Exchange 2013 の sp1 またはそれ以降の設置型展開および Skype ビジネス サーバー 2015 またはそれ以降がある場合は場合、は、デバイスのアカウントを作成するのには、指定された Windows PowerShell スクリプトを使用できます。</span><span class="sxs-lookup"><span data-stu-id="813b5-105">If you have a single-forest, on-premises deployment with Exchange 2013 SP1 or later and Skype for Business Server 2015 or later, then you can use the provided Windows PowerShell scripts to create device accounts.</span></span> <span data-ttu-id="813b5-106">マルチ フォレスト展開を使用する場合は、同じ結果を生成すると同等のコマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="813b5-106">If you're using a multi-forest deployment, you can use equivalent cmdlets that will produce the same results.</span></span> <span data-ttu-id="813b5-107">これらのコマンドレットは、このセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="813b5-107">Those cmdlets are described in this section.</span></span>

  
<span data-ttu-id="813b5-108">マイクロソフト チームの会議室を展開する作業を開始する前に、関連付けられているコマンドレットを実行する適切なアクセス許可があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="813b5-108">Before you begin to deploy Microsoft Teams Rooms, be sure you have the right permissions to run the associated cmdlets.</span></span>
  

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

   <span data-ttu-id="813b5-109">$StrExchangeServer は、Exchange サーバーの完全修飾ドメイン名 (FQDN)、$strLyncFQDN は、ビジネスのサーバーの展開に、Skype の FQDN を確認します。</span><span class="sxs-lookup"><span data-stu-id="813b5-109">Note that $strExchangeServer is the fully qualified domain name (FQDN) of your Exchange server, and $strLyncFQDN is the FQDN of your Skype for Business Server deployment.</span></span>

2. <span data-ttu-id="813b5-110">セッションを確立するには後、するが新しいメールボックスを作成して、RoomMailboxAccount、として有効にか既存の会議室メールボックスの設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="813b5-110">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="813b5-111">これにより、マイクロソフトのチームの会議室への認証にアカウントが許可されます。</span><span class="sxs-lookup"><span data-stu-id="813b5-111">This will allow the account to authenticate to Microsoft Teams Rooms.</span></span>

    <span data-ttu-id="813b5-112">既存のリソース メールボックスを変更している場合:</span><span class="sxs-lookup"><span data-stu-id="813b5-112">If you're changing an existing resource mailbox:</span></span>

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   <span data-ttu-id="813b5-113">: 新しいリソース メールボックスを作成する場合</span><span class="sxs-lookup"><span data-stu-id="813b5-113">If you're creating a new resource mailbox:</span></span>

   ``` Powershell
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="813b5-114">人の会議エクスペリエンスを向上させるためにデバイスのアカウントには、Exchange のさまざまなプロパティを設定できます。</span><span class="sxs-lookup"><span data-stu-id="813b5-114">You can set various Exchange properties on the device account to improve the meeting experience for people.</span></span> <span data-ttu-id="813b5-115">設定する必要のあるプロパティは、「Exchange のプロパティ」セクションで確認できます。</span><span class="sxs-lookup"><span data-stu-id="813b5-115">You can see which properties need to be set in the Exchange properties section.</span></span>

   ``` Powershell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. <span data-ttu-id="813b5-116">無期限のパスワードを入力する場合も Windows PowerShell コマンドレットを設定できます。</span><span class="sxs-lookup"><span data-stu-id="813b5-116">If you decide to have the password not expire, you can set that with Windows PowerShell cmdlets too.</span></span> <span data-ttu-id="813b5-117">詳細については、「パスワードの管理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="813b5-117">See Password management for more information.</span></span>

   ``` Powershell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. <span data-ttu-id="813b5-118">マイクロソフト チームの会議室に、認証は、Active Directory のアカウントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="813b5-118">Enable the account in Active Directory so it will authenticate to Microsoft Teams Rooms.</span></span>

   ``` Powershell
   Set-AdUser $acctUpn -Enabled $true
   ```

6. <span data-ttu-id="813b5-119">ビジネス サーバー プールのため、Skype でマイクロソフト チーム ルームの Active Directory アカウントを有効にすると、Business Server の Skype でデバイスのアカウントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="813b5-119">Enable the device account with Skype for Business Server by enabling your Microsoft Teams Rooms Active Directory account on a Skype for Business Server pool:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    <span data-ttu-id="813b5-120">セッション開始プロトコル (SIP) アドレスとプロジェクトのドメイン コントローラーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="813b5-120">You'll need to use the Session Initiation Protocol (SIP) address and domain controller for the Project</span></span>

7. <span data-ttu-id="813b5-121">**オプション。**</span><span class="sxs-lookup"><span data-stu-id="813b5-121">**Optional.**</span></span> <span data-ttu-id="813b5-122">マイクロソフト チームの会議室になり、公衆交換電話網 (PSTN) 電話でお使いのアカウントでエンタープライズ VoIP を有効にすることも可能です。</span><span class="sxs-lookup"><span data-stu-id="813b5-122">You can also allow Microsoft Teams Rooms to make and receive public switched telephone network (PSTN) phone calls by enabling Enterprise Voice for your account.</span></span> <span data-ttu-id="813b5-123">エンタープライズ VoIP がマイクロソフト チームの会議室の要件はありませんが、PSTN のダイヤル機能をマイクロソフト チームの会議室のクライアントの使用すると、それを有効にする方法です。</span><span class="sxs-lookup"><span data-stu-id="813b5-123">Enterprise Voice isn't a requirement for Microsoft Teams Rooms, but if you want PSTN dialing functionality for the Microsoft Teams Rooms client, here's how to enable it:</span></span>

   ``` Powershell
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   <span data-ttu-id="813b5-p106">繰り返しますが、提供されるドメイン コントローラーと電話番号の例は、実際に使用する情報に置き換える必要があります。パラメータ値 $true は同じままです。</span><span class="sxs-lookup"><span data-stu-id="813b5-p106">Again, you'll need to replace the provided domain controller and phone number examples with your own information. The parameter value $true stays the same.</span></span>

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a><span data-ttu-id="813b5-126">Exchange およびビジネス上のサーバー設置型の Skype のサンプル: ルームのアカウントのセットアップ</span><span class="sxs-lookup"><span data-stu-id="813b5-126">Sample: room account setup in Exchange and Skype for Business Server on premises</span></span>

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

## <a name="see-also"></a><span data-ttu-id="813b5-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="813b5-127">See also</span></span>

[<span data-ttu-id="813b5-128">マイクロソフト チームの会議室のアカウントを構成します。</span><span class="sxs-lookup"><span data-stu-id="813b5-128">Configure accounts for Microsoft Teams Rooms</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="813b5-129">マイクロソフト チームの会議室のプラン</span><span class="sxs-lookup"><span data-stu-id="813b5-129">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)
  
[<span data-ttu-id="813b5-130">マイクロソフト チームの会議室を配置します。</span><span class="sxs-lookup"><span data-stu-id="813b5-130">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="813b5-131">マイクロソフト チームの会議室のコンソールを構成します。</span><span class="sxs-lookup"><span data-stu-id="813b5-131">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="813b5-132">Microsoft Teams Rooms を管理する</span><span class="sxs-lookup"><span data-stu-id="813b5-132">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)