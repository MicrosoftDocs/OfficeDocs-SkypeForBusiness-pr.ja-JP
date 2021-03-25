---
title: Skype Room System の単一フォレストのオンプレミス展開
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
ms.assetid: 80da9d71-3dcd-4ca4-8bd1-6d8196823206
description: 単一フォレストのオンプレミス環境に Skype Room System を展開する方法については、このトピックを参照してください。
ms.openlocfilehash: df213b24ef3400aa5551a090d2dd218d05794988
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120326"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a><span data-ttu-id="e2efa-103">Skype Room System の単一フォレストのオンプレミス展開</span><span class="sxs-lookup"><span data-stu-id="e2efa-103">Skype Room System single forest on-premises deployments</span></span>
 
<span data-ttu-id="e2efa-104">単一フォレストのオンプレミス環境に Skype Room System を展開する方法については、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2efa-104">Read this topic to learn how to deploy Skype Room System in a single forest on-premises environment.</span></span>
  
<span data-ttu-id="e2efa-105">このセクションでは、単一フォレストのオンプレミス展開でホストされている Exchange Server および Skype for Business Server で Skype Room System アカウントをプロビジョニングする手順の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="e2efa-105">This section provides an overview of the steps for provisioning the Skype Room System account on Exchange Server and Skype for Business Server hosted in a single forest on-premises deployment.</span></span>
  
## <a name="single-forest-on-premises-deployments"></a><span data-ttu-id="e2efa-106">単一フォレスト オンプレミスの展開</span><span class="sxs-lookup"><span data-stu-id="e2efa-106">Single forest on-premises deployments</span></span>

<span data-ttu-id="e2efa-107">会議室のリソース メールボックス アカウントが既に存在する場合は、そのアカウントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e2efa-107">If you already have a resource mailbox account for the conferencing room, you can use it.</span></span> <span data-ttu-id="e2efa-108">それ以外の場合は、新しい作成が必要です。</span><span class="sxs-lookup"><span data-stu-id="e2efa-108">Otherwise, you will need to create a new one.</span></span> <span data-ttu-id="e2efa-109">Exchange 管理シェル (PowerShell) または管理者を使用してExchange 管理コンソールリソース メールボックス アカウントを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e2efa-109">You can use either Exchange Management Shell (PowerShell) or Exchange Management Console to create a new resource mailbox account.</span></span> <span data-ttu-id="e2efa-110">Skype Room System の新しい (古いメールボックスを削除して、再作成する) リソース メールボックスを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e2efa-110">We recommend using a new (delete old mailbox and re-create) resource mailbox for Skype Room System.</span></span> <span data-ttu-id="e2efa-111">削除する前にメールボックス データをバックアップし、Outlook クライアントを使用して再作成したメールボックスにエクスポートし戻してください (詳細については、「メッセージ、予定表、タスク、連絡先をエクスポートまたはバックアップする」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="e2efa-111">Make sure to back up mailbox data before deleting and then export it back to the re-created mailbox using the Outlook client (see Export or back up messages, calendar, tasks, and contacts for more information).</span></span> <span data-ttu-id="e2efa-112">メールボックスを削除して失われた会議を復元するには、「削除されたメールボックスを接続または復元 [する」を参照してください](/exchange/connect-or-restore-a-deleted-mailbox-exchange-2013-help)。</span><span class="sxs-lookup"><span data-stu-id="e2efa-112">To restore the meetings lost by deleting the mailbox, see [Connect or restore a deleted mailbox](/exchange/connect-or-restore-a-deleted-mailbox-exchange-2013-help).</span></span> 
  
<span data-ttu-id="e2efa-113">既存のリソース メールボックス アカウント (LRS-01 など) を使用するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="e2efa-113">To use an existing resource mailbox account (for example, LRS-01) follow the steps below:</span></span>
  
1. <span data-ttu-id="e2efa-114">次の Exchange 管理 PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e2efa-114">Run the following Exchange Management PowerShell command:</span></span>
    
   ```powershell
   Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

2. <span data-ttu-id="e2efa-115">新しいメールボックスを作成する予定の場合は、単一のフォレストのオンプレミス Exchange 組織に対して、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e2efa-115">If you plan to create a new mailbox, then, for a single forest on-premises Exchange organization, run the following command:</span></span>
    
   ```powershell
   New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   <span data-ttu-id="e2efa-116">上記の例では、Active Directory に有効なユーザー アカウントと、オンプレミスの Exchange 組織の会議室用の会議室メールボックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="e2efa-116">The above example creates an enabled user account in Active Directory and a room mailbox for a conference room in an on-premises Exchange organization.</span></span> <span data-ttu-id="e2efa-117">RoomMailboxPassword パラメーターは、ユーザー アカウントのパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="e2efa-117">The RoomMailboxPassword parameter specifies the password for the user account.</span></span>
    
