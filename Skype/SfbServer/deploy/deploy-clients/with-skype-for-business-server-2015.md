---
title: Skype Room Systems バージョン 2 と Skype for Business Server 2015 を展開する
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/18/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: ビジネス サーバー 2015 の Skype と Skype ルーム システム v2 を展開する方法の詳細については、このトピックを参照してください。
ms.openlocfilehash: 49d52b866c210554d66bf7cd9f59d1b5d8539070
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="deploy-skype-room-systems-v2-with-skype-for-business-server-2015"></a><span data-ttu-id="5471c-103">Skype Room Systems バージョン 2 と Skype for Business Server 2015 を展開する</span><span class="sxs-lookup"><span data-stu-id="5471c-103">Deploy Skype Room Systems v2 with Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5471c-104">ビジネス サーバー 2015 の Skype と Skype ルーム システム v2 を展開する方法の詳細については、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5471c-104">Read this topic for information on how to deploy Skype Room Systems v2 with Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="5471c-105">このトピックでは、単一フォレストでは、設置型の展開がある場合に Skype ルーム システムのバージョン 2 のデバイスのアカウントを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5471c-105">This topic explains how you add a device account for Skype Room Systems v2 when you have a single-forest, on-premises deployment.</span></span>
  
<span data-ttu-id="5471c-106">単一フォレスト、Exchange 2013 の sp1 またはそれ以降の設置型展開および Skype ビジネス サーバー 2015 またはそれ以降がある場合は場合、は、デバイスのアカウントを作成するのには、指定された Windows PowerShell スクリプトを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5471c-106">If you have a single-forest, on-premises deployment with Exchange 2013 SP1 or later and Skype for Business Server 2015 or later, then you can use the provided Windows PowerShell scripts to create device accounts.</span></span> <span data-ttu-id="5471c-107">マルチ フォレスト展開を使用する場合は、同じ結果を生成すると同等のコマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5471c-107">If you're using a multi-forest deployment, you can use equivalent cmdlets that will produce the same results.</span></span> <span data-ttu-id="5471c-108">これらのコマンドレットは、このセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="5471c-108">Those cmdlets are described in this section.</span></span>
  
## <a name="deploy-skype-room-systems-v2-with-skype-for-business-server-2015"></a><span data-ttu-id="5471c-109">Skype Room Systems バージョン 2 と Skype for Business Server 2015 を展開する</span><span class="sxs-lookup"><span data-stu-id="5471c-109">Deploy Skype Room Systems v2 with Skype for Business Server 2015</span></span>

