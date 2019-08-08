---
title: グローバルスコープとタグスコープを使う Skype for Business Online のコマンドレット
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Cmdlets that use the global scope and the tag scope
ms:assetid: 1e2bc055-8a72-425e-967b-e253add7018c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362774(v=OCS.15)
ms:contentKeyID: 56558824
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b274469f16ebb10338504afb2855e1c92774e545
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233100"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope"></a><span data-ttu-id="f13fc-102">グローバルスコープとタグスコープを使う Skype for Business Online のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="f13fc-102">Cmdlets in Skype for Business Online that use the global scope and the tag scope</span></span>

 


<span data-ttu-id="f13fc-103">Skype for Business Online では、ポリシーは*グローバルスコープ*または*タグのスコープ*(または*ユーザーごとのスコープ*) で構成できます。</span><span class="sxs-lookup"><span data-stu-id="f13fc-103">In Skype for Business Online, policies can be configured at either the *global scope* or at the *tag scope* (or *per-user scope*).</span></span> <span data-ttu-id="f13fc-104">**Get-Cs**コマンドレットを使う場合は、スコープまたは id を指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f13fc-104">When using the **Get-Cs** cmdlets, you do not have to specify a scope or identity.</span></span> <span data-ttu-id="f13fc-105">パラメーターを指定せずにこれらのコマンドレットのいずれかを呼び出すと、関連するすべての項目が返されます。</span><span class="sxs-lookup"><span data-stu-id="f13fc-105">If you call one of these cmdlets without any parameters, then all the relevant items will be returned.</span></span> <span data-ttu-id="f13fc-106">たとえば、次のコマンドは、すべての外部アクセスポリシーに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="f13fc-106">For example, this command returns information about all your external access policies:</span></span>

    Get-CsExternalAccessPolicy

<span data-ttu-id="f13fc-107">返されるデータを制限する場合は、Identity パラメーターまたは Filter パラメーターのみを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="f13fc-107">You need to include only the Identity parameter or the Filter parameter if you want to limit the returned data.</span></span> <span data-ttu-id="f13fc-108">たとえば、グローバルポリシーのみを返すには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="f13fc-108">For example, to return only the global policy, use this command:</span></span>

    Get-CsExternalAccessPolicy -Identity "global"

<span data-ttu-id="f13fc-109">Id が "RedmondAccessPolicy" のユーザーごとのポリシーを返すには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="f13fc-109">To return a per-user policy that has the Identity “RedmondAccessPolicy”, use this command:</span></span>

    Get-CsExternalAccessPolicy -Identity "RedmondAccessPolicy"


> [!NOTE]  
> <span data-ttu-id="f13fc-110">ユーザーごとのポリシーを参照する場合、タグ<STRONG>プレフィックス</STRONG>は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="f13fc-110">When referencing a per-user policy, the tag <STRONG>prefix</STRONG> is optional.</span></span> <span data-ttu-id="f13fc-111">プレフィックスを含むこの構文は、次の場合にも有効です。</span><span class="sxs-lookup"><span data-stu-id="f13fc-111">This syntax, which includes the prefix, is also valid:</span></span><BR><span data-ttu-id="f13fc-112">Get-CsExternalAccessPolicy – Identity "tag: RedmondAccessPolicy"</span><span class="sxs-lookup"><span data-stu-id="f13fc-112">Get-CsExternalAccessPolicy –Identity "tag:RedmondAccessPolicy"</span></span>



<span data-ttu-id="f13fc-113">グローバルポリシー (つまり、ユーザーごとのポリシー) を除くすべてのポリシーを返すには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="f13fc-113">To return all policies except the global policies (that is, all the per-user policies), use this command:</span></span>

    Get-CsExternalAccessPolicy -Filter "tag:*"

<span data-ttu-id="f13fc-114">次のコマンドレットは、グローバルスコープとユーザーごとの (タグ) スコープの両方に対して動作します。</span><span class="sxs-lookup"><span data-stu-id="f13fc-114">The following cmdlets operate against both the global scope and the per-user (tag) scope:</span></span>

  - <span data-ttu-id="f13fc-115">[CsClientPolicy の入手](https://technet.microsoft.com/en-us/library/gg398830\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="f13fc-115">[Get-CsClientPolicy](https://technet.microsoft.com/en-us/library/gg398830\(v=ocs.15\))</span></span>

  - <span data-ttu-id="f13fc-116">[Get-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg398293\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="f13fc-116">[Get-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg398293\(v=ocs.15\))</span></span>

  - <span data-ttu-id="f13fc-117">[Get-CsDialPlan](https://technet.microsoft.com/en-us/library/gg413043\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="f13fc-117">[Get-CsDialPlan](https://technet.microsoft.com/en-us/library/gg413043\(v=ocs.15\))</span></span>

  - <span data-ttu-id="f13fc-118">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/gg425805\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="f13fc-118">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/gg425805\(v=ocs.15\))</span></span>

  - <span data-ttu-id="f13fc-119">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg398348\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="f13fc-119">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg398348\(v=ocs.15\))</span></span>

  - <span data-ttu-id="f13fc-120">[Get-CsPresencePolicy](https://technet.microsoft.com/en-us/library/gg398463\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="f13fc-120">[Get-CsPresencePolicy](https://technet.microsoft.com/en-us/library/gg398463\(v=ocs.15\))</span></span>

  - <span data-ttu-id="f13fc-121">[Get-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398101\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="f13fc-121">[Get-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398101\(v=ocs.15\))</span></span>


> [!NOTE]  
> <span data-ttu-id="f13fc-122">名前にかかわらず、ダイヤルプランは、機能的に言うことができます。ポリシー。</span><span class="sxs-lookup"><span data-stu-id="f13fc-122">Despite the name, dial plans are, functionally speaking, policies.</span></span> <span data-ttu-id="f13fc-123">以前のバージョンの Lync Server で使用されていた用語を保存するために、[ダイヤルポリシー] の代わりに、"<EM>ダイヤルプラン</EM>" という用語を使用します。</span><span class="sxs-lookup"><span data-stu-id="f13fc-123">The term <EM>dial plan</EM> is used instead of, for example, dialing policy, in order to preserve the terminology used with previous versions of Lync Server.</span></span>



## <a name="see-also"></a><span data-ttu-id="f13fc-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="f13fc-124">See Also</span></span>


[<span data-ttu-id="f13fc-125">Skype for Business Online の id、スコープ、テナント</span><span class="sxs-lookup"><span data-stu-id="f13fc-125">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="f13fc-126">[Lync Online のコマンドレット](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="f13fc-126">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

