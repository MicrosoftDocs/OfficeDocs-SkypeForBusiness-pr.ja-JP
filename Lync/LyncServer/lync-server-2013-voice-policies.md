---
title: 'Lync Server 2013: 音声ポリシー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Voice policies
ms:assetid: b7433c62-9d8c-48af-89a0-19f0d34806ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412891(v=OCS.15)
ms:contentKeyID: 48185223
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a9df9b1caa42d3dc17d2f4f9e0908ed69d5660d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041286"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voice-policies-in-lync-server-2013"></a><span data-ttu-id="72056-102">Lync Server 2013 の音声ポリシー</span><span class="sxs-lookup"><span data-stu-id="72056-102">Voice policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72056-103">_**トピックの最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="72056-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="72056-104">Lync Server の*音声ポリシー*によって、ポリシーが割り当てられている各ユーザー、サイト、または組織に対して次のものが定義されます。</span><span class="sxs-lookup"><span data-stu-id="72056-104">Lync Server *voice policies* define the following for each user, site, or organization that is assigned the policy:</span></span>

  - <span data-ttu-id="72056-105">ユーザーが使用できるエンタープライズ Voip 機能を決定するために有効または無効にできる一連の通話機能。</span><span class="sxs-lookup"><span data-stu-id="72056-105">A set of calling features that can be enabled or disabled to determine the Enterprise Voice functionality available to users.</span></span>

  - <span data-ttu-id="72056-106">承認される通話の種類を定義する一連の公衆交換電話網 (PSTN) 使用法レコード。</span><span class="sxs-lookup"><span data-stu-id="72056-106">A set of public switched telephone network (PSTN) usage records that define what types of calls are authorized.</span></span>

<div>

## <a name="planning-for-voice-policies"></a><span data-ttu-id="72056-107">音声ポリシーの計画</span><span class="sxs-lookup"><span data-stu-id="72056-107">Planning for Voice Policies</span></span>

<span data-ttu-id="72056-108">次の手順は、エンタープライズ Voip 展開に必要な音声ポリシーを計画するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="72056-108">The following steps will help you plan the voice policies that you will need for your Enterprise Voice deployment:</span></span>

  - <span data-ttu-id="72056-109">グローバル音声ポリシー (製品と共にインストールされる既定の音声ポリシー) の構成方法を決定する。</span><span class="sxs-lookup"><span data-stu-id="72056-109">Determine how you will configure your global voice policy (the default voice policy that is installed with the product).</span></span> <span data-ttu-id="72056-110">このポリシーは、サイトレベルまたはユーザーごとのポリシーを明示的に割り当てられていないすべてのエンタープライズ Voip ユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="72056-110">This policy will apply to all Enterprise Voice users who are not explicitly assigned a site-level or per-user policy.</span></span>

  - <span data-ttu-id="72056-111">必要なサイトレベルの音声ポリシーをすべて識別する。</span><span class="sxs-lookup"><span data-stu-id="72056-111">Identify any site-level voice policies that you might need.</span></span>

  - <span data-ttu-id="72056-112">必要なユーザー単位の音声ポリシーをすべて識別する。</span><span class="sxs-lookup"><span data-stu-id="72056-112">Identify any per-user voice policies that you might need.</span></span>

  - <span data-ttu-id="72056-113">音声ポリシーごとに、有効にする通話機能を決定する。</span><span class="sxs-lookup"><span data-stu-id="72056-113">Decide which call features to enable for each voice policy.</span></span>

  - <span data-ttu-id="72056-114">音声ポリシーごとに、構成する PSTN 使用法レコードを決定する。</span><span class="sxs-lookup"><span data-stu-id="72056-114">Determine what PSTN usage records to configure for each voice policy.</span></span>

<div>

## <a name="voice-policy-scope"></a><span data-ttu-id="72056-115">音声ポリシー スコープ</span><span class="sxs-lookup"><span data-stu-id="72056-115">Voice Policy Scope</span></span>

