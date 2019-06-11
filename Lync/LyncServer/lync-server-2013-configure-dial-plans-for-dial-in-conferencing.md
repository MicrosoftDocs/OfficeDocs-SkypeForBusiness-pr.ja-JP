---
title: 'Lync Server 2013: ダイヤルイン会議のダイヤル プランの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure dial plans for dial-in conferencing
ms:assetid: a3e0958e-384f-43e5-b4c9-686b6ecac7ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412768(v=OCS.15)
ms:contentKeyID: 48185051
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11424148db609fa8225b6c98d1de52fa360eb044
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840389"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dial-plans-for-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="5d882-102">Lync Server 2013 でのダイヤルイン会議のダイヤル プランの構成</span><span class="sxs-lookup"><span data-stu-id="5d882-102">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d882-103">_**最終更新日:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="5d882-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="5d882-104">ダイヤルイン会議を展開するときに、ダイヤルインアクセス用電話番号をルーティングするための1つ以上のダイヤルプランを作成または変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d882-104">When you deploy dial-in conferencing, you need to create or modify one or more dial plans for routing dial-in access phone numbers.</span></span> <span data-ttu-id="5d882-105">各ダイヤルプランの少なくとも1つの正規化ルールによって、電話の内線番号が E.i 形式で完全な電話番号に変換されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="5d882-105">Make sure that at least one normalization rule in each dial plan converts telephone extensions into complete phone numbers in E.164 format.</span></span> <span data-ttu-id="5d882-106">ダイヤルイン会議のユーザーは、自らの暗証番号 (PIN) と電話番号を入力することで、認証されたエンタープライズ ユーザーとして会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="5d882-106">Users of dial-in conferencing join conferences as authenticated enterprise users by entering their personal identification number (PIN) and their phone number.</span></span> <span data-ttu-id="5d882-107">内線番号を総合的な電話番号に変化する正規化ルールを管理者が定義する必要があり、その結果、ユーザーは内線番号のみを入力したときに認証を受けることができます。</span><span class="sxs-lookup"><span data-stu-id="5d882-107">You need a normalization rule to convert extensions into complete phone numbers so that users can be authenticated when they enter just a telephone extension.</span></span>

<span data-ttu-id="5d882-108">ダイヤルイン会議のダイヤルプランをセットアップするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5d882-108">To set up dial plans for dial-in conferencing, do the following:</span></span>

  - <span data-ttu-id="5d882-109">エンタープライズ VoIP を展開するかどうかに関係なく、グローバル ダイヤル プランを変更して、ダイヤルイン会議の地域を追加し、正規化ルールによりダイヤルイン アクセス番号が正確に変換されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5d882-109">Whether or not you deploy Enterprise Voice, modify the global dial plan to add a dial-in conferencing region and to make sure that a normalization rule accurately converts your dial-in access numbers.</span></span> <span data-ttu-id="5d882-110">詳細な手順については、「 [Lync Server 2013 でダイヤルプランを変更する](lync-server-2013-modify-a-dial-plan.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d882-110">For detailed instructions, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

  - <span data-ttu-id="5d882-111">エンタープライズ VoIP が展開されていない場合は、ダイヤルイン会議のアクセス電話番号に対応するダイヤル プランを作成します。</span><span class="sxs-lookup"><span data-stu-id="5d882-111">If you did not deploy Enterprise Voice, create dial plans for your dial-in conferencing access numbers.</span></span> <span data-ttu-id="5d882-112">ダイヤルイン会議の地域を忘れないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="5d882-112">Be sure to include a dial-in conferencing region.</span></span> <span data-ttu-id="5d882-113">詳細な手順については、「 [Lync Server 2013 でダイヤルプランを作成](lync-server-2013-create-a-dial-plan.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d882-113">For detailed instructions, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

  - <span data-ttu-id="5d882-114">エンタープライズ VoIP が展開されている場合は、必要に応じてエンタープライズ VoIP を変更して地域を含め、ダイヤルイン アクセス番号のための適切な正規化ルールを使用します。</span><span class="sxs-lookup"><span data-stu-id="5d882-114">If you deployed Enterprise Voice, modify Enterprise Voice dial plans as necessary to include regions and use appropriate normalization rules for dial-in access numbers.</span></span> <span data-ttu-id="5d882-115">詳細な手順については、「 [Lync Server 2013 でダイヤルプランを変更する](lync-server-2013-modify-a-dial-plan.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d882-115">For detailed instructions, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span> <span data-ttu-id="5d882-116">また、ダイヤルイン アクセス番号のみのために使用する、専用のダイヤル プランを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="5d882-116">You can also create dedicated dial plans that are used only for dial-in access numbers.</span></span> <span data-ttu-id="5d882-117">詳細な手順については、「 [Lync Server 2013 でダイヤルプランを作成](lync-server-2013-create-a-dial-plan.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d882-117">For detailed instructions, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

<span data-ttu-id="5d882-118">計画地域の詳細については、計画ドキュメントの「 [Lync Server 2013 でのダイヤルイン会議の要件](lync-server-2013-dial-in-conferencing-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d882-118">For details about planning regions, see [Dial-in conferencing requirements in Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) in the Planning documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5d882-119">このセクション中</span><span class="sxs-lookup"><span data-stu-id="5d882-119">In This Section</span></span>

  - [<span data-ttu-id="5d882-120">Lync Server 2013 でのダイヤルプラン情報の表示</span><span class="sxs-lookup"><span data-stu-id="5d882-120">View dial plan information in Lync Server 2013</span></span>](lync-server-2013-view-dial-plan-information.md)

  - [<span data-ttu-id="5d882-121">Lync Server 2013 でダイヤルプランを作成する</span><span class="sxs-lookup"><span data-stu-id="5d882-121">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)

  - [<span data-ttu-id="5d882-122">Lync Server 2013 でのダイヤル プランの変更</span><span class="sxs-lookup"><span data-stu-id="5d882-122">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)

  - [<span data-ttu-id="5d882-123">Lync Server 2013 の正規化ルールの定義</span><span class="sxs-lookup"><span data-stu-id="5d882-123">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

