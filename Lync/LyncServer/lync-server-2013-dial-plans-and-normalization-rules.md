---
title: 'Lync Server 2013: ダイヤルプランと正規化ルール'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Dial plans and normalization rules
ms:assetid: fde45195-6eb4-403c-9094-57df7fc0bd2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413082(v=OCS.15)
ms:contentKeyID: 48185960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5d399c49db109a7bac1a1cd3ac430280cb70f665
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833420"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-plans-and-normalization-rules-in-lync-server-2013"></a><span data-ttu-id="ca5ee-102">Lync Server 2013 でのダイヤルプランと正規化ルール</span><span class="sxs-lookup"><span data-stu-id="ca5ee-102">Dial plans and normalization rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca5ee-103">_**最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="ca5ee-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="ca5ee-104">ダイヤル プランとは、電話番号の承認と通話のルーティングを目的として、特定の場所、個々のユーザー、または連絡先オブジェクトの電話番号を 1 つの標準形式 (E.164) に変換する正規化ルールのセットに名前を付けたものです。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-104">A dial plan is a named set of normalization rules that translates phone numbers for a named location, individual user, or contact object into a single standard (E.164) format for purposes of phone authorization and call routing.</span></span>

<span data-ttu-id="ca5ee-p101">正規化ルールは、さまざまな形式で表現された電話番号を指定された各場所、ユーザー、または連絡先オブジェクトにルーティングする方法を定義します。ダイヤル元の場所および電話をかける人や連絡先オブジェクトによって、同じダイヤル文字列が異なる方法で解釈および変換される場合があります。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-p101">Normalization rules define how phone numbers expressed in various formats are to be routed for each specified location, user, or contact object. The same dial string may be interpreted and translated differently, depending on the location from which it is dialed and the person or contact object making the call.</span></span>

<div>

## <a name="dial-plan-scope"></a><span data-ttu-id="ca5ee-107">ダイヤル プランのスコープ</span><span class="sxs-lookup"><span data-stu-id="ca5ee-107">Dial Plan Scope</span></span>

<span data-ttu-id="ca5ee-108">ダイヤル プランの*スコープ*によって、ダイヤル プランを適用できる階層レベルが決まります。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-108">A dial plan’s *scope* determines the hierarchical level at which the dial plan can be applied.</span></span> <span data-ttu-id="ca5ee-109">Lync Server では、ユーザーに特定のユーザーごとのダイヤルプランを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-109">In Lync Server, a user can be assigned a specific per-user dial plan.</span></span> <span data-ttu-id="ca5ee-110">ユーザーダイヤルプランが割り当てられていない場合は、レジストラー pool dial plan が適用されます。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-110">If a user dial plan is not assigned, the Registrar pool dial plan is applied.</span></span> <span data-ttu-id="ca5ee-111">レジストラー pool ダイヤルプランがない場合は、サイトダイヤルプランが適用されます。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-111">If there is no Registrar pool dial plan, the site dial plan is applied.</span></span> <span data-ttu-id="ca5ee-112">ユーザーに適用可能な他のダイヤル プランがない場合は、最後にグローバル ダイヤル プランが適用されます。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-112">Finally, if there is no other dial plan applicable to the user, the global dial plan is applied.</span></span>

<span data-ttu-id="ca5ee-113">クライアントは、ユーザーが Lync Server にログオンしたときに提供されるインバンドプロビジョニングの設定を通じて、ダイヤルプランのスコープレベルを取得します。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-113">Clients obtain dial plan scope levels through in-band provisioning settings that are provided when users log on to Lync Server.</span></span> <span data-ttu-id="ca5ee-114">管理者は、Lync Server コントロールパネルを使用して、ダイヤルプランのスコープレベルを管理して割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-114">As the administrator, you can manage and assign dial plan scope levels by using Lync Server Control Panel.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ca5ee-115">サービス レベルの公衆交換電話網 (PSTN) ゲートウェイのダイヤル プランは、特定のゲートウェイからの着信に適用されます。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-115">The service level public switched telephone network (PSTN) gateway dial plan is applied to the incoming calls from a particular gateway.</span></span>



</div>

