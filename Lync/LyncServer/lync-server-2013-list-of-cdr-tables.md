---
title: 'Lync Server 2013: CDR テーブルの一覧'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: List of CDR tables
ms:assetid: 031843fd-c7ff-4534-9b02-8847aad70807
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398084(v=OCS.15)
ms:contentKeyID: 48183254
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1ac043d144e73d8e1b40ca717e278619e053fdc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832949"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-cdr-tables-in-lync-server-2013"></a><span data-ttu-id="fb4d1-102">Lync Server 2013 の CDR テーブルの一覧</span><span class="sxs-lookup"><span data-stu-id="fb4d1-102">List of CDR tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb4d1-103">_**最終更新日:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="fb4d1-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="fb4d1-104">通話の詳細記録 (CDR) データベーススキーマは、次の表で構成されています。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-104">The call detail recording (CDR) database schema consists of the following tables.</span></span>

<div>

## <a name="static-tables"></a><span data-ttu-id="fb4d1-105">静的なテーブル</span><span class="sxs-lookup"><span data-stu-id="fb4d1-105">Static Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fb4d1-106">テーブル</span><span class="sxs-lookup"><span data-stu-id="fb4d1-106">Table</span></span></th>
<th><span data-ttu-id="fb4d1-107">説明</span><span class="sxs-lookup"><span data-stu-id="fb4d1-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fb4d1-108"><a href="lync-server-2013-callpriorities-table.md">Lync Server 2013 の CallPriorities テーブル</a></span><span class="sxs-lookup"><span data-stu-id="fb4d1-108"><a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-109">緊急、緊急、標準、不急など、可能な通話の優先順位のリストを保存します。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-109">Stores the list of possible call priorities, such as emergency, urgent, normal, non-urgent, and more.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb4d1-110"><a href="lync-server-2013-conferencejointimethresholds-table.md">Lync Server 2013 の ConferenceJoinTimeThresholds テーブル</a></span><span class="sxs-lookup"><span data-stu-id="fb4d1-110"><a href="lync-server-2013-conferencejointimethresholds-table.md">ConferenceJoinTimeThresholds table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-111">会議参加時間のサマリーレポートで使用される分類境界を格納します。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-111">Stores the classification boundaries used by the Conference Join Time Summary Report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb4d1-112"><a href="lync-server-2013-deregistertype-table.md">Lync Server 2013 の DeRegisterType テーブル</a></span><span class="sxs-lookup"><span data-stu-id="fb4d1-112"><a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-113">&quot;クライアントによって開始された、&quot; &quot;登録の期限切れ&quot; &quot;、クライアントのクラッシュ&quot;など、可能なユーザー登録解除の理由のリストを保存します。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-113">Stores the list of possible user de-register reasons, such as &quot;client initiated,&quot; &quot;registration expired,&quot; &quot;client crash,&quot; and more.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb4d1-114"><a href="lync-server-2013-medialist-table.md">Lync Server 2013 の MediaList テーブル</a></span><span class="sxs-lookup"><span data-stu-id="fb4d1-114"><a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-115">データベースにエントリを生成できるメディアの種類の一覧を保存します (たとえば、IM、音声、ビデオ、ファイル転送など)。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-115">Stores the list of media types that can generate entries in the database (for example, IM, audio, video, and file transfer).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb4d1-116"><a href="lync-server-2013-purgesettings-table.md">Lync Server 2013 の PurgeSettings テーブル</a></span><span class="sxs-lookup"><span data-stu-id="fb4d1-116"><a href="lync-server-2013-purgesettings-table.md">PurgeSettings table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-117">古い通話の詳細レコードが CDR データベースから自動的に削除されるかどうかを指定する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-117">Stores information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb4d1-118"><a href="lync-server-2013-roles-table.md">Lync Server 2013 の Roles テーブル</a></span><span class="sxs-lookup"><span data-stu-id="fb4d1-118"><a href="lync-server-2013-roles-table.md">Roles table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-119">可能な電話会議の役割のリスト ([出席者] と [発表者] など) を保存します。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-119">Stores the list of possible conference roles (for example, attendee and presenter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb4d1-120"><a href="lync-server-2013-sipresponsemetadata-table.md">Lync Server 2013 の SIPResponseMetaData テーブル</a></span><span class="sxs-lookup"><span data-stu-id="fb4d1-120"><a href="lync-server-2013-sipresponsemetadata-table.md">SIPResponseMetaData table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-121">SIP 応答コードの一覧と、各コードの分類と定義を保存します。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-121">Stores a list of SIP response codes and the classification and definition of each of those codes.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supporting-tables"></a><span data-ttu-id="fb4d1-122">サポートテーブル</span><span class="sxs-lookup"><span data-stu-id="fb4d1-122">Supporting Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fb4d1-123">テーブル</span><span class="sxs-lookup"><span data-stu-id="fb4d1-123">Table</span></span></th>
<th><span data-ttu-id="fb4d1-124">説明</span><span class="sxs-lookup"><span data-stu-id="fb4d1-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fb4d1-125"><a href="lync-server-2013-clientversions-table.md">Lync Server 2013 の ClientVersions テーブル</a></span><span class="sxs-lookup"><span data-stu-id="fb4d1-125"><a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-126">このデータベースにキャプチャされた情報を使って、通話に関係する各クライアントのクライアント (クライアントの種類とバージョン番号の両方) を保存します。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-126">Stores the clients (both client type and version number) of each client involved in a call with information captured in this database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb4d1-127"><a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 の ConferenceUris テーブル</a></span><span class="sxs-lookup"><span data-stu-id="fb4d1-127"><a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-128">会議関連の通話で使用される ConferenceURIs のリストを保存します。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-128">Stores a list of ConferenceURIs that are used in conference related calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb4d1-129"><a href="lync-server-2013-contenttypes-table.md">Lync Server 2013 の ContentTypes テーブル</a></span><span class="sxs-lookup"><span data-stu-id="fb4d1-129"><a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-130">ピアツーピア通話と電話会議の両方で使用されるセッション開始プロトコル (SIP) コンテンツタイプのリストを保存します。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-130">Stores a list of Session Initiation Protocol (SIP) content types that are used in both peer-to-peer calls and conference calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb4d1-131"><a href="lync-server-2013-devices-table.md">Lync Server 2013 の Devices テーブル</a></span><span class="sxs-lookup"><span data-stu-id="fb4d1-131"><a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-132">製造元、ハードウェアのバージョン、MAC アドレスなど、デバイスの一覧を保存します。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-132">Stores a list of devices, including their manufacturer, hardware version, and MAC address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb4d1-133"><a href="lync-server-2013-dialogs-table.md">Lync Server 2013 の Dialogs テーブル</a></span><span class="sxs-lookup"><span data-stu-id="fb4d1-133"><a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-134">データベース内の各セッションのダイアログ ID に関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-134">Stores information about the Dialog ID for each session in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb4d1-135"><a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 の EdgeServers テーブル</a></span><span class="sxs-lookup"><span data-stu-id="fb4d1-135"><a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-136">外部通話に使用されるエッジサーバーの一覧を保存します。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-136">Stores a list of Edge Servers that are used for external calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb4d1-137"><a href="lync-server-2013-gateways-table.md">Lync Server 2013 のゲートウェイ テーブル</a></span><span class="sxs-lookup"><span data-stu-id="fb4d1-137"><a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-138">VoIP (Voice over Internet Protocol) 通話に使用されるゲートウェイの一覧を保存します。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-138">Stores a list of Gateways that are used for Voice over Internet Protocol (VoIP) calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb4d1-139"><a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013 の HardwareVersions テーブル</a></span><span class="sxs-lookup"><span data-stu-id="fb4d1-139"><a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-140">ハードウェアバージョンのデバイス (卓上電話) の一覧を保存します。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-140">Stores a list of hardware versions of devices (desk phone).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb4d1-141"><a href="lync-server-2013-manufacturers-table.md">Lync Server 2013 の Manufacturers テーブル</a></span><span class="sxs-lookup"><span data-stu-id="fb4d1-141"><a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-142">デバイスの製造元の一覧を保存します (卓上電話)。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-142">Stores a list of manufacturers of devices (desk phone).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb4d1-143"><a href="lync-server-2013-mcus-table.md">Lync Server 2013 の Mcus テーブル</a></span><span class="sxs-lookup"><span data-stu-id="fb4d1-143"><a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-144">さまざまな A/V 会議サーバーとその Uri に関する情報を保存します。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-144">Stores information about the various A/V Conferencing Servers and their URIs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb4d1-145"><a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 の MediationServers テーブル</a></span><span class="sxs-lookup"><span data-stu-id="fb4d1-145"><a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-146">VoIP 通話に使用される仲介サーバーのリストを保存します。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-146">Stores a list of Mediation Servers that are used for VoIP calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb4d1-147"><a href="lync-server-2013-phones-table.md">Lync Server 2013 の Phones テーブル</a></span><span class="sxs-lookup"><span data-stu-id="fb4d1-147"><a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-148">アーカイブされた、または通話の詳細が記録された VoIP 通話で使用されたすべての電話番号が格納されます。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-148">Stores all the phone numbers used in VoIP calls that were archived or whose call details were recorded.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb4d1-149"><a href="lync-server-2013-pools-table.md">Lync Server 2013 の Pools テーブル</a></span><span class="sxs-lookup"><span data-stu-id="fb4d1-149"><a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-150">IM メッセージがキャプチャされるプールの名前を格納します。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-150">Stores the names of the pool on which IM messages are captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb4d1-151"><a href="lync-server-2013-servers-table.md">Lync Server 2013 の Servers テーブル</a></span><span class="sxs-lookup"><span data-stu-id="fb4d1-151"><a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-152">通話に関連するサーバーの名前が格納されます。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-152">Stores the name of servers involved in calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb4d1-153"><a href="lync-server-2013-tenants-table.md">Lync Server 2013 の Tenants テーブル</a></span><span class="sxs-lookup"><span data-stu-id="fb4d1-153"><a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-154">現在の展開でサポートされているテナントを格納します。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-154">Stores the tenants supported by current deployment.</span></span> <span data-ttu-id="fb4d1-155">エンタープライズユーザー、フェデレーションユーザー、パブリック IM 接続ユーザー、匿名ユーザー向けの一部のビルドのテナントがあります。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-155">There some build-in tenants for Enterprise user, Federated User, public IM connectivity user, and Anonymous users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb4d1-156"><a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 の UserAgentDef テーブル</a></span><span class="sxs-lookup"><span data-stu-id="fb4d1-156"><a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-157">ユーザーエージェント識別子をエージェントのわかりやすい名前にマップします。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-157">Maps user agent identifiers to the agent’s descriptive names.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb4d1-158"><a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー テーブル</a></span><span class="sxs-lookup"><span data-stu-id="fb4d1-158"><a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-159">このデータベースに記録またはアーカイブされたセッションに参加しているユーザーの Uri を格納します。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-159">Stores the user URIs of users who have participated in sessions recorded or archived in this database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb4d1-160"><a href="lync-server-2013-userstatistics-table.md">Lync Server 2013 の UserStatistics テーブル</a></span><span class="sxs-lookup"><span data-stu-id="fb4d1-160"><a href="lync-server-2013-userstatistics-table.md">UserStatistics table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-161">個々のユーザーによるシステムの使用状況に関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-161">Stores information about an individual user’s usage of the system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-specific-to-conference-cdr-records"></a><span data-ttu-id="fb4d1-162">会議 CDR レコードに固有のテーブル</span><span class="sxs-lookup"><span data-stu-id="fb4d1-162">Tables Specific to Conference CDR Records</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fb4d1-163">テーブル</span><span class="sxs-lookup"><span data-stu-id="fb4d1-163">Table</span></span></th>
<th><span data-ttu-id="fb4d1-164">説明</span><span class="sxs-lookup"><span data-stu-id="fb4d1-164">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fb4d1-165"><a href="lync-server-2013-conferences-table.md">Lync Server 2013 の Conferences テーブル</a></span><span class="sxs-lookup"><span data-stu-id="fb4d1-165"><a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-166">ConferenceURI、開始時刻、終了時刻など、アーカイブされた、または情報が記録されたすべての会議に関する情報を保存します。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-166">Stores information about all conferences that were archived or whose details were recorded, including ConferenceURI, and start and end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb4d1-167"><a href="lync-server-2013-conferencesessiondetails-table.md">Lync Server 2013 の ConferenceSessionDetails テーブル</a></span><span class="sxs-lookup"><span data-stu-id="fb4d1-167"><a href="lync-server-2013-conferencesessiondetails-table.md">ConferenceSessionDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-168">各セッションの開始時刻、終了時刻、ユーザー ID、応答コード、診断 ID など、SIP ベースのすべての会議セッションに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-168">Stores information about every SIP-based conference session, including start and end time, user ID, response code, and diagnostic ID for each session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb4d1-169"><a href="lync-server-2013-focusjoinsandleaves-table.md">Lync Server 2013 の FocusJoinsAndLeaves テーブル</a></span><span class="sxs-lookup"><span data-stu-id="fb4d1-169"><a href="lync-server-2013-focusjoinsandleaves-table.md">FocusJoinsAndLeaves table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-170">ユーザーの役割やクライアントのバージョンなど、会議の参加と退席に関する情報を保存します。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-170">Stores information about conference joins and leaves, including users’ role and client version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb4d1-171"><a href="lync-server-2013-mcujoinsandleaves-table.md">Lync Server 2013 の McuJoinsAndLeaves テーブル</a></span><span class="sxs-lookup"><span data-stu-id="fb4d1-171"><a href="lync-server-2013-mcujoinsandleaves-table.md">McuJoinsAndLeaves table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-172">会議に参加している、またはユーザーが参加して休暇している A/V 会議サーバーに関する情報を保存します。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-172">Stores information about the A/V Conferencing Servers that are involved in a conference and the user join and leave times.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-messages-in-im-conferences"></a><span data-ttu-id="fb4d1-173">IM 会議のメッセージのテーブル</span><span class="sxs-lookup"><span data-stu-id="fb4d1-173">Tables for Messages in IM Conferences</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fb4d1-174">テーブル</span><span class="sxs-lookup"><span data-stu-id="fb4d1-174">Table</span></span></th>
<th><span data-ttu-id="fb4d1-175">説明</span><span class="sxs-lookup"><span data-stu-id="fb4d1-175">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fb4d1-176"><a href="lync-server-2013-conferencemessagecount-table.md">Lync Server 2013 の ConferenceMessageCount テーブル</a></span><span class="sxs-lookup"><span data-stu-id="fb4d1-176"><a href="lync-server-2013-conferencemessagecount-table.md">ConferenceMessageCount table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-177">IM 会議ごとに、各ユーザーが送信したメッセージの数が保存されます。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-177">For each IM conference, stores the number of messages that were sent by each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb4d1-178"><a href="lync-server-2013-imreportsummary-table.md">Lync Server 2013 の IMReportSummary テーブル</a></span><span class="sxs-lookup"><span data-stu-id="fb4d1-178"><a href="lync-server-2013-imreportsummary-table.md">IMReportSummary table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-179">組織内で開催されたインスタントメッセージセッションに関する全体的なレポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-179">Provides an overall report on the instant messaging sessions held in an organization.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-peer-to-peer-sessions"></a><span data-ttu-id="fb4d1-180">ピアツーピアセッションのテーブル</span><span class="sxs-lookup"><span data-stu-id="fb4d1-180">Tables for Peer-to-Peer Sessions</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fb4d1-181">テーブル</span><span class="sxs-lookup"><span data-stu-id="fb4d1-181">Table</span></span></th>
<th><span data-ttu-id="fb4d1-182">説明</span><span class="sxs-lookup"><span data-stu-id="fb4d1-182">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fb4d1-183"><a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013 の SessionDetails テーブル</a></span><span class="sxs-lookup"><span data-stu-id="fb4d1-183"><a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-184">各ユーザーの開始時刻、終了時刻、ユーザー ID、応答コード、メッセージ数など、すべてのピアツーピアセッションに関する情報を保存します。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-184">Stores information about every peer-to-peer session, including start and end time, user ID, response code, and message count for each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb4d1-185"><a href="lync-server-2013-filetransfers-table.md">Lync Server 2013 の FileTransfers テーブル</a></span><span class="sxs-lookup"><span data-stu-id="fb4d1-185"><a href="lync-server-2013-filetransfers-table.md">FileTransfers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-186">ファイル名や結果 (承諾、拒否、またはキャンセル) などのファイル転送セッションに関する情報を保存します。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-186">Stores information about file transfer sessions, including file name and result (accepted, rejected, or canceled).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb4d1-187"><a href="lync-server-2013-media-table.md">Lync Server 2013 の Media テーブル</a></span><span class="sxs-lookup"><span data-stu-id="fb4d1-187"><a href="lync-server-2013-media-table.md">Media table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-188">ピアツーピアセッションに関連するさまざまなメディアの種類に関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-188">Stores information about the different media types involved in peer-to-peer sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-voip-call-details"></a><span data-ttu-id="fb4d1-189">VoIP 通話の詳細の表</span><span class="sxs-lookup"><span data-stu-id="fb4d1-189">Table for VoIP Call Details</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fb4d1-190">テーブル</span><span class="sxs-lookup"><span data-stu-id="fb4d1-190">Table</span></span></th>
<th><span data-ttu-id="fb4d1-191">説明</span><span class="sxs-lookup"><span data-stu-id="fb4d1-191">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fb4d1-192"><a href="lync-server-2013-voipdetails-table.md">Lync Server 2013 の VoipDetails テーブル</a></span><span class="sxs-lookup"><span data-stu-id="fb4d1-192"><a href="lync-server-2013-voipdetails-table.md">VoipDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-193">各 [voip/PSTN 通話] には、VoIP 電話の電話 ID、使用されているゲートウェイ、切断されているパーティなど、通話に関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-193">For each two-party VoIP/PSTN call, stores information about the call, such as the phone ID of VoIP phone, gateway used, and which party disconnected.</span></span> <span data-ttu-id="fb4d1-194">電話の開始/終了時刻と応答コードのための<a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013 の Sessiondetails テーブル</a>を指します。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-194">Refers to the <a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a> for call start/end times and response code.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="fb4d1-195">通話中に1人の当事者が VoIP ユーザーの場合、または仲介サーバーが通話に参加していた場合は、次の表でレコードが作成されます。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-195">If one party on a call is a VoIP user or if a Mediation Server was involved in the call, a record will be created in this table.</span></span> <span data-ttu-id="fb4d1-196">公衆交換電話網 (PSTN) 電話を含まない VoIP/VoIP 通話に関する情報は、 <A href="lync-server-2013-sessiondetails-table.md">Lync Server 2013 の Sessiondetails の表</A>に記載されています。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-196">Information about VoIP/VoIP calls not involving a public switched telephone network (PSTN) phone is captured in the <A href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</A>.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-e9-1-1-call-auditing"></a><span data-ttu-id="fb4d1-197">E9 の表 (1 ~ 1 の通話監査)</span><span class="sxs-lookup"><span data-stu-id="fb4d1-197">Table for E9-1-1 Call Auditing</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fb4d1-198">テーブル</span><span class="sxs-lookup"><span data-stu-id="fb4d1-198">Table</span></span></th>
<th><span data-ttu-id="fb4d1-199">説明</span><span class="sxs-lookup"><span data-stu-id="fb4d1-199">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fb4d1-200"><a href="lync-server-2013-locations-table.md">Lync Server 2013 の Locations テーブル</a></span><span class="sxs-lookup"><span data-stu-id="fb4d1-200"><a href="lync-server-2013-locations-table.md">Locations table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-201">拡張 9-1-1 (E9) 通話などの各緊急通話では、通話に関する位置情報が保存されます。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-201">For each emergency call, such as an Enhanced 9-1-1 (E9-1-1) call, stores location information about the call.</span></span> <span data-ttu-id="fb4d1-202">電話の開始/終了時刻と応答コードのための<a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013 の Sessiondetails テーブル</a>を指します。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-202">Refers to the <a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a> for call start/end times and response code.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="fb4d1-203">このテーブルには、E9 通話の位置 blob のみが含まれています。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-203">This table only contains the location blob for the E9-1-1 call.</span></span> <span data-ttu-id="fb4d1-204">通話に関するその他の詳細情報については、SessionDetails テーブルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-204">Refers to the SessionDetails table for other detailed information about the call.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-troubleshooting"></a><span data-ttu-id="fb4d1-205">トラブルシューティングのための表</span><span class="sxs-lookup"><span data-stu-id="fb4d1-205">Tables for Troubleshooting</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fb4d1-206">テーブル</span><span class="sxs-lookup"><span data-stu-id="fb4d1-206">Table</span></span></th>
<th><span data-ttu-id="fb4d1-207">説明</span><span class="sxs-lookup"><span data-stu-id="fb4d1-207">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fb4d1-208"><a href="lync-server-2013-application-table.md">Lync Server 2013 の Application テーブル</a></span><span class="sxs-lookup"><span data-stu-id="fb4d1-208"><a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-209">ルーティングと接続に関連する、Lync Server 2013 内のさまざまなプロセスに関する情報を保存します。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-209">Stores information about various processes within Lync Server 2013 that are involved in routing and connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb4d1-210"><a href="lync-server-2013-calltype-table.md">Lync Server 2013 の CallType テーブル</a></span><span class="sxs-lookup"><span data-stu-id="fb4d1-210"><a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-211">[オーディオ]、[インスタントメッセージング]、[音声とビデオ]、[アプリケーションの共有] など、通話の種類に関する情報を保存します。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-211">Stores information about types of the call, such as, “audio”, “Instant Messaging”, “audio and video” and “application sharing”.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb4d1-212"><a href="lync-server-2013-errorcategory-table.md">Lync Server 2013 の ErrorCategory テーブル</a></span><span class="sxs-lookup"><span data-stu-id="fb4d1-212"><a href="lync-server-2013-errorcategory-table.md">ErrorCategory table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-213">各 Microsoft Lync Server 2013 診断分類のフレンドリ名を格納します。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-213">Stores the friendly name for each Microsoft Lync Server 2013 diagnostic classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb4d1-214"><a href="lync-server-2013-errordef-table.md">Lync Server 2013 ErrorDef テーブル</a></span><span class="sxs-lookup"><span data-stu-id="fb4d1-214"><a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-215">エラーの種類とその定義に関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-215">Stores information about types of errors and their definitions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb4d1-216"><a href="lync-server-2013-errorreport-table.md">Lync Server 2013 の ErrorReport テーブル</a></span><span class="sxs-lookup"><span data-stu-id="fb4d1-216"><a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-217">発生したエラーに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-217">Stores information about errors that have occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb4d1-218"><a href="lync-server-2013-progressreport-table.md">Lync Server 2013 の ProgressReport テーブル</a></span><span class="sxs-lookup"><span data-stu-id="fb4d1-218"><a href="lync-server-2013-progressreport-table.md">ProgressReport table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-219">Lync Server 2013 プロセスに関連するさまざまな手順の進捗レポートに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-219">Stores information about the progress reports of various steps involved in Lync Server 2013 processes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fb4d1-220">次の一覧の表は、Lync Server によって内部的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-220">The tables in the following list are used internally by Lync Server.</span></span> <span data-ttu-id="fb4d1-221">このドキュメントには、詳細が記載されていません。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-221">Their details are not described in this document.</span></span>

