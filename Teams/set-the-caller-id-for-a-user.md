---
title: ユーザーに発信者番号を設定する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: jens, roykuntz
ms.topic: article
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business Online
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: 通話回線 ID Microsoft 365既定Office 365 (ユーザーに割り当てられた電話番号) の呼び出し元 ID と呼ばれる番号について学習します。 ユーザーの発信者番号を変更またはブロックできます。
ms.openlocfilehash: 20b80bbc96f46d6b1a2766eea367132b9e0b1418
ms.sourcegitcommit: b39bd1de0219a9e3a3b0c97fc485c9578ddb643c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2021
ms.locfileid: "53230604"
---
# <a name="set-the-caller-id-for-a-user"></a><span data-ttu-id="1d92a-104">ユーザーに発信者番号を設定する</span><span class="sxs-lookup"><span data-stu-id="1d92a-104">Set the Caller ID for a user</span></span>

<span data-ttu-id="1d92a-105">電話システムではMicrosoft 365、ユーザーに割り当てられた電話番号である既定の発信者番号が提供されます。</span><span class="sxs-lookup"><span data-stu-id="1d92a-105">Phone System in Microsoft 365 provides a default caller ID that is the user's assigned telephone number.</span></span> <span data-ttu-id="1d92a-106">ユーザーのために発信者番号 (通話回線番号) を変更または禁止することができます。</span><span class="sxs-lookup"><span data-stu-id="1d92a-106">You can either change or block the caller ID (also called a Calling Line ID) for a user.</span></span> <span data-ttu-id="1d92a-107">組織での発信者番号の使用方法の詳細については、[組織内での発信者番号の使用方法](how-can-caller-id-be-used-in-your-organization.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1d92a-107">You can learn more about how to use caller ID in your organization by going [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
<span data-ttu-id="1d92a-108">既定では、次の発信者番号の設定は **オフになっています**。</span><span class="sxs-lookup"><span data-stu-id="1d92a-108">By default, the following caller ID settings are **turned off**.</span></span> <span data-ttu-id="1d92a-109">つまり、ユーザー Teams PSTN 電話に通話を発信すると、そのユーザーの電話番号が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1d92a-109">This means that the Teams user's phone number can be seen when that user makes a call to a PSTN phone.</span></span> <span data-ttu-id="1d92a-110">これらの設定は次のように変更できます。</span><span class="sxs-lookup"><span data-stu-id="1d92a-110">You can change these settings as follows:</span></span>
  
- <span data-ttu-id="1d92a-111">**発信元 ID** ユーザーの発信者番号 (既定では電話番号) を別の電話番号に置き換え可能です。</span><span class="sxs-lookup"><span data-stu-id="1d92a-111">**Outgoing caller ID** You can replace a user's Caller ID, which by default is their telephone number, with another phone number.</span></span> <span data-ttu-id="1d92a-112">たとえば、ユーザーの発信者番号を個人電話番号から会社の代表電話番号に変更したり、ユーザーの通話回線番号を個人電話番号から法務部の代表電話番号に変更したりできます。</span><span class="sxs-lookup"><span data-stu-id="1d92a-112">For example, you could change the user's Caller ID from their phone number to a main phone number for your business or change the user's Calling Line ID from their phone number to a main phone number for the legal department.</span></span> <span data-ttu-id="1d92a-113">通話 ID 番号は、任意のオンライン サービス番号 (有料または無料) に変更できます。</span><span class="sxs-lookup"><span data-stu-id="1d92a-113">You can change the Calling ID number to any online service number (toll or toll-free).</span></span> <span data-ttu-id="1d92a-114">また、通話 ID 番号をオンプレミスの電話番号に変更するには、自動応答 または通話キューで使用されるリソース アカウントに割り当てられている直接ルーティングを使用します。</span><span class="sxs-lookup"><span data-stu-id="1d92a-114">You can also change the Calling ID number to an on-premises phone number through Direct Routing that is assigned to a resource account used by an Auto Attendant or Call Queue.</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="1d92a-115">Service パラメーターを *使用する場合* は、有効なサービス番号を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d92a-115">If you want to use the *Service* parameter, you must specify a valid service number.</span></span>
  > <span data-ttu-id="1d92a-116">ドロップダウンに表示されない場合は、リソース アカウント番号に PowerShell コマンドレットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d92a-116">You need to use the PowerShell cmdlets for Resource account number if not visible in drop down.</span></span>
  
