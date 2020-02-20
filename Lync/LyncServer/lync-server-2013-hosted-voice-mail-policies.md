---
title: 'Lync Server 2013: ホストボイスメールポリシー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted voice mail policies
ms:assetid: d62a35ed-cbe2-4f06-86b4-e192c18435c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398932(v=OCS.15)
ms:contentKeyID: 48185506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16570331d0d7e154388c51ecb11be591bf3bbd05
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154909"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hosted-voice-mail-policies-in-lync-server-2013"></a><span data-ttu-id="509b9-102">Lync Server 2013 のホストボイスメールポリシー</span><span class="sxs-lookup"><span data-stu-id="509b9-102">Hosted voice mail policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="509b9-103">_**トピックの最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="509b9-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="509b9-104">*ホストボイスメールポリシー*は、ホストされた Exchange サービスにメールボックスがあるユーザーの呼び出しをルーティングする場所について、Lync Server 2013 Exum ルーティングアプリケーションに情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="509b9-104">A *hosted voice mail policy* provides information to the Lync Server 2013 ExUM Routing application about where to route calls for users whose mailboxes are located on a hosted Exchange service.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="509b9-105">ホストボイスメールポリシーは、ホストされた Exchange UM との Lync Server 2013 の統合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="509b9-105">Hosted voice mail policies are required only for Lync Server 2013 integration with hosted Exchange UM.</span></span> <span data-ttu-id="509b9-106">内部設置型の Exchange UM との統合には必要ありません。</span><span class="sxs-lookup"><span data-stu-id="509b9-106">They are not needed for integration with on-premises Exchange UM.</span></span>



</div>

<div>

## <a name="hosted-voice-mail-policy-scope"></a><span data-ttu-id="509b9-107">ホスト ボイス メール ポリシーのスコープ</span><span class="sxs-lookup"><span data-stu-id="509b9-107">Hosted Voice Mail Policy Scope</span></span>

<span data-ttu-id="509b9-p102">ホスト ボイス メール ポリシーのスコープでは、ポリシーが適用される階層レベルが指定されます。以下のスコープ レベルのホスト ボイス メール ポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="509b9-p102">Hosted voice mail policy scope determines the hierarchical level at which the policy applies. You can configure hosted voice mail policies with the following scope levels:</span></span>

  - <span data-ttu-id="509b9-110">*グローバル*ポリシーは、Lync Server 2013 展開内のすべてのユーザーに影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="509b9-110">The *global* policy can potentially affect all users in the Lync Server 2013 deployment.</span></span> <span data-ttu-id="509b9-111">Hosted Exchange UM へのアクセスが有効になっているユーザーに対してユーザー単位のポリシーが割り当てられていない場合、およびユーザーのサイトにサイト ポリシーが割り当てられていない場合には、グローバル ポーリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="509b9-111">If a user is enabled for hosted Exchange UM access and has not been assigned a per-user policy, and if a site policy has not been assigned to the user’s site, the global policy applies.</span></span> <span data-ttu-id="509b9-112">グローバルポリシーは、Lync Server 2013 と共にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="509b9-112">The global policy is installed with Lync Server 2013.</span></span> <span data-ttu-id="509b9-113">グローバル ポリシーを必要に応じて変更することはできますが、名前変更や削除はできません。</span><span class="sxs-lookup"><span data-stu-id="509b9-113">You can modify it to meet your needs, but you cannot rename or delete it.</span></span>

  - <span data-ttu-id="509b9-p104">*サイト* ポリシーは、このポリシーが定義されているサイトに所属するすべてのユーザーに影響します。Hosted Exchange UM にアクセスできるように構成されているユーザーにユーザー単位のポリシーが割り当てられていない場合には、サイト ポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="509b9-p104">A *site* policy can affect all users that are homed on the site for which the policy is defined. If a user is configured for hosted Exchange UM access and has not been assigned a per-user policy, the site policy applies.</span></span>

  - <span data-ttu-id="509b9-p105">*ユーザー単位の*ポリシーは、個々のユーザーやグループにだけ影響します。ユーザー単位のポリシーを適用するには、個々のユーザー、グループ、または連絡先オブジェクトにこのポリシーを明示的に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="509b9-p105">A *per-user* policy can affect only individual users or groups. To enforce a per-user policy, you must explicitly assign the policy to individual users, groups, and contact objects.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="509b9-p106">ほとんどの場合には、必要なホスト ボイス メール ポリシーは 1 つだけです。多くの場合には、必要に応じてグローバル ポリシーを変更できます。複数のホスト ボイス メール ポリシーを展開する場合には、展開するすべてのポリシーにユーザー単位のスコープがあります。</span><span class="sxs-lookup"><span data-stu-id="509b9-p106">In most cases, only one hosted voice mail policy is required. You can often modify the global policy to meet all your needs. If you deploy multiple hosted voice mail policies, all such policies have per-user scope.</span></span>



</div>

</div>

<div>