</div>

<div>

## <a name="tables-for-internal-use-by-lync-server"></a><span data-ttu-id="fb4d1-222">Lync Server で内部的に使用するテーブル</span><span class="sxs-lookup"><span data-stu-id="fb4d1-222">Tables for Internal Use by Lync Server</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fb4d1-223">テーブル</span><span class="sxs-lookup"><span data-stu-id="fb4d1-223">Table</span></span></th>
<th><span data-ttu-id="fb4d1-224">説明</span><span class="sxs-lookup"><span data-stu-id="fb4d1-224">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fb4d1-225"><strong>DbConfigDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="fb4d1-225"><strong>DbConfigDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-226">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-226">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb4d1-227"><strong>DbConfigInt</strong></span><span class="sxs-lookup"><span data-stu-id="fb4d1-227"><strong>DbConfigInt</strong></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-228">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-228">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb4d1-229"><strong>DbErrorMessage</strong></span><span class="sxs-lookup"><span data-stu-id="fb4d1-229"><strong>DbErrorMessage</strong></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-230">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-230">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb4d1-231"><strong>フロントエンドテーブル</strong></span><span class="sxs-lookup"><span data-stu-id="fb4d1-231"><strong>FrontEnd Table</strong></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-232">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-232">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb4d1-233"><strong>MSMQProcessing テーブル</strong></span><span class="sxs-lookup"><span data-stu-id="fb4d1-233"><strong>MSMQProcessing Table</strong></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-234">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-234">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb4d1-235"><strong>概要 tabltabl</strong></span><span class="sxs-lookup"><span data-stu-id="fb4d1-235"><strong>SummaryTableConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-236">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-236">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb4d1-237"><strong>Syndicators テーブル</strong></span><span class="sxs-lookup"><span data-stu-id="fb4d1-237"><strong>Syndicators Table</strong></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-238">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-238">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb4d1-239"><strong>SyndicatorsTenantMap テーブル</strong></span><span class="sxs-lookup"><span data-stu-id="fb4d1-239"><strong>SyndicatorsTenantMap Table</strong></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-240">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-240">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb4d1-241"><strong>タスクテーブル</strong></span><span class="sxs-lookup"><span data-stu-id="fb4d1-241"><strong>Task Table</strong></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-242">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-242">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb4d1-243"><strong>UserStatistics</strong></span><span class="sxs-lookup"><span data-stu-id="fb4d1-243"><strong>UserStatistics</strong></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-244">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-244">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb4d1-245"><strong>UsageSummary_UQ</strong></span><span class="sxs-lookup"><span data-stu-id="fb4d1-245"><strong>UsageSummary_UQ</strong></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-246">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-246">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb4d1-247"><strong>UsageSummary</strong></span><span class="sxs-lookup"><span data-stu-id="fb4d1-247"><strong>UsageSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-248">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-248">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb4d1-249"><strong>DaylightSavingYears</strong></span><span class="sxs-lookup"><span data-stu-id="fb4d1-249"><strong>DaylightSavingYears</strong></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-250">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-250">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb4d1-251"><strong>TimeZoneConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="fb4d1-251"><strong>TimeZoneConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-252">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-252">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb4d1-253"><strong>タイム</strong></span><span class="sxs-lookup"><span data-stu-id="fb4d1-253"><strong>TimeZones</strong></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-254">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-254">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb4d1-255"><strong>FailureSummary_UQ</strong></span><span class="sxs-lookup"><span data-stu-id="fb4d1-255"><strong>FailureSummary_UQ</strong></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-256">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-256">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb4d1-257"><strong>FailureSummary 概要</strong></span><span class="sxs-lookup"><span data-stu-id="fb4d1-257"><strong>FailureSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-258">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-258">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb4d1-259"><strong>ServerSummary</strong></span><span class="sxs-lookup"><span data-stu-id="fb4d1-259"><strong>ServerSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-260">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-260">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb4d1-261"><strong>MsDiagMetaData</strong></span><span class="sxs-lookup"><span data-stu-id="fb4d1-261"><strong>MsDiagMetaData</strong></span></span></p></td>
<td><p><span data-ttu-id="fb4d1-262">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="fb4d1-262">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