<span data-ttu-id="72056-116">*音声ポリシー スコープ*により、ポリシーを適用可能な階層レベルが決まります。</span><span class="sxs-lookup"><span data-stu-id="72056-116">*Voice policy scope* determines the hierarchical level at which the policy can be applied.</span></span> <span data-ttu-id="72056-117">Lync Server では、次の範囲レベルで音声ポリシーを構成できます (最も限定的なものから最も一般的なものにリストされています)。</span><span class="sxs-lookup"><span data-stu-id="72056-117">In Lync Server, you can configure voice policies with the following scope levels (listed from the most specific to the most general).</span></span>

  - <span data-ttu-id="72056-p103">**ユーザー音声ポリシー**は、個々のユーザー、グループ、または連絡先オブジェクトに割り当てることができます。これは最下位レベルのポリシーです。ユーザー音声ポリシーを展開することにより、サイトの特定のユーザーまたはグループを対象に機能を有効にし、同じサイトの他のユーザーまたはグループに対しては有効にしないようにすることができます。たとえば、一部の従業員に対しては長距離ダイヤル機能を無効にすることができます。連絡先オブジェクトは、音声ポリシーを割り当てる目的で個々のユーザーとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="72056-p103">**User voice policy** can be assigned to individual users, groups, or contact objects. This is the lowest level policy. User voice policies can be deployed to enable features for certain users or groups at a site, but not for others in the same site. For example, you may want to disable long distance dialing for some employees. For the purpose of assigning a voice policy, a contact object is treated as an individual user.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="72056-123">中央サイト展開に登録されているブランチサイトエンタープライズ Voip ユーザー、または存続可能ブランチアプライアンスに登録されているユーザーに対して、ユーザーの音声ポリシーを展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="72056-123">We recommend that you deploy a user voice policy for branch site Enterprise Voice users who are registered with the central site deployment, or users who are registered on a Survivable Branch Appliance.</span></span>

    
    </div>

  - <span data-ttu-id="72056-p104">**サイト音声ポリシー**は、ユーザー音声ポリシーが割り当てられているユーザー、グループ、または連絡先オブジェクトを除いて、サイト全体に適用されます。サイト音声ポリシーを定義するには、ポリシーを適用するサイトを指定する必要があります。ユーザー音声ポリシーが割り当てられていない場合は、サイト音声ポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="72056-p104">**Site voice policy** applies to an entire site, except for any users, groups, or contact objects that are assigned a user voice policy. To define a site voice policy, you must specify the site to which the policy applies. If a user voice policy is not assigned, the site voice policy is used.</span></span>

  - <span data-ttu-id="72056-127">**グローバル音声ポリシー**は、製品と一緒にインストールされる既定の音声ポリシーです。</span><span class="sxs-lookup"><span data-stu-id="72056-127">**Global voice policy** is the default voice policy that is installed with the product.</span></span> <span data-ttu-id="72056-128">グローバル音声ポリシーは、組織の具体的な必要性を満たすように編集できますが、名前を変更したり、削除したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="72056-128">You can edit the global voice policy to meet the specific needs of your organization, but you cannot rename or delete it.</span></span> <span data-ttu-id="72056-129">この音声ポリシーは、より具体的なスコープで音声ポリシーを構成して割り当てる場合を除いて、展開内のすべてのエンタープライズ Voip ユーザー、グループ、および連絡先オブジェクトに適用されます。</span><span class="sxs-lookup"><span data-stu-id="72056-129">This voice policy applies to all Enterprise Voice users, groups, and contact objects in your deployment unless you configure and assign a voice policy with more specific scope.</span></span> <span data-ttu-id="72056-130">このポリシー全体を無効にする場合は、サイトおよびユーザーのすべてにカスタム ポリシーが割り当てられるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="72056-130">If you want to disable this policy entirely, be sure that all sites and users have custom policies assigned to them.</span></span>

</div>

<div>

