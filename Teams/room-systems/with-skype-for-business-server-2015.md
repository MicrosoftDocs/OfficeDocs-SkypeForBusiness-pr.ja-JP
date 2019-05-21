---
title: Microsoft Teams のルームを Skype for Business Server に展開する
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: このトピックでは、Skype for Business Server で Microsoft Teams のルームを展開する方法について説明します。
ms.openlocfilehash: a0e476738cb1ff68020b87624cbcdbabb220c248
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288445"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a><span data-ttu-id="9c731-103">Microsoft Teams のルームを Skype for Business Server に展開する</span><span class="sxs-lookup"><span data-stu-id="9c731-103">Deploy Microsoft Teams Rooms with Skype for Business Server</span></span>
  
<span data-ttu-id="9c731-104">このトピックでは、単一フォレストのオンプレミス展開を使用しているときに、Microsoft Teams ルームのデバイスアカウントを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9c731-104">This topic explains how you add a device account for Microsoft Teams Rooms when you have a single-forest, on-premises deployment.</span></span>
  
<span data-ttu-id="9c731-105">フォレストが1つのフォレスト、Exchange 2013 SP1 以降、および Skype for Business Server 2015 以降を搭載している場合は、提供されている Windows PowerShell スクリプトを使用して、デバイスアカウントを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="9c731-105">If you have a single-forest, on-premises deployment with Exchange 2013 SP1 or later and Skype for Business Server 2015 or later, then you can use the provided Windows PowerShell scripts to create device accounts.</span></span> <span data-ttu-id="9c731-106">複数フォレストの展開を使用している場合は、同じ結果を生成する同等のコマンドレットを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="9c731-106">If you're using a multi-forest deployment, you can use equivalent cmdlets that will produce the same results.</span></span> <span data-ttu-id="9c731-107">これらのコマンドレットについては、このセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="9c731-107">Those cmdlets are described in this section.</span></span>

  
<span data-ttu-id="9c731-108">Microsoft Teams ルームの展開を開始する前に、関連付けられたコマンドレットを実行する適切な権限があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9c731-108">Before you begin to deploy Microsoft Teams Rooms, be sure you have the right permissions to run the associated cmdlets.</span></span>
  

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

   <span data-ttu-id="9c731-109">$StrExchangeServer は Exchange server の完全修飾ドメイン名 (FQDN) であり、$strLyncFQDN は Skype for Business Server の展開の FQDN です。</span><span class="sxs-lookup"><span data-stu-id="9c731-109">Note that $strExchangeServer is the fully qualified domain name (FQDN) of your Exchange server, and $strLyncFQDN is the FQDN of your Skype for Business Server deployment.</span></span>

