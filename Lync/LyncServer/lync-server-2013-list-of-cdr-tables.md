---
title: 'Lync Server 2013: CDR テーブルのリスト'
description: 'Lync Server 2013: CDR テーブルのリスト。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of CDR tables
ms:assetid: 031843fd-c7ff-4534-9b02-8847aad70807
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398084(v=OCS.15)
ms:contentKeyID: 48183254
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21d0f683ffeb0f5f1cbba5db4c45d248aa14e8e4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558703"
---
# <a name="list-of-cdr-tables-in-lync-server-2013"></a><span data-ttu-id="95015-103">Lync Server 2013 の CDR テーブルの一覧</span><span class="sxs-lookup"><span data-stu-id="95015-103">List of CDR tables in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95015-104">_**トピックの最終更新日:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="95015-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="95015-105">通話詳細記録 (CDR) データベース スキーマは、次のテーブルで構成されています。</span><span class="sxs-lookup"><span data-stu-id="95015-105">The call detail recording (CDR) database schema consists of the following tables.</span></span>

<div>

## <a name="static-tables"></a><span data-ttu-id="95015-106">静的テーブル</span><span class="sxs-lookup"><span data-stu-id="95015-106">Static Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="95015-107">Table</span><span class="sxs-lookup"><span data-stu-id="95015-107">Table</span></span></th>
<th><span data-ttu-id="95015-108">説明</span><span class="sxs-lookup"><span data-stu-id="95015-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="95015-109"><a href="lync-server-2013-callpriorities-table.md">Lync Server 2013 の CallPriorities テーブル</a></span><span class="sxs-lookup"><span data-stu-id="95015-109"><a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95015-110">可能な通話優先順位の一覧を格納します (緊急、至急、通常、非至急など)。</span><span class="sxs-lookup"><span data-stu-id="95015-110">Stores the list of possible call priorities, such as emergency, urgent, normal, non-urgent, and more.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95015-111"><a href="lync-server-2013-conferencejointimethresholds-table.md">Lync Server 2013 の ConferenceJoinTimeThresholds テーブル</a></span><span class="sxs-lookup"><span data-stu-id="95015-111"><a href="lync-server-2013-conferencejointimethresholds-table.md">ConferenceJoinTimeThresholds table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95015-112">電話会議参加時間の概要レポートで使用される分類の境界を格納します。</span><span class="sxs-lookup"><span data-stu-id="95015-112">Stores the classification boundaries used by the Conference Join Time Summary Report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95015-113"><a href="lync-server-2013-deregistertype-table.md">Lync Server 2013 の DeRegisterType テーブル</a></span><span class="sxs-lookup"><span data-stu-id="95015-113"><a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95015-114">ユーザーが開始した &quot; 、 &quot; &quot; 登録期限切れ、クライアントクラッシュなど、ユーザーに対して発生する可能性のある登録解除の理由の一覧を格納 &quot; &quot; &quot; します。</span><span class="sxs-lookup"><span data-stu-id="95015-114">Stores the list of possible user de-register reasons, such as &quot;client initiated,&quot; &quot;registration expired,&quot; &quot;client crash,&quot; and more.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95015-115"><a href="lync-server-2013-medialist-table.md">Lync Server 2013 の MediaList テーブル</a></span><span class="sxs-lookup"><span data-stu-id="95015-115"><a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95015-116">データベースのエントリを生成できるメディアの種類の一覧を格納します (IM、音声、ビデオ、ファイル送信など)。</span><span class="sxs-lookup"><span data-stu-id="95015-116">Stores the list of media types that can generate entries in the database (for example, IM, audio, video, and file transfer).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95015-117"><a href="lync-server-2013-purgesettings-table.md">Lync Server 2013 の PurgeSettings テーブル</a></span><span class="sxs-lookup"><span data-stu-id="95015-117"><a href="lync-server-2013-purgesettings-table.md">PurgeSettings table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95015-118">通話詳細記録を CDR データベースから自動的に削除するかどうか (削除する場合はそのタイミング) を指定する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="95015-118">Stores information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95015-119"><a href="lync-server-2013-roles-table.md">Lync Server 2013 の Roles テーブル</a></span><span class="sxs-lookup"><span data-stu-id="95015-119"><a href="lync-server-2013-roles-table.md">Roles table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95015-120">可能な電話会議の役割の一覧を格納します (参加者、発表者など)。</span><span class="sxs-lookup"><span data-stu-id="95015-120">Stores the list of possible conference roles (for example, attendee and presenter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95015-121"><a href="lync-server-2013-sipresponsemetadata-table.md">Lync Server 2013 の SIPResponseMetaData テーブル</a></span><span class="sxs-lookup"><span data-stu-id="95015-121"><a href="lync-server-2013-sipresponsemetadata-table.md">SIPResponseMetaData table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95015-122">SIP 応答コードの一覧と、それらの各コードの分類および定義を格納します。</span><span class="sxs-lookup"><span data-stu-id="95015-122">Stores a list of SIP response codes and the classification and definition of each of those codes.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supporting-tables"></a><span data-ttu-id="95015-123">サポート テーブル</span><span class="sxs-lookup"><span data-stu-id="95015-123">Supporting Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="95015-124">Table</span><span class="sxs-lookup"><span data-stu-id="95015-124">Table</span></span></th>
<th><span data-ttu-id="95015-125">説明</span><span class="sxs-lookup"><span data-stu-id="95015-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="95015-126"><a href="lync-server-2013-clientversions-table.md">Lync Server 2013 の ClientVersions テーブル</a></span><span class="sxs-lookup"><span data-stu-id="95015-126"><a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95015-127">通話に関わった各クライアントのクライアント情報 (クライアントの種類とバージョン番号の両方) およびこのデータベースでキャプチャされた情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="95015-127">Stores the clients (both client type and version number) of each client involved in a call with information captured in this database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95015-128"><a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 の ConferenceUris テーブル</a></span><span class="sxs-lookup"><span data-stu-id="95015-128"><a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95015-129">電話会議関連の通話で使用された ConferenceURI の一覧を格納します。</span><span class="sxs-lookup"><span data-stu-id="95015-129">Stores a list of ConferenceURIs that are used in conference related calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95015-130"><a href="lync-server-2013-contenttypes-table.md">Lync Server 2013 の ContentTypes テーブル</a></span><span class="sxs-lookup"><span data-stu-id="95015-130"><a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95015-131">ピアツーピア通話と電話会議の両方で使用されるセッション開始プロトコル (SIP) のコンテンツの種類の一覧を格納します。</span><span class="sxs-lookup"><span data-stu-id="95015-131">Stores a list of Session Initiation Protocol (SIP) content types that are used in both peer-to-peer calls and conference calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95015-132"><a href="lync-server-2013-devices-table.md">Lync Server 2013 の Devices テーブル</a></span><span class="sxs-lookup"><span data-stu-id="95015-132"><a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95015-133">デバイスの一覧を格納します。製造元、ハードウェアのバージョン、MAC アドレスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="95015-133">Stores a list of devices, including their manufacturer, hardware version, and MAC address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95015-134"><a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a></span><span class="sxs-lookup"><span data-stu-id="95015-134"><a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95015-135">データベースでの各セッションのダイアログ ID に関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="95015-135">Stores information about the Dialog ID for each session in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95015-136"><a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 の EdgeServers テーブル</a></span><span class="sxs-lookup"><span data-stu-id="95015-136"><a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95015-137">外線発信に使用されるエッジ サーバーの一覧を格納します。</span><span class="sxs-lookup"><span data-stu-id="95015-137">Stores a list of Edge Servers that are used for external calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95015-138"><a href="lync-server-2013-gateways-table.md">Lync Server 2013 のゲートウェイテーブル</a></span><span class="sxs-lookup"><span data-stu-id="95015-138"><a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95015-139">ボイス オーバー インターネット プロトコル (VoIP) 通話に使用されるゲートウェイの一覧を格納します。</span><span class="sxs-lookup"><span data-stu-id="95015-139">Stores a list of Gateways that are used for Voice over Internet Protocol (VoIP) calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95015-140"><a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013 の [ハードウェアバージョン表の一覧</a></span><span class="sxs-lookup"><span data-stu-id="95015-140"><a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95015-141">デバイス (電話) のハードウェア バージョンの一覧を格納します。</span><span class="sxs-lookup"><span data-stu-id="95015-141">Stores a list of hardware versions of devices (desk phone).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95015-142"><a href="lync-server-2013-manufacturers-table.md">Lync Server 2013 の [製造元の表」</a></span><span class="sxs-lookup"><span data-stu-id="95015-142"><a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95015-143">デバイス (電話) の製造元の一覧を格納します。</span><span class="sxs-lookup"><span data-stu-id="95015-143">Stores a list of manufacturers of devices (desk phone).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95015-144"><a href="lync-server-2013-mcus-table.md">Lync Server 2013 の mcu テーブル</a></span><span class="sxs-lookup"><span data-stu-id="95015-144"><a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95015-145">さまざまな音声ビデオ会議サーバーとその URI に関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="95015-145">Stores information about the various A/V Conferencing Servers and their URIs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95015-146"><a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 の MediationServers テーブル</a></span><span class="sxs-lookup"><span data-stu-id="95015-146"><a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95015-147">VoIP 通話に使用される仲介サーバーの一覧を格納します。</span><span class="sxs-lookup"><span data-stu-id="95015-147">Stores a list of Mediation Servers that are used for VoIP calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95015-148"><a href="lync-server-2013-phones-table.md">Lync Server 2013 の電話表</a></span><span class="sxs-lookup"><span data-stu-id="95015-148"><a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95015-149">アーカイブされた VoIP 通話または通話の詳細が記録された VoIP 通話において使用されたすべての電話番号を格納します。</span><span class="sxs-lookup"><span data-stu-id="95015-149">Stores all the phone numbers used in VoIP calls that were archived or whose call details were recorded.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95015-150"><a href="lync-server-2013-pools-table.md">Lync Server 2013 のプールテーブル</a></span><span class="sxs-lookup"><span data-stu-id="95015-150"><a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95015-151">IM メッセージがキャプチャされたプールの名前を格納します。</span><span class="sxs-lookup"><span data-stu-id="95015-151">Stores the names of the pool on which IM messages are captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95015-152"><a href="lync-server-2013-servers-table.md">Lync Server 2013 のサーバーテーブル</a></span><span class="sxs-lookup"><span data-stu-id="95015-152"><a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95015-153">通話に関係したサーバーの名前を格納します。</span><span class="sxs-lookup"><span data-stu-id="95015-153">Stores the name of servers involved in calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95015-154"><a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントテーブル</a></span><span class="sxs-lookup"><span data-stu-id="95015-154"><a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95015-155">現在の展開でサポートされるテナントを格納します。</span><span class="sxs-lookup"><span data-stu-id="95015-155">Stores the tenants supported by current deployment.</span></span> <span data-ttu-id="95015-156">エンタープライズ ユーザー用、フェデレーション ユーザー用、パブリック IM 接続ユーザー用、および匿名ユーザー用に、複数の組み込みテナントがあります。</span><span class="sxs-lookup"><span data-stu-id="95015-156">There some build-in tenants for Enterprise user, Federated User, public IM connectivity user, and Anonymous users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95015-157"><a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 の UserAgentDef テーブル</a></span><span class="sxs-lookup"><span data-stu-id="95015-157"><a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95015-158">ユーザー エージェント識別子をエージェントを表す名前にマッピングします。</span><span class="sxs-lookup"><span data-stu-id="95015-158">Maps user agent identifiers to the agent’s descriptive names.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95015-159"><a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザーテーブル</a></span><span class="sxs-lookup"><span data-stu-id="95015-159"><a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95015-160">このデータベースに記録またはアーカイブされたセッションに参加していたユーザーのユーザー URI を格納します。</span><span class="sxs-lookup"><span data-stu-id="95015-160">Stores the user URIs of users who have participated in sessions recorded or archived in this database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95015-161"><a href="lync-server-2013-userstatistics-table.md">Lync Server 2013 の UserStatistics テーブル</a></span><span class="sxs-lookup"><span data-stu-id="95015-161"><a href="lync-server-2013-userstatistics-table.md">UserStatistics table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95015-162">個別のユーザーによるシステムの使用状況に関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="95015-162">Stores information about an individual user’s usage of the system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-specific-to-conference-cdr-records"></a><span data-ttu-id="95015-163">電話会議 CDR レコードに固有のテーブル</span><span class="sxs-lookup"><span data-stu-id="95015-163">Tables Specific to Conference CDR Records</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="95015-164">Table</span><span class="sxs-lookup"><span data-stu-id="95015-164">Table</span></span></th>
<th><span data-ttu-id="95015-165">説明</span><span class="sxs-lookup"><span data-stu-id="95015-165">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="95015-166"><a href="lync-server-2013-conferences-table.md">Lync Server 2013 の会議テーブル</a></span><span class="sxs-lookup"><span data-stu-id="95015-166"><a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95015-167">アーカイブされた、または詳細が記録されたすべての電話会議に関する情報を格納します (ConferenceURI、開始時刻、終了時刻など)。</span><span class="sxs-lookup"><span data-stu-id="95015-167">Stores information about all conferences that were archived or whose details were recorded, including ConferenceURI, and start and end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95015-168"><a href="lync-server-2013-conferencesessiondetails-table.md">Lync Server 2013 の ConferenceSessionDetails テーブル</a></span><span class="sxs-lookup"><span data-stu-id="95015-168"><a href="lync-server-2013-conferencesessiondetails-table.md">ConferenceSessionDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95015-169">すべての SIP ベースの電話会議セッションに関する情報を格納します (各セッションの開始時刻と終了時刻、ユーザー ID、応答コード、診断 ID など)。</span><span class="sxs-lookup"><span data-stu-id="95015-169">Stores information about every SIP-based conference session, including start and end time, user ID, response code, and diagnostic ID for each session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95015-170"><a href="lync-server-2013-focusjoinsandleaves-table.md">Lync Server 2013 の FocusJoinsAndLeaves テーブル</a></span><span class="sxs-lookup"><span data-stu-id="95015-170"><a href="lync-server-2013-focusjoinsandleaves-table.md">FocusJoinsAndLeaves table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95015-171">電話会議の参加および退出に関する情報を格納します (ユーザーの役割、クライアントのバージョンなど)。</span><span class="sxs-lookup"><span data-stu-id="95015-171">Stores information about conference joins and leaves, including users’ role and client version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95015-172"><a href="lync-server-2013-mcujoinsandleaves-table.md">Lync Server 2013 の McuJoinsAndLeaves テーブル</a></span><span class="sxs-lookup"><span data-stu-id="95015-172"><a href="lync-server-2013-mcujoinsandleaves-table.md">McuJoinsAndLeaves table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95015-173">電話会議に関係する音声ビデオ会議サーバーおよびユーザーの参加と退出の時刻に関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="95015-173">Stores information about the A/V Conferencing Servers that are involved in a conference and the user join and leave times.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-messages-in-im-conferences"></a><span data-ttu-id="95015-174">IM 会議でのメッセージ関するテーブル</span><span class="sxs-lookup"><span data-stu-id="95015-174">Tables for Messages in IM Conferences</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="95015-175">Table</span><span class="sxs-lookup"><span data-stu-id="95015-175">Table</span></span></th>
<th><span data-ttu-id="95015-176">説明</span><span class="sxs-lookup"><span data-stu-id="95015-176">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="95015-177"><a href="lync-server-2013-conferencemessagecount-table.md">Lync Server 2013 の ConferenceMessageCount テーブル</a></span><span class="sxs-lookup"><span data-stu-id="95015-177"><a href="lync-server-2013-conferencemessagecount-table.md">ConferenceMessageCount table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95015-178">IM 会議ごとに、各ユーザーが送信したメッセージの数を格納します。</span><span class="sxs-lookup"><span data-stu-id="95015-178">For each IM conference, stores the number of messages that were sent by each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95015-179"><a href="lync-server-2013-imreportsummary-table.md">Lync Server 2013 の IMReportSummary テーブル</a></span><span class="sxs-lookup"><span data-stu-id="95015-179"><a href="lync-server-2013-imreportsummary-table.md">IMReportSummary table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95015-180">組織で行われたインスタント メッセージング セッションに関する概要レポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="95015-180">Provides an overall report on the instant messaging sessions held in an organization.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-peer-to-peer-sessions"></a><span data-ttu-id="95015-181">ピアツーピア セッションに関するテーブル</span><span class="sxs-lookup"><span data-stu-id="95015-181">Tables for Peer-to-Peer Sessions</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="95015-182">Table</span><span class="sxs-lookup"><span data-stu-id="95015-182">Table</span></span></th>
<th><span data-ttu-id="95015-183">説明</span><span class="sxs-lookup"><span data-stu-id="95015-183">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="95015-184"><a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013 の SessionDetails テーブル</a></span><span class="sxs-lookup"><span data-stu-id="95015-184"><a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95015-185">すべてのピアツーピア セッションに関する情報を格納します (各ユーザーの開始時刻と終了時刻、ユーザー ID、応答コード、メッセージ数など)。</span><span class="sxs-lookup"><span data-stu-id="95015-185">Stores information about every peer-to-peer session, including start and end time, user ID, response code, and message count for each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95015-186"><a href="lync-server-2013-filetransfers-table.md">Lync Server 2013 の FileTransfers テーブル</a></span><span class="sxs-lookup"><span data-stu-id="95015-186"><a href="lync-server-2013-filetransfers-table.md">FileTransfers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95015-187">ファイル転送セッションに関する情報を格納します (ファイル名、結果 (許可、禁止、取り消し) など)。</span><span class="sxs-lookup"><span data-stu-id="95015-187">Stores information about file transfer sessions, including file name and result (accepted, rejected, or canceled).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95015-188"><a href="lync-server-2013-media-table.md">Lync Server 2013 のメディアテーブル</a></span><span class="sxs-lookup"><span data-stu-id="95015-188"><a href="lync-server-2013-media-table.md">Media table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95015-189">ピアツーピア セッションに関係するメディアの種類に関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="95015-189">Stores information about the different media types involved in peer-to-peer sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-voip-call-details"></a><span data-ttu-id="95015-190">VoIP 通話の詳細に関するテーブル</span><span class="sxs-lookup"><span data-stu-id="95015-190">Table for VoIP Call Details</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="95015-191">Table</span><span class="sxs-lookup"><span data-stu-id="95015-191">Table</span></span></th>
<th><span data-ttu-id="95015-192">説明</span><span class="sxs-lookup"><span data-stu-id="95015-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="95015-193"><a href="lync-server-2013-voipdetails-table.md">Lync Server 2013 の VoipDetails テーブル</a></span><span class="sxs-lookup"><span data-stu-id="95015-193"><a href="lync-server-2013-voipdetails-table.md">VoipDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95015-194">各 2 パーティ VoIP/PSTN 通話について、通話に関する情報を格納します (VoIP 電話の電話 ID、使用されたゲートウェイ、切断したパーティなど)。</span><span class="sxs-lookup"><span data-stu-id="95015-194">For each two-party VoIP/PSTN call, stores information about the call, such as the phone ID of VoIP phone, gateway used, and which party disconnected.</span></span> <span data-ttu-id="95015-195">通話の開始/終了時刻と応答コードのための <a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013 の Sessiondetails テーブル</a> を参照します。</span><span class="sxs-lookup"><span data-stu-id="95015-195">Refers to the <a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a> for call start/end times and response code.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="95015-196">通話の 1 つのパーティが VoIP ユーザーの場合、または仲介サーバーが通話に関係していた場合、このテーブルにレコードが作成されます。</span><span class="sxs-lookup"><span data-stu-id="95015-196">If one party on a call is a VoIP user or if a Mediation Server was involved in the call, a record will be created in this table.</span></span> <span data-ttu-id="95015-197">公衆交換電話網 (PSTN) 電話を含まない VoIP/VoIP 通話に関する情報は、 <A href="lync-server-2013-sessiondetails-table.md">Lync Server 2013 の Sessiondetails テーブル</A>に記録されます。</span><span class="sxs-lookup"><span data-stu-id="95015-197">Information about VoIP/VoIP calls not involving a public switched telephone network (PSTN) phone is captured in the <A href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</A>.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-e9-1-1-call-auditing"></a><span data-ttu-id="95015-198">E9-1-1 通話監査に関するテーブル</span><span class="sxs-lookup"><span data-stu-id="95015-198">Table for E9-1-1 Call Auditing</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="95015-199">Table</span><span class="sxs-lookup"><span data-stu-id="95015-199">Table</span></span></th>
<th><span data-ttu-id="95015-200">説明</span><span class="sxs-lookup"><span data-stu-id="95015-200">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="95015-201"><a href="lync-server-2013-locations-table.md">Lync Server 2013 の場所テーブル</a></span><span class="sxs-lookup"><span data-stu-id="95015-201"><a href="lync-server-2013-locations-table.md">Locations table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95015-202">Enhanced 9-1-1 (E9-1-1) 呼び出しなどの緊急呼び出しごとに、通話に関する場所情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="95015-202">For each emergency call, such as an Enhanced 9-1-1 (E9-1-1) call, stores location information about the call.</span></span> <span data-ttu-id="95015-203">通話の開始/終了時刻と応答コードのための <a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013 の Sessiondetails テーブル</a> を参照します。</span><span class="sxs-lookup"><span data-stu-id="95015-203">Refers to the <a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a> for call start/end times and response code.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="95015-p105">このテーブルには、E9-1-1 呼び出しの場所の BLOB だけが格納されます。通話に関する他の詳細情報については、SessionDetails テーブルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="95015-p105">This table only contains the location blob for the E9-1-1 call. Refers to the SessionDetails table for other detailed information about the call.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-troubleshooting"></a><span data-ttu-id="95015-206">トラブルシューティングに関するテーブル</span><span class="sxs-lookup"><span data-stu-id="95015-206">Tables for Troubleshooting</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="95015-207">Table</span><span class="sxs-lookup"><span data-stu-id="95015-207">Table</span></span></th>
<th><span data-ttu-id="95015-208">説明</span><span class="sxs-lookup"><span data-stu-id="95015-208">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="95015-209"><a href="lync-server-2013-application-table.md">Lync Server 2013 のアプリケーションテーブル</a></span><span class="sxs-lookup"><span data-stu-id="95015-209"><a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95015-210">ルーティングと接続に関係する Lync Server 2013 内のさまざまなプロセスに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="95015-210">Stores information about various processes within Lync Server 2013 that are involved in routing and connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95015-211"><a href="lync-server-2013-calltype-table.md">Lync Server 2013 の CallType テーブル</a></span><span class="sxs-lookup"><span data-stu-id="95015-211"><a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95015-212">通話の種類に関する情報を格納します ("音声"、"インスタント メッセージング"、Instant Messaging"、"音声とビデオ"、アプリケーション共有" など)。</span><span class="sxs-lookup"><span data-stu-id="95015-212">Stores information about types of the call, such as, “audio”, “Instant Messaging”, “audio and video” and “application sharing”.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95015-213"><a href="lync-server-2013-errorcategory-table.md">Lync Server 2013 の ErrorCategory テーブル</a></span><span class="sxs-lookup"><span data-stu-id="95015-213"><a href="lync-server-2013-errorcategory-table.md">ErrorCategory table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95015-214">各 Microsoft Lync Server 2013 診断分類のフレンドリ名を格納します。</span><span class="sxs-lookup"><span data-stu-id="95015-214">Stores the friendly name for each Microsoft Lync Server 2013 diagnostic classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95015-215"><a href="lync-server-2013-errordef-table.md">Lync Server 2013 の ErrorDef テーブル</a></span><span class="sxs-lookup"><span data-stu-id="95015-215"><a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95015-216">エラーの種類およびその定義に関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="95015-216">Stores information about types of errors and their definitions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95015-217"><a href="lync-server-2013-errorreport-table.md">Lync Server 2013 の ErrorReport テーブル</a></span><span class="sxs-lookup"><span data-stu-id="95015-217"><a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95015-218">発生したエラーに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="95015-218">Stores information about errors that have occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95015-219"><a href="lync-server-2013-progressreport-table.md">Lync Server 2013 の進捗レポートの表</a></span><span class="sxs-lookup"><span data-stu-id="95015-219"><a href="lync-server-2013-progressreport-table.md">ProgressReport table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="95015-220">Lync Server 2013 プロセスに関係するさまざまな手順の進捗レポートに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="95015-220">Stores information about the progress reports of various steps involved in Lync Server 2013 processes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="95015-221">次の表は、Lync Server によって内部的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="95015-221">The tables in the following list are used internally by Lync Server.</span></span> <span data-ttu-id="95015-222">これらのテーブルの詳細については、このドキュメントでは説明しません。</span><span class="sxs-lookup"><span data-stu-id="95015-222">Their details are not described in this document.</span></span>

</div>

<div>

## <a name="tables-for-internal-use-by-lync-server"></a><span data-ttu-id="95015-223">Lync Server の内部用テーブル</span><span class="sxs-lookup"><span data-stu-id="95015-223">Tables for Internal Use by Lync Server</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="95015-224">Table</span><span class="sxs-lookup"><span data-stu-id="95015-224">Table</span></span></th>
<th><span data-ttu-id="95015-225">説明</span><span class="sxs-lookup"><span data-stu-id="95015-225">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="95015-226"><strong>DbConfigDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="95015-226"><strong>DbConfigDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="95015-227">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="95015-227">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95015-228"><strong>DbConfigInt</strong></span><span class="sxs-lookup"><span data-stu-id="95015-228"><strong>DbConfigInt</strong></span></span></p></td>
<td><p><span data-ttu-id="95015-229">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="95015-229">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95015-230"><strong>DbErrorMessage</strong></span><span class="sxs-lookup"><span data-stu-id="95015-230"><strong>DbErrorMessage</strong></span></span></p></td>
<td><p><span data-ttu-id="95015-231">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="95015-231">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95015-232"><strong>FrontEnd テーブル</strong></span><span class="sxs-lookup"><span data-stu-id="95015-232"><strong>FrontEnd Table</strong></span></span></p></td>
<td><p><span data-ttu-id="95015-233">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="95015-233">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95015-234"><strong>MSMQProcessing テーブル</strong></span><span class="sxs-lookup"><span data-stu-id="95015-234"><strong>MSMQProcessing Table</strong></span></span></p></td>
<td><p><span data-ttu-id="95015-235">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="95015-235">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95015-236"><strong>概要 (Tabl)</strong></span><span class="sxs-lookup"><span data-stu-id="95015-236"><strong>SummaryTableConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="95015-237">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="95015-237">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95015-238"><strong>Syndicators テーブル</strong></span><span class="sxs-lookup"><span data-stu-id="95015-238"><strong>Syndicators Table</strong></span></span></p></td>
<td><p><span data-ttu-id="95015-239">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="95015-239">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95015-240"><strong>SyndicatorsTenantMap テーブル</strong></span><span class="sxs-lookup"><span data-stu-id="95015-240"><strong>SyndicatorsTenantMap Table</strong></span></span></p></td>
<td><p><span data-ttu-id="95015-241">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="95015-241">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95015-242"><strong>Task テーブル</strong></span><span class="sxs-lookup"><span data-stu-id="95015-242"><strong>Task Table</strong></span></span></p></td>
<td><p><span data-ttu-id="95015-243">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="95015-243">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95015-244"><strong>UserStatistics</strong></span><span class="sxs-lookup"><span data-stu-id="95015-244"><strong>UserStatistics</strong></span></span></p></td>
<td><p><span data-ttu-id="95015-245">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="95015-245">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95015-246"><strong>UsageSummary_UQ</strong></span><span class="sxs-lookup"><span data-stu-id="95015-246"><strong>UsageSummary_UQ</strong></span></span></p></td>
<td><p><span data-ttu-id="95015-247">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="95015-247">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95015-248"><strong>UsageSummary</strong></span><span class="sxs-lookup"><span data-stu-id="95015-248"><strong>UsageSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="95015-249">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="95015-249">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95015-250"><strong>DaylightSavingYears</strong></span><span class="sxs-lookup"><span data-stu-id="95015-250"><strong>DaylightSavingYears</strong></span></span></p></td>
<td><p><span data-ttu-id="95015-251">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="95015-251">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95015-252"><strong>TimeZoneConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="95015-252"><strong>TimeZoneConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="95015-253">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="95015-253">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95015-254"><strong>TimeZones</strong></span><span class="sxs-lookup"><span data-stu-id="95015-254"><strong>TimeZones</strong></span></span></p></td>
<td><p><span data-ttu-id="95015-255">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="95015-255">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95015-256"><strong>FailureSummary_UQ</strong></span><span class="sxs-lookup"><span data-stu-id="95015-256"><strong>FailureSummary_UQ</strong></span></span></p></td>
<td><p><span data-ttu-id="95015-257">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="95015-257">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95015-258"><strong>FailureSummary</strong></span><span class="sxs-lookup"><span data-stu-id="95015-258"><strong>FailureSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="95015-259">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="95015-259">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95015-260"><strong>ServerSummary</strong></span><span class="sxs-lookup"><span data-stu-id="95015-260"><strong>ServerSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="95015-261">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="95015-261">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95015-262"><strong>MsDiagMetaData</strong></span><span class="sxs-lookup"><span data-stu-id="95015-262"><strong>MsDiagMetaData</strong></span></span></p></td>
<td><p><span data-ttu-id="95015-263">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="95015-263">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

