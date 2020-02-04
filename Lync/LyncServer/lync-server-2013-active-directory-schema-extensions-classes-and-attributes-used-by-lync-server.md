---
title: 'Lync Server 2013: Lync Server が使用する Active Directory のスキーマ拡張、クラス、属性'
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
ms.openlocfilehash: 2ec6b3eff05ba27b41488aea49bb0347d058b6f0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735197"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-schema-extensions-classes-and-attributes-used-by-lync-server-2013"></a><span data-ttu-id="ed5a7-102">Lync Server 2013 が使用する Active Directory のスキーマ拡張、クラス、属性</span><span class="sxs-lookup"><span data-stu-id="ed5a7-102">Active Directory schema extensions, classes, and attributes used by Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed5a7-103">_**最終更新日:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="ed5a7-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="ed5a7-104">このリファレンスセクションには、次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ed5a7-104">This reference section includes the following information:</span></span>

  - <span data-ttu-id="ed5a7-105">Lync Server 2013 で新規または変更された Active Directory スキーマの拡張機能</span><span class="sxs-lookup"><span data-stu-id="ed5a7-105">Active Directory schema extensions that are new or changed for Lync Server 2013</span></span>
    
    <span data-ttu-id="ed5a7-106">Active Directory のスキーマには、Active Directory フォレストで作成できるすべてのオブジェクトクラスの正式な定義が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ed5a7-106">The Active Directory schema contains formal definitions of every object class that can be created in an Active Directory forest.</span></span> <span data-ttu-id="ed5a7-107">また、スキーマには、Active Directory オブジェクトに存在できるすべての属性の正式な定義も含まれています。</span><span class="sxs-lookup"><span data-stu-id="ed5a7-107">The schema also contains formal definitions of every attribute that can exist on an Active Directory object.</span></span> <span data-ttu-id="ed5a7-108">Active Directory のグローバルカタログには、フォレストのすべてのオブジェクトのレプリカと、各オブジェクトの属性のサブセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ed5a7-108">The Active Directory global catalog contains replicas of all the objects for the forest, along with a subset of the attributes for each object.</span></span> <span data-ttu-id="ed5a7-109">このセクションでは、Lync Server 2013 で新規または変更されたクラスと属性について説明します。</span><span class="sxs-lookup"><span data-stu-id="ed5a7-109">This section describes the classes and attributes that are new or changed in Lync Server 2013.</span></span>

  - <span data-ttu-id="ed5a7-110">Lync Server で使用されるすべてのクラスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ed5a7-110">All the classes used by Lync Server, with a description of each</span></span>

  - <span data-ttu-id="ed5a7-111">Lync Server で使用されるすべての属性とそれぞれの説明</span><span class="sxs-lookup"><span data-stu-id="ed5a7-111">All the attributes used by Lync Server, with a description of each</span></span>

  - <span data-ttu-id="ed5a7-112">Lync Server で使用されるクラスの一覧と、それぞれに含まれる可能性のある属性</span><span class="sxs-lookup"><span data-stu-id="ed5a7-112">A list of the classes used by Lync Server, with the attributes each may contain</span></span>

  - <span data-ttu-id="ed5a7-113">グローバル設定とオブジェクト、およびフォレストの準備の際に作成されるユニバーサルサービスと管理グループに加えて、</span><span class="sxs-lookup"><span data-stu-id="ed5a7-113">Global settings and objects, in addition to the universal service and administration groups that are created during forest preparation</span></span>

  - <span data-ttu-id="ed5a7-114">ドメインの準備中にドメインルートと組み込みのコンテナー上に作成されるアクセス制御エントリ (Ace)</span><span class="sxs-lookup"><span data-stu-id="ed5a7-114">Access control entries (ACEs) that are created on the domain root and built-in containers during domain preparation</span></span>

  - <span data-ttu-id="ed5a7-115">Active Directory 組織単位 (OU) で実行される変更は、cssetuppermission の付与\_コマンドレットによって行われます。</span><span class="sxs-lookup"><span data-stu-id="ed5a7-115">Changes that are made on an Active Directory organizational unit (OU) by the Grant\_CsSetupPermission cmdlet.</span></span>

  - <span data-ttu-id="ed5a7-116">Active Directory の OU で行われる変更は、"csoupermission の付与\_" コマンドレットによって変更されます。</span><span class="sxs-lookup"><span data-stu-id="ed5a7-116">Changes that are made on an Active Directory OU by the Grant\_CsOUPermission cmdlet.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ed5a7-117">このセクション中</span><span class="sxs-lookup"><span data-stu-id="ed5a7-117">In This Section</span></span>

  - [<span data-ttu-id="ed5a7-118">Lync Server 2013 でのスキーマの変更</span><span class="sxs-lookup"><span data-stu-id="ed5a7-118">Schema changes in Lync Server 2013</span></span>](lync-server-2013-schema-changes-in-lync-server-2013.md)

  - [<span data-ttu-id="ed5a7-119">Lync Server 2013 のスキーマクラスと説明</span><span class="sxs-lookup"><span data-stu-id="ed5a7-119">Schema classes and descriptions in Lync Server 2013</span></span>](lync-server-2013-schema-classes-and-descriptions.md)

  - [<span data-ttu-id="ed5a7-120">Lync Server 2013 でのスキーマの属性と説明</span><span class="sxs-lookup"><span data-stu-id="ed5a7-120">Schema attributes and descriptions in Lync Server 2013</span></span>](lync-server-2013-schema-attributes-and-descriptions.md)

  - [<span data-ttu-id="ed5a7-121">Lync Server 2013 のクラス別のスキーマ属性</span><span class="sxs-lookup"><span data-stu-id="ed5a7-121">Schema attributes by class in Lync Server 2013</span></span>](lync-server-2013-schema-attributes-by-class.md)

  - [<span data-ttu-id="ed5a7-122">Lync Server 2013 でのフォレストの準備によって行われた変更</span><span class="sxs-lookup"><span data-stu-id="ed5a7-122">Changes made by forest preparation in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-forest-preparation.md)

  - [<span data-ttu-id="ed5a7-123">Lync Server 2013 でのドメインの準備によって行われた変更</span><span class="sxs-lookup"><span data-stu-id="ed5a7-123">Changes made by domain preparation in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-domain-preparation.md)

  - [<span data-ttu-id="ed5a7-124">Lync Server 2013 での権限の付与によって行われる変更</span><span class="sxs-lookup"><span data-stu-id="ed5a7-124">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission)

  - [<span data-ttu-id="ed5a7-125">Lync Server 2013 のアクセス許可によって行われた変更</span><span class="sxs-lookup"><span data-stu-id="ed5a7-125">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission)

</div>

</div>

<span> </span>

</div>

</div>

</div>

