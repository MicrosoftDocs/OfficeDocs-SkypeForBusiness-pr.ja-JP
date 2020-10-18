---
title: 'Lync Server 2013: 役割ベースのアクセス制御 (RBAC)'
description: 'Lync Server 2013: 役割ベースのアクセス制御 (RBAC)。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Role-based access control (RBAC) for Lync Server 2013
ms:assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481134(v=OCS.15)
ms:contentKeyID: 59893872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6586517083ff6cd2c4e20d83e9b8f861edf800c0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576583"
---
# <a name="role-based-access-control-rbac-for-lync-server-2013"></a><span data-ttu-id="e3139-103">Lync Server 2013 の役割ベースのアクセス制御 (RBAC)</span><span class="sxs-lookup"><span data-stu-id="e3139-103">Role-based access control (RBAC) for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3139-104">_**トピックの最終更新日:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="e3139-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="e3139-105">Microsoft Lync Server 2013 には、高水準のセキュリティを維持しながら管理タスクを委任できるようにする Role-Based アクセス制御 (RBAC) グループが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e3139-105">Microsoft Lync Server 2013 includes Role-Based Access Control (RBAC) groups to enable you to delegate administrative tasks while maintaining high standards for security.</span></span> <span data-ttu-id="e3139-106">これらのグループはフォレストの準備の際に作成されます。</span><span class="sxs-lookup"><span data-stu-id="e3139-106">These groups are created during forest preparation.</span></span> <span data-ttu-id="e3139-107">フォレストの準備の詳細については、「 [Active Directory Domain Services For Lync Server 2013](lync-server-2013-active-directory-domain-services-for-lync-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3139-107">For details about forest preparation, see [Active Directory Domain Services for Lync Server 2013](lync-server-2013-active-directory-domain-services-for-lync-server.md).</span></span> <span data-ttu-id="e3139-108">フォレストの準備によって作成される特定のグループの詳細については、「展開」のドキュメントの「 [Lync Server 2013 でのフォレストの準備による変更点](lync-server-2013-changes-made-by-forest-preparation.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3139-108">For details about the specific groups created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="e3139-109">RBAC を使用すると、管理者特権が付与されます。これには、多くの一般的な管理タスクをカバーする11の定義済みの役割など、定義済みの管理者の役割を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="e3139-109">With RBAC, administrative privilege is granted by assigning users to pre-defined administrative roles, including the 11 predefined roles that cover many common administrative tasks.</span></span> <span data-ttu-id="e3139-110">各役割は、その役割のユーザーが実行を許可されている Lync Server 管理シェルコマンドレットの特定のリストに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="e3139-110">Each role is associated with a specific list of Lync Server Management Shell cmdlets that users in that role are allowed to run.</span></span> <span data-ttu-id="e3139-111">RBAC を使用すると、"最小限の特権" の原則に従うことができます。ユーザーには、ジョブに必要な管理機能のみが与えられます。</span><span class="sxs-lookup"><span data-stu-id="e3139-111">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative abilities that their jobs require.</span></span> <span data-ttu-id="e3139-112">詳細については、「計画」のドキュメントの「 [Lync Server 2013 でのロールベースのアクセス制御の計画](lync-server-2013-planning-for-role-based-access-control.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3139-112">For details, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

