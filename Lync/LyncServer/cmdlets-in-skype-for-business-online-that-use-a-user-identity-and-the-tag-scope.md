---
title: ユーザー id とタグのスコープを使う Skype for Business Online のコマンドレット
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use a user identity and the tag scope
ms:assetid: 344a21b0-5301-4e77-853a-970bb1c11e1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362781(v=OCS.15)
ms:contentKeyID: 56558838
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 24c197934705a86d91e0492949aa2a9e6484f903
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727567"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope"></a><span data-ttu-id="503eb-102">ユーザー id とタグのスコープを使う Skype for Business Online のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="503eb-102">Cmdlets in Skype for Business Online that use a user identity and the tag scope</span></span>

 


<span data-ttu-id="503eb-103">ユーザーにポリシーを割り当てるために使用される**Grant-Cs**コマンドレットは、ユーザー Id (identity パラメーター) とユーザーごとのポリシーの Id (PolicyName パラメーター) の2つの識別子を必要とします。</span><span class="sxs-lookup"><span data-stu-id="503eb-103">The **Grant-Cs** cmdlets (used for assigning policies to users) require two identifiers: a user identity (the Identity parameter) and the identity of a per-user policy (the PolicyName parameter).</span></span> <span data-ttu-id="503eb-104">たとえば、ユーザー Ken Myer にボイスポリシー RedmondVoicePolicy を割り当てるには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="503eb-104">For example, to assign the voice policy, RedmondVoicePolicy, to the user Ken Myer, you use the following command:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

<span data-ttu-id="503eb-105">ユーザーにポリシーを割り当てるときは、次の2つの点に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="503eb-105">There are two things to keep in mind when assigning policies to users.</span></span> <span data-ttu-id="503eb-106">最初に、ユーザーごとのポリシーのみを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="503eb-106">First, only per-user policies can be assigned.</span></span> <span data-ttu-id="503eb-107">グローバルポリシーをユーザーに割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="503eb-107">You cannot assign the global policy to a user.</span></span> <span data-ttu-id="503eb-108">たとえば、次のコマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="503eb-108">For example, this command will fail:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "global"

<span data-ttu-id="503eb-109">グローバルポリシーを割り当てる必要がないため、このコマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="503eb-109">This command fails because there is no need to assign the global policy.</span></span> <span data-ttu-id="503eb-110">グローバルポリシーを使用してユーザーを管理する場合は、そのユーザーにユーザーごとのポリシーを割り当てないでください。</span><span class="sxs-lookup"><span data-stu-id="503eb-110">If you want to manage a user by using the global policy, just be sure that you do not assign that user a per-user policy.</span></span> <span data-ttu-id="503eb-111">ユーザーごとのポリシーが割り当てられていない場合、そのユーザーはグローバルポリシーを使用して自動的に管理されます。</span><span class="sxs-lookup"><span data-stu-id="503eb-111">If no per-user policy has been assigned to a user, the user will automatically be managed by using the global policy.</span></span>


> [!NOTE]  
> <span data-ttu-id="503eb-112">ユーザーに以前にユーザーポリシーが割り当てられていて、そのポリシーを割り当て解除して、代わりにグローバルポリシーでユーザーを管理する場合は、どうすればよいですか。</span><span class="sxs-lookup"><span data-stu-id="503eb-112">What if the user has previously been assigned a per-user policy, and you want to unassign that policy and have the user managed by the global policy instead?</span></span> <span data-ttu-id="503eb-113">その場合は、最初に次の構文を使用します。この構文は、ユーザーに対して、null ポリシーを付与することにより、ユーザーごとのポリシーを割り当て解除します。</span><span class="sxs-lookup"><span data-stu-id="503eb-113">In that case, you’ll first use the following syntax, which unassigns a per-user policy by granting that user a null policy:</span></span><BR><span data-ttu-id="503eb-114">Grant-CsVoicePolicy – Identity "Ken Myer" – PolicyName $Null</span><span class="sxs-lookup"><span data-stu-id="503eb-114">Grant-CsVoicePolicy –Identity "Ken Myer" –PolicyName $Null</span></span>



<span data-ttu-id="503eb-115">次に、ユーザーごとのポリシーはタグのスコープで作成されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="503eb-115">Second, keep in mind that per-user policies are created at the tag scope.</span></span> <span data-ttu-id="503eb-116">ただし、ポリシー名を指定するときは、タグ**プレフィックス**を省略できます。</span><span class="sxs-lookup"><span data-stu-id="503eb-116">However, you can omit the tag **prefix** when specifying a policy name.</span></span> <span data-ttu-id="503eb-117">次の2つのコマンドは同じです。</span><span class="sxs-lookup"><span data-stu-id="503eb-117">These two commands are identical:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "tag:RedmondVoicePolicy"
    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

<span data-ttu-id="503eb-118">すべてのユーザーごとのポリシー (音声ポリシーなど、指定した種類のすべてのユーザーごとのポリシー) の id を返す場合は、次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="503eb-118">If you would like to return the identities for all your per-user policies (or, at least, all the per-user policies of specified type, such as voice policies), use a command similar to this:</span></span>

    Get-CsVoicePolicy -Filter "tag:*"

<span data-ttu-id="503eb-119">次のコマンドレットでは、ユーザー Id とタグスコープの両方を使用します。</span><span class="sxs-lookup"><span data-stu-id="503eb-119">The following cmdlets make use of both a user Identity and the tag scope:</span></span>

  - <span data-ttu-id="503eb-120">[権限の付与: CsClientPolicy](https://technet.microsoft.com/en-us/library/gg412942\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="503eb-120">[Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/gg412942\(v=ocs.15\))</span></span>

  - <span data-ttu-id="503eb-121">[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg425937\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="503eb-121">[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg425937\(v=ocs.15\))</span></span>

  - <span data-ttu-id="503eb-122">[Grant-CsDialPlan](https://technet.microsoft.com/en-us/library/gg398547\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="503eb-122">[Grant-CsDialPlan](https://technet.microsoft.com/en-us/library/gg398547\(v=ocs.15\))</span></span>

  - <span data-ttu-id="503eb-123">[Grant-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/gg425942\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="503eb-123">[Grant-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/gg425942\(v=ocs.15\))</span></span>

  - <span data-ttu-id="503eb-124">[Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg412829\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="503eb-124">[Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg412829\(v=ocs.15\))</span></span>

  - <span data-ttu-id="503eb-125">[Grant-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398828\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="503eb-125">[Grant-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398828\(v=ocs.15\))</span></span>

## <a name="see-also"></a><span data-ttu-id="503eb-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="503eb-126">See Also</span></span>


[<span data-ttu-id="503eb-127">Skype for Business Online の id、スコープ、テナント</span><span class="sxs-lookup"><span data-stu-id="503eb-127">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="503eb-128">[Lync Online のコマンドレット](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="503eb-128">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