- <span data-ttu-id="1d92a-117">**発信呼び出し元 ID をブロックします。**</span><span class="sxs-lookup"><span data-stu-id="1d92a-117">**Block outbound caller ID.**</span></span> <span data-ttu-id="1d92a-118">発信発信者 ID がユーザーの発信 PSTN 通話で送信されるのをブロックできます。</span><span class="sxs-lookup"><span data-stu-id="1d92a-118">You can block the outgoing Caller ID from being sent on a user's outgoing PSTN calls.</span></span> <span data-ttu-id="1d92a-119">このようにすると、呼び出し中の電話に電話番号が表示されるのを禁止することができます。</span><span class="sxs-lookup"><span data-stu-id="1d92a-119">Doing this will block their phone number from being displayed on the phone of a person being called.</span></span>
    
- <span data-ttu-id="1d92a-120">**着信呼び出し元 ID をブロックします。**</span><span class="sxs-lookup"><span data-stu-id="1d92a-120">**Block incoming caller ID.**</span></span> <span data-ttu-id="1d92a-121">ユーザーが着信 PSTN 通話で発信者番号を受け取るのをブロックできます。</span><span class="sxs-lookup"><span data-stu-id="1d92a-121">You can block a user from receiving Caller ID on any incoming PSTN calls.</span></span>

