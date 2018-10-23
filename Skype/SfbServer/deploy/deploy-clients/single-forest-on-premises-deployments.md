---
title: 単一フォレストのオンプレミス環境での Skype Room System の展開
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 80da9d71-3dcd-4ca4-8bd1-6d8196823206
description: このトピックでは、単一フォレストのオンプレミス環境で Skype Room System を展開する方法について説明します。
ms.openlocfilehash: 5fd9ab3f2a2e581f2f1675bea0f663b95cfa3eb5
ms.sourcegitcommit: d3c3467320a2928d3bad14a1a44a31ee5a9a988c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2018
ms.locfileid: "25699715"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a><span data-ttu-id="fb827-103">単一フォレストのオンプレミス環境での Skype Room System の展開</span><span class="sxs-lookup"><span data-stu-id="fb827-103">Skype Room System single forest on-premises deployments</span></span>
 
<span data-ttu-id="fb827-104">このトピックでは、単一フォレストのオンプレミス環境で Skype Room System を展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fb827-104">Read this topic to learn how to deploy Skype Room System in a single forest on-premises environment.</span></span>
  
<span data-ttu-id="fb827-105">ここでは、単一フォレストの設置型展開でホストされているビジネスのサーバーの Exchange Server と Skype の Skype の部屋のシステム アカウントをプロビジョニングするための手順の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="fb827-105">This section provides an overview of the steps for provisioning the Skype Room System account on Exchange Server and Skype for Business Server hosted in a single forest on-premises deployment.</span></span>
  
## <a name="single-forest-on-premises-deployments"></a><span data-ttu-id="fb827-106">単一フォレストのオンプレミス展開</span><span class="sxs-lookup"><span data-stu-id="fb827-106">Single forest on-premises deployments</span></span>

