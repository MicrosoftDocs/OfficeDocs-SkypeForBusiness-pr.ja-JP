---
title: 'Lync Server 2013: アーカイブデータベースと監視データベースのバックアップ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up Archiving and Monitoring databases
ms:assetid: c120db81-b02c-4a4c-90cd-8aca6cff64f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202188(v=OCS.15)
ms:contentKeyID: 51541515
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec4f76c0bea6c9ffd98ec0ce6105698dfd3718e3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196940"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backing-up-archiving-and-monitoring-databases-in-lync-server-2013"></a><span data-ttu-id="f7cc9-102">Lync Server 2013 でのアーカイブおよび監視データベースのバックアップ</span><span class="sxs-lookup"><span data-stu-id="f7cc9-102">Backing up Archiving and Monitoring databases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7cc9-103">_**トピックの最終更新日:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="f7cc9-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="f7cc9-104">アーカイブまたは監視を展開した場合は、組織の SQL Server バックアップ ポリシーに従ってこれらのデータベースをバックアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7cc9-104">If you deployed Archiving or Monitoring, you need to back up these databases according to your organization's SQL Server backup policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f7cc9-105">中央管理ストアをバックアップすると、アーカイブと監視の設定がバックアップされます。</span><span class="sxs-lookup"><span data-stu-id="f7cc9-105">The settings for Archiving and Monitoring are backed up when you back up the Central Management store.</span></span> <span data-ttu-id="f7cc9-106">詳細については、「 <A href="lync-server-2013-backing-up-core-data-and-settings.md">Lync Server 2013 でのコアデータと設定のバックアップ</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7cc9-106">For details, see <A href="lync-server-2013-backing-up-core-data-and-settings.md">Backing up core data and settings in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="f7cc9-107">アーカイブおよび監視の場合、SQL Server Management Studio などの SQL Server ツールを使用して手動でのバックアップを行ったり、SQL Server 管理ツールを使用して定期的な自動バックアップをスケジュールしたりできます。</span><span class="sxs-lookup"><span data-stu-id="f7cc9-107">For Archiving and Monitoring, you can use a SQL Server tool such as SQL Server Management Studio to perform a manual backup, or you can use SQL Server management tools to schedule regular, automatic backups.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

