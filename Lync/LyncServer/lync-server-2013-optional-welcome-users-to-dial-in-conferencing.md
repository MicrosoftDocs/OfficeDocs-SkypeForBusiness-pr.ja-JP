---
title: 'Lync Server 2013: (オプション) ダイヤルイン会議へのユーザーの受け入れ'
TOCTitle: (オプション) ダイヤルイン会議へのユーザーの受け入れ
ms:assetid: caa4fd61-f506-4c09-bb5b-1aa260d7a720
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398846(v=OCS.15)
ms:contentKeyID: 48273578
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# (オプション) Lync Server 2013 でのダイヤルイン会議へのユーザーの受け入れ

 

_**トピックの最終更新日:** 2012-09-30_

ダイヤルイン電話会議を構成し、テストして正常に機能することを確認したら、ユーザーの初期暗証番号 (PIN) を設定し、その機能の可用性に関してユーザーに伝えてください。これには、初期 PIN や、ダイヤルイン電話会議設定 Web ページへのリンクなどについての指示が含まれます。このステップはオプションです。通常は、 **Set-CsClientPin** コマンドレットを使用して PIN をリセットしますが、その情報と一緒にようこそメールを初めて送信する場合は、ここで示す手順を使用できます。ようこそメールを送信しない場合は、代わりに **Set-CsClientPin** を使用できます。

PIN を設定し、1 人のユーザーにようこそメールを送信する場合は、 **Set-CsPinSendCAWelcomeMail** スクリプトを使用できます。既定で、このスクリプトを実行しても、値が既に設定されている場合には PIN をリセットしませんが、 **Force** パラメーターを使用すれば PIN のリセットを強制できます。電子メール メッセージは、SMTP (Simple Mail Transfer Protocol) を使用して送信されます。

**Set-CsPinSendCAWelcomeMail** スクリプトを繰り返し実行して PIN を設定し、ユーザー グループに電子メールを送信するスクリプトを作成できます。電子メール テンプレート ( **CAWelcomeEmailTemplate.html** ファイル) を変更してイントラネット ページにリンクを追加するか、電子メール テキストを変更できます。

## 初期 PIN を設定してようこそメールを送信するには

1.  RTCUniversalServerAdmins group のメンバーとしてログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  コマンド プロンプトで次のコマンドを実行します。
    
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
    
    **SmtpServer**   スクリプトは、既定でこのパラメーターに予約された環境変数 **$PSEmailServer** の値を使用します。 **$PSEmailServer** 変数が設定されていない場合は、このパラメーターを指定する必要があります。
    
    **Credential**   スクリプトは、既定で現在ユーザーの資格情報を使用します。現在ユーザーが、指定した \[差出人\] アドレスに代わって電子メールを送信するアクセス許可を持っていない場合は、このパラメーターを指定する必要があります。一般的な規則として、自分の電子メール アドレスを \[差出人\] アドレスとして指定しない場合は、このパラメーターを指定してください。
    
    次に例を示します。
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com"
    
    この例では、新しい PIN を作成し、Marco から Bob にようこそメールを送信します。既定のテンプレートにある電子メール テキストを使用し、HTML 形式で電子メール メッセージを作成します。既定の \[件名\] は、"ダイヤルイン電話会議へようこそ" です。
    
    別の例:
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
        -Pin "383042650" -Force
        -Credential Admin@contoso.com -UseSsl
    
    この例では、Bob に PIN が既に設定されているとしても、Bob の新しい PIN の値を強制的に "383042650" とし、Marco から Bob にようこそメールを送信します。Credential パラメーターが指定されているため、コマンドを実行するユーザーはパスワードを入力するよう求められます。電子メールは、SSL (Secure Sockets Layer) を使用して送信されます。