<span data-ttu-id="ca5ee-116">ダイヤル プランのスコープ レベルは、次のように定義されます。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-116">Dial plan scope levels are defined as follows:</span></span>

  - <span data-ttu-id="ca5ee-117">**ユーザーダイヤルプラン:** 個々のユーザー、グループ、または連絡先オブジェクトに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-117">**User dial plan:** Can be assigned to individual users, groups, or contact objects.</span></span> <span data-ttu-id="ca5ee-118">音声アプリケーションは、user-default に設定された電話コンテキストのコールを受信したとき、ユーザーごとのダイヤル プランを参照できます。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-118">Voice applications can look up a per-user dial plan when a call is received with the phone-context set to user-default.</span></span> <span data-ttu-id="ca5ee-119">連絡先オブジェクトは、ダイヤル プラン割り当ての際には個々のユーザーとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-119">For the purpose of assigning a dial plan, a contact object is treated as an individual user.</span></span>

  - <span data-ttu-id="ca5ee-120">**プールダイヤルプラン:** お客様のトポロジの PSTN ゲートウェイまたはレジストラーのサービスレベルで作成できます。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-120">**Pool dial plan:** Can be created at the service level for any PSTN gateway or Registrar in your topology.</span></span> <span data-ttu-id="ca5ee-121">プール ダイヤル プランを定義するには、ダイヤル プランを適用する特定のサービス (PSTN ゲートウェイまたはレジストラー プール) を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-121">To define a pool dial plan, you must specify the particular service (PSTN gateway or Registrar pool) to which the dial plan applies.</span></span>

  - <span data-ttu-id="ca5ee-122">**サイトダイヤルプラン:** プールダイヤルプランまたはユーザーダイヤルプランが割り当てられているユーザー、グループ、または連絡先オブジェクトを除き、サイト全体に対して作成できます。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-122">**Site dial plan:** Can be created for an entire site, except for any users, groups, or contact objects that are assigned a pool dial plan or user dial plan.</span></span> <span data-ttu-id="ca5ee-123">サイト ダイヤル プランを定義するには、ダイヤル プランを適用するサイトを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-123">To define a site dial plan, you must specify the site to which the dial plan applies.</span></span>

  - <span data-ttu-id="ca5ee-124">**グローバルダイヤルプラン:** 製品と共にインストールされた既定のダイヤルプラン。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-124">**Global dial plan:** The default dial plan installed with the product.</span></span> <span data-ttu-id="ca5ee-125">グローバル ダイヤル プランは、編集することはできますが削除はできません。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-125">You can edit the global dial plan, but you cannot delete it.</span></span> <span data-ttu-id="ca5ee-126">このダイヤルプランは、より具体的なスコープのダイヤルプランを構成して割り当てる場合を除き、展開内のすべてのエンタープライズボイスユーザー、グループ、連絡先オブジェクトに適用されます。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-126">This dial plan applies to all Enterprise Voice users, groups, and contact objects in your deployment, unless you configure and assign a dial plan with a more specific scope.</span></span>

</div>

<div>

## <a name="planning-for-dial-plans"></a><span data-ttu-id="ca5ee-127">ダイヤル プランの計画</span><span class="sxs-lookup"><span data-stu-id="ca5ee-127">Planning for Dial Plans</span></span>