## <a name="call-features"></a><span data-ttu-id="72056-131">通話機能</span><span class="sxs-lookup"><span data-stu-id="72056-131">Call Features</span></span>

<span data-ttu-id="72056-132">音声ポリシーごとに、以下の通話機能を有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="72056-132">You can enable or disable the following call features for each voice policy:</span></span>

  - <span data-ttu-id="72056-p106">[**着信の転送**] では、他の電話機やクライアント デバイスに通話を転送できます。既定では有効です。</span><span class="sxs-lookup"><span data-stu-id="72056-p106">**Call forwarding** enables users to forward calls to other phones and client devices. Enabled by default.</span></span>

  - <span data-ttu-id="72056-p107">[**委任**] では、代わりに通話を送受信する他のユーザーを指定できます。既定では有効です。</span><span class="sxs-lookup"><span data-stu-id="72056-p107">**Delegation** enables users to specify other users to send and receive calls on their behalf. Enabled by default.</span></span>

  - <span data-ttu-id="72056-p108">[**通話の転送**] では、他のユーザーに通話を転送できます。既定では有効です。</span><span class="sxs-lookup"><span data-stu-id="72056-p108">**Call transfer** enables users to transfer calls to other users. Enabled by default.</span></span>

  - <span data-ttu-id="72056-p109">[**コール パーク**] では、通話を保留し、別の電話機やクライアントで受けることができます。既定では無効です。</span><span class="sxs-lookup"><span data-stu-id="72056-p109">**Call park** enables users to park calls and then pick up the call from a different phone or client. Disabled by default.</span></span>

  - <span data-ttu-id="72056-p110">**[同時呼び出し]** では、追加の電話機 (携帯電話など) や他のエンドポイント デバイスで、着信の呼び出し音を鳴らすことができます。既定では有効です。</span><span class="sxs-lookup"><span data-stu-id="72056-p110">**Simultaneous ringing** enables incoming calls to ring on an additional phone (for example, a mobile phone) or other endpoint devices. Enabled by default.</span></span>

  - <span data-ttu-id="72056-p111">[**チーム呼び出し**] では、定義したチームのユーザーがチームの他のメンバーの呼び出しに応答できます。既定では有効です。</span><span class="sxs-lookup"><span data-stu-id="72056-p111">**Team call** enables users on a defined team to answer calls for other members of the team. Enabled by default.</span></span>

  - <span data-ttu-id="72056-p112">**[PSTN 再ルート]** では、WAN が混雑していたり利用できない場合に、このポリシーを割り当てられているユーザーが他のエンタープライズ ユーザーに掛けた通話を、公衆交換電話網 (PSTN) で再ルートできます。既定では有効です。</span><span class="sxs-lookup"><span data-stu-id="72056-p112">**PSTN reroute** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the public switched telephone network (PSTN) if the WAN is congested or unavailable. Enabled by default.</span></span>

  - <span data-ttu-id="72056-p113">[**帯域幅ポリシーの上書き**] により管理者は、特定のユーザーに関する通話受付管理ポリシーによる決定を上書きできます。既定では無効です。</span><span class="sxs-lookup"><span data-stu-id="72056-p113">**Bandwidth policy override** enables administrators to override call admission control policy decisions for a particular user. Disabled by default.</span></span>

  - <span data-ttu-id="72056-149">**悪意**のある呼び出しのトレースを使用すると、ユーザーは Lync クライアントを使用して悪意のある電話を報告し、通話詳細記録でそのような呼び出しにフラグを付けます。</span><span class="sxs-lookup"><span data-stu-id="72056-149">**Malicious call tracing** enables users to report malicious calls by using the Lync client, and then flags such calls in the call detail records.</span></span> <span data-ttu-id="72056-150">既定では無効です。</span><span class="sxs-lookup"><span data-stu-id="72056-150">Disabled by default.</span></span>

  - <span data-ttu-id="72056-151">**ボイスメール エスケープ**は、同時呼び出しが構成されている場合で、電話が電源オフ、電池切れ、または圏外になっていて、タイマー値に基づいているときに、通話がユーザーの携帯電話のボイスメール システムにすぐにルーティングされることを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="72056-151">**Voicemail escape** prevents calls from being immediately routed to the user’s mobile phone voicemail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range, and is based on a timer value.</span></span> <span data-ttu-id="72056-152">この設定でタイマーを有効または無効にし、タイマーの値を設定します。</span><span class="sxs-lookup"><span data-stu-id="72056-152">This setting enables and disables the timer and sets the value of the timer.</span></span> <span data-ttu-id="72056-153">この構成は、Lync Server 管理シェルを使用してのみ行うことができます。</span><span class="sxs-lookup"><span data-stu-id="72056-153">It can be configured only by using the Lync Server Management Shell.</span></span> <span data-ttu-id="72056-154">既定では無効です。</span><span class="sxs-lookup"><span data-stu-id="72056-154">Disabled by default.</span></span>

  - <span data-ttu-id="72056-p116">**着信の転送および同時呼び出しの PSTN 使用法**では、管理者は、着信の転送および同時呼び出しに対して音声ポリシーと同じ PSTN 使用法を指定したり、着信の転送および同時呼び出しを内部 Lync ユーザーのみに制限したり、音声ポリシーの PSTN 使用法とは異なるカスタム PSTN 使用法を指定したりすることができます。既定では、着信の転送および同時呼び出しに対して音声ポリシーと同じ PSTN 使用法を使用します。</span><span class="sxs-lookup"><span data-stu-id="72056-p116">**Call forwarding and simultaneous ringing PSTN usages** enables administrators to specify the same PSTN usage as the voice policy for call forwarding and simultaneous ringing, restrict call forwarding and simultaneous ringing to internal Lync users only, or specify a custom PSTN usage that is different from the voice policy’s PSTN usage. The default is to use the same PSTN usage as the voice policy for call forwarding and simultaneous ringing.</span></span>

