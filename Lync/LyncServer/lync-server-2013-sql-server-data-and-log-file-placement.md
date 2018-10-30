---
title: 'Lync Server 2013: SQL Server データとログ ファイルの配置'
TOCTitle: SQL Server データとログ ファイルの配置
ms:assetid: 67aa525b-8aa3-474f-827e-8e1d4697f30f
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398479(v=OCS.15)
ms:contentKeyID: 48272361
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の SQL Server データとログ ファイルの配置

 

_**トピックの最終更新日:** 2015-03-09_

Microsoft SQL Server 2012 または Microsoft SQL Server 2008 R2 SP1 を Lync Server 2013フロント エンド プール用に計画、展開する際に重要なのは、パフォーマンスを向上させるためにデータ ファイルとログ ファイルをどのように物理ハード ディスクに配置するかという点です。推奨のディスク構成は、6 スピンドルを使用した 1+0 RAID セットの実装です。Lync Server 展開ウィザードを使用している RAID ドライブ セットに、フロント エンド プールと関連するサーバーの役割およびサービス (つまり、アーカイブおよび監視サーバー、Lync Server 応答グループ サービス、Lync Server コール パーク サービス) によって使用されるすべてのデータベースとログ ファイルを配置する構成は、よいパフォーマンスが得られることがテストで確認されています。データベース ファイルとその役割の詳細を次の表に示します。

> [!NOTE]
> ポリシーと SQL Server 構成がより特殊なインストールを必要とする場合、データベースとログ ファイルは Lync Server 管理シェルを使用して、任意の定義済みの場所にインストールできます。詳細は、「<a href="lync-server-2013-database-installation-using-lync-server-management-shell.md">Lync Server 2013 での Lync Server 管理シェルを使用したデータベースのインストール</a>」を参照してください。


### 中央管理ストアのデータ ファイルとログ ファイル

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>中央管理ストアのデータベース ファイル</th>
<th>データ ファイルまたはログ目的</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Xds.ldf</p></td>
<td><p>中央管理ストアのトランザクション ログ ファイル</p></td>
</tr>
<tr class="even">
<td><p>Xds.mdf</p></td>
<td><p>トポロジ ビルダーによって定義および公開されたとおりの現在の Lync Server 2013 トポロジの構成を保持</p></td>
</tr>
<tr class="odd">
<td><p>Lis.mdf</p></td>
<td><p>場所情報サービス のデータ ファイル</p></td>
</tr>
<tr class="even">
<td><p>Lis.ldf</p></td>
<td><p>場所情報サービスのデータ ファイルのトランザクション ログ</p></td>
</tr>
</tbody>
</table>


### ユーザー、会議、およびアドレス帳のデータおよびログ ファイル

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Lync Server 2013 のコア データベース ファイル</th>
<th>データ ファイルまたはログ目的</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Rtc.mdf</p></td>
<td><p>常設ユーザー データ (たとえば、アクセス制御リスト (ACL)、連絡先、スケジュールされた電話会議)</p></td>
</tr>
<tr class="even">
<td><p>Rtc.ldf</p></td>
<td><p>Rtc データのトランザクション ログ</p></td>
</tr>
<tr class="odd">
<td><p>Rtcdyn.mdf</p></td>
<td><p>一時ユーザー データ (プレゼンス実行時データ) を管理します</p></td>
</tr>
<tr class="even">
<td><p>Rtcdyn.ldf</p></td>
<td><p>Rtcdyn データのトランザクション ログ</p></td>
</tr>
<tr class="odd">
<td><p>Rtcab.mdf</p></td>
<td><p>リアルタイム通信 (RTC) アドレス帳データベースは、アドレス帳サービス情報が保存される SQL Server リポジトリです。</p></td>
</tr>
<tr class="even">
<td><p>Rtcab.ldf</p></td>
<td><p>アドレス帳サービスのトランザクション ログ</p></td>
</tr>
<tr class="odd">
<td><p>Rtclocal.mdb</p></td>
<td><p>会議ディレクトリをホスト</p></td>
</tr>
<tr class="even">
<td><p>Rtcxds.mdf</p></td>
<td><p>ユーザー データのバックアップを保持</p></td>
</tr>
<tr class="odd">
<td><p>Rtcxds.ldf</p></td>
<td><p>Rtcxds データのトランザクション ログ</p></td>
</tr>
</tbody>
</table>


