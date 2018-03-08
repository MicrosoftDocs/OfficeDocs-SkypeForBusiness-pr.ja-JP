---
title: "ユーザーの発信者番号を設定します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.date: 01/22/2018
ms.topic: article
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
- Strat_SB_PSTN
description: "Office 365 で電話システムでは、ユーザーの割り当てられている電話番号を既定の発信者番号を提供します。変更するかユーザーの (呼び出しの行 ID とも呼ばれます) の発信者番号をブロックすることができます。発信者の使い方、組織内では、組織内の発信者番号を使用する方法の詳細を学びます。"
ms.openlocfilehash: 3ac690bd331e050abd18be8bc559f9ea555c815a
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="set-the-caller-id-for-a-user"></a><span data-ttu-id="44233-105">ユーザーの発信者番号を設定します。</span><span class="sxs-lookup"><span data-stu-id="44233-105">Set the Caller ID for a user</span></span>
<span data-ttu-id="44233-p102">Office 365 で電話システムでは、ユーザーの割り当てられている電話番号を既定の発信者番号を提供します。変更するかユーザーの (呼び出しの行 ID とも呼ばれます) の発信者番号をブロックすることができます。[発信者の使い方組織内](how-can-caller-id-be-used-in-your-organization.md)を移動して、組織内の発信者番号を使用する方法を学びます。</span><span class="sxs-lookup"><span data-stu-id="44233-p102">The Phone System in Office 365 provides a default caller ID that is the user's assigned telephone number. You can either change or block the caller ID (also called a Calling Line ID) for a user. You can learn more about how to use caller ID in your organization by going [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
> [!TIP]
> <span data-ttu-id="44233-109">For Business Online Skype で現在の着信をブロックすることはできません。</span><span class="sxs-lookup"><span data-stu-id="44233-109">You can't block incoming calls currently in Skype for Business Online.</span></span> 
  
<span data-ttu-id="44233-110">変更できる設定があります。</span><span class="sxs-lookup"><span data-stu-id="44233-110">There are settings that you can change:</span></span>
  
> [!NOTE]
> <span data-ttu-id="44233-111">これ**は**Business Server の Lync または Skype の社内組織の場合です。</span><span class="sxs-lookup"><span data-stu-id="44233-111">This **is not** for on-premises organizations with Lync or Skype for Business Server.</span></span>
  
- <span data-ttu-id="44233-p103">**変更の送信の発信者番号**別の電話番号を使って、電話番号には、ユーザーの発信者番号を置き換えることができます。たとえば、業務用の電話番号からメインの電話番号、ユーザーの発信者番号を変更または法的部門のメインの電話番号、電話番号からユーザーの呼び出し行 ID を変更する可能性があります。呼び出す番号を変更すると、オンライン**サービス**の数値を指定することができます (有料またはフリー ダイヤル)。</span><span class="sxs-lookup"><span data-stu-id="44233-p103">**Change their outgoing caller ID** You can replace a user's Caller ID, which by default is their telephone number, with another phone number. For example, you could change the user's Caller ID from their phone number to a main phone number for your business or change the user's Calling Line ID from their phone number to a main phone number for the legal department. You can change the Calling ID number to any Online **service** number (toll or toll-free).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="44233-115">_サービス_のパラメーターを使用する場合は、有効なサービス数を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="44233-115">If you want to use the  _Service_ parameter, you must specify a valid service number.</span></span>
  
- <span data-ttu-id="44233-p104">**ブロックの外部の発信者番号**PSTN 通話を発信するユーザーの送信されない送信の発信者番号をブロックすることができます。これから呼び出される人の電話に表示されている電話番号がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="44233-p104">**Block their outbound caller ID** You can block the outgoing Caller ID from being sent on a user's outgoing PSTN calls. Doing this will block their phone number from being displayed on the phone of a person being called.</span></span>
    
- <span data-ttu-id="44233-118">**ブロックの着信の発信者番号**発信者番号を受信しない、PSTN 通話を受信したユーザーをブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="44233-118">**Block their incoming caller ID** You can block a user from receiving Caller ID on any incoming PSTN calls.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="44233-119">緊急の通話には、常にユーザーの電話番号 (発信者) が送信されます。</span><span class="sxs-lookup"><span data-stu-id="44233-119">Emergency calls will always send the user's telephone number (caller ID).</span></span> 
  
<span data-ttu-id="44233-p105">既定では、これらの呼び出し元 ID 設定がすべて**オフになっています**。つまりと、そのユーザーは、PSTN の電話番号に通話を Skype for Business Online のユーザーの電話番号を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="44233-p105">By default, all of these caller ID settings are **turned off**. This means that the Skype for Business Online user's phone number can be seen when that user makes a call to a PSTN phone.</span></span>
  
