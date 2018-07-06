---
title: チーム ポリシー内の特殊文字の制限は?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords:
- me.teamsadmincenter.policies.naming.error
description: ポリシーおよびその修正を行うことができますの名前に特殊文字を含むが、どのような問題を参照してください。
ms.openlocfilehash: 7d835669f0acc7cd2a2e42acb1aa9fa9d2fdf765
ms.sourcegitcommit: 26d93a15c9d4704c08f3fabc5635839ce2456b2d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "20205079"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a><span data-ttu-id="ef5c0-103">チーム ポリシー内の特殊文字の制限は?</span><span class="sxs-lookup"><span data-stu-id="ef5c0-103">What are the special character restrictions in Teams policies?</span></span>

<span data-ttu-id="ef5c0-104">**PowerShell でチームのポリシーを作成するための特殊文字を使用できますが、これらのポリシーを管理する制限されます。 このため、ポリシーの名前に特殊文字が含まれていないを強くお勧めします。**</span><span class="sxs-lookup"><span data-stu-id="ef5c0-104">**Although special characters can be used for creating Teams policies with PowerShell, you will be limited in managing these policies .  As such, we strongly recommend policy names do not include special characters.**</span></span>

<span data-ttu-id="ef5c0-105">PowerShell を使用して会議を作成し、チームでチャットするポリシー名は次のように特殊文字を持つことができます @、#、$。</span><span class="sxs-lookup"><span data-stu-id="ef5c0-105">Policy names that you create using PowerShell for meetings and chat in Teams can have special characters such as @,#,$.</span></span> <span data-ttu-id="ef5c0-106">ただし、ビジネス管理センターは、マイクロソフトのチームと Skype でポリシーを編集しようとしている場合することはできませんにします。</span><span class="sxs-lookup"><span data-stu-id="ef5c0-106">However, if you are wanting to edit the policy in the Microsoft Teams and Skype for Business admin center, you won't be able to.</span></span> <span data-ttu-id="ef5c0-107">Windows PowerShell と適切なポリシーのコマンドレットを使用して、変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef5c0-107">You must use Windows PowerShell and the correct policy cmdlet to make changes.</span></span>

<span data-ttu-id="ef5c0-108">使用する必要があります特別な文字を使用して、ポリシーのオブジェクトがあり、ビジネス管理センターは、マイクロソフトのチームと Skype でポリシーを効率的に管理するために特殊文字を削除する場合、手順の下。</span><span class="sxs-lookup"><span data-stu-id="ef5c0-108">If you have a policy object with special characters and you want to remove the special characters in order to better manage the policy in the Microsoft Teams and Skype for Business admin center, you will need to use the below procedure.</span></span> 

<span data-ttu-id="ef5c0-109">注: 明確手順メッセージング ポリシーの例をここで使用します。</span><span class="sxs-lookup"><span data-stu-id="ef5c0-109">Note: The procedure articulated here uses the example of a Messaging policy.</span></span>  <span data-ttu-id="ef5c0-110">同じプロセス subsituting 関連のコマンドレットで別のポリシーの種類 (たとえば会議) に使用されます。</span><span class="sxs-lookup"><span data-stu-id="ef5c0-110">The same process would be used for another policy type (Meetings for example) by subsituting the relevant cmdlets.</span></span> 

<span data-ttu-id="ef5c0-111">1) Get CSMessagingPolicy を呼び出す-< old_policy_name > を識別し、ポリシーの出力をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="ef5c0-111">1.) Call Get-CSMessagingPolicy -identity <old_policy_name> and capture the output of the policy.</span></span>
<span data-ttu-id="ef5c0-112">2) 呼び出しのセット CSMessagingPolicy-< new_policy_name > を識別名に特殊文字を含まない元のポリシーとしては、同じ構成で新しいポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="ef5c0-112">2.) Call Set-CSMessagingPolicy -identity <new_policy_name> to create a new policy with the same configuration as the original policy but without any special characters in the name.</span></span>
<span data-ttu-id="ef5c0-113">3) 削除 CSMessagingPolicy を呼び出す-ポリシーを削除する < old_policy_name > を識別します。</span><span class="sxs-lookup"><span data-stu-id="ef5c0-113">3.) Call Delete-CSMessagingPolicy -identity <old_policy_name> to delete the policy.</span></span>  <span data-ttu-id="ef5c0-114">このコマンドが成功すると、完了し、ビジネス管理センターの PowerShell またはマイクロソフトのチームと Skype のいずれかを使用して新しいポリシーをユーザーの割り当てを開始します。</span><span class="sxs-lookup"><span data-stu-id="ef5c0-114">If this command succeeds, you're done and can begin to assign users to the new policy using either PowerShell or the Microsoft Teams and Skype for Business admin center.</span></span>
<span data-ttu-id="ef5c0-115">4) 上記のコマンドが成功しない場合は、古いポリシーは、ユーザーに割り当てられているので、です。</span><span class="sxs-lookup"><span data-stu-id="ef5c0-115">4.) If the above command does not succeed, it is because the old policy has been assigned to a user.</span></span>  <span data-ttu-id="ef5c0-116">ユーザーからポリシーの割り当てを解除、新規のポリシーを適用し、dwlete をもう一度実行するコマンドレット実行の割り当てを解除します。</span><span class="sxs-lookup"><span data-stu-id="ef5c0-116">Run unassign cmdlet to unassign the policy from user, assign new policy, then run dwlete again.</span></span>


