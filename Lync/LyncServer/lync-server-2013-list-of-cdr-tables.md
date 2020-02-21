---
title: 'Lync Server 2013: CDR テーブルのリスト'
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
ms.openlocfilehash: 8ca9fd0b05eba812730c926685fedb244d60a29e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186630"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="list-of-cdr-tables-in-lync-server-2013"></a><span data-ttu-id="6999b-102">Lync Server 2013 の CDR テーブルの一覧</span><span class="sxs-lookup"><span data-stu-id="6999b-102">List of CDR tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6999b-103">_**トピックの最終更新日:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="6999b-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="6999b-104">通話詳細記録 (CDR) データベース スキーマは、次のテーブルで構成されています。</span><span class="sxs-lookup"><span data-stu-id="6999b-104">The call detail recording (CDR) database schema consists of the following tables.</span></span>

<div>

## <a name="static-tables"></a><span data-ttu-id="6999b-105">静的テーブル</span><span class="sxs-lookup"><span data-stu-id="6999b-105">Static Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6999b-106">Table</span><span class="sxs-lookup"><span data-stu-id="6999b-106">Table</span></span></th>
<th><span data-ttu-id="6999b-107">説明</span><span class="sxs-lookup"><span data-stu-id="6999b-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6999b-108"><a href="lync-server-2013-callpriorities-table.md">Lync Server 2013 の CallPriorities テーブル</a></span><span class="sxs-lookup"><span data-stu-id="6999b-108"><a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6999b-109">可能な通話優先順位の一覧を格納します (緊急、至急、通常、非至急など)。</span><span class="sxs-lookup"><span data-stu-id="6999b-109">Stores the list of possible call priorities, such as emergency, urgent, normal, non-urgent, and more.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6999b-110"><a href="lync-server-2013-conferencejointimethresholds-table.md">Lync Server 2013 の ConferenceJoinTimeThresholds テーブル</a></span><span class="sxs-lookup"><span data-stu-id="6999b-110"><a href="lync-server-2013-conferencejointimethresholds-table.md">ConferenceJoinTimeThresholds table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6999b-111">電話会議参加時間の概要レポートで使用される分類の境界を格納します。</span><span class="sxs-lookup"><span data-stu-id="6999b-111">Stores the classification boundaries used by the Conference Join Time Summary Report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6999b-112"><a href="lync-server-2013-deregistertype-table.md">Lync Server 2013 の DeRegisterType テーブル</a></span><span class="sxs-lookup"><span data-stu-id="6999b-112"><a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6999b-113">ユーザー &quot;が開始した、&quot; &quot;登録期限切れ&quot; &quot;、クライアントクラッシュなど、ユーザーに対して発生する可能性の&quot;ある登録解除の理由の一覧を格納します。</span><span class="sxs-lookup"><span data-stu-id="6999b-113">Stores the list of possible user de-register reasons, such as &quot;client initiated,&quot; &quot;registration expired,&quot; &quot;client crash,&quot; and more.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6999b-114"><a href="lync-server-2013-medialist-table.md">Lync Server 2013 の MediaList テーブル</a></span><span class="sxs-lookup"><span data-stu-id="6999b-114"><a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6999b-115">データベースのエントリを生成できるメディアの種類の一覧を格納します (IM、音声、ビデオ、ファイル送信など)。</span><span class="sxs-lookup"><span data-stu-id="6999b-115">Stores the list of media types that can generate entries in the database (for example, IM, audio, video, and file transfer).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6999b-116"><a href="lync-server-2013-purgesettings-table.md">Lync Server 2013 の PurgeSettings テーブル</a></span><span class="sxs-lookup"><span data-stu-id="6999b-116"><a href="lync-server-2013-purgesettings-table.md">PurgeSettings table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6999b-117">通話詳細記録を CDR データベースから自動的に削除するかどうか (削除する場合はそのタイミング) を指定する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="6999b-117">Stores information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6999b-118"><a href="lync-server-2013-roles-table.md">Lync Server 2013 の Roles テーブル</a></span><span class="sxs-lookup"><span data-stu-id="6999b-118"><a href="lync-server-2013-roles-table.md">Roles table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6999b-119">可能な電話会議の役割の一覧を格納します (参加者、発表者など)。</span><span class="sxs-lookup"><span data-stu-id="6999b-119">Stores the list of possible conference roles (for example, attendee and presenter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6999b-120"><a href="lync-server-2013-sipresponsemetadata-table.md">Lync Server 2013 の SIPResponseMetaData テーブル</a></span><span class="sxs-lookup"><span data-stu-id="6999b-120"><a href="lync-server-2013-sipresponsemetadata-table.md">SIPResponseMetaData table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6999b-121">SIP 応答コードの一覧と、それらの各コードの分類および定義を格納します。</span><span class="sxs-lookup"><span data-stu-id="6999b-121">Stores a list of SIP response codes and the classification and definition of each of those codes.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supporting-tables"></a><span data-ttu-id="6999b-122">サポート テーブル</span><span class="sxs-lookup"><span data-stu-id="6999b-122">Supporting Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6999b-123">Table</span><span class="sxs-lookup"><span data-stu-id="6999b-123">Table</span></span></th>
<th><span data-ttu-id="6999b-124">説明</span><span class="sxs-lookup"><span data-stu-id="6999b-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6999b-125"><a href="lync-server-2013-clientversions-table.md">Lync Server 2013 の ClientVersions テーブル</a></span><span class="sxs-lookup"><span data-stu-id="6999b-125"><a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6999b-126">通話に関わった各クライアントのクライアント情報 (クライアントの種類とバージョン番号の両方) およびこのデータベースでキャプチャされた情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="6999b-126">Stores the clients (both client type and version number) of each client involved in a call with information captured in this database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6999b-127"><a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 の ConferenceUris テーブル</a></span><span class="sxs-lookup"><span data-stu-id="6999b-127"><a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6999b-128">電話会議関連の通話で使用された ConferenceURI の一覧を格納します。</span><span class="sxs-lookup"><span data-stu-id="6999b-128">Stores a list of ConferenceURIs that are used in conference related calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6999b-129"><a href="lync-server-2013-contenttypes-table.md">Lync Server 2013 の ContentTypes テーブル</a></span><span class="sxs-lookup"><span data-stu-id="6999b-129"><a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6999b-130">ピアツーピア通話と電話会議の両方で使用されるセッション開始プロトコル (SIP) のコンテンツの種類の一覧を格納します。</span><span class="sxs-lookup"><span data-stu-id="6999b-130">Stores a list of Session Initiation Protocol (SIP) content types that are used in both peer-to-peer calls and conference calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6999b-131"><a href="lync-server-2013-devices-table.md">Lync Server 2013 の Devices テーブル</a></span><span class="sxs-lookup"><span data-stu-id="6999b-131"><a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6999b-132">デバイスの一覧を格納します。製造元、ハードウェアのバージョン、MAC アドレスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6999b-132">Stores a list of devices, including their manufacturer, hardware version, and MAC address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6999b-133"><a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a></span><span class="sxs-lookup"><span data-stu-id="6999b-133"><a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6999b-134">データベースでの各セッションのダイアログ ID に関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="6999b-134">Stores information about the Dialog ID for each session in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6999b-135"><a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 の EdgeServers テーブル</a></span><span class="sxs-lookup"><span data-stu-id="6999b-135"><a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6999b-136">外線発信に使用されるエッジ サーバーの一覧を格納します。</span><span class="sxs-lookup"><span data-stu-id="6999b-136">Stores a list of Edge Servers that are used for external calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6999b-137"><a href="lync-server-2013-gateways-table.md">Lync Server 2013 のゲートウェイテーブル</a></span><span class="sxs-lookup"><span data-stu-id="6999b-137"><a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6999b-138">ボイス オーバー インターネット プロトコル (VoIP) 通話に使用されるゲートウェイの一覧を格納します。</span><span class="sxs-lookup"><span data-stu-id="6999b-138">Stores a list of Gateways that are used for Voice over Internet Protocol (VoIP) calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6999b-139"><a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013 の [ハードウェアバージョン表の一覧</a></span><span class="sxs-lookup"><span data-stu-id="6999b-139"><a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6999b-140">デバイス (電話) のハードウェア バージョンの一覧を格納します。</span><span class="sxs-lookup"><span data-stu-id="6999b-140">Stores a list of hardware versions of devices (desk phone).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6999b-141"><a href="lync-server-2013-manufacturers-table.md">Lync Server 2013 の [製造元の表」</a></span><span class="sxs-lookup"><span data-stu-id="6999b-141"><a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6999b-142">デバイス (電話) の製造元の一覧を格納します。</span><span class="sxs-lookup"><span data-stu-id="6999b-142">Stores a list of manufacturers of devices (desk phone).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6999b-143"><a href="lync-server-2013-mcus-table.md">Lync Server 2013 の mcu テーブル</a></span><span class="sxs-lookup"><span data-stu-id="6999b-143"><a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6999b-144">さまざまな音声ビデオ会議サーバーとその URI に関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="6999b-144">Stores information about the various A/V Conferencing Servers and their URIs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6999b-145"><a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 の MediationServers テーブル</a></span><span class="sxs-lookup"><span data-stu-id="6999b-145"><a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6999b-146">VoIP 通話に使用される仲介サーバーの一覧を格納します。</span><span class="sxs-lookup"><span data-stu-id="6999b-146">Stores a list of Mediation Servers that are used for VoIP calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6999b-147"><a href="lync-server-2013-phones-table.md">Lync Server 2013 の電話表</a></span><span class="sxs-lookup"><span data-stu-id="6999b-147"><a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6999b-148">アーカイブされた VoIP 通話または通話の詳細が記録された VoIP 通話において使用されたすべての電話番号を格納します。</span><span class="sxs-lookup"><span data-stu-id="6999b-148">Stores all the phone numbers used in VoIP calls that were archived or whose call details were recorded.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6999b-149"><a href="lync-server-2013-pools-table.md">Lync Server 2013 のプールテーブル</a></span><span class="sxs-lookup"><span data-stu-id="6999b-149"><a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6999b-150">IM メッセージがキャプチャされたプールの名前を格納します。</span><span class="sxs-lookup"><span data-stu-id="6999b-150">Stores the names of the pool on which IM messages are captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6999b-151"><a href="lync-server-2013-servers-table.md">Lync Server 2013 のサーバーテーブル</a></span><span class="sxs-lookup"><span data-stu-id="6999b-151"><a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6999b-152">通話に関係したサーバーの名前を格納します。</span><span class="sxs-lookup"><span data-stu-id="6999b-152">Stores the name of servers involved in calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6999b-153"><a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントテーブル</a></span><span class="sxs-lookup"><span data-stu-id="6999b-153"><a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6999b-154">現在の展開でサポートされるテナントを格納します。</span><span class="sxs-lookup"><span data-stu-id="6999b-154">Stores the tenants supported by current deployment.</span></span> <span data-ttu-id="6999b-155">エンタープライズ ユーザー用、フェデレーション ユーザー用、パブリック IM 接続ユーザー用、および匿名ユーザー用に、複数の組み込みテナントがあります。</span><span class="sxs-lookup"><span data-stu-id="6999b-155">There some build-in tenants for Enterprise user, Federated User, public IM connectivity user, and Anonymous users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6999b-156"><a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 の UserAgentDef テーブル</a></span><span class="sxs-lookup"><span data-stu-id="6999b-156"><a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6999b-157">ユーザー エージェント識別子をエージェントを表す名前にマッピングします。</span><span class="sxs-lookup"><span data-stu-id="6999b-157">Maps user agent identifiers to the agent’s descriptive names.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6999b-158"><a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザーテーブル</a></span><span class="sxs-lookup"><span data-stu-id="6999b-158"><a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6999b-159">このデータベースに記録またはアーカイブされたセッションに参加していたユーザーのユーザー URI を格納します。</span><span class="sxs-lookup"><span data-stu-id="6999b-159">Stores the user URIs of users who have participated in sessions recorded or archived in this database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6999b-160"><a href="lync-server-2013-userstatistics-table.md">Lync Server 2013 の UserStatistics テーブル</a></span><span class="sxs-lookup"><span data-stu-id="6999b-160"><a href="lync-server-2013-userstatistics-table.md">UserStatistics table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6999b-161">個別のユーザーによるシステムの使用状況に関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="6999b-161">Stores information about an individual user’s usage of the system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-specific-to-conference-cdr-records"></a><span data-ttu-id="6999b-162">電話会議 CDR レコードに固有のテーブル</span><span class="sxs-lookup"><span data-stu-id="6999b-162">Tables Specific to Conference CDR Records</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6999b-163">Table</span><span class="sxs-lookup"><span data-stu-id="6999b-163">Table</span></span></th>
<th><span data-ttu-id="6999b-164">説明</span><span class="sxs-lookup"><span data-stu-id="6999b-164">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6999b-165"><a href="lync-server-2013-conferences-table.md">Lync Server 2013 の会議テーブル</a></span><span class="sxs-lookup"><span data-stu-id="6999b-165"><a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6999b-166">アーカイブされた、または詳細が記録されたすべての電話会議に関する情報を格納します (ConferenceURI、開始時刻、終了時刻など)。</span><span class="sxs-lookup"><span data-stu-id="6999b-166">Stores information about all conferences that were archived or whose details were recorded, including ConferenceURI, and start and end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6999b-167"><a href="lync-server-2013-conferencesessiondetails-table.md">Lync Server 2013 の ConferenceSessionDetails テーブル</a></span><span class="sxs-lookup"><span data-stu-id="6999b-167"><a href="lync-server-2013-conferencesessiondetails-table.md">ConferenceSessionDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6999b-168">すべての SIP ベースの電話会議セッションに関する情報を格納します (各セッションの開始時刻と終了時刻、ユーザー ID、応答コード、診断 ID など)。</span><span class="sxs-lookup"><span data-stu-id="6999b-168">Stores information about every SIP-based conference session, including start and end time, user ID, response code, and diagnostic ID for each session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6999b-169"><a href="lync-server-2013-focusjoinsandleaves-table.md">Lync Server 2013 の FocusJoinsAndLeaves テーブル</a></span><span class="sxs-lookup"><span data-stu-id="6999b-169"><a href="lync-server-2013-focusjoinsandleaves-table.md">FocusJoinsAndLeaves table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6999b-170">電話会議の参加および退出に関する情報を格納します (ユーザーの役割、クライアントのバージョンなど)。</span><span class="sxs-lookup"><span data-stu-id="6999b-170">Stores information about conference joins and leaves, including users’ role and client version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6999b-171"><a href="lync-server-2013-mcujoinsandleaves-table.md">Lync Server 2013 の McuJoinsAndLeaves テーブル</a></span><span class="sxs-lookup"><span data-stu-id="6999b-171"><a href="lync-server-2013-mcujoinsandleaves-table.md">McuJoinsAndLeaves table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6999b-172">電話会議に関係する音声ビデオ会議サーバーおよびユーザーの参加と退出の時刻に関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="6999b-172">Stores information about the A/V Conferencing Servers that are involved in a conference and the user join and leave times.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-messages-in-im-conferences"></a><span data-ttu-id="6999b-173">IM 会議でのメッセージ関するテーブル</span><span class="sxs-lookup"><span data-stu-id="6999b-173">Tables for Messages in IM Conferences</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6999b-174">Table</span><span class="sxs-lookup"><span data-stu-id="6999b-174">Table</span></span></th>
<th><span data-ttu-id="6999b-175">説明</span><span class="sxs-lookup"><span data-stu-id="6999b-175">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6999b-176"><a href="lync-server-2013-conferencemessagecount-table.md">Lync Server 2013 の ConferenceMessageCount テーブル</a></span><span class="sxs-lookup"><span data-stu-id="6999b-176"><a href="lync-server-2013-conferencemessagecount-table.md">ConferenceMessageCount table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6999b-177">IM 会議ごとに、各ユーザーが送信したメッセージの数を格納します。</span><span class="sxs-lookup"><span data-stu-id="6999b-177">For each IM conference, stores the number of messages that were sent by each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6999b-178"><a href="lync-server-2013-imreportsummary-table.md">Lync Server 2013 の IMReportSummary テーブル</a></span><span class="sxs-lookup"><span data-stu-id="6999b-178"><a href="lync-server-2013-imreportsummary-table.md">IMReportSummary table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6999b-179">組織で行われたインスタント メッセージング セッションに関する概要レポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="6999b-179">Provides an overall report on the instant messaging sessions held in an organization.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-peer-to-peer-sessions"></a><span data-ttu-id="6999b-180">ピアツーピア セッションに関するテーブル</span><span class="sxs-lookup"><span data-stu-id="6999b-180">Tables for Peer-to-Peer Sessions</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6999b-181">Table</span><span class="sxs-lookup"><span data-stu-id="6999b-181">Table</span></span></th>
<th><span data-ttu-id="6999b-182">説明</span><span class="sxs-lookup"><span data-stu-id="6999b-182">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6999b-183"><a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013 の SessionDetails テーブル</a></span><span class="sxs-lookup"><span data-stu-id="6999b-183"><a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6999b-184">すべてのピアツーピア セッションに関する情報を格納します (各ユーザーの開始時刻と終了時刻、ユーザー ID、応答コード、メッセージ数など)。</span><span class="sxs-lookup"><span data-stu-id="6999b-184">Stores information about every peer-to-peer session, including start and end time, user ID, response code, and message count for each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6999b-185"><a href="lync-server-2013-filetransfers-table.md">Lync Server 2013 の FileTransfers テーブル</a></span><span class="sxs-lookup"><span data-stu-id="6999b-185"><a href="lync-server-2013-filetransfers-table.md">FileTransfers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6999b-186">ファイル転送セッションに関する情報を格納します (ファイル名、結果 (許可、禁止、取り消し) など)。</span><span class="sxs-lookup"><span data-stu-id="6999b-186">Stores information about file transfer sessions, including file name and result (accepted, rejected, or canceled).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6999b-187"><a href="lync-server-2013-media-table.md">Lync Server 2013 のメディアテーブル</a></span><span class="sxs-lookup"><span data-stu-id="6999b-187"><a href="lync-server-2013-media-table.md">Media table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6999b-188">ピアツーピア セッションに関係するメディアの種類に関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="6999b-188">Stores information about the different media types involved in peer-to-peer sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-voip-call-details"></a><span data-ttu-id="6999b-189">VoIP 通話の詳細に関するテーブル</span><span class="sxs-lookup"><span data-stu-id="6999b-189">Table for VoIP Call Details</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6999b-190">Table</span><span class="sxs-lookup"><span data-stu-id="6999b-190">Table</span></span></th>
<th><span data-ttu-id="6999b-191">説明</span><span class="sxs-lookup"><span data-stu-id="6999b-191">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6999b-192"><a href="lync-server-2013-voipdetails-table.md">Lync Server 2013 の VoipDetails テーブル</a></span><span class="sxs-lookup"><span data-stu-id="6999b-192"><a href="lync-server-2013-voipdetails-table.md">VoipDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6999b-193">各 2 パーティ VoIP/PSTN 通話について、通話に関する情報を格納します (VoIP 電話の電話 ID、使用されたゲートウェイ、切断したパーティなど)。</span><span class="sxs-lookup"><span data-stu-id="6999b-193">For each two-party VoIP/PSTN call, stores information about the call, such as the phone ID of VoIP phone, gateway used, and which party disconnected.</span></span> <span data-ttu-id="6999b-194">通話の開始/終了時刻と応答コードのための<a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013 の Sessiondetails テーブル</a>を参照します。</span><span class="sxs-lookup"><span data-stu-id="6999b-194">Refers to the <a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a> for call start/end times and response code.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="6999b-195">通話の 1 つのパーティが VoIP ユーザーの場合、または仲介サーバーが通話に関係していた場合、このテーブルにレコードが作成されます。</span><span class="sxs-lookup"><span data-stu-id="6999b-195">If one party on a call is a VoIP user or if a Mediation Server was involved in the call, a record will be created in this table.</span></span> <span data-ttu-id="6999b-196">公衆交換電話網 (PSTN) 電話を含まない VoIP/VoIP 通話に関する情報は、 <A href="lync-server-2013-sessiondetails-table.md">Lync Server 2013 の Sessiondetails テーブル</A>に記録されます。</span><span class="sxs-lookup"><span data-stu-id="6999b-196">Information about VoIP/VoIP calls not involving a public switched telephone network (PSTN) phone is captured in the <A href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</A>.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-e9-1-1-call-auditing"></a><span data-ttu-id="6999b-197">E9-1-1 通話監査に関するテーブル</span><span class="sxs-lookup"><span data-stu-id="6999b-197">Table for E9-1-1 Call Auditing</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6999b-198">Table</span><span class="sxs-lookup"><span data-stu-id="6999b-198">Table</span></span></th>
<th><span data-ttu-id="6999b-199">説明</span><span class="sxs-lookup"><span data-stu-id="6999b-199">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6999b-200"><a href="lync-server-2013-locations-table.md">Lync Server 2013 の場所テーブル</a></span><span class="sxs-lookup"><span data-stu-id="6999b-200"><a href="lync-server-2013-locations-table.md">Locations table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6999b-201">Enhanced 9-1-1 (E9-1-1) 呼び出しなどの緊急呼び出しごとに、通話に関する場所情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="6999b-201">For each emergency call, such as an Enhanced 9-1-1 (E9-1-1) call, stores location information about the call.</span></span> <span data-ttu-id="6999b-202">通話の開始/終了時刻と応答コードのための<a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013 の Sessiondetails テーブル</a>を参照します。</span><span class="sxs-lookup"><span data-stu-id="6999b-202">Refers to the <a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a> for call start/end times and response code.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="6999b-p105">このテーブルには、E9-1-1 呼び出しの場所の BLOB だけが格納されます。通話に関する他の詳細情報については、SessionDetails テーブルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6999b-p105">This table only contains the location blob for the E9-1-1 call. Refers to the SessionDetails table for other detailed information about the call.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-troubleshooting"></a><span data-ttu-id="6999b-205">トラブルシューティングに関するテーブル</span><span class="sxs-lookup"><span data-stu-id="6999b-205">Tables for Troubleshooting</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6999b-206">Table</span><span class="sxs-lookup"><span data-stu-id="6999b-206">Table</span></span></th>
<th><span data-ttu-id="6999b-207">説明</span><span class="sxs-lookup"><span data-stu-id="6999b-207">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6999b-208"><a href="lync-server-2013-application-table.md">Lync Server 2013 のアプリケーションテーブル</a></span><span class="sxs-lookup"><span data-stu-id="6999b-208"><a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6999b-209">ルーティングと接続に関係する Lync Server 2013 内のさまざまなプロセスに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="6999b-209">Stores information about various processes within Lync Server 2013 that are involved in routing and connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6999b-210"><a href="lync-server-2013-calltype-table.md">Lync Server 2013 の CallType テーブル</a></span><span class="sxs-lookup"><span data-stu-id="6999b-210"><a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6999b-211">通話の種類に関する情報を格納します ("音声"、"インスタント メッセージング"、Instant Messaging"、"音声とビデオ"、アプリケーション共有" など)。</span><span class="sxs-lookup"><span data-stu-id="6999b-211">Stores information about types of the call, such as, “audio”, “Instant Messaging”, “audio and video” and “application sharing”.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6999b-212"><a href="lync-server-2013-errorcategory-table.md">Lync Server 2013 の ErrorCategory テーブル</a></span><span class="sxs-lookup"><span data-stu-id="6999b-212"><a href="lync-server-2013-errorcategory-table.md">ErrorCategory table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6999b-213">各 Microsoft Lync Server 2013 診断分類のフレンドリ名を格納します。</span><span class="sxs-lookup"><span data-stu-id="6999b-213">Stores the friendly name for each Microsoft Lync Server 2013 diagnostic classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6999b-214"><a href="lync-server-2013-errordef-table.md">Lync Server 2013 の ErrorDef テーブル</a></span><span class="sxs-lookup"><span data-stu-id="6999b-214"><a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6999b-215">エラーの種類およびその定義に関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="6999b-215">Stores information about types of errors and their definitions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6999b-216"><a href="lync-server-2013-errorreport-table.md">Lync Server 2013 の ErrorReport テーブル</a></span><span class="sxs-lookup"><span data-stu-id="6999b-216"><a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6999b-217">発生したエラーに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="6999b-217">Stores information about errors that have occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6999b-218"><a href="lync-server-2013-progressreport-table.md">Lync Server 2013 の進捗レポートの表</a></span><span class="sxs-lookup"><span data-stu-id="6999b-218"><a href="lync-server-2013-progressreport-table.md">ProgressReport table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6999b-219">Lync Server 2013 プロセスに関係するさまざまな手順の進捗レポートに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="6999b-219">Stores information about the progress reports of various steps involved in Lync Server 2013 processes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6999b-220">次の表は、Lync Server によって内部的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="6999b-220">The tables in the following list are used internally by Lync Server.</span></span> <span data-ttu-id="6999b-221">これらのテーブルの詳細については、このドキュメントでは説明しません。</span><span class="sxs-lookup"><span data-stu-id="6999b-221">Their details are not described in this document.</span></span>

