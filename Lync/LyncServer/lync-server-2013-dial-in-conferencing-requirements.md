---
title: Lync Server 2013 ダイヤルイン会議の要件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing requirements
ms:assetid: 9aff949e-3dac-481a-be46-a180c72e8066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398802(v=OCS.15)
ms:contentKeyID: 48184969
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dcdf30ac0fc35f470e74991b2127cd81b05c5c5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153869"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-requirements-in-lync-server-2013"></a><span data-ttu-id="f6b35-102">Lync Server 2013 でのダイヤルイン会議の要件</span><span class="sxs-lookup"><span data-stu-id="f6b35-102">Dial-in conferencing requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6b35-103">_**トピックの最終更新日:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="f6b35-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="f6b35-104">Lync Server 2013 の展開プロセスを開始する前に、以下のことを計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6b35-104">Before you start the Lync Server 2013 deployment process you need to plan for the following:</span></span>

  - <span data-ttu-id="f6b35-105">公衆交換電話網 (PSTN) への接続に使用する構成</span><span class="sxs-lookup"><span data-stu-id="f6b35-105">The configuration to use for connecting to the public switched telephone network (PSTN)</span></span>

  - <span data-ttu-id="f6b35-106">ダイヤルイン アクセス番号にダイヤルイン会議の地域を割り当てるための戦略</span><span class="sxs-lookup"><span data-stu-id="f6b35-106">Your strategy for assigning dial-in conferencing regions to dial-in access numbers</span></span>

  - <span data-ttu-id="f6b35-107">会議ディレクトリを作成するための戦略</span><span class="sxs-lookup"><span data-stu-id="f6b35-107">Your strategy for creating conference directories</span></span>

<div>

## <a name="planning-for-dial-in-pstn-connectivity"></a><span data-ttu-id="f6b35-108">ダイヤルイン PSTN 接続の計画</span><span class="sxs-lookup"><span data-stu-id="f6b35-108">Planning for Dial-in PSTN Connectivity</span></span>

<span data-ttu-id="f6b35-109">ダイヤルイン会議には、少なくとも1つの仲介サーバーと少なくとも1つの PSTN ゲートウェイが必要です。</span><span class="sxs-lookup"><span data-stu-id="f6b35-109">Dial-in conferencing requires at least one Mediation Server and at least one PSTN gateway.</span></span>

<span data-ttu-id="f6b35-110">仲介サーバーは、中央サイトまたはブランチサイトに展開できます。</span><span class="sxs-lookup"><span data-stu-id="f6b35-110">You can deploy a Mediation Server in a central site or in a branch site.</span></span> <span data-ttu-id="f6b35-111">中央サイトでは、仲介サーバーをフロントエンドプールまたは Standard Edition サーバーに併置したり、スタンドアロンのサーバーまたはプールに展開したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="f6b35-111">In a central site, you can collocate a Mediation Server on a Front End pool or Standard Edition server, or you can deploy it on a stand-alone server or pool.</span></span> <span data-ttu-id="f6b35-112">ブランチサイトでは、仲介サーバーをスタンドアロンサーバーまたは存続可能ブランチアプライアンスのコンポーネントとして展開できます。</span><span class="sxs-lookup"><span data-stu-id="f6b35-112">In a branch site, you can deploy a Mediation Server on a stand-alone server or as a component of the Survivable Branch Appliance.</span></span>

<span data-ttu-id="f6b35-113">PSTN ゲートウェイは、中央サイトまたはブランチ サイトに展開できます。</span><span class="sxs-lookup"><span data-stu-id="f6b35-113">You can deploy a PSTN gateway in a central site or in a branch site.</span></span> <span data-ttu-id="f6b35-114">ブランチサイトでは、PSTN ゲートウェイはスタンドアロンまたは存続可能ブランチアプライアンスのコンポーネントにすることができます。</span><span class="sxs-lookup"><span data-stu-id="f6b35-114">In a branch site, the PSTN gateway can be stand-alone or a component of the Survivable Branch Appliance.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f6b35-115">音声ビデオ会議サーバーがメディアバイパスをサポートしていないため、ダイヤルイン会議でメディアバイパスが使用されることはありません。</span><span class="sxs-lookup"><span data-stu-id="f6b35-115">Dial-in conferencing does not use media bypass because A/V Conferencing Server do not support media bypass.</span></span>



</div>

