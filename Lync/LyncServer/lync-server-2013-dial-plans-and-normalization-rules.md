---
title: 'Lync Server 2013: ダイヤルプランと正規化ルール'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial plans and normalization rules
ms:assetid: fde45195-6eb4-403c-9094-57df7fc0bd2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413082(v=OCS.15)
ms:contentKeyID: 48185960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edd44cbb1e54e811fc646a99362b18a284376953
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213423"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dial-plans-and-normalization-rules-in-lync-server-2013"></a><span data-ttu-id="4eeca-102">Lync Server 2013 のダイヤルプランと正規化ルール</span><span class="sxs-lookup"><span data-stu-id="4eeca-102">Dial plans and normalization rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4eeca-103">_**トピックの最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="4eeca-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="4eeca-104">ダイヤル プランとは、電話番号の承認と通話のルーティングを目的として、特定の場所、個々のユーザー、または連絡先オブジェクトの電話番号を 1 つの標準形式 (E.164) に変換する正規化ルールのセットに名前を付けたものです。</span><span class="sxs-lookup"><span data-stu-id="4eeca-104">A dial plan is a named set of normalization rules that translates phone numbers for a named location, individual user, or contact object into a single standard (E.164) format for purposes of phone authorization and call routing.</span></span>

<span data-ttu-id="4eeca-105">正規化ルールは、さまざまな形式で表現された電話番号を指定された各場所、ユーザー、または連絡先オブジェクトにルーティングする方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="4eeca-105">Normalization rules define how phone numbers expressed in various formats are to be routed for each specified location, user, or contact object.</span></span> <span data-ttu-id="4eeca-106">ダイヤル元の場所や、呼び出しを行った人物または連絡先オブジェクトによって、同じダイヤル文字列が異なる方法で解釈および変換される場合があります。</span><span class="sxs-lookup"><span data-stu-id="4eeca-106">The same dial string may be interpreted and translated differently, depending on the location from which it is dialed and the person or contact object making the call.</span></span>

<div>

## <a name="dial-plan-scope"></a><span data-ttu-id="4eeca-107">ダイヤル プランのスコープ</span><span class="sxs-lookup"><span data-stu-id="4eeca-107">Dial Plan Scope</span></span>

<span data-ttu-id="4eeca-108">ダイヤル プランの*スコープ*によって、ダイヤル プランを適用できる階層レベルが決まります。</span><span class="sxs-lookup"><span data-stu-id="4eeca-108">A dial plan’s *scope* determines the hierarchical level at which the dial plan can be applied.</span></span> <span data-ttu-id="4eeca-109">Lync Server では、ユーザーに特定のユーザーごとのダイヤルプランを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="4eeca-109">In Lync Server, a user can be assigned a specific per-user dial plan.</span></span> <span data-ttu-id="4eeca-110">ユーザーのダイヤル プランが割り当てられていない場合は、レジストラー プールのダイヤル プランが適用されます。</span><span class="sxs-lookup"><span data-stu-id="4eeca-110">If a user dial plan is not assigned, the Registrar pool dial plan is applied.</span></span> <span data-ttu-id="4eeca-111">レジストラー プールのダイヤル プランがない場合は、サイトのダイヤル プランが適用されます。</span><span class="sxs-lookup"><span data-stu-id="4eeca-111">If there is no Registrar pool dial plan, the site dial plan is applied.</span></span> <span data-ttu-id="4eeca-112">ユーザーに適用可能な他のダイヤル プランがない場合は、最後にグローバル ダイヤル プランが適用されます。</span><span class="sxs-lookup"><span data-stu-id="4eeca-112">Finally, if there is no other dial plan applicable to the user, the global dial plan is applied.</span></span>

<span data-ttu-id="4eeca-113">クライアントは、ユーザーが Lync Server にログオンするときに提供されるインバンドプロビジョニング設定によって、ダイヤルプランのスコープレベルを取得します。</span><span class="sxs-lookup"><span data-stu-id="4eeca-113">Clients obtain dial plan scope levels through in-band provisioning settings that are provided when users log on to Lync Server.</span></span> <span data-ttu-id="4eeca-114">管理者は、Lync Server コントロールパネルを使用して、ダイヤルプランのスコープレベルの管理と割り当てを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="4eeca-114">As the administrator, you can manage and assign dial plan scope levels by using Lync Server Control Panel.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4eeca-115">サービスレベルの公衆交換電話網 (PSTN) ゲートウェイのダイヤルプランは、特定のゲートウェイからの着信呼び出しに適用されます。</span><span class="sxs-lookup"><span data-stu-id="4eeca-115">The service level public switched telephone network (PSTN) gateway dial plan is applied to the incoming calls from a particular gateway.</span></span>



