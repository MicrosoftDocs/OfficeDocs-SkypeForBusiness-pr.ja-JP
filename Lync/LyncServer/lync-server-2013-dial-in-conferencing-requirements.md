---
title: Lync Server 2013 ダイヤルイン会議の要件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Dial-in conferencing requirements
ms:assetid: 9aff949e-3dac-481a-be46-a180c72e8066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398802(v=OCS.15)
ms:contentKeyID: 48184969
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2f4878e81a28b5d51726cb1f3e2dc5c7c5aa0fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833405"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-requirements-in-lync-server-2013"></a><span data-ttu-id="1f235-102">Lync Server 2013 でのダイヤルイン会議の要件</span><span class="sxs-lookup"><span data-stu-id="1f235-102">Dial-in conferencing requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f235-103">_**最終更新日:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="1f235-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="1f235-104">Lync Server 2013 展開プロセスを開始する前に、次のことを計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f235-104">Before you start the Lync Server 2013 deployment process you need to plan for the following:</span></span>

  - <span data-ttu-id="1f235-105">公衆交換電話網 (PSTN) に接続するために使用する構成</span><span class="sxs-lookup"><span data-stu-id="1f235-105">The configuration to use for connecting to the public switched telephone network (PSTN)</span></span>

  - <span data-ttu-id="1f235-106">ダイヤルインアクセス番号にダイヤルイン会議領域を割り当てるための戦略</span><span class="sxs-lookup"><span data-stu-id="1f235-106">Your strategy for assigning dial-in conferencing regions to dial-in access numbers</span></span>

  - <span data-ttu-id="1f235-107">会議ディレクトリを作成するための戦略</span><span class="sxs-lookup"><span data-stu-id="1f235-107">Your strategy for creating conference directories</span></span>

<div>

## <a name="planning-for-dial-in-pstn-connectivity"></a><span data-ttu-id="1f235-108">ダイヤルイン PSTN 接続の計画</span><span class="sxs-lookup"><span data-stu-id="1f235-108">Planning for Dial-in PSTN Connectivity</span></span>

<span data-ttu-id="1f235-109">ダイヤルイン会議には、少なくとも1つの仲介サーバーと少なくとも1つの PSTN ゲートウェイが必要です。</span><span class="sxs-lookup"><span data-stu-id="1f235-109">Dial-in conferencing requires at least one Mediation Server and at least one PSTN gateway.</span></span>

<span data-ttu-id="1f235-110">仲介サーバーは、中央サイトまたはブランチ サイトに展開できます。</span><span class="sxs-lookup"><span data-stu-id="1f235-110">You can deploy a Mediation Server in a central site or in a branch site.</span></span> <span data-ttu-id="1f235-111">中央サイトでは、仲介サーバーをフロントエンド プールまたは Standard Edition サーバー上に併置するか、スタンドアロンのサーバー上またはプールに展開できます。</span><span class="sxs-lookup"><span data-stu-id="1f235-111">In a central site, you can collocate a Mediation Server on a Front End pool or Standard Edition server, or you can deploy it on a stand-alone server or pool.</span></span> <span data-ttu-id="1f235-112">ブランチ サイトでは、仲介サーバーをスタンドアロンのサーバー上か、存続可能ブランチ アプライアンスのコンポーネントとして展開できます。</span><span class="sxs-lookup"><span data-stu-id="1f235-112">In a branch site, you can deploy a Mediation Server on a stand-alone server or as a component of the Survivable Branch Appliance.</span></span>

