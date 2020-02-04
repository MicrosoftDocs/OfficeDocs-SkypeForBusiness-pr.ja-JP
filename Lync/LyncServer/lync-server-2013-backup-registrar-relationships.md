---
title: 'Lync Server 2013: バックアップ レジストラー関係'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup Registrar relationships
ms:assetid: 7e078271-84b9-4666-989c-c4507a0cdf4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205033(v=OCS.15)
ms:contentKeyID: 48184631
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44111dbdec945e525b1ef54d910e1cf7f3b5a5d0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730347"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-registrar-relationships-in-lync-server-2013"></a><span data-ttu-id="b33f8-102">Lync Server 2013 のバックアップ レジストラー関係</span><span class="sxs-lookup"><span data-stu-id="b33f8-102">Backup Registrar relationships in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b33f8-103">_**最終更新日:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="b33f8-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="b33f8-104">障害復旧の機能を提供するほか、ペアになった 2 つのプールは互いにバックアップ レジストラーの役割も果たします。</span><span class="sxs-lookup"><span data-stu-id="b33f8-104">In addition to providing disaster recovery ability, two paired pools serve as the backup Registrars for each other.</span></span> <span data-ttu-id="b33f8-105">Lync Server 2013 では、フロントエンドプール間のバックアップレジストラーの関係は、常に1:1 と逆数になります。</span><span class="sxs-lookup"><span data-stu-id="b33f8-105">In Lync Server 2013, backup Registrar relationships between Front End pools are always 1:1 and reciprocal.</span></span> <span data-ttu-id="b33f8-106">つまり、P1 が P2 のバックアップである場合、P2 は P1 のバックアップである必要があります。また、その他のフロントエンドプールのバックアップを行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="b33f8-106">This means that if P1 is the backup for P2, then P2 must be the backup for P1, and neither can be the backup for any other Front End pool.</span></span> <span data-ttu-id="b33f8-107">これは、Lync Server 2010 からの変更であり、フロントエンドプールのバックアップ関係は何度でもかまいません。</span><span class="sxs-lookup"><span data-stu-id="b33f8-107">This is a change from Lync Server 2010, in which Front End pool backup relationships could be many to one.</span></span>

<span data-ttu-id="b33f8-108">2つのフロントエンドプール間のバックアップリレーションシップは1:1 と対称である必要がありますが、Lync Server 2010 の場合と同様に、各フロントエンドプールも、任意の数の Survivable Branch アプライアンスのバックアップレジストラーにすることができます。</span><span class="sxs-lookup"><span data-stu-id="b33f8-108">Even though backup relationships between two Front End pools must be 1:1 and symmetrical, each Front End pool can still also be the backup registrar for any number of Survivable Branch Appliances, just as in Lync Server 2010.</span></span>

<span data-ttu-id="b33f8-109">Lync Server 2013 は、Survivable Branch アプライアンスをホームにしているユーザーに対して、障害回復のサポートを拡張しないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b33f8-109">Note that Lync Server 2013 does not extend disaster recovery support to users homed on a Survivable Branch Appliance.</span></span> <span data-ttu-id="b33f8-110">Survivable Branch アプライアンスのバックアップとして機能するフロントエンドプールがダウンしている場合は、フロントエンドプールに所属しているユーザーが、バックアップフロントエンドプールにフェールオーバーした後でも、Survivable Branch アプライアンスにサインインしたユーザーは復元性モードになります。</span><span class="sxs-lookup"><span data-stu-id="b33f8-110">If a Front End pool that serves as the backup for a Survivable Branch Appliance goes down, users signed into the Survivable Branch Appliance fall into resiliency mode even after users homed on the Front End pool are failed over to the backup Front End pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

