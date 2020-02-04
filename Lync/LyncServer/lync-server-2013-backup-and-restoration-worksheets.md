---
title: 'Lync Server 2013: バックアップと復元のワークシート'
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
ms.openlocfilehash: 390d6289daf8075c873e90319642f0e74b61d835
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730367"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-worksheets-for-lync-server-2013"></a>Lync Server 2013 のバックアップと復元ワークシート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-18_

組織のバックアップと復元の計画には、データと設定をバックアップする方法とタイミングについての詳細が含まれている必要があります。 ここに記載されているワークシートを使用して、特定の展開や組織のバックアップと復元の要件について、この情報を文書化することができます。

次のワークシートを使用して、Lync Server プールまたは Standard Edition サーバーのデータベース、ファイルストア、設定情報をバックアップおよび復元するために必要な情報を記録します。 Lync Server を復元する必要がある場合は、これらのワークシートのコピーを安全な場所に保管して、簡単にアクセスできるようにします。

<div>


> [!NOTE]  
> このセクションのワークシートには、Lync Server データベースおよびサーバーのデータと設定を復元するために必要な情報のみが記載されています。 オペレーティングシステムやその他のソフトウェアの再インストールに関する情報など、他の復元情報を文書化する必要がある場合は、組織の展開計画とバックアップおよび復元計画を使用して、これらの要件に対応します。



</div>

<div>

## <a name="database-backup-and-restoration-worksheet"></a>データベースのバックアップと復元のワークシート

次の表を使用して、Lync Server データベースのバックアップと復元に必要な情報を記録します。

### <a name="database-information-for-backup-and-restoration"></a>バックアップと復元に関するデータベース情報

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
<th>データベース</th>
<th>サーバー名 (FQDN)</th>
<th>バックアップスケジュール</th>
<th>データベースバックアップツール</th>
<th>バックアップセット</th>
<th>バックアップ先</th>
<th>メモ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>バックエンドサーバー上の Rtc データベース (ユーザーデータの場合)</p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><strong>エクスポート-CsUserData</strong>コマンドレット</p></td>
<td><p>氏名</p>
<p>無期限</p>
<p>                   </p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
</tr>
<tr class="even">
<td><p>アーカイブデータベースサーバーの LcsLog (既定の名前) データベース</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>SQL Server 管理ツール</p></td>
<td><p>氏名</p>
<p>無期限</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p>通話詳細レコードのモニタリングデータベースサーバー上の LcsCdr データベース (CDRs)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>SQL Server 管理ツール</p></td>
<td><p>氏名</p>
<p>無期限</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p>Quality of Experience (QoE) データの監視データベースサーバー上の QoEMetrics データベース</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>SQL Server 管理ツール</p></td>
<td><p>氏名</p>
<p>無期限</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p>常設チャットデータベース</p></td>
<td></td>
<td></td>
<td><p>SQL Server management tool または<strong>Export-CsPersistentChatData</strong>コマンドレット</p></td>
<td><p>氏名</p>
<p>無期限</p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


次のデータベースのバックアップまたは復元は必要ありません。

  - Rtcdyn. このデータベースの一時的なユーザーデータは、サービスの復元には必要ありません。

  - Rtcab アドレス帳データベースは、Active Directory ドメインサービスのグローバルアドレス一覧 (GAL) から自動的に再作成されます。

  - Rgsdyn. このデータベースの一時的な応答グループサービスデータは、サービスの復元には必要ありません。

  - Cpsdyn. コールパークアプリケーションの動的な情報は、サービスの復元には必要ありません。

  - ・カンプ 常設チャットのコンプライアンスデータベースは、サービスの復元には必要ありません。

</div>

<div>

## <a name="file-store-backup-and-restoration-worksheet"></a>ファイルストアのバックアップと復元のワークシート

次の表を使用して、ファイルストアのバックアップと復元に必要な情報を記録します。 ファイルストアには、会議コンテンツメタデータ、会議のコンプライアンスログ、デバイス更新プログラムの更新ログ、応答グループ、コールパーク、アナウンスメントアプリケーションのオーディオファイルなどのデータが含まれています。

### <a name="file-store-information-for-backup-and-restoration"></a>バックアップと復元に関するファイルストア情報

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
<th>メモ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server ファイルストア</p></td>
<td></td>
<td></td>
<td><p>標準バックアップツール (Robocopy など)</p></td>
<td><p>Enterprise Edition のファイルサーバー。 Standard edition デプロイメントの場合は、標準エディションでは既定でオンになっています。 通常、サイトごとに1つ。</p></td>
<td></td>
<td><p>" <strong>Meeting. Active</strong> " という名前のファイルはバックアップしないでください。 これらのファイルは使用中であり、会議の実行中にロックされます。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="settings-backup-and-restoration-worksheet"></a>設定のバックアップと復元のワークシート

次の表を使用して、設定のバックアップと復元に必要な情報を記録します。

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
<th>データベース</th>
<th>サーバー名 (FQDN)</th>
<th>バックアップスケジュール</th>
<th>バックアップツール</th>
<th>構成ファイル (.xml) 名</th>
<th>バックアップの場所</th>
<th>メモ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>トポロジ構成用の中央管理ストア内の Xds データベース (グローバル)</p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><strong>エクスポート-CsConfiguration</strong>コマンドレット</p></td>
<td><p>                   </p></td>
<td><p>                    </p></td>
<td><p>                   </p></td>
</tr>
<tr class="even">
<td><p>E9 の中央管理ストアの Lis データベース (グローバル) の場所情報 (グローバル)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><strong>CsLisConfiguration</strong>コマンドレット</p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
<tr class="odd">
<td><p>応答グループ構成用のバックエンドサーバー上の RgsConfig データベース (プール)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><strong>Export-CsRgsConfiguration</strong>コマンドレット</p></td>
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