<span data-ttu-id="ca5ee-128">ダイヤル プランを計画するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-128">To plan a dial plan, follow these steps:</span></span>

  - <span data-ttu-id="ca5ee-129">組織内のオフィスがあるすべてのロケールをリストアップします。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-129">List all the locales in which your organization has an office.</span></span>
    
    <span data-ttu-id="ca5ee-p108">このリストは、すべてを網羅した最新の情報である必要があります。また、組織の変化に合わせて改訂する必要があります。多数の小規模なブランチ オフィスを持つ大規模な多国籍企業の場合は、この作業に時間がかかる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-p108">The list must be up-to-date and complete. It will need to be revised as company organization evolves. In a large, multinational company with numerous small branch offices, this can be a time-consuming task.</span></span>

  - <span data-ttu-id="ca5ee-133">各サイトにおける有効な番号パターンを特定します。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-133">Identify valid number patterns for each site.</span></span>
    
    <span data-ttu-id="ca5ee-p109">ダイヤル プランの計画で最も時間がかかるのは、それぞれのサイトの有効な番号パターンを特定することです。あるダイヤル プラン用に記述した正規化ルールを他のダイヤル プランにコピーできる場合があります (特に、対応しているサイトが同じ国/地域または大陸にある場合)。これ以外の場合でも、あるダイヤル プランの番号を少し変更すれば他のダイヤル プランに十分使用できる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-p109">The most time-consuming part of planning your dial plans is identifying the valid number patterns for each site. In some cases, you may be able to copy normalization rules that you have written for one dial plan to other dial plans, especially if the corresponding sites are within the same country/region or even continent. In other cases, small changes to numbers in one dial plan may be enough to use them in other dial plans.</span></span>

  - <span data-ttu-id="ca5ee-137">ダイヤル プランの名前付けのための、組織全体のスキームを開発します。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-137">Develop an organization-wide scheme for naming dial plans.</span></span>
    
    <span data-ttu-id="ca5ee-138">標準の名前付けスキームを採用することで、組織間の一貫性を保ち、メンテナンスと更新を簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-138">Adopting a standard naming scheme assures consistency across an organization and makes maintenance and updates easier.</span></span>

  - <span data-ttu-id="ca5ee-139">1 つの場所で複数のダイヤル プランが必要かどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-139">Decide whether multiple dial plans are required for a single location.</span></span>
    
    <span data-ttu-id="ca5ee-140">組織が複数の場所で1つのダイヤルプランを管理している場合は、プライベートブランチ exchange (PBX) から移行している、または既存の拡張機能が保持されている必要があるエンタープライズボイスユーザーに対して、別のダイヤルプランを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-140">If your organization maintains a single dial plan across multiple locations, you may still need to create a separate dial plan for Enterprise Voice users who are migrating from a private branch exchange (PBX) and who need to have their existing extensions retained.</span></span>

  - <span data-ttu-id="ca5ee-141">ユーザーごとのダイヤル プランが必要かどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-141">Decide whether per-user dial plans are required.</span></span> <span data-ttu-id="ca5ee-142">たとえば、セントラルサイトに登録されているブランチサイトにユーザーがいる場合、または Survivable Branch アプライアンスに登録されているユーザーがいる場合、ユーザーのダイヤルプランと正規化ルールを使用しているユーザーのために特別なダイヤルシナリオを検討することができます。.</span><span class="sxs-lookup"><span data-stu-id="ca5ee-142">For example, if you have users at a branch site who are registered with the central site or if you have users who are registered on a Survivable Branch Appliance, you can consider special dialing scenarios for such users using per-user dial plans and normalization rules.</span></span> <span data-ttu-id="ca5ee-143">詳細については、「 [Lync Server 2013 のブランチサイトの回復性の要件](lync-server-2013-branch-site-resiliency-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-143">For details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).</span></span>

  - <span data-ttu-id="ca5ee-144">ダイヤル プランのスコープを決定します (このトピック内で前述)。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-144">Determine dial plan scope (as previously described in this topic).</span></span>

<span data-ttu-id="ca5ee-145">ダイヤルプランを作成するには、Lync Server コントロールパネルまたは Lync Server 管理シェルを使用して、必要に応じて次のフィールドの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-145">To create a dial plan, you specify values in the following fields, as required, by using Lync Server Control Panel or Lync Server Management Shell.</span></span>

<div>

## <a name="name-and-simple-name"></a><span data-ttu-id="ca5ee-146">名前および簡単な名前</span><span class="sxs-lookup"><span data-stu-id="ca5ee-146">Name and Simple Name</span></span>