### 通話保留および応答グループのデータとログ ファイル

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
<td><p>コール パーク アプリケーションの動的な情報データベース</p></td>
</tr>
<tr class="even">
<td><p>Cpsdyn.ldf</p></td>
<td><p>コール パーク アプリケーションのデータ ファイルのトランザクション ログ</p></td>
</tr>
<tr class="odd">
<td><p>Rgsconfig.mdf</p></td>
<td><p>サービスの構成の Lync Server 応答グループ サービス データ ファイル</p></td>
</tr>
<tr class="even">
<td><p>Rgsconfig.ldf</p></td>
<td><p>応答グループ アプリケーションの構成のトランザクション ログ ファイル</p></td>
</tr>
<tr class="odd">
<td><p>Rgsdyn.mdf</p></td>
<td><p>ランタイム操作の応答グループ サービス データ ファイル</p></td>
</tr>
<tr class="even">
<td><p>Rgsdyn.ldf</p></td>
<td><p>応答グループ サービス ランタイム データ ファイルのトランザクション ログ</p></td>
</tr>
</tbody>
</table>


### アーカイブ サーバーおよび監視サーバーのデータとログ ファイル

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
<td><p>LcsCdr.mdf</p></td>
<td><p>監視サーバーの通話詳細記録 (CDR) プロセスのデータ ストア</p></td>
</tr>
<tr class="even">
<td><p>LcsCdr.ldf</p></td>
<td><p>通話詳細記録 (CDR) データのトランザクション ログ</p></td>
</tr>
<tr class="odd">
<td><p>QoEMetrics.mdf</p></td>
<td><p>監視サーバーから保存した体感品質データ ファイル</p></td>
</tr>
<tr class="even">
<td><p>QoEMetrics.ldf</p></td>
<td><p>監視データのトランザクション ログ</p></td>
</tr>
<tr class="odd">
<td><p>Lcslog.mdf</p></td>
<td><p>アーカイブ サーバー上のインスタント メッセージングおよび電話会議のデータの保持期間のデータ ファイル</p></td>
</tr>
<tr class="even">
<td><p>Lcslog.ldf</p></td>
<td><p>アーカイブ データのトランザクション ログ</p></td>
</tr>
</tbody>
</table>


このトピックでは、ディスクおよび RAID セットについて説明します。SQL Server リソースの構成では、ディスクへの参照は単一のハードディスク デバイスへの参照を意味します。2 つのパーティションがある 1 台のハード ディスク ドライブ (1 つはログ ファイルを保持し、もう 1 つのパーティションはデータ ファイルを保持) は、2 台のディスクそれぞれがログ ファイル専用またはデータ ファイル専用になっている状態とは異なります。

RAID セットの場合、さまざまなベンダーから出ている多様な RAID テクノロジが多数あります。また、ストレージ エリア ネットワーク (SAN) が急増しているため、RAID セットが単一のシステム専用にされることはほとんどありません。SQL Server を Lync Server 2013 で構成する場合のディスク レイアウトに最適な構成を決定するには、RAID または SAN ベンダーに相談する必要があります。

また、すべてのディスク ドライブが同じように作成されるわけではありません。一部のディスク ドライブは他のディスク ドライブよりも高パフォーマンスになります。同じメーカーのドライブでも、回転速度、ハードウェアのキャッシュ サイズ、その他の要因により、パフォーマンスに差が生じることがあります。