## <a name="hosted-voice-mail-policy-attributes"></a><span data-ttu-id="509b9-121">ホスト ボイス メール ポリシーの属性</span><span class="sxs-lookup"><span data-stu-id="509b9-121">Hosted Voice Mail Policy Attributes</span></span>

<span data-ttu-id="509b9-122">ボイスメールポリシーは、Lync Server 2013 ExUM ルーティングアプリケーションが、hosted Exchange UM 実装に送信される INVITE メッセージの要求 URI に挿入する2つの属性を定義します。</span><span class="sxs-lookup"><span data-stu-id="509b9-122">A voice mail policy defines two attributes that the Lync Server 2013 ExUM Routing application inserts in the request URI of an INVITE message that is sent to the hosted Exchange UM implementation:</span></span>

  - <span data-ttu-id="509b9-123">**Destination:** Hosted Exchange UM サービスの完全修飾ドメイン名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="509b9-123">**Destination:** The fully qualified domain name (FQDN) of the hosted Exchange UM service.</span></span> <span data-ttu-id="509b9-124">この値は、ルーティングのためにオンプレミスの Lync Server エッジサーバーによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="509b9-124">This value is used by the on-premises Lync Server Edge Server for routing purposes.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="509b9-125">Exchange Online の FQDN は exap.um.outlook.com です。</span><span class="sxs-lookup"><span data-stu-id="509b9-125">The FQDN for Exchange Online is exap.um.outlook.com.</span></span>

    
    </div>

  - <span data-ttu-id="509b9-126">**組織:** Lync Server 2013 ユーザーのメールボックスをホームとする、ホストされた Exchange UM サービス上のテナントの FQDN。</span><span class="sxs-lookup"><span data-stu-id="509b9-126">**Organization:** The FQDN of the tenant on the hosted Exchange UM service that homes your Lync Server 2013 users’ mailboxes.</span></span> <span data-ttu-id="509b9-127">ボイス メール ポリシーには複数の組織が含まれていることがあります。</span><span class="sxs-lookup"><span data-stu-id="509b9-127">A voice mail policy can contain multiple organizations.</span></span> <span data-ttu-id="509b9-128">ポリシーに複数の組織が含まれている場合、この属性は、Lync Server 2013 ユーザーメールボックスのホームとなる Exchange Server テナントのコンマ区切りのリストである必要があります。</span><span class="sxs-lookup"><span data-stu-id="509b9-128">If more than one organization is included in the policy, this attribute must be a comma-separated list of the Exchange Server tenants that home your Lync Server 2013 user mailboxes.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="509b9-p109">Hosted Exchange UM サービスのテナント管理者が、宛先と組織の属性設定に必要な値を提供します。ポリシーを構成するには、New-CsHostedVoicemailPolicy コマンドレットを実行するか、または Set-CsHostedVoicemailPolicy コマンドレットを使用して既存のポリシー (例: グローバル ポリシー) を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="509b9-p109">The tenant administrator of your hosted Exchange UM service will provide the necessary values for your Destination and Organization attribute settings. To configure your policy, you must run the New-CsHostedVoicemailPolicy cmdlet or use the Set-CsHostedVoicemailPolicy cmdlet to modify one that exists (for example, the global policy).</span></span>



</div>

<span data-ttu-id="509b9-131">ホストボイスメールポリシーの管理の詳細については、「Lync Server Management Shell」のドキュメントの次のコマンドレットを参照してください。</span><span class="sxs-lookup"><span data-stu-id="509b9-131">For details about managing hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="509b9-132">New-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="509b9-132">New-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="509b9-133">Set-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="509b9-133">Set-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="509b9-134">Get-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="509b9-134">Get-CsHostedVoicemailPolicy</span></span>

</div>

<div>

## <a name="per-user-voice-mail-policy-assignment"></a><span data-ttu-id="509b9-135">ユーザー単位のボイス メール ポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="509b9-135">Per-User Voice Mail Policy Assignment</span></span>

<span data-ttu-id="509b9-p110">ホスト ボイス メール ポリシーがユーザー単位のスコープで定義されている場合には、ユーザー単位のスコープを明示的に割り当てる必要があります。Grant-CsHostedVoicemailPolicy コマンドレッドを実行して、ポリシーを個々のユーザーまたはグループに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="509b9-p110">If your hosted voice mail policy is defined with per-user scope, you must explicitly assign it. You can run the Grant-CsHostedVoicemailPolicy cmdlet to assign the policy to individual users or groups.</span></span>

<span data-ttu-id="509b9-138">ユーザーごとのホストボイスメールポリシーの割り当てまたは削除の詳細については、「Lync Server Management Shell」のドキュメントの次のコマンドレットを参照してください。</span><span class="sxs-lookup"><span data-stu-id="509b9-138">For details about assigning or removing a per-user hosted voice mail policy, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="509b9-139">Grant-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="509b9-139">Grant-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="509b9-140">Remove-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="509b9-140">Remove-CsHostedVoicemailPolicy</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