<span data-ttu-id="5471c-110">ビジネス サーバー 2015 の Skype と Skype ルーム システム v2 を展開する前に、要件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="5471c-110">Before you deploy Skype Room Systems v2 with Skype for Business Server 2015, be sure you have met the requirements.</span></span> <span data-ttu-id="5471c-111">詳細については、 [Skype ルーム システム v2 の要件](../../plan-your-deployment/clients-and-devices/requirements.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5471c-111">For more information, see [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>
  
<span data-ttu-id="5471c-112">Skype ルーム システム v2 を展開する作業を開始する前に、関連付けられているコマンドレットを実行する適切なアクセス許可があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5471c-112">Before you begin to deploy Skype Room Systems v2, be sure you have the right permissions to run the associated cmdlets.</span></span>
  
1. <span data-ttu-id="5471c-113">PC からリモートの Windows PowerShell セッションを開始し、Exchange に接続します。</span><span class="sxs-lookup"><span data-stu-id="5471c-113">Start a remote Windows PowerShell session from a PC and connect to Exchange.</span></span> 
    
   ```
   Set-ExecutionPolicy Unrestricted
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sessExchange = New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication Kerberos -ConnectionUri
   "http://$strExchangeServer/powershell" -WarningAction SilentlyContinue
   $sessLync = New-PSSession -Credential $cred -ConnectionURI "https://$strLyncFQDN/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
   Import-PSSession $sessExchange
   Import-PSSession $sessLync
 
   ```

   <span data-ttu-id="5471c-114">$StrExchangeServer は、Exchange サーバーの完全修飾ドメイン名 (FQDN)、$strLyncFQDN は、サーバー 2015 のビジネスを展開するため、Skype の FQDN を確認します。</span><span class="sxs-lookup"><span data-stu-id="5471c-114">Note that $strExchangeServer is the fully qualified domain name (FQDN) of your Exchange server, and $strLyncFQDN is the FQDN of your Skype for Business Server 2015 deployment.</span></span>
    
2. <span data-ttu-id="5471c-115">セッションを確立するには後、するが新しいメールボックスを作成して、RoomMailboxAccount、として有効にか既存の会議室メールボックスの設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="5471c-115">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="5471c-116">これにより、Skype ルーム システム v2 を認証するためにアカウントが許可されます。</span><span class="sxs-lookup"><span data-stu-id="5471c-116">This will allow the account to authenticate to Skype Room Systems v2.</span></span>
    
    <span data-ttu-id="5471c-117">既存のリソース メールボックスを変更している場合:</span><span class="sxs-lookup"><span data-stu-id="5471c-117">If you're changing an existing resource mailbox:</span></span>
    
   ```
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   <span data-ttu-id="5471c-118">: 新しいリソース メールボックスを作成する場合</span><span class="sxs-lookup"><span data-stu-id="5471c-118">If you're creating a new resource mailbox:</span></span>
    
   ```
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room 
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="5471c-119">人の会議エクスペリエンスを向上させるためにデバイスのアカウントには、Exchange のさまざまなプロパティを設定できます。</span><span class="sxs-lookup"><span data-stu-id="5471c-119">You can set various Exchange properties on the device account to improve the meeting experience for people.</span></span> <span data-ttu-id="5471c-120">設定する必要のあるプロパティは、「Exchange のプロパティ」セクションで確認できます。</span><span class="sxs-lookup"><span data-stu-id="5471c-120">You can see which properties need to be set in the Exchange properties section.</span></span>
    
   ```
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments 
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. <span data-ttu-id="5471c-121">無期限のパスワードを入力する場合も Windows PowerShell コマンドレットを設定できます。</span><span class="sxs-lookup"><span data-stu-id="5471c-121">If you decide to have the password not expire, you can set that with Windows PowerShell cmdlets too.</span></span> <span data-ttu-id="5471c-122">詳細については、「パスワードの管理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5471c-122">See Password management for more information.</span></span>
    
   ```
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. <span data-ttu-id="5471c-123">Skype ルーム システム v2 を認証するために Active Directory のアカウントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="5471c-123">Enable the account in Active Directory so it will authenticate to Skype Room Systems v2.</span></span>
    
   ```
   Set-AdUser $acctUpn -Enabled $true
   ```

6. <span data-ttu-id="5471c-124">ビジネス サーバー 2015 のプールのため、Skype の Skype ルーム システム v2 Active Directory アカウントを有効にすると、ビジネス サーバー 2015 の Skype でデバイスのアカウントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="5471c-124">Enable the device account with Skype for Business Server 2015 by enabling your Skype Room Systems v2 Active Directory account on a Skype for Business Server 2015 pool:</span></span>
    
   ```
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com 
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    <span data-ttu-id="5471c-125">セッション開始プロトコル (SIP) アドレスとプロジェクトのドメイン コントローラーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5471c-125">You'll need to use the Session Initiation Protocol (SIP) address and domain controller for the Project</span></span> 
    
7. <span data-ttu-id="5471c-126">**オプション。**</span><span class="sxs-lookup"><span data-stu-id="5471c-126">**Optional.**</span></span> <span data-ttu-id="5471c-127">Skype ルーム システムの v2 になり、公衆交換電話網 (PSTN) 電話でお使いのアカウントでエンタープライズ VoIP を有効にすることも可能です。</span><span class="sxs-lookup"><span data-stu-id="5471c-127">You can also allow Skype Room Systems v2 to make and receive public switched telephone network (PSTN) phone calls by enabling Enterprise Voice for your account.</span></span> <span data-ttu-id="5471c-128">エンタープライズ VoIP Skype ルーム システム v2 では、必要のないが、PSTN のダイヤル機能を Skype ルーム システムのバージョン 2 のクライアントの使用すると、それを有効にする方法です。</span><span class="sxs-lookup"><span data-stu-id="5471c-128">Enterprise Voice isn't a requirement for Skype Room Systems v2, but if you want PSTN dialing functionality for the Skype Room Systems v2 client, here's how to enable it:</span></span>
    
   ```
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01

   ```

   <span data-ttu-id="5471c-p107">繰り返しますが、提供されるドメイン コントローラーと電話番号の例は、実際に使用する情報に置き換える必要があります。パラメータ値 $true は同じままです。</span><span class="sxs-lookup"><span data-stu-id="5471c-p107">Again, you'll need to replace the provided domain controller and phone number examples with your own information. The parameter value $true stays the same.</span></span>
    
## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-2015-on-premises"></a><span data-ttu-id="5471c-131">Exchange との社内のビジネス サーバー 2015 の Skype のサンプル: ルームのアカウントのセットアップ</span><span class="sxs-lookup"><span data-stu-id="5471c-131">Sample: room account setup in Exchange and Skype for Business Server 2015 on premises</span></span>

```
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

## <a name="see-also"></a><span data-ttu-id="5471c-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="5471c-132">See also</span></span>

#### 

[<span data-ttu-id="5471c-133">Skype ルームの計画システム v2</span><span class="sxs-lookup"><span data-stu-id="5471c-133">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="5471c-134">Skype の部屋を配置するシステム v2</span><span class="sxs-lookup"><span data-stu-id="5471c-134">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="5471c-135">Skype ルーム システム v2 のコンソールを構成します。</span><span class="sxs-lookup"><span data-stu-id="5471c-135">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="5471c-136">Skype ルームの管理システム v2</span><span class="sxs-lookup"><span data-stu-id="5471c-136">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

