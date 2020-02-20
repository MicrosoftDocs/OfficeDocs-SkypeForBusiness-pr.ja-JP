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
ms.openlocfilehash: d3a949d1de2c3237e1cd432297a1ce1e1a7f3543
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153337"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="optional-welcome-users-to-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="dbc94-102">オプションLync Server 2013 でのダイヤルイン会議へのユーザーのようこそ</span><span class="sxs-lookup"><span data-stu-id="dbc94-102">(Optional) Welcome users to dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dbc94-103">_**トピックの最終更新日:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="dbc94-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="dbc94-104">ダイヤルイン会議を構成し、正常に機能することを確認した後、ユーザーの初期の暗証番号 (Pin) を設定して、機能の可用性についてユーザーに通知する必要があります。これについては、概要説明など最初の PIN として、およびダイヤルイン会議の設定の web ページへのリンク。</span><span class="sxs-lookup"><span data-stu-id="dbc94-104">After you configure dial-in conferencing and test to verify that it is functioning properly, you should set initial personal identification numbers (PINs) for users and notify users about the availability of the feature, including introductory instructions such as the initial PIN and the link to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="dbc94-105">この手順は省略できます。</span><span class="sxs-lookup"><span data-stu-id="dbc94-105">This step is optional.</span></span> <span data-ttu-id="dbc94-106">通常**は、この**トピックの手順を使用して pin をリセットします。ただし、情報を含むウェルカムメールを送信する場合は、このトピックの手順を初めて使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="dbc94-106">Typically, you use the **Set-CsClientPin** cmdlet to reset PINs, but you can use the procedure in this topic the first time if you want to send a welcome email with the information.</span></span> <span data-ttu-id="dbc94-107">メールを送信しない場合は、代わりに**Set-CsClientPin**を使用できます。</span><span class="sxs-lookup"><span data-stu-id="dbc94-107">If you do not want to send the email, you can use **Set-CsClientPin** instead.</span></span>

<span data-ttu-id="dbc94-108">PIN を設定し、1 人のユーザーにようこそメールを送信する場合は、**Set-CsPinSendCAWelcomeMail** スクリプトを使用できます。</span><span class="sxs-lookup"><span data-stu-id="dbc94-108">You can use the **Set-CsPinSendCAWelcomeMail** script to set the PIN and send a welcome email to a single user.</span></span> <span data-ttu-id="dbc94-109">既定で、このスクリプトを実行しても、値が既に設定されている場合には PIN をリセットしませんが、**Force** パラメーターを使用すれば PIN のリセットを強制できます。</span><span class="sxs-lookup"><span data-stu-id="dbc94-109">By default, the script does not reset a PIN if it is already set, but you can use the **Force** parameter to force reset a PIN.</span></span> <span data-ttu-id="dbc94-110">電子メール メッセージは、SMTP (Simple Mail Transfer Protocol) を使用して送信されます。</span><span class="sxs-lookup"><span data-stu-id="dbc94-110">The email message is sent using Simple Mail Transfer Protocol (SMTP).</span></span>

<span data-ttu-id="dbc94-111">**Set-CsPinSendCAWelcomeMail** スクリプトを繰り返し実行して PIN を設定し、ユーザー グループに電子メールを送信するスクリプトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="dbc94-111">You can create a script that runs the **Set-CsPinSendCAWelcomeMail** script iteratively to set PINs and send email to a group of users.</span></span> <span data-ttu-id="dbc94-112">電子メール テンプレート (**CAWelcomeEmailTemplate.html** ファイル) を変更してイントラネット ページにリンクを追加するか、電子メール テキストを変更できます。</span><span class="sxs-lookup"><span data-stu-id="dbc94-112">You can modify the email template (that is, the **CAWelcomeEmailTemplate.html** file) to add more links to intranet pages or modify the email text.</span></span>

<div>

## <a name="to-set-an-initial-pin-and-send-welcome-email"></a><span data-ttu-id="dbc94-113">初期 PIN を設定してようこそメールを送信するには</span><span class="sxs-lookup"><span data-stu-id="dbc94-113">To set an initial PIN and send welcome email</span></span>

1.  <span data-ttu-id="dbc94-114">RTCUniversalServerAdmins group のメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="dbc94-114">Log on as a member of the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="dbc94-115">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbc94-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="dbc94-116">コマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="dbc94-116">Run the following at the command prompt:</span></span>
    
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
    
    <span data-ttu-id="dbc94-117">**Smtpserver**   既定では、このパラメーターには予約された環境変数 **$PSEmailServer**の値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="dbc94-117">**SmtpServer**   By default, the script uses the value of the reserved environment variable **$PSEmailServer** for this parameter.</span></span> <span data-ttu-id="dbc94-118">**$PSEmailServer**変数が設定されていない場合は、このパラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbc94-118">If the **$PSEmailServer** variable is not set, you must specify this parameter.</span></span>
    
    <span data-ttu-id="dbc94-119">**Credential**   既定では、このスクリプトは現在のユーザーの資格情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="dbc94-119">**Credential**   By default, the script uses the credentials of the current user.</span></span> <span data-ttu-id="dbc94-120">現在のユーザーが、指定された差出人のアドレスに代わって電子メールを送信するためのアクセス許可を持っていない場合は、このパラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbc94-120">If the current user does not have permission to send email on behalf of the specified From address, you must specify this parameter.</span></span> <span data-ttu-id="dbc94-121">一般的なルールとして、電子メールアドレスを差出人アドレスとして指定しない場合は、このパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="dbc94-121">As a general rule, specify this parameter if you do not specify your email address as the From address.</span></span>
    
    <span data-ttu-id="dbc94-122">次にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="dbc94-122">For example:</span></span>
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com"
    
    <span data-ttu-id="dbc94-p106">この例では、新しい PIN を作成し、Marco から Bob にようこそメールを送信します。 既定のテンプレートにある電子メール テキストを使用し、HTML 形式で電子メール メッセージを作成します。 既定の [件名] は、"ダイヤルイン電話会議へようこそ" です。</span><span class="sxs-lookup"><span data-stu-id="dbc94-p106">This example creates a new PIN and then sends a welcome email from Marco to Bob. It uses the email text from the default template and creates the email message in HTML format. The default Subject is "Welcome to Dial In Conferencing".</span></span>
    
    <span data-ttu-id="dbc94-126">別の例:</span><span class="sxs-lookup"><span data-stu-id="dbc94-126">Another example:</span></span>
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
        -Pin "383042650" -Force
        -Credential Admin@contoso.com -UseSsl
    
    <span data-ttu-id="dbc94-p107">この例では、Bob に PIN が既に設定されているとしても、Bob の新しい PIN の値を強制的に "383042650" とし、Marco から Bob にようこそメールを送信します。 Credential パラメーターが指定されているため、コマンドを実行するユーザーはパスワードを入力するよう求められます。 電子メールは、SSL (Secure Sockets Layer) を使用して送信されます。</span><span class="sxs-lookup"><span data-stu-id="dbc94-p107">This example forces a new PIN with a value of "383042650" for Bob, even though Bob had an existing PIN, and then sends a welcome email from Marco to Bob. Because the Credential parameter is specified, the person running the command is prompted to enter a password. The email is sent by using the Secure Sockets Layer (SSL).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

