---
title: 'Lync Server 2013: Lync Server で使用される Active Directory スキーマの拡張、クラス、属性'
description: 'Lync Server 2013: Lync Server で使用される Active Directory スキーマの拡張、クラス、および属性。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory schema extensions, classes, and attributes used by Lync Server 2013
ms:assetid: 579bfa5a-9443-46dd-9a8e-07d00ba2824d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398379(v=OCS.15)
ms:contentKeyID: 48184188
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: beac778d3315573f4d5cc6cb9c827a3a2fce9d0e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567953"
---
# <a name="active-directory-schema-extensions-classes-and-attributes-used-by-lync-server-2013"></a><span data-ttu-id="e28d1-103">Lync Server 2013 で使用される Active Directory スキーマの拡張、クラス、属性</span><span class="sxs-lookup"><span data-stu-id="e28d1-103">Active Directory schema extensions, classes, and attributes used by Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e28d1-104">_**トピックの最終更新日:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="e28d1-104">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="e28d1-105">このリファレンス セクションの内容は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e28d1-105">This reference section includes the following information:</span></span>

  - <span data-ttu-id="e28d1-106">Lync Server 2013 の新しいまたは変更された Active Directory スキーマ拡張機能</span><span class="sxs-lookup"><span data-stu-id="e28d1-106">Active Directory schema extensions that are new or changed for Lync Server 2013</span></span>
    
    <span data-ttu-id="e28d1-107">Active directory のスキーマには、Active Directory フォレストで作成できるすべてのオブジェクトクラスの正式な定義が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e28d1-107">The Active Directory schema contains formal definitions of every object class that can be created in an Active Directory forest.</span></span> <span data-ttu-id="e28d1-108">このスキーマには、Active Directory オブジェクトに存在するすべての属性の正式な定義も含まれています。</span><span class="sxs-lookup"><span data-stu-id="e28d1-108">The schema also contains formal definitions of every attribute that can exist on an Active Directory object.</span></span> <span data-ttu-id="e28d1-109">Active Directory のグローバルカタログには、フォレストのすべてのオブジェクトのレプリカと、各オブジェクトの属性のサブセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e28d1-109">The Active Directory global catalog contains replicas of all the objects for the forest, along with a subset of the attributes for each object.</span></span> <span data-ttu-id="e28d1-110">このセクションでは、Lync Server 2013 で新規または変更されたクラスと属性について説明します。</span><span class="sxs-lookup"><span data-stu-id="e28d1-110">This section describes the classes and attributes that are new or changed in Lync Server 2013.</span></span>

  - <span data-ttu-id="e28d1-111">Lync Server で使用されるすべてのクラスと、それぞれについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e28d1-111">All the classes used by Lync Server, with a description of each</span></span>

  - <span data-ttu-id="e28d1-112">Lync Server で使用されるすべての属性と、それぞれの説明</span><span class="sxs-lookup"><span data-stu-id="e28d1-112">All the attributes used by Lync Server, with a description of each</span></span>

  - <span data-ttu-id="e28d1-113">Lync Server で使用されるクラスの一覧。それぞれに含まれる可能性のある属性</span><span class="sxs-lookup"><span data-stu-id="e28d1-113">A list of the classes used by Lync Server, with the attributes each may contain</span></span>

  - <span data-ttu-id="e28d1-114">グローバル設定とオブジェクト、およびフォレストの準備中に作成されたユニバーサル サービス グループとユニバーサル管理グループ</span><span class="sxs-lookup"><span data-stu-id="e28d1-114">Global settings and objects, in addition to the universal service and administration groups that are created during forest preparation</span></span>

  - <span data-ttu-id="e28d1-115">ドメインの準備中にドメイン ルートおよび組み込みコンテナーに作成されたアクセス制御エントリ (ACE)</span><span class="sxs-lookup"><span data-stu-id="e28d1-115">Access control entries (ACEs) that are created on the domain root and built-in containers during domain preparation</span></span>

  - <span data-ttu-id="e28d1-116">Active Directory の組織単位 (OU) に対して、 \_ cssetuppermission コマンドレットの付与によって加えられた変更。</span><span class="sxs-lookup"><span data-stu-id="e28d1-116">Changes that are made on an Active Directory organizational unit (OU) by the Grant\_CsSetupPermission cmdlet.</span></span>

  - <span data-ttu-id="e28d1-117">Active Directory OU に対して、 \_ csoupermission コマンドレットの付与によって加えられた変更。</span><span class="sxs-lookup"><span data-stu-id="e28d1-117">Changes that are made on an Active Directory OU by the Grant\_CsOUPermission cmdlet.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e28d1-118">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e28d1-118">In This Section</span></span>

  - [<span data-ttu-id="e28d1-119">Lync Server 2013 でのスキーマの変更</span><span class="sxs-lookup"><span data-stu-id="e28d1-119">Schema changes in Lync Server 2013</span></span>](lync-server-2013-schema-changes-in-lync-server-2013.md)

  - [<span data-ttu-id="e28d1-120">Lync Server 2013 のスキーマクラスと説明</span><span class="sxs-lookup"><span data-stu-id="e28d1-120">Schema classes and descriptions in Lync Server 2013</span></span>](lync-server-2013-schema-classes-and-descriptions.md)

  - [<span data-ttu-id="e28d1-121">Lync Server 2013 のスキーマの属性と説明</span><span class="sxs-lookup"><span data-stu-id="e28d1-121">Schema attributes and descriptions in Lync Server 2013</span></span>](lync-server-2013-schema-attributes-and-descriptions.md)

  - [<span data-ttu-id="e28d1-122">Lync Server 2013 のクラスごとのスキーマの属性</span><span class="sxs-lookup"><span data-stu-id="e28d1-122">Schema attributes by class in Lync Server 2013</span></span>](lync-server-2013-schema-attributes-by-class.md)

  - [<span data-ttu-id="e28d1-123">Lync Server 2013 でのフォレストの準備によって加えられた変更</span><span class="sxs-lookup"><span data-stu-id="e28d1-123">Changes made by forest preparation in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-forest-preparation.md)

  - [<span data-ttu-id="e28d1-124">Lync Server 2013 のドメインの準備によって加えられた変更</span><span class="sxs-lookup"><span data-stu-id="e28d1-124">Changes made by domain preparation in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-domain-preparation.md)

  - [<span data-ttu-id="e28d1-125">Lync Server 2013 での Grant-CsSetupPermission による変更</span><span class="sxs-lookup"><span data-stu-id="e28d1-125">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission)

  - [<span data-ttu-id="e28d1-126">Lync Server 2013 での Grant-CsOUPermission による変更</span><span class="sxs-lookup"><span data-stu-id="e28d1-126">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission)

</div>

</div>

<span> </span>

</div>

</div>

</div>

