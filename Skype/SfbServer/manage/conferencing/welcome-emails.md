---
title: Skype for Business Server でダイヤルイン ユーザーにようこそメールを送信する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5507827b-6f8d-4ea4-94e6-1cf72c1d38eb
description: '概要: Skype for Business Server でユーザーをダイヤルイン会議に参加する方法について説明します。'
ms.openlocfilehash: dea63f02bcdd3fab323f7f4eff8f420bf012e9a7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817497"
---
# <a name="send-welcome-email-to-dial-in-users-in-skype-for-business-server"></a>Skype for Business Server でダイヤルイン ユーザーにようこそメールを送信する
 
**概要:** Skype for Business Server でユーザーをダイヤルイン会議に参加する方法について説明します。
  
ダイヤルイン会議を構成し、テストして正常に機能しているか確認した後、ユーザーの初期の個人識別番号 (PIN) を設定し、機能の可用性についてユーザーに通知する必要があります。 初期 PIN やダイヤルイン会議の設定 Web ページへのリンクなどの導入手順を含めできます。 
  
通常は **Set-CsClientPin** コマンドレットを使用して PIN をリセットしますが、PIN 情報を記載した入門用のウェルカム メールを送信する場合は、このトピックの手順を使用できます。 電子メールを送信しない場合は、代わりに **Set-CsClientPin を** 使用できます。
  
PIN を設定し、1 人のユーザーにようこそメールを送信する場合は、**Set-CsPinSendCAWelcomeMail** スクリプトを使用できます。 既定で、このスクリプトを実行しても、値が既に設定されている場合には PIN をリセットしませんが、Force パラメーターを使用すれば PIN のリセットを強制できます。 電子メール メッセージは、SMTP (Simple Mail Transfer Protocol) を使用して送信されます。
  
**Set-CsPinSendCAWelcomeMail** スクリプトを繰り返し実行して PIN を設定し、ユーザー グループに電子メールを送信するスクリプトを作成できます。 電子メール テンプレート (CAWelcomeEmailTemplate.html ファイル) を変更してイントラネット ページにリンクを追加するか、電子メール テキストを変更できます。
  


## <a name="set-an-initial-pin-and-send-welcome-email"></a>初期 PIN を設定してようこそメールを送信する

1. RTCUniversalServerAdmins group のメンバーとしてログオンします。
    
2. Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理シェル**] をクリックします。
    
3. コマンド プロンプトで次のコマンドを実行します。
    
   ```PowerShell
   Set-CsPinSendCAWelcomeMail -UserUri <user identifier>
   -From <email address of sender> [-Subject <subject for email message>]
   [-UserEmailAddress <destination email address>]
   [-Cc <email address of recipients who receive copy of email>]
   [-Bcc <email address of recipients who receive blind copies>]
   [-TemplatePath <path for email template>]
   [-SmtpServer] <SMTP server name>]
   [-BodyAsPlainText] [-UseSsl]
   [-Pin <new numeric PIN>] [-Force] `
   [-Credential <SMTP server credentials used to send email with the specified From address>]
   ```

**SmtpServer** 既定では、スクリプトは予約された環境変数の値をこのパラメーター **$PSEmailServer** 使用します。 変数$PSEmailServer **設定** しない場合は、このパラメーターを指定する必要があります。
    
**資格情報** 既定では、スクリプトは現在のユーザーの資格情報を使用します。 現在のユーザーに、指定した From アドレスの代わりに電子メールを送信するアクセス許可が付与されていない場合は、このパラメーターを指定する必要があります。 一般に、電子メール アドレスを From アドレスとして指定しない場合は、このパラメーターを指定します。
    
次の例では、新しい PIN を作成し、Bob に Bob からようこそメールを送信します。 既定のテンプレートにある電子メール テキストを使用し、HTML 形式で電子メール メッセージを作成します。 既定の件名は "ダイヤルイン会議へようこそ" です。
  
```PowerShell
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com"
```

次の例では、Bob が既存の PIN を持っていた場合でも、Bob に対して値 "383042650" の新しい PIN を強制的に設定し、次に、Bob から Bob にようこそメールを送信します。 Credential パラメーターが指定されているため、コマンドを実行するユーザーはパスワードを入力するよう求められます。 電子メールは SSL (Secure Sockets Layer使用して送信されます。
  
```PowerShell
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
-Pin "383042650" -Force
-Credential Admin@contoso.com -UseSsl
```
