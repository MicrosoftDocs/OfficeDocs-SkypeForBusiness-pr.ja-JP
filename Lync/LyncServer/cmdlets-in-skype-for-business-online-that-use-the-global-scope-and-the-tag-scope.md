---
title: グローバルスコープとタグスコープを使用する Skype for Business Online のコマンドレット
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use the global scope and the tag scope
ms:assetid: 1e2bc055-8a72-425e-967b-e253add7018c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362774(v=OCS.15)
ms:contentKeyID: 56558824
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 998201bf7772003c83ae27d56b3a238f9f0ca055
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42001152"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope"></a><span data-ttu-id="53547-102">グローバルスコープとタグスコープを使用する Skype for Business Online のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="53547-102">Cmdlets in Skype for Business Online that use the global scope and the tag scope</span></span>

 


<span data-ttu-id="53547-103">Skype for Business Online では、ポリシーは、*グローバルスコープ*または*タグの範囲*(または*ユーザーごとのスコープ*) のいずれかで構成できます。</span><span class="sxs-lookup"><span data-stu-id="53547-103">In Skype for Business Online, policies can be configured at either the *global scope* or at the *tag scope* (or *per-user scope*).</span></span> <span data-ttu-id="53547-104">**Get-Cs**コマンドレットを使用する場合、スコープまたは id を指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="53547-104">When using the **Get-Cs** cmdlets, you do not have to specify a scope or identity.</span></span> <span data-ttu-id="53547-105">パラメーターを指定せずにこれらのコマンドレットのいずれかを呼び出すと、関連するすべての項目が返されます。</span><span class="sxs-lookup"><span data-stu-id="53547-105">If you call one of these cmdlets without any parameters, then all the relevant items will be returned.</span></span> <span data-ttu-id="53547-106">たとえば、次のコマンドを実行すると、すべての外部アクセスポリシーに関する情報が戻されます。</span><span class="sxs-lookup"><span data-stu-id="53547-106">For example, this command returns information about all your external access policies:</span></span>

    Get-CsExternalAccessPolicy

<span data-ttu-id="53547-107">返されるデータを制限する場合は、Identity パラメーターまたは Filter パラメーターのみを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="53547-107">You need to include only the Identity parameter or the Filter parameter if you want to limit the returned data.</span></span> <span data-ttu-id="53547-108">たとえば、グローバルポリシーのみを返すには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="53547-108">For example, to return only the global policy, use this command:</span></span>

    Get-CsExternalAccessPolicy -Identity "global"

<span data-ttu-id="53547-109">Id が "RedmondAccessPolicy" のユーザーごとのポリシーを返すには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="53547-109">To return a per-user policy that has the Identity “RedmondAccessPolicy”, use this command:</span></span>

    Get-CsExternalAccessPolicy -Identity "RedmondAccessPolicy"


> [!NOTE]  
> <span data-ttu-id="53547-110">ユーザーごとのポリシーを参照する場合、タグ<STRONG>プリフィックス</STRONG>はオプションです。</span><span class="sxs-lookup"><span data-stu-id="53547-110">When referencing a per-user policy, the tag <STRONG>prefix</STRONG> is optional.</span></span> <span data-ttu-id="53547-111">この構文は、プレフィックスを含むので、次のようにも有効です。</span><span class="sxs-lookup"><span data-stu-id="53547-111">This syntax, which includes the prefix, is also valid:</span></span><BR><span data-ttu-id="53547-112">Get-csexternalaccesspolicy – Identity "タグ: RedmondAccessPolicy"</span><span class="sxs-lookup"><span data-stu-id="53547-112">Get-CsExternalAccessPolicy –Identity "tag:RedmondAccessPolicy"</span></span>



<span data-ttu-id="53547-113">グローバルポリシー (つまり、すべてのユーザーごとのポリシー) を除くすべてのポリシーを戻すには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="53547-113">To return all policies except the global policies (that is, all the per-user policies), use this command:</span></span>

    Get-CsExternalAccessPolicy -Filter "tag:*"

<span data-ttu-id="53547-114">次のコマンドレットは、グローバルスコープとユーザーごと (タグ) スコープの両方に対して動作します。</span><span class="sxs-lookup"><span data-stu-id="53547-114">The following cmdlets operate against both the global scope and the per-user (tag) scope:</span></span>

  - <span data-ttu-id="53547-115">[Get-CsClientPolicy](https://technet.microsoft.com/library/gg398830\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="53547-115">[Get-CsClientPolicy](https://technet.microsoft.com/library/gg398830\(v=ocs.15\))</span></span>

  - <span data-ttu-id="53547-116">[Get-CsConferencingPolicy](https://technet.microsoft.com/library/gg398293\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="53547-116">[Get-CsConferencingPolicy](https://technet.microsoft.com/library/gg398293\(v=ocs.15\))</span></span>

  - <span data-ttu-id="53547-117">[Get-CsDialPlan](https://technet.microsoft.com/library/gg413043\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="53547-117">[Get-CsDialPlan](https://technet.microsoft.com/library/gg413043\(v=ocs.15\))</span></span>

  - <span data-ttu-id="53547-118">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425805\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="53547-118">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425805\(v=ocs.15\))</span></span>

  - <span data-ttu-id="53547-119">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg398348\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="53547-119">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg398348\(v=ocs.15\))</span></span>

  - <span data-ttu-id="53547-120">[Get-CsPresencePolicy](https://technet.microsoft.com/library/gg398463\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="53547-120">[Get-CsPresencePolicy](https://technet.microsoft.com/library/gg398463\(v=ocs.15\))</span></span>

  - <span data-ttu-id="53547-121">[Get-CsVoicePolicy](https://technet.microsoft.com/library/gg398101\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="53547-121">[Get-CsVoicePolicy](https://technet.microsoft.com/library/gg398101\(v=ocs.15\))</span></span>


> [!NOTE]  
> <span data-ttu-id="53547-122">名前にかかわらず、ダイヤルプランは、機能的には、ポリシーになります。</span><span class="sxs-lookup"><span data-stu-id="53547-122">Despite the name, dial plans are, functionally speaking, policies.</span></span> <span data-ttu-id="53547-123">以前のバージョンの Lync Server で使用されていた用語を保持するために、ダイヤルポリシーなどの代わりに、"<EM>ダイヤルプラン</EM>" という用語を使用します。</span><span class="sxs-lookup"><span data-stu-id="53547-123">The term <EM>dial plan</EM> is used instead of, for example, dialing policy, in order to preserve the terminology used with previous versions of Lync Server.</span></span>



## <a name="see-also"></a><span data-ttu-id="53547-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="53547-124">See Also</span></span>


[<span data-ttu-id="53547-125">Skype for Business Online の id、スコープ、およびテナント</span><span class="sxs-lookup"><span data-stu-id="53547-125">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="53547-126">[Skype for Business Online のコマンドレット](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="53547-126">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

