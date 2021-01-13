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
# <a name="send-welcome-email-to-dial-in-users-in-skype-for-business-server"></a><span data-ttu-id="71b2e-103">Skype for Business Server でダイヤルイン ユーザーにようこそメールを送信する</span><span class="sxs-lookup"><span data-stu-id="71b2e-103">Send welcome email to dial-in users in Skype for Business Server</span></span>
 
<span data-ttu-id="71b2e-104">**概要:** Skype for Business Server でユーザーをダイヤルイン会議に参加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="71b2e-104">**Summary:** Learn how to welcome users to dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="71b2e-105">ダイヤルイン会議を構成し、テストして正常に機能しているか確認した後、ユーザーの初期の個人識別番号 (PIN) を設定し、機能の可用性についてユーザーに通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71b2e-105">After you configure dial-in conferencing and test to verify that it is functioning properly, you should set initial personal identification numbers (PINs) for users and notify users about the availability of the feature.</span></span> <span data-ttu-id="71b2e-106">初期 PIN やダイヤルイン会議の設定 Web ページへのリンクなどの導入手順を含めできます。</span><span class="sxs-lookup"><span data-stu-id="71b2e-106">You can include introductory instructions such as the initial PIN and the link to the Dial-in Conferencing Settings web page.</span></span> 
  
<span data-ttu-id="71b2e-107">通常は **Set-CsClientPin** コマンドレットを使用して PIN をリセットしますが、PIN 情報を記載した入門用のウェルカム メールを送信する場合は、このトピックの手順を使用できます。</span><span class="sxs-lookup"><span data-stu-id="71b2e-107">Typically, you use the **Set-CsClientPin** cmdlet to reset PINs, but you can use the procedure in this topic if you want to send an introductory welcome email with the PIN information.</span></span> <span data-ttu-id="71b2e-108">電子メールを送信しない場合は、代わりに **Set-CsClientPin を** 使用できます。</span><span class="sxs-lookup"><span data-stu-id="71b2e-108">If you do not want to send the email, you can use **Set-CsClientPin** instead.</span></span>
  
<span data-ttu-id="71b2e-109">PIN を設定し、1 人のユーザーにようこそメールを送信する場合は、**Set-CsPinSendCAWelcomeMail** スクリプトを使用できます。</span><span class="sxs-lookup"><span data-stu-id="71b2e-109">You can use the **Set-CsPinSendCAWelcomeMail** script to set the PIN and send a welcome email to a single user.</span></span> <span data-ttu-id="71b2e-110">既定で、このスクリプトを実行しても、値が既に設定されている場合には PIN をリセットしませんが、Force パラメーターを使用すれば PIN のリセットを強制できます。</span><span class="sxs-lookup"><span data-stu-id="71b2e-110">By default, the script does not reset a PIN if it is already set, but you can use the Force parameter to force reset a PIN.</span></span> <span data-ttu-id="71b2e-111">電子メール メッセージは、SMTP (Simple Mail Transfer Protocol) を使用して送信されます。</span><span class="sxs-lookup"><span data-stu-id="71b2e-111">The email message is sent using Simple Mail Transfer Protocol (SMTP).</span></span>
  
<span data-ttu-id="71b2e-112">**Set-CsPinSendCAWelcomeMail** スクリプトを繰り返し実行して PIN を設定し、ユーザー グループに電子メールを送信するスクリプトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="71b2e-112">You can create a script that runs the **Set-CsPinSendCAWelcomeMail** script iteratively to set PINs and send email to a group of users.</span></span> <span data-ttu-id="71b2e-113">電子メール テンプレート (CAWelcomeEmailTemplate.html ファイル) を変更してイントラネット ページにリンクを追加するか、電子メール テキストを変更できます。</span><span class="sxs-lookup"><span data-stu-id="71b2e-113">You can modify the email template (that is, the CAWelcomeEmailTemplate.html file) to add more links to intranet pages or modify the email text.</span></span>
  


