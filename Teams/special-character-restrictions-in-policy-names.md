---
title: Teams のポリシーでの特殊文字の制限について
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords:
- ms.teamsadmincenter.policies.naming.error
description: ポリシー名に特殊文字が含まれている問題と、その問題を修正する際の対処方法を確認します。
ms.openlocfilehash: a3e7bccc78641a07b7e2f2b02e12b6fe501f2405
ms.sourcegitcommit: 1de5e4d829405b75c0a87918cc7c8fa7227e0ad6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "40952760"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a><span data-ttu-id="a76e1-103">Teams のポリシーでの特殊文字の制限について</span><span class="sxs-lookup"><span data-stu-id="a76e1-103">What are the special character restrictions in Teams policies?</span></span>

<span data-ttu-id="a76e1-104">**Microsoft Teams 管理センターにある名前に特殊文字が含まれている（メッセージングや会議などの）ポリシーは、作成または編集できません**。</span><span class="sxs-lookup"><span data-stu-id="a76e1-104">**You can't create or edit policies (for messaging, meetings, etc.) that have a special character in the name in the Microsoft Teams admin center**.</span></span> 

<span data-ttu-id="a76e1-105">ポリシー名に特殊文字が含まれている場合、Microsoft Teams 管理センターでの該当のポリシーの管理は制限されます。</span><span class="sxs-lookup"><span data-stu-id="a76e1-105">If a policy name contains special characters, you will be limited in managing these policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="a76e1-106">**したがって、ポリシー名に特殊文字を入れないことを強くお勧めします**。</span><span class="sxs-lookup"><span data-stu-id="a76e1-106">**As such, we strongly recommend that policy names don't include special characters**.</span></span> 

<span data-ttu-id="a76e1-107">PowerShell を使用して Teams での会議とメッセージング用に作成されたポリシー名には、@、#、$ などの特殊文字を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="a76e1-107">Policy names that have been created using PowerShell for meetings and messaging in Teams can have special characters such as @,#,$.</span></span> <span data-ttu-id="a76e1-108">ただし、Microsoft Teams 管理センターでポリシーに変更を加える場合は、特殊文字を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="a76e1-108">However, if you are wanting to make changes to the policy in the Microsoft Teams admin center,you won't be able to.</span></span> 

<span data-ttu-id="a76e1-109">特殊文字が含まれているポリシーがある場合は、Windows PowerShell (永続版) を使用してポリシーを編集するか、または以前のポリシーと同じ設定で Microsoft Teams 管理センターで新しいポリシーを作成し、同じグループのユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a76e1-109">If you have a policy with special characters, you will need to either edit the policy using Windows PowerShell (forever) or create a new policy in the Microsoft Teams admin center with the same settings as the old policy and assign it to the same group of users.</span></span>

## <a name="to-remove-special-characters"></a><span data-ttu-id="a76e1-110">特殊文字を削除するには</span><span class="sxs-lookup"><span data-stu-id="a76e1-110">To remove special characters</span></span>

<span data-ttu-id="a76e1-111">**手順 1 - PowerShell でリモート接続を確立します。**
まだインストールしていない場合は、[Windows PowerShell 用にお使いのコンピューターを設定します。](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="a76e1-111">**Step 1 - Make a remote connection with PowerShell.**
[Set up your computer for Windows PowerShell](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) if you haven't yet.</span></span>
```PowerShell
 Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
 $credential = Get-Credential
 $session = New-CsOnlineSession -Credential $credential
 Import-PSSession $session
```


<span data-ttu-id="a76e1-112">**手順 2 - 以前のポリシーの設定を取得し、出力をキャプチャします。**</span><span class="sxs-lookup"><span data-stu-id="a76e1-112">**Step 2 - Get the settings for the old policy and capture the output.**</span></span>

> [!NOTE]
> <span data-ttu-id="a76e1-113">この例は、[メッセージング](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) ポリシー向けです。</span><span class="sxs-lookup"><span data-stu-id="a76e1-113">This example is for a [Messaging](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) policy.</span></span>  <span data-ttu-id="a76e1-114">他のポリシーの種類でも同じ手順になりますが、適切なコマンドレットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a76e1-114">The steps would be the same for other policy types but you must use the correct cmdlet.</span></span> 

  ```PowerShell
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


<span data-ttu-id="a76e1-115">**手順 3 - 新しいポリシーを作成します。**</span><span class="sxs-lookup"><span data-stu-id="a76e1-115">**Step 3 - Create a new policy.**</span></span>

<span data-ttu-id="a76e1-116">Microsoft Teams 管理センターまたは PowerShell を使用して同じ設定で、新しいポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="a76e1-116">You can either create the new policy with the same setting by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="a76e1-117">これを実行すると、新しいポリシーが作成されますが、[Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) を確認し、次の手順を実行して、正しい設定を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a76e1-117">Running this will create a new policy for you but you will need to add the correct settings by seeing [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) and then running it:</span></span>

  ```PowerShell
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
<span data-ttu-id="a76e1-118">**手順 4 - ポリシーを割り当てます。**</span><span class="sxs-lookup"><span data-stu-id="a76e1-118">**Step 4 - Assign the policy.**</span></span>
 ```PowerShell
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
<span data-ttu-id="a76e1-119">このコマンドレットの詳細については、[Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a76e1-119">See, [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="a76e1-120">**手順 5 - 以前のポリシーを削除します。**</span><span class="sxs-lookup"><span data-stu-id="a76e1-120">**Step 5 - Delete the old policy.**</span></span>

<span data-ttu-id="a76e1-121">これにより、特殊文字を含む以前のポリシーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="a76e1-121">This will delete the old policy with the special characters.</span></span>
  ```PowerShell
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
<span data-ttu-id="a76e1-122">このコマンドレットの詳細については、[Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a76e1-122">See, [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="a76e1-123">このコマンドが成功した場合は完了です。</span><span class="sxs-lookup"><span data-stu-id="a76e1-123">If this command succeeds, you're done.</span></span> <span data-ttu-id="a76e1-124">上記のコマンドがエラーを返す場合、ユーザーに以前のポリシーが割り当てられているため、ポリシーから割り当てられているすべてのユーザーを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a76e1-124">If the above command returns an error, it is because the old policy is assigned to users so you need to run to remove all assigned users from the policy:</span></span>

```PowerShell
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="a76e1-125">Windows PowerShell での管理方法について</span><span class="sxs-lookup"><span data-stu-id="a76e1-125">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="a76e1-p105">Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a76e1-p105">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="a76e1-129">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="a76e1-129">Why you need to use Office 365 PowerShell?</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="a76e1-130">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="a76e1-130">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="a76e1-p106">Windows PowerShell には、Microsoft 365 管理センターを使用する場合にのみ、速度、簡素化、生産性を高めるためのさまざまな利点があります。たとえば、多くのユーザーの設定を一度に変更する場合です。次のトピックで、これらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="a76e1-p106">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="a76e1-133">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="a76e1-133">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="a76e1-134">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="a76e1-134">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="a76e1-135">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="a76e1-135">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="a76e1-136">Skype for Business Online 用 Windows PowerShell モジュールでは、リモート Windows PowerShell セッションを作成して Skype for Business Online と Microsoft Teams に接続できます。</span><span class="sxs-lookup"><span data-stu-id="a76e1-136">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online and Microsoft Teams.</span></span> <span data-ttu-id="a76e1-137">このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「[Skype for Business Online 用 Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)」からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="a76e1-137">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  

