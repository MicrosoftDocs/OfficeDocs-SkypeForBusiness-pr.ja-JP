---
title: Lync Server 2013 の中央管理ストアのフェールオーバー
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
ms.openlocfilehash: 38bde96b74fa1c00fc937a159c5e8e40df42d4dc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736867"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="central-management-store-failover-in-lync-server-2013"></a><span data-ttu-id="6fc34-102">Lync Server 2013 の中央管理ストアのフェールオーバー</span><span class="sxs-lookup"><span data-stu-id="6fc34-102">Central Management store failover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6fc34-103">_**最終更新日:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="6fc34-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="6fc34-104">全体管理ストアには、Lync 2013 展開のサーバーとサービスに関する構成データが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6fc34-104">The Central Management store contains configuration data about servers and services in your Lync 2013 deployment.</span></span> <span data-ttu-id="6fc34-105">これにより、Lync 2013 の展開を定義、セットアップ、管理、管理、説明、操作するために必要なデータの堅牢な schematized ストレージが提供されます。</span><span class="sxs-lookup"><span data-stu-id="6fc34-105">It provides a robust, schematized storage of the data needed to define, set up, maintain, administer, describe, and operate a Lync 2013 deployment.</span></span> <span data-ttu-id="6fc34-106">また、データを検証して構成の一貫性を保ちます。</span><span class="sxs-lookup"><span data-stu-id="6fc34-106">It also validates the data to ensure configuration consistency.</span></span>

<span data-ttu-id="6fc34-107">各 Lync 展開には1つの一元管理ストアが含まれています。これは、1つのフロントエンドプールのバックエンドサーバーによってホストされます。</span><span class="sxs-lookup"><span data-stu-id="6fc34-107">Each Lync deployment includes one Central Management store, which is hosted by the Back End Server of one Front End pool.</span></span>

<span data-ttu-id="6fc34-108">一元管理ストアをホストしているプールを含むプールのペアリングを確立すると、バックアッププールにバックアップ全体管理ストアデータベースがセットアップされ、中央管理ストアサービスが両方のプールにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="6fc34-108">When you establish a pool pairing that includes the pool hosting the Central Management store, a backup Central Management store database is set up in the backup pool, and Central Management store services are installed in both pools.</span></span> <span data-ttu-id="6fc34-109">任意の時点で、2つの中央管理ストアデータベースの一方がアクティブなマスターになり、もう1つはスタンバイ状態になります。</span><span class="sxs-lookup"><span data-stu-id="6fc34-109">At any point in time, one of the two Central Management store databases is the active master, and the other is a standby.</span></span> <span data-ttu-id="6fc34-110">コンテンツは、バックアップサービスによってアクティブなマスターからスタンバイにレプリケートされます。</span><span class="sxs-lookup"><span data-stu-id="6fc34-110">The content is replicated by the Backup Service from the active master to the standby.</span></span>

<span data-ttu-id="6fc34-111">中央管理ストアをホストしているプールに関連するプールのフェールオーバー中に、管理者は、フロントエンドプールをフェールオーバーする前に、中央管理ストアでフェールオーバーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fc34-111">During a pool failover that involves the pools hosting the Central Management store, the administrator must fail over the Central Management store before failing over the Front End pool.</span></span>

<span data-ttu-id="6fc34-112">障害が修復された後に中央管理ストアをフェールバックする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6fc34-112">After the disaster is repaired, it is not necessary to fail back the Central Management store.</span></span> <span data-ttu-id="6fc34-113">修復した後は、元のバックアッププールの中央管理ストアをアクティブなマスターとして残すことができます。</span><span class="sxs-lookup"><span data-stu-id="6fc34-113">After repair, the Central Management store in the original backup pool can remain as the active master.</span></span>

<span data-ttu-id="6fc34-114">中央管理ストアのフェールオーバーのエンジニアリング目標は、5 分の目標復旧時間 (RTO) と 5 分の目標復旧ポイント (RPO) です。</span><span class="sxs-lookup"><span data-stu-id="6fc34-114">The engineering targets for Central Management store failover are 5 minutes for recovery time objective (RTO) and 5 minutes for recovery point objective (RPO).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

