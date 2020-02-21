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
ms.openlocfilehash: 876fb58c9e9a953e89c02b3b4ef6bd76255c1d65
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191140"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="cdr-table-details-in-lync-server-2013"></a><span data-ttu-id="65a89-102">Lync Server 2013 の CDR テーブルの詳細</span><span class="sxs-lookup"><span data-stu-id="65a89-102">CDR table details in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65a89-103">_**トピックの最終更新日:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="65a89-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="65a89-104">以下のトピックでは、通話詳細記録 (CDR) データベース スキーマの各テーブル内の列について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="65a89-104">The following topics detail the columns in each of the call detail records (CDR) database schema tables.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="65a89-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="65a89-105">In This Section</span></span>

  - [<span data-ttu-id="65a89-106">Lync Server 2013 のアプリケーションテーブル</span><span class="sxs-lookup"><span data-stu-id="65a89-106">Application table in Lync Server 2013</span></span>](lync-server-2013-application-table.md)

  - [<span data-ttu-id="65a89-107">Lync Server 2013 の CallPriorities テーブル</span><span class="sxs-lookup"><span data-stu-id="65a89-107">CallPriorities table in Lync Server 2013</span></span>](lync-server-2013-callpriorities-table.md)

  - [<span data-ttu-id="65a89-108">Lync Server 2013 の CallType テーブル</span><span class="sxs-lookup"><span data-stu-id="65a89-108">CallType table in Lync Server 2013</span></span>](lync-server-2013-calltype-table.md)

  - [<span data-ttu-id="65a89-109">Lync Server 2013 の ClientVersions テーブル</span><span class="sxs-lookup"><span data-stu-id="65a89-109">ClientVersions table in Lync Server 2013</span></span>](lync-server-2013-clientversions-table.md)

  - [<span data-ttu-id="65a89-110">Lync Server 2013 の ConferenceJoinTimeThresholds テーブル</span><span class="sxs-lookup"><span data-stu-id="65a89-110">ConferenceJoinTimeThresholds table in Lync Server 2013</span></span>](lync-server-2013-conferencejointimethresholds-table.md)

  - [<span data-ttu-id="65a89-111">Lync Server 2013 の ConferenceMessageCount テーブル</span><span class="sxs-lookup"><span data-stu-id="65a89-111">ConferenceMessageCount table in Lync Server 2013</span></span>](lync-server-2013-conferencemessagecount-table.md)

  - [<span data-ttu-id="65a89-112">Lync Server 2013 の会議テーブル</span><span class="sxs-lookup"><span data-stu-id="65a89-112">Conferences table in Lync Server 2013</span></span>](lync-server-2013-conferences-table.md)

  - [<span data-ttu-id="65a89-113">Lync Server 2013 の ConferenceSessionDetails テーブル</span><span class="sxs-lookup"><span data-stu-id="65a89-113">ConferenceSessionDetails table in Lync Server 2013</span></span>](lync-server-2013-conferencesessiondetails-table.md)

  - [<span data-ttu-id="65a89-114">Lync Server 2013 の ConferenceUris テーブル</span><span class="sxs-lookup"><span data-stu-id="65a89-114">ConferenceUris table in Lync Server 2013</span></span>](lync-server-2013-conferenceuris-table.md)

  - [<span data-ttu-id="65a89-115">Lync Server 2013 の ContentTypes テーブル</span><span class="sxs-lookup"><span data-stu-id="65a89-115">ContentTypes table in Lync Server 2013</span></span>](lync-server-2013-contenttypes-table.md)

  - [<span data-ttu-id="65a89-116">Lync Server 2013 の DeRegisterType テーブル</span><span class="sxs-lookup"><span data-stu-id="65a89-116">DeRegisterType table in Lync Server 2013</span></span>](lync-server-2013-deregistertype-table.md)

  - [<span data-ttu-id="65a89-117">Lync Server 2013 の Devices テーブル</span><span class="sxs-lookup"><span data-stu-id="65a89-117">Devices table in Lync Server 2013</span></span>](lync-server-2013-devices-table.md)

  - [<span data-ttu-id="65a89-118">Lync Server 2013 のダイアログテーブル</span><span class="sxs-lookup"><span data-stu-id="65a89-118">Dialogs table in Lync Server 2013</span></span>](lync-server-2013-dialogs-table.md)

  - [<span data-ttu-id="65a89-119">Lync Server 2013 の EdgeServers テーブル</span><span class="sxs-lookup"><span data-stu-id="65a89-119">EdgeServers table in Lync Server 2013</span></span>](lync-server-2013-edgeservers-table.md)

  - [<span data-ttu-id="65a89-120">Lync Server 2013 の ErrorCategory テーブル</span><span class="sxs-lookup"><span data-stu-id="65a89-120">ErrorCategory table in Lync Server 2013</span></span>](lync-server-2013-errorcategory-table.md)

  - [<span data-ttu-id="65a89-121">Lync Server 2013 の ErrorDef テーブル</span><span class="sxs-lookup"><span data-stu-id="65a89-121">ErrorDef table in Lync Server 2013</span></span>](lync-server-2013-errordef-table.md)

  - [<span data-ttu-id="65a89-122">Lync Server 2013 の ErrorReport テーブル</span><span class="sxs-lookup"><span data-stu-id="65a89-122">ErrorReport table in Lync Server 2013</span></span>](lync-server-2013-errorreport-table.md)

  - [<span data-ttu-id="65a89-123">Lync Server 2013 の FileTransfers テーブル</span><span class="sxs-lookup"><span data-stu-id="65a89-123">FileTransfers table in Lync Server 2013</span></span>](lync-server-2013-filetransfers-table.md)

  - [<span data-ttu-id="65a89-124">Lync Server 2013 の FocusJoinsAndLeaves テーブル</span><span class="sxs-lookup"><span data-stu-id="65a89-124">FocusJoinsAndLeaves table in Lync Server 2013</span></span>](lync-server-2013-focusjoinsandleaves-table.md)

  - [<span data-ttu-id="65a89-125">Lync Server 2013 のフロントエンドテーブル</span><span class="sxs-lookup"><span data-stu-id="65a89-125">FrontEnd table in Lync Server 2013</span></span>](lync-server-2013-frontend-table.md)

  - [<span data-ttu-id="65a89-126">Lync Server 2013 のゲートウェイテーブル</span><span class="sxs-lookup"><span data-stu-id="65a89-126">Gateways table in Lync Server 2013</span></span>](lync-server-2013-gateways-table.md)

  - <span data-ttu-id="65a89-127">[Lync Server 2013 の [ハードウェアバージョン表の一覧](lync-server-2013-hardwareversions-table.md)</span><span class="sxs-lookup"><span data-stu-id="65a89-127">[HardwareVersions table in Lync Server 2013](lync-server-2013-hardwareversions-table.md)</span></span>

  - [<span data-ttu-id="65a89-128">Lync Server 2013 の IMReportSummary テーブル</span><span class="sxs-lookup"><span data-stu-id="65a89-128">IMReportSummary table in Lync Server 2013</span></span>](lync-server-2013-imreportsummary-table.md)

  - [<span data-ttu-id="65a89-129">Lync Server 2013 の場所テーブル</span><span class="sxs-lookup"><span data-stu-id="65a89-129">Locations table in Lync Server 2013</span></span>](lync-server-2013-locations-table.md)

  - <span data-ttu-id="65a89-130">[Lync Server 2013 の [製造元の表」](lync-server-2013-manufacturers-table.md)</span><span class="sxs-lookup"><span data-stu-id="65a89-130">[Manufacturers table in Lync Server 2013](lync-server-2013-manufacturers-table.md)</span></span>

  - [<span data-ttu-id="65a89-131">Lync Server 2013 の McuJoinsAndLeaves テーブル</span><span class="sxs-lookup"><span data-stu-id="65a89-131">McuJoinsAndLeaves table in Lync Server 2013</span></span>](lync-server-2013-mcujoinsandleaves-table.md)

  - [<span data-ttu-id="65a89-132">Lync Server 2013 の mcu テーブル</span><span class="sxs-lookup"><span data-stu-id="65a89-132">Mcus table in Lync Server 2013</span></span>](lync-server-2013-mcus-table.md)

  - [<span data-ttu-id="65a89-133">Lync Server 2013 のメディアテーブル</span><span class="sxs-lookup"><span data-stu-id="65a89-133">Media table in Lync Server 2013</span></span>](lync-server-2013-media-table.md)

  - [<span data-ttu-id="65a89-134">Lync Server 2013 の MediaList テーブル</span><span class="sxs-lookup"><span data-stu-id="65a89-134">MediaList table in Lync Server 2013</span></span>](lync-server-2013-medialist-table.md)

  - [<span data-ttu-id="65a89-135">Lync Server 2013 の MediationServers テーブル</span><span class="sxs-lookup"><span data-stu-id="65a89-135">MediationServers table in Lync Server 2013</span></span>](lync-server-2013-mediationservers-table.md)

  - [<span data-ttu-id="65a89-136">Lync Server 2013 の MSMQProcessing テーブル</span><span class="sxs-lookup"><span data-stu-id="65a89-136">MSMQProcessing table in Lync Server 2013</span></span>](lync-server-2013-msmqprocessing-table.md)

  - [<span data-ttu-id="65a89-137">Lync Server 2013 の電話表</span><span class="sxs-lookup"><span data-stu-id="65a89-137">Phones table in Lync Server 2013</span></span>](lync-server-2013-phones-table.md)

  - [<span data-ttu-id="65a89-138">Lync Server 2013 のプールテーブル</span><span class="sxs-lookup"><span data-stu-id="65a89-138">Pools table in Lync Server 2013</span></span>](lync-server-2013-pools-table.md)

  - [<span data-ttu-id="65a89-139">Lync Server 2013 の進捗レポートの表</span><span class="sxs-lookup"><span data-stu-id="65a89-139">ProgressReport table in Lync Server 2013</span></span>](lync-server-2013-progressreport-table.md)

  - [<span data-ttu-id="65a89-140">Lync Server 2013 の PurgeSettings テーブル</span><span class="sxs-lookup"><span data-stu-id="65a89-140">PurgeSettings table in Lync Server 2013</span></span>](lync-server-2013-purgesettings-table.md)

  - [<span data-ttu-id="65a89-141">Lync Server 2013 の登録テーブル</span><span class="sxs-lookup"><span data-stu-id="65a89-141">Registration table in Lync Server 2013</span></span>](lync-server-2013-registration-table.md)

  - [<span data-ttu-id="65a89-142">Lync Server 2013 の Roles テーブル</span><span class="sxs-lookup"><span data-stu-id="65a89-142">Roles table in Lync Server 2013</span></span>](lync-server-2013-roles-table.md)

  - [<span data-ttu-id="65a89-143">Lync Server 2013 のサーバーテーブル</span><span class="sxs-lookup"><span data-stu-id="65a89-143">Servers table in Lync Server 2013</span></span>](lync-server-2013-servers-table.md)

  - [<span data-ttu-id="65a89-144">Lync Server 2013 の SessionDetails テーブル</span><span class="sxs-lookup"><span data-stu-id="65a89-144">SessionDetails table in Lync Server 2013</span></span>](lync-server-2013-sessiondetails-table.md)

  - [<span data-ttu-id="65a89-145">Lync Server 2013 の SIPResponseMetaData テーブル</span><span class="sxs-lookup"><span data-stu-id="65a89-145">SIPResponseMetaData table in Lync Server 2013</span></span>](lync-server-2013-sipresponsemetadata-table.md)

  - [<span data-ttu-id="65a89-146">Lync Server 2013 の Syndicators テーブル</span><span class="sxs-lookup"><span data-stu-id="65a89-146">Syndicators table in Lync Server 2013</span></span>](lync-server-2013-syndicators-table.md)

  - [<span data-ttu-id="65a89-147">Lync Server 2013 の SyndicatorsTenantMap テーブル</span><span class="sxs-lookup"><span data-stu-id="65a89-147">SyndicatorsTenantMap table in Lync Server 2013</span></span>](lync-server-2013-syndicatorstenantmap-table.md)

  - [<span data-ttu-id="65a89-148">Lync Server 2013 のタスクテーブル</span><span class="sxs-lookup"><span data-stu-id="65a89-148">Task table in Lync Server 2013</span></span>](lync-server-2013-task-table.md)

  - [<span data-ttu-id="65a89-149">Lync Server 2013 のテナントテーブル</span><span class="sxs-lookup"><span data-stu-id="65a89-149">Tenants table in Lync Server 2013</span></span>](lync-server-2013-tenants-table.md)

  - [<span data-ttu-id="65a89-150">Lync Server 2013 の UriTypes テーブル</span><span class="sxs-lookup"><span data-stu-id="65a89-150">UriTypes table in Lync Server 2013</span></span>](lync-server-2013-uritypes-table.md)

  - [<span data-ttu-id="65a89-151">Lync Server 2013 のユーザーテーブル</span><span class="sxs-lookup"><span data-stu-id="65a89-151">Users table in Lync Server 2013</span></span>](lync-server-2013-users-table.md)

  - [<span data-ttu-id="65a89-152">Lync Server 2013 の UserAgentDef テーブル</span><span class="sxs-lookup"><span data-stu-id="65a89-152">UserAgentDef table in Lync Server 2013</span></span>](lync-server-2013-useragentdef-table.md)

  - [<span data-ttu-id="65a89-153">Lync Server 2013 の UserStatistics テーブル</span><span class="sxs-lookup"><span data-stu-id="65a89-153">UserStatistics table in Lync Server 2013</span></span>](lync-server-2013-userstatistics-table.md)

  - [<span data-ttu-id="65a89-154">Lync Server 2013 の VoipDetails テーブル</span><span class="sxs-lookup"><span data-stu-id="65a89-154">VoipDetails table in Lync Server 2013</span></span>](lync-server-2013-voipdetails-table.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