3. <span data-ttu-id="e2efa-118">会議を受け入れる/拒否することで、競合を自動的に解決するアカウントを構成します。</span><span class="sxs-lookup"><span data-stu-id="e2efa-118">Configure the account to automatically resolve conflicts by accepting/rejecting meetings.</span></span> <span data-ttu-id="e2efa-119">Exchange の Skype Room System に装備された会議室アカウントは、個人が管理できますが、個人が会議を受け入れるまで、Skype Room System のホーム画面カレンダーには表示されません。</span><span class="sxs-lookup"><span data-stu-id="e2efa-119">Skype Room System-equipped conference room accounts in Exchange can be managed by individuals, but note that until the individual accepts a meeting it will not appear on the Skype Room System home screen calendar.</span></span>
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   <span data-ttu-id="e2efa-120">使用可能なコマンドの完全なセットについては、「Set-CalendarProcessing」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2efa-120">For a complete set of commands available, see Set-CalendarProcessing.</span></span>
    
   <span data-ttu-id="e2efa-121">Outlook で会議をオンラインの Skype for Business 会議に設定する会議の開催者に通知するには、次のコマンドを実行して、新しいアカウントのメール ヒントを設定します。</span><span class="sxs-lookup"><span data-stu-id="e2efa-121">To remind meeting organizers to make the meeting an online Skype for Business meeting in Outlook, run the following command to set up a MailTip for the new account:</span></span> 
    
   ```powershell
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. <span data-ttu-id="e2efa-122">ローカライズされた文字列を構成するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="e2efa-122">Use the following commands to configure localized strings.</span></span> <span data-ttu-id="e2efa-123">組織で必要な場合は、カスタム翻訳を追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="e2efa-123">If required by your organization, you can also add custom translations:</span></span> 
   ```powershell
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. <span data-ttu-id="e2efa-124">省略可能: Skype for Business Meeting Room に関する情報と、会議のスケジュールと参加時にユーザーが期待する内容をユーザーに提供する会議の受け入れテキストを構成します。</span><span class="sxs-lookup"><span data-stu-id="e2efa-124">Optional: Configure meeting acceptance text that provides users with information about Skype for Business Meeting Room, and what to expect when they schedule and join meetings.</span></span> 
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a><span data-ttu-id="e2efa-125">Active Directory でリソース メールボックス アカウントを確認する</span><span class="sxs-lookup"><span data-stu-id="e2efa-125">Check Resource Mailbox Account in Active Directory</span></span>

<span data-ttu-id="e2efa-126">上記の手順 1 で Exchange によって作成された会議室メールボックス アカウントは、Active Directory の無効なユーザー オブジェクトである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e2efa-126">The conference room mailbox account created by Exchange in step 1 above might be a disabled user object in Active Directory.</span></span> <span data-ttu-id="e2efa-127">アカウントが Active Directory で無効になっている場合、Skype Room System は Kerberos/NTLM 認証を使用してサインインまたは認証できません。</span><span class="sxs-lookup"><span data-stu-id="e2efa-127">Skype Room System cannot sign in or authenticate by using Kerberos/NTLM authentication if the account is disabled in Active Directory.</span></span> <span data-ttu-id="e2efa-128">Skype Room System クライアントは、予定表の設定を取得するために Exchange Web サービスに対して認証できる必要があります。また、ホワイトボードの内容を含む電子メールを送信できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2efa-128">The Skype Room System client must be able to authenticate against Exchange Web Services to retrieve calendar settings, and must also be able to send email with whiteboard contents.</span></span> 
  
<span data-ttu-id="e2efa-129">したがって、アカウントが無効になっている場合は、次の手順を実行して Active Directory でこのアカウントを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2efa-129">Therefore, if the account is disabled, you must enable this account in Active Directory by doing the following:</span></span> 
  
1. <span data-ttu-id="e2efa-130">Active Directory で、次のコマンドを実行してアカウント ログオンを有効にします。</span><span class="sxs-lookup"><span data-stu-id="e2efa-130">In Active Directory, run the following command to enable account log on:</span></span> 
    
   ```powershell
   Set-ADAccountPassword -Identity LRS01
   ```

   <span data-ttu-id="e2efa-131">このコマンドを実行すると、現在のパスワードを入力し、確認のためにパスワードを 2 回再入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="e2efa-131">Running this command will prompt you to enter the current password, and then to re-enter the password twice for confirmation.</span></span>
    
