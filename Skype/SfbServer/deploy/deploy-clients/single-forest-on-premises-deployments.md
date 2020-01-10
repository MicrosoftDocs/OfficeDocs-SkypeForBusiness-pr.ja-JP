---
title: 単一フォレストのオンプレミス環境での Skype Room System の展開
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 80da9d71-3dcd-4ca4-8bd1-6d8196823206
description: このトピックでは、単一フォレストのオンプレミス環境で Skype Room System を展開する方法について説明します。
ms.openlocfilehash: 091500e1abc1a5e65bb060793aca0d5babe9fb35
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002947"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a><span data-ttu-id="877f6-103">単一フォレストのオンプレミス環境での Skype Room System の展開</span><span class="sxs-lookup"><span data-stu-id="877f6-103">Skype Room System single forest on-premises deployments</span></span>
 
<span data-ttu-id="877f6-104">このトピックでは、単一フォレストのオンプレミス環境で Skype Room System を展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="877f6-104">Read this topic to learn how to deploy Skype Room System in a single forest on-premises environment.</span></span>
  
<span data-ttu-id="877f6-105">このセクションでは、Exchange Server の Skype Room System アカウントと、1つのフォレストのオンプレミス展開でホストされている Skype for Business Server をプロビジョニングする手順の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="877f6-105">This section provides an overview of the steps for provisioning the Skype Room System account on Exchange Server and Skype for Business Server hosted in a single forest on-premises deployment.</span></span>
  
## <a name="single-forest-on-premises-deployments"></a><span data-ttu-id="877f6-106">単一フォレストのオンプレミス展開</span><span class="sxs-lookup"><span data-stu-id="877f6-106">Single forest on-premises deployments</span></span>

