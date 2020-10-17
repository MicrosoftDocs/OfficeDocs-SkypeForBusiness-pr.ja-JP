---
title: グローバルスコープとタグスコープを使用する Skype for Business Online のコマンドレット
description: グローバルスコープとタグスコープを使用する Skype for Business Online のコマンドレット。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
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
ms.openlocfilehash: ba89ebe7322159027c5de765117afd366cb3dc23
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545623"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope"></a><span data-ttu-id="63d3e-103">グローバルスコープとタグスコープを使用する Skype for Business Online のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="63d3e-103">Cmdlets in Skype for Business Online that use the global scope and the tag scope</span></span>

 


<span data-ttu-id="63d3e-104">Skype for Business Online では、ポリシーは、 *グローバルスコープ* または *タグの範囲* (または *ユーザーごとのスコープ*) のいずれかで構成できます。</span><span class="sxs-lookup"><span data-stu-id="63d3e-104">In Skype for Business Online, policies can be configured at either the *global scope* or at the *tag scope* (or *per-user scope*).</span></span> <span data-ttu-id="63d3e-105">**Get-Cs**コマンドレットを使用する場合、スコープまたは id を指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="63d3e-105">When using the **Get-Cs** cmdlets, you do not have to specify a scope or identity.</span></span> <span data-ttu-id="63d3e-106">パラメーターを指定せずにこれらのコマンドレットのいずれかを呼び出すと、関連するすべての項目が返されます。</span><span class="sxs-lookup"><span data-stu-id="63d3e-106">If you call one of these cmdlets without any parameters, then all the relevant items will be returned.</span></span> <span data-ttu-id="63d3e-107">たとえば、次のコマンドを実行すると、すべての外部アクセスポリシーに関する情報が戻されます。</span><span class="sxs-lookup"><span data-stu-id="63d3e-107">For example, this command returns information about all your external access policies:</span></span>

    Get-CsExternalAccessPolicy

<span data-ttu-id="63d3e-108">返されるデータを制限する場合は、Identity パラメーターまたは Filter パラメーターのみを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="63d3e-108">You need to include only the Identity parameter or the Filter parameter if you want to limit the returned data.</span></span> <span data-ttu-id="63d3e-109">たとえば、グローバルポリシーのみを返すには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="63d3e-109">For example, to return only the global policy, use this command:</span></span>

    Get-CsExternalAccessPolicy -Identity "global"

<span data-ttu-id="63d3e-110">Id が "RedmondAccessPolicy" のユーザーごとのポリシーを返すには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="63d3e-110">To return a per-user policy that has the Identity “RedmondAccessPolicy”, use this command:</span></span>

    Get-CsExternalAccessPolicy -Identity "RedmondAccessPolicy"


> [!NOTE]  
> <span data-ttu-id="63d3e-111">ユーザーごとのポリシーを参照する場合、タグ <STRONG>プリフィックス</STRONG> はオプションです。</span><span class="sxs-lookup"><span data-stu-id="63d3e-111">When referencing a per-user policy, the tag <STRONG>prefix</STRONG> is optional.</span></span> <span data-ttu-id="63d3e-112">この構文は、プレフィックスを含むので、次のようにも有効です。</span><span class="sxs-lookup"><span data-stu-id="63d3e-112">This syntax, which includes the prefix, is also valid:</span></span><BR><span data-ttu-id="63d3e-113">Get-CsExternalAccessPolicy – Identity "tag: RedmondAccessPolicy"</span><span class="sxs-lookup"><span data-stu-id="63d3e-113">Get-CsExternalAccessPolicy –Identity "tag:RedmondAccessPolicy"</span></span>



<span data-ttu-id="63d3e-114">グローバルポリシー (つまり、すべてのユーザーごとのポリシー) を除くすべてのポリシーを戻すには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="63d3e-114">To return all policies except the global policies (that is, all the per-user policies), use this command:</span></span>

    Get-CsExternalAccessPolicy -Filter "tag:*"

<span data-ttu-id="63d3e-115">次のコマンドレットは、グローバルスコープとユーザーごと (タグ) スコープの両方に対して動作します。</span><span class="sxs-lookup"><span data-stu-id="63d3e-115">The following cmdlets operate against both the global scope and the per-user (tag) scope:</span></span>

  - <span data-ttu-id="63d3e-116">[Get-CsClientPolicy](https://technet.microsoft.com/library/gg398830\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="63d3e-116">[Get-CsClientPolicy](https://technet.microsoft.com/library/gg398830\(v=ocs.15\))</span></span>

  - <span data-ttu-id="63d3e-117">[Get-CsConferencingPolicy](https://technet.microsoft.com/library/gg398293\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="63d3e-117">[Get-CsConferencingPolicy](https://technet.microsoft.com/library/gg398293\(v=ocs.15\))</span></span>

  - <span data-ttu-id="63d3e-118">[Get-CsDialPlan](https://technet.microsoft.com/library/gg413043\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="63d3e-118">[Get-CsDialPlan](https://technet.microsoft.com/library/gg413043\(v=ocs.15\))</span></span>

  - <span data-ttu-id="63d3e-119">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425805\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="63d3e-119">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425805\(v=ocs.15\))</span></span>

  - <span data-ttu-id="63d3e-120">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg398348\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="63d3e-120">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg398348\(v=ocs.15\))</span></span>

  - <span data-ttu-id="63d3e-121">[Get-CsPresencePolicy](https://technet.microsoft.com/library/gg398463\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="63d3e-121">[Get-CsPresencePolicy](https://technet.microsoft.com/library/gg398463\(v=ocs.15\))</span></span>

  - <span data-ttu-id="63d3e-122">[Get-CsVoicePolicy](https://technet.microsoft.com/library/gg398101\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="63d3e-122">[Get-CsVoicePolicy](https://technet.microsoft.com/library/gg398101\(v=ocs.15\))</span></span>


> [!NOTE]  
> <span data-ttu-id="63d3e-123">名前にかかわらず、ダイヤルプランは、機能的には、ポリシーになります。</span><span class="sxs-lookup"><span data-stu-id="63d3e-123">Despite the name, dial plans are, functionally speaking, policies.</span></span> <span data-ttu-id="63d3e-124">以前のバージョンの Lync Server で使用されていた用語を保持するために、ダイヤルポリシーなどの代わりに、" <EM>ダイヤルプラン</EM> " という用語を使用します。</span><span class="sxs-lookup"><span data-stu-id="63d3e-124">The term <EM>dial plan</EM> is used instead of, for example, dialing policy, in order to preserve the terminology used with previous versions of Lync Server.</span></span>



## <a name="see-also"></a><span data-ttu-id="63d3e-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="63d3e-125">See Also</span></span>


[<span data-ttu-id="63d3e-126">Skype for Business Online の id、スコープ、およびテナント</span><span class="sxs-lookup"><span data-stu-id="63d3e-126">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="63d3e-127">[Skype for Business Online のコマンドレット](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="63d3e-127">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

