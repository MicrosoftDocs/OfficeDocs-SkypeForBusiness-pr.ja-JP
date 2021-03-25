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
# <a name="skype-room-system-single-forest-on-premises-deployments"></a>Skype Room System の単一フォレストのオンプレミス展開
 
単一フォレストのオンプレミス環境に Skype Room System を展開する方法については、このトピックを参照してください。
  
このセクションでは、単一フォレストのオンプレミス展開でホストされている Exchange Server および Skype for Business Server で Skype Room System アカウントをプロビジョニングする手順の概要を説明します。
  
## <a name="single-forest-on-premises-deployments"></a>単一フォレスト オンプレミスの展開

会議室のリソース メールボックス アカウントが既に存在する場合は、そのアカウントを使用できます。 それ以外の場合は、新しい作成が必要です。 Exchange 管理シェル (PowerShell) または管理者を使用してExchange 管理コンソールリソース メールボックス アカウントを作成できます。 Skype Room System の新しい (古いメールボックスを削除して、再作成する) リソース メールボックスを使用することをお勧めします。 削除する前にメールボックス データをバックアップし、Outlook クライアントを使用して再作成したメールボックスにエクスポートし戻してください (詳細については、「メッセージ、予定表、タスク、連絡先をエクスポートまたはバックアップする」を参照してください)。 メールボックスを削除して失われた会議を復元するには、「削除されたメールボックスを接続または復元 [する」を参照してください](/exchange/connect-or-restore-a-deleted-mailbox-exchange-2013-help)。 
  
既存のリソース メールボックス アカウント (LRS-01 など) を使用するには、次の手順に従います。
  
1. 次の Exchange 管理 PowerShell コマンドを実行します。
    
   ```powershell
   Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

2. 新しいメールボックスを作成する予定の場合は、単一のフォレストのオンプレミス Exchange 組織に対して、次のコマンドを実行します。
    
   ```powershell
   New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   上記の例では、Active Directory に有効なユーザー アカウントと、オンプレミスの Exchange 組織の会議室用の会議室メールボックスを作成します。 RoomMailboxPassword パラメーターは、ユーザー アカウントのパスワードを指定します。
    
3. 会議を受け入れる/拒否することで、競合を自動的に解決するアカウントを構成します。 Exchange の Skype Room System に装備された会議室アカウントは、個人が管理できますが、個人が会議を受け入れるまで、Skype Room System のホーム画面カレンダーには表示されません。
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   使用可能なコマンドの完全なセットについては、「Set-CalendarProcessing」を参照してください。
    
   Outlook で会議をオンラインの Skype for Business 会議に設定する会議の開催者に通知するには、次のコマンドを実行して、新しいアカウントのメール ヒントを設定します。 
    
   ```powershell
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. ローカライズされた文字列を構成するには、次のコマンドを使用します。 組織で必要な場合は、カスタム翻訳を追加することもできます。 
   ```powershell
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. 省略可能: Skype for Business Meeting Room に関する情報と、会議のスケジュールと参加時にユーザーが期待する内容をユーザーに提供する会議の受け入れテキストを構成します。 
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a>Active Directory でリソース メールボックス アカウントを確認する

上記の手順 1 で Exchange によって作成された会議室メールボックス アカウントは、Active Directory の無効なユーザー オブジェクトである可能性があります。 アカウントが Active Directory で無効になっている場合、Skype Room System は Kerberos/NTLM 認証を使用してサインインまたは認証できません。 Skype Room System クライアントは、予定表の設定を取得するために Exchange Web サービスに対して認証できる必要があります。また、ホワイトボードの内容を含む電子メールを送信できる必要があります。 
  
したがって、アカウントが無効になっている場合は、次の手順を実行して Active Directory でこのアカウントを有効にする必要があります。 
  
1. Active Directory で、次のコマンドを実行してアカウント ログオンを有効にします。 
    
   ```powershell
   Set-ADAccountPassword -Identity LRS01
   ```

   このコマンドを実行すると、現在のパスワードを入力し、確認のためにパスワードを 2 回再入力するように求められます。
    
2. パスワードを設定したら、次のコマンドを実行してアカウントを有効にしてください。 
    
   ```powershell
   Enable-ADAccount -Identity LRS01
   ```

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a>Skype for Business の Skype ルーム システム アカウントの有効化

このセクションでは、Skype Room System で構成される会議室アカウントで Skype for Business を有効にするために必要な手順の概要を説明します。 
  
会議ルームのリソース メールボックス アカウントを作成した後、Skype for Business Server 管理シェルを使用して Skype for Business サービスの Skype Room System アカウントを有効にします。
  
> [!NOTE]
> 次の手順では、Active Directory で Skype Room System アカウントを有効にしたと仮定します。 
  
1. 次のコマンドを実行して、Skype for Business Server プールで Skype Room System アカウントを有効にします。
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. 省略可能: このアカウントが PSTN 電話の発信および受信を許可するには、このアカウントのアカウントを有効にエンタープライズ VoIP。 エンタープライズ VoIP Skype ルーム システムでは必須ではありませんが、エンタープライズ VoIP で有効にしない場合、Skype Room System クライアントは PSTN ダイヤル機能を提供できます。
    
   ```powershell
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Skype Room System エンタープライズ VoIPアカウントに対して有効にする場合は、組織に適した制限付き音声ポリシーを構成してください。 Skype for Business Meeting Room が一般に公開されているリソースである場合、誰でもスケジュール済みまたは臨時の会議に参加するために使用できます。 会議に参加した後、そのユーザーは任意の番号にダイヤルアウトできます。 Skype for Business Server では、会議からのダイヤルアウト機能は、ユーザーの音声ポリシー (この場合は会議に参加するために使用される Skype Room System アカウント) を使用します。 以前のバージョンの Lync Server では、オーガナイザーの音声ポリシーが使用されています。 そのため、以前のバージョンの Lync Server のユーザーが会議室をスケジュールし、Skype Room System ルーム アカウントを招待した場合、開催者がそれらの番号にダイヤルできる限り、誰でも Skype for Business Meeting Room を使用して会議に参加し、国内/地域または国際電話番号にダイヤルできます。 