<span data-ttu-id="1f235-p102">PSTN ゲートウェイは、中央サイトまたはブランチ サイトに展開できます。ブランチ サイトでは、PSTN ゲートウェイは、スタンドアロンの場合と存続可能ブランチ アプライアンスのコンポーネントの場合があります。</span><span class="sxs-lookup"><span data-stu-id="1f235-p102">You can deploy a PSTN gateway in a central site or in a branch site. In a branch site, the PSTN gateway can be stand-alone or a component of the Survivable Branch Appliance.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1f235-115">電話会議サーバーでメディアのバイパスがサポートされていないため、ダイヤルイン会議でメディアのバイパスは使用されません。</span><span class="sxs-lookup"><span data-stu-id="1f235-115">Dial-in conferencing does not use media bypass because A/V Conferencing Server do not support media bypass.</span></span>



</div>

<span data-ttu-id="1f235-116">ダイヤルイン会議での仲介サーバーと PSTN ゲートウェイの構成の計画の詳細については、計画ドキュメントの「 [Lync server 2013 での仲介サーバーのコンポーネントとトポロジ](lync-server-2013-components-and-topologies-for-mediation-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f235-116">For details about planning your configuration for Mediation Server and PSTN gateways for dial-in conferencing, see [Components and topologies for Mediation Server in Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) in the Planning documentation.</span></span>

</div>

<span id="bkmk_PlanningforDialinConferencingRegions"></span>

<div>

## <a name="planning-for-dial-in-conferencing-regions"></a><span data-ttu-id="1f235-117">ダイヤルイン会議領域の計画</span><span class="sxs-lookup"><span data-stu-id="1f235-117">Planning for Dial-in Conferencing Regions</span></span>

<span data-ttu-id="1f235-118">ダイヤルイン構成では、ダイヤルプランとダイヤルイン会議アクセス番号を作成します。</span><span class="sxs-lookup"><span data-stu-id="1f235-118">During dial-in configuration, you create dial plans and dial-in conferencing access numbers.</span></span> <span data-ttu-id="1f235-119">ダイヤルプランとは、電話番号の数字とパターンを指定し、電話番号を標準の E.i 形式 (着信ルーティング用) に変換する正規化ルールのセットです。</span><span class="sxs-lookup"><span data-stu-id="1f235-119">Dial plans are sets of normalization rules that specify the number and pattern of digits in a phone number and translate the phone number into the standard E.164 format for call routing.</span></span> <span data-ttu-id="1f235-120">ダイヤルイン会議アクセス番号は、会議に参加するために参加者が発信する番号です。</span><span class="sxs-lookup"><span data-stu-id="1f235-120">Dial-in conferencing access numbers are the numbers participants call to join a conference.</span></span>

<span data-ttu-id="1f235-121">すべてのダイヤルイン会議アクセス番号を、少なくとも 1 つのダイヤル プランに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f235-121">Every dial-in conferencing access number must be associated with at least one dial plan.</span></span> <span data-ttu-id="1f235-122">ダイヤルイン会議領域は、ダイヤルイン会議アクセス番号をダイヤルプランに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="1f235-122">Dial-in conferencing regions associate a dial-in conferencing access number with its dial plans.</span></span> <span data-ttu-id="1f235-123">ダイヤルプランを設定するときに、ダイヤルイン会議の地域をダイヤルプランに適用するように指定します。</span><span class="sxs-lookup"><span data-stu-id="1f235-123">When you set up a dial plan, you specify the dial-in conferencing region that applies to the dial plan.</span></span> <span data-ttu-id="1f235-124">ダイヤルイン アクセス番号を作成するときには、アクセス番号と適切なダイヤル プランを関連付ける地域を選択します。</span><span class="sxs-lookup"><span data-stu-id="1f235-124">When you create the dial-in access number, you select the regions that associate the access number with the appropriate dial plans.</span></span>

<span data-ttu-id="1f235-125">ダイヤルプランを作成する場合は、ダイヤルプランの範囲 (ユーザー範囲、プールスコープ、またはサイトの範囲) を指定します。</span><span class="sxs-lookup"><span data-stu-id="1f235-125">When you create a dial plan, you specify the scope of the dial plan: user scope, pool scope, or site scope.</span></span> <span data-ttu-id="1f235-126">すべてのユーザーに、そのユーザーに適用される最も狭いスコープからダイヤル プランが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="1f235-126">Every user is assigned the dial plan from the narrowest scope that applies to the user.</span></span> <span data-ttu-id="1f235-127">たとえば、ユーザー レベルのダイヤル プランが適用される場合、ユーザーにはユーザー レベルのダイヤル プランが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="1f235-127">For example, a user is assigned a user-level dial plan, if one applies.</span></span> <span data-ttu-id="1f235-128">ユーザー レベルのダイヤル プランが適用されない場合、そのユーザーにはプール レベルのダイヤル プランが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="1f235-128">If a user-level dial plan does not apply, the user is assigned a pool-level dial plan.</span></span> <span data-ttu-id="1f235-129">プール レベルのダイヤル プランが適用されない場合、そのユーザーにはサイト レベルのダイヤル プランが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="1f235-129">If a pool-level dial plan does not apply, the user is assigned a site-level dial plan.</span></span> <span data-ttu-id="1f235-130">サイト レベルのダイヤル プランが適用されない場合、そのユーザーにはグローバル ダイヤル プランが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="1f235-130">If a site-level dial plan does not apply, the user is assigned the global dial plan.</span></span>

<span data-ttu-id="1f235-p106">ダイヤル プランを構成する前に、地域にどのように名前を指定してその地域をどのように使用するのかを計画することが重要です。 ダイヤルイン会議の地域には、次の考慮事項が適用されます。</span><span class="sxs-lookup"><span data-stu-id="1f235-p106">Before you configure the dial plans, is it important to plan how you want to name and use regions. The following considerations apply to dial-in conferencing regions:</span></span>

  - <span data-ttu-id="1f235-133">地域は通常、1 つのオフィスまたはオフィスのグループに関連付けられた地理的地域です。</span><span class="sxs-lookup"><span data-stu-id="1f235-133">A region is typically a geographical area that is associated with an office or group of offices.</span></span>

  - <span data-ttu-id="1f235-p107">言語をダイヤル アクセス番号に関連付けます。複数の言語が使用されている地理的地域をサポートしている場合、複数の言語をサポートするよう地域をどのように定義するのかを決定する必要があります。たとえば、地理的条件と言語の組み合わせに基づいて複数の言語を定義したり、地理的条件に基づいて 1 つの地域を定義し、各言語に異なるダイヤルイン アクセス番号を付与することができます。</span><span class="sxs-lookup"><span data-stu-id="1f235-p107">Languages are associated with dial-in access numbers. If you support geographical areas that have multiple languages, you should decide how you want to define regions to support the multiple languages. For example, you might define multiple regions based on a combination of geography and language, or you might define a single region based on geography and have a different dial-in access numbers for each language.</span></span>

  - <span data-ttu-id="1f235-137">ユーザーが会議をスケジュールする際、既定では、会議にはそのユーザーのダイヤル プランで指定されている地域が使用されます。</span><span class="sxs-lookup"><span data-stu-id="1f235-137">When a user schedules a meeting, by default the meeting uses the region specified by that user's dial plan.</span></span>

  - <span data-ttu-id="1f235-138">既定では、地域のダイヤルインアクセス番号はすべて、会議出席依頼に含まれています。</span><span class="sxs-lookup"><span data-stu-id="1f235-138">By default, the all of the dial-in access numbers for the region are included in the meeting invitation.</span></span>

  - <span data-ttu-id="1f235-139">明確に認識できるように、地域に名前を指定することが重要です。</span><span class="sxs-lookup"><span data-stu-id="1f235-139">It is important to name regions so that they are clearly recognizable.</span></span> <span data-ttu-id="1f235-140">ユーザーは、地域の名前を使用して会議の地域を変更し、出席依頼に異なるアクセス番号が含まれるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="1f235-140">The user can use the names of the regions to change a meeting's region so that different access numbers are included in the invitation.</span></span> <span data-ttu-id="1f235-141">(ユーザーが Outlook を使用して会議をスケジュールする場合、ユーザーは Lync 2013 用のオンライン会議アドインを使用して地域を変更します)。</span><span class="sxs-lookup"><span data-stu-id="1f235-141">(When users use Outlook to schedule a meeting, the user uses the Online Meeting Add-in for Lync 2013 to change the region).</span></span>

  - <span data-ttu-id="1f235-142">会議にダイヤルインする招待されたユーザーが会議出席依頼で地域のアクセス番号を確認できるよう、地域を設計する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f235-142">Regions should be designed so that any invitee who wants to dial into a conference can see a local access number in the conference invitation.</span></span>

  - <span data-ttu-id="1f235-143">Lync Server 管理シェルコマンドレットを使用して、[ダイヤルイン会議の設定] ページ (および会議の出席依頼に表示される順序) に、地域内のアクセス番号を表示する順序を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="1f235-143">You can configure the order in which access numbers within a region appear on the Dial-in Conferencing Settings page (and, therefore, the order in which they appear in the conference invitation) by using Lync Server Management Shell cmdlets.</span></span>

  - <span data-ttu-id="1f235-144">すべての場所のすべてのユーザーが、任意のダイヤルイン アクセス番号を発信して会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="1f235-144">Any user from any location can call any dial-in access number to join a conference.</span></span>

</div>

<div>

## <a name="planning-for-conference-directories"></a><span data-ttu-id="1f235-145">会議ディレクトリの計画</span><span class="sxs-lookup"><span data-stu-id="1f235-145">Planning for Conference Directories</span></span>

<span data-ttu-id="1f235-146">会議ディレクトリは、Lync 2013 を使っているときに参加者が会議に参加するために使用する英数字の会議 ID と、ダイヤルイン会議の参加者が会議に参加するために使用する電話番号のみの会議 id の間のマッピングを維持します。</span><span class="sxs-lookup"><span data-stu-id="1f235-146">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Lync 2013, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> <span data-ttu-id="1f235-147">電話会議 ID の形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1f235-147">The format of the conference ID is as follows:</span></span>

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

<span data-ttu-id="1f235-148">複数の会議ディレクトリを作成すると、作成する会議の数がよほど多くならない限り電話会議 ID を短く保つことができます。</span><span class="sxs-lookup"><span data-stu-id="1f235-148">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created.</span></span> <span data-ttu-id="1f235-149">ユーザーあたりの電話会議の数が一般的な組織の場合、プール内の 999 ユーザーごとに 1 つの会議ディレクトリを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1f235-149">In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool.</span></span> <span data-ttu-id="1f235-150">このガイドラインを使用すると、通常は会議 Id を小さく抑えることができます。</span><span class="sxs-lookup"><span data-stu-id="1f235-150">Using this guideline the conference IDs can generally be kept small.</span></span> <span data-ttu-id="1f235-151">ただし、(すべてのプールの) 会議ディレクトリの数が 9 を超えると、追加の会議をサポートするために電話会議 ID の番号が長くなります。</span><span class="sxs-lookup"><span data-stu-id="1f235-151">However, once the number of conference directories (across the pools) exceed 9, the Conference ID number will grow to support additional conferences.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1f235-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="1f235-152">See Also</span></span>


[<span data-ttu-id="1f235-153">Lync Server 2013 の仲介サーバーコンポーネント</span><span class="sxs-lookup"><span data-stu-id="1f235-153">Mediation Server component in Lync Server 2013</span></span>](lync-server-2013-mediation-server-component.md)  
[<span data-ttu-id="1f235-154">Lync Server 2013 でのダイヤルプランと正規化ルール</span><span class="sxs-lookup"><span data-stu-id="1f235-154">Dial plans and normalization rules in Lync Server 2013</span></span>](lync-server-2013-dial-plans-and-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

