---
title: トポロジ ビルダーを使用して高可用性と障害回復を構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Topology Builder to configure high availability and disaster recovery
ms:assetid: abc1a25d-1f5e-46ef-91d2-0144fc847206
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205172(v=OCS.15)
ms:contentKeyID: 48185113
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b167ea64f42510febe0f405d15e2eafab7efc2bd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848261"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-topology-builder-to-configure-high-availability-and-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="0b548-102">Lync Server 2013 でトポロジ ビルダーを使用して高可用性と障害回復を構成する</span><span class="sxs-lookup"><span data-stu-id="0b548-102">Using Topology Builder to configure high availability and disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b548-103">_**最終更新日:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="0b548-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="0b548-104">[トポロジビルダー] で次の手順を実行して、常設チャットサーバーの高可用性と障害回復を構成します。</span><span class="sxs-lookup"><span data-stu-id="0b548-104">Perform the following steps within Topology Builder to configure high availability and disaster recovery for Persistent Chat Server.</span></span>

1.  <span data-ttu-id="0b548-105">ミラーデータベースとログ配布のセカンダリデータベース SQL Server ストアを追加します。</span><span class="sxs-lookup"><span data-stu-id="0b548-105">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>

2.  <span data-ttu-id="0b548-106">常設チャットサーバーサービスのプロパティを編集するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0b548-106">Edit the Persistent Chat Server service properties to:</span></span>
    
    1.  <span data-ttu-id="0b548-107">プライマリ データベースのミラーリングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="0b548-107">Enable mirroring for the primary database.</span></span>
    
    2.  <span data-ttu-id="0b548-108">プライマリミラー SQL Server ストアを追加します。</span><span class="sxs-lookup"><span data-stu-id="0b548-108">Add the primary mirror SQL Server store.</span></span>
    
    3.  <span data-ttu-id="0b548-109">SQL Server のログ配布データベースを有効にします。</span><span class="sxs-lookup"><span data-stu-id="0b548-109">Enable the SQL Server Log Shipping database.</span></span>
    
    4.  <span data-ttu-id="0b548-110">SQL Server ログ配布のセカンダリ SQL Server ストアを追加します。</span><span class="sxs-lookup"><span data-stu-id="0b548-110">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    5.  <span data-ttu-id="0b548-111">セカンダリデータベースの SQL Server ストアミラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="0b548-111">Add the SQL Server store mirror for the secondary database.</span></span>
    
    6.  <span data-ttu-id="0b548-112">トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="0b548-112">Publish the topology.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

