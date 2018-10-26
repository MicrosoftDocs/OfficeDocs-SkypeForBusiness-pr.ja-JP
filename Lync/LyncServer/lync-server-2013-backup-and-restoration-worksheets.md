---
title: バックアップと復元のワークシート
TOCTitle: バックアップと復元のワークシート
ms:assetid: 26c78155-0306-41ac-845b-7ad58000a1d6
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Hh202169(v=OCS.15)
ms:contentKeyID: 52056561
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# バックアップと復元のワークシート

 

_**トピックの最終更新日:** 2015-03-09_

組織のバックアップおよび復元計画には、データと設定をバックアップする方法とタイミングに関する詳細を含める必要があります。ここで提供されているワークシートを使用して、特定の展開および組織のバックアップおよび復元の要件に関するこの情報を文書化できます。

次のワークシートを使用して、データベース、ファイル ストア、および Lync Server プールまたは Standard Edition サーバーの設定情報をバックアップおよび復元するために必要な情報を記録してください。これらのワークシートのコピーを安全な場所に保管し、Lync Server を復元する必要がある場合にすぐに入手できるようにしてください。

> [!NOTE]
> このセクションのワークシートは、Lync Server のデータベースおよびサーバーのデータと設定を復元するために必要な情報だけが対象です。オペレーティング システムおよび他のソフトウェアの再インストールに関する情報など、他の復元情報を文書化する必要がある場合は、組織の展開計画およびバックアップと復元の計画を使用して、要件に対応してください。


## データベースのバックアップと復元のワークシート

次の表を使用して、Lync Server データベースをバックアップおよび復元するために必要な情報を記録します。

### バックアップおよび復元のためのデータベース情報

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
<th>バックアップ スケジュール</th>
<th>データベース バックアップ ツール</th>
<th>バックアップ セット</th>
<th>バックアップ先</th>
<th>メモ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>バックエンド サーバー上のユーザー データ用の Rtc データベース</p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><strong>Export-CsUserData</strong> コマンドレット</p></td>
<td><p>名前 :</p>
<p>有効期限:</p>
<p>                   </p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
</tr>
<tr class="even">
<td><p>アーカイブ データベース サーバー上の LcsLog (既定名) データベース</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>SQL Server 管理ツール</p></td>
<td><p>名前 :</p>
<p>有効期限:</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p>監視データベース サーバー上の通話詳細記録 (CDR) 用の LcsCdr データベース</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>SQL Server 管理ツール</p></td>
<td><p>名前 :</p>
<p>有効期限:</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p>監視データベース サーバー上の QoE (Quality of Experience) データ用の QoEMetrics データベース</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>SQL Server 管理ツール</p></td>
<td><p>名前 :</p>
<p>有効期限:</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p>常設チャット データベース</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>SQL Server 管理ツールまたは <strong>Export-CsPersistentChatData</strong> コマンドレット</p></td>
<td><p>名前:</p>
<p>有効期限:</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


次のデータベースのバックアップまたは復元は必要ありません。

  - Rtcdyn。このデータベースの一時的なユーザー データは、サービスの復元に必要ありません。

  - Rtcab。アドレス帳データベースは、Active Directory ドメイン サービス のグローバル アドレス一覧 (GAL) から自動的に再作成されます。

  - Rgsdyn。このデータベースの一時的な応答グループ サービス データは、サービスの復元に必要ありません。

  - Cpsdyn。コール パーク アプリケーションの動的な情報は、サービスの復元に必要ありません。

  - MgcComp。常設チャットのコンプライアンス データベースは、サービスの復元に必要ありません。

## ファイル ストアのバックアップと復元のワークシート

次の表を使用して、ファイル ストアをバックアップおよび復元するために必要な情報を記録します。ファイル ストアには、会議コンテンツ メタデータ、会議コンプライアンス ログ、デバイス更新プログラムの更新ログのほかに、応答グループ、コール パーク、アナウンス アプリケーションのオーディオ ファイルなど、各種データが格納されます。

### バックアップおよび復元のためのファイル ストア情報

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
<th>バックアップ スケジュール</th>
<th>ファイル システム バックアップ ツール</th>
<th>バックアップ対象のファイル共有 *</th>
<th>バックアップ先</th>
<th>メモ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server ファイル ストア</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>標準バックアップ ツール (Robocopy など)</p></td>
<td><p>Enterprise Edition の場合はファイル サーバー上。Standard Edition の展開の場合は、既定では Standard Edition 上。通常はサイトごとに 1 つ。</p></td>
<td><p></p></td>
<td><p><strong>Meeting.Active</strong> という名前のファイルはバックアップしないでください。これらのファイルは、会議の開催中に使用されており、ロックされています。</p></td>
</tr>
</tbody>
</table>


## 設定のバックアップと復元のワークシート

次の表を使用して、設定をバックアップおよび復元するために必要な情報を記録します。

### バックアップおよび復元のための設定情報

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
<th>バックアップ スケジュール</th>
<th>バックアップ ツール</th>
<th>構成ファイル (.xml) 名</th>
<th>バックアップ場所</th>
<th>メモ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>トポロジ構成用の中央管理ストア内の Xds データベース (グローバル)</p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><strong>Export-CsConfiguration</strong> コマンドレット</p></td>
<td><p>                   </p></td>
<td><p>                    </p></td>
<td><p>                   </p></td>
</tr>
<tr class="even">
<td><p>E9-1-1 場所情報用の中央管理ストア内の Lis データベース (グローバル)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><strong>Export-CsLisConfiguration</strong> コマンドレット</p></td>
<td><p></p></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
<tr class="odd">
<td><p>応答グループ構成用のバックエンド サーバー上の RgsConfig データベース (プール)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><strong>Export-CsRgsConfiguration</strong> コマンドレット</p></td>
<td><p></p></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
</tbody>
</table>