2. <span data-ttu-id="9c731-110">セッションを確立したら、新しいメールボックスを作成して、RoomMailboxAccount として有効にするか、既存の会議のメールボックスの設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="9c731-110">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="9c731-111">これにより、アカウントは Microsoft Teams のルームに対して認証されます。</span><span class="sxs-lookup"><span data-stu-id="9c731-111">This will allow the account to authenticate to Microsoft Teams Rooms.</span></span>

    <span data-ttu-id="9c731-112">既存のリソース メールボックスを変更している場合:</span><span class="sxs-lookup"><span data-stu-id="9c731-112">If you're changing an existing resource mailbox:</span></span>

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   <span data-ttu-id="9c731-113">新しいリソースメールボックスを作成する場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9c731-113">If you're creating a new resource mailbox:</span></span>

   ``` Powershell
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="9c731-114">デバイスアカウントのさまざまな Exchange プロパティを設定して、ユーザーの会議の操作性を向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="9c731-114">You can set various Exchange properties on the device account to improve the meeting experience for people.</span></span> <span data-ttu-id="9c731-115">設定する必要のあるプロパティは、「Exchange のプロパティ」セクションで確認できます。</span><span class="sxs-lookup"><span data-stu-id="9c731-115">You can see which properties need to be set in the Exchange properties section.</span></span>

   ``` Powershell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. <span data-ttu-id="9c731-116">パスワードの有効期限が切れないと判断した場合は、Windows PowerShell コマンドレットを使用して設定できます。</span><span class="sxs-lookup"><span data-stu-id="9c731-116">If you decide to have the password not expire, you can set that with Windows PowerShell cmdlets too.</span></span> <span data-ttu-id="9c731-117">詳細については、「パスワードの管理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c731-117">See Password management for more information.</span></span>

   ``` Powershell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. <span data-ttu-id="9c731-118">Active Directory でアカウントを有効にして、Microsoft Teams のルームに対して認証されるようにします。</span><span class="sxs-lookup"><span data-stu-id="9c731-118">Enable the account in Active Directory so it will authenticate to Microsoft Teams Rooms.</span></span>

   ``` Powershell
   Set-AdUser $acctUpn -Enabled $true
   ```

6. <span data-ttu-id="9c731-119">Skype for business Server プールで Microsoft Teams 会議の Active Directory アカウントを有効にして、Skype for Business Server でデバイスアカウントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="9c731-119">Enable the device account with Skype for Business Server by enabling your Microsoft Teams Rooms Active Directory account on a Skype for Business Server pool:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    <span data-ttu-id="9c731-120">セッション開始プロトコル (SIP) アドレスとプロジェクトのドメイン コントローラーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c731-120">You'll need to use the Session Initiation Protocol (SIP) address and domain controller for the Project</span></span>

7. <span data-ttu-id="9c731-121">**オプション。**</span><span class="sxs-lookup"><span data-stu-id="9c731-121">**Optional.**</span></span> <span data-ttu-id="9c731-122">また、アカウントのエンタープライズ Voip を有効にすることで、Microsoft Teams の会議通話の発信や受信を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="9c731-122">You can also allow Microsoft Teams Rooms to make and receive public switched telephone network (PSTN) phone calls by enabling Enterprise Voice for your account.</span></span> <span data-ttu-id="9c731-123">エンタープライズ Voip は Microsoft Teams のルームでは必要ありませんが、Microsoft Teams のルームクライアントで PSTN ダイヤル機能を使用する場合は、次のようにして有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="9c731-123">Enterprise Voice isn't a requirement for Microsoft Teams Rooms, but if you want PSTN dialing functionality for the Microsoft Teams Rooms client, here's how to enable it:</span></span>

   ``` Powershell
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   <span data-ttu-id="9c731-p106">繰り返しますが、提供されるドメイン コントローラーと電話番号の例は、実際に使用する情報に置き換える必要があります。パラメータ値 $true は同じままです。</span><span class="sxs-lookup"><span data-stu-id="9c731-p106">Again, you'll need to replace the provided domain controller and phone number examples with your own information. The parameter value $true stays the same.</span></span>

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a><span data-ttu-id="9c731-126">サンプル: Exchange および Skype for Business Server on it での room アカウントのセットアップ</span><span class="sxs-lookup"><span data-stu-id="9c731-126">Sample: room account setup in Exchange and Skype for Business Server on premises</span></span>

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

## <a name="see-also"></a><span data-ttu-id="9c731-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="9c731-127">See also</span></span>

[<span data-ttu-id="9c731-128">Microsoft Teams 室のアカウントを構成する</span><span class="sxs-lookup"><span data-stu-id="9c731-128">Configure accounts for Microsoft Teams Rooms</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="9c731-129">Microsoft Teams のルームを計画する</span><span class="sxs-lookup"><span data-stu-id="9c731-129">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)
  
[<span data-ttu-id="9c731-130">Microsoft Teams ルームの展開</span><span class="sxs-lookup"><span data-stu-id="9c731-130">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="9c731-131">Microsoft Teams 室コンソールを構成する</span><span class="sxs-lookup"><span data-stu-id="9c731-131">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="9c731-132">Microsoft Teams Rooms を管理する</span><span class="sxs-lookup"><span data-stu-id="9c731-132">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)
