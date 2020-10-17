---
title: 'Lync Server 2013: QoE テーブルの一覧'
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
ms.openlocfilehash: 2c5078ac2e8e97364455d88d32c79a03c58f0c2f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513834"
---
# <a name="list-of-qoe-tables-in-lync-server-2013"></a><span data-ttu-id="222c8-102">Lync Server 2013 の QoE テーブルの一覧</span><span class="sxs-lookup"><span data-stu-id="222c8-102">List of QoE tables in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="222c8-103">_**トピックの最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="222c8-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="222c8-104">データベース スキーマは、次のテーブルで構成されます。</span><span class="sxs-lookup"><span data-stu-id="222c8-104">The database schema consists of the following tables.</span></span>

<span data-ttu-id="222c8-105">**サポート テーブル**</span><span class="sxs-lookup"><span data-stu-id="222c8-105">**Supporting Tables**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="222c8-106"><strong>Table</strong></span><span class="sxs-lookup"><span data-stu-id="222c8-106"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="222c8-107"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="222c8-107"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="222c8-108"><a href="lync-server-2013-appsharingmetricsthreshold-table.md">Lync Server 2013 の AppSharingMetricsThreshold テーブル</a></span><span class="sxs-lookup"><span data-stu-id="222c8-108"><a href="lync-server-2013-appsharingmetricsthreshold-table.md">AppSharingMetricsThreshold table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="222c8-109">アプリケーション共有で使用される QoE 指標の最適値および許容値を格納します。</span><span class="sxs-lookup"><span data-stu-id="222c8-109">Stores optimal and acceptable values for the Quality of Experience metrics used with application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="222c8-110"><a href="lync-server-2013-codecdescription-table.md">Lync Server 2013 の CodecDescription テーブル</a></span><span class="sxs-lookup"><span data-stu-id="222c8-110"><a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="222c8-111">一意のコーデック識別子を対応するコーデックにマッピングします。</span><span class="sxs-lookup"><span data-stu-id="222c8-111">Maps unique codec identifiers to their corresponding codec.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="222c8-112"><a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a></span><span class="sxs-lookup"><span data-stu-id="222c8-112"><a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="222c8-113">IP アドレスを、QoE データベース内の他の場所で使用される一意の IP アドレス識別子にマッピングします。</span><span class="sxs-lookup"><span data-stu-id="222c8-113">Maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="222c8-114"><a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 の NetworkConnectionDetail テーブル</a></span><span class="sxs-lookup"><span data-stu-id="222c8-114"><a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="222c8-115">ネットワーク接続の種類を、QoE データベース内の他の場所で使用されるネットワーク接続識別子にマッピングします。</span><span class="sxs-lookup"><span data-stu-id="222c8-115">Maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="222c8-116"><a href="lync-server-2013-purgesettings-table-qoe.md">Lync Server 2013 の PurgeSettings テーブル (QoE)</a></span><span class="sxs-lookup"><span data-stu-id="222c8-116"><a href="lync-server-2013-purgesettings-table-qoe.md">PurgeSettings table (QoE) in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="222c8-117">古くなった QoE レコードが QoE データベースから自動的に削除されるかどうか (およびそのタイミング) を指定する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="222c8-117">Stores information that specifies if (and when) outdated Quality of Experience records will automatically be deleted from the QoE database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="222c8-118"><a href="lync-server-2013-traceroute-table.md">Lync Server 2013 の TraceRoute テーブル</a></span><span class="sxs-lookup"><span data-stu-id="222c8-118"><a href="lync-server-2013-traceroute-table.md">TraceRoute table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="222c8-119">通話のルーティング情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="222c8-119">Stores routing information for calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="222c8-120"><a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 の UserAgentDef テーブル (QoE)</a></span><span class="sxs-lookup"><span data-stu-id="222c8-120"><a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="222c8-121">ユーザー エージェント識別子をエージェントを表す名前にマッピングします。</span><span class="sxs-lookup"><span data-stu-id="222c8-121">Maps user agent identifiers to the agent’s descriptive names.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="222c8-122"><a href="lync-server-2013-videometricsthreshold-table.md">Lync Server 2013 の VideoMetricsThreshold テーブル</a></span><span class="sxs-lookup"><span data-stu-id="222c8-122"><a href="lync-server-2013-videometricsthreshold-table.md">VideoMetricsThreshold table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="222c8-123">ビデオ通話で使用される QoE 指標の最適値および許容値を格納します。</span><span class="sxs-lookup"><span data-stu-id="222c8-123">Stores optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="222c8-124"><a href="lync-server-2013-useragent-table.md">Lync Server 2013 の UserAgent テーブル</a></span><span class="sxs-lookup"><span data-stu-id="222c8-124"><a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="222c8-125">音声およびビデオ セッションで使用されるセッション開始プロトコル (SIP) ユーザー エージェント (UA) 文字列および UA の種類を格納します。</span><span class="sxs-lookup"><span data-stu-id="222c8-125">Stores Session Initiation Protocol (SIP) User Agent (UA) strings and UA types used in audio and video sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="222c8-126"><a href="lync-server-2013-user-table.md">Lync Server 2013 のユーザーテーブル</a></span><span class="sxs-lookup"><span data-stu-id="222c8-126"><a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="222c8-127">音声およびビデオ セッションで使用されるユーザー、会議、電話の URI を格納します。</span><span class="sxs-lookup"><span data-stu-id="222c8-127">Stores user, conference, and phone URIs used in audio and video sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="222c8-128"><a href="lync-server-2013-endpoint-table.md">Lync Server 2013 のエンドポイントテーブル</a></span><span class="sxs-lookup"><span data-stu-id="222c8-128"><a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="222c8-129">音声およびビデオ セッションに参加しているエンドポイントの FQDN コンピューター名を格納します。</span><span class="sxs-lookup"><span data-stu-id="222c8-129">Stores FQDN computer names of endpoints participating in audio and video sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="222c8-130"><a href="lync-server-2013-pool-table.md">Lync Server 2013 のプールテーブル</a></span><span class="sxs-lookup"><span data-stu-id="222c8-130"><a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="222c8-131">指標データが属するプールの名前を格納します。</span><span class="sxs-lookup"><span data-stu-id="222c8-131">Stores the names of pools to which metrics data belongs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="222c8-132"><a href="lync-server-2013-device-table.md">Lync Server 2013 のデバイステーブル</a></span><span class="sxs-lookup"><span data-stu-id="222c8-132"><a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="222c8-133">音声ビデオ通話で使用されるキャプチャ デバイスおよびレンダー デバイスを格納します。</span><span class="sxs-lookup"><span data-stu-id="222c8-133">Stores capture devices and render devices which are used in an audio/video calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="222c8-134"><a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 の DeviceDriver テーブル</a></span><span class="sxs-lookup"><span data-stu-id="222c8-134"><a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="222c8-135">音声ビデオ通話で使用されるキャプチャ デバイスおよびレンダー デバイスのドライバーを格納します。</span><span class="sxs-lookup"><span data-stu-id="222c8-135">Stores driver for the capture device and the render device which are used in audio/video calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="222c8-136"><a href="lync-server-2013-conference-table.md">Lync Server 2013 の会議テーブル</a></span><span class="sxs-lookup"><span data-stu-id="222c8-136"><a href="lync-server-2013-conference-table.md">Conference table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="222c8-137">会議シナリオの会議 URI または他のシナリオの DialogID を格納します。</span><span class="sxs-lookup"><span data-stu-id="222c8-137">Stores Conference URIs for conference scenarios or DialogID for other scenarios.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="222c8-138"><a href="lync-server-2013-sessioncorrelation-table.md">Lync Server 2013 の SessionCorrelation テーブル</a></span><span class="sxs-lookup"><span data-stu-id="222c8-138"><a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="222c8-139">PSTN 通話の CorrelationID を格納します。</span><span class="sxs-lookup"><span data-stu-id="222c8-139">Stores CorrelationID for PSTN calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="222c8-140"><a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 の PayloadDescription テーブル</a></span><span class="sxs-lookup"><span data-stu-id="222c8-140"><a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="222c8-141">音声ビデオ通話で使用されるコーデックを格納します。</span><span class="sxs-lookup"><span data-stu-id="222c8-141">Stores the Codec used in audio/video calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="222c8-142"><a href="lync-server-2013-appliedbandwidthsource-table.md">Lync Server 2013 の AppliedBandwidthSource テーブル</a></span><span class="sxs-lookup"><span data-stu-id="222c8-142"><a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="222c8-143">音声ビデオ通話で使用される帯域幅ソースを格納します。</span><span class="sxs-lookup"><span data-stu-id="222c8-143">Stores the bandwidth source used in audio/video calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="222c8-144"><a href="lync-server-2013-macaddress-table.md">Lync Server 2013 の MacAddress テーブル</a></span><span class="sxs-lookup"><span data-stu-id="222c8-144"><a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="222c8-145">音声およびビデオ セッションに参加しているエンドポイントの MAC アドレスを格納します。</span><span class="sxs-lookup"><span data-stu-id="222c8-145">Stores the MAC address of the endpoints participating in audio and video sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="222c8-146"><a href="lync-server-2013-dialog-table.md">Lync Server 2013 のダイアログテーブル</a></span><span class="sxs-lookup"><span data-stu-id="222c8-146"><a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="222c8-147">音声およびビデオ セッションのダイアログ ID を格納します。</span><span class="sxs-lookup"><span data-stu-id="222c8-147">Stores the Dialog ID of audio and video sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="222c8-148"><a href="lync-server-2013-region-table.md">Lync Server 2013 の Region テーブル</a></span><span class="sxs-lookup"><span data-stu-id="222c8-148"><a href="lync-server-2013-region-table.md">Region table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="222c8-149">NCS 設定で定義されているネットワーク地域を格納します。</span><span class="sxs-lookup"><span data-stu-id="222c8-149">Stores the network region defined in NCS setting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="222c8-150"><a href="lync-server-2013-usersite-table.md">Lync Server 2013 の UserSite テーブル</a></span><span class="sxs-lookup"><span data-stu-id="222c8-150"><a href="lync-server-2013-usersite-table.md">UserSite table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="222c8-151">NCS 設定で定義されているネットワーク サイトを格納します。</span><span class="sxs-lookup"><span data-stu-id="222c8-151">Stores the network site defined in NCS setting.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="222c8-152"><a href="lync-server-2013-subnet-table.md">Lync Server 2013 のサブネットテーブル</a></span><span class="sxs-lookup"><span data-stu-id="222c8-152"><a href="lync-server-2013-subnet-table.md">Subnet table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="222c8-153">NCS 設定で定義されているサブネットを格納します。</span><span class="sxs-lookup"><span data-stu-id="222c8-153">Stores the subnet defined in NCS setting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="222c8-154"><a href="lync-server-2013-monitoredregionlink-table.md">Lync Server 2013 の MonitoredRegionLink テーブル</a></span><span class="sxs-lookup"><span data-stu-id="222c8-154"><a href="lync-server-2013-monitoredregionlink-table.md">MonitoredRegionLink table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="222c8-155">NCS 設定で定義されている地域リンクを格納します。</span><span class="sxs-lookup"><span data-stu-id="222c8-155">Stores the region link defined in NCS setting.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="222c8-156"><a href="monitoredusersitelink-table.md">MonitoredUserSiteLink リンクテーブル</a></span><span class="sxs-lookup"><span data-stu-id="222c8-156"><a href="monitoredusersitelink-table.md">MonitoredUserSiteLink table</a></span></span></p></td>
<td><p><span data-ttu-id="222c8-157">NCS 設定で定義されているネットワーク サイト リンクを格納します。</span><span class="sxs-lookup"><span data-stu-id="222c8-157">Stores the network site links defined in NCS setting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="222c8-158"><a href="lync-server-2013-endpointsubnet-table.md">Lync Server 2013 の EndpointSubnet テーブル</a></span><span class="sxs-lookup"><span data-stu-id="222c8-158"><a href="lync-server-2013-endpointsubnet-table.md">EndpointSubnet table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="222c8-159">音声およびビデオ セッションに参加しているエンドポイントのサブネットを格納します。</span><span class="sxs-lookup"><span data-stu-id="222c8-159">Stores the subnet of the endpoint participating in an audio and video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="222c8-160"><a href="lync-server-2013-server-table.md">Lync Server 2013 のサーバーテーブル</a></span><span class="sxs-lookup"><span data-stu-id="222c8-160"><a href="lync-server-2013-server-table.md">Server table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="222c8-161">メディアが通過するサーバーの FQDN または IP アドレスを格納します。</span><span class="sxs-lookup"><span data-stu-id="222c8-161">Stores the FQDN or IP address of the server the media goes through.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="222c8-162">**指標データ用テーブル**</span><span class="sxs-lookup"><span data-stu-id="222c8-162">**Tables for metrics data**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="222c8-163"><strong>Table</strong></span><span class="sxs-lookup"><span data-stu-id="222c8-163"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="222c8-164"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="222c8-164"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="222c8-165"><a href="lync-server-2013-appsharingstream-table.md">Lync Server 2013 の AppSharingStream テーブル</a></span><span class="sxs-lookup"><span data-stu-id="222c8-165"><a href="lync-server-2013-appsharingstream-table.md">AppSharingStream table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="222c8-p101">アプリケーション共有で使用されるネットワーク ストリームの QoE 指標を格納します。</span><span class="sxs-lookup"><span data-stu-id="222c8-p101">Stores Quality of Experience metrics for the network streams used for application sharing. Quality of Experience metrics for the network streams used for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="222c8-168"><a href="lync-server-2013-session-table.md">Lync Server 2013 の Session テーブル</a></span><span class="sxs-lookup"><span data-stu-id="222c8-168"><a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="222c8-169">音声セッションまたは音声ビデオ セッションに関する全体的な情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="222c8-169">Stores overall information about an audio or audio/video session.</span></span> <span data-ttu-id="222c8-170">セッションとは、2 つのエンドポイント間の音声またはビデオでの SIP ダイアログと定義されます。</span><span class="sxs-lookup"><span data-stu-id="222c8-170">A session is defined as an audio or video SIP dialog between two endpoints.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="222c8-171"><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a></span><span class="sxs-lookup"><span data-stu-id="222c8-171"><a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="222c8-p103">セッションでの各メディア ラインについての情報を格納します。メディア ラインとは、1 つ以上の音声およびビデオ ストリームのコレクションです。通常、1 つのメディア ラインには音声またはビデオの 2 つのストリームが含まれます。</span><span class="sxs-lookup"><span data-stu-id="222c8-p103">Stores information about each media line in a session. A media line is a collection of one or more audio and video streams. Typically, a single media line will have two streams, either audio or video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="222c8-175"><a href="lync-server-2013-audiostream-table.md">Lync Server 2013 の AudioStream テーブル</a></span><span class="sxs-lookup"><span data-stu-id="222c8-175"><a href="lync-server-2013-audiostream-table.md">AudioStream table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="222c8-176">メディア ラインに含まれる各音声ストリームの音声メディア品質指標を格納します。</span><span class="sxs-lookup"><span data-stu-id="222c8-176">Stores audio media quality metrics for each audio stream in the media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="222c8-177"><a href="lync-server-2013-audiosignal-table.md">Lync Server 2013 の AudioSignal テーブル</a></span><span class="sxs-lookup"><span data-stu-id="222c8-177"><a href="lync-server-2013-audiosignal-table.md">AudioSignal table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="222c8-178">メディア ラインの音声メディア品質指標を格納します。</span><span class="sxs-lookup"><span data-stu-id="222c8-178">Stores audio media quality metrics in the media line.</span></span> <span data-ttu-id="222c8-179">これには、アコーステック エコー キャンセレーション (AEC) 指標および自動ゲイン制御 (AGC) 指標が含まれます。</span><span class="sxs-lookup"><span data-stu-id="222c8-179">This includes acoustic echo cancellation (AEC) and automatic gain control (AGC) metrics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="222c8-180"><a href="lync-server-2013-videostream-table.md">Lync Server 2013 の VideoStream テーブル</a></span><span class="sxs-lookup"><span data-stu-id="222c8-180"><a href="lync-server-2013-videostream-table.md">VideoStream table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="222c8-181">メディア ラインに含まれる各音声ストリームのビデオ メディア品質指標を格納します。</span><span class="sxs-lookup"><span data-stu-id="222c8-181">Stores video media quality metrics for each audio stream in the media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="222c8-182"><a href="lync-server-2013-audioclientevent-table.md">Lync Server 2013 の AudioClientEvent テーブル</a></span><span class="sxs-lookup"><span data-stu-id="222c8-182"><a href="lync-server-2013-audioclientevent-table.md">AudioClientEvent table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="222c8-183">クライアント イベントから収集された音声メディア品質指標を格納します。</span><span class="sxs-lookup"><span data-stu-id="222c8-183">Stores audio media quality metrics collected from the client event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="222c8-184"><a href="lync-server-2013-videoclientevent-table.md">Lync Server 2013 の VideoClientEvent テーブル</a></span><span class="sxs-lookup"><span data-stu-id="222c8-184"><a href="lync-server-2013-videoclientevent-table.md">VideoClientEvent table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="222c8-185">クライアント イベントから収集されたビデオ メディア品質指標を格納します。</span><span class="sxs-lookup"><span data-stu-id="222c8-185">Stores video media quality metrics collected from the client event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="222c8-186"><strong>DiagnosticData テーブル</strong></span><span class="sxs-lookup"><span data-stu-id="222c8-186"><strong>DiagnosticData Table</strong></span></span></p></td>
<td><p><span data-ttu-id="222c8-187">内部使用専用の診断データを格納します。</span><span class="sxs-lookup"><span data-stu-id="222c8-187">Stores diagnostic data which is for internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="222c8-188">**概要データ用テーブル**</span><span class="sxs-lookup"><span data-stu-id="222c8-188">**Tables for summary data**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="222c8-189"><strong>Table</strong></span><span class="sxs-lookup"><span data-stu-id="222c8-189"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="222c8-190"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="222c8-190"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="222c8-191"><strong>ServerSummary テーブル</strong></span><span class="sxs-lookup"><span data-stu-id="222c8-191"><strong>ServerSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="222c8-192">サーバーの概要データを格納します。このデータは、QoE (Quality of Experience) レポートのみに使用されます。</span><span class="sxs-lookup"><span data-stu-id="222c8-192">Stores summary data for the servers, these data is used for Quality of Experience (QoE) reporting only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="222c8-193"><strong>UserSummary テーブル</strong></span><span class="sxs-lookup"><span data-stu-id="222c8-193"><strong>UserSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="222c8-194">ユーザーの概要データを格納します。このデータは、QoE レポートのみに使用されます。</span><span class="sxs-lookup"><span data-stu-id="222c8-194">Stores summary data for users, these data is used for QoE reporting only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="222c8-195"><strong>CallTypeSummary テーブル</strong></span><span class="sxs-lookup"><span data-stu-id="222c8-195"><strong>CallTypeSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="222c8-196">通話種類の概要データを格納します。このデータは、QoE レポートのみに使用されます。</span><span class="sxs-lookup"><span data-stu-id="222c8-196">Store summary data for call types, these data is used for QoE reporting only.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="222c8-197">**監視サーバーの内部用テーブル**</span><span class="sxs-lookup"><span data-stu-id="222c8-197">**Tables for Internal Use by Monitoring Server**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="222c8-198"><strong>Table</strong></span><span class="sxs-lookup"><span data-stu-id="222c8-198"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="222c8-199"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="222c8-199"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="222c8-200"><strong>DbConfigDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="222c8-200"><strong>DbConfigDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="222c8-201">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="222c8-201">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="222c8-202"><strong>DbConfigInt</strong></span><span class="sxs-lookup"><span data-stu-id="222c8-202"><strong>DbConfigInt</strong></span></span></p></td>
<td><p><span data-ttu-id="222c8-203">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="222c8-203">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="222c8-204"><strong>FrontEnd テーブル</strong></span><span class="sxs-lookup"><span data-stu-id="222c8-204"><strong>FrontEnd Table</strong></span></span></p></td>
<td><p><span data-ttu-id="222c8-205">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="222c8-205">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="222c8-206"><strong>Task テーブル</strong></span><span class="sxs-lookup"><span data-stu-id="222c8-206"><strong>Task Table</strong></span></span></p></td>
<td><p><span data-ttu-id="222c8-207">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="222c8-207">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="222c8-208"><strong>概要 (Tabl)</strong></span><span class="sxs-lookup"><span data-stu-id="222c8-208"><strong>SummaryTableConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="222c8-209">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="222c8-209">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="222c8-210"><strong>DbErrorMessage</strong></span><span class="sxs-lookup"><span data-stu-id="222c8-210"><strong>DbErrorMessage</strong></span></span></p></td>
<td><p><span data-ttu-id="222c8-211">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="222c8-211">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="222c8-212"><strong>MetricsThreshold</strong></span><span class="sxs-lookup"><span data-stu-id="222c8-212"><strong>MetricsThreshold</strong></span></span></p></td>
<td><p><span data-ttu-id="222c8-213">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="222c8-213">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="222c8-214"><strong>DaylightSavingYears</strong></span><span class="sxs-lookup"><span data-stu-id="222c8-214"><strong>DaylightSavingYears</strong></span></span></p></td>
<td><p><span data-ttu-id="222c8-215">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="222c8-215">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="222c8-216"><strong>TimeZoneConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="222c8-216"><strong>TimeZoneConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="222c8-217">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="222c8-217">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="222c8-218"><strong>TimeZones</strong></span><span class="sxs-lookup"><span data-stu-id="222c8-218"><strong>TimeZones</strong></span></span></p></td>
<td><p><span data-ttu-id="222c8-219">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="222c8-219">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="222c8-220"><strong>CallSummary テーブル</strong></span><span class="sxs-lookup"><span data-stu-id="222c8-220"><strong>CallSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="222c8-221">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="222c8-221">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="222c8-222"><strong>DeviceCallSumary テーブル</strong></span><span class="sxs-lookup"><span data-stu-id="222c8-222"><strong>DeviceCallSumary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="222c8-223">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="222c8-223">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="222c8-224"><strong>Tenant テーブル</strong></span><span class="sxs-lookup"><span data-stu-id="222c8-224"><strong>Tenant Table</strong></span></span></p></td>
<td><p><span data-ttu-id="222c8-225">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="222c8-225">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="222c8-226"><strong>VideoCallSummaryTable</strong></span><span class="sxs-lookup"><span data-stu-id="222c8-226"><strong>VideoCallSummaryTable</strong></span></span></p></td>
<td><p><span data-ttu-id="222c8-227">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="222c8-227">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="222c8-228"><strong>Ascall概要テーブル</strong></span><span class="sxs-lookup"><span data-stu-id="222c8-228"><strong>ASCallSummaryTable</strong></span></span></p></td>
<td><p><span data-ttu-id="222c8-229">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="222c8-229">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

