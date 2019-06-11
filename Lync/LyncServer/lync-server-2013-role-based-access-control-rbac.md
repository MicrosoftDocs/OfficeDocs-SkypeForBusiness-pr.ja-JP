---
title: 'Lync Server 2013: 役割ベースのアクセス制御 (RBAC)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Role-based access control (RBAC) for Lync Server 2013
ms:assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481134(v=OCS.15)
ms:contentKeyID: 59893872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75287cd418d22418f8de2c1a1b018eab8cca4e49
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822343"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="role-based-access-control-rbac-for-lync-server-2013"></a><span data-ttu-id="83cc7-102">Lync Server 2013 の役割ベースのアクセス制御 (RBAC)</span><span class="sxs-lookup"><span data-stu-id="83cc7-102">Role-based access control (RBAC) for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83cc7-103">_**最終更新日:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="83cc7-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="83cc7-104">Microsoft Lync Server 2013 には役割ベースのアクセス制御 (RBAC) グループが含まれています。これにより、セキュリティの高水準を維持しながら、管理タスクの委任を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="83cc7-104">Microsoft Lync Server 2013 includes Role-Based Access Control (RBAC) groups to enable you to delegate administrative tasks while maintaining high standards for security.</span></span> <span data-ttu-id="83cc7-105">これらのグループはフォレストの準備の際に作成されます。</span><span class="sxs-lookup"><span data-stu-id="83cc7-105">These groups are created during forest preparation.</span></span> <span data-ttu-id="83cc7-106">フォレストの準備の詳細については、「 [Lync Server 2013 の Active Directory ドメインサービス](lync-server-2013-active-directory-domain-services-for-lync-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83cc7-106">For details about forest preparation, see [Active Directory Domain Services for Lync Server 2013](lync-server-2013-active-directory-domain-services-for-lync-server.md).</span></span> <span data-ttu-id="83cc7-107">フォレストの準備によって作成される特定のグループの詳細については、展開ドキュメントの「 [Lync Server 2013 でのフォレストの準備による変更](lync-server-2013-changes-made-by-forest-preparation.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83cc7-107">For details about the specific groups created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="83cc7-108">RBAC では、管理者特権が与えられているのは、事前に定義された管理者ロールにユーザーを割り当てることによって、多くの一般的な管理タスクに適用される11定義済みのロールを含むことです</span><span class="sxs-lookup"><span data-stu-id="83cc7-108">With RBAC, administrative privilege is granted by assigning users to pre-defined administrative roles, including the 11 predefined roles that cover many common administrative tasks.</span></span> <span data-ttu-id="83cc7-109">各役割は、その役割のユーザーが実行できる Lync Server 管理シェルコマンドレットの特定のリストに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="83cc7-109">Each role is associated with a specific list of Lync Server Management Shell cmdlets that users in that role are allowed to run.</span></span> <span data-ttu-id="83cc7-110">RBAC を使うと、ユーザーに対して、自分のジョブで必要な管理機能のみが与えられる、"最低限の権限" の原則に従うことができます。</span><span class="sxs-lookup"><span data-stu-id="83cc7-110">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative abilities that their jobs require.</span></span> <span data-ttu-id="83cc7-111">詳細については、計画ドキュメントの「 [Lync Server 2013 での役割ベースのアクセス制御の計画](lync-server-2013-planning-for-role-based-access-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83cc7-111">For details, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