- <span data-ttu-id="1d92a-122">**[通話者名 (CNAM) を設定します。**</span><span class="sxs-lookup"><span data-stu-id="1d92a-122">**Set Calling Party Name (CNAM).**</span></span> <span data-ttu-id="1d92a-123">ユーザーはMicrosoft Teams PSTN 通話で CNAM を送信できます。</span><span class="sxs-lookup"><span data-stu-id="1d92a-123">For your Microsoft Teams users you can send a CNAM on outbound PSTN calls.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="1d92a-124">緊急通話では、ユーザーの電話番号 (発信者番号) が常に送信されます。</span><span class="sxs-lookup"><span data-stu-id="1d92a-124">Emergency calls will always send the user's telephone number (caller ID).</span></span> 
  

  
<span data-ttu-id="1d92a-125">これらの設定とそれらの使い方の詳細については、「組織で発信者番号を使用する方法」 [を参照してください](how-can-caller-id-be-used-in-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="1d92a-125">To learn more about these settings and how you can use them, see [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
## <a name="set-your-caller-id-policy-settings"></a><span data-ttu-id="1d92a-126">発信者番号ポリシー設定を設定する</span><span class="sxs-lookup"><span data-stu-id="1d92a-126">Set your caller ID policy settings</span></span>

> [!NOTE]
> <span data-ttu-id="1d92a-127">呼び出し元 ID をリソース アカウントの電話番号に設定し、発信者名を設定するには、Teams PowerShell モジュール 2.3.1 以降の PowerShell コマンドレット New-CsCallingLineIdentity または Set-CsCallingLineIdentity を使用します。</span><span class="sxs-lookup"><span data-stu-id="1d92a-127">To set the caller ID to a resource account phone number and to set the calling party name, use the PowerShell cmdlets New-CsCallingLineIdentity or Set-CsCallingLineIdentity in the Teams PowerShell module 2.3.1 or later.</span></span> <span data-ttu-id="1d92a-128">(これらのオプションは現在、管理センター Microsoft Teams使用できません)。</span><span class="sxs-lookup"><span data-stu-id="1d92a-128">(These options are not currently available in the Microsoft Teams admin center.)</span></span> 

<span data-ttu-id="1d92a-129">コマンド プロンプトWindows PowerShellし、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1d92a-129">Open a Windows PowerShell command prompt and run the following commands:</span></span>

```PowerShell
# When using Teams PowerShell Module

Import-Module MicrosoftTeams
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
``` 

### <a name="view-create-and-apply-policy-settings"></a><span data-ttu-id="1d92a-130">ポリシー設定を表示、作成、適用する</span><span class="sxs-lookup"><span data-stu-id="1d92a-130">View, create, and apply policy settings</span></span>

1. <span data-ttu-id="1d92a-131">組織内のすべての発信者番号のポリシー設定を表示するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="1d92a-131">To view all of the caller ID policy settings in your organization, run:</span></span>

     ```PowerShell
     Get-CsCallingLineIdentity |fl
     ```
   <span data-ttu-id="1d92a-132">詳細については [、Get-CsCallingLineIdentity に関するページを参照してください](/powershell/module/skype/Get-CsCallingLineIdentity)。</span><span class="sxs-lookup"><span data-stu-id="1d92a-132">For more information, see [Get-CsCallingLineIdentity](/powershell/module/skype/Get-CsCallingLineIdentity).</span></span>
    
2. <span data-ttu-id="1d92a-133">組織の新しい発信者番号ポリシーを作成するには、次のコマンドレットNew-CsCallingIdentityします。</span><span class="sxs-lookup"><span data-stu-id="1d92a-133">To create a new caller ID policy for your organization, use the New-CsCallingIdentity cmdlet:</span></span>
    
     ```PowerShell
     New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
     ```
    <span data-ttu-id="1d92a-134">すべての場合において、「サービス番号」フィールドに "+" を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="1d92a-134">In all cases, the "Service Number" field should not include an initial "+".</span></span>

   <span data-ttu-id="1d92a-135">詳細については [、New-CsCallingLineIdentity に関するページを参照してください](/powershell/module/skype/New-CsCallingLineIdentity)。</span><span class="sxs-lookup"><span data-stu-id="1d92a-135">For more information, see [New-CsCallingLineIdentity](/powershell/module/skype/New-CsCallingLineIdentity).</span></span>
    
3. <span data-ttu-id="1d92a-136">次のコマンドレットを使用して作成した新しいポリシーGrant-CsCallingIdentityします。</span><span class="sxs-lookup"><span data-stu-id="1d92a-136">Apply the new policy you created by using the Grant-CsCallingIdentity cmdlet.</span></span> <span data-ttu-id="1d92a-137">たとえば、次の例では、ユーザー Amos Marble に新しいポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="1d92a-137">For example, the following example applies the new policy to user Amos Marble.</span></span>
    
     ```PowerShell
      Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
     ```
   <span data-ttu-id="1d92a-138">詳細については [、「Grant-CsCallingLineIdentity コマンドレット」を参照](/powershell/module/skype/Grant-CsCallingLineIdentity) してください。</span><span class="sxs-lookup"><span data-stu-id="1d92a-138">For more information, see [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) cmdlet.</span></span>
    

4. <span data-ttu-id="1d92a-139">着信呼び出し元 ID をブロックする場合は、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="1d92a-139">If you want to block the incoming caller ID, run:</span></span>
    
   ```PowerShell
   Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true
   ``` 

   <span data-ttu-id="1d92a-140">詳細については [、Set-CsCallingLineIdentity に関するページを参照してください](/powershell/module/skype/Set-CsCallingLineIdentity)。</span><span class="sxs-lookup"><span data-stu-id="1d92a-140">For more information, see [Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity).</span></span>
    
5. <span data-ttu-id="1d92a-141">作成したポリシー設定を組織内のユーザーに適用するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="1d92a-141">To apply the policy setting you created to a user in your organization, run:</span></span>
    
   ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
   ```
   <span data-ttu-id="1d92a-142">詳細については [、Grant-CsCallingLineIdentity に関するページを参照してください](/powershell/module/skype/Grant-CsCallingLineIdentity)。</span><span class="sxs-lookup"><span data-stu-id="1d92a-142">For more information, see [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity).</span></span>

6. <span data-ttu-id="1d92a-143">新しい発信者番号ポリシーを作成するには、発信者番号を指定されたリソース アカウントの電話番号に設定し、発信者名を Contoso に設定します。</span><span class="sxs-lookup"><span data-stu-id="1d92a-143">To create a new Caller ID policy that sets the Caller ID to the phone number of the specified resource account and sets the Calling party name to Contoso:</span></span>

   ```PowerShell
   $ObjId = (Get-CsOnlineApplicationInstance -Identity dkcq@contoso.com).ObjectId
   New-CsCallingLineIdentity  -Identity DKCQ -CallingIDSubstitute Resource -EnableUserOverride $false -ResourceAccount $ObjId -CompanyName "Contoso"
   ```

<span data-ttu-id="1d92a-144">既にポリシーを作成している場合は [、Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity) コマンドレットを使用して既存のポリシーを変更し [、Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) コマンドレットを使用して設定をユーザーに適用できます。</span><span class="sxs-lookup"><span data-stu-id="1d92a-144">If you have already created a policy, you can use the [Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity) cmdlet to make changes to the existing policy, and then use the [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) cmdlet to apply the settings to your users.</span></span>
    
### <a name="remove-a-policy-setting"></a><span data-ttu-id="1d92a-145">ポリシー設定を削除する</span><span class="sxs-lookup"><span data-stu-id="1d92a-145">Remove a policy setting</span></span>

<span data-ttu-id="1d92a-146">組織からポリシーを削除するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="1d92a-146">To remove a policy from your organization, run:</span></span>
  
```PowerShell
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
<span data-ttu-id="1d92a-147">ユーザーからポリシーを削除するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="1d92a-147">To remove a policy from a user, run:</span></span>
  
```PowerShell
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="1d92a-148">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="1d92a-148">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="1d92a-149">Windows PowerShellは、ユーザーの管理と、ユーザーが許可または許可されていない操作についてすべて行います。</span><span class="sxs-lookup"><span data-stu-id="1d92a-149">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="1d92a-150">このWindows PowerShell、1 つの管理Microsoft 365を使用して管理し、毎日の作業を簡略化できます。</span><span class="sxs-lookup"><span data-stu-id="1d92a-150">With Windows PowerShell, you can manage Microsoft 365 using a single point of administration that can simplify your daily work.</span></span> <span data-ttu-id="1d92a-151">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d92a-151">To get started with Windows PowerShell, see these topics:</span></span>
    
- [<span data-ttu-id="1d92a-152">Windows PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="1d92a-152">An introduction to Windows PowerShell</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
- [<span data-ttu-id="1d92a-153">アプリを使用して管理する 6 Windows PowerShell理由Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1d92a-153">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="1d92a-154">Windows PowerShell多くのユーザーに対して一度に設定を変更する場合など、Microsoft 365 管理センター の使用に対する速度、シンプルさ、生産性に多くの利点があります。</span><span class="sxs-lookup"><span data-stu-id="1d92a-154">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="1d92a-155">次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="1d92a-155">Learn about these advantages in the following topics:</span></span>
    
- <span data-ttu-id="1d92a-156">[アプリを使用してMicrosoft 365を管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="1d92a-156">[Best ways to manage Microsoft 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- [<span data-ttu-id="1d92a-157">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="1d92a-157">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
- [<span data-ttu-id="1d92a-158">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="1d92a-158">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  
 ## <a name="related-topics"></a><span data-ttu-id="1d92a-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="1d92a-159">Related topics</span></span>
[<span data-ttu-id="1d92a-160">電話番号の移行に関するよくある質問</span><span class="sxs-lookup"><span data-stu-id="1d92a-160">Transferring phone numbers common questions</span></span>](./phone-number-calling-plans/port-order-overview.md)

[<span data-ttu-id="1d92a-161">通話プランで使用されるさまざまな種類の電話番号</span><span class="sxs-lookup"><span data-stu-id="1d92a-161">Different kinds of phone numbers used for Calling Plans</span></span>](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="1d92a-162">組織の電話番号を管理する</span><span class="sxs-lookup"><span data-stu-id="1d92a-162">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="1d92a-163">発信回線 ID と発信者名の詳細</span><span class="sxs-lookup"><span data-stu-id="1d92a-163">More about Calling Line ID and Calling Party Name</span></span>](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[<span data-ttu-id="1d92a-164">緊急通話の利用条件</span><span class="sxs-lookup"><span data-stu-id="1d92a-164">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)

<span data-ttu-id="1d92a-165">[Skype for Business Online: 緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="1d92a-165">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
