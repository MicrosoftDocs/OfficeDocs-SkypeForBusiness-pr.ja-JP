---
title: Lync Server 2013 中央管理ストアのフェールオーバー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Central Management store failover
ms:assetid: f464d715-68a4-462c-9584-00f41ab10db0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205376(v=OCS.15)
ms:contentKeyID: 48185809
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be877275c2d5f70b7a7038b55f5d42f887ba1739
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008499"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="central-management-store-failover-in-lync-server-2013"></a><span data-ttu-id="c184f-102">Lync Server 2013 での中央管理ストアのフェールオーバー</span><span class="sxs-lookup"><span data-stu-id="c184f-102">Central Management store failover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c184f-103">_**トピックの最終更新日:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="c184f-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="c184f-104">中央管理ストアには、Lync 2013 展開内のサーバーとサービスに関する構成データが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c184f-104">The Central Management store contains configuration data about servers and services in your Lync 2013 deployment.</span></span> <span data-ttu-id="c184f-105">これにより、Lync 2013 展開の定義、設定、管理、管理、説明、および運用に必要なデータの堅牢で schematized ストレージが提供されます。</span><span class="sxs-lookup"><span data-stu-id="c184f-105">It provides a robust, schematized storage of the data needed to define, set up, maintain, administer, describe, and operate a Lync 2013 deployment.</span></span> <span data-ttu-id="c184f-106">また、CMS はこのデータを検証して構成の一貫性も保証します。</span><span class="sxs-lookup"><span data-stu-id="c184f-106">It also validates the data to ensure configuration consistency.</span></span>

<span data-ttu-id="c184f-107">各 Lync 展開には、1つのフロントエンドプールのバックエンドサーバーによってホストされる1つの中央管理ストアが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c184f-107">Each Lync deployment includes one Central Management store, which is hosted by the Back End Server of one Front End pool.</span></span>

<span data-ttu-id="c184f-108">中央管理ストアをホストするプールを含むプールのペアを確立すると、バックアッププールにバックアップ中央管理ストアデータベースがセットアップされ、中央管理ストアサービスが両方のプールにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="c184f-108">When you establish a pool pairing that includes the pool hosting the Central Management store, a backup Central Management store database is set up in the backup pool, and Central Management store services are installed in both pools.</span></span> <span data-ttu-id="c184f-109">いずれかの時点で、2つの中央管理ストアデータベースのうちの1つがアクティブマスターで、もう1つはスタンバイです。</span><span class="sxs-lookup"><span data-stu-id="c184f-109">At any point in time, one of the two Central Management store databases is the active master, and the other is a standby.</span></span> <span data-ttu-id="c184f-110">コンテンツは、バックアップサービスによってアクティブマスターからスタンバイにレプリケートされます。</span><span class="sxs-lookup"><span data-stu-id="c184f-110">The content is replicated by the Backup Service from the active master to the standby.</span></span>

<span data-ttu-id="c184f-111">中央管理ストアをホストしているプールのフェールオーバー中に、管理者はフロントエンドプールをフェールオーバーする前に、中央管理ストアをフェールオーバーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c184f-111">During a pool failover that involves the pools hosting the Central Management store, the administrator must fail over the Central Management store before failing over the Front End pool.</span></span>

<span data-ttu-id="c184f-112">障害が修復された後、中央管理ストアをフェールバックする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c184f-112">After the disaster is repaired, it is not necessary to fail back the Central Management store.</span></span> <span data-ttu-id="c184f-113">修復後は、元のバックアッププールの中央管理ストアをアクティブマスターとして残すことができます。</span><span class="sxs-lookup"><span data-stu-id="c184f-113">After repair, the Central Management store in the original backup pool can remain as the active master.</span></span>

<span data-ttu-id="c184f-114">中央管理ストアのフェールオーバーのためのエンジニアリング目標は、目標復旧時間 (RTO) と5分の目標復旧ポイント (RPO) です。</span><span class="sxs-lookup"><span data-stu-id="c184f-114">The engineering targets for Central Management store failover are 5 minutes for recovery time objective (RTO) and 5 minutes for recovery point objective (RPO).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

