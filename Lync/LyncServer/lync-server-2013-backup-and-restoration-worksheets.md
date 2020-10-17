---
title: 'Lync Server 2013: バックアップと復元のワークシート'
description: 'Lync Server 2013: バックアップと復元のワークシート。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup and restoration worksheets
ms:assetid: 26c78155-0306-41ac-845b-7ad58000a1d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202169(v=OCS.15)
ms:contentKeyID: 51541460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1713e291ae7132cc96309fa499bd97bf7f4f5016
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552323"
---
# <a name="backup-and-restoration-worksheets-for-lync-server-2013"></a>Lync Server 2013 のバックアップと復元のワークシート

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-18_

組織のバックアップと復元の計画には、データと設定をバックアップする方法と時期の詳細が含まれている必要があります。 ここに示されているワークシートを使用して、特定の展開および組織のバックアップと復元の要件に関する情報を文書化することができます。

次のワークシートを使用して、Lync Server プールまたは Standard Edition サーバーのデータベース、ファイルストア、および設定に関する情報をバックアップおよび復元するために必要な情報を記録します。 Lync Server を復元する必要がある場合に容易にアクセスできるように、これらのワークシートの1つ以上のコピーを安全な場所に保管してください。

<div>


> [!NOTE]  
> このセクションのワークシートでは、Lync Server データベースおよびサーバーのデータと設定を復元するために必要な情報のみを説明します。 オペレーティングシステムおよびその他のソフトウェアを再インストールするための情報など、他の復元情報を文書化する必要がある場合は、組織の展開計画と、それらの要件に対応するためのバックアップと復元の計画を使用します。



</div>

<div>

## <a name="database-backup-and-restoration-worksheet"></a>データベースのバックアップと復元のワークシート

次の表を使用して、Lync Server データベースのバックアップと復元に必要な情報を記録します。

### <a name="database-information-for-backup-and-restoration"></a>バックアップと復元のためのデータベース情報

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>Database</th>
<th>サーバー名 (FQDN)</th>
<th>バックアップスケジュール</th>
<th>データベースバックアップツール</th>
<th>バックアップセット</th>
<th>バックアップ先</th>
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>バックエンドサーバー上のユーザーデータ用の Rtc データベース</p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><strong>Export-CsUserData</strong> コマンドレット</p></td>
<td><p>拡張子</p>
<p>Nntp</p>
<p>                   </p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
</tr>
<tr class="even">
<td><p>アーカイブデータベースサーバー上の LcsLog (既定の名前) データベース</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>SQL Server 管理ツール</p></td>
<td><p>拡張子</p>
<p>Nntp</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p>通話詳細レコードの監視データベースサーバー上の LcsCdr データベース (Cdr)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>SQL Server 管理ツール</p></td>
<td><p>拡張子</p>
<p>Nntp</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p>QoEMetrics データベースサーバーの監視データベースサーバーでの、QoE (Quality of Experience) データ</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>SQL Server 管理ツール</p></td>
<td><p>拡張子</p>
<p>Nntp</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p>常設チャットデータベース</p></td>
<td></td>
<td></td>
<td><p>SQL Server 管理ツールまたは <strong>export-cspersistentchatdata</strong> コマンドレット</p></td>
<td><p>拡張子</p>
<p>Nntp</p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


次のデータベースのバックアップまたは復元は必要ありません。

  - Rtcdyn. このデータベースの一時ユーザーデータは、サービスの復元には必要ありません。

  - Rtcab. アドレス帳データベースは、Active Directory ドメインサービスのグローバルアドレス一覧 (GAL) から自動的に再作成されます。

  - Rgsdyn.mdf. このデータベース内の一時応答グループサービスデータは、サービスの復元には必要ありません。

  - Cpsdyn.mdf. コールパークアプリケーションの動的情報は、サービスの復元には必要ありません。

  - MgcComp. 常設チャットのコンプライアンスデータベースは、サービスの復元には必要ありません。

</div>

<div>

## <a name="file-store-backup-and-restoration-worksheet"></a>ファイルストアのバックアップと復元のワークシート

次の表を使用して、ファイルストアのバックアップと復元に必要な情報を記録します。 ファイルストアには、会議コンテンツのメタデータ、会議のコンプライアンスログ、デバイス更新のための更新ログ、応答グループ、コールパーク、アナウンスアプリケーションのオーディオファイルなどのデータが含まれています。

### <a name="file-store-information-for-backup-and-restoration"></a>バックアップと復元のためのファイルストア情報

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>コンテンツ</th>
<th>サーバー名 (FQDN)</th>
<th>バックアップスケジュール</th>
<th>ファイルシステムバックアップツール</th>
<th>バックアップするファイル共有 *</th>
<th>バックアップ先</th>
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server ファイルストア</p></td>
<td></td>
<td></td>
<td><p>標準バックアップツール (Robocopy など)</p></td>
<td><p>Enterprise Edition のファイルサーバー。 Standard edition では、standard edition の展開に既定で適用されます。 通常は、サイトごとに1つ。</p></td>
<td></td>
<td><p><strong>Meeting.Active</strong> という名前のファイルはバックアップしないでください。 これらのファイルは使用中で、会議中にロックされます。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="settings-backup-and-restoration-worksheet"></a>[設定のバックアップと復元] ワークシート

次の表を使用して、設定をバックアップおよび復元するために必要な情報を記録します。

### <a name="settings-information-for-backup-and-restoration"></a>バックアップと復元の設定情報

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>Database</th>
<th>サーバー名 (FQDN)</th>
<th>バックアップスケジュール</th>
<th>バックアップツール</th>
<th>構成ファイル (.xml) 名</th>
<th>バックアップの場所</th>
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>トポロジ構成用の中央管理ストアの Xds データベース (グローバル)</p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><strong>Export-CsConfiguration</strong> コマンドレット</p></td>
<td><p>                   </p></td>
<td><p>                    </p></td>
<td><p>                   </p></td>
</tr>
<tr class="even">
<td><p>E9-1-1 場所情報 (グローバル) の中央管理ストアの Lis データベース</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><strong>Export-cslisconfiguration</strong> コマンドレット</p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
<tr class="odd">
<td><p>応答グループ構成のバックエンドサーバー上の RgsConfig データベース (プール)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><strong>Export-CsRgsConfiguration</strong> コマンドレット</p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