</div>

<span data-ttu-id="4eeca-116">ダイヤル プランのスコープ レベルは、次のように定義されます。</span><span class="sxs-lookup"><span data-stu-id="4eeca-116">Dial plan scope levels are defined as follows:</span></span>

  - <span data-ttu-id="4eeca-117">**ユーザーダイヤルプラン:** 個別のユーザー、グループ、または連絡先オブジェクトに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="4eeca-117">**User dial plan:** Can be assigned to individual users, groups, or contact objects.</span></span> <span data-ttu-id="4eeca-118">音声アプリケーションは、電話コンテキストがユーザー既定に設定された通話を受信したときに、ユーザーごとのダイヤルプランを検索できます。</span><span class="sxs-lookup"><span data-stu-id="4eeca-118">Voice applications can look up a per-user dial plan when a call is received with the phone-context set to user-default.</span></span> <span data-ttu-id="4eeca-119">ダイヤルプランを割り当てる目的で、連絡先オブジェクトは個別のユーザーとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="4eeca-119">For the purpose of assigning a dial plan, a contact object is treated as an individual user.</span></span>

  - <span data-ttu-id="4eeca-120">**プールダイヤルプラン:** は、トポロジ内の PSTN ゲートウェイまたはレジストラーのサービスレベルで作成できます。</span><span class="sxs-lookup"><span data-stu-id="4eeca-120">**Pool dial plan:** Can be created at the service level for any PSTN gateway or Registrar in your topology.</span></span> <span data-ttu-id="4eeca-121">プール ダイヤル プランを定義するには、ダイヤル プランを適用する特定のサービス (PSTN ゲートウェイまたはレジストラー プール) を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4eeca-121">To define a pool dial plan, you must specify the particular service (PSTN gateway or Registrar pool) to which the dial plan applies.</span></span>

  - <span data-ttu-id="4eeca-122">**サイトダイヤルプラン:** プールダイヤルプランまたはユーザーダイヤルプランが割り当てられているユーザー、グループ、または連絡先オブジェクトを除く、サイト全体に対して作成できます。</span><span class="sxs-lookup"><span data-stu-id="4eeca-122">**Site dial plan:** Can be created for an entire site, except for any users, groups, or contact objects that are assigned a pool dial plan or user dial plan.</span></span> <span data-ttu-id="4eeca-123">サイト ダイヤル プランを定義するには、ダイヤル プランを適用するサイトを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4eeca-123">To define a site dial plan, you must specify the site to which the dial plan applies.</span></span>

  - <span data-ttu-id="4eeca-124">**グローバルダイヤルプラン:** 製品と共にインストールされる既定のダイヤルプラン。</span><span class="sxs-lookup"><span data-stu-id="4eeca-124">**Global dial plan:** The default dial plan installed with the product.</span></span> <span data-ttu-id="4eeca-125">グローバル ダイヤル プランは、編集はできますが削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="4eeca-125">You can edit the global dial plan, but you cannot delete it.</span></span> <span data-ttu-id="4eeca-126">このダイヤルプランは、より具体的なスコープを持つダイヤルプランを構成して割り当てる場合を除き、展開内のすべてのエンタープライズ Voip ユーザー、グループ、および連絡先オブジェクトに適用されます。</span><span class="sxs-lookup"><span data-stu-id="4eeca-126">This dial plan applies to all Enterprise Voice users, groups, and contact objects in your deployment, unless you configure and assign a dial plan with a more specific scope.</span></span>

</div>

<div>

## <a name="planning-for-dial-plans"></a><span data-ttu-id="4eeca-127">ダイヤル プランの計画</span><span class="sxs-lookup"><span data-stu-id="4eeca-127">Planning for Dial Plans</span></span>