<span data-ttu-id="877f6-107">会議室用のリソース メールボックス アカウントが既存の場合は、そのアカウントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="877f6-107">If you already have a resource mailbox account for the conferencing room, you can use it.</span></span> <span data-ttu-id="877f6-108">ない場合は、新しいアカウントを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="877f6-108">Otherwise, you will need to create a new one.</span></span> <span data-ttu-id="877f6-109">新しいリソース メールボックス アカウントの作成には Exchange 管理シェル (PowerShell) または Exchange 管理コンソールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="877f6-109">You can use either Exchange Management Shell (PowerShell) or Exchange Management Console to create a new resource mailbox account.</span></span> <span data-ttu-id="877f6-110">Skype Room System の新規 (古いメールボックスの削除と再作成) リソースメールボックスの使用をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="877f6-110">We recommend using a new (delete old mailbox and re-create) resource mailbox for Skype Room System.</span></span> <span data-ttu-id="877f6-111">Outlook クライアントを使用して、削除する前にメールボックス データをバックアップし、作成し直したメールボックスにバックアップをあらためて読み込んでください (詳細については、「メッセージ、予定表、タスク、連絡先をエクスポートまたはバックアップする」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="877f6-111">Make sure to back up mailbox data before deleting and then export it back to the re-created mailbox using the Outlook client (see Export or back up messages, calendar, tasks, and contacts for more information).</span></span> <span data-ttu-id="877f6-112">メールボックスの削除によって失われた会議を復元するには、「[削除されたメールボックスを接続または復元](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="877f6-112">To restore the meetings lost by deleting the mailbox, see [Connect or restore a deleted mailbox](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span></span> 
  
<span data-ttu-id="877f6-113">既存のリソース メールボックス アカウント (LRS-01 など) を使用するには、以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="877f6-113">To use an existing resource mailbox account (for example, LRS-01) follow the steps below:</span></span>
  
1. <span data-ttu-id="877f6-114">次の Exchange 管理シェル (PowerShell) コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="877f6-114">Run the following Exchange Management PowerShell command:</span></span>
    
   ```powershell
   Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

2. <span data-ttu-id="877f6-115">新しいメールボックスを作成する予定の場合、単一フォレストのオンプレミス Exchange 組織であれば、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="877f6-115">If you plan to create a new mailbox, then, for a single forest on-premises Exchange organization, run the following command:</span></span>
    
   ```powershell
   New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   <span data-ttu-id="877f6-p102">上の例は、有効化されたユーザー アカウントを Active Directory に作成し、会議室用の会議室メールボックスをオンプレミスの Exchange 組織に作成します。RoomMailboxPassword パラメーターには、ユーザー アカウントのパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="877f6-p102">The above example creates an enabled user account in Active Directory and a room mailbox for a conference room in an on-premises Exchange organization. The RoomMailboxPassword parameter specifies the password for the user account.</span></span>
    
3. <span data-ttu-id="877f6-118">会議の承諾と辞退を通じて競合を自動的に解消するようにアカウントを構成します。</span><span class="sxs-lookup"><span data-stu-id="877f6-118">Configure the account to automatically resolve conflicts by accepting/rejecting meetings.</span></span> <span data-ttu-id="877f6-119">Skype Room システムを備えた skype の会議室のアカウントは、個人で管理できますが、会議を承諾するまでは、Skype Room System のホーム画面の予定表には表示されません。</span><span class="sxs-lookup"><span data-stu-id="877f6-119">Skype Room System-equipped conference room accounts in Exchange can be managed by individuals, but note that until the individual accepts a meeting it will not appear on the Skype Room System home screen calendar.</span></span>
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   <span data-ttu-id="877f6-120">使用できるコマンドの一覧については、「Set-CalendarProcessing」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="877f6-120">For a complete set of commands available, see Set-CalendarProcessing.</span></span>
    
   <span data-ttu-id="877f6-121">会議の開催者に、Outlook でオンラインの Skype for Business 会議に参加するように依頼するには、次のコマンドを実行して、新しいアカウントのメールヒントを設定します。</span><span class="sxs-lookup"><span data-stu-id="877f6-121">To remind meeting organizers to make the meeting an online Skype for Business meeting in Outlook, run the following command to set up a MailTip for the new account:</span></span> 
    
   ```powershell
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. <span data-ttu-id="877f6-122">次のコマンドを使用して、ローカライズされた文字列を構成します。</span><span class="sxs-lookup"><span data-stu-id="877f6-122">Use the following commands to configure localized strings.</span></span> <span data-ttu-id="877f6-123">組織での必要に応じて、カスタマイズした翻訳を追加できます。</span><span class="sxs-lookup"><span data-stu-id="877f6-123">If required by your organization, you can also add custom translations:</span></span> 
   ```powershell
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. <span data-ttu-id="877f6-124">オプション: Skype for Business 会議室に関する情報をユーザーに提供する会議承諾テキストと、会議をスケジュールして参加するときの考慮事項を構成します。</span><span class="sxs-lookup"><span data-stu-id="877f6-124">Optional: Configure meeting acceptance text that provides users with information about Skype for Business Meeting Room, and what to expect when they schedule and join meetings.</span></span> 
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a><span data-ttu-id="877f6-125">Active Directory のリソース メールボックス アカウントの確認</span><span class="sxs-lookup"><span data-stu-id="877f6-125">Check Resource Mailbox Account in Active Directory</span></span>

<span data-ttu-id="877f6-126">上の手順 1 で Exchange を使用して作成した会議室メールボックス アカウントが、Active Directory で無効になっているユーザー オブジェクトの場合があります。</span><span class="sxs-lookup"><span data-stu-id="877f6-126">The conference room mailbox account created by Exchange in step 1 above might be a disabled user object in Active Directory.</span></span> <span data-ttu-id="877f6-127">Active Directory でアカウントが無効になっている場合、Skype Room システムは、Kerberos/NTLM 認証を使用してサインインまたは認証することはできません。</span><span class="sxs-lookup"><span data-stu-id="877f6-127">Skype Room System cannot sign in or authenticate by using Kerberos/NTLM authentication if the account is disabled in Active Directory.</span></span> <span data-ttu-id="877f6-128">Skype Room システムクライアントは、Exchange Web サービスから認証して、予定表の設定を取得できるようにする必要があります。また、ホワイトボードの内容を含むメールを送信することもできなければなりません。</span><span class="sxs-lookup"><span data-stu-id="877f6-128">The Skype Room System client must be able to authenticate against Exchange Web Services to retrieve calendar settings, and must also be able to send email with whiteboard contents.</span></span> 
  
<span data-ttu-id="877f6-129">そのため、アカウントが無効になっている場合は、以下の手順で Active Directory でアカウントを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="877f6-129">Therefore, if the account is disabled, you must enable this account in Active Directory by doing the following:</span></span> 
  
1. <span data-ttu-id="877f6-130">Active Directory で、次のコマンドを実行してアカウント ログオンを有効にします。</span><span class="sxs-lookup"><span data-stu-id="877f6-130">In Active Directory, run the following command to enable account log on:</span></span> 
    
   ```powershell
   Set-ADAccountPassword -Identity LRS01
   ```

   <span data-ttu-id="877f6-131">このコマンドを実行すると、現在のパスワードの入力が求められ、続いて確認のために同じパスワードの入力がもう一度求められます。</span><span class="sxs-lookup"><span data-stu-id="877f6-131">Running this command will prompt you to enter the current password, and then to re-enter the password twice for confirmation.</span></span>
    
2. <span data-ttu-id="877f6-132">パスワードが設定されたら、次のコマンドを実行してアカウントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="877f6-132">Once the password is set, run the following command to enable the account:</span></span> 
    
   ```powershell
   Enable-ADAccount -Identity LRS01
   ```

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a><span data-ttu-id="877f6-133">Skype for Business の Skype Room System アカウントを有効にする</span><span class="sxs-lookup"><span data-stu-id="877f6-133">Enabling Skype Room System Accounts for Skype for Business</span></span>

<span data-ttu-id="877f6-134">このセクションでは、skype for Business を会議室のアカウントとして有効にするために必要な手順の概要について説明します。これは、Skype Room System で構成されます。</span><span class="sxs-lookup"><span data-stu-id="877f6-134">This section provides an overview of the steps required to enable Skype for Business for your conference room account, which will be configured on Skype Room System.</span></span> 
  
<span data-ttu-id="877f6-135">会議室のリソースメールボックスアカウントを作成したら、skype for Business Server 管理シェルを使って、skype for business サービスの Skype Room System アカウントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="877f6-135">After you create a resource mailbox account for the conferencing rooms, use Skype for Business Server Management Shell to enable Skype Room System accounts for Skype for Business services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="877f6-136">次の手順では、Active Directory で Skype Room System アカウントが有効になっていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="877f6-136">The following procedure assumes that you have enabled the Skype Room System account in Active Directory.</span></span> 
  
1. <span data-ttu-id="877f6-137">Skype for Business サーバープールで Skype Room System アカウントを有効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="877f6-137">Run the following command to enable the Skype Room System account on a Skype for Business Server pool:</span></span>
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. <span data-ttu-id="877f6-138">オプション: このアカウントについて Enterprise VoIP を有効にして、このアカウントで PSTN 通話を発着信できるようにします。</span><span class="sxs-lookup"><span data-stu-id="877f6-138">Optional: Allow this account to make and receive PSTN phone calls by enabling the account for Enterprise Voice.</span></span> <span data-ttu-id="877f6-139">エンタープライズ Voip は Skype Room システムには必要ありませんが、エンタープライズ Voip に対して有効にしていない場合、Skype Room System クライアントは PSTN ダイヤル機能を提供することはできません。</span><span class="sxs-lookup"><span data-stu-id="877f6-139">Enterprise Voice is not required for Skype Room System, but if you do not enable it for Enterprise Voice, the Skype Room System client won't be able to provide PSTN dialing functionality:</span></span>
    
   ```powershell
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="877f6-140">Skype Room System 会議室アカウントのエンタープライズ Voip を有効にしている場合は、組織に適した制限付きの音声ポリシーを必ず構成してください。</span><span class="sxs-lookup"><span data-stu-id="877f6-140">If you enable Enterprise Voice for the Skype Room System conference room account, make sure to configure a restricted Voice Policy suitable for your organization.</span></span> <span data-ttu-id="877f6-141">Skype for Business の会議室が公開されている場合は、会議に参加するために、スケジュールまたはアドホックのいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="877f6-141">If the Skype for Business Meeting Room is a publicly available resource, anyone could use it to join a meeting, either scheduled or ad hoc.</span></span> <span data-ttu-id="877f6-142">会議に参加したユーザーは、任意の番号を発信できます。</span><span class="sxs-lookup"><span data-stu-id="877f6-142">After joining a meeting, the person could dial out to any number.</span></span> <span data-ttu-id="877f6-143">Skype for Business Server では、電話会議機能でユーザーの音声ポリシーが使用されます。この場合は、会議への参加に使用した Skype Room System アカウント。</span><span class="sxs-lookup"><span data-stu-id="877f6-143">In Skype for Business Server, the dial-out from conferences feature uses the voice policy of the user, in this case the Skype Room System account used to join the meeting.</span></span> <span data-ttu-id="877f6-144">Lync Server の以前のバージョンでは、開催者の音声ポリシーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="877f6-144">In earlier versions of Lync Server, the voice policy of the organizer is used.</span></span> <span data-ttu-id="877f6-145">そのため、以前のバージョンの Lync Server のユーザーが会議室をスケジュールして、Skype Room System room アカウントを招待した場合、すべてのユーザーは、Skype for Business 会議室を使って会議に参加し、開催者がその番号にダイヤルできる限り、国/地域または国際電話番号をダイヤルすることができます。</span><span class="sxs-lookup"><span data-stu-id="877f6-145">Therefore, if a user of an earlier version of Lync Server schedules a meeting room and invites the Skype Room System room account, anyone could use the Skype for Business Meeting Room to join the meeting and could dial any national/regional or international phone number, as long as the organizer is allowed to dial those numbers.</span></span> 
  