<span data-ttu-id="ca5ee-147">ユーザー ダイヤル プランの場合、ダイヤル プランの割り当て先のユーザー、グループ、または連絡先オブジェクトを識別する説明的な名前を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-147">For user dial plans, you should specify a descriptive name that identifies the users, groups, or contact objects to which the dial plan will be assigned.</span></span> <span data-ttu-id="ca5ee-148">サイトダイヤルプランの場合、[名前] フィールドにはサイト名があらかじめ記載されているため、変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-148">For site dial plans, the Name field is prepopulated with the site name and cannot be changed.</span></span> <span data-ttu-id="ca5ee-149">プールダイヤルプランの場合、[名前] フィールドには PSTN ゲートウェイまたはフロントエンドプールの完全修飾ドメイン名 (FQDN) が事前に指定されているため、変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-149">For pool dial plans, the Name field is prepopulated with the PSTN gateway or Front End pool fully qualified domain name (FQDN) and cannot be changed.</span></span>

<span data-ttu-id="ca5ee-150">ダイヤルプランの*簡易名*は、ダイヤルプラン名から派生した文字列を基にして編成されます。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-150">The dial plan *Simple Name* is prepopulated with a string that is derived from the dial plan name.</span></span> <span data-ttu-id="ca5ee-151">"簡単な名前" フィールドは編集することができ、よりわかりやすいダイヤル プランの名前付け規則を作成できるようになっています。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-151">The Simple Name field is editable, which enables you to create a more descriptive naming convention for your dial plans.</span></span> <span data-ttu-id="ca5ee-152">*簡単な名前*の値を空にすることはできず、一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-152">The *Simple Name* value cannot be empty and must be unique.</span></span> <span data-ttu-id="ca5ee-153">組織全体の名前付け規則を開発し、この規則をすべてのサイトとユーザーで一貫して使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-153">A best practice is to develop a naming convention for your entire organization and then use this convention consistently across all sites and users.</span></span>

</div>

<div>

## <a name="description"></a><span data-ttu-id="ca5ee-154">説明</span><span class="sxs-lookup"><span data-stu-id="ca5ee-154">Description</span></span>

<span data-ttu-id="ca5ee-p113">対応するダイヤル プランが適用される地理的な場所の、一般的でわかりやすい名前を入力することをお勧めします。たとえば、ダイヤル プランの名前が London.Contoso.com である場合、説明を London とすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-p113">We recommend that you type the common, recognizable name of the geographic location to which the corresponding dial plan applies. For example, if the dial plan name is London.Contoso.com, the recommended description would be London.</span></span>

</div>

<div>

## <a name="dial-in-conferencing-region"></a><span data-ttu-id="ca5ee-157">ダイヤルイン会議の地域</span><span class="sxs-lookup"><span data-stu-id="ca5ee-157">Dial-in Conferencing Region</span></span>

<span data-ttu-id="ca5ee-158">ダイヤルイン会議を展開している場合、ダイヤルイン会議の地域を指定し、ダイヤルイン会議のアクセス番号をダイヤル プランと関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-158">If you are deploying dial-in conferencing, you will need to specify a dial-in conferencing region to associate dial-in conferencing access numbers with a dial plan.</span></span>

</div>

<div>

## <a name="external-access-prefix"></a><span data-ttu-id="ca5ee-159">外部アクセス プレフィックス</span><span class="sxs-lookup"><span data-stu-id="ca5ee-159">External Access Prefix</span></span>

<span data-ttu-id="ca5ee-160">ユーザーが追加の先頭の数字 (9 など) をダイヤル\#する\*必要がある場合は、最大4文字 (,、0-9) の外部アクセスプレフィックスを指定して、外部の行を取得できます。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-160">You can specify an external access prefix of up to four characters (\#, \*, and 0-9) if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ca5ee-161">外部アクセス プレフィックスを指定する場合に、プレフィックスに対応するために追加の正規化ルールを作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-161">If you specify an external access prefix, you do not need to create an additional normalization rule to accommodate the prefix.</span></span>



</div>

</div>

</div>

<div>

## <a name="normalization-rules"></a><span data-ttu-id="ca5ee-162">正規化ルール</span><span class="sxs-lookup"><span data-stu-id="ca5ee-162">Normalization Rules</span></span>

