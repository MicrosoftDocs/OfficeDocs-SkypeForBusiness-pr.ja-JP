---
title: 'Lync Server 2013: SQL Server データとログファイルの配置'
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
ms.openlocfilehash: 3f536f2d67010856259abf6b98936cd9e096fc93
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509624"
---
# <a name="sql-server-data-and-log-file-placement-for-lync-server-2013"></a>Lync Server 2013 の SQL Server データとログファイルの配置

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-21_

Lync Server 2013 フロントエンドプールのための Microsoft SQL Server 2012 または Microsoft SQL Server 2008 R2 SP1 の計画と展開では、パフォーマンスを向上するために、データファイルとログファイルを物理ハードディスクに配置することが重要な考慮事項です。 推奨されるディスク構成は、6スピンドルを使用して 1 + 0 RAID セットを実装することです。 [Lync Server 展開ウィザード] を使用して、フロントエンドプールによって使用されるすべてのデータベースとログファイル、および関連するサーバーの役割とサービス (つまり、アーカイブおよび監視サーバー、Lync server Response Group service、Lync Server コールパークサービス) を RAID ドライブセットに配置すると、良好なパフォーマンスをテストした構成になります。 データベース ファイルとその役割の詳細を次の表に示します。

<div>


> [!NOTE]  
> ポリシーと SQL Server の構成でより特殊なインストールが必要な場合は、Lync Server 管理シェルを使用して、定義済みの任意の場所にデータベースとログファイルをインストールできます。 詳細については、「 <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">lync Server 管理シェルを使用したデータベースのインストール 2013</A> 」を参照してください。



</div>

### <a name="data-and-log-files-for-central-management-store"></a>中央管理ストアのデータ ファイルとログ ファイル

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>中央管理ストアデータベースファイル</th>
<th>データ ファイルまたはログ目的</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Xds</p></td>
<td><p>中央管理ストアのトランザクションログファイル</p></td>
</tr>
<tr class="even">
<td><p>Xds</p></td>
<td><p>トポロジビルダーによって定義および公開された、現在の Lync Server 2013 トポロジの構成を維持します。</p></td>
</tr>
<tr class="odd">
<td><p>Lis</p></td>
<td><p>場所情報サービスデータファイル</p></td>
</tr>
<tr class="even">
<td><p>Lis. .ldf</p></td>
<td><p>場所情報サービスデータファイルのトランザクションログ</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-user-conferencing-and-address-book"></a>ユーザー、会議、およびアドレス帳のデータおよびログ ファイル

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>主要な Lync Server 2013 データベースファイル</th>
<th>データ ファイルまたはログ目的</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Rtc</p></td>
<td><p>永続的なユーザーデータ (たとえば、アクセス制御リスト (Acl)、連絡先、スケジュールされた会議)</p></td>
</tr>
<tr class="even">
<td><p>Rtc. .ldf</p></td>
<td><p>Rtc データのトランザクションログ</p></td>
</tr>
<tr class="odd">
<td><p>Rtcdyn</p></td>
<td><p>一時ユーザーデータを保持する (プレゼンスランタイムデータ)</p></td>
</tr>
<tr class="even">
<td><p>Rtcdyn</p></td>
<td><p>Rtcdyn データのトランザクションログ</p></td>
</tr>
<tr class="odd">
<td><p>Rtcab</p></td>
<td><p>リアルタイム通信 (RTC) アドレス帳データベースは、アドレス帳サービス情報が保存される SQL Server リポジトリです。</p></td>
</tr>
<tr class="even">
<td><p>Rtcab. .ldf</p></td>
<td><p>アドレス帳サービスのトランザクション ログ</p></td>
</tr>
<tr class="odd">
<td><p>Rtclocal .mdb</p></td>
<td><p>会議ディレクトリをホストする</p></td>
</tr>
<tr class="even">
<td><p>Rtcxds</p></td>
<td><p>ユーザーデータのバックアップを維持する</p></td>
</tr>
<tr class="odd">
<td><p>Rtcxds</p></td>
<td><p>Rtcxds データのトランザクションログ</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-call-park-and-response-group"></a>通話保留および応答グループのデータとログ ファイル

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>アプリケーション データベース</th>
<th>データ ファイルまたはログ目的</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Cpsdyn.mdf</p></td>
<td><p>コールパークアプリケーションの動的情報データベース</p></td>
</tr>
<tr class="even">
<td><p>Cpsdyn.mdf</p></td>
<td><p>コールパークアプリケーションデータファイルのトランザクションログ</p></td>
</tr>
<tr class="odd">
<td><p>Rgsconfig</p></td>
<td><p>サービスの構成の Lync Server 応答グループ サービス データ ファイル</p></td>
</tr>
<tr class="even">
<td><p>Rgsconfig</p></td>
<td><p>応答グループアプリケーションの構成のトランザクションログファイル</p></td>
</tr>
<tr class="odd">
<td><p>Rgsdyn.mdf</p></td>
<td><p>ランタイム操作の応答グループ サービス データ ファイル</p></td>
</tr>
<tr class="even">
<td><p>Rgsdyn.mdf</p></td>
<td><p>応答グループ サービス ランタイム データ ファイルのトランザクション ログ</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-archiving-and-monitoring-server"></a>アーカイブ サーバーおよび監視サーバーのデータとログ ファイル

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>アーカイブ データベースと監視データベースのファイル</th>
<th>データ ファイルまたはログ目的</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>LcsCdr .mdf</p></td>
<td><p>監視サーバーの通話詳細記録 (CDR) プロセスのデータストア</p></td>
</tr>
<tr class="even">
<td><p>LcsCdr .ldf</p></td>
<td><p>通話詳細記録 (CDR) データのトランザクション ログ</p></td>
</tr>
<tr class="odd">
<td><p>QoEMetrics</p></td>
<td><p>監視サーバーから保存された qoe (Quality of Experience) データファイル</p></td>
</tr>
<tr class="even">
<td><p>QoEMetrics</p></td>
<td><p>監視データのトランザクション ログ</p></td>
</tr>
<tr class="odd">
<td><p>Lcslog .mdf</p></td>
<td><p>アーカイブサーバーでのインスタントメッセージングおよび電話会議データの保持期間のデータファイル</p></td>
</tr>
<tr class="even">
<td><p>Lcslog .ldf</p></td>
<td><p>アーカイブ データのトランザクション ログ</p></td>
</tr>
</tbody>
</table>


このトピックでは、ディスクおよび RAID セットについて説明します。SQL Server リソースの構成では、ディスクへの参照は単一のハードディスク デバイスへの参照を意味します。 2 つのパーティションがある 1 台のハード ディスク ドライブ (1 つはログ ファイルを保持し、もう 1 つのパーティションはデータ ファイルを保持) は、2 台のディスクそれぞれがログ ファイル専用またはデータ ファイル専用になっている状態とは異なります。

RAID セットの場合、さまざまなベンダーから出ている多様な RAID テクノロジが多数あります。 また、ストレージ エリア ネットワーク (SAN) が急増しているため、RAID セットが単一のシステム専用にされることはほとんどありません。 Lync Server 2013 で SQL Server のパフォーマンスを構成する場合は、RAID または SAN ベンダーに問い合わせて、ディスクレイアウトに最適な構成を決定する必要があります。

また、すべてのディスクドライブが同じように作成されるわけではないことにも注意してください。一部の機能は他よりもパフォーマンスが優れています。 同じ製造元のドライブでも、回転速度、ハードウェアキャッシュサイズ、その他の要因によってパフォーマンスが異なる場合があります。

</div>

<span> </span>

</div>

</div>

</div>