<span data-ttu-id="fb827-107">会議室用のリソース メールボックス アカウントが既存の場合は、そのアカウントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="fb827-107">If you already have a resource mailbox account for the conferencing room, you can use it.</span></span> <span data-ttu-id="fb827-108">ない場合は、新しいアカウントを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb827-108">Otherwise, you will need to create a new one.</span></span> <span data-ttu-id="fb827-109">新しいリソース メールボックス アカウントの作成には Exchange 管理シェル (PowerShell) または Exchange 管理コンソールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="fb827-109">You can use either Exchange Management Shell (PowerShell) or Exchange Management Console to create a new resource mailbox account.</span></span> <span data-ttu-id="fb827-110">新しいを使用することをお勧めします。 (古いメールボックスを削除して再作成) Skype ルーム システムのリソース メールボックスです。</span><span class="sxs-lookup"><span data-stu-id="fb827-110">We recommend using a new (delete old mailbox and re-create) resource mailbox for Skype Room System.</span></span> <span data-ttu-id="fb827-111">Outlook クライアントを使用して、削除する前にメールボックス データをバックアップし、作成し直したメールボックスにバックアップをあらためて読み込んでください (詳細については、「メッセージ、予定表、タスク、連絡先をエクスポートまたはバックアップする」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="fb827-111">Make sure to back up mailbox data before deleting and then export it back to the re-created mailbox using the Outlook client (see Export or back up messages, calendar, tasks, and contacts for more information).</span></span> <span data-ttu-id="fb827-112">メールボックスの削除で失われた会議を復元する方法については、「[削除されたメールボックスの接続または復元](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb827-112">To restore the meetings lost by deleting the mailbox, see [Connect or restore a deleted mailbox](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span></span> 
  
<span data-ttu-id="fb827-113">既存のリソース メールボックス アカウント (LRS-01 など) を使用するには、以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="fb827-113">To use an existing resource mailbox account (for example, LRS-01) follow the steps below:</span></span>
  
1. <span data-ttu-id="fb827-114">次の Exchange 管理シェル (PowerShell) コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fb827-114">Run the following Exchange Management PowerShell command:</span></span>
    
   ```
   Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

2. <span data-ttu-id="fb827-115">新しいメールボックスを作成する予定の場合、単一フォレストのオンプレミス Exchange 組織であれば、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fb827-115">If you plan to create a new mailbox, then, for a single forest on-premises Exchange organization, run the following command:</span></span>
    
   ```
   New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   <span data-ttu-id="fb827-p102">上の例は、有効化されたユーザー アカウントを Active Directory に作成し、会議室用の会議室メールボックスをオンプレミスの Exchange 組織に作成します。RoomMailboxPassword パラメーターには、ユーザー アカウントのパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="fb827-p102">The above example creates an enabled user account in Active Directory and a room mailbox for a conference room in an on-premises Exchange organization. The RoomMailboxPassword parameter specifies the password for the user account.</span></span>
    
3. <span data-ttu-id="fb827-118">会議の承諾と辞退を通じて競合を自動的に解消するようにアカウントを構成します。</span><span class="sxs-lookup"><span data-stu-id="fb827-118">Configure the account to automatically resolve conflicts by accepting/rejecting meetings.</span></span> <span data-ttu-id="fb827-119">Skype ルーム システム対応の会議室の Exchange のアカウントは、個人が管理することができますが、個人は、会議を受け入れるまでに表示されないこと Skype ルーム システム ホーム画面のカレンダーに注意してください。</span><span class="sxs-lookup"><span data-stu-id="fb827-119">Skype Room System-equipped conference room accounts in Exchange can be managed by individuals, but note that until the individual accepts a meeting it will not appear on the Skype Room System home screen calendar.</span></span>
    
   ```
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   <span data-ttu-id="fb827-120">使用できるコマンドの一覧については、「Set-CalendarProcessing」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb827-120">For a complete set of commands available, see Set-CalendarProcessing.</span></span>
    
   <span data-ttu-id="fb827-121">ミーティングの開催者は会議出席のアラームには、Outlook では、ビジネス会議のためのオンラインの Skype は、MailTip の新しいアカウントを設定する次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fb827-121">To remind meeting organizers to make the meeting an online Skype for Business meeting in Outlook, run the following command to set up a MailTip for the new account:</span></span> 
    
   ```
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. <span data-ttu-id="fb827-122">次のコマンドを使用して、ローカライズされた文字列を構成します。</span><span class="sxs-lookup"><span data-stu-id="fb827-122">Use the following commands to configure localized strings.</span></span> <span data-ttu-id="fb827-123">組織での必要に応じて、カスタマイズした翻訳を追加できます。</span><span class="sxs-lookup"><span data-stu-id="fb827-123">If required by your organization, you can also add custom translations:</span></span> 
   ```
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. <span data-ttu-id="fb827-124">オプション: を構成するビジネス会議室、および予想される結果をスケジュールし、参加する Skype に関する情報をユーザーに提供する受け入れテキストの会議の会議。</span><span class="sxs-lookup"><span data-stu-id="fb827-124">Optional: Configure meeting acceptance text that provides users with information about Skype for Business Meeting Room, and what to expect when they schedule and join meetings.</span></span> 
    
   ```
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a><span data-ttu-id="fb827-125">Active Directory のリソース メールボックス アカウントの確認</span><span class="sxs-lookup"><span data-stu-id="fb827-125">Check Resource Mailbox Account in Active Directory</span></span>

<span data-ttu-id="fb827-126">上の手順 1 で Exchange を使用して作成した会議室メールボックス アカウントが、Active Directory で無効になっているユーザー オブジェクトの場合があります。</span><span class="sxs-lookup"><span data-stu-id="fb827-126">The conference room mailbox account created by Exchange in step 1 above might be a disabled user object in Active Directory.</span></span> <span data-ttu-id="fb827-127">Skype ルームのシステムでは、サインインまたは Active Directory にアカウントが無効になっている場合、Kerberos または NTLM 認証を使用して認証できません。</span><span class="sxs-lookup"><span data-stu-id="fb827-127">Skype Room System cannot sign in or authenticate by using Kerberos/NTLM authentication if the account is disabled in Active Directory.</span></span> <span data-ttu-id="fb827-128">Skype ルーム システムのクライアントは、カレンダーの設定を取得するために、Exchange Web サービスに対して認証を行うことができる必要があり、ホワイト ボードの内容をメールを送信することもあります。</span><span class="sxs-lookup"><span data-stu-id="fb827-128">The Skype Room System client must be able to authenticate against Exchange Web Services to retrieve calendar settings, and must also be able to send email with whiteboard contents.</span></span> 
  
<span data-ttu-id="fb827-129">そのため、アカウントが無効になっている場合は、以下の手順で Active Directory でアカウントを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb827-129">Therefore, if the account is disabled, you must enable this account in Active Directory by doing the following:</span></span> 
  
1. <span data-ttu-id="fb827-130">Active Directory で、次のコマンドを実行してアカウント ログオンを有効にします。</span><span class="sxs-lookup"><span data-stu-id="fb827-130">In Active Directory, run the following command to enable account log on:</span></span> 
    
   ```
   Set-ADAccountPassword -Identity LRS01
   ```

   <span data-ttu-id="fb827-131">このコマンドを実行すると、現在のパスワードの入力が求められ、続いて確認のために同じパスワードの入力がもう一度求められます。</span><span class="sxs-lookup"><span data-stu-id="fb827-131">Running this command will prompt you to enter the current password, and then to re-enter the password twice for confirmation.</span></span>
    
2. <span data-ttu-id="fb827-132">パスワードが設定されたら、次のコマンドを実行してアカウントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="fb827-132">Once the password is set, run the following command to enable the account:</span></span> 
    
   ```
   Enable-ADAccount -Identity LRS01
   ```

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a><span data-ttu-id="fb827-133">ビジネスの Skype のアカウントの Skype の部屋のシステムを有効化</span><span class="sxs-lookup"><span data-stu-id="fb827-133">Enabling Skype Room System Accounts for Skype for Business</span></span>

<span data-ttu-id="fb827-134">Skype ルームのシステム上で構成する会議室アカウントのビジネス用の Skype を有効にする必要な手順の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="fb827-134">This section provides an overview of the steps required to enable Skype for Business for your conference room account, which will be configured on Skype Room System.</span></span> 
  
<span data-ttu-id="fb827-135">会議室のリソース メールボックスのアカウントを作成した後は、ビジネス サービスの Skype の Skype ルーム システムのアカウントを有効にするのにビジネス サーバー管理シェルの Skype を使用します。</span><span class="sxs-lookup"><span data-stu-id="fb827-135">After you create a resource mailbox account for the conferencing rooms, use Skype for Business Server Management Shell to enable Skype Room System accounts for Skype for Business services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fb827-136">次の手順では、Active Directory で Skype ルームのシステム アカウントが有効になっていると仮定します。</span><span class="sxs-lookup"><span data-stu-id="fb827-136">The following procedure assumes that you have enabled the Skype Room System account in Active Directory.</span></span> 
  
1. <span data-ttu-id="fb827-137">ビジネス サーバー プールのため、Skype の Skype ルームのシステム アカウントを有効にするのには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fb827-137">Run the following command to enable the Skype Room System account on a Skype for Business Server pool:</span></span>
    
   ```
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. <span data-ttu-id="fb827-138">オプション: このアカウントについて Enterprise VoIP を有効にして、このアカウントで PSTN 通話を発着信できるようにします。</span><span class="sxs-lookup"><span data-stu-id="fb827-138">Optional: Allow this account to make and receive PSTN phone calls by enabling the account for Enterprise Voice.</span></span> <span data-ttu-id="fb827-139">エンタープライズ VoIP は Skype ルーム システムでは、必須ではありませんはない有効にした場合、エンタープライズ VoIP を Skype ルーム システム クライアントできない PSTN のダイヤル機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="fb827-139">Enterprise Voice is not required for Skype Room System, but if you do not enable it for Enterprise Voice, the Skype Room System client won't be able to provide PSTN dialing functionality:</span></span>
    
   ```
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="fb827-140">Skype ルーム システム会議ルームのアカウントでエンタープライズ VoIP を有効にした場合は、組織に適した制限された音声ポリシーを構成することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="fb827-140">If you enable Enterprise Voice for the Skype Room System conference room account, make sure to configure a restricted Voice Policy suitable for your organization.</span></span> <span data-ttu-id="fb827-141">ビジネス会議室の Skype が公開されているリソースの場合は、誰でもそれを使用、アドホックまたはスケジュールされたミーティングに参加します。</span><span class="sxs-lookup"><span data-stu-id="fb827-141">If the Skype for Business Meeting Room is a publicly available resource, anyone could use it to join a meeting, either scheduled or ad hoc.</span></span> <span data-ttu-id="fb827-142">会議に参加したユーザーは、任意の番号を発信できます。</span><span class="sxs-lookup"><span data-stu-id="fb827-142">After joining a meeting, the person could dial out to any number.</span></span> <span data-ttu-id="fb827-143">ビジネス サーバーの Skype、ダイヤルアウト会議機能からミーティングに参加する Skype ルームのシステム アカウントを使用するここでは、ユーザーの音声ポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="fb827-143">In Skype for Business Server, the dial-out from conferences feature uses the voice policy of the user, in this case the Skype Room System account used to join the meeting.</span></span> <span data-ttu-id="fb827-144">Lync Server の以前のバージョンでは、開催者の音声ポリシーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="fb827-144">In earlier versions of Lync Server, the voice policy of the organizer is used.</span></span> <span data-ttu-id="fb827-145">したがって、Lync Server の以前のバージョンのユーザーは、会議室のスケジュールを設定し、Skype ルーム システム領域のアカウントへの招待、誰でもミーティングに参加するのには、ビジネス会議室の Skype を使用してし、国/地域または国際電話をダイヤルする可能性があります。数、開催者がこれらの番号をダイヤルできる限りです。</span><span class="sxs-lookup"><span data-stu-id="fb827-145">Therefore, if a user of an earlier version of Lync Server schedules a meeting room and invites the Skype Room System room account, anyone could use the Skype for Business Meeting Room to join the meeting and could dial any national/regional or international phone number, as long as the organizer is allowed to dial those numbers.</span></span> 
  