<span data-ttu-id="f6b35-116">ダイヤルイン会議のための仲介サーバーと PSTN ゲートウェイの構成の計画の詳細については、「計画」のドキュメントの「 [Lync server 2013 の仲介サーバーのコンポーネントとトポロジ](lync-server-2013-components-and-topologies-for-mediation-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6b35-116">For details about planning your configuration for Mediation Server and PSTN gateways for dial-in conferencing, see [Components and topologies for Mediation Server in Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) in the Planning documentation.</span></span>

</div>

<span id="bkmk_PlanningforDialinConferencingRegions"></span>

<div>

## <a name="planning-for-dial-in-conferencing-regions"></a><span data-ttu-id="f6b35-117">ダイヤルイン会議の地域の計画</span><span class="sxs-lookup"><span data-stu-id="f6b35-117">Planning for Dial-in Conferencing Regions</span></span>

<span data-ttu-id="f6b35-p103">ダイヤルイン構成時に、ダイヤル プランとダイヤルイン会議アクセス番号を作成します。 ダイヤル プランは、通話のルーティングのために、電話番号の桁数と数字パターンを指定して電話番号を標準の E.164 形式に変換する、正規化ルールのセットです。 ダイヤルイン会議アクセス番号は、会議に参加するために参加者が発信する番号です。</span><span class="sxs-lookup"><span data-stu-id="f6b35-p103">During dial-in configuration, you create dial plans and dial-in conferencing access numbers. Dial plans are sets of normalization rules that specify the number and pattern of digits in a phone number and translate the phone number into the standard E.164 format for call routing. Dial-in conferencing access numbers are the numbers participants call to join a conference.</span></span>

<span data-ttu-id="f6b35-p104">すべてのダイヤルイン会議アクセス番号を、少なくとも 1 つのダイヤル プランに関連付ける必要があります。ダイヤルイン会議の地域により、ダイヤルイン会議アクセス番号をダイヤル プランに関連付けます。ダイヤル プランを設定するときに、そのダイヤル プランに適用されるダイヤルイン会議の地域を指定します。ダイヤルイン アクセス番号を作成するときに、アクセス番号を該当するダイヤル プランに関連付ける地域を選択します。</span><span class="sxs-lookup"><span data-stu-id="f6b35-p104">Every dial-in conferencing access number must be associated with at least one dial plan. Dial-in conferencing regions associate a dial-in conferencing access number with its dial plans. When you set up a dial plan, you specify the dial-in conferencing region that applies to the dial plan. When you create the dial-in access number, you select the regions that associate the access number with the appropriate dial plans.</span></span>

<span data-ttu-id="f6b35-p105">ダイヤル プランを作成するときに、ダイヤル プランのスコープとして ユーザー スコープ、プール スコープ、またはサイト スコープを指定します。 すべてのユーザーに、そのユーザーに適用される最も狭いスコープからダイヤル プランが割り当てられます。 たとえば、ユーザー レベルのダイヤル プランが適用される場合、ユーザーにはユーザー レベルのダイヤル プランが割り当てらます。 ユーザー レベルのダイヤル プランが適用されない場合、そのユーザーにはプール レベルのダイヤル プランが割り当てられます。 プール レベルのダイヤル プランが適用されない場合、そのユーザーにはサイト レベルのダイヤル プランが割り当てられます。 サイト レベルのダイヤル プランが適用されない場合、そのユーザーにはグローバル ダイヤル プランが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="f6b35-p105">When you create a dial plan, you specify the scope of the dial plan: user scope, pool scope, or site scope. Every user is assigned the dial plan from the narrowest scope that applies to the user. For example, a user is assigned a user-level dial plan, if one applies. If a user-level dial plan does not apply, the user is assigned a pool-level dial plan. If a pool-level dial plan does not apply, the user is assigned a site-level dial plan. If a site-level dial plan does not apply, the user is assigned the global dial plan.</span></span>

<span data-ttu-id="f6b35-p106">ダイヤル プランを構成する前に、地域にどのように名前を指定してその地域をどのように使用するのかを計画することが重要です。 ダイヤルイン会議の地域には、次の考慮事項が適用されます。</span><span class="sxs-lookup"><span data-stu-id="f6b35-p106">Before you configure the dial plans, is it important to plan how you want to name and use regions. The following considerations apply to dial-in conferencing regions:</span></span>

  - <span data-ttu-id="f6b35-133">地域は通常、1 つのオフィスまたはオフィスのグループに関連付けられた地理的地域です。</span><span class="sxs-lookup"><span data-stu-id="f6b35-133">A region is typically a geographical area that is associated with an office or group of offices.</span></span>

  - <span data-ttu-id="f6b35-p107">言語をダイヤル アクセス番号に関連付けます。 複数の言語が使用されている地理的地域をサポートしている場合、複数の言語をサポートするよう地域をどのように定義するのかを決定する必要があります。 たとえば、地理的条件と言語の組み合わせに基づいて複数の言語を定義したり、地理的条件に基づいて 1 つの地域を定義し、各言語に異なるダイヤルイン アクセス番号を付与することができます。</span><span class="sxs-lookup"><span data-stu-id="f6b35-p107">Languages are associated with dial-in access numbers. If you support geographical areas that have multiple languages, you should decide how you want to define regions to support the multiple languages. For example, you might define multiple regions based on a combination of geography and language, or you might define a single region based on geography and have a different dial-in access numbers for each language.</span></span>

  - <span data-ttu-id="f6b35-137">ユーザーが会議をスケジュールする際、既定では、会議にはそのユーザーのダイヤル プランで指定されている地域が使用されます。</span><span class="sxs-lookup"><span data-stu-id="f6b35-137">When a user schedules a meeting, by default the meeting uses the region specified by that user's dial plan.</span></span>

  - <span data-ttu-id="f6b35-138">既定では、その地域のすべてのダイヤルイン アクセス番号が会議出席依頼に含まれます。</span><span class="sxs-lookup"><span data-stu-id="f6b35-138">By default, the all of the dial-in access numbers for the region are included in the meeting invitation.</span></span>

  - <span data-ttu-id="f6b35-139">明確にわかるように、地域名を指定することが重要です。</span><span class="sxs-lookup"><span data-stu-id="f6b35-139">It is important to name regions so that they are clearly recognizable.</span></span> <span data-ttu-id="f6b35-140">ユーザーは地域の名前を使用して会議の地域を変更し、招待状に異なるアクセス番号が含まれるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="f6b35-140">The user can use the names of the regions to change a meeting's region so that different access numbers are included in the invitation.</span></span> <span data-ttu-id="f6b35-141">(ユーザーが Outlook を使用して会議をスケジュールする場合、ユーザーは Lync 2013 用オンラインミーティングアドインを使用して地域を変更します)。</span><span class="sxs-lookup"><span data-stu-id="f6b35-141">(When users use Outlook to schedule a meeting, the user uses the Online Meeting Add-in for Lync 2013 to change the region).</span></span>

  - <span data-ttu-id="f6b35-142">会議にダイヤルインする招待されたユーザーが会議出席依頼で地域のアクセス番号を確認できるよう、地域を設計する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6b35-142">Regions should be designed so that any invitee who wants to dial into a conference can see a local access number in the conference invitation.</span></span>

  - <span data-ttu-id="f6b35-143">Lync Server 管理シェルコマンドレットを使用すると、[ダイヤルイン会議の設定] ページ (つまり、会議出席依頼に表示される順序) に、地域内のアクセス番号が表示される順序を構成できます。</span><span class="sxs-lookup"><span data-stu-id="f6b35-143">You can configure the order in which access numbers within a region appear on the Dial-in Conferencing Settings page (and, therefore, the order in which they appear in the conference invitation) by using Lync Server Management Shell cmdlets.</span></span>

  - <span data-ttu-id="f6b35-144">すべての場所のすべてのユーザーが、任意のダイヤルイン アクセス番号を発信して会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="f6b35-144">Any user from any location can call any dial-in access number to join a conference.</span></span>

</div>

<div>

## <a name="planning-for-conference-directories"></a><span data-ttu-id="f6b35-145">会議ディレクトリの計画</span><span class="sxs-lookup"><span data-stu-id="f6b35-145">Planning for Conference Directories</span></span>

<span data-ttu-id="f6b35-146">会議ディレクトリは、Lync 2013 を使用するときに参加者が会議への参加に使用する英数字のミーティング ID と、ダイヤルイン会議の参加者が会議に参加するために使用する数字のみの会議 id のマッピングを維持します。</span><span class="sxs-lookup"><span data-stu-id="f6b35-146">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Lync 2013, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> <span data-ttu-id="f6b35-147">電話会議 ID の形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f6b35-147">The format of the conference ID is as follows:</span></span>

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

<span data-ttu-id="f6b35-p110">複数の会議ディレクトリを作成すると、作成する会議の数がよほど多くならない限り電話会議 ID を短く保つことができます。ユーザーあたりの電話会議の数が一般的な組織の場合、プール内の 999 ユーザーごとに 1 つの会議ディレクトリを作成することをお勧めします。このガイドラインを使用すると、一般に電話会議 ID が短く保たれます。ただし、(すべてのプールの) 会議ディレクトリの数が 9 を超えると、追加の会議をサポートするために電話会議 ID の番号が長くなります。</span><span class="sxs-lookup"><span data-stu-id="f6b35-p110">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created. In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool. Using this guideline the conference IDs can generally be kept small. However, once the number of conference directories (across the pools) exceed 9, the Conference ID number will grow to support additional conferences.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f6b35-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="f6b35-152">See Also</span></span>


[<span data-ttu-id="f6b35-153">Lync Server 2013 の仲介サーバーコンポーネント</span><span class="sxs-lookup"><span data-stu-id="f6b35-153">Mediation Server component in Lync Server 2013</span></span>](lync-server-2013-mediation-server-component.md)  
[<span data-ttu-id="f6b35-154">Lync Server 2013 のダイヤルプランと正規化ルール</span><span class="sxs-lookup"><span data-stu-id="f6b35-154">Dial plans and normalization rules in Lync Server 2013</span></span>](lync-server-2013-dial-plans-and-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

