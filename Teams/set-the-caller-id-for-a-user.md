---
title: ユーザーに発信者番号を設定する
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: Microsoft 365 および Office 365 の既定の発信者番号 (ユーザーに割り当てられた電話番号) について説明します。これには、発信行 ID とも呼ばれます。 ユーザーの発信者番号通知を変更またはブロックすることができます。
ms.openlocfilehash: 3c39497618927c20d1103b9aaaec82960a06d56c
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255430"
---
# <a name="set-the-caller-id-for-a-user"></a><span data-ttu-id="331f5-104">ユーザーに発信者番号を設定する</span><span class="sxs-lookup"><span data-stu-id="331f5-104">Set the Caller ID for a user</span></span>
<span data-ttu-id="331f5-105">Microsoft 365 および Office 365 の電話システムでは、ユーザーに割り当てられた電話番号である既定の発信者番号を提供します。</span><span class="sxs-lookup"><span data-stu-id="331f5-105">The Phone System in Microsoft 365 and Office 365 provides a default caller ID that is the user's assigned telephone number.</span></span> <span data-ttu-id="331f5-106">ユーザーのために発信者番号 (通話回線番号) を変更または禁止することができます。</span><span class="sxs-lookup"><span data-stu-id="331f5-106">You can either change or block the caller ID (also called a Calling Line ID) for a user.</span></span> <span data-ttu-id="331f5-107">組織での発信者番号の使用方法の詳細については、[組織内での発信者番号の使用方法](how-can-caller-id-be-used-in-your-organization.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="331f5-107">You can learn more about how to use caller ID in your organization by going [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
> [!TIP]
> <span data-ttu-id="331f5-108">Skype for Business Online で、着信通話を遮断することは現時点ではできません。</span><span class="sxs-lookup"><span data-stu-id="331f5-108">You can't block incoming calls currently in Skype for Business Online.</span></span> 
  
<span data-ttu-id="331f5-109">次の設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="331f5-109">There are settings that you can change:</span></span>
  
> [!NOTE]
> <span data-ttu-id="331f5-110">これは、Lync または Skype for Business Server を使用するオンプレミスの組織向け **ではありません**</span><span class="sxs-lookup"><span data-stu-id="331f5-110">This **is not** for on-premises organizations with Lync or Skype for Business Server.</span></span>
  
- <span data-ttu-id="331f5-p103">**発信する発信者番号を変更する**: ユーザーの発信者番号は、既定で電話番号になっていますが、別の電話番号に置き換えることができます。たとえば、ユーザーの発信者番号を個人電話番号から会社の代表電話番号に変更したり、ユーザーの通話回線番号を個人電話番号から法務部の代表電話番号に変更したりできます。発信者番号はどのオンライン **サービス** 番号 (有料電話番号または無料電話番号) にでも変更することができます。</span><span class="sxs-lookup"><span data-stu-id="331f5-p103">**Change their outgoing caller ID** You can replace a user's Caller ID, which by default is their telephone number, with another phone number. For example, you could change the user's Caller ID from their phone number to a main phone number for your business or change the user's Calling Line ID from their phone number to a main phone number for the legal department. You can change the Calling ID number to any Online **service** number (toll or toll-free).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="331f5-114">_Service_ パラメーターを使用する場合は、有効のサービス番号を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="331f5-114">If you want to use the  _Service_ parameter, you must specify a valid service number.</span></span>
  
- <span data-ttu-id="331f5-p104">**発信する発信者番号を禁止する**: ユーザーの発信する PSTN 通話に発信者番号が送信されるのを禁止することができます。このようにすると、呼び出し中の電話に電話番号が表示されるのを禁止することができます。</span><span class="sxs-lookup"><span data-stu-id="331f5-p104">**Block their outbound caller ID** You can block the outgoing Caller ID from being sent on a user's outgoing PSTN calls. Doing this will block their phone number from being displayed on the phone of a person being called.</span></span>
    
- <span data-ttu-id="331f5-117">**着信する発信者番号を禁止する**: あらゆる着信 PSTN 通話でユーザーが発信者番号を受信できないようにします。</span><span class="sxs-lookup"><span data-stu-id="331f5-117">**Block their incoming caller ID** You can block a user from receiving Caller ID on any incoming PSTN calls.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="331f5-118">緊急通話では、ユーザーの電話番号 (発信者番号) が常に送信されます。</span><span class="sxs-lookup"><span data-stu-id="331f5-118">Emergency calls will always send the user's telephone number (caller ID).</span></span> 
  
