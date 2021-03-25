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
description: Microsoft 365 および Office 365 の既定の発信者番号 (ユーザーに割り当てられた電話番号) (通話回線 ID とも呼ばれる) について説明します。 ユーザーの発信者番号を変更またはブロックすることができます。
ms.openlocfilehash: 41883e00955cf5f39f4420fb10ead1be2e131a77
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117155"
---
# <a name="set-the-caller-id-for-a-user"></a><span data-ttu-id="b20d8-104">ユーザーに発信者番号を設定する</span><span class="sxs-lookup"><span data-stu-id="b20d8-104">Set the Caller ID for a user</span></span>
<span data-ttu-id="b20d8-105">Microsoft 365 および Office 365 の電話システムは、ユーザーに割り当てられた電話番号である既定の発信者番号を提供します。</span><span class="sxs-lookup"><span data-stu-id="b20d8-105">The Phone System in Microsoft 365 and Office 365 provides a default caller ID that is the user's assigned telephone number.</span></span> <span data-ttu-id="b20d8-106">ユーザーのために発信者番号 (通話回線番号) を変更または禁止することができます。</span><span class="sxs-lookup"><span data-stu-id="b20d8-106">You can either change or block the caller ID (also called a Calling Line ID) for a user.</span></span> <span data-ttu-id="b20d8-107">組織での発信者番号の使用方法の詳細については、[組織内での発信者番号の使用方法](how-can-caller-id-be-used-in-your-organization.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b20d8-107">You can learn more about how to use caller ID in your organization by going [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
> [!TIP]
> <span data-ttu-id="b20d8-108">Skype for Business Online で、着信通話を遮断することは現時点ではできません。</span><span class="sxs-lookup"><span data-stu-id="b20d8-108">You can't block incoming calls currently in Skype for Business Online.</span></span> 
  
<span data-ttu-id="b20d8-109">次の設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="b20d8-109">There are settings that you can change:</span></span>
  
> [!NOTE]
> <span data-ttu-id="b20d8-110">これは、Lync または Skype for Business Server を使用するオンプレミスの組織向け **ではありません**</span><span class="sxs-lookup"><span data-stu-id="b20d8-110">This **is not** for on-premises organizations with Lync or Skype for Business Server.</span></span>
  
- <span data-ttu-id="b20d8-p103">**発信する発信者番号を変更する**: ユーザーの発信者番号は、既定で電話番号になっていますが、別の電話番号に置き換えることができます。たとえば、ユーザーの発信者番号を個人電話番号から会社の代表電話番号に変更したり、ユーザーの通話回線番号を個人電話番号から法務部の代表電話番号に変更したりできます。発信者番号はどのオンライン **サービス** 番号 (有料電話番号または無料電話番号) にでも変更することができます。</span><span class="sxs-lookup"><span data-stu-id="b20d8-p103">**Change their outgoing caller ID** You can replace a user's Caller ID, which by default is their telephone number, with another phone number. For example, you could change the user's Caller ID from their phone number to a main phone number for your business or change the user's Calling Line ID from their phone number to a main phone number for the legal department. You can change the Calling ID number to any Online **service** number (toll or toll-free).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b20d8-114">_Service_ パラメーターを使用する場合は、有効のサービス番号を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b20d8-114">If you want to use the  _Service_ parameter, you must specify a valid service number.</span></span>
  
- <span data-ttu-id="b20d8-p104">**発信する発信者番号を禁止する**: ユーザーの発信する PSTN 通話に発信者番号が送信されるのを禁止することができます。このようにすると、呼び出し中の電話に電話番号が表示されるのを禁止することができます。</span><span class="sxs-lookup"><span data-stu-id="b20d8-p104">**Block their outbound caller ID** You can block the outgoing Caller ID from being sent on a user's outgoing PSTN calls. Doing this will block their phone number from being displayed on the phone of a person being called.</span></span>
    
- <span data-ttu-id="b20d8-117">**着信する発信者番号を禁止する**: あらゆる着信 PSTN 通話でユーザーが発信者番号を受信できないようにします。</span><span class="sxs-lookup"><span data-stu-id="b20d8-117">**Block their incoming caller ID** You can block a user from receiving Caller ID on any incoming PSTN calls.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="b20d8-118">緊急通話では、ユーザーの電話番号 (発信者番号) が常に送信されます。</span><span class="sxs-lookup"><span data-stu-id="b20d8-118">Emergency calls will always send the user's telephone number (caller ID).</span></span> 
  
