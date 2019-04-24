---
title: Skype Room System ルームのセットアップ スクリプト
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a66067d2-22b0-48f1-a5d0-e0cd0ece2e5a
description: このトピックでは、Skype Room System アカウントをプロビジョニングするためのサンプル スクリプトの検索について説明します。
ms.openlocfilehash: 2032799059d59d1a99526a2b90630dd3c7b1cb3e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32219382"
---
# <a name="skype-room-system-room-setup-scripts"></a><span data-ttu-id="11c73-103">Skype Room System ルームのセットアップ スクリプト</span><span class="sxs-lookup"><span data-stu-id="11c73-103">Skype Room System room setup scripts</span></span>
 
<span data-ttu-id="11c73-104">このトピックでは、Skype Room System アカウントをプロビジョニングするためのサンプル スクリプトの検索について説明します。</span><span class="sxs-lookup"><span data-stu-id="11c73-104">Read this topic to find sample scripts for provisioning Skype Room System accounts.</span></span>
  
<span data-ttu-id="11c73-105">このセクションでは、Skype ルームのシステム アカウントのプロビジョニングに使用できるサンプル スクリプトについて説明します。</span><span class="sxs-lookup"><span data-stu-id="11c73-105">This section illustrates sample scripts that can be used to provision Skype Room System accounts.</span></span> <span data-ttu-id="11c73-106">これらのスクリプトは、説明の目的にのみ提供されており、使用する場合は必ず IT エキスパートまたはドメイン管理者に事前に相談してください。</span><span class="sxs-lookup"><span data-stu-id="11c73-106">These scripts are for illustrative purposes only and should be used only after consulting with your IT expert or domain administrator.</span></span>
  
## <a name="example-setup-script-skype-for-business-and-exchange-server-on-premises"></a><span data-ttu-id="11c73-107">ビジネスと (設置型) の Exchange Server のセットアップ スクリプトの例: Skype</span><span class="sxs-lookup"><span data-stu-id="11c73-107">Example Setup Script: Skype for Business and Exchange Server (On Premises)</span></span>

```
# On Exchange 
Set-Mailbox -Identity confroom@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a 
Lync Meeting to take advantage of enhanced meeting experience from LRS"

Set-CalendarProcessing -id confroom@contoso.com -RemovePrivateProperty $false -AddOrganizerToSubject $false -AddAdditionalResponse 
$true -AdditionalResponse "This is an LRS room!" -DeleteSubject $false -AutomateProcessing AutoAccept 
# The following is used to preserve the Lync Meeting invitations - so create these based on your Lync Federated partners# Per Lync Federated Partner as a Recommended Practice to ensure Meetings show in Lync with Join#New-RemoteDomain -DomainName Microsoft.com -Name Microsoft$true#Set-RemoteDomain -Identity Microsoft -TNEFEnabled $true
Set-ADAccountPassword -Identity "conference room"# Paste the next command on its own. Enter a blank password first, then enter the new password "password" twiceEnable-ADAccount -Identity "confroom"# On LyncEnable-CsMeetingRoom -SipAddress "sip:confroom@contoso.com" -RegistrarPool cie-srv-02.contoso.com -Identity 'conference room' 
Set-CsMeetingRoom -Identity "conference room" -LineURI "tel:+14255551669;ext=1669" -EnterpriseVoiceEnabled $true
```

## <a name="example-setup-script-skype-for-business-and-exchange-server-online"></a><span data-ttu-id="11c73-108">ビジネスおよび Exchange Server のオンラインの Skype をセットアップ スクリプトの例:</span><span class="sxs-lookup"><span data-stu-id="11c73-108">Example Setup Script: Skype for Business and Exchange Server Online</span></span>

<span data-ttu-id="11c73-109">スクリプトを実行する前に、次の前提条件を確認してください。</span><span class="sxs-lookup"><span data-stu-id="11c73-109">Make sure you've reviewed the following prerequisites before running the script:</span></span>
  
- <span data-ttu-id="11c73-110">Microsoft Online Services サインイン アシスタント (IT Professionals BETA 用)</span><span class="sxs-lookup"><span data-stu-id="11c73-110">Microsoft Online Services Sign-In Assistant for IT Professionals BETA</span></span>
    
- <span data-ttu-id="11c73-111">Windows PowerShell 用 Windows Azure Active Directory モジュール (64 ビット バージョン) または (32 ビット バージョン)</span><span class="sxs-lookup"><span data-stu-id="11c73-111">Windows Azure Active Directory Module for Windows PowerShell (64-bit version) or (32-bit version)</span></span>
    
- <span data-ttu-id="11c73-112">Lync Online 用 Windows PowerShell モジュール</span><span class="sxs-lookup"><span data-stu-id="11c73-112">Windows PowerShell Module for Lync Online</span></span>
    
- <span data-ttu-id="11c73-113">必要な場合は再起動します</span><span class="sxs-lookup"><span data-stu-id="11c73-113">Reboot if needed</span></span>
    
```
# Note you have to enter each command one at a time and update any bold fields for your environment
$rm="LyncRoom"
$org='YourTenantName.onmicrosoft.com'
$rmURI="$rm@$org"$newpass='MyPass@word1'# This Section Signs into Remote PowerShell
$cred=Get-Credential admin@$org
$sess=New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication basic -ConnectionUri https://ps.outlook.com/powershell
Import-PSSession $sess
Import-Module LyncOnlineConnector
$cssess=New-CsOnlineSession -Credential $cred
Import-PSSession $cssess -AllowClobber
Connect-MsolService -Credential $cred# This Section Create the Calendar Mailbox and Enables it for Lync
New-Mailbox -MicrosoftOnlineServicesID $rmURI -room -Name $rm -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
 -EnableRoomMailboxAccount $true

Set-CalendarProcessing -Identity $rmURI -DeleteSubject $false -AutomateProcessing AutoAccept 
Set-CalendarProcessing -Identity $rmURI -RemovePrivateProperty $false -AddOrganizerToSubject $false -AddAdditionalResponse $true -AdditionalResponse
 "This is an LRS room!"# Configure the Account to Not Expire
Set-MsolUser -UserPrincipalName $rm -PasswordNeverExpires $true# You need to detect your Lync Pool Registrar name. Using a normal Offic365/LyncOnline user account from your tenant, run the next command and update the RegistrarPool value for the second command coming up
Get-CsOnlineUser -Identity 'admin@YourTenantName.onmicrosoft.com' | fl *registrar*# Update with above result
Enable-CsMeetingRoom -Identity $rmURI -RegistrarPool "sippoolsn20a07.infra.lync.com" -SipAddressType EmailAddress
# If the previous command fails with an error regarding the account name not being found you might need to wait and try again in a few minutes. If you wait too long, you'll need to sign in again to remote PowerShell as detailed above.
```


