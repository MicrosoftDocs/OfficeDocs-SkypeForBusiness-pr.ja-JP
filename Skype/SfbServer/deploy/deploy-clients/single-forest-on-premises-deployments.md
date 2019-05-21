---
title: 単一フォレストのオンプレミス環境での Skype Room System の展開
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 80da9d71-3dcd-4ca4-8bd1-6d8196823206
description: このトピックでは、単一フォレストのオンプレミス環境で Skype Room System を展開する方法について説明します。
ms.openlocfilehash: 0eae077662b050ed2accb5869f1423e0a201a0d1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287954"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a>単一フォレストのオンプレミス環境での Skype Room System の展開
 
このトピックでは、単一フォレストのオンプレミス環境で Skype Room System を展開する方法について説明します。
  
このセクションでは、Exchange Server の Skype Room System アカウントと、1つのフォレストのオンプレミス展開でホストされている Skype for Business Server をプロビジョニングする手順の概要について説明します。
  
## <a name="single-forest-on-premises-deployments"></a>単一フォレストのオンプレミス展開

会議室用のリソース メールボックス アカウントが既存の場合は、そのアカウントを使用できます。 ない場合は、新しいアカウントを作成する必要があります。 新しいリソース メールボックス アカウントの作成には Exchange 管理シェル (PowerShell) または Exchange 管理コンソールを使用できます。 Skype Room System の新規 (古いメールボックスの削除と再作成) リソースメールボックスの使用をお勧めします。 Outlook クライアントを使用して、削除する前にメールボックス データをバックアップし、作成し直したメールボックスにバックアップをあらためて読み込んでください (詳細については、「メッセージ、予定表、タスク、連絡先をエクスポートまたはバックアップする」を参照してください)。 メールボックスの削除によって失われた会議を復元するには、「[削除されたメールボックスを接続または復元](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx)する」をご覧ください。 
  
既存のリソース メールボックス アカウント (LRS-01 など) を使用するには、以下の手順に従います。
  
1. 次の Exchange 管理シェル (PowerShell) コマンドを実行します。
    
   ```
   Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

2. 新しいメールボックスを作成する予定の場合、単一フォレストのオンプレミス Exchange 組織であれば、次のコマンドを実行します。
    
   ```
   New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   上の例は、有効化されたユーザー アカウントを Active Directory に作成し、会議室用の会議室メールボックスをオンプレミスの Exchange 組織に作成します。RoomMailboxPassword パラメーターには、ユーザー アカウントのパスワードを指定します。
    
3. 会議の承諾と辞退を通じて競合を自動的に解消するようにアカウントを構成します。 Skype Room システムを備えた skype の会議室のアカウントは、個人で管理できますが、会議を承諾するまでは、Skype Room System のホーム画面の予定表には表示されません。
    
   ```
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   使用できるコマンドの一覧については、「Set-CalendarProcessing」を参照してください。
    
   会議の開催者に、Outlook でオンラインの Skype for Business 会議に参加するように依頼するには、次のコマンドを実行して、新しいアカウントのメールヒントを設定します。 
    
   ```
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. 次のコマンドを使用して、ローカライズされた文字列を構成します。 組織での必要に応じて、カスタマイズした翻訳を追加できます。 
   ```
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. オプション: Skype for Business 会議室に関する情報をユーザーに提供する会議承諾テキストと、会議をスケジュールして参加するときの考慮事項を構成します。 
    
   ```
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a>Active Directory のリソース メールボックス アカウントの確認

上の手順 1 で Exchange を使用して作成した会議室メールボックス アカウントが、Active Directory で無効になっているユーザー オブジェクトの場合があります。 Active Directory でアカウントが無効になっている場合、Skype Room システムは、Kerberos/NTLM 認証を使用してサインインまたは認証することはできません。 Skype Room システムクライアントは、Exchange Web サービスから認証して、予定表の設定を取得できるようにする必要があります。また、ホワイトボードの内容を含むメールを送信することもできなければなりません。 
  
そのため、アカウントが無効になっている場合は、以下の手順で Active Directory でアカウントを有効にする必要があります。 
  
1. Active Directory で、次のコマンドを実行してアカウント ログオンを有効にします。 
    
   ```
   Set-ADAccountPassword -Identity LRS01
   ```

   このコマンドを実行すると、現在のパスワードの入力が求められ、続いて確認のために同じパスワードの入力がもう一度求められます。
    
2. パスワードが設定されたら、次のコマンドを実行してアカウントを有効にします。 
    
   ```
   Enable-ADAccount -Identity LRS01
   ```

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a>Skype for Business の Skype Room System アカウントを有効にする

このセクションでは、skype for Business を会議室のアカウントとして有効にするために必要な手順の概要について説明します。これは、Skype Room System で構成されます。 
  
会議室のリソースメールボックスアカウントを作成したら、skype for Business Server 管理シェルを使って、skype for business サービスの Skype Room System アカウントを有効にします。
  
> [!NOTE]
> 次の手順では、Active Directory で Skype Room System アカウントが有効になっていることを前提としています。 
  
1. Skype for Business サーバープールで Skype Room System アカウントを有効にするには、次のコマンドを実行します。
    
   ```
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. オプション: このアカウントについて Enterprise VoIP を有効にして、このアカウントで PSTN 通話を発着信できるようにします。 エンタープライズ Voip は Skype Room システムには必要ありませんが、エンタープライズ Voip に対して有効にしていない場合、Skype Room System クライアントは PSTN ダイヤル機能を提供することはできません。
    
   ```
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Skype Room System 会議室アカウントのエンタープライズ Voip を有効にしている場合は、組織に適した制限付きの音声ポリシーを必ず構成してください。 Skype for Business の会議室が公開されている場合は、会議に参加するために、スケジュールまたはアドホックのいずれかを使用できます。 会議に参加したユーザーは、任意の番号を発信できます。 Skype for Business Server では、電話会議機能でユーザーの音声ポリシーが使用されます。この場合は、会議への参加に使用した Skype Room System アカウント。 Lync Server の以前のバージョンでは、開催者の音声ポリシーが使用されます。 そのため、以前のバージョンの Lync Server のユーザーが会議室をスケジュールして、Skype Room System room アカウントを招待した場合、すべてのユーザーは Skype for Business 会議室を使って会議に参加することができ、国/地域または国際電話にダイヤルすることができます。番号。開催者がこれらの番号にダイヤルすることが許可されている場合に限ります。 
  

