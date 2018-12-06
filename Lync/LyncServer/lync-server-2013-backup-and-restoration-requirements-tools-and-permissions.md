---
title: 'バックアップと復元の要件: ツールとアクセス許可'
TOCTitle: 'バックアップと復元の要件: ツールとアクセス許可'
ms:assetid: 35ec2e33-f33e-4f84-9e64-6550fd78aa52
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Hh202171(v=OCS.15)
ms:contentKeyID: 52056568
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# バックアップと復元の要件: ツールとアクセス許可

 

_**トピックの最終更新日:** 2015-03-09_

このトピックでは、Lync Server 2013 のバックアップおよび復元に使用できるツール、必要なアクセス許可、およびリモートまたはローカルで実行できるコマンドについて説明します。特に、このトピックでは、Lync Server に用意されているバックアップ ツールおよび復元ツールに焦点を絞ります。

## バックアップ

Lync Server をバックアップするには、次の表に示すツールを使用します。Lync Server のバックアップに必要なコマンドはすべてスクリプトで使用できます。また、これらのコマンドは、リモートで実行できます。

### Lync Server のバックアップ ツール

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>バックアップ対象:</th>
<th>使用するツールまたはコマンドレット:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>トポロジ構成データ (Xds.mdf)</p></td>
<td><p>Export-CsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>Location Information Service (E9-1-1) データ (Lis.mdf)</p></td>
<td><p>Export-CsLisConfiguration</p></td>
</tr>
<tr class="odd">
<td><p>応答グループ構成データ (RgsConfig.mdf)</p></td>
<td><p>Export-CsRgsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>永続ユーザー データ (Rtcxds.mdf データベース)</p>
<p>会議 ID</p></td>
<td><p>Export-CsUserData</p></td>
</tr>
<tr class="odd">
<td><ul>
<li><p>アーカイブ データベース (LcsLog.mdf)</p></li>
<li><p>監視通話詳細記録データベース (LcsCDR.mdf)</p></li>
<li><p>監視 QoE データベース (QoEMetrics.mdf)</p></li>
</ul></td>
<td><p>SQL Server Management Studio などの SQL Server データベース ツール</p></td>
</tr>
<tr class="even">
<td><p>常設チャット データベース (Mgc.mdf)</p></td>
<td><p>SQL Server バックアップ手順または Export-CsPersistentChatData。Export-CsPersistentChatData によって、常設チャットがファイルとしてエクスポートされます。</p></td>
</tr>
<tr class="odd">
<td><p>すべてのファイル ストア: Lync Server ファイル ストア、アーカイブ ファイル ストア</p>

> [!NOTE]
> <strong>Meeting.Active</strong> という名前のファイルはバックアップしないでください。これらのファイルは、会議の開催中に使用されており、ロックされています。

</div></td>
<td><p>標準のファイル システム管理ツール (Robocopy など)</p></td>
</tr>
</tbody>
</table>


## 復元

Lync Server を復元するには、次の表に示すツールを使用します。Lync Server の復元に必要なコマンドはすべてスクリプトで使用できます。一部のコマンドについてはリモートで実行できますが、次の表に示すように、ローカルで実行しなければならないものもあります。

### Lync Server の復元ツール

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>操作内容:</th>
<th>使用するツールまたはコマンドレット:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>新規またはクリーン コンピューターを構築する</p></td>
<td><ul>
<li><p>Windows オペレーティング システム インストール ソフトウェア</p></li>
<li><p>SQL Server インストール ソフトウェア</p></li>
<li><p>証明書とエクスポート可能な秘密キーを復元する場合は、Microsoft 管理コンソール (MMC) の証明書スナップイン</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>ファイル ストア データを復元する</p></td>
<td><p>標準のファイル システム管理ツール (Robocopy など)</p></td>
</tr>
<tr class="odd">
<td><p>空のデータベースを再作成し、次のアクセス許可を設定する</p>
<ul>
<li><p>中央管理ストア</p></li>
<li><p>バック エンド サーバー</p></li>
<li><p>監視データベース</p></li>
<li><p>アーカイブ データベース</p></li>
</ul></td>
<td><p>Install-CsDatabase</p></td>
</tr>
<tr class="even">
<td><p>Active Directory ドメイン サービス ポインターを中央管理ストアに復元する</p>

> [!NOTE]
> サービス接続ポイントを失った場合は、このコマンドレットをいつでも再実行できます。

</div></td>
<td><p>Set-CsConfigurationStoreLocation</p></td>
</tr>
<tr class="odd">
<td><p>トポロジ、ポリシー、および構成設定を中央管理ストアにインポートします (Xds.mdf)。</p></td>
<td><p>Import-CsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>トポロジを公開して有効にする</p></td>
<td><p>トポロジ ビルダー</p>
<p>- または -</p>
<p>Publish-CsTopology および Enable-CsTopology</p></td>
</tr>
<tr class="odd">
<td><p>最後に公開したトポロジを有効にする</p></td>
<td><p>Enable-CsTopology</p></td>
</tr>
<tr class="even">
<td><p>Lync Server コンポーネントを再インストールする</p></td>
<td><p>Lync Server セットアップ</p>

> [!NOTE]
> Lync Server インストール フォルダーまたは \setup\amd64\Setup.exe のインストール メディアにあります。

</div></td>
</tr>
<tr class="odd">
<td><p>位置情報 (E9-1-1) データ (Lis.mdf) を復元する</p></td>
<td><p>Import-CsLisConfiguration</p></td>
</tr>
<tr class="even">
<td><p>永続ユーザー データ (Rtcxds.mdf) を復元する</p></td>
<td><p>Import-CsUserData</p></td>
</tr>
<tr class="odd">
<td><p>応答グループ構成データ (RgsConfig.mdf) を復元する</p></td>
<td><p>Set-CsRgsConfiguration</p>

> [!NOTE]
> 応答グループのデータがデータベースに含まれない、新しく展開されたプールに構成が復元される場合は、-OverwriteOwner オプションを使用することをお勧めします。このオプションは、データが、完全修飾ドメイン名 (FQDN) を持つプールに復元される場合にも使用してください。応答グループの連絡先オブジェクトは既に Active Directory に存在するので、このオプションを使用しないと、インポートは正常に行われません。

</div></td>
</tr>
<tr class="even">
<td><p>次のデータベースを復元する</p>
<ul>
<li><p>アーカイブ データベース (LcsLog.mdf)</p></li>
<li><p>監視データベース: 通話詳細記録データベース (LcsCDR.mdf) と QoE データベース (QoEMetrics.mdf)</p></li>
</ul></td>
<td><p>SQL Server データベース管理ツール</p></td>
</tr>
<tr class="odd">
<td><p>常設チャット データベース (Mgs.mdf)</p></td>
<td><p>SQL Server 復元手順または Import-CsPersistentChatData。Import-CsPersistentChatData を、Export-CsPersistentChatData で作成されたファイルで使用すると、データは常設チャット データベースにインポートされます。</p></td>
</tr>
</tbody>
</table>


## 必要なアクセス許可

このトピックに記載されているコマンドを実行するには、**RTCUniversalServerAdmins** グループのメンバーである必要があります。バックアップおよび復元コマンドのほとんどが、ロール ベースのアクセス制御 (RBAC) をサポートしていません。ただし、常設チャット コマンドレットである Export-CsPersistentChatData と Import-CsPersistentChatData の 2 つは除きます。このコマンドレットは両方とも、CsPersistentChatAdministrator グループのメンバーが実行する必要があります。また、Lync Server 展開ウィザードを実行するには、Local Adminstrators グループのメンバーである必要もあります。

