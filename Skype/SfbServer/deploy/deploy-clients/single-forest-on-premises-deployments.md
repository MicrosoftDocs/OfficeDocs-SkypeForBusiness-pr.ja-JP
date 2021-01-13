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
description: このトピックでは、単一フォレストのオンプレミス環境に Skype Room System を展開する方法について説明します。
ms.openlocfilehash: 0449a5e909fa044df12766aec0a036bf97315386
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820757"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a>Skype Room System の単一フォレストのオンプレミス展開
 
このトピックでは、単一フォレストのオンプレミス環境に Skype Room System を展開する方法について説明します。
  
このセクションでは、単一フォレストのオンプレミス展開でホストされている Exchange Server および Skype for Business Server で Skype Room System アカウントをプロビジョニングする手順の概要について説明します。
  
## <a name="single-forest-on-premises-deployments"></a>単一フォレスト オンプレミスの展開

会議ルームのリソース メールボックス アカウントが既に存在する場合は、そのアカウントを使用できます。 それ以外の場合は、新しいファイルを作成する必要があります。 Exchange 管理シェル (PowerShell) または Exchange 管理コンソールを使用して、新しいリソース メールボックス アカウントを作成できます。 Skype Room System では、新しい (古いメールボックスを削除して、作成し再作成する) リソース メールボックスを使用することをお勧めします。 削除する前にメールボックス データをバックアップし、Outlook クライアントを使用して、作成し戻したメールボックスにエクスポートしてください (詳細については、「メッセージ、予定表、タスク、連絡先をエクスポートまたはバックアップする」を参照してください)。 メールボックスを削除して失われた会議を復元するには、「削除されたメールボックスを接続または [復元する」を参照してください](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx)。 
  
既存のリソース メールボックス アカウント (LRS-01 など) を使用するには、次の手順を実行します。
  
1. 次の Exchange Management PowerShell コマンドを実行します。
    
   ```powershell
   Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

2. 新しいメールボックスを作成する予定の場合は、単一フォレストのオンプレミス Exchange 組織に対して、次のコマンドを実行します。
    
   ```powershell
   New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   上記の例では、Active Directory に有効なユーザー アカウントと、オンプレミスの Exchange 組織の会議室の会議室メールボックスを作成します。 RoomMailboxPassword パラメーターは、ユーザー アカウントのパスワードを指定します。
    
3. 会議の承諾/拒否によって競合が自動的に解決されるアカウントを構成します。 Exchange の Skype Room System に搭載された会議室アカウントは、個人が管理できますが、個別のユーザーが会議を承諾するまでは、Skype Room System のホーム画面の予定表には表示されません。
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   使用可能なコマンドの完全なセットについては、「Set-CalendarProcessing」を参照してください。
    
   会議を Outlook でオンラインの Skype for Business 会議に変更する会議の開催者に通知するには、次のコマンドを実行して新しいアカウントのメール ヒントを設定します。 
    
   ```powershell
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. ローカライズされた文字列を構成するには、次のコマンドを使用します。 組織で必要な場合は、カスタム翻訳を追加することもできます。 
   ```powershell
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. オプション: Skype for Business ミーティング ルームに関する情報と、ユーザーが会議をスケジュールおよび参加するときに期待する内容をユーザーに提供する会議承認テキストを構成します。 
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a>Active Directory でリソース メールボックス アカウントを確認する

上記の手順 1 で Exchange によって作成された会議室メールボックス アカウントは、Active Directory の無効なユーザー オブジェクトである可能性があります。 アカウントが Active Directory で無効になっている場合、Skype Room System は Kerberos/NTLM 認証を使用してサインインまたは認証できません。 Skype Room System クライアントは、予定表の設定を取得するために Exchange Web サービスに対して認証できる必要があります。また、ホワイトボード の内容を含む電子メールを送信できる必要もあります。 
  
したがって、アカウントが無効になっている場合は、次の手順を実行して、Active Directory でこのアカウントを有効にする必要があります。 
  
1. Active Directory で、次のコマンドを実行してアカウント ログオンを有効にします。 
    
   ```powershell
   Set-ADAccountPassword -Identity LRS01
   ```

   このコマンドを実行すると、現在のパスワードを入力し、確認のためにパスワードを 2 回再入力するように求められます。
    
2. パスワードを設定したら、次のコマンドを実行してアカウントを有効にしてください。 
    
   ```powershell
   Enable-ADAccount -Identity LRS01
   ```

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a>Skype for Business の Skype Room System アカウントの有効化

このセクションでは、Skype Room System で構成される会議室アカウントで Skype for Business を有効にするために必要な手順の概要を説明します。 
  
会議ルームのリソース メールボックス アカウントを作成した後、Skype for Business Server 管理シェルを使用して、Skype for Business サービスの Skype Room System アカウントを有効にします。
  
> [!NOTE]
> 次の手順では、Active Directory で Skype Room System アカウントを有効にしている必要があります。 
  
1. 次のコマンドを実行して、Skype for Business Server プールで Skype Room System アカウントを有効にします。
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. オプション: このアカウントで PSTN 通話の発信と受信を許可するには、このアカウントに対して PSTN 通話を有効エンタープライズ VoIP。 エンタープライズ VoIPは Skype Room System では必要ありませんが、エンタープライズ VoIP で有効にしない場合、Skype Room System クライアントは PSTN ダイヤル機能を提供できます。
    
   ```powershell
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Skype Room System エンタープライズ VoIPアカウントの音声ポリシーを有効にする場合は、組織に適した制限付き音声ポリシーを構成してください。 Skype for Business ミーティング ルームがパブリックに利用可能なリソースである場合、誰でもそれを使用して、スケジュールされた会議または臨時の会議に参加できます。 会議に参加した後、そのユーザーは任意の番号にダイヤルアウトできます。 Skype for Business Server では、会議からのダイヤルアウト機能は、ユーザーの音声ポリシー (この場合は会議への参加に使用される Skype Room System アカウント) を使用します。 以前のバージョンの Lync Server では、開催者の音声ポリシーが使用されています。 したがって、以前のバージョンの Lync Server のユーザーが会議室をスケジュールし、Skype Room System の会議室アカウントを招待した場合、開催者がそれらの番号をダイヤルできる限り、誰でも Skype for Business ミーティング ルームを使用して会議に参加し、国/地域または国際電話番号をダイヤルできます。 
  

