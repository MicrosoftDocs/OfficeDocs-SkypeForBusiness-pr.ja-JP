---
title: チーム ポリシー内の特殊文字の制限は?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service:
- msteams
- skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Teams_ITAdmin_Help
search.appverid: MET150
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords:
- ms.teamsadmincenter.policies.naming.error
description: ポリシーおよびその修正を行うことができますの名前に特殊文字を含むが、どのような問題を参照してください。
ms.openlocfilehash: e1d46f70b42b96b2f3811c97d0110946fd013cd7
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "25017504"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a><span data-ttu-id="3c66e-103">チーム ポリシー内の特殊文字の制限は?</span><span class="sxs-lookup"><span data-stu-id="3c66e-103">What are the special character restrictions in Teams policies?</span></span>

<span data-ttu-id="3c66e-104">**ビジネス管理センターは、マイクロソフトのチームと Skype で名前に特殊文字がある (メッセージ、会議など) 用のポリシーを編集または作成できません。**</span><span class="sxs-lookup"><span data-stu-id="3c66e-104">**You can't create or edit policies (for messaging, meetings, etc.) that have a special character in the name in the Microsoft Teams and Skype for Business Admin Center.**</span></span> 

<span data-ttu-id="3c66e-105">ポリシー名に特殊文字が含まれている場合は、マイクロソフトのチームとビジネス管理センターの Skype でこれらのポリシーを管理するうえで制限されます。</span><span class="sxs-lookup"><span data-stu-id="3c66e-105">If a policy name contains special characters, you will be limited in managing these policies in the Microsoft Teams and Skype for Business Admin Center.</span></span> <span data-ttu-id="3c66e-106">**よう、強くお勧めポリシー名に特殊文字を含めない**。</span><span class="sxs-lookup"><span data-stu-id="3c66e-106">**As such, we strongly recommend that policy names don't include special characters**.</span></span> 

<span data-ttu-id="3c66e-107">会議、メッセージング チームには特殊文字など、PowerShell を使用して作成されているポリシー名 @、#、$。</span><span class="sxs-lookup"><span data-stu-id="3c66e-107">Policy names that have been created using PowerShell for meetings and messaging in Teams can have special characters such as @,#,$.</span></span> <span data-ttu-id="3c66e-108">ただし場合は、マイクロソフトのチームと Skype のビジネス管理センターでポリシーを変更するためのお問い合わせは、することはできませんにします。</span><span class="sxs-lookup"><span data-stu-id="3c66e-108">However, if you are wanting to make changes to the policy in the Microsoft Teams and Skype for Business Admin Center,you won't be able to.</span></span> 

<span data-ttu-id="3c66e-109">特殊文字を含むポリシーがあれば、(無限) に Windows PowerShell を使用して、ポリシーを編集するか、または古いポリシーと同じ設定で、マイクロソフトのチームとビジネス管理センターの Skype の新しいポリシーを作成し、同じグループに割り当てることする必要があります。ユーザーの p です。</span><span class="sxs-lookup"><span data-stu-id="3c66e-109">If you have a policy with special characters, you will need to either edit the policy using Windows PowerShell (forever) or create a new policy in the Microsoft Teams and Skype for Business Admin Center with the same settings as the old policy and assign it to the same group of users.</span></span>

## <a name="to-remove-special-characters"></a><span data-ttu-id="3c66e-110">特殊文字を削除するのには</span><span class="sxs-lookup"><span data-stu-id="3c66e-110">To remove special characters</span></span>



<span data-ttu-id="3c66e-111">**手順 1 - PowerShell でリモート接続を確立します**。
まだしていない場合は、 [Windows PowerShell には、コンピューターの設定](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)をします。</span><span class="sxs-lookup"><span data-stu-id="3c66e-111">**Step 1 - Make a remote connection with PowerShell.**
[Set up your computer for Windows PowerShell](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) if you haven't yet.</span></span>
```
 Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
 $credential = Get-Credential
 $session = New-CsOnlineSession -Credential $credential
 Import-PSSession $session
```


<span data-ttu-id="3c66e-112">**手順 2 - 以前のポリシーの設定を取得し、出力をキャプチャします。**</span><span class="sxs-lookup"><span data-stu-id="3c66e-112">**Step 2 - Get the settings for the old policy and capture the output.**</span></span>