</div>

<div>

## <a name="tables-for-internal-use-by-lync-server"></a><span data-ttu-id="6999b-222">Lync Server の内部用テーブル</span><span class="sxs-lookup"><span data-stu-id="6999b-222">Tables for Internal Use by Lync Server</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6999b-223">Table</span><span class="sxs-lookup"><span data-stu-id="6999b-223">Table</span></span></th>
<th><span data-ttu-id="6999b-224">説明</span><span class="sxs-lookup"><span data-stu-id="6999b-224">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6999b-225"><strong>DbConfigDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="6999b-225"><strong>DbConfigDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6999b-226">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="6999b-226">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6999b-227"><strong>DbConfigInt</strong></span><span class="sxs-lookup"><span data-stu-id="6999b-227"><strong>DbConfigInt</strong></span></span></p></td>
<td><p><span data-ttu-id="6999b-228">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="6999b-228">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6999b-229"><strong>DbErrorMessage</strong></span><span class="sxs-lookup"><span data-stu-id="6999b-229"><strong>DbErrorMessage</strong></span></span></p></td>
<td><p><span data-ttu-id="6999b-230">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="6999b-230">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6999b-231"><strong>FrontEnd テーブル</strong></span><span class="sxs-lookup"><span data-stu-id="6999b-231"><strong>FrontEnd Table</strong></span></span></p></td>
<td><p><span data-ttu-id="6999b-232">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="6999b-232">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6999b-233"><strong>MSMQProcessing テーブル</strong></span><span class="sxs-lookup"><span data-stu-id="6999b-233"><strong>MSMQProcessing Table</strong></span></span></p></td>
<td><p><span data-ttu-id="6999b-234">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="6999b-234">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6999b-235"><strong>概要 (Tabl)</strong></span><span class="sxs-lookup"><span data-stu-id="6999b-235"><strong>SummaryTableConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="6999b-236">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="6999b-236">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6999b-237"><strong>Syndicators テーブル</strong></span><span class="sxs-lookup"><span data-stu-id="6999b-237"><strong>Syndicators Table</strong></span></span></p></td>
<td><p><span data-ttu-id="6999b-238">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="6999b-238">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6999b-239"><strong>SyndicatorsTenantMap テーブル</strong></span><span class="sxs-lookup"><span data-stu-id="6999b-239"><strong>SyndicatorsTenantMap Table</strong></span></span></p></td>
<td><p><span data-ttu-id="6999b-240">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="6999b-240">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6999b-241"><strong>Task テーブル</strong></span><span class="sxs-lookup"><span data-stu-id="6999b-241"><strong>Task Table</strong></span></span></p></td>
<td><p><span data-ttu-id="6999b-242">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="6999b-242">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6999b-243"><strong>UserStatistics</strong></span><span class="sxs-lookup"><span data-stu-id="6999b-243"><strong>UserStatistics</strong></span></span></p></td>
<td><p><span data-ttu-id="6999b-244">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="6999b-244">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6999b-245"><strong>UsageSummary_UQ</strong></span><span class="sxs-lookup"><span data-stu-id="6999b-245"><strong>UsageSummary_UQ</strong></span></span></p></td>
<td><p><span data-ttu-id="6999b-246">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="6999b-246">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6999b-247"><strong>UsageSummary</strong></span><span class="sxs-lookup"><span data-stu-id="6999b-247"><strong>UsageSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="6999b-248">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="6999b-248">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6999b-249"><strong>DaylightSavingYears</strong></span><span class="sxs-lookup"><span data-stu-id="6999b-249"><strong>DaylightSavingYears</strong></span></span></p></td>
<td><p><span data-ttu-id="6999b-250">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="6999b-250">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6999b-251"><strong>TimeZoneConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="6999b-251"><strong>TimeZoneConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="6999b-252">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="6999b-252">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6999b-253"><strong>TimeZones</strong></span><span class="sxs-lookup"><span data-stu-id="6999b-253"><strong>TimeZones</strong></span></span></p></td>
<td><p><span data-ttu-id="6999b-254">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="6999b-254">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6999b-255"><strong>FailureSummary_UQ</strong></span><span class="sxs-lookup"><span data-stu-id="6999b-255"><strong>FailureSummary_UQ</strong></span></span></p></td>
<td><p><span data-ttu-id="6999b-256">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="6999b-256">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6999b-257"><strong>FailureSummary</strong></span><span class="sxs-lookup"><span data-stu-id="6999b-257"><strong>FailureSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="6999b-258">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="6999b-258">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6999b-259"><strong>ServerSummary</strong></span><span class="sxs-lookup"><span data-stu-id="6999b-259"><strong>ServerSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="6999b-260">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="6999b-260">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6999b-261"><strong>MsDiagMetaData</strong></span><span class="sxs-lookup"><span data-stu-id="6999b-261"><strong>MsDiagMetaData</strong></span></span></p></td>
<td><p><span data-ttu-id="6999b-262">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="6999b-262">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

