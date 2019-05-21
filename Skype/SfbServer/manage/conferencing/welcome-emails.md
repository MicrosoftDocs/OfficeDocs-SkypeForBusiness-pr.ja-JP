---
title: Skype for Business Server でダイヤルインユーザーにウェルカムメールを送信する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5507827b-6f8d-4ea4-94e6-1cf72c1d38eb
description: '概要: Skype for Business Server でユーザーをダイヤルイン会議にようこそ方法について説明します。'
ms.openlocfilehash: db2e8bd84fa6a03bad845a87f7fb3c1532ae7ec2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280307"
---
# <a name="send-welcome-email-to-dial-in-users-in-skype-for-business-server"></a>Skype for Business Server でダイヤルインユーザーにウェルカムメールを送信する
 
**概要:** Skype for Business Server でユーザーをダイヤルイン会議にようこそ方法について説明します。
  
ダイヤルイン電話会議を構成し、テストして正常に機能することを確認したら、ユーザーの初期暗証番号 (PIN) を設定し、その機能の可用性に関してユーザーに伝えてください。 これには、初期 PIN や、ダイヤルイン電話会議設定 Web ページへのリンクなどについての指示を含めることができます。 
  
通常、pin をリセットするには、 **CsClientPin の Set**コマンドレットを使用しますが、pin 情報を使って紹介のウェルカムメールを送信する場合は、このトピックの手順を使用できます。 ようこそメールを送信しない場合は、代わりに **Set-CsClientPin** を使用できます。
  
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

**Smtpserver**既定では、スクリプトはこのパラメーターに対して予約された環境変数 **$PSEmailServer**の値を使います。 **$PSEmailServer**変数が設定されていない場合は、このパラメーターを指定する必要があります。
    
**資格情報**既定では、スクリプトは現在のユーザーの資格情報を使用します。 現在のユーザーが、指定された差出人アドレスに代わってメールを送信するアクセス許可を持っていない場合は、このパラメーターを指定する必要があります。 一般的な規則として、差出人アドレスとしてメールアドレスを指定しない場合は、このパラメーターを指定します。
    
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
