---
title: ユーザー id とタグスコープを使用する Skype for Business Online のコマンドレット
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
ms.openlocfilehash: a5319d527c859d239cd58eb5561d82a0b47a322e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42001442"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope"></a><span data-ttu-id="74d5c-102">ユーザー id とタグスコープを使用する Skype for Business Online のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="74d5c-102">Cmdlets in Skype for Business Online that use a user identity and the tag scope</span></span>

 


<span data-ttu-id="74d5c-103">**Grant-Cs**コマンドレット (ユーザーにポリシーを割り当てるために使用される) には、ユーザー Id (identity パラメーター) とユーザーごとのポリシーの Id (PolicyName パラメーター) という2つの識別子が必要です。</span><span class="sxs-lookup"><span data-stu-id="74d5c-103">The **Grant-Cs** cmdlets (used for assigning policies to users) require two identifiers: a user identity (the Identity parameter) and the identity of a per-user policy (the PolicyName parameter).</span></span> <span data-ttu-id="74d5c-104">たとえば、音声ポリシー RedmondVoicePolicy をユーザー Ken Myer に割り当てるには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="74d5c-104">For example, to assign the voice policy, RedmondVoicePolicy, to the user Ken Myer, you use the following command:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

<span data-ttu-id="74d5c-105">ポリシーをユーザーに割り当てる際には、次の2つの点に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="74d5c-105">There are two things to keep in mind when assigning policies to users.</span></span> <span data-ttu-id="74d5c-106">最初に、ユーザーごとのポリシーのみを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="74d5c-106">First, only per-user policies can be assigned.</span></span> <span data-ttu-id="74d5c-107">グローバルポリシーをユーザーに割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="74d5c-107">You cannot assign the global policy to a user.</span></span> <span data-ttu-id="74d5c-108">たとえば、次のコマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="74d5c-108">For example, this command will fail:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "global"

<span data-ttu-id="74d5c-109">グローバルポリシーを割り当てる必要がないため、このコマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="74d5c-109">This command fails because there is no need to assign the global policy.</span></span> <span data-ttu-id="74d5c-110">グローバルポリシーを使用してユーザーを管理する場合は、そのユーザーにユーザーごとのポリシーを割り当てないでください。</span><span class="sxs-lookup"><span data-stu-id="74d5c-110">If you want to manage a user by using the global policy, just be sure that you do not assign that user a per-user policy.</span></span> <span data-ttu-id="74d5c-111">ユーザーごとのポリシーがユーザーに割り当てられていない場合、そのユーザーはグローバルポリシーを使用して自動的に管理されます。</span><span class="sxs-lookup"><span data-stu-id="74d5c-111">If no per-user policy has been assigned to a user, the user will automatically be managed by using the global policy.</span></span>


> [!NOTE]  
> <span data-ttu-id="74d5c-112">ユーザーが以前ユーザーごとのポリシーを割り当てていて、そのポリシーの割り当てを解除して、代わりにグローバルポリシーでユーザーを管理する場合は、どうなりますか。</span><span class="sxs-lookup"><span data-stu-id="74d5c-112">What if the user has previously been assigned a per-user policy, and you want to unassign that policy and have the user managed by the global policy instead?</span></span> <span data-ttu-id="74d5c-113">その場合は、まず、次の構文を使用します。これは、ユーザーごとのポリシーを割り当てないようにするために、そのユーザーに null ポリシーを付与します。</span><span class="sxs-lookup"><span data-stu-id="74d5c-113">In that case, you’ll first use the following syntax, which unassigns a per-user policy by granting that user a null policy:</span></span><BR><span data-ttu-id="74d5c-114">Set-csvoicepolicy – Identity "Ken Myer" – PolicyName $Null</span><span class="sxs-lookup"><span data-stu-id="74d5c-114">Grant-CsVoicePolicy –Identity "Ken Myer" –PolicyName $Null</span></span>



<span data-ttu-id="74d5c-115">2番目に、ユーザーごとのポリシーがタグスコープで作成されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="74d5c-115">Second, keep in mind that per-user policies are created at the tag scope.</span></span> <span data-ttu-id="74d5c-116">ただし、ポリシー名を指定するときは、タグ**プレフィックス**を省略できます。</span><span class="sxs-lookup"><span data-stu-id="74d5c-116">However, you can omit the tag **prefix** when specifying a policy name.</span></span> <span data-ttu-id="74d5c-117">これらの2つのコマンドは同じです。</span><span class="sxs-lookup"><span data-stu-id="74d5c-117">These two commands are identical:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "tag:RedmondVoicePolicy"
    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

<span data-ttu-id="74d5c-118">すべてのユーザーごとのポリシー (または、少なくとも、音声ポリシーなど、指定された種類のすべてのユーザーごとのポリシー) の id を返す場合は、次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="74d5c-118">If you would like to return the identities for all your per-user policies (or, at least, all the per-user policies of specified type, such as voice policies), use a command similar to this:</span></span>

    Get-CsVoicePolicy -Filter "tag:*"

<span data-ttu-id="74d5c-119">次のコマンドレットでは、ユーザー Id とタグスコープの両方を使用します。</span><span class="sxs-lookup"><span data-stu-id="74d5c-119">The following cmdlets make use of both a user Identity and the tag scope:</span></span>

  - <span data-ttu-id="74d5c-120">[Grant-CsClientPolicy](https://technet.microsoft.com/library/gg412942\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="74d5c-120">[Grant-CsClientPolicy](https://technet.microsoft.com/library/gg412942\(v=ocs.15\))</span></span>

  - <span data-ttu-id="74d5c-121">[Get-csconferencingpolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="74d5c-121">[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\))</span></span>

  - <span data-ttu-id="74d5c-122">[Get-csdialplan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="74d5c-122">[Grant-CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\))</span></span>

  - <span data-ttu-id="74d5c-123">[Get-csexternalaccesspolicy](https://technet.microsoft.com/library/gg425942\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="74d5c-123">[Grant-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425942\(v=ocs.15\))</span></span>

  - <span data-ttu-id="74d5c-124">[Set-cshostedvoicemailpolicy](https://technet.microsoft.com/library/gg412829\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="74d5c-124">[Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg412829\(v=ocs.15\))</span></span>

  - <span data-ttu-id="74d5c-125">[Set-csvoicepolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="74d5c-125">[Grant-CsVoicePolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\))</span></span>

## <a name="see-also"></a><span data-ttu-id="74d5c-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="74d5c-126">See Also</span></span>


[<span data-ttu-id="74d5c-127">Skype for Business Online の id、スコープ、およびテナント</span><span class="sxs-lookup"><span data-stu-id="74d5c-127">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="74d5c-128">[Skype for Business Online のコマンドレット](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="74d5c-128">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

