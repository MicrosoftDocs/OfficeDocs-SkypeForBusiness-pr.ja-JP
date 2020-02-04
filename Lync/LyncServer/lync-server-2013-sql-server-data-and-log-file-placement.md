---
title: 'Lync Server 2013: SQL Server データとログ ファイルの配置'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SQL Server data and log file placement
ms:assetid: 67aa525b-8aa3-474f-827e-8e1d4697f30f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398479(v=OCS.15)
ms:contentKeyID: 48184395
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 197141ea62307631eab206fce5403d25b4d89583
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764443"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sql-server-data-and-log-file-placement-for-lync-server-2013"></a>Lync Server 2013 の SQL Server データとログ ファイルの配置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-21_

Lync Server 2013 フロントエンドプール用の Microsoft SQL Server 2012 または Microsoft SQL Server 2008 R2 SP1 の計画および展開中に、パフォーマンスを考慮して、データとログファイルを物理ハードディスクに配置することが重要となります。 推奨されるディスク構成は、6つのスピンドルを使用した 1 + 0 RAID セットの実装です。 フロントエンドプールおよび関連付けられているサーバーの役割とサービスによって使用されるすべてのデータベースファイルとログファイルを配置します。これには、Lync Server を使用している RAID ドライブへのアーカイブと監視サーバー、lync server の応答グループサービス、Lync Server Call パークサービス。展開ウィザードは、良好なパフォーマンスをテストした構成になります。 次の表では、データベースファイルとその役割について説明します。

<div>


> [!NOTE]  
> ポリシーと SQL Server の構成でより特殊なインストールが必要な場合は、Lync Server 管理シェルを使用して、定義済みの場所にデータベースとログファイルをインストールできます。 詳細については、「lync server<A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">の管理シェルを使用したデータベースのインストール 2013</A> 」を参照してください。



</div>

### <a name="data-and-log-files-for-central-management-store"></a>中央管理ストアのデータとログファイル

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>一元管理ストアのデータベースファイル</th>
<th>データファイルまたはログ目的</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Xds</p></td>
<td><p>中央管理ストアのトランザクションログファイル</p></td>
</tr>
<tr class="even">
<td><p>Xds</p></td>
<td><p>トポロジビルダーで定義および公開されている、現在の Lync Server 2013 トポロジの構成を保持します。</p></td>
</tr>
<tr class="odd">
<td><p>Lis</p></td>
<td><p>位置情報サービスデータファイル</p></td>
</tr>
<tr class="even">
<td><p>Lis</p></td>
<td><p>位置情報サービスデータファイルのトランザクションログ</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-user-conferencing-and-address-book"></a>ユーザー、会議、アドレス帳のデータとログファイル

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>主要な Lync Server 2013 データベースファイル</th>
<th>データファイルまたはログ目的</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Rtc</p></td>
<td><p>固定ユーザーデータ (アクセス制御リスト (Acl)、連絡先、スケジュールされた会議など)</p></td>
</tr>
<tr class="even">
<td><p>Rtc. .ldf</p></td>
<td><p>Rtc データのトランザクションログ</p></td>
</tr>
<tr class="odd">
<td><p>Rtcdyn</p></td>
<td><p>一時的なユーザーデータ (プレゼンスランタイムデータ) を保持する</p></td>
</tr>
<tr class="even">
<td><p>Rtcdyn</p></td>
<td><p>Rtcdyn データのトランザクションログ</p></td>
</tr>
<tr class="odd">
<td><p>Rtcab. mdf</p></td>
<td><p>リアルタイム通信 (RTC) アドレス帳データベースは、アドレス帳サービス情報が保存される SQL Server リポジトリです。</p></td>
</tr>
<tr class="even">
<td><p>Rtcab. .ldf</p></td>
<td><p>アドレス帳サービスのトランザクションログ</p></td>
</tr>
<tr class="odd">
<td><p>Rtclocal</p></td>
<td><p>会議ディレクトリのホスト</p></td>
</tr>
<tr class="even">
<td><p>Rtcxds</p></td>
<td><p>ユーザーデータのバックアップを保持する</p></td>
</tr>
<tr class="odd">
<td><p>Rtcxds</p></td>
<td><p>Rtcxds データのトランザクションログ</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-call-park-and-response-group"></a>コールパークと応答グループのデータとログファイル

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>アプリケーション データベース</th>
<th>データファイルまたはログ目的</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Cpsdyn</p></td>
<td><p>コールパークアプリケーションの動的情報データベース</p></td>
</tr>
<tr class="even">
<td><p>Cpsdyn</p></td>
<td><p>コールパークアプリケーションデータファイルのトランザクションログ</p></td>
</tr>
<tr class="odd">
<td><p>Rgsconfig</p></td>
<td><p>サービスの構成用の Lync サーバー応答グループサービスデータファイル</p></td>
</tr>
<tr class="even">
<td><p>Rgsconfig</p></td>
<td><p>応答グループアプリケーション構成のトランザクションログファイル</p></td>
</tr>
<tr class="odd">
<td><p>Rgsdyn</p></td>
<td><p>ランタイム操作の応答グループサービスデータファイル</p></td>
</tr>
<tr class="even">
<td><p>Rgsdyn</p></td>
<td><p>応答グループサービスランタイムデータファイルのトランザクションログ</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-archiving-and-monitoring-server"></a>アーカイブおよび監視サーバー用のデータとログファイル

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>データベースファイルのアーカイブと監視</th>
<th>データファイルまたはログ目的</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>LcsCdr mdf</p></td>
<td><p>監視サーバーの通話の詳細記録 (CDR) プロセスのデータストア</p></td>
</tr>
<tr class="even">
<td><p>LcsCdr .ldf</p></td>
<td><p>通話の詳細記録 (CDR) データのトランザクションログ</p></td>
</tr>
<tr class="odd">
<td><p>QoEMetrics</p></td>
<td><p>監視サーバーから保存された環境の品質データファイル</p></td>
</tr>
<tr class="even">
<td><p>QoEMetrics</p></td>
<td><p>データを監視するためのトランザクションログ</p></td>
</tr>
<tr class="odd">
<td><p>Lcslog</p></td>
<td><p>アーカイブサーバー上のインスタントメッセージングと会議データの保持に使用するデータファイル</p></td>
</tr>
<tr class="even">
<td><p>Lcslog</p></td>
<td><p>データをアーカイブするためのトランザクションログ</p></td>
</tr>
</tbody>
</table>


このトピックでは、ディスクと RAID セットへの参照が行われます。 ディスクを参照する SQL Server リソースの構成では、単一のハードウェアデバイスを指します。 2つのパーティション、1つのログファイルを保持する他のパーティションのハードディスクドライブは、それぞれログファイルまたはデータファイル専用の2つのディスクとは異なります。

RAID セットのリファレンスとして、さまざまなベンダーからのさまざまな RAID テクノロジが用意されています。 また、ストレージエリアネットワーク (SAN) が普及しているため、単一システム専用の RAID セットは非常にまれです。 Lync Server 2013 で SQL Server のパフォーマンスを構成する場合は、使用しているディスクレイアウトの最適な構成を判断するために、お使いの RAID または SAN ベンダーにお問い合わせください。

また、ディスクドライブがすべて同じではないことにも注意してください。他の機能よりも優れたパフォーマンスを発揮します。 同じ製造元のドライブでも、回転速度、ハードウェアキャッシュサイズ、その他の要因によってパフォーマンスが異なる場合があります。

</div>

<span> </span>

</div>

</div>

</div>