<span data-ttu-id="b20d8-p105">既定では、これらのすべての発信者番号設定が **オフ** になっています。このため、Skype for Business Online のユーザーが PSTN 電話に通話を発信すると、そのユーザーの電話番号は相手に表示されることになります。</span><span class="sxs-lookup"><span data-stu-id="b20d8-p105">By default, all of these caller ID settings are **turned off**. This means that the Skype for Business Online user's phone number can be seen when that user makes a call to a PSTN phone.</span></span>
  
<span data-ttu-id="b20d8-121">これらの設定と使用方法の詳細については、[組織内での発信者番号の使用方法](how-can-caller-id-be-used-in-your-organization.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b20d8-121">To learn more about these settings and how you can use them, go [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
## <a name="set-your-caller-id-policy-settings"></a><span data-ttu-id="b20d8-122">発信者番号ポリシー設定を設定する</span><span class="sxs-lookup"><span data-stu-id="b20d8-122">Set your caller ID policy settings</span></span>

> [!NOTE]
> <span data-ttu-id="b20d8-123">Skype for Business Online のすべての発信者番号設定では、Windows PowerShell を使用する必要があります。 **Skype for Business 管理センター** を **使用することはできません**。</span><span class="sxs-lookup"><span data-stu-id="b20d8-123">For all of the Caller ID settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="start-powershell"></a><span data-ttu-id="b20d8-124">PowerShell を起動する</span><span class="sxs-lookup"><span data-stu-id="b20d8-124">Start PowerShell</span></span>

- <span data-ttu-id="b20d8-125">コマンド プロンプトWindows PowerShellし、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b20d8-125">Open a Windows PowerShell command prompt and run the following commands:</span></span>

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a><span data-ttu-id="b20d8-126">組織内のすべての発信者番号のポリシー設定を表示する</span><span class="sxs-lookup"><span data-stu-id="b20d8-126">See all of the caller ID policy settings in your organization</span></span>

- <span data-ttu-id="b20d8-127">組織内のすべての発信者番号のポリシー設定を表示するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="b20d8-127">To view all of the caller ID policy settings in your organization, run:</span></span>

  ```PowerShell
  Get-CsCallingLineIdentity |fl
  ```
  <span data-ttu-id="b20d8-128">[Get-CsCallingLineIdentity](/powershell/module/skype/Get-CsCallingLineIdentity) のその他の例と詳細について確認してください。</span><span class="sxs-lookup"><span data-stu-id="b20d8-128">See more examples and details for [Get-CsCallingLineIdentity](/powershell/module/skype/Get-CsCallingLineIdentity).</span></span>
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a><span data-ttu-id="b20d8-129">組織の新しい発信者番号ポリシーを作成します</span><span class="sxs-lookup"><span data-stu-id="b20d8-129">Create a new caller ID policy for your organization</span></span>


- <span data-ttu-id="b20d8-130">発信者番号を匿名に設定する発信者番号ポリシーを新たに作成するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="b20d8-130">To create a new caller ID policy that sets the caller ID to anonymous, run:</span></span>
    
  ```PowerShell
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```
  > [!NOTE]  
  > <span data-ttu-id="b20d8-131">すべての場合において、「サービス番号」フィールドに "+" を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="b20d8-131">In all cases, the "Service Number" field should not include an initial "+".</span></span>

  <span data-ttu-id="b20d8-132">[New-CsCallingLineIdentity](/powershell/module/skype/New-CsCallingLineIdentity) のその他の例と詳細について確認してください。</span><span class="sxs-lookup"><span data-stu-id="b20d8-132">See more examples and details for [New-CsCallingLineIdentity](/powershell/module/skype/New-CsCallingLineIdentity).</span></span>
    
- <span data-ttu-id="b20d8-133">Amos Marble に作成した新しいポリシーを適用するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="b20d8-133">To apply the new policy you created to Amos Marble, run:</span></span>
    
  ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  <span data-ttu-id="b20d8-134">詳細については、[Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) コマンドレットをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b20d8-134">See more on the [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) cmdlet.</span></span>
    
<span data-ttu-id="b20d8-135">既にポリシーを作成している場合は [、Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity) コマンドレットを使用して既存のポリシーを変更し [、Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) コマンドレットを使用して設定をユーザーに適用できます。</span><span class="sxs-lookup"><span data-stu-id="b20d8-135">If you have already created a policy, you can use the [Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity) cmdlet to make changes to the existing policy, and then use the [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) cmdlet to apply the settings to your users.</span></span>
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a><span data-ttu-id="b20d8-136">着信する発信者番号を禁止するように設定する</span><span class="sxs-lookup"><span data-stu-id="b20d8-136">Set it so the incoming caller ID is blocked</span></span>

- <span data-ttu-id="b20d8-137">着信する発信者番号を禁止するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="b20d8-137">To block the incoming caller ID, run:</span></span>
    
  ```PowerShell
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  <span data-ttu-id="b20d8-138">[Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity) のその他の例と詳細について確認してください。</span><span class="sxs-lookup"><span data-stu-id="b20d8-138">See more examples and details for [Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity).</span></span>
    
- <span data-ttu-id="b20d8-139">作成したポリシー設定を組織内のユーザーに適用するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="b20d8-139">To apply the policy setting you created to a user in your organization, run:</span></span>
    
  ```PowerShell
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```
    <span data-ttu-id="b20d8-140">詳細については、[Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) コマンドレットをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b20d8-140">See more on the [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) cmdlet.</span></span>
    
### <a name="remove-a-caller-id-policy"></a><span data-ttu-id="b20d8-141">発信者番号ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="b20d8-141">Remove a caller ID policy</span></span>

<span data-ttu-id="b20d8-142">組織からポリシーを削除するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="b20d8-142">To remove a policy from your organization, run:</span></span>
  
```PowerShell
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
<span data-ttu-id="b20d8-143">ユーザーからポリシーを削除するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="b20d8-143">To remove a policy from a user, run:</span></span>
  
```PowerShell
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="b20d8-144">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="b20d8-144">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="b20d8-145">Windows PowerShellは、ユーザーの管理と、ユーザーに許可する操作と許可しない操作の管理に使います。</span><span class="sxs-lookup"><span data-stu-id="b20d8-145">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="b20d8-146">Windows PowerShell を使用すると、単一の管理ポイントを使用して Microsoft 365 または Office 365 と Skype for Business Online を管理できます。複数のタスクを実行する必要がある場合に毎日の作業を簡略化できます。</span><span class="sxs-lookup"><span data-stu-id="b20d8-146">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="b20d8-147">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b20d8-147">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="b20d8-148">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="b20d8-148">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [<span data-ttu-id="b20d8-149">Microsoft 365 または Windows PowerShell 365 の管理に使用する 6 Office理由</span><span class="sxs-lookup"><span data-stu-id="b20d8-149">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="b20d8-150">Windows PowerShellは、多くのユーザーに対して同時に設定変更を行う場合など、Microsoft 365 管理センターを使用する場合に限って、速度、シンプルさ、生産性の点で多くの利点があります。</span><span class="sxs-lookup"><span data-stu-id="b20d8-150">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="b20d8-151">次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="b20d8-151">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="b20d8-152">[Microsoft 365 または Office 365 を他のユーザーとWindows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="b20d8-152">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="b20d8-153">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="b20d8-153">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [<span data-ttu-id="b20d8-154">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="b20d8-154">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  
 ## <a name="related-topics"></a><span data-ttu-id="b20d8-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="b20d8-155">Related topics</span></span>
[<span data-ttu-id="b20d8-156">電話番号の移行に関するよくある質問</span><span class="sxs-lookup"><span data-stu-id="b20d8-156">Transferring phone numbers common questions</span></span>](./phone-number-calling-plans/port-order-overview.md)

[<span data-ttu-id="b20d8-157">通話プランで使用されるさまざまな種類の電話番号</span><span class="sxs-lookup"><span data-stu-id="b20d8-157">Different kinds of phone numbers used for Calling Plans</span></span>](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="b20d8-158">組織の電話番号を管理する</span><span class="sxs-lookup"><span data-stu-id="b20d8-158">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="b20d8-159">発信回線 ID と発信者名の詳細</span><span class="sxs-lookup"><span data-stu-id="b20d8-159">More about Calling Line ID and Calling Party Name</span></span>](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[<span data-ttu-id="b20d8-160">緊急通話の利用条件</span><span class="sxs-lookup"><span data-stu-id="b20d8-160">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)

<span data-ttu-id="b20d8-161">[Skype for Business Online: 緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="b20d8-161">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