<span data-ttu-id="4eeca-128">ダイヤルプランを計画するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="4eeca-128">To plan a dial plan, follow these steps:</span></span>

  - <span data-ttu-id="4eeca-129">組織に office があるすべてのロケールを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="4eeca-129">List all the locales in which your organization has an office.</span></span>
    
    <span data-ttu-id="4eeca-130">リストは、最新の状態にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4eeca-130">The list must be up-to-date and complete.</span></span> <span data-ttu-id="4eeca-131">また、組織の変化に合わせて改訂する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4eeca-131">It will need to be revised as company organization evolves.</span></span> <span data-ttu-id="4eeca-132">多数の小規模な支社を持つ大規模な多国籍企業では、この作業は時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="4eeca-132">In a large, multinational company with numerous small branch offices, this can be a time-consuming task.</span></span>

  - <span data-ttu-id="4eeca-133">各サイトの有効な番号パターンを特定します。</span><span class="sxs-lookup"><span data-stu-id="4eeca-133">Identify valid number patterns for each site.</span></span>
    
    <span data-ttu-id="4eeca-p109">ダイヤル プランの計画で最も時間がかかるのは、それぞれのサイトの有効な番号パターンを特定することです。 あるダイヤル プラン用に記述した正規化ルールを他のダイヤル プランにコピーできる場合があります (特に、対応しているサイトが同じ国/地域または大陸にある場合)。 これ以外の場合でも、あるダイヤル プランの番号を少し変更すれば他のダイヤル プランに十分使用できる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4eeca-p109">The most time-consuming part of planning your dial plans is identifying the valid number patterns for each site. In some cases, you may be able to copy normalization rules that you have written for one dial plan to other dial plans, especially if the corresponding sites are within the same country/region or even continent. In other cases, small changes to numbers in one dial plan may be enough to use them in other dial plans.</span></span>

  - <span data-ttu-id="4eeca-137">ダイヤルプランの名前付けのための、組織全体のスキームを開発します。</span><span class="sxs-lookup"><span data-stu-id="4eeca-137">Develop an organization-wide scheme for naming dial plans.</span></span>
    
    <span data-ttu-id="4eeca-138">標準の名前付けスキームを採用することで、組織間の一貫性を保ち、メンテナンスと更新を簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="4eeca-138">Adopting a standard naming scheme assures consistency across an organization and makes maintenance and updates easier.</span></span>

  - <span data-ttu-id="4eeca-139">1つの場所に複数のダイヤルプランが必要かどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="4eeca-139">Decide whether multiple dial plans are required for a single location.</span></span>
    
    <span data-ttu-id="4eeca-140">組織が複数の場所で単一のダイヤルプランを保有している場合は、構内交換機 (PBX) から移行していて、既存の内線番号を保持する必要があるエンタープライズ Voip ユーザー向けに、別のダイヤルプランを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4eeca-140">If your organization maintains a single dial plan across multiple locations, you may still need to create a separate dial plan for Enterprise Voice users who are migrating from a private branch exchange (PBX) and who need to have their existing extensions retained.</span></span>

  - <span data-ttu-id="4eeca-141">ユーザーごとのダイヤルプランが必要かどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="4eeca-141">Decide whether per-user dial plans are required.</span></span> <span data-ttu-id="4eeca-142">たとえば、中央サイトに登録されているブランチサイトにユーザーがいる場合、または存続可能 Branch アプライアンスに登録されているユーザーがいる場合は、ユーザーごとのダイヤルプランや正規化ルールを使用して、そのようなユーザーに対して特別なダイヤルシナリオを検討できます。.</span><span class="sxs-lookup"><span data-stu-id="4eeca-142">For example, if you have users at a branch site who are registered with the central site or if you have users who are registered on a Survivable Branch Appliance, you can consider special dialing scenarios for such users using per-user dial plans and normalization rules.</span></span> <span data-ttu-id="4eeca-143">詳細については、「 [Lync Server 2013 のブランチサイトの復元要件](lync-server-2013-branch-site-resiliency-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4eeca-143">For details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).</span></span>

  - <span data-ttu-id="4eeca-144">ダイヤルプランのスコープを決定します (このトピックで前述したとおり)。</span><span class="sxs-lookup"><span data-stu-id="4eeca-144">Determine dial plan scope (as previously described in this topic).</span></span>

<span data-ttu-id="4eeca-145">ダイヤルプランを作成するには、Lync Server コントロールパネルまたは Lync Server 管理シェルを使用して、必要に応じて以下のフィールドに値を指定します。</span><span class="sxs-lookup"><span data-stu-id="4eeca-145">To create a dial plan, you specify values in the following fields, as required, by using Lync Server Control Panel or Lync Server Management Shell.</span></span>

<div>

## <a name="name-and-simple-name"></a><span data-ttu-id="4eeca-146">名前および簡単な名前</span><span class="sxs-lookup"><span data-stu-id="4eeca-146">Name and Simple Name</span></span>

<span data-ttu-id="4eeca-147">ユーザーダイヤルプランの場合は、ダイヤルプランを割り当てるユーザー、グループ、または連絡先オブジェクトを識別するわかりやすい名前を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4eeca-147">For user dial plans, you should specify a descriptive name that identifies the users, groups, or contact objects to which the dial plan will be assigned.</span></span> <span data-ttu-id="4eeca-148">サイト ダイヤル プランの場合、[名前] フィールドにサイト名が事前に入力されており、変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="4eeca-148">For site dial plans, the Name field is prepopulated with the site name and cannot be changed.</span></span> <span data-ttu-id="4eeca-149">プールダイヤルプランの場合、[名前] フィールドに PSTN ゲートウェイまたはフロントエンドプールの完全修飾ドメイン名 (FQDN) が事前に設定されており、変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="4eeca-149">For pool dial plans, the Name field is prepopulated with the PSTN gateway or Front End pool fully qualified domain name (FQDN) and cannot be changed.</span></span>

<span data-ttu-id="4eeca-150">ダイヤル プランの*簡単な名前*には、ダイヤル プラン名を使用した文字列が事前に入力されています。</span><span class="sxs-lookup"><span data-stu-id="4eeca-150">The dial plan *Simple Name* is prepopulated with a string that is derived from the dial plan name.</span></span> <span data-ttu-id="4eeca-151">[簡易名] フィールドは編集できます。これにより、ダイヤルプランのわかりやすい名前付け規則を作成できます。</span><span class="sxs-lookup"><span data-stu-id="4eeca-151">The Simple Name field is editable, which enables you to create a more descriptive naming convention for your dial plans.</span></span> <span data-ttu-id="4eeca-152">*簡単な名前*の値を空にすることはできず、一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="4eeca-152">The *Simple Name* value cannot be empty and must be unique.</span></span> <span data-ttu-id="4eeca-153">ベストプラクティスとして、組織全体の名前付け規則を作成し、すべてのサイトとユーザーに対してこの規則を一貫して使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4eeca-153">A best practice is to develop a naming convention for your entire organization and then use this convention consistently across all sites and users.</span></span>

</div>

<div>

## <a name="description"></a><span data-ttu-id="4eeca-154">説明</span><span class="sxs-lookup"><span data-stu-id="4eeca-154">Description</span></span>

<span data-ttu-id="4eeca-p113">対応するダイヤル プランが適用される地理的な場所の、一般的でわかりやすい名前を入力することをお勧めします。 たとえば、ダイヤル プランの名前が London.Contoso.com である場合、説明を London とすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4eeca-p113">We recommend that you type the common, recognizable name of the geographic location to which the corresponding dial plan applies. For example, if the dial plan name is London.Contoso.com, the recommended description would be London.</span></span>

</div>

<div>

## <a name="dial-in-conferencing-region"></a><span data-ttu-id="4eeca-157">ダイヤルイン会議の地域</span><span class="sxs-lookup"><span data-stu-id="4eeca-157">Dial-in Conferencing Region</span></span>

<span data-ttu-id="4eeca-158">ダイヤルイン会議を展開している場合、ダイヤルイン会議の地域を指定し、ダイヤルイン会議のアクセス番号をダイヤル プランと関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="4eeca-158">If you are deploying dial-in conferencing, you will need to specify a dial-in conferencing region to associate dial-in conferencing access numbers with a dial plan.</span></span>

</div>

<div>

## <a name="external-access-prefix"></a><span data-ttu-id="4eeca-159">外部アクセス プレフィックス</span><span class="sxs-lookup"><span data-stu-id="4eeca-159">External Access Prefix</span></span>

<span data-ttu-id="4eeca-160">外部の行を取得するためにユーザーが1つまた\#は\*複数の追加の数字 (9 など) をダイヤルする必要がある場合は、最大4文字 (,, および 0-9) の外部アクセスプレフィックスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="4eeca-160">You can specify an external access prefix of up to four characters (\#, \*, and 0-9) if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4eeca-161">外部アクセス プレフィックスを指定する場合に、プレフィックスに対応するために追加の正規化ルールを作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4eeca-161">If you specify an external access prefix, you do not need to create an additional normalization rule to accommodate the prefix.</span></span>



</div>

</div>

</div>

<div>

## <a name="normalization-rules"></a><span data-ttu-id="4eeca-162">正規化ルール</span><span class="sxs-lookup"><span data-stu-id="4eeca-162">Normalization Rules</span></span>

<span data-ttu-id="4eeca-163">正規化ルールは、さまざまな形式で表現される電話番号を、名前付きの場所にルーティングする方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="4eeca-163">Normalization rules define how phone numbers expressed in various formats are to be routed for the named location.</span></span> <span data-ttu-id="4eeca-164">同じ数値文字列は、ダイヤル元のロケールに応じて、異なる方法で解釈および変換される場合があります。</span><span class="sxs-lookup"><span data-stu-id="4eeca-164">The same number string may be interpreted and translated differently, depending on the locale from which it is dialed.</span></span> <span data-ttu-id="4eeca-165">ユーザーが連絡先リストに電話番号を入力する際にさまざまな形式を使用できるため、通話のルーティングに正規化ルールが必要です。</span><span class="sxs-lookup"><span data-stu-id="4eeca-165">Normalization rules are necessary for call routing because users can, and do, use various formats when entering phone numbers in their Contacts lists.</span></span>

<span data-ttu-id="4eeca-166">ユーザーが指定した電話番号を正規化すると、次のタスクを容易にする一貫した形式が提供されます。</span><span class="sxs-lookup"><span data-stu-id="4eeca-166">Normalizing user-supplied phone numbers provides a consistent format that facilitates the following tasks:</span></span>

  - <span data-ttu-id="4eeca-167">ダイヤル番号を目的の受信者の SIP URI と一致させます。</span><span class="sxs-lookup"><span data-stu-id="4eeca-167">Match a dialed number to the intended recipient’s SIP-URI.</span></span>

  - <span data-ttu-id="4eeca-168">発信者にダイヤル承認ルールを適用します。</span><span class="sxs-lookup"><span data-stu-id="4eeca-168">Apply dialing authorization rules to the calling party.</span></span>

<span data-ttu-id="4eeca-169">次の番号フィールドでは、正規化ルールの考慮が必要になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4eeca-169">The following number fields are among those that your normalization rules may need to account for:</span></span>

  - <span data-ttu-id="4eeca-170">ダイヤル プラン</span><span class="sxs-lookup"><span data-stu-id="4eeca-170">Dial plan</span></span>

  - <span data-ttu-id="4eeca-171">国番号</span><span class="sxs-lookup"><span data-stu-id="4eeca-171">Country code</span></span>

  - <span data-ttu-id="4eeca-172">市外局番</span><span class="sxs-lookup"><span data-stu-id="4eeca-172">Area code</span></span>

  - <span data-ttu-id="4eeca-173">内線番号の長さ</span><span class="sxs-lookup"><span data-stu-id="4eeca-173">Length of extension</span></span>

  - <span data-ttu-id="4eeca-174">サイトのプレフィックス</span><span class="sxs-lookup"><span data-stu-id="4eeca-174">Site prefix</span></span>

<div>

## <a name="creating-normalization-rules"></a><span data-ttu-id="4eeca-175">正規化ルールの作成</span><span class="sxs-lookup"><span data-stu-id="4eeca-175">Creating Normalization Rules</span></span>

<span data-ttu-id="4eeca-176">正規化ルールは、.NET Framework 正規表現を使用して、逆引き番号検索を実行するために、サーバーがダイヤル文字列を e.164 形式に変換するために使用する数値一致パターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="4eeca-176">Normalization rules use .NET Framework regular expressions to specify numeric match patterns that the server uses to translate dial strings to E.164 format for the purpose of performing reverse number lookup.</span></span> <span data-ttu-id="4eeca-177">Lync Server コントロールパネルで正規化ルールを作成するには、式を手動で入力するか、一致するダイヤル文字列の先頭の数字と長さを入力して、Lync Server コントロールパネルで対応する正規表現。</span><span class="sxs-lookup"><span data-stu-id="4eeca-177">You create normalization rules in the Lync Server Control Panel either by entering the expressions manually, or by entering the starting digits and the length of the dial strings to be matched and letting the Lync Server Control Panel generate the corresponding regular expression for you.</span></span> <span data-ttu-id="4eeca-178">完了したら、テスト番号を入力して、正規化ルールが期待どおりに動作するかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="4eeca-178">Either way, when you finish, you can enter a test number to verify that the normalization rule works as expected.</span></span>

<span data-ttu-id="4eeca-179">.NET Framework の正規表現の使用の詳細については、「」の[https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927)「.Net Framework 正規表現」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4eeca-179">For details about using .NET Framework regular expressions, see ".NET Framework Regular Expressions" at [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

</div>

<span id="BKMK_SampleNormalizationRules"></span>

<div>

## <a name="sample-normalization-rules"></a><span data-ttu-id="4eeca-180">正規化ルールの例</span><span class="sxs-lookup"><span data-stu-id="4eeca-180">Sample Normalization Rules</span></span>

<span data-ttu-id="4eeca-p116">次の表は、.NET Framework 正規表現で記述された正規化ルールの例です。 ここに示すのは単なる例であり、ご自分の正規化ルールをこのとおりに作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4eeca-p116">The following table shows sample normalization rules that are written as .NET Framework regular expressions. The samples are examples only and are not meant to be a prescriptive reference for creating your own normalization rules.</span></span>

### <a name="table-1normalization-rules-using-net-framework-regular-expressions"></a><span data-ttu-id="4eeca-183">表 1. .NET Framework 正規表現を使用した正規化ルール</span><span class="sxs-lookup"><span data-stu-id="4eeca-183">Table 1.Normalization Rules Using .NET Framework Regular Expressions</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4eeca-184">ルール名</span><span class="sxs-lookup"><span data-stu-id="4eeca-184">Rule name</span></span></th>
<th><span data-ttu-id="4eeca-185">説明</span><span class="sxs-lookup"><span data-stu-id="4eeca-185">Description</span></span></th>
<th><span data-ttu-id="4eeca-186">番号のパターン</span><span class="sxs-lookup"><span data-stu-id="4eeca-186">Number pattern</span></span></th>
<th><span data-ttu-id="4eeca-187">翻訳</span><span class="sxs-lookup"><span data-stu-id="4eeca-187">Translation</span></span></th>
<th><span data-ttu-id="4eeca-188">例</span><span class="sxs-lookup"><span data-stu-id="4eeca-188">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4eeca-189">4digitExtension</span><span class="sxs-lookup"><span data-stu-id="4eeca-189">4digitExtension</span></span></p></td>
<td><p><span data-ttu-id="4eeca-190">4 桁の内線番号を変換します。</span><span class="sxs-lookup"><span data-stu-id="4eeca-190">Translates 4-digit extensions</span></span></p></td>
<td><p><span data-ttu-id="4eeca-191">^ (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="4eeca-191">^(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="4eeca-192">+ 1425555 $ 1</span><span class="sxs-lookup"><span data-stu-id="4eeca-192">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="4eeca-193">0100 が +14255550100 に変換されます。</span><span class="sxs-lookup"><span data-stu-id="4eeca-193">0100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4eeca-194">5digitExtension</span><span class="sxs-lookup"><span data-stu-id="4eeca-194">5digitExtension</span></span></p></td>
<td><p><span data-ttu-id="4eeca-195">5 桁の内線番号を変換します。</span><span class="sxs-lookup"><span data-stu-id="4eeca-195">Translates 5-digit extensions</span></span></p></td>
<td><p><span data-ttu-id="4eeca-196">^ 5 (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="4eeca-196">^5(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="4eeca-197">+ 1425555 $ 1</span><span class="sxs-lookup"><span data-stu-id="4eeca-197">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="4eeca-198">50100 が +14255550100 に変換されます。</span><span class="sxs-lookup"><span data-stu-id="4eeca-198">50100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4eeca-199">7digitcallingRedmond</span><span class="sxs-lookup"><span data-stu-id="4eeca-199">7digitcallingRedmond</span></span></p></td>
<td><p><span data-ttu-id="4eeca-200">7 桁の番号を Redmond の電話番号に変換します。</span><span class="sxs-lookup"><span data-stu-id="4eeca-200">Translates 7-digit numbers to Redmond local numbers</span></span></p></td>
<td><p><span data-ttu-id="4eeca-201">^ (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="4eeca-201">^(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="4eeca-202">+ 1425 $ 1</span><span class="sxs-lookup"><span data-stu-id="4eeca-202">+1425$1</span></span></p></td>
<td><p><span data-ttu-id="4eeca-203">5550100 が +14255550100 に変換されます。</span><span class="sxs-lookup"><span data-stu-id="4eeca-203">5550100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4eeca-204">7digitcallingDallas</span><span class="sxs-lookup"><span data-stu-id="4eeca-204">7digitcallingDallas</span></span></p></td>
<td><p><span data-ttu-id="4eeca-205">7 桁の番号を Dallas の電話番号に変換します。</span><span class="sxs-lookup"><span data-stu-id="4eeca-205">Translates 7-digit numbers to Dallas local numbers</span></span></p></td>
<td><p><span data-ttu-id="4eeca-206">^ (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="4eeca-206">^(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="4eeca-207">+ 1972 $ 1</span><span class="sxs-lookup"><span data-stu-id="4eeca-207">+1972$1</span></span></p></td>
<td><p><span data-ttu-id="4eeca-208">5550100 が +19725550100 に変換されます。</span><span class="sxs-lookup"><span data-stu-id="4eeca-208">5550100 is translated to +19725550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4eeca-209">10digitcallingUS</span><span class="sxs-lookup"><span data-stu-id="4eeca-209">10digitcallingUS</span></span></p></td>
<td><p><span data-ttu-id="4eeca-210">米国の 10 桁の番号を変換します。</span><span class="sxs-lookup"><span data-stu-id="4eeca-210">Translates 10-digit numbers in the United States</span></span></p></td>
<td><p><span data-ttu-id="4eeca-211">^ (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="4eeca-211">^(\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="4eeca-212">+ 1 $ 1</span><span class="sxs-lookup"><span data-stu-id="4eeca-212">+1$1</span></span></p></td>
<td><p><span data-ttu-id="4eeca-213">2065550100 が +12065550100 に変換されます。</span><span class="sxs-lookup"><span data-stu-id="4eeca-213">2065550100 is translated to +12065550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4eeca-214">LDCallingUS</span><span class="sxs-lookup"><span data-stu-id="4eeca-214">LDCallingUS</span></span></p></td>
<td><p><span data-ttu-id="4eeca-215">米国の長距離プレフィックス付きの番号を変換します。</span><span class="sxs-lookup"><span data-stu-id="4eeca-215">Translates numbers with long distance prefixes in the United States</span></span></p></td>
<td><p><span data-ttu-id="4eeca-216">^ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="4eeca-216">^1(\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="4eeca-217">+ $1</span><span class="sxs-lookup"><span data-stu-id="4eeca-217">+$1</span></span></p></td>
<td><p><span data-ttu-id="4eeca-218">12145550100 が +2145550100 に変換されます。</span><span class="sxs-lookup"><span data-stu-id="4eeca-218">12145550100 is translated to +2145550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4eeca-219">IntlCallingUS</span><span class="sxs-lookup"><span data-stu-id="4eeca-219">IntlCallingUS</span></span></p></td>
<td><p><span data-ttu-id="4eeca-220">米国の国際プレフィックス付きの番号を変換します。</span><span class="sxs-lookup"><span data-stu-id="4eeca-220">Translates numbers with international prefixes in the United States</span></span></p></td>
<td><p><span data-ttu-id="4eeca-221">^ 011 (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="4eeca-221">^011(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="4eeca-222">+ $1</span><span class="sxs-lookup"><span data-stu-id="4eeca-222">+$1</span></span></p></td>
<td><p><span data-ttu-id="4eeca-223">01191445550100 が +91445550100 に変換されます。</span><span class="sxs-lookup"><span data-stu-id="4eeca-223">01191445550100 is translated to +91445550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4eeca-224">RedmondOperator</span><span class="sxs-lookup"><span data-stu-id="4eeca-224">RedmondOperator</span></span></p></td>
<td><p><span data-ttu-id="4eeca-225">0 を Redmond のオペレータ呼び出し番号に変換します。</span><span class="sxs-lookup"><span data-stu-id="4eeca-225">Translates 0 to Redmond Operator</span></span></p></td>
<td><p><span data-ttu-id="4eeca-226">^ $0</span><span class="sxs-lookup"><span data-stu-id="4eeca-226">^0$</span></span></p></td>
<td><p><span data-ttu-id="4eeca-227">+ 14255550100</span><span class="sxs-lookup"><span data-stu-id="4eeca-227">+14255550100</span></span></p></td>
<td><p><span data-ttu-id="4eeca-228">0 が +14255550100 に変換されます。</span><span class="sxs-lookup"><span data-stu-id="4eeca-228">0 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4eeca-229">RedmondSitePrefix</span><span class="sxs-lookup"><span data-stu-id="4eeca-229">RedmondSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="4eeca-230">ネットワーク内プレフィックス (6) および Redmond のサイト コード (222) 付きの番号を変換します。</span><span class="sxs-lookup"><span data-stu-id="4eeca-230">Translates numbers with on-net prefix (6) and Redmond site code (222)</span></span></p></td>
<td><p><span data-ttu-id="4eeca-231">^ 6222 (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="4eeca-231">^6222(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="4eeca-232">+ 1425555 $ 1</span><span class="sxs-lookup"><span data-stu-id="4eeca-232">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="4eeca-233">62220100 が +14255550100 に変換されます。</span><span class="sxs-lookup"><span data-stu-id="4eeca-233">62220100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4eeca-234">NYSitePrefix</span><span class="sxs-lookup"><span data-stu-id="4eeca-234">NYSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="4eeca-235">ネットワーク内プレフィックス (6) および NY のサイト コード (333) 付きの番号を変換します。</span><span class="sxs-lookup"><span data-stu-id="4eeca-235">Translates numbers with on-net prefix (6) and NY site code (333)</span></span></p></td>
<td><p><span data-ttu-id="4eeca-236">^ 6333 (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="4eeca-236">^6333(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="4eeca-237">+ 1202555 $ 1</span><span class="sxs-lookup"><span data-stu-id="4eeca-237">+1202555$1</span></span></p></td>
<td><p><span data-ttu-id="4eeca-238">63330100 が +12025550100 に変換されます。</span><span class="sxs-lookup"><span data-stu-id="4eeca-238">63330100 is translated to +12025550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4eeca-239">DallasSitePrefix</span><span class="sxs-lookup"><span data-stu-id="4eeca-239">DallasSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="4eeca-240">ネットワーク内プレフィックス (6) および Dallas のサイト コード (444) 付きの番号を変換します。</span><span class="sxs-lookup"><span data-stu-id="4eeca-240">Translates numbers with on-net prefix (6) and Dallas site code (444)</span></span></p></td>
<td><p><span data-ttu-id="4eeca-241">^ 6444 (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="4eeca-241">^6444(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="4eeca-242">+ 1972555 $ 1</span><span class="sxs-lookup"><span data-stu-id="4eeca-242">+1972555$1</span></span></p></td>
<td><p><span data-ttu-id="4eeca-243">64440100 が +19725550100 に変換されます。</span><span class="sxs-lookup"><span data-stu-id="4eeca-243">64440100 is translated to +19725550100</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4eeca-244">以下の表は、Redmond (Washington、米国) の場所のダイヤル プランの例です。これは、前の表に示す正規化ルールに基づいています。</span><span class="sxs-lookup"><span data-stu-id="4eeca-244">The following table illustrates a sample dial plan for Redmond, Washington, United States, based on the normalization rules shown in the previous table.</span></span>

### <a name="table-2-redmond-dial-plan-based-on-normalization-rules-shown-in-table-1"></a><span data-ttu-id="4eeca-p117">表 2. 表 1 の正規化ルールに基づく Redmond のダイヤル プラン</span><span class="sxs-lookup"><span data-stu-id="4eeca-p117">Table 2. Redmond Dial Plan Based on Normalization Rules Shown in Table 1</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4eeca-247">Redmond. forestFQDN</span><span class="sxs-lookup"><span data-stu-id="4eeca-247">Redmond.forestFQDN</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4eeca-248">5digitExtension</span><span class="sxs-lookup"><span data-stu-id="4eeca-248">5digitExtension</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4eeca-249">7digitcallingRedmond</span><span class="sxs-lookup"><span data-stu-id="4eeca-249">7digitcallingRedmond</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4eeca-250">10digitcallingUS</span><span class="sxs-lookup"><span data-stu-id="4eeca-250">10digitcallingUS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4eeca-251">IntlCallingUS</span><span class="sxs-lookup"><span data-stu-id="4eeca-251">IntlCallingUS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4eeca-252">RedmondSitePrefix</span><span class="sxs-lookup"><span data-stu-id="4eeca-252">RedmondSitePrefix</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4eeca-253">NYSitePrefix</span><span class="sxs-lookup"><span data-stu-id="4eeca-253">NYSitePrefix</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4eeca-254">DallasSitePrefix</span><span class="sxs-lookup"><span data-stu-id="4eeca-254">DallasSitePrefix</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4eeca-255">RedmondOperator</span><span class="sxs-lookup"><span data-stu-id="4eeca-255">RedmondOperator</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="4eeca-p118">前の表に記載した正規化ルールの名前にはスペースが含まれていませんが、これは任意に設定できます。たとえば、この表の最初の名前は、「5 digit extension」または「5-digit Extension」のどちらで記述しても問題ありません。</span><span class="sxs-lookup"><span data-stu-id="4eeca-p118">The normalization rules names shown in the preceding table do not include spaces, but this is a matter of choice. The first name in the table, for example, could have been written "5 digit extension" or "5-digit Extension" and still be valid.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

