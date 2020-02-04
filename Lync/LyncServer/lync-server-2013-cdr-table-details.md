---
title: 'Lync Server 2013: CDR テーブルの詳細'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: CDR table details
ms:assetid: 896198f5-672b-48ea-852f-0211c0c90857
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398693(v=OCS.15)
ms:contentKeyID: 48184730
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 650caa5244eaf796c066f1388f2fcbb5d3b0703a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736947"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="cdr-table-details-in-lync-server-2013"></a><span data-ttu-id="575f9-102">Lync Server 2013 の CDR テーブルの詳細</span><span class="sxs-lookup"><span data-stu-id="575f9-102">CDR table details in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="575f9-103">_**最終更新日:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="575f9-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="575f9-104">次のトピックでは、各通話詳細レコード (CDR) データベーススキーマテーブルの列について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="575f9-104">The following topics detail the columns in each of the call detail records (CDR) database schema tables.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="575f9-105">このセクション中</span><span class="sxs-lookup"><span data-stu-id="575f9-105">In This Section</span></span>

  - [<span data-ttu-id="575f9-106">Lync Server 2013 の Application テーブル</span><span class="sxs-lookup"><span data-stu-id="575f9-106">Application table in Lync Server 2013</span></span>](lync-server-2013-application-table.md)

  - [<span data-ttu-id="575f9-107">Lync Server 2013 の CallPriorities テーブル</span><span class="sxs-lookup"><span data-stu-id="575f9-107">CallPriorities table in Lync Server 2013</span></span>](lync-server-2013-callpriorities-table.md)

  - [<span data-ttu-id="575f9-108">Lync Server 2013 の CallType テーブル</span><span class="sxs-lookup"><span data-stu-id="575f9-108">CallType table in Lync Server 2013</span></span>](lync-server-2013-calltype-table.md)

  - [<span data-ttu-id="575f9-109">Lync Server 2013 の ClientVersions テーブル</span><span class="sxs-lookup"><span data-stu-id="575f9-109">ClientVersions table in Lync Server 2013</span></span>](lync-server-2013-clientversions-table.md)

  - [<span data-ttu-id="575f9-110">Lync Server 2013 の ConferenceJoinTimeThresholds テーブル</span><span class="sxs-lookup"><span data-stu-id="575f9-110">ConferenceJoinTimeThresholds table in Lync Server 2013</span></span>](lync-server-2013-conferencejointimethresholds-table.md)

  - [<span data-ttu-id="575f9-111">Lync Server 2013 の ConferenceMessageCount テーブル</span><span class="sxs-lookup"><span data-stu-id="575f9-111">ConferenceMessageCount table in Lync Server 2013</span></span>](lync-server-2013-conferencemessagecount-table.md)

  - [<span data-ttu-id="575f9-112">Lync Server 2013 の Conferences テーブル</span><span class="sxs-lookup"><span data-stu-id="575f9-112">Conferences table in Lync Server 2013</span></span>](lync-server-2013-conferences-table.md)

  - [<span data-ttu-id="575f9-113">Lync Server 2013 の ConferenceSessionDetails テーブル</span><span class="sxs-lookup"><span data-stu-id="575f9-113">ConferenceSessionDetails table in Lync Server 2013</span></span>](lync-server-2013-conferencesessiondetails-table.md)

  - [<span data-ttu-id="575f9-114">Lync Server 2013 の ConferenceUris テーブル</span><span class="sxs-lookup"><span data-stu-id="575f9-114">ConferenceUris table in Lync Server 2013</span></span>](lync-server-2013-conferenceuris-table.md)

  - [<span data-ttu-id="575f9-115">Lync Server 2013 の ContentTypes テーブル</span><span class="sxs-lookup"><span data-stu-id="575f9-115">ContentTypes table in Lync Server 2013</span></span>](lync-server-2013-contenttypes-table.md)

  - [<span data-ttu-id="575f9-116">Lync Server 2013 の DeRegisterType テーブル</span><span class="sxs-lookup"><span data-stu-id="575f9-116">DeRegisterType table in Lync Server 2013</span></span>](lync-server-2013-deregistertype-table.md)

  - [<span data-ttu-id="575f9-117">Lync Server 2013 の Devices テーブル</span><span class="sxs-lookup"><span data-stu-id="575f9-117">Devices table in Lync Server 2013</span></span>](lync-server-2013-devices-table.md)

  - [<span data-ttu-id="575f9-118">Lync Server 2013 の Dialogs テーブル</span><span class="sxs-lookup"><span data-stu-id="575f9-118">Dialogs table in Lync Server 2013</span></span>](lync-server-2013-dialogs-table.md)

  - [<span data-ttu-id="575f9-119">Lync Server 2013 の EdgeServers テーブル</span><span class="sxs-lookup"><span data-stu-id="575f9-119">EdgeServers table in Lync Server 2013</span></span>](lync-server-2013-edgeservers-table.md)

  - [<span data-ttu-id="575f9-120">Lync Server 2013 の ErrorCategory テーブル</span><span class="sxs-lookup"><span data-stu-id="575f9-120">ErrorCategory table in Lync Server 2013</span></span>](lync-server-2013-errorcategory-table.md)

  - [<span data-ttu-id="575f9-121">Lync Server 2013 ErrorDef テーブル</span><span class="sxs-lookup"><span data-stu-id="575f9-121">ErrorDef table in Lync Server 2013</span></span>](lync-server-2013-errordef-table.md)

  - [<span data-ttu-id="575f9-122">Lync Server 2013 の ErrorReport テーブル</span><span class="sxs-lookup"><span data-stu-id="575f9-122">ErrorReport table in Lync Server 2013</span></span>](lync-server-2013-errorreport-table.md)

  - [<span data-ttu-id="575f9-123">Lync Server 2013 の FileTransfers テーブル</span><span class="sxs-lookup"><span data-stu-id="575f9-123">FileTransfers table in Lync Server 2013</span></span>](lync-server-2013-filetransfers-table.md)

  - [<span data-ttu-id="575f9-124">Lync Server 2013 の FocusJoinsAndLeaves テーブル</span><span class="sxs-lookup"><span data-stu-id="575f9-124">FocusJoinsAndLeaves table in Lync Server 2013</span></span>](lync-server-2013-focusjoinsandleaves-table.md)

  - [<span data-ttu-id="575f9-125">Lync Server 2013 のフロントエンドテーブル</span><span class="sxs-lookup"><span data-stu-id="575f9-125">FrontEnd table in Lync Server 2013</span></span>](lync-server-2013-frontend-table.md)

  - [<span data-ttu-id="575f9-126">Lync Server 2013 のゲートウェイ テーブル</span><span class="sxs-lookup"><span data-stu-id="575f9-126">Gateways table in Lync Server 2013</span></span>](lync-server-2013-gateways-table.md)

  - [<span data-ttu-id="575f9-127">Lync Server 2013 の HardwareVersions テーブル</span><span class="sxs-lookup"><span data-stu-id="575f9-127">HardwareVersions table in Lync Server 2013</span></span>](lync-server-2013-hardwareversions-table.md)

  - [<span data-ttu-id="575f9-128">Lync Server 2013 の IMReportSummary テーブル</span><span class="sxs-lookup"><span data-stu-id="575f9-128">IMReportSummary table in Lync Server 2013</span></span>](lync-server-2013-imreportsummary-table.md)

  - [<span data-ttu-id="575f9-129">Lync Server 2013 の Locations テーブル</span><span class="sxs-lookup"><span data-stu-id="575f9-129">Locations table in Lync Server 2013</span></span>](lync-server-2013-locations-table.md)

  - [<span data-ttu-id="575f9-130">Lync Server 2013 の Manufacturers テーブル</span><span class="sxs-lookup"><span data-stu-id="575f9-130">Manufacturers table in Lync Server 2013</span></span>](lync-server-2013-manufacturers-table.md)

  - [<span data-ttu-id="575f9-131">Lync Server 2013 の McuJoinsAndLeaves テーブル</span><span class="sxs-lookup"><span data-stu-id="575f9-131">McuJoinsAndLeaves table in Lync Server 2013</span></span>](lync-server-2013-mcujoinsandleaves-table.md)

  - [<span data-ttu-id="575f9-132">Lync Server 2013 の Mcus テーブル</span><span class="sxs-lookup"><span data-stu-id="575f9-132">Mcus table in Lync Server 2013</span></span>](lync-server-2013-mcus-table.md)

  - [<span data-ttu-id="575f9-133">Lync Server 2013 の Media テーブル</span><span class="sxs-lookup"><span data-stu-id="575f9-133">Media table in Lync Server 2013</span></span>](lync-server-2013-media-table.md)

  - [<span data-ttu-id="575f9-134">Lync Server 2013 の MediaList テーブル</span><span class="sxs-lookup"><span data-stu-id="575f9-134">MediaList table in Lync Server 2013</span></span>](lync-server-2013-medialist-table.md)

  - [<span data-ttu-id="575f9-135">Lync Server 2013 の MediationServers テーブル</span><span class="sxs-lookup"><span data-stu-id="575f9-135">MediationServers table in Lync Server 2013</span></span>](lync-server-2013-mediationservers-table.md)

  - [<span data-ttu-id="575f9-136">Lync Server 2013 の MSMQProcessing テーブル</span><span class="sxs-lookup"><span data-stu-id="575f9-136">MSMQProcessing table in Lync Server 2013</span></span>](lync-server-2013-msmqprocessing-table.md)

  - [<span data-ttu-id="575f9-137">Lync Server 2013 の Phones テーブル</span><span class="sxs-lookup"><span data-stu-id="575f9-137">Phones table in Lync Server 2013</span></span>](lync-server-2013-phones-table.md)

  - [<span data-ttu-id="575f9-138">Lync Server 2013 の Pools テーブル</span><span class="sxs-lookup"><span data-stu-id="575f9-138">Pools table in Lync Server 2013</span></span>](lync-server-2013-pools-table.md)

  - [<span data-ttu-id="575f9-139">Lync Server 2013 の ProgressReport テーブル</span><span class="sxs-lookup"><span data-stu-id="575f9-139">ProgressReport table in Lync Server 2013</span></span>](lync-server-2013-progressreport-table.md)

  - [<span data-ttu-id="575f9-140">Lync Server 2013 の PurgeSettings テーブル</span><span class="sxs-lookup"><span data-stu-id="575f9-140">PurgeSettings table in Lync Server 2013</span></span>](lync-server-2013-purgesettings-table.md)

  - [<span data-ttu-id="575f9-141">Lync Server 2013 の Registration テーブル</span><span class="sxs-lookup"><span data-stu-id="575f9-141">Registration table in Lync Server 2013</span></span>](lync-server-2013-registration-table.md)

  - [<span data-ttu-id="575f9-142">Lync Server 2013 の Roles テーブル</span><span class="sxs-lookup"><span data-stu-id="575f9-142">Roles table in Lync Server 2013</span></span>](lync-server-2013-roles-table.md)

  - [<span data-ttu-id="575f9-143">Lync Server 2013 の Servers テーブル</span><span class="sxs-lookup"><span data-stu-id="575f9-143">Servers table in Lync Server 2013</span></span>](lync-server-2013-servers-table.md)

  - [<span data-ttu-id="575f9-144">Lync Server 2013 の SessionDetails テーブル</span><span class="sxs-lookup"><span data-stu-id="575f9-144">SessionDetails table in Lync Server 2013</span></span>](lync-server-2013-sessiondetails-table.md)

  - [<span data-ttu-id="575f9-145">Lync Server 2013 の SIPResponseMetaData テーブル</span><span class="sxs-lookup"><span data-stu-id="575f9-145">SIPResponseMetaData table in Lync Server 2013</span></span>](lync-server-2013-sipresponsemetadata-table.md)

  - [<span data-ttu-id="575f9-146">Lync Server 2013 の Syndicators テーブル</span><span class="sxs-lookup"><span data-stu-id="575f9-146">Syndicators table in Lync Server 2013</span></span>](lync-server-2013-syndicators-table.md)

  - [<span data-ttu-id="575f9-147">Lync Server 2013 の SyndicatorsTenantMap テーブル</span><span class="sxs-lookup"><span data-stu-id="575f9-147">SyndicatorsTenantMap table in Lync Server 2013</span></span>](lync-server-2013-syndicatorstenantmap-table.md)

  - [<span data-ttu-id="575f9-148">Lync Server 2013 のタスクテーブル</span><span class="sxs-lookup"><span data-stu-id="575f9-148">Task table in Lync Server 2013</span></span>](lync-server-2013-task-table.md)

  - [<span data-ttu-id="575f9-149">Lync Server 2013 の Tenants テーブル</span><span class="sxs-lookup"><span data-stu-id="575f9-149">Tenants table in Lync Server 2013</span></span>](lync-server-2013-tenants-table.md)

  - [<span data-ttu-id="575f9-150">Lync Server 2013 の UriTypes テーブル</span><span class="sxs-lookup"><span data-stu-id="575f9-150">UriTypes table in Lync Server 2013</span></span>](lync-server-2013-uritypes-table.md)

  - [<span data-ttu-id="575f9-151">Lync Server 2013 のユーザー テーブル</span><span class="sxs-lookup"><span data-stu-id="575f9-151">Users table in Lync Server 2013</span></span>](lync-server-2013-users-table.md)

  - [<span data-ttu-id="575f9-152">Lync Server 2013 の UserAgentDef テーブル</span><span class="sxs-lookup"><span data-stu-id="575f9-152">UserAgentDef table in Lync Server 2013</span></span>](lync-server-2013-useragentdef-table.md)

  - [<span data-ttu-id="575f9-153">Lync Server 2013 の UserStatistics テーブル</span><span class="sxs-lookup"><span data-stu-id="575f9-153">UserStatistics table in Lync Server 2013</span></span>](lync-server-2013-userstatistics-table.md)

  - [<span data-ttu-id="575f9-154">Lync Server 2013 の VoipDetails テーブル</span><span class="sxs-lookup"><span data-stu-id="575f9-154">VoipDetails table in Lync Server 2013</span></span>](lync-server-2013-voipdetails-table.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