<span data-ttu-id="ca5ee-p114">正規化ルールは、さまざまな形式で表現された電話番号を指定の場所にルーティングする方法を定義します。同じ電話番号文字列が、その番号がダイヤルされたロケールに応じて、異なる方法で解釈および変換されることがあります。正規化ルールは通話のルーティングに不可欠です。これは、ユーザーが連絡先リストに電話番号を入力する際にさまざまな形式を使用する可能性があるためです。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-p114">Normalization rules define how phone numbers expressed in various formats are to be routed for the named location. The same number string may be interpreted and translated differently, depending on the locale from which it is dialed. Normalization rules are necessary for call routing because users can, and do, use various formats when entering phone numbers in their Contacts lists.</span></span>

<span data-ttu-id="ca5ee-166">ユーザーがダイヤルした電話番号を正規化することによって、形式の一貫性を確保できます。これは、次の処理に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-166">Normalizing user-supplied phone numbers provides a consistent format that facilitates the following tasks:</span></span>

  - <span data-ttu-id="ca5ee-167">ダイヤルされた番号と受信者の SIP-URI のマッチング</span><span class="sxs-lookup"><span data-stu-id="ca5ee-167">Match a dialed number to the intended recipient’s SIP-URI.</span></span>

  - <span data-ttu-id="ca5ee-168">発信者へのダイヤル承認ルールの適用</span><span class="sxs-lookup"><span data-stu-id="ca5ee-168">Apply dialing authorization rules to the calling party.</span></span>

<span data-ttu-id="ca5ee-169">次の番号フィールドでは、正規化ルールの考慮が必要になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-169">The following number fields are among those that your normalization rules may need to account for:</span></span>

  - <span data-ttu-id="ca5ee-170">ダイヤル プラン</span><span class="sxs-lookup"><span data-stu-id="ca5ee-170">Dial plan</span></span>

  - <span data-ttu-id="ca5ee-171">国番号</span><span class="sxs-lookup"><span data-stu-id="ca5ee-171">Country code</span></span>

  - <span data-ttu-id="ca5ee-172">市外局番</span><span class="sxs-lookup"><span data-stu-id="ca5ee-172">Area code</span></span>

  - <span data-ttu-id="ca5ee-173">内線番号の長さ</span><span class="sxs-lookup"><span data-stu-id="ca5ee-173">Length of extension</span></span>

  - <span data-ttu-id="ca5ee-174">サイトのプレフィックス</span><span class="sxs-lookup"><span data-stu-id="ca5ee-174">Site prefix</span></span>

<div>

## <a name="creating-normalization-rules"></a><span data-ttu-id="ca5ee-175">正規化ルールの作成</span><span class="sxs-lookup"><span data-stu-id="ca5ee-175">Creating Normalization Rules</span></span>

<span data-ttu-id="ca5ee-176">正規化ルールでは、リバース番号検索でダイヤル文字列を E.164 形式に変換するためにサーバーによって使用される番号一致パターンを指定するために, .NET Framework の正規表現が使用されます。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-176">Normalization rules use .NET Framework regular expressions to specify numeric match patterns that the server uses to translate dial strings to E.164 format for the purpose of performing reverse number lookup.</span></span> <span data-ttu-id="ca5ee-177">Lync Server コントロールパネルで正規化ルールを作成するには、式を手動で入力するか、対応するダイヤル文字列の開始番号と長さを入力して、Lync Server コントロールパネルで対応する正規表現。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-177">You create normalization rules in the Lync Server Control Panel either by entering the expressions manually, or by entering the starting digits and the length of the dial strings to be matched and letting the Lync Server Control Panel generate the corresponding regular expression for you.</span></span> <span data-ttu-id="ca5ee-178">どちらの場合も、完了したら、テスト番号を入力して正規化ルールが期待どおりに動作することを確認できます。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-178">Either way, when you finish, you can enter a test number to verify that the normalization rule works as expected.</span></span>

<span data-ttu-id="ca5ee-179">.NET Framework の正規表現の使い方の詳細については、「」の[http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927)「.net Framework の正規表現」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-179">For details about using .NET Framework regular expressions, see ".NET Framework Regular Expressions" at [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

</div>

<span id="BKMK_SampleNormalizationRules"></span>

<div>