<span data-ttu-id="44233-122">これらの設定と使用する方法の詳細については、[発信者の使い方組織内](how-can-caller-id-be-used-in-your-organization.md)を移動します。</span><span class="sxs-lookup"><span data-stu-id="44233-122">To learn more about these settings and how you can use them, go [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
## <a name="set-your-caller-id-policy-settings"></a><span data-ttu-id="44233-123">ID ポリシーの呼び出し元の設定します。</span><span class="sxs-lookup"><span data-stu-id="44233-123">Set your caller ID policy settings</span></span>

> [!NOTE]
> <span data-ttu-id="44233-124">Skype for Business Online 発信者設定のすべての Windows PowerShell と**使用できない** **Skype for Business 管理センター**を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="44233-124">For all of the Caller ID settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="44233-125">確認し、Windows PowerShell を起動する.</span><span class="sxs-lookup"><span data-stu-id="44233-125">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="44233-126">**3.0 以降のバージョンの Windows PowerShell が実行していることを確認します。**</span><span class="sxs-lookup"><span data-stu-id="44233-126">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="44233-127">3.0 以降のバージョンが実行していることを確認する: **[スタート] メニュー** > **Windows PowerShell**します。</span><span class="sxs-lookup"><span data-stu-id="44233-127">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="44233-128">**Windows PowerShell**のウィンドウで_ホストの取得_を入力して、バージョンを確認してください。</span><span class="sxs-lookup"><span data-stu-id="44233-128">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="44233-p106">バージョン 3.0 以降をお持ちでない場合は、ダウンロードして、Windows PowerShell への更新プログラムをインストールする必要があります。[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845)をダウンロードして 4.0 への Windows PowerShell を更新するを参照してください。表示されたら、お使いのコンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="44233-p106">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="44233-p107">Skype for Business Online できるようにする Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成するのには、Windows PowerShell モジュールをインストールする必要もします。このモジュールでは、64 ビット版コンピューターにのみサポートされているが、 [Skype for Business Online 用の Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)では、Microsoft ダウンロード センターからダウンロードできます。求められた場合は、お使いのコンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="44233-p107">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="44233-135">さらに詳しく調べ必要がある場合は、[単一の Windows PowerShell ウィンドウ内のすべての Office 365 サービスへの接続](https://technet.microsoft.com/EN-US/library/dn568015.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44233-135">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="44233-136">**Windows PowerShell セッションを開始します。**</span><span class="sxs-lookup"><span data-stu-id="44233-136">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="44233-137">**[スタート] メニュー**から > **Windows PowerShell**します。</span><span class="sxs-lookup"><span data-stu-id="44233-137">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="44233-138">**Windows PowerShell**ウィンドウで、実行して、Office 365 の組織に接続します。</span><span class="sxs-lookup"><span data-stu-id="44233-138">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="44233-139">Skype for Business Online の Windows PowerShell モジュールに使用する**インポート モジュール**の最初のレコード] コマンドの実行にのみがあります。</span><span class="sxs-lookup"><span data-stu-id="44233-139">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
> 
  ```
Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  ```
> 
  ```
  $credential = Get-Credential
  ```
> 
  ```
  $session = New-CsOnlineSession -Credential $credential
  ```
> 
  ```
  Import-PSSession $session
  ```

<span data-ttu-id="44233-140">詳細については、Windows PowerShell を開始する場合は、[単一の Windows PowerShell ウィンドウ内のすべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)」または「 [Skype for Business Online Windows PowerShell を使用してへ接続](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44233-140">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a><span data-ttu-id="44233-141">発信者 ID ポリシーの設定を組織内のすべてを参照してください。</span><span class="sxs-lookup"><span data-stu-id="44233-141">See all of the caller ID policy settings in your organization</span></span>

- <span data-ttu-id="44233-142">組織では、すべての呼び出し元の ID ポリシーの設定を表示、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="44233-142">To view all of the caller ID policy settings in your organization, run:</span></span>

  ```
  Get-CsCallingLineIdentity |fl
  ```
<span data-ttu-id="44233-143">[Get CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793856.aspx)の他の例と詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44233-143">See more examples and details for [Get-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793856.aspx).</span></span>
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a><span data-ttu-id="44233-144">組織用の新しい発信者 ID ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="44233-144">Create a new caller ID policy for your organization</span></span>

- <span data-ttu-id="44233-145">匿名の発信者番号を設定する新しい発信者 ID ポリシーを作成するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="44233-145">To create a new caller ID policy that sets the caller ID to anonymous, run:</span></span>
    
  ```
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```

  <span data-ttu-id="44233-146">[新規 CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793855.aspx)の他の例と詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44233-146">See more examples and details for [New-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793855.aspx).</span></span>
    
- <span data-ttu-id="44233-147">Amos 大理石に作成した新しいポリシーを適用するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="44233-147">To apply the new policy you created to Amos Marble, run:</span></span>
    
  ```
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  <span data-ttu-id="44233-148">[許可を付与する CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx)コマンドレットの詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44233-148">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) cmdlet.</span></span>
    
<span data-ttu-id="44233-149">既にポリシーを作成している場合は、[セット CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx)コマンドレットを使用して、既存のポリシーを変更してをユーザーに、設定を適用する[許可を付与する CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx)コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="44233-149">If you have already created a policy, you can use the [Set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a><span data-ttu-id="44233-150">着信、発信者がブロックされているように設定します。</span><span class="sxs-lookup"><span data-stu-id="44233-150">Set it so the incoming caller ID is blocked</span></span>

- <span data-ttu-id="44233-151">着信の発信者番号をブロックするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="44233-151">To block the incoming caller ID, run:</span></span>
    
  ```
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  <span data-ttu-id="44233-152">[セット CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx)その他の例と詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44233-152">See more examples and details for [Set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx).</span></span>
    
- <span data-ttu-id="44233-153">作成したポリシーの設定を適用するには、組織内のユーザーに、次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="44233-153">To apply the policy setting you created to a user in your organization, run:</span></span>
    
  ```
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```
    <span data-ttu-id="44233-154">[許可を付与する CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx)コマンドレットの詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44233-154">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) cmdlet.</span></span>
    
### <a name="remove-a-caller-id-policy"></a><span data-ttu-id="44233-155">発信者 ID ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="44233-155">Remove a caller ID policy</span></span>

<span data-ttu-id="44233-156">組織内のポリシーを削除するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="44233-156">To remove a policy from your organization, run:</span></span>
  
```
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
<span data-ttu-id="44233-157">ポリシーを削除するユーザーから、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="44233-157">To remove a policy from a user, run:</span></span>
  
```
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="44233-158">Windows PowerShell の詳細を知りたいとしていますか。</span><span class="sxs-lookup"><span data-stu-id="44233-158">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="44233-p108">Windows powershell となるはすべてを管理するユーザーとユーザーの許可または使用できません。Windows PowerShell で Office 365 と Skype for Business Online の複数のタスクを実行するがある場合、日常業務を簡素化する管理の 1 つのポイントを使用して管理できます。Windows PowerShell で開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="44233-p108">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="44233-162">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="44233-162">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="44233-163">Office 365 の管理に Windows PowerShell を使用する理由 6 つの理由</span><span class="sxs-lookup"><span data-stu-id="44233-163">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365 </span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="44233-p109">Windows PowerShell では多くの利点速度、わかりやすいように、および生産性でのみ実行しようとする設定の変更、多くのユーザーに一度になどの Office 365 管理センターを使用します。次のトピックでこれらの利点について学習します。</span><span class="sxs-lookup"><span data-stu-id="44233-p109">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="44233-166">Windows PowerShell で Office 365 を管理する最善の方法</span><span class="sxs-lookup"><span data-stu-id="44233-166">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="44233-167">Windows PowerShell を使用して、Skype for Business Online の管理するには</span><span class="sxs-lookup"><span data-stu-id="44233-167">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="44233-168">Windows PowerShell を使用して、共通の Skype for Business Online の管理タスクを実行するには</span><span class="sxs-lookup"><span data-stu-id="44233-168">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="44233-169">関連トピック</span><span class="sxs-lookup"><span data-stu-id="44233-169">Related topics</span></span>
[<span data-ttu-id="44233-170">電話番号のよく寄せられる質問を転送します。</span><span class="sxs-lookup"><span data-stu-id="44233-170">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)

[<span data-ttu-id="44233-171">さまざまなプランの呼び出し用の電話番号</span><span class="sxs-lookup"><span data-stu-id="44233-171">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="44233-172">組織の電話番号を管理します。</span><span class="sxs-lookup"><span data-stu-id="44233-172">Manage phone numbers for your organization</span></span>](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="44233-173">緊急の呼び出し元の条項および条件</span><span class="sxs-lookup"><span data-stu-id="44233-173">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

[<span data-ttu-id="44233-174">Skype for Business Online: 緊急発信免責事項のラベル</span><span class="sxs-lookup"><span data-stu-id="44233-174">Skype for Business Online: Emergency Calling disclaimer label</span></span>](https://go.microsoft.com/fwlink/?LinkID=692099)
  

