---
title: 'Lync Server 2013: QoE テーブルの一覧'
description: 'Lync Server 2013: QoE テーブルのリスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of QoE tables
ms:assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398236(v=OCS.15)
ms:contentKeyID: 48183512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 871babf246f616d306a03f84f9134605dd595999
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550043"
---
# <a name="list-of-qoe-tables-in-lync-server-2013"></a><span data-ttu-id="ab96d-103">Lync Server 2013 の QoE テーブルの一覧</span><span class="sxs-lookup"><span data-stu-id="ab96d-103">List of QoE tables in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab96d-104">_**トピックの最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="ab96d-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="ab96d-105">データベース スキーマは、次のテーブルで構成されます。</span><span class="sxs-lookup"><span data-stu-id="ab96d-105">The database schema consists of the following tables.</span></span>

<span data-ttu-id="ab96d-106">**サポート テーブル**</span><span class="sxs-lookup"><span data-stu-id="ab96d-106">**Supporting Tables**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ab96d-107"><strong>Table</strong></span><span class="sxs-lookup"><span data-stu-id="ab96d-107"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="ab96d-108"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="ab96d-108"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ab96d-109"><a href="lync-server-2013-appsharingmetricsthreshold-table.md">Lync Server 2013 の AppSharingMetricsThreshold テーブル</a></span><span class="sxs-lookup"><span data-stu-id="ab96d-109"><a href="lync-server-2013-appsharingmetricsthreshold-table.md">AppSharingMetricsThreshold table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ab96d-110">アプリケーション共有で使用される QoE 指標の最適値および許容値を格納します。</span><span class="sxs-lookup"><span data-stu-id="ab96d-110">Stores optimal and acceptable values for the Quality of Experience metrics used with application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab96d-111"><a href="lync-server-2013-codecdescription-table.md">Lync Server 2013 の CodecDescription テーブル</a></span><span class="sxs-lookup"><span data-stu-id="ab96d-111"><a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ab96d-112">一意のコーデック識別子を対応するコーデックにマッピングします。</span><span class="sxs-lookup"><span data-stu-id="ab96d-112">Maps unique codec identifiers to their corresponding codec.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab96d-113"><a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a></span><span class="sxs-lookup"><span data-stu-id="ab96d-113"><a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ab96d-114">IP アドレスを、QoE データベース内の他の場所で使用される一意の IP アドレス識別子にマッピングします。</span><span class="sxs-lookup"><span data-stu-id="ab96d-114">Maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab96d-115"><a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 の NetworkConnectionDetail テーブル</a></span><span class="sxs-lookup"><span data-stu-id="ab96d-115"><a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ab96d-116">ネットワーク接続の種類を、QoE データベース内の他の場所で使用されるネットワーク接続識別子にマッピングします。</span><span class="sxs-lookup"><span data-stu-id="ab96d-116">Maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab96d-117"><a href="lync-server-2013-purgesettings-table-qoe.md">Lync Server 2013 の PurgeSettings テーブル (QoE)</a></span><span class="sxs-lookup"><span data-stu-id="ab96d-117"><a href="lync-server-2013-purgesettings-table-qoe.md">PurgeSettings table (QoE) in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ab96d-118">古くなった QoE レコードが QoE データベースから自動的に削除されるかどうか (およびそのタイミング) を指定する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="ab96d-118">Stores information that specifies if (and when) outdated Quality of Experience records will automatically be deleted from the QoE database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab96d-119"><a href="lync-server-2013-traceroute-table.md">Lync Server 2013 の TraceRoute テーブル</a></span><span class="sxs-lookup"><span data-stu-id="ab96d-119"><a href="lync-server-2013-traceroute-table.md">TraceRoute table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ab96d-120">通話のルーティング情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="ab96d-120">Stores routing information for calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab96d-121"><a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 の UserAgentDef テーブル (QoE)</a></span><span class="sxs-lookup"><span data-stu-id="ab96d-121"><a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ab96d-122">ユーザー エージェント識別子をエージェントを表す名前にマッピングします。</span><span class="sxs-lookup"><span data-stu-id="ab96d-122">Maps user agent identifiers to the agent’s descriptive names.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab96d-123"><a href="lync-server-2013-videometricsthreshold-table.md">Lync Server 2013 の VideoMetricsThreshold テーブル</a></span><span class="sxs-lookup"><span data-stu-id="ab96d-123"><a href="lync-server-2013-videometricsthreshold-table.md">VideoMetricsThreshold table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ab96d-124">ビデオ通話で使用される QoE 指標の最適値および許容値を格納します。</span><span class="sxs-lookup"><span data-stu-id="ab96d-124">Stores optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab96d-125"><a href="lync-server-2013-useragent-table.md">Lync Server 2013 の UserAgent テーブル</a></span><span class="sxs-lookup"><span data-stu-id="ab96d-125"><a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ab96d-126">音声およびビデオ セッションで使用されるセッション開始プロトコル (SIP) ユーザー エージェント (UA) 文字列および UA の種類を格納します。</span><span class="sxs-lookup"><span data-stu-id="ab96d-126">Stores Session Initiation Protocol (SIP) User Agent (UA) strings and UA types used in audio and video sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab96d-127"><a href="lync-server-2013-user-table.md">Lync Server 2013 のユーザーテーブル</a></span><span class="sxs-lookup"><span data-stu-id="ab96d-127"><a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ab96d-128">音声およびビデオ セッションで使用されるユーザー、会議、電話の URI を格納します。</span><span class="sxs-lookup"><span data-stu-id="ab96d-128">Stores user, conference, and phone URIs used in audio and video sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab96d-129"><a href="lync-server-2013-endpoint-table.md">Lync Server 2013 のエンドポイントテーブル</a></span><span class="sxs-lookup"><span data-stu-id="ab96d-129"><a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ab96d-130">音声およびビデオ セッションに参加しているエンドポイントの FQDN コンピューター名を格納します。</span><span class="sxs-lookup"><span data-stu-id="ab96d-130">Stores FQDN computer names of endpoints participating in audio and video sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab96d-131"><a href="lync-server-2013-pool-table.md">Lync Server 2013 のプールテーブル</a></span><span class="sxs-lookup"><span data-stu-id="ab96d-131"><a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ab96d-132">指標データが属するプールの名前を格納します。</span><span class="sxs-lookup"><span data-stu-id="ab96d-132">Stores the names of pools to which metrics data belongs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab96d-133"><a href="lync-server-2013-device-table.md">Lync Server 2013 のデバイステーブル</a></span><span class="sxs-lookup"><span data-stu-id="ab96d-133"><a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ab96d-134">音声ビデオ通話で使用されるキャプチャ デバイスおよびレンダー デバイスを格納します。</span><span class="sxs-lookup"><span data-stu-id="ab96d-134">Stores capture devices and render devices which are used in an audio/video calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab96d-135"><a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 の DeviceDriver テーブル</a></span><span class="sxs-lookup"><span data-stu-id="ab96d-135"><a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ab96d-136">音声ビデオ通話で使用されるキャプチャ デバイスおよびレンダー デバイスのドライバーを格納します。</span><span class="sxs-lookup"><span data-stu-id="ab96d-136">Stores driver for the capture device and the render device which are used in audio/video calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab96d-137"><a href="lync-server-2013-conference-table.md">Lync Server 2013 の会議テーブル</a></span><span class="sxs-lookup"><span data-stu-id="ab96d-137"><a href="lync-server-2013-conference-table.md">Conference table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ab96d-138">会議シナリオの会議 URI または他のシナリオの DialogID を格納します。</span><span class="sxs-lookup"><span data-stu-id="ab96d-138">Stores Conference URIs for conference scenarios or DialogID for other scenarios.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab96d-139"><a href="lync-server-2013-sessioncorrelation-table.md">Lync Server 2013 の SessionCorrelation テーブル</a></span><span class="sxs-lookup"><span data-stu-id="ab96d-139"><a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ab96d-140">PSTN 通話の CorrelationID を格納します。</span><span class="sxs-lookup"><span data-stu-id="ab96d-140">Stores CorrelationID for PSTN calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab96d-141"><a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 の PayloadDescription テーブル</a></span><span class="sxs-lookup"><span data-stu-id="ab96d-141"><a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ab96d-142">音声ビデオ通話で使用されるコーデックを格納します。</span><span class="sxs-lookup"><span data-stu-id="ab96d-142">Stores the Codec used in audio/video calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab96d-143"><a href="lync-server-2013-appliedbandwidthsource-table.md">Lync Server 2013 の AppliedBandwidthSource テーブル</a></span><span class="sxs-lookup"><span data-stu-id="ab96d-143"><a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ab96d-144">音声ビデオ通話で使用される帯域幅ソースを格納します。</span><span class="sxs-lookup"><span data-stu-id="ab96d-144">Stores the bandwidth source used in audio/video calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab96d-145"><a href="lync-server-2013-macaddress-table.md">Lync Server 2013 の MacAddress テーブル</a></span><span class="sxs-lookup"><span data-stu-id="ab96d-145"><a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ab96d-146">音声およびビデオ セッションに参加しているエンドポイントの MAC アドレスを格納します。</span><span class="sxs-lookup"><span data-stu-id="ab96d-146">Stores the MAC address of the endpoints participating in audio and video sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab96d-147"><a href="lync-server-2013-dialog-table.md">Lync Server 2013 のダイアログテーブル</a></span><span class="sxs-lookup"><span data-stu-id="ab96d-147"><a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ab96d-148">音声およびビデオ セッションのダイアログ ID を格納します。</span><span class="sxs-lookup"><span data-stu-id="ab96d-148">Stores the Dialog ID of audio and video sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab96d-149"><a href="lync-server-2013-region-table.md">Lync Server 2013 の Region テーブル</a></span><span class="sxs-lookup"><span data-stu-id="ab96d-149"><a href="lync-server-2013-region-table.md">Region table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ab96d-150">NCS 設定で定義されているネットワーク地域を格納します。</span><span class="sxs-lookup"><span data-stu-id="ab96d-150">Stores the network region defined in NCS setting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab96d-151"><a href="lync-server-2013-usersite-table.md">Lync Server 2013 の UserSite テーブル</a></span><span class="sxs-lookup"><span data-stu-id="ab96d-151"><a href="lync-server-2013-usersite-table.md">UserSite table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ab96d-152">NCS 設定で定義されているネットワーク サイトを格納します。</span><span class="sxs-lookup"><span data-stu-id="ab96d-152">Stores the network site defined in NCS setting.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab96d-153"><a href="lync-server-2013-subnet-table.md">Lync Server 2013 のサブネットテーブル</a></span><span class="sxs-lookup"><span data-stu-id="ab96d-153"><a href="lync-server-2013-subnet-table.md">Subnet table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ab96d-154">NCS 設定で定義されているサブネットを格納します。</span><span class="sxs-lookup"><span data-stu-id="ab96d-154">Stores the subnet defined in NCS setting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab96d-155"><a href="lync-server-2013-monitoredregionlink-table.md">Lync Server 2013 の MonitoredRegionLink テーブル</a></span><span class="sxs-lookup"><span data-stu-id="ab96d-155"><a href="lync-server-2013-monitoredregionlink-table.md">MonitoredRegionLink table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ab96d-156">NCS 設定で定義されている地域リンクを格納します。</span><span class="sxs-lookup"><span data-stu-id="ab96d-156">Stores the region link defined in NCS setting.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab96d-157"><a href="monitoredusersitelink-table.md">MonitoredUserSiteLink リンクテーブル</a></span><span class="sxs-lookup"><span data-stu-id="ab96d-157"><a href="monitoredusersitelink-table.md">MonitoredUserSiteLink table</a></span></span></p></td>
<td><p><span data-ttu-id="ab96d-158">NCS 設定で定義されているネットワーク サイト リンクを格納します。</span><span class="sxs-lookup"><span data-stu-id="ab96d-158">Stores the network site links defined in NCS setting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab96d-159"><a href="lync-server-2013-endpointsubnet-table.md">Lync Server 2013 の EndpointSubnet テーブル</a></span><span class="sxs-lookup"><span data-stu-id="ab96d-159"><a href="lync-server-2013-endpointsubnet-table.md">EndpointSubnet table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ab96d-160">音声およびビデオ セッションに参加しているエンドポイントのサブネットを格納します。</span><span class="sxs-lookup"><span data-stu-id="ab96d-160">Stores the subnet of the endpoint participating in an audio and video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab96d-161"><a href="lync-server-2013-server-table.md">Lync Server 2013 のサーバーテーブル</a></span><span class="sxs-lookup"><span data-stu-id="ab96d-161"><a href="lync-server-2013-server-table.md">Server table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ab96d-162">メディアが通過するサーバーの FQDN または IP アドレスを格納します。</span><span class="sxs-lookup"><span data-stu-id="ab96d-162">Stores the FQDN or IP address of the server the media goes through.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ab96d-163">**指標データ用テーブル**</span><span class="sxs-lookup"><span data-stu-id="ab96d-163">**Tables for metrics data**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ab96d-164"><strong>Table</strong></span><span class="sxs-lookup"><span data-stu-id="ab96d-164"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="ab96d-165"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="ab96d-165"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ab96d-166"><a href="lync-server-2013-appsharingstream-table.md">Lync Server 2013 の AppSharingStream テーブル</a></span><span class="sxs-lookup"><span data-stu-id="ab96d-166"><a href="lync-server-2013-appsharingstream-table.md">AppSharingStream table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ab96d-p101">アプリケーション共有で使用されるネットワーク ストリームの QoE 指標を格納します。</span><span class="sxs-lookup"><span data-stu-id="ab96d-p101">Stores Quality of Experience metrics for the network streams used for application sharing. Quality of Experience metrics for the network streams used for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab96d-169"><a href="lync-server-2013-session-table.md">Lync Server 2013 の Session テーブル</a></span><span class="sxs-lookup"><span data-stu-id="ab96d-169"><a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ab96d-170">音声セッションまたは音声ビデオ セッションに関する全体的な情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="ab96d-170">Stores overall information about an audio or audio/video session.</span></span> <span data-ttu-id="ab96d-171">セッションとは、2 つのエンドポイント間の音声またはビデオでの SIP ダイアログと定義されます。</span><span class="sxs-lookup"><span data-stu-id="ab96d-171">A session is defined as an audio or video SIP dialog between two endpoints.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab96d-172"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a></span><span class="sxs-lookup"><span data-stu-id="ab96d-172"><a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ab96d-p103">セッションでの各メディア ラインについての情報を格納します。メディア ラインとは、1 つ以上の音声およびビデオ ストリームのコレクションです。通常、1 つのメディア ラインには音声またはビデオの 2 つのストリームが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ab96d-p103">Stores information about each media line in a session. A media line is a collection of one or more audio and video streams. Typically, a single media line will have two streams, either audio or video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab96d-176"><a href="lync-server-2013-audiostream-table.md">Lync Server 2013 の AudioStream テーブル</a></span><span class="sxs-lookup"><span data-stu-id="ab96d-176"><a href="lync-server-2013-audiostream-table.md">AudioStream table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ab96d-177">メディア ラインに含まれる各音声ストリームの音声メディア品質指標を格納します。</span><span class="sxs-lookup"><span data-stu-id="ab96d-177">Stores audio media quality metrics for each audio stream in the media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab96d-178"><a href="lync-server-2013-audiosignal-table.md">Lync Server 2013 の AudioSignal テーブル</a></span><span class="sxs-lookup"><span data-stu-id="ab96d-178"><a href="lync-server-2013-audiosignal-table.md">AudioSignal table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ab96d-179">メディア ラインの音声メディア品質指標を格納します。</span><span class="sxs-lookup"><span data-stu-id="ab96d-179">Stores audio media quality metrics in the media line.</span></span> <span data-ttu-id="ab96d-180">これには、アコーステック エコー キャンセレーション (AEC) 指標および自動ゲイン制御 (AGC) 指標が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ab96d-180">This includes acoustic echo cancellation (AEC) and automatic gain control (AGC) metrics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab96d-181"><a href="lync-server-2013-videostream-table.md">Lync Server 2013 の VideoStream テーブル</a></span><span class="sxs-lookup"><span data-stu-id="ab96d-181"><a href="lync-server-2013-videostream-table.md">VideoStream table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ab96d-182">メディア ラインに含まれる各音声ストリームのビデオ メディア品質指標を格納します。</span><span class="sxs-lookup"><span data-stu-id="ab96d-182">Stores video media quality metrics for each audio stream in the media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab96d-183"><a href="lync-server-2013-audioclientevent-table.md">Lync Server 2013 の AudioClientEvent テーブル</a></span><span class="sxs-lookup"><span data-stu-id="ab96d-183"><a href="lync-server-2013-audioclientevent-table.md">AudioClientEvent table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ab96d-184">クライアント イベントから収集された音声メディア品質指標を格納します。</span><span class="sxs-lookup"><span data-stu-id="ab96d-184">Stores audio media quality metrics collected from the client event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab96d-185"><a href="lync-server-2013-videoclientevent-table.md">Lync Server 2013 の VideoClientEvent テーブル</a></span><span class="sxs-lookup"><span data-stu-id="ab96d-185"><a href="lync-server-2013-videoclientevent-table.md">VideoClientEvent table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ab96d-186">クライアント イベントから収集されたビデオ メディア品質指標を格納します。</span><span class="sxs-lookup"><span data-stu-id="ab96d-186">Stores video media quality metrics collected from the client event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab96d-187"><strong>DiagnosticData テーブル</strong></span><span class="sxs-lookup"><span data-stu-id="ab96d-187"><strong>DiagnosticData Table</strong></span></span></p></td>
<td><p><span data-ttu-id="ab96d-188">内部使用専用の診断データを格納します。</span><span class="sxs-lookup"><span data-stu-id="ab96d-188">Stores diagnostic data which is for internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ab96d-189">**概要データ用テーブル**</span><span class="sxs-lookup"><span data-stu-id="ab96d-189">**Tables for summary data**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ab96d-190"><strong>Table</strong></span><span class="sxs-lookup"><span data-stu-id="ab96d-190"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="ab96d-191"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="ab96d-191"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ab96d-192"><strong>ServerSummary テーブル</strong></span><span class="sxs-lookup"><span data-stu-id="ab96d-192"><strong>ServerSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="ab96d-193">サーバーの概要データを格納します。このデータは、QoE (Quality of Experience) レポートのみに使用されます。</span><span class="sxs-lookup"><span data-stu-id="ab96d-193">Stores summary data for the servers, these data is used for Quality of Experience (QoE) reporting only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab96d-194"><strong>UserSummary テーブル</strong></span><span class="sxs-lookup"><span data-stu-id="ab96d-194"><strong>UserSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="ab96d-195">ユーザーの概要データを格納します。このデータは、QoE レポートのみに使用されます。</span><span class="sxs-lookup"><span data-stu-id="ab96d-195">Stores summary data for users, these data is used for QoE reporting only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab96d-196"><strong>CallTypeSummary テーブル</strong></span><span class="sxs-lookup"><span data-stu-id="ab96d-196"><strong>CallTypeSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="ab96d-197">通話種類の概要データを格納します。このデータは、QoE レポートのみに使用されます。</span><span class="sxs-lookup"><span data-stu-id="ab96d-197">Store summary data for call types, these data is used for QoE reporting only.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ab96d-198">**監視サーバーの内部用テーブル**</span><span class="sxs-lookup"><span data-stu-id="ab96d-198">**Tables for Internal Use by Monitoring Server**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ab96d-199"><strong>Table</strong></span><span class="sxs-lookup"><span data-stu-id="ab96d-199"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="ab96d-200"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="ab96d-200"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ab96d-201"><strong>DbConfigDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="ab96d-201"><strong>DbConfigDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ab96d-202">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="ab96d-202">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab96d-203"><strong>DbConfigInt</strong></span><span class="sxs-lookup"><span data-stu-id="ab96d-203"><strong>DbConfigInt</strong></span></span></p></td>
<td><p><span data-ttu-id="ab96d-204">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="ab96d-204">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab96d-205"><strong>FrontEnd テーブル</strong></span><span class="sxs-lookup"><span data-stu-id="ab96d-205"><strong>FrontEnd Table</strong></span></span></p></td>
<td><p><span data-ttu-id="ab96d-206">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="ab96d-206">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab96d-207"><strong>Task テーブル</strong></span><span class="sxs-lookup"><span data-stu-id="ab96d-207"><strong>Task Table</strong></span></span></p></td>
<td><p><span data-ttu-id="ab96d-208">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="ab96d-208">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab96d-209"><strong>概要 (Tabl)</strong></span><span class="sxs-lookup"><span data-stu-id="ab96d-209"><strong>SummaryTableConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="ab96d-210">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="ab96d-210">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab96d-211"><strong>DbErrorMessage</strong></span><span class="sxs-lookup"><span data-stu-id="ab96d-211"><strong>DbErrorMessage</strong></span></span></p></td>
<td><p><span data-ttu-id="ab96d-212">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="ab96d-212">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab96d-213"><strong>MetricsThreshold</strong></span><span class="sxs-lookup"><span data-stu-id="ab96d-213"><strong>MetricsThreshold</strong></span></span></p></td>
<td><p><span data-ttu-id="ab96d-214">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="ab96d-214">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab96d-215"><strong>DaylightSavingYears</strong></span><span class="sxs-lookup"><span data-stu-id="ab96d-215"><strong>DaylightSavingYears</strong></span></span></p></td>
<td><p><span data-ttu-id="ab96d-216">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="ab96d-216">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab96d-217"><strong>TimeZoneConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="ab96d-217"><strong>TimeZoneConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="ab96d-218">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="ab96d-218">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab96d-219"><strong>TimeZones</strong></span><span class="sxs-lookup"><span data-stu-id="ab96d-219"><strong>TimeZones</strong></span></span></p></td>
<td><p><span data-ttu-id="ab96d-220">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="ab96d-220">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab96d-221"><strong>CallSummary テーブル</strong></span><span class="sxs-lookup"><span data-stu-id="ab96d-221"><strong>CallSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="ab96d-222">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="ab96d-222">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab96d-223"><strong>DeviceCallSumary テーブル</strong></span><span class="sxs-lookup"><span data-stu-id="ab96d-223"><strong>DeviceCallSumary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="ab96d-224">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="ab96d-224">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab96d-225"><strong>Tenant テーブル</strong></span><span class="sxs-lookup"><span data-stu-id="ab96d-225"><strong>Tenant Table</strong></span></span></p></td>
<td><p><span data-ttu-id="ab96d-226">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="ab96d-226">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab96d-227"><strong>VideoCallSummaryTable</strong></span><span class="sxs-lookup"><span data-stu-id="ab96d-227"><strong>VideoCallSummaryTable</strong></span></span></p></td>
<td><p><span data-ttu-id="ab96d-228">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="ab96d-228">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab96d-229"><strong>Ascall概要テーブル</strong></span><span class="sxs-lookup"><span data-stu-id="ab96d-229"><strong>ASCallSummaryTable</strong></span></span></p></td>
<td><p><span data-ttu-id="ab96d-230">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="ab96d-230">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

