---
title: 'Lync Server 2013: (オプション) ダイヤルイン会議へのユーザーのようこそ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Welcome users to dial-in conferencing
ms:assetid: caa4fd61-f506-4c09-bb5b-1aa260d7a720
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398846(v=OCS.15)
ms:contentKeyID: 48185443
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4698484c240322623760f1fd308398192bfb928f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216443"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="optional-welcome-users-to-dial-in-conferencing-in-lync-server-2013"></a>オプションLync Server 2013 でのダイヤルイン会議へのユーザーのようこそ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-30_

ダイヤルイン会議を構成し、正常に機能することを確認した後、ユーザーの初期の暗証番号 (Pin) を設定して、機能の可用性についてユーザーに通知する必要があります。これについては、概要説明など最初の PIN として、およびダイヤルイン会議の設定の web ページへのリンク。 この手順は省略できます。 通常**は、この**トピックの手順を使用して pin をリセットします。ただし、情報を含むウェルカムメールを送信する場合は、このトピックの手順を初めて使用することもできます。 メールを送信しない場合は、代わりに**Set-CsClientPin**を使用できます。

PIN を設定し、1 人のユーザーにようこそメールを送信する場合は、**Set-CsPinSendCAWelcomeMail** スクリプトを使用できます。 既定で、このスクリプトを実行しても、値が既に設定されている場合には PIN をリセットしませんが、**Force** パラメーターを使用すれば PIN のリセットを強制できます。 電子メール メッセージは、SMTP (Simple Mail Transfer Protocol) を使用して送信されます。

**Set-CsPinSendCAWelcomeMail** スクリプトを繰り返し実行して PIN を設定し、ユーザー グループに電子メールを送信するスクリプトを作成できます。 電子メール テンプレート (**CAWelcomeEmailTemplate.html** ファイル) を変更してイントラネット ページにリンクを追加するか、電子メール テキストを変更できます。

<div>

## <a name="to-set-an-initial-pin-and-send-welcome-email"></a>初期 PIN を設定してようこそメールを送信するには

1.  RTCUniversalServerAdmins group のメンバーとしてログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

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
    
    **Smtpserver**   既定では、このパラメーターには予約された環境変数 **$PSEmailServer**の値が使用されます。 **$PSEmailServer**変数が設定されていない場合は、このパラメーターを指定する必要があります。
    
    **Credential**   既定では、このスクリプトは現在のユーザーの資格情報を使用します。 現在のユーザーが、指定された差出人のアドレスに代わって電子メールを送信するためのアクセス許可を持っていない場合は、このパラメーターを指定する必要があります。 一般的なルールとして、電子メールアドレスを差出人アドレスとして指定しない場合は、このパラメーターを指定します。
    
    次にその例を示します。
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com"
    
    この例では、新しい PIN を作成し、Marco から Bob にようこそメールを送信します。 既定のテンプレートにある電子メール テキストを使用し、HTML 形式で電子メール メッセージを作成します。 既定の [件名] は、"ダイヤルイン電話会議へようこそ" です。
    
    別の例:
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
        -Pin "383042650" -Force
        -Credential Admin@contoso.com -UseSsl
    
    この例では、Bob に PIN が既に設定されているとしても、Bob の新しい PIN の値を強制的に "383042650" とし、Marco から Bob にようこそメールを送信します。 Credential パラメーターが指定されているため、コマンドを実行するユーザーはパスワードを入力するよう求められます。 電子メールは、SSL (Secure Sockets Layer) を使用して送信されます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

