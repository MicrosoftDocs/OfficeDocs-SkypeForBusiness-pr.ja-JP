---
title: SkypeRoom System 単一フォレストのオンプレミス展開
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 80da9d71-3dcd-4ca4-8bd1-6d8196823206
description: このトピックでは、単一フォレストのオンプレミス環境Skype Room System を展開する方法について説明します。
ms.openlocfilehash: 7a68171ebf8d56b61ed77c6cef9739b701a0c07e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58591941"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a>SkypeRoom System 単一フォレストのオンプレミス展開
 
このトピックでは、単一フォレストのオンプレミス環境Skype Room System を展開する方法について説明します。
  
このセクションでは、Skype および Exchange Server および Skype for Business Server でホストされている Skype Room System アカウントをプロビジョニングする手順の概要を説明します。
  
## <a name="single-forest-on-premises-deployments"></a>単一フォレスト オンプレミスの展開

会議室のリソース メールボックス アカウントが既に存在する場合は、そのアカウントを使用できます。 それ以外の場合は、新しい作成が必要です。 新しいリソース メールボックス アカウントExchange管理シェル (PowerShell) または Exchange 管理コンソールを使用して作成できます。 新しい (古いメールボックスを削除し、再作成する) リソース メールボックスを使用して、Skypeすることをお勧めします。 削除する前にメールボックス データをバックアップし、Outlook クライアントを使用して再作成したメールボックスにエクスポートし戻してください (詳細については、「メッセージ、予定表、タスク、連絡先のエクスポートまたはバックアップ」を参照してください)。 メールボックスを削除して失われた会議を復元するには、「削除されたメールボックスConnect[復元する」を参照してください](/exchange/connect-or-restore-a-deleted-mailbox-exchange-2013-help)。 
  
既存のリソース メールボックス アカウント (LRS-01 など) を使用するには、次の手順に従います。
  
1. 管理 PowerShell コマンドExchange実行します。
    
   ```powershell
   Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

2. 新しいメールボックスを作成する予定の場合は、組織内の単一のフォレストExchange、次のコマンドを実行します。
    
   ```powershell
   New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   上記の例では、Active Directory に有効なユーザー アカウントと、組織内の会議室用の会議室メールボックスをExchangeします。 RoomMailboxPassword パラメーターは、ユーザー アカウントのパスワードを指定します。
    
3. 会議を受け入れる/拒否することで、競合を自動的に解決するアカウントを構成します。 SkypeExchange の会議室システムが装備された会議室アカウントは、個人が管理できますが、個人が会議を受け入れるまで、Skype Room System のホーム画面カレンダーには表示されません。
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   使用可能なコマンドの完全なセットについては、「Set-CalendarProcessing」を参照してください。
    
   会議の開催者に、会議を Skype for Business でオンライン会議にOutlookするには、次のコマンドを実行して、新しいアカウントのメール ヒントを設定します。 
    
   ```powershell
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. ローカライズされた文字列を構成するには、次のコマンドを使用します。 組織で必要な場合は、カスタム翻訳を追加することもできます。 
   ```powershell
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. オプション: ユーザーに会議のスケジュールと参加を行う際にSkype for Business ミーティング ルーム情報をユーザーに提供する会議の受け入れテキストを構成します。 
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a>Active Directory でリソース メールボックス アカウントを確認する

上記の手順 1 の Exchangeによって作成された会議室メールボックス アカウントは、Active Directory の無効なユーザー オブジェクトである可能性があります。 Skypeアカウントが Active Directory で無効になっている場合、Room System は Kerberos/NTLM 認証を使用してサインインまたは認証できません。 ルーム Skype クライアントは、予定表の設定を取得するために Exchange Web サービスに対して認証できる必要があります。また、ホワイトボードの内容を含む電子メールを送信できる必要があります。 
  
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

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a>ルーム システム Skypeアカウントの有効化Skype for Business

このセクションでは、会議室のアカウントのSkype for Businessを有効にするために必要な手順の概要を示します。この手順は、会議室システムSkype構成されます。 
  
会議会議室のリソース メールボックス アカウントを作成した後、Skype for Business Server 管理シェルを使用して、Skype サービスの会議室システム アカウントSkype for Businessします。
  
> [!NOTE]
> 次の手順では、Active Directory で Room System Skypeを有効にしたと仮定します。 
  
1. 次のコマンドを実行して、Skypeルーム システム アカウントを有効Skype for Business Serverします。
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. 省略可能: このアカウントが PSTN 電話の発信および受信を許可するには、このアカウントで PSTN 電話の通話を有効エンタープライズ VoIP。 エンタープライズ VoIP Skype Room System では必須ではありませんが、エンタープライズ VoIP で有効にしない場合、Skype Room System クライアントは PSTN ダイヤル機能を提供できます。
    
   ```powershell
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> 会議室の会議室アカウントエンタープライズ VoIPを有効Skype、組織に適した制限付き音声ポリシーを構成してください。 ユーザーがSkype for Business ミーティング ルーム利用可能なリソースである場合、だれでも、スケジュール済みまたは臨時の会議に参加できます。 会議に参加した後、そのユーザーは任意の番号にダイヤルアウトできます。 このSkype for Business Server会議からのダイヤルアウト機能では、ユーザーの音声ポリシー (この場合、会議に参加するために使用される Skype Room System アカウント) が使用されます。 以前のバージョンの Lync Server では、オーガナイザーの音声ポリシーが使用されています。 そのため、以前のバージョンの Lync Server のユーザーが会議室をスケジュールし、Skype Room System ルーム アカウントを招待した場合、開催者がそれらの番号にダイヤルできる限り、誰でも Skype for Business ミーティング ルーム を使用して会議に参加し、国内または地域または国際電話番号にダイヤルできます。 
