---
title: 'Lync Server 2013: (オプション) ダイヤルイン会議へのユーザーの受け入れ'
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
ms.openlocfilehash: 27abf5da520f1c5befd3a477783bc3f9ae67e1b5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755661"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-welcome-users-to-dial-in-conferencing-in-lync-server-2013"></a>(オプション) Lync Server 2013 でのダイヤルイン会議へのユーザーの受け入れ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-30_

ダイヤルイン会議を構成し、テストを行って正常に機能していることを確認した後、ユーザーの最初の暗証番号 (Pin) を設定し、この機能の利用可能性についてユーザーに通知します。たとえば、基本的な手順も記載されています。最初の PIN として、およびダイヤルイン会議の設定の web ページへのリンク。 この手順は省略可能です。 通常は、ユーザーが Pin をリセットするために、 **Set-CsClientPin**コマンドレットを使用しますが、情報を含むウェルカムメールを送信する場合は、このトピックの手順を初めて使用することができます。 ようこそメールを送信しない場合は、代わりに **Set-CsClientPin** を使用できます。

PIN を設定し、1 人のユーザーにようこそメールを送信する場合は、**Set-CsPinSendCAWelcomeMail** スクリプトを使用できます。 既定では、スクリプトは既に設定されている場合、PIN はリセットされませんが、 **force**パラメーターを使用して pin を強制的にリセットすることができます。 電子メール メッセージは、SMTP (Simple Mail Transfer Protocol) を使用して送信されます。

**Set-CsPinSendCAWelcomeMail** スクリプトを繰り返し実行して PIN を設定し、ユーザー グループに電子メールを送信するスクリプトを作成できます。 メールテンプレート ( **CAWelcomeEmailTemplate**ファイル) を変更して、イントラネットページへのリンクを追加したり、メールのテキストを変更したりすることができます。

<div>

## <a name="to-set-an-initial-pin-and-send-welcome-email"></a>初期の PIN を設定し、[ようこそ] のメールを送信するには

1.  RTCUniversalServerAdmins group のメンバーとしてログオンします。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

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
    
    **Smtpserver**   既定では、スクリプトはこのパラメーターに対して予約された環境変数 **$PSEmailServer**の値を使います。 **$PSEmailServer**変数が設定されていない場合は、このパラメーターを指定する必要があります。
    
    **Credential**   既定では、スクリプトは現在のユーザーの資格情報を使用します。 現在のユーザーが、指定された差出人アドレスに代わってメールを送信するアクセス許可を持っていない場合は、このパラメーターを指定する必要があります。 一般的な規則として、差出人アドレスとしてメールアドレスを指定しない場合は、このパラメーターを指定します。
    
    次に例を示します。
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com"
    
    この例では、新しい PIN を作成し、Marco からボブにウェルカムメールを送信します。 既定のテンプレートにある電子メール テキストを使用し、HTML 形式で電子メール メッセージを作成します。 既定の件名は "会議へようこそ" です。
    
    もう1つの例を次に示します。
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
        -Pin "383042650" -Force
        -Credential Admin@contoso.com -UseSsl
    
    次の例では、ボブが既存の PIN を持っている場合でも、Bob に対して "383042650" という新しい PIN を強制的に使用します。その後、Marco からボブにウェルカムメールを送信します。 Credential パラメーターが指定されているため、コマンドを実行するユーザーはパスワードを入力するよう求められます。 メールは、Secure Sockets Layer (SSL) を使って送信されます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

