---
title: 単一フォレストのオンプレミス環境での Skype Room System の展開
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 80da9d71-3dcd-4ca4-8bd1-6d8196823206
description: このトピックでは、単一フォレストのオンプレミス環境で Skype Room System を展開する方法について説明します。
ms.openlocfilehash: b998c0b1e139951297eca8a963536dd59dcd4b39
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a>単一フォレストのオンプレミス環境での Skype Room System の展開
 
このトピックでは、単一フォレストのオンプレミス環境で Skype Room System を展開する方法について説明します。
  
ここでは、単一フォレストの設置型展開でホストされているビジネスのサーバーの Exchange Server と Skype の Skype の部屋のシステム アカウントをプロビジョニングするための手順の概要を示します。
  
## <a name="single-forest-on-premises-deployments"></a>単一フォレストのオンプレミス展開

会議室用のリソース メールボックス アカウントが既存の場合は、そのアカウントを使用できます。 ない場合は、新しいアカウントを作成する必要があります。 新しいリソース メールボックス アカウントの作成には Exchange 管理シェル (PowerShell) または Exchange 管理コンソールを使用できます。 新しいを使用することをお勧めします。 (古いメールボックスを削除して再作成) Skype ルーム システムのリソース メールボックスです。 Outlook クライアントを使用して、削除する前にメールボックス データをバックアップし、作成し直したメールボックスにバックアップをあらためて読み込んでください (詳細については、「メッセージ、予定表、タスク、連絡先をエクスポートまたはバックアップする」を参照してください)。 メールボックスを削除することによって失われた会議を復元するには、 [[接続] または [削除済みメールボックスの復元](https://technet.microsoft.com/en-us/library/jj863438%28v=exchg.150%29.aspx)を参照してください。 
  
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
    
3. 会議の承諾と辞退を通じて競合を自動的に解消するようにアカウントを構成します。 Skype ルーム システム対応の会議室の Exchange のアカウントは、個人が管理することができますが、個人は、会議を受け入れるまでに表示されないこと Skype ルーム システム ホーム画面のカレンダーに注意してください。
    
   ```
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   使用できるコマンドの一覧については、「Set-CalendarProcessing」を参照してください。
    
   ミーティングの開催者は会議出席のアラームには、Outlook では、ビジネス会議のためのオンラインの Skype は、MailTip の新しいアカウントを設定する次のコマンドを実行します。 
    
   ```
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. 次のコマンドを使用して、ローカライズされた文字列を構成します。組織での必要に応じて、カスタマイズした翻訳を追加できます。 
   ```
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. オプション: を構成するビジネス会議室、および予想される結果をスケジュールし、参加する Skype に関する情報をユーザーに提供する受け入れテキストの会議の会議。 
    
   ```
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a>Active Directory のリソース メールボックス アカウントの確認

上の手順 1 で Exchange を使用して作成した会議室メールボックス アカウントが、Active Directory で無効になっているユーザー オブジェクトの場合があります。 Skype ルームのシステムでは、サインインまたは Active Directory にアカウントが無効になっている場合、Kerberos または NTLM 認証を使用して認証できません。 Skype ルーム システムのクライアントは、カレンダーの設定を取得するために、Exchange Web サービスに対して認証を行うことができる必要があり、ホワイト ボードの内容をメールを送信することもあります。 
  
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

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a>ビジネスの Skype のアカウントの Skype の部屋のシステムを有効化

Skype ルームのシステム上で構成する会議室アカウントのビジネス用の Skype を有効にする必要な手順の概要を説明します。 
  
会議室のリソース メールボックスのアカウントを作成した後は、ビジネス サービスの Skype の Skype ルーム システムのアカウントを有効にするのにビジネス サーバー管理シェルの Skype を使用します。
  
> [!NOTE]
> 次の手順では、Active Directory で Skype ルームのシステム アカウントが有効になっていると仮定します。 
  
1. ビジネス サーバー プールのため、Skype の Skype ルームのシステム アカウントを有効にするのには、次のコマンドを実行します。
    
   ```
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. オプション: このアカウントについて Enterprise VoIP を有効にして、このアカウントで PSTN 通話を発着信できるようにします。 エンタープライズ VoIP は Skype ルーム システムでは、必須ではありませんはない有効にした場合、エンタープライズ VoIP を Skype ルーム システム クライアントできない PSTN のダイヤル機能を提供します。
    
   ```
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true

   ```

> [!NOTE]
> Skype ルーム システム会議ルームのアカウントでエンタープライズ VoIP を有効にした場合は、組織に適した制限された音声ポリシーを構成することを確認してください。 ビジネス会議室の Skype が公開されているリソースの場合は、誰でもそれを使用、アドホックまたはスケジュールされたミーティングに参加します。 会議に参加したユーザーは、任意の番号を発信できます。 ビジネス サーバーの Skype、ダイヤルアウト会議機能からミーティングに参加する Skype ルームのシステム アカウントを使用するここでは、ユーザーの音声ポリシーを使用します。 Lync Server の以前のバージョンでは、開催者の音声ポリシーが使用されます。 したがって、Lync Server の以前のバージョンのユーザーは、会議室のスケジュールを設定し、Skype ルーム システム領域のアカウントへの招待、誰でもミーティングに参加するのには、ビジネス会議室の Skype を使用してし、国/地域または国際電話をダイヤルする可能性があります。数、開催者がこれらの番号をダイヤルできる限りです。 
  

