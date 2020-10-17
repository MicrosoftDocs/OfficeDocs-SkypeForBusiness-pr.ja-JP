---
title: 'Lync Server 2013: ダイヤルイン会議のダイヤルプランを構成する'
description: 'Lync Server 2013: ダイヤルイン会議のダイヤルプランを構成します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure dial plans for dial-in conferencing
ms:assetid: a3e0958e-384f-43e5-b4c9-686b6ecac7ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412768(v=OCS.15)
ms:contentKeyID: 48185051
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28123f905288ce35b6f470168962a3d8e6faa22b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567583"
---
# <a name="configure-dial-plans-for-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="6c03a-103">Lync Server 2013 でダイヤルイン会議のダイヤルプランを構成する</span><span class="sxs-lookup"><span data-stu-id="6c03a-103">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c03a-104">_**トピックの最終更新日:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="6c03a-104">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="6c03a-p101">ダイヤルイン会議を展開するときは、ダイヤルインのアクセス電話番号をルーティングするために、1 つ以上のダイヤル プランを作成または変更する必要があります。 各ダイヤル プランの少なくとも 1 つの正規化ルールにより、内線電話番号が E.164 形式の完全な電話番号に変換されることを確認してください。ダイヤルイン会議のユーザーは、自分の暗証番号 (PIN) と電話番号を入力して、認証済みのエンタープライズ ユーザーとして会議に参加します。 内線番号を完全な電話番号に変換する正規化ルールが必要なのは、内線番号だけの入力でユーザーを認証できるようにするためです。</span><span class="sxs-lookup"><span data-stu-id="6c03a-p101">When you deploy dial-in conferencing, you need to create or modify one or more dial plans for routing dial-in access phone numbers. Make sure that at least one normalization rule in each dial plan converts telephone extensions into complete phone numbers in E.164 format. Users of dial-in conferencing join conferences as authenticated enterprise users by entering their personal identification number (PIN) and their phone number. You need a normalization rule to convert extensions into complete phone numbers so that users can be authenticated when they enter just a telephone extension.</span></span>

<span data-ttu-id="6c03a-109">ダイヤルイン会議のダイヤル プランをセットアップするには、次の作業を行います。</span><span class="sxs-lookup"><span data-stu-id="6c03a-109">To set up dial plans for dial-in conferencing, do the following:</span></span>

  - <span data-ttu-id="6c03a-110">エンタープライズ Voip を展開するかどうかにかかわらず、グローバルダイヤルプランを変更してダイヤルイン会議の地域を追加し、ダイヤルインアクセス番号を正規化ルールに正確に変換するようにします。</span><span class="sxs-lookup"><span data-stu-id="6c03a-110">Whether or not you deploy Enterprise Voice, modify the global dial plan to add a dial-in conferencing region and to make sure that a normalization rule accurately converts your dial-in access numbers.</span></span> <span data-ttu-id="6c03a-111">詳細な手順については、「 [Modify a dial plan In Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c03a-111">For detailed instructions, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

  - <span data-ttu-id="6c03a-112">エンタープライズ Voip を展開しなかった場合は、ダイヤルイン会議アクセス番号のダイヤルプランを作成します。</span><span class="sxs-lookup"><span data-stu-id="6c03a-112">If you did not deploy Enterprise Voice, create dial plans for your dial-in conferencing access numbers.</span></span> <span data-ttu-id="6c03a-113">ダイヤルイン会議の地域を忘れないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="6c03a-113">Be sure to include a dial-in conferencing region.</span></span> <span data-ttu-id="6c03a-114">詳細な手順については、「 [Lync Server 2013 でダイヤルプランを作成する](lync-server-2013-create-a-dial-plan.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c03a-114">For detailed instructions, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

  - <span data-ttu-id="6c03a-115">エンタープライズ Voip を展開した場合は、必要に応じて、地域を含め、ダイヤルインアクセス番号に適切な正規化ルールを使用するようにエンタープライズ Voip ダイヤルプランを変更します。</span><span class="sxs-lookup"><span data-stu-id="6c03a-115">If you deployed Enterprise Voice, modify Enterprise Voice dial plans as necessary to include regions and use appropriate normalization rules for dial-in access numbers.</span></span> <span data-ttu-id="6c03a-116">詳細な手順については、「 [Modify a dial plan In Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c03a-116">For detailed instructions, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span> <span data-ttu-id="6c03a-117">また、ダイヤルイン アクセス番号のみのために使用する、専用のダイヤル プランを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="6c03a-117">You can also create dedicated dial plans that are used only for dial-in access numbers.</span></span> <span data-ttu-id="6c03a-118">詳細な手順については、「 [Lync Server 2013 でダイヤルプランを作成する](lync-server-2013-create-a-dial-plan.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c03a-118">For detailed instructions, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

<span data-ttu-id="6c03a-119">地域の計画の詳細については、「計画」のドキュメントの「 [Lync Server 2013 のダイヤルイン会議の要件](lync-server-2013-dial-in-conferencing-requirements.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c03a-119">For details about planning regions, see [Dial-in conferencing requirements in Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) in the Planning documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6c03a-120">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="6c03a-120">In This Section</span></span>

  - [<span data-ttu-id="6c03a-121">Lync Server 2013 でのダイヤルプラン情報の表示</span><span class="sxs-lookup"><span data-stu-id="6c03a-121">View dial plan information in Lync Server 2013</span></span>](lync-server-2013-view-dial-plan-information.md)

  - [<span data-ttu-id="6c03a-122">Lync Server 2013 でダイヤルプランを作成する</span><span class="sxs-lookup"><span data-stu-id="6c03a-122">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)

  - [<span data-ttu-id="6c03a-123">Lync Server 2013 でダイヤルプランを変更する</span><span class="sxs-lookup"><span data-stu-id="6c03a-123">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)

  - [<span data-ttu-id="6c03a-124">Lync Server 2013 での正規化ルールの定義</span><span class="sxs-lookup"><span data-stu-id="6c03a-124">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

