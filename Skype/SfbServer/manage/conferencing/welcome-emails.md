---
title: ダイヤルに登録完了メールを送信するビジネス サーバーの Skype のユーザー
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5507827b-6f8d-4ea4-94e6-1cf72c1d38eb
description: '概要: は、Skype のビジネス サーバーのユーザーにダイヤルイン会議を開始する方法を説明します。'
ms.openlocfilehash: 90c56fd97d9eb51c96c1a0cb149f732a31a70743
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373714"
---
# <a name="send-welcome-email-to-dial-in-users-in-skype-for-business-server"></a>ダイヤルに登録完了メールを送信するビジネス サーバーの Skype のユーザー
 
**の概要:** Skype のビジネス サーバーのユーザーにダイヤルイン会議を開始する方法について説明します。
  
ダイヤルイン電話会議を構成し、テストして正常に機能することを確認したら、ユーザーの初期暗証番号 (PIN) を設定し、その機能の可用性に関してユーザーに伝えてください。 これには、初期 PIN や、ダイヤルイン電話会議設定 Web ページへのリンクなどについての指示を含めることができます。 
  
通常、**セット CsClientPin**コマンドレットを使用して、Pin をリセットするのには、暗証番号 (pin) の情報を紹介、登録完了メールを送信する場合は、このトピックの手順を使用できます。 ようこそメールを送信しない場合は、代わりに **Set-CsClientPin** を使用できます。
  
PIN を設定し、1 人のユーザーにようこそメールを送信する場合は、**Set-CsPinSendCAWelcomeMail** スクリプトを使用できます。既定で、このスクリプトを実行しても、値が既に設定されている場合には PIN をリセットしませんが、Force パラメーターを使用すれば PIN のリセットを強制できます。電子メール メッセージは、SMTP (Simple Mail Transfer Protocol) を使用して送信されます。
  
**Set-CsPinSendCAWelcomeMail** スクリプトを繰り返し実行して PIN を設定し、ユーザー グループに電子メールを送信するスクリプトを作成できます。電子メール テンプレート (CAWelcomeEmailTemplate.html ファイル) を変更してイントラネット ページにリンクを追加するか、電子メール テキストを変更できます。
  


## <a name="set-an-initial-pin-and-send-welcome-email"></a>初期 PIN を設定してようこそメールを送信する

1. RTCUniversalServerAdmins group のメンバーとしてログオンします。
    
2. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
3. コマンド プロンプトで次のコマンドを実行します。
    
   ```
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

**Smtp サーバ**既定では、スクリプトはこのパラメーターは予約されている環境変数 **$PSEmailServer**の値を使用します。 **$PSEmailServer**変数が設定されていない場合は、このパラメーターを指定する必要があります。
    
**資格情報**既定では、スクリプトは、現在のユーザーの資格情報を使用します。 現在のユーザーが、指定のための電子メールを送信するアクセス許可を持っていない場合、アドレスからは、このパラメーターを指定する必要があります。 一般的に、差出人のアドレスに電子メール アドレスを指定しない場合、このパラメーターを指定します。
    
次の例では、新しい PIN を作成し、Marco から Bob にようこそメールを送信します。既定のテンプレートにある電子メール テキストを使用し、HTML 形式で電子メール メッセージを作成します。既定の [件名] は、"ダイヤルイン電話会議へようこそ" です。
  
```
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com"
```

次の例では、Bob に PIN が既に設定されているとしても、Bob の新しい PIN の値を強制的に "383042650" とし、Marco から Bob にようこそメールを送信します。Credential パラメーターが指定されているため、コマンドを実行するユーザーはパスワードを入力するよう求められます。電子メールは、SSL (Secure Sockets Layer) を使用して送信されます。
  
```
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
-Pin "383042650" -Force
-Credential Admin@contoso.com -UseSsl
```