## <a name="set-an-initial-pin-and-send-welcome-email"></a><span data-ttu-id="71b2e-114">初期 PIN を設定してようこそメールを送信する</span><span class="sxs-lookup"><span data-stu-id="71b2e-114">Set an initial PIN and send welcome email</span></span>

1. <span data-ttu-id="71b2e-115">RTCUniversalServerAdmins group のメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="71b2e-115">Log on as a member of the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="71b2e-116">Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理シェル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="71b2e-116">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="71b2e-117">コマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="71b2e-117">Run the following at the command prompt:</span></span>
    
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

<span data-ttu-id="71b2e-118">**SmtpServer** 既定では、スクリプトは予約された環境変数の値をこのパラメーター **$PSEmailServer** 使用します。</span><span class="sxs-lookup"><span data-stu-id="71b2e-118">**SmtpServer** By default, the script uses the value of the reserved environment variable **$PSEmailServer** for this parameter.</span></span> <span data-ttu-id="71b2e-119">変数$PSEmailServer **設定** しない場合は、このパラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71b2e-119">If the **$PSEmailServer** variable is not set, you must specify this parameter.</span></span>
    
<span data-ttu-id="71b2e-120">**資格情報** 既定では、スクリプトは現在のユーザーの資格情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="71b2e-120">**Credential** By default, the script uses the credentials of the current user.</span></span> <span data-ttu-id="71b2e-121">現在のユーザーに、指定した From アドレスの代わりに電子メールを送信するアクセス許可が付与されていない場合は、このパラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71b2e-121">If the current user does not have permission to send email on behalf of the specified From address, you must specify this parameter.</span></span> <span data-ttu-id="71b2e-122">一般に、電子メール アドレスを From アドレスとして指定しない場合は、このパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="71b2e-122">As a general rule, specify this parameter if you do not specify your email address as the From address.</span></span>
    
<span data-ttu-id="71b2e-123">次の例では、新しい PIN を作成し、Bob に Bob からようこそメールを送信します。</span><span class="sxs-lookup"><span data-stu-id="71b2e-123">The following example creates a new PIN, and then sends a welcome email from Marco to Bob.</span></span> <span data-ttu-id="71b2e-124">既定のテンプレートにある電子メール テキストを使用し、HTML 形式で電子メール メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="71b2e-124">It uses the email text from the default template and creates the email message in HTML format.</span></span> <span data-ttu-id="71b2e-125">既定の件名は "ダイヤルイン会議へようこそ" です。</span><span class="sxs-lookup"><span data-stu-id="71b2e-125">The default Subject is "Welcome to Dial In Conferencing":</span></span>
  
```PowerShell
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com"
```

<span data-ttu-id="71b2e-126">次の例では、Bob が既存の PIN を持っていた場合でも、Bob に対して値 "383042650" の新しい PIN を強制的に設定し、次に、Bob から Bob にようこそメールを送信します。</span><span class="sxs-lookup"><span data-stu-id="71b2e-126">The next example forces a new PIN with a value of "383042650" for Bob, even though Bob had an existing PIN, and then sends a welcome email from Marco to Bob.</span></span> <span data-ttu-id="71b2e-127">Credential パラメーターが指定されているため、コマンドを実行するユーザーはパスワードを入力するよう求められます。</span><span class="sxs-lookup"><span data-stu-id="71b2e-127">Because the Credential parameter is specified, the person running the command is prompted to enter a password.</span></span> <span data-ttu-id="71b2e-128">電子メールは SSL (Secure Sockets Layer使用して送信されます。</span><span class="sxs-lookup"><span data-stu-id="71b2e-128">The email is sent by using the Secure Sockets Layer (SSL):</span></span>
  
```PowerShell
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
-Pin "383042650" -Force
-Credential Admin@contoso.com -UseSsl
```