> [!NOTE]
> <span data-ttu-id="3c66e-113">この例では、[メッセージング](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps)ポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="3c66e-113">This example is for a [Messaging](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) policy.</span></span>  <span data-ttu-id="3c66e-114">その他のポリシーの種類の同じ手順になりますが、適切なコマンドレットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c66e-114">The steps would be the same for other policy types but you must use the correct cmdlet.</span></span> 

  ```
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


<span data-ttu-id="3c66e-115">**手順 3: 新しいポリシーを作成します。**</span><span class="sxs-lookup"><span data-stu-id="3c66e-115">**Step 3 - Create a new policy.**</span></span>

<span data-ttu-id="3c66e-116">ビジネス管理センターまたは PowerShell のマイクロソフトのチームと Skype を使用して同じ設定で新しいポリシーを作成できますか。</span><span class="sxs-lookup"><span data-stu-id="3c66e-116">You can either create the new policy with the same setting using the Microsoft Teams and Skype for Business Admin Center or PowerShell.</span></span>

<span data-ttu-id="3c66e-117">新しいポリシーを作成、これを実行しているが、[セット CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)を表示し、後に実行する適切な設定を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c66e-117">Running this will create a new policy for you but you will need to add the correct settings by seeing [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) and then running it:</span></span>

  ```
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
<span data-ttu-id="3c66e-118">**ステップ 4: ポリシーを割り当てます。**</span><span class="sxs-lookup"><span data-stu-id="3c66e-118">**Step 4 - Assign the policy.**</span></span>
 ```
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
<span data-ttu-id="3c66e-119">参照してください、このコマンドレットの詳細については[Grant CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) 。</span><span class="sxs-lookup"><span data-stu-id="3c66e-119">See, [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="3c66e-120">**手順 5: 古いポリシーを削除します。**</span><span class="sxs-lookup"><span data-stu-id="3c66e-120">**Step 5 - Delete the old policy.**</span></span>

<span data-ttu-id="3c66e-121">特殊文字を含む古いポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="3c66e-121">This will delete the old policy with the special characters.</span></span>
  ```
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
<span data-ttu-id="3c66e-122">このコマンドレットの詳細については[削除 CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps)を参照します。</span><span class="sxs-lookup"><span data-stu-id="3c66e-122">See, [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="3c66e-123">このコマンドが成功した場合は終了しました。</span><span class="sxs-lookup"><span data-stu-id="3c66e-123">If this command succeeds, you're done.</span></span> <span data-ttu-id="3c66e-124">上記のコマンドでは、エラーが返された場合は、割り当てられたすべてのユーザーをポリシーから削除するために実行する必要がありますので、古いポリシーがユーザーに割り当てられますため。</span><span class="sxs-lookup"><span data-stu-id="3c66e-124">If the above command returns an error, it is because the old policy is assigned to users so you need to run to remove all assigned users from the policy:</span></span>

```
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="3c66e-125">Go to the Office 365 admin centerSkype for Business.</span><span class="sxs-lookup"><span data-stu-id="3c66e-125">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="3c66e-p105">Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c66e-p105">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="3c66e-129">なぜ Office 365 の PowerShell を使用する必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="3c66e-129">Why you need to use Office 365 PowerShell?</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="3c66e-130">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="3c66e-130">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="3c66e-p106">多くのユーザーの設定を同時に変更するときなどは、Office 365 管理センターのみを使用するよりも、Windows PowerShell の方に、速度、わかりやすさ、生産性の点で多くのメリットがあります。</span><span class="sxs-lookup"><span data-stu-id="3c66e-p106">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="3c66e-133">Windows PowerShell と Lync Online の概要</span><span class="sxs-lookup"><span data-stu-id="3c66e-133">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="3c66e-134">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="3c66e-134">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="3c66e-135">クイック リファレンス: Windows PowerShell を使用した一般的な Lync Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="3c66e-135">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="3c66e-136">ビジネス オンラインの Skype については、Windows PowerShell モジュールを使用すると、Skype のビジネスをオンラインで、マイクロソフトのチームに接続するリモートの Windows PowerShell セッションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="3c66e-136">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online and Microsoft Teams.</span></span> <span data-ttu-id="3c66e-137">Skype for Business Online 用 Windows PowerShell モジュールでは、リモート Windows PowerShell セッションを作成して Skype for Business Online に接続できます。</span><span class="sxs-lookup"><span data-stu-id="3c66e-137">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
### <a name="related-topics"></a><span data-ttu-id="3c66e-138">このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="3c66e-138">Related topics</span></span>