<span data-ttu-id="331f5-p105">既定では、これらのすべての発信者番号設定が **オフ** になっています。このため、Skype for Business Online のユーザーが PSTN 電話に通話を発信すると、そのユーザーの電話番号は相手に表示されることになります。</span><span class="sxs-lookup"><span data-stu-id="331f5-p105">By default, all of these caller ID settings are **turned off**. This means that the Skype for Business Online user's phone number can be seen when that user makes a call to a PSTN phone.</span></span>
  
<span data-ttu-id="331f5-121">これらの設定と使用方法の詳細については、[組織内での発信者番号の使用方法](how-can-caller-id-be-used-in-your-organization.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="331f5-121">To learn more about these settings and how you can use them, go [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
## <a name="set-your-caller-id-policy-settings"></a><span data-ttu-id="331f5-122">発信者番号ポリシー設定を設定する</span><span class="sxs-lookup"><span data-stu-id="331f5-122">Set your caller ID policy settings</span></span>

> [!NOTE]
> <span data-ttu-id="331f5-123">Skype for Business Online のすべての発信者番号設定では、Windows PowerShell を使用する必要があります。 **Skype for Business 管理センター** を **使用することはできません**。</span><span class="sxs-lookup"><span data-stu-id="331f5-123">For all of the Caller ID settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="331f5-124">Windows PowerShell を検証および開始する</span><span class="sxs-lookup"><span data-stu-id="331f5-124">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="331f5-125">**Windows PowerShell バージョン 3.0 以降を実行していることを確認する**</span><span class="sxs-lookup"><span data-stu-id="331f5-125">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="331f5-126">3.0 以降のバージョンが実行されていることを確認する場合: **[スタート] メニュー** > **[Windows PowerShell]**。</span><span class="sxs-lookup"><span data-stu-id="331f5-126">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="331f5-127">[ _Windows PowerShell_] ウィンドウに「 **Get-Host**」と入力して、バージョンを確認します。</span><span class="sxs-lookup"><span data-stu-id="331f5-127">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="331f5-128">バージョン 3.0 以降を使用していない場合は、Windows PowerShell の更新プログラムをダウンロードおよびインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="331f5-128">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="331f5-129">Windows PowerShell をバージョン4.0 にダウンロードして更新するには、「 [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="331f5-129">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="331f5-130">メッセージが表示されたら、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="331f5-130">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="331f5-p107">Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できるように、Skype for Business Online の Windows PowerShell モジュールもインストールする必要があります。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。メッセージが表示されたら、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="331f5-p107">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="331f5-134">詳細については、「 [単一の Windows PowerShell ウィンドウですべての Microsoft 365 または Office 365 サービスに接続する](https://technet.microsoft.com/library/dn568015.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="331f5-134">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="331f5-135">**Windows PowerShell セッションを開始する**</span><span class="sxs-lookup"><span data-stu-id="331f5-135">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="331f5-136">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="331f5-136">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="331f5-137">**Windows PowerShell**ウィンドウで、次を実行して Microsoft 365 または Office 365 に接続します。</span><span class="sxs-lookup"><span data-stu-id="331f5-137">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="331f5-138">Skype for Business Online Windows PowerShell モジュールを初めて使用するときに、 **Import-Module** コマンドを実行するだけです。</span><span class="sxs-lookup"><span data-stu-id="331f5-138">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
   > 
   ```PowerShell
    Import-Module -Name SkypeOnlineConnector
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

<span data-ttu-id="331f5-139">Windows PowerShell の起動の詳細については、「 [1 つの Windows powershell ウィンドウですべての Microsoft 365 または Office 365 サービスに接続](https://technet.microsoft.com/library/dn568015.aspx) する」または「 [windows powershell 用のコンピューターをセットアップ](/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="331f5-139">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a><span data-ttu-id="331f5-140">組織内のすべての発信者番号のポリシー設定を表示する</span><span class="sxs-lookup"><span data-stu-id="331f5-140">See all of the caller ID policy settings in your organization</span></span>

- <span data-ttu-id="331f5-141">組織内のすべての発信者番号のポリシー設定を表示するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="331f5-141">To view all of the caller ID policy settings in your organization, run:</span></span>

  ```PowerShell
  Get-CsCallingLineIdentity |fl
  ```
  <span data-ttu-id="331f5-142">[Get-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793856.aspx) のその他の例と詳細について確認してください。</span><span class="sxs-lookup"><span data-stu-id="331f5-142">See more examples and details for [Get-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793856.aspx).</span></span>
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a><span data-ttu-id="331f5-143">組織の新しい発信者番号ポリシーを作成します</span><span class="sxs-lookup"><span data-stu-id="331f5-143">Create a new caller ID policy for your organization</span></span>


- <span data-ttu-id="331f5-144">発信者番号を匿名に設定する発信者番号ポリシーを新たに作成するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="331f5-144">To create a new caller ID policy that sets the caller ID to anonymous, run:</span></span>
    
  ```PowerShell
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```
  > [!NOTE]  
  > <span data-ttu-id="331f5-145">すべての場合において、「サービス番号」フィールドに "+" を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="331f5-145">In all cases, the "Service Number" field should not include an initial "+".</span></span>

  <span data-ttu-id="331f5-146">[New-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793855.aspx) のその他の例と詳細について確認してください。</span><span class="sxs-lookup"><span data-stu-id="331f5-146">See more examples and details for [New-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793855.aspx).</span></span>
    
- <span data-ttu-id="331f5-147">Amos Marble に作成した新しいポリシーを適用するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="331f5-147">To apply the new policy you created to Amos Marble, run:</span></span>
    
  ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  <span data-ttu-id="331f5-148">詳細については、[Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) コマンドレットをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="331f5-148">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet.</span></span>
    
<span data-ttu-id="331f5-149">既にポリシーを作成済みの場合は、 [CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx) コマンドレットを使用して既存のポリシーに変更を加えることができます。次に、 [CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) コマンドレットを使用して、ユーザーに設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="331f5-149">If you have already created a policy, you can use the [Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a><span data-ttu-id="331f5-150">着信する発信者番号を禁止するように設定する</span><span class="sxs-lookup"><span data-stu-id="331f5-150">Set it so the incoming caller ID is blocked</span></span>

- <span data-ttu-id="331f5-151">着信する発信者番号を禁止するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="331f5-151">To block the incoming caller ID, run:</span></span>
    
  ```PowerShell
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  <span data-ttu-id="331f5-152">[Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx) のその他の例と詳細について確認してください。</span><span class="sxs-lookup"><span data-stu-id="331f5-152">See more examples and details for [Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx).</span></span>
    
- <span data-ttu-id="331f5-153">作成したポリシー設定を組織内のユーザーに適用するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="331f5-153">To apply the policy setting you created to a user in your organization, run:</span></span>
    
  ```PowerShell
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```
    <span data-ttu-id="331f5-154">詳細については、[Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) コマンドレットをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="331f5-154">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet.</span></span>
    
### <a name="remove-a-caller-id-policy"></a><span data-ttu-id="331f5-155">発信者番号ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="331f5-155">Remove a caller ID policy</span></span>

<span data-ttu-id="331f5-156">組織からポリシーを削除するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="331f5-156">To remove a policy from your organization, run:</span></span>
  
```PowerShell
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
<span data-ttu-id="331f5-157">ユーザーからポリシーを削除するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="331f5-157">To remove a policy from a user, run:</span></span>
  
```PowerShell
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="331f5-158">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="331f5-158">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="331f5-159">Windows PowerShell では、ユーザーの管理と、許可または許可されていないユーザーの操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="331f5-159">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="331f5-160">Windows PowerShell を使用すると、複数のタスクがある場合に、1つの管理ポイントを使用して、Microsoft 365 または Office 365 と Skype for Business Online を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="331f5-160">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="331f5-161">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="331f5-161">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="331f5-162">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="331f5-162">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="331f5-163">Windows PowerShell を使用して Microsoft 365 または Office 365 を管理する6つの理由</span><span class="sxs-lookup"><span data-stu-id="331f5-163">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="331f5-164">Windows PowerShell には、多くのユーザーについて同時に設定を変更する場合など、Microsoft 365 管理センターを使用する場合にのみ、速度、シンプルさ、生産性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="331f5-164">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="331f5-165">次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="331f5-165">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="331f5-166">Windows PowerShell を使用して Microsoft 365 または Office 365 を管理するのに最適な方法</span><span class="sxs-lookup"><span data-stu-id="331f5-166">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="331f5-167">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="331f5-167">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="331f5-168">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="331f5-168">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
  
 ## <a name="related-topics"></a><span data-ttu-id="331f5-169">関連トピック</span><span class="sxs-lookup"><span data-stu-id="331f5-169">Related topics</span></span>
[<span data-ttu-id="331f5-170">電話番号の移行に関するよくある質問</span><span class="sxs-lookup"><span data-stu-id="331f5-170">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="331f5-171">通話プランで使用されるさまざまな種類の電話番号</span><span class="sxs-lookup"><span data-stu-id="331f5-171">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="331f5-172">組織の電話番号を管理する</span><span class="sxs-lookup"><span data-stu-id="331f5-172">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="331f5-173">発信回線 ID と発信者名の詳細</span><span class="sxs-lookup"><span data-stu-id="331f5-173">More about Calling Line ID and Calling Party Name</span></span>](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[<span data-ttu-id="331f5-174">緊急通話の利用条件</span><span class="sxs-lookup"><span data-stu-id="331f5-174">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="331f5-175">[Skype for Business Online: 緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="331f5-175">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
 