## <a name="sample-normalization-rules"></a><span data-ttu-id="ca5ee-180">正規化ルールの例</span><span class="sxs-lookup"><span data-stu-id="ca5ee-180">Sample Normalization Rules</span></span>

<span data-ttu-id="ca5ee-p116">次の表は、.NET Framework 正規表現で記述された正規化ルールの例です。ここに示すのは単なる例であり、ご自分の正規化ルールをこのとおりに作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-p116">The following table shows sample normalization rules that are written as .NET Framework regular expressions. The samples are examples only and are not meant to be a prescriptive reference for creating your own normalization rules.</span></span>

### <a name="table-1normalization-rules-using-net-framework-regular-expressions"></a><span data-ttu-id="ca5ee-183">表 1. .NET Framework 正規表現を使用した正規化ルール</span><span class="sxs-lookup"><span data-stu-id="ca5ee-183">Table 1.Normalization Rules Using .NET Framework Regular Expressions</span></span>

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
<th><span data-ttu-id="ca5ee-184">ルール名</span><span class="sxs-lookup"><span data-stu-id="ca5ee-184">Rule name</span></span></th>
<th><span data-ttu-id="ca5ee-185">説明</span><span class="sxs-lookup"><span data-stu-id="ca5ee-185">Description</span></span></th>
<th><span data-ttu-id="ca5ee-186">番号のパターン</span><span class="sxs-lookup"><span data-stu-id="ca5ee-186">Number pattern</span></span></th>
<th><span data-ttu-id="ca5ee-187">変換</span><span class="sxs-lookup"><span data-stu-id="ca5ee-187">Translation</span></span></th>
<th><span data-ttu-id="ca5ee-188">例</span><span class="sxs-lookup"><span data-stu-id="ca5ee-188">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ca5ee-189">4digitExtension</span><span class="sxs-lookup"><span data-stu-id="ca5ee-189">4digitExtension</span></span></p></td>
<td><p><span data-ttu-id="ca5ee-190">4 桁の内線番号を変換します。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-190">Translates 4-digit extensions</span></span></p></td>
<td><p><span data-ttu-id="ca5ee-191">^ (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="ca5ee-191">^(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="ca5ee-192">+1425555$1</span><span class="sxs-lookup"><span data-stu-id="ca5ee-192">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="ca5ee-193">0100 は +14255550100 に変換されます</span><span class="sxs-lookup"><span data-stu-id="ca5ee-193">0100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca5ee-194">5digitExtension</span><span class="sxs-lookup"><span data-stu-id="ca5ee-194">5digitExtension</span></span></p></td>
<td><p><span data-ttu-id="ca5ee-195">5 桁の内線番号を変換します。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-195">Translates 5-digit extensions</span></span></p></td>
<td><p><span data-ttu-id="ca5ee-196">^ 5 (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="ca5ee-196">^5(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="ca5ee-197">+1425555$1</span><span class="sxs-lookup"><span data-stu-id="ca5ee-197">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="ca5ee-198">50100 は +14255550100 に変換されます</span><span class="sxs-lookup"><span data-stu-id="ca5ee-198">50100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca5ee-199">7digitcallingRedmond</span><span class="sxs-lookup"><span data-stu-id="ca5ee-199">7digitcallingRedmond</span></span></p></td>
<td><p><span data-ttu-id="ca5ee-200">7 桁の番号を Redmond の電話番号に変換します。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-200">Translates 7-digit numbers to Redmond local numbers</span></span></p></td>
<td><p><span data-ttu-id="ca5ee-201">^ (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="ca5ee-201">^(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="ca5ee-202">+1425$1</span><span class="sxs-lookup"><span data-stu-id="ca5ee-202">+1425$1</span></span></p></td>
<td><p><span data-ttu-id="ca5ee-203">5550100 が +14255550100 に変換されます。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-203">5550100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca5ee-204">7digitcallingDallas</span><span class="sxs-lookup"><span data-stu-id="ca5ee-204">7digitcallingDallas</span></span></p></td>
<td><p><span data-ttu-id="ca5ee-205">7 桁の番号を Dallas の電話番号に変換します。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-205">Translates 7-digit numbers to Dallas local numbers</span></span></p></td>
<td><p><span data-ttu-id="ca5ee-206">^ (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="ca5ee-206">^(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="ca5ee-207">+1972$1</span><span class="sxs-lookup"><span data-stu-id="ca5ee-207">+1972$1</span></span></p></td>
<td><p><span data-ttu-id="ca5ee-208">5550100 が +19725550100 に変換されます。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-208">5550100 is translated to +19725550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca5ee-209">10digitcallingUS</span><span class="sxs-lookup"><span data-stu-id="ca5ee-209">10digitcallingUS</span></span></p></td>
<td><p><span data-ttu-id="ca5ee-210">米国の 10 桁の番号を変換します。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-210">Translates 10-digit numbers in the United States</span></span></p></td>
<td><p><span data-ttu-id="ca5ee-211">^ (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="ca5ee-211">^(\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="ca5ee-212">+1$1</span><span class="sxs-lookup"><span data-stu-id="ca5ee-212">+1$1</span></span></p></td>
<td><p><span data-ttu-id="ca5ee-213">2065550100 が +12065550100 に変換されます。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-213">2065550100 is translated to +12065550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca5ee-214">LDCallingUS</span><span class="sxs-lookup"><span data-stu-id="ca5ee-214">LDCallingUS</span></span></p></td>
<td><p><span data-ttu-id="ca5ee-215">米国の長距離プレフィックス付きの番号を変換します。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-215">Translates numbers with long distance prefixes in the United States</span></span></p></td>
<td><p><span data-ttu-id="ca5ee-216">^ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="ca5ee-216">^1(\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="ca5ee-217">+$1</span><span class="sxs-lookup"><span data-stu-id="ca5ee-217">+$1</span></span></p></td>
<td><p><span data-ttu-id="ca5ee-218">12145550100 が +2145550100 に変換されます。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-218">12145550100 is translated to +2145550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca5ee-219">IntlCallingUS</span><span class="sxs-lookup"><span data-stu-id="ca5ee-219">IntlCallingUS</span></span></p></td>
<td><p><span data-ttu-id="ca5ee-220">米国の国際プレフィックス付きの番号を変換します。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-220">Translates numbers with international prefixes in the United States</span></span></p></td>
<td><p><span data-ttu-id="ca5ee-221">^011(\d\*)$</span><span class="sxs-lookup"><span data-stu-id="ca5ee-221">^011(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="ca5ee-222">+$1</span><span class="sxs-lookup"><span data-stu-id="ca5ee-222">+$1</span></span></p></td>
<td><p><span data-ttu-id="ca5ee-223">01191445550100 が +91445550100 に変換されます。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-223">01191445550100 is translated to +91445550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca5ee-224">RedmondOperator</span><span class="sxs-lookup"><span data-stu-id="ca5ee-224">RedmondOperator</span></span></p></td>
<td><p><span data-ttu-id="ca5ee-225">0 を Redmond のオペレーター呼び出し番号に変換します。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-225">Translates 0 to Redmond Operator</span></span></p></td>
<td><p><span data-ttu-id="ca5ee-226">^0$</span><span class="sxs-lookup"><span data-stu-id="ca5ee-226">^0$</span></span></p></td>
<td><p><span data-ttu-id="ca5ee-227">+14255550100</span><span class="sxs-lookup"><span data-stu-id="ca5ee-227">+14255550100</span></span></p></td>
<td><p><span data-ttu-id="ca5ee-228">0 は +14255550100 に変換されます</span><span class="sxs-lookup"><span data-stu-id="ca5ee-228">0 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca5ee-229">RedmondSitePrefix</span><span class="sxs-lookup"><span data-stu-id="ca5ee-229">RedmondSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="ca5ee-230">ネットワーク内プレフィックス (6) および Redmond のサイト コード (222) 付きの番号を変換します。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-230">Translates numbers with on-net prefix (6) and Redmond site code (222)</span></span></p></td>
<td><p><span data-ttu-id="ca5ee-231">^ 6222 (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="ca5ee-231">^6222(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="ca5ee-232">+1425555$1</span><span class="sxs-lookup"><span data-stu-id="ca5ee-232">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="ca5ee-233">62220100 が +14255550100 に変換されます。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-233">62220100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca5ee-234">NYSitePrefix</span><span class="sxs-lookup"><span data-stu-id="ca5ee-234">NYSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="ca5ee-235">ネットワーク内プレフィックス (6) および NY のサイト コード (333) 付きの番号を変換します。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-235">Translates numbers with on-net prefix (6) and NY site code (333)</span></span></p></td>
<td><p><span data-ttu-id="ca5ee-236">^ 6333 (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="ca5ee-236">^6333(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="ca5ee-237">+1202555$1</span><span class="sxs-lookup"><span data-stu-id="ca5ee-237">+1202555$1</span></span></p></td>
<td><p><span data-ttu-id="ca5ee-238">63330100 が +12025550100 に変換されます。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-238">63330100 is translated to +12025550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca5ee-239">DallasSitePrefix</span><span class="sxs-lookup"><span data-stu-id="ca5ee-239">DallasSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="ca5ee-240">ネットワーク内プレフィックス (6) および Dallas のサイト コード (444) 付きの番号を変換します。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-240">Translates numbers with on-net prefix (6) and Dallas site code (444)</span></span></p></td>
<td><p><span data-ttu-id="ca5ee-241">^ 6444 (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="ca5ee-241">^6444(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="ca5ee-242">+1972555$1</span><span class="sxs-lookup"><span data-stu-id="ca5ee-242">+1972555$1</span></span></p></td>
<td><p><span data-ttu-id="ca5ee-243">64440100 が +19725550100 に変換されます。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-243">64440100 is translated to +19725550100</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ca5ee-244">以下の表は、Redmond (Washington、米国) の場所のダイヤル プランの例です。これは、前の表に示す正規化ルールに基づいています。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-244">The following table illustrates a sample dial plan for Redmond, Washington, United States, based on the normalization rules shown in the previous table.</span></span>

### <a name="table-2-redmond-dial-plan-based-on-normalization-rules-shown-in-table-1"></a><span data-ttu-id="ca5ee-p117">表 2. 表 1 の正規化ルールに基づく Redmond のダイヤル プラン</span><span class="sxs-lookup"><span data-stu-id="ca5ee-p117">Table 2. Redmond Dial Plan Based on Normalization Rules Shown in Table 1</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ca5ee-247">Redmond.forestFQDN</span><span class="sxs-lookup"><span data-stu-id="ca5ee-247">Redmond.forestFQDN</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ca5ee-248">5digitExtension</span><span class="sxs-lookup"><span data-stu-id="ca5ee-248">5digitExtension</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca5ee-249">7digitcallingRedmond</span><span class="sxs-lookup"><span data-stu-id="ca5ee-249">7digitcallingRedmond</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca5ee-250">10digitcallingUS</span><span class="sxs-lookup"><span data-stu-id="ca5ee-250">10digitcallingUS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca5ee-251">IntlCallingUS</span><span class="sxs-lookup"><span data-stu-id="ca5ee-251">IntlCallingUS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca5ee-252">RedmondSitePrefix</span><span class="sxs-lookup"><span data-stu-id="ca5ee-252">RedmondSitePrefix</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca5ee-253">NYSitePrefix</span><span class="sxs-lookup"><span data-stu-id="ca5ee-253">NYSitePrefix</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca5ee-254">DallasSitePrefix</span><span class="sxs-lookup"><span data-stu-id="ca5ee-254">DallasSitePrefix</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca5ee-255">RedmondOperator</span><span class="sxs-lookup"><span data-stu-id="ca5ee-255">RedmondOperator</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="ca5ee-p118">前の表に示した正規化ルールの名前にはスペースが含まれていませんが、必要に応じて含めることもできます。たとえば、表に最初に示されている名前は、「5 digit extension」と「5-digit Extension」のどちらの形式で記述しても有効になります。</span><span class="sxs-lookup"><span data-stu-id="ca5ee-p118">The normalization rules names shown in the preceding table do not include spaces, but this is a matter of choice. The first name in the table, for example, could have been written "5 digit extension" or "5-digit Extension" and still be valid.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

