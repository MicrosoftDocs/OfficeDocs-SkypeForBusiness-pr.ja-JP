---
title: Skype for Business Server 2015 でのダイヤルイン ユーザーへのようこそメールの送信
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5507827b-6f8d-4ea4-94e6-1cf72c1d38eb
description: '概要: ビジネス サーバー 2015 の Skype のユーザーがダイヤルイン会議を開始する方法を説明します。'
ms.openlocfilehash: 0aa939e2ef742c554339967e31204461bca52b6f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="send-welcome-email-to-dial-in-users-in-skype-for-business-server-2015"></a><span data-ttu-id="dd34f-103">Skype for Business Server 2015 でのダイヤルイン ユーザーへのようこそメールの送信</span><span class="sxs-lookup"><span data-stu-id="dd34f-103">Send welcome email to dial-in users in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="dd34f-104">**の概要:**ビジネス サーバー 2015 の Skype のユーザーがダイヤルイン会議を開始する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="dd34f-104">**Summary:** Learn how to welcome users to dial-in conferencing in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="dd34f-105">ダイヤルイン電話会議を構成し、テストして正常に機能することを確認したら、ユーザーの初期暗証番号 (PIN) を設定し、その機能の可用性に関してユーザーに伝えてください。</span><span class="sxs-lookup"><span data-stu-id="dd34f-105">After you configure dial-in conferencing and test to verify that it is functioning properly, you should set initial personal identification numbers (PINs) for users and notify users about the availability of the feature.</span></span> <span data-ttu-id="dd34f-106">これには、初期 PIN や、ダイヤルイン電話会議設定 Web ページへのリンクなどについての指示を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="dd34f-106">You can include introductory instructions such as the initial PIN and the link to the Dial-in Conferencing Settings web page.</span></span> 
  
<span data-ttu-id="dd34f-107">通常、**セット CsClientPin**コマンドレットを使用して、Pin をリセットするのには、暗証番号 (pin) の情報を紹介、登録完了メールを送信する場合は、このトピックの手順を使用できます。</span><span class="sxs-lookup"><span data-stu-id="dd34f-107">Typically, you use the **Set-CsClientPin** cmdlet to reset PINs, but you can use the procedure in this topic if you want to send an introductory welcome email with the PIN information.</span></span> <span data-ttu-id="dd34f-108">ようこそメールを送信しない場合は、代わりに **Set-CsClientPin** を使用できます。</span><span class="sxs-lookup"><span data-stu-id="dd34f-108">If you do not want to send the email, you can use **Set-CsClientPin** instead.</span></span>
  
<span data-ttu-id="dd34f-p103">PIN を設定し、1 人のユーザーにようこそメールを送信する場合は、**Set-CsPinSendCAWelcomeMail** スクリプトを使用できます。既定で、このスクリプトを実行しても、値が既に設定されている場合には PIN をリセットしませんが、Force パラメーターを使用すれば PIN のリセットを強制できます。電子メール メッセージは、SMTP (Simple Mail Transfer Protocol) を使用して送信されます。</span><span class="sxs-lookup"><span data-stu-id="dd34f-p103">You can use the **Set-CsPinSendCAWelcomeMail** script to set the PIN and send a welcome email to a single user. By default, the script does not reset a PIN if it is already set, but you can use the Force parameter to force reset a PIN. The email message is sent using Simple Mail Transfer Protocol (SMTP).</span></span>
  
<span data-ttu-id="dd34f-p104">**Set-CsPinSendCAWelcomeMail** スクリプトを繰り返し実行して PIN を設定し、ユーザー グループに電子メールを送信するスクリプトを作成できます。電子メール テンプレート (CAWelcomeEmailTemplate.html ファイル) を変更してイントラネット ページにリンクを追加するか、電子メール テキストを変更できます。</span><span class="sxs-lookup"><span data-stu-id="dd34f-p104">You can create a script that runs the **Set-CsPinSendCAWelcomeMail** script iteratively to set PINs and send email to a group of users. You can modify the email template (that is, the CAWelcomeEmailTemplate.html file) to add more links to intranet pages or modify the email text.</span></span>
  
## 

### <a name="set-an-initial-pin-and-send-welcome-email"></a><span data-ttu-id="dd34f-114">初期 PIN を設定してようこそメールを送信する</span><span class="sxs-lookup"><span data-stu-id="dd34f-114">Set an initial PIN and send welcome email</span></span>

1. <span data-ttu-id="dd34f-115">RTCUniversalServerAdmins group のメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="dd34f-115">Log on as a member of the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="dd34f-116">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="dd34f-116">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="dd34f-117">コマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="dd34f-117">Run the following at the command prompt:</span></span>
    
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

<span data-ttu-id="dd34f-118">**Smtp サーバ**既定では、スクリプトはこのパラメーターは予約されている環境変数**$PSEmailServer**の値を使用します。</span><span class="sxs-lookup"><span data-stu-id="dd34f-118">**SmtpServer** By default, the script uses the value of the reserved environment variable **$PSEmailServer** for this parameter.</span></span> <span data-ttu-id="dd34f-119">**$PSEmailServer**変数が設定されていない場合は、このパラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd34f-119">If the **$PSEmailServer** variable is not set, you must specify this parameter.</span></span>
    
<span data-ttu-id="dd34f-120">**資格情報**既定では、スクリプトは、現在のユーザーの資格情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="dd34f-120">**Credential** By default, the script uses the credentials of the current user.</span></span> <span data-ttu-id="dd34f-121">現在のユーザーが、指定のための電子メールを送信するアクセス許可を持っていない場合、アドレスからは、このパラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd34f-121">If the current user does not have permission to send email on behalf of the specified From address, you must specify this parameter.</span></span> <span data-ttu-id="dd34f-122">一般的に、差出人のアドレスに電子メール アドレスを指定しない場合、このパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="dd34f-122">As a general rule, specify this parameter if you do not specify your email address as the From address.</span></span>
    
<span data-ttu-id="dd34f-p107">次の例では、新しい PIN を作成し、Marco から Bob にようこそメールを送信します。既定のテンプレートにある電子メール テキストを使用し、HTML 形式で電子メール メッセージを作成します。既定の [件名] は、"ダイヤルイン電話会議へようこそ" です。</span><span class="sxs-lookup"><span data-stu-id="dd34f-p107">The following example creates a new PIN, and then sends a welcome email from Marco to Bob. It uses the email text from the default template and creates the email message in HTML format. The default Subject is "Welcome to Dial In Conferencing":</span></span>
  
```
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com"
```

<span data-ttu-id="dd34f-p108">次の例では、Bob に PIN が既に設定されているとしても、Bob の新しい PIN の値を強制的に "383042650" とし、Marco から Bob にようこそメールを送信します。Credential パラメーターが指定されているため、コマンドを実行するユーザーはパスワードを入力するよう求められます。電子メールは、SSL (Secure Sockets Layer) を使用して送信されます。</span><span class="sxs-lookup"><span data-stu-id="dd34f-p108">The next example forces a new PIN with a value of "383042650" for Bob, even though Bob had an existing PIN, and then sends a welcome email from Marco to Bob. Because the Credential parameter is specified, the person running the command is prompted to enter a password. The email is sent by using the Secure Sockets Layer (SSL):</span></span>
  
```
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
-Pin "383042650" -Force
-Credential Admin@contoso.com -UseSsl
```