</div>

<div>

## <a name="pstn-usage-records"></a><span data-ttu-id="72056-157">PSTN 使用法レコード</span><span class="sxs-lookup"><span data-stu-id="72056-157">PSTN Usage Records</span></span>

<span data-ttu-id="72056-158">各音声ポリシーには、1 つ以上の PSTN 使用法レコードが関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="72056-158">Each voice policy should have one or more associated PSTN usage records.</span></span> <span data-ttu-id="72056-159">PSTN 使用法は、同時呼び出しおよび着信の転送のみのための音声ポリシーと関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="72056-159">PSTN usages can be associated with a voice policy for the purpose of simultaneous ringing and call forwarding only.</span></span> <span data-ttu-id="72056-160">PSTN 使用法レコードの計画の詳細については、「 [Lync Server 2013 の pstn 使用法レコード](lync-server-2013-pstn-usage-records.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="72056-160">For details about planning PSTN usage records, see [PSTN usage records in Lync Server 2013](lync-server-2013-pstn-usage-records.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="72056-p118">発信ルーティング機能では、ユーザーとルートの照合時に PSTN 使用法を上位から下位の順に比較するため、PSTN 使用法の順序は重要です。 最初の使用法が通話ルートに一致した場合は、そのルートが使用されます。 一致しない場合、発信ルーティング機能はリスト内の次の PSTN 使用法との照合を、一致が検出されるまで続けます。 事実上、後続の PSTN 使用法は、リストの最初の使用法が使用できない場合のバックアップとなります。</span><span class="sxs-lookup"><span data-stu-id="72056-p118">PSTN usage order is critical because in matching users to routes, the outbound routing functionality compares PSTN usages from top to bottom. If the first usage matches the call route, that route is used. If not, the outbound routing functionality looks at the next PSTN usage on the list and continues until a match is found. In effect, the subsequent PSTN usages provide backup if the first one on the list is unavailable.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

