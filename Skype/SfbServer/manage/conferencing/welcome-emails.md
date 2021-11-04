---
title: 会議のダイヤルイン ユーザーにウェルカム メールを送信Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 5507827b-6f8d-4ea4-94e6-1cf72c1d38eb
description: '概要: ユーザーを会議でダイヤルイン会議に参加する方法についてSkype for Business Server。'
ms.openlocfilehash: 64dd7086b1a40de0c0cc2e0b33a66257153541cd
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60772073"
---
# <a name="send-welcome-email-to-dial-in-users-in-skype-for-business-server"></a>会議のダイヤルイン ユーザーにウェルカム メールを送信Skype for Business Server
 
**概要:** ユーザーをダイヤルイン会議に参加する方法については、Skype for Business Server。
  
ダイヤルイン会議とテストを構成して正常に機能しているか確認した後、ユーザーの初期個人識別番号 (PIN) を設定し、機能の可用性についてユーザーに通知する必要があります。 初期 PIN やダイヤルイン会議 web ページへのリンクなどの入門設定できます。 
  
**通常、Set-CsClientPin** コマンドレットを使用して PIN をリセットしますが、PIN 情報を含む入門ウェルカム メールを送信する場合は、このトピックの手順を使用できます。 電子メールを送信しない場合は、代わりに **Set-CsClientPin を** 使用できます。
  
PIN を設定し、1 人のユーザーにようこそメールを送信する場合は、**Set-CsPinSendCAWelcomeMail** スクリプトを使用できます。 既定で、このスクリプトを実行しても、値が既に設定されている場合には PIN をリセットしませんが、Force パラメーターを使用すれば PIN のリセットを強制できます。 電子メール メッセージは、SMTP (Simple Mail Transfer Protocol) を使用して送信されます。
  
**Set-CsPinSendCAWelcomeMail** スクリプトを繰り返し実行して PIN を設定し、ユーザー グループに電子メールを送信するスクリプトを作成できます。 電子メール テンプレート (CAWelcomeEmailTemplate.html ファイル) を変更してイントラネット ページにリンクを追加するか、電子メール テキストを変更できます。
  


## <a name="set-an-initial-pin-and-send-welcome-email"></a>初期 PIN を設定し、ウェルカム メールを送信する

1. RTCUniversalServerAdmins group のメンバーとしてログオンします。
    
2. 管理シェルをSkype for Business Serverする: [**スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[管理シェルSkype for Business Server **クリックします**。
    
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

**SmtpServer** 既定では、スクリプトは、このパラメーターに対して予約済 **$PSEmailServer** 値を使用します。 変数 **$PSEmailServerが** 設定されていない場合は、このパラメーターを指定する必要があります。
    
**資格情報** 既定では、スクリプトは現在のユーザーの資格情報を使用します。 現在のユーザーが指定した From アドレスに代わって電子メールを送信するアクセス許可を持ってない場合は、このパラメーターを指定する必要があります。 一般的なルールとして、電子メール アドレスを From アドレスとして指定しない場合は、このパラメーターを指定します。
    
次の例では、新しい PIN を作成し、Marco から Bob にウェルカム メールを送信します。 既定のテンプレートにある電子メール テキストを使用し、HTML 形式で電子メール メッセージを作成します。 既定の件名は"会議のダイヤルへようこそ" です。
  
```PowerShell
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com"
```

次の例では、Bob に既存の PIN がある場合でも、Bob に対して "383042650" の値を持つ新しい PIN を強制的に作成し、その後、Marco から Bob にウェルカム メールを送信します。 Credential パラメーターが指定されているため、コマンドを実行するユーザーはパスワードを入力するよう求められます。 電子メールは、次の SSL (Secure Sockets Layer使用して送信されます。
  
```PowerShell
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
-Pin "383042650" -Force
-Credential Admin@contoso.com -UseSsl
```