2. <span data-ttu-id="e2efa-132">パスワードを設定したら、次のコマンドを実行してアカウントを有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="e2efa-132">Once the password is set, run the following command to enable the account:</span></span> 
    
   ```powershell
   Enable-ADAccount -Identity LRS01
   ```

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a><span data-ttu-id="e2efa-133">Skype for Business の Skype ルーム システム アカウントの有効化</span><span class="sxs-lookup"><span data-stu-id="e2efa-133">Enabling Skype Room System Accounts for Skype for Business</span></span>

<span data-ttu-id="e2efa-134">このセクションでは、Skype Room System で構成される会議室アカウントで Skype for Business を有効にするために必要な手順の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="e2efa-134">This section provides an overview of the steps required to enable Skype for Business for your conference room account, which will be configured on Skype Room System.</span></span> 
  
<span data-ttu-id="e2efa-135">会議ルームのリソース メールボックス アカウントを作成した後、Skype for Business Server 管理シェルを使用して Skype for Business サービスの Skype Room System アカウントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="e2efa-135">After you create a resource mailbox account for the conferencing rooms, use Skype for Business Server Management Shell to enable Skype Room System accounts for Skype for Business services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e2efa-136">次の手順では、Active Directory で Skype Room System アカウントを有効にしたと仮定します。</span><span class="sxs-lookup"><span data-stu-id="e2efa-136">The following procedure assumes that you have enabled the Skype Room System account in Active Directory.</span></span> 
  
1. <span data-ttu-id="e2efa-137">次のコマンドを実行して、Skype for Business Server プールで Skype Room System アカウントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="e2efa-137">Run the following command to enable the Skype Room System account on a Skype for Business Server pool:</span></span>
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. <span data-ttu-id="e2efa-138">省略可能: このアカウントが PSTN 電話の発信および受信を許可するには、このアカウントのアカウントを有効にエンタープライズ VoIP。</span><span class="sxs-lookup"><span data-stu-id="e2efa-138">Optional: Allow this account to make and receive PSTN phone calls by enabling the account for Enterprise Voice.</span></span> <span data-ttu-id="e2efa-139">エンタープライズ VoIP Skype ルーム システムでは必須ではありませんが、エンタープライズ VoIP で有効にしない場合、Skype Room System クライアントは PSTN ダイヤル機能を提供できます。</span><span class="sxs-lookup"><span data-stu-id="e2efa-139">Enterprise Voice is not required for Skype Room System, but if you do not enable it for Enterprise Voice, the Skype Room System client won't be able to provide PSTN dialing functionality:</span></span>
    
   ```powershell
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="e2efa-140">Skype Room System エンタープライズ VoIPアカウントに対して有効にする場合は、組織に適した制限付き音声ポリシーを構成してください。</span><span class="sxs-lookup"><span data-stu-id="e2efa-140">If you enable Enterprise Voice for the Skype Room System conference room account, make sure to configure a restricted Voice Policy suitable for your organization.</span></span> <span data-ttu-id="e2efa-141">Skype for Business Meeting Room が一般に公開されているリソースである場合、誰でもスケジュール済みまたは臨時の会議に参加するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="e2efa-141">If the Skype for Business Meeting Room is a publicly available resource, anyone could use it to join a meeting, either scheduled or ad hoc.</span></span> <span data-ttu-id="e2efa-142">会議に参加した後、そのユーザーは任意の番号にダイヤルアウトできます。</span><span class="sxs-lookup"><span data-stu-id="e2efa-142">After joining a meeting, the person could dial out to any number.</span></span> <span data-ttu-id="e2efa-143">Skype for Business Server では、会議からのダイヤルアウト機能は、ユーザーの音声ポリシー (この場合は会議に参加するために使用される Skype Room System アカウント) を使用します。</span><span class="sxs-lookup"><span data-stu-id="e2efa-143">In Skype for Business Server, the dial-out from conferences feature uses the voice policy of the user, in this case the Skype Room System account used to join the meeting.</span></span> <span data-ttu-id="e2efa-144">以前のバージョンの Lync Server では、オーガナイザーの音声ポリシーが使用されています。</span><span class="sxs-lookup"><span data-stu-id="e2efa-144">In earlier versions of Lync Server, the voice policy of the organizer is used.</span></span> <span data-ttu-id="e2efa-145">そのため、以前のバージョンの Lync Server のユーザーが会議室をスケジュールし、Skype Room System ルーム アカウントを招待した場合、開催者がそれらの番号にダイヤルできる限り、誰でも Skype for Business Meeting Room を使用して会議に参加し、国内/地域または国際電話番号にダイヤルできます。</span><span class="sxs-lookup"><span data-stu-id="e2efa-145">Therefore, if a user of an earlier version of Lync Server schedules a meeting room and invites the Skype Room System room account, anyone could use the Skype for Business Meeting Room to join the meeting and could dial any national/regional or international phone number, as long as the organizer is allowed to dial those numbers.</span></span> 
