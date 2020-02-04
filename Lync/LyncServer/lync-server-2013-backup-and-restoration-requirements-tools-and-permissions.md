---
title: 'Lync Server 2013: バックアップと復元の要件: ツールと権限'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Backup and restoration requirements: tools and permissions'
ms:assetid: 35ec2e33-f33e-4f84-9e64-6550fd78aa52
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202171(v=OCS.15)
ms:contentKeyID: 51541465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea5e4ce57e61be50bfd1e2a78529830b4a40e3ed
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730407"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-requirements-in-lync-server-2013-tools-and-permissions"></a>Lync Server 2013 でのバックアップと復元の要件: ツールと権限

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-17_

このトピックでは、Lync Server 2013 のバックアップと復元に使用できるツール、必要なアクセス許可、コマンドをリモートまたはローカルで実行できるかどうかについて説明します。 具体的には、このトピックでは、Lync Server にバックアップと復元のために提供されるツールについて説明します。

<div>

## <a name="backups"></a>バックアップ

Lync Server をバックアップするには、次の表で示されているツールを使用します。 Lync Server のバックアップに必要なすべてのコマンドをスクリプト化して、リモートで実行することができます。

### <a name="tools-for-backing-up-lync-server"></a>Lync Server のバックアップツール

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>バックアップするには、次の操作を行います。</th>
<th>このツールまたはコマンドレットを使用します。</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>トポロジ構成データ (Xds)</p></td>
<td><p>エクスポート-CsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>位置情報サービス (E9-1) データ (Lis)</p></td>
<td><p>エクスポート-CsLisConfiguration</p></td>
</tr>
<tr class="odd">
<td><p>応答グループの構成データ (RgsConfig)</p></td>
<td><p>Export-CsRgsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>常設ユーザーデータ (Rtcxds データベース)</p>
<p>会議 Id</p></td>
<td><p>Export-CsUserData</p></td>
</tr>
<tr class="odd">
<td><ul>
<li><p>アーカイブデータベース (LcsLog)</p></li>
<li><p>通話の詳細レコードデータベース (LcsCDR. mdf) を監視する</p></li>
<li><p>QoE データベース (QoEMetrics) の監視</p></li>
</ul></td>
<td><p>Sql server Management Studio などの SQL Server データベースツール</p></td>
</tr>
<tr class="even">
<td><p>常設チャットデータベース (行う)</p></td>
<td><p>SQL Server のバックアップ手順またはエクスポート-CsPersistentChatData。 エクスポート-CsPersistentChatData は、常設チャットデータをファイルとしてエクスポートします。</p></td>
</tr>
<tr class="odd">
<td><p>すべてのファイルストア: Lync Server ファイルストア、アーカイブファイルストア</p>
<div>

> [!NOTE]  
> " <STRONG>Meeting. Active</STRONG> " という名前のファイルはバックアップしないでください。 これらのファイルは、会議の実行時に使用され、ロックされます。


</div></td>
<td><p>標準ファイルシステム管理ツール (Robocopy など)。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="restoration"></a>回復

Lync Server を復元するには、次の表のツールを使用します。 Lync Server を復元するために必要なすべてのコマンドをスクリプト化することができます。 一部はリモートで実行できますが、次の表に示すようにローカルで実行する必要があります。

### <a name="tools-for-restoring-lync-server"></a>Lync Server を復元するためのツール

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>その手順は次のとおりです。</th>
<th>このツールまたはコマンドレットを使用します。</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>新しいコンピューターまたはクリーンコンピューターを作成する</p></td>
<td><ul>
<li><p>Windows オペレーティングシステムのインストールソフトウェア</p></li>
<li><p>SQL Server インストールソフトウェア</p></li>
<li><p>証明書 Microsoft 管理コンソール (MMC) スナップイン (エクスポート可能な秘密キーで証明書を復元する場合)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>ファイルストアデータを復元する</p></td>
<td><p>標準ファイルシステム管理ツール (Robocopy など)</p></td>
</tr>
<tr class="odd">
<td><p>空のデータベースを再作成し、次の権限を設定します。</p>
<ul>
<li><p>中央管理ストア</p></li>
<li><p>バック エンド サーバー</p></li>
<li><p>監視データベース</p></li>
<li><p>アーカイブ データベース</p></li>
</ul></td>
<td><p>Install-CsDatabase</p></td>
</tr>
<tr class="even">
<td><p>Active Directory ドメインサービスのポインターを中央管理ストアに復元します。</p>
<div>

> [!NOTE]  
> サービス接続ポイントをいつでも紛失した場合は、このコマンドレットを再実行できます。


</div></td>
<td><p>Set-CsConfigurationStoreLocation</p></td>
</tr>
<tr class="odd">
<td><p>トポロジ、ポリシー、構成の設定を中央管理ストア (Xds) にインポートする</p></td>
<td><p>インポート-CsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>トポロジを公開して有効にする</p></td>
<td><p>トポロジ ビルダー</p>
<p>/</p>
<p>公開-CsTopology と有効化-CsTopology 機能</p></td>
</tr>
<tr class="odd">
<td><p>最後に公開されたトポロジを有効にする</p></td>
<td><p>有効にする-CsTopology テクノロジー</p></td>
</tr>
<tr class="even">
<td><p>Lync Server コンポーネントを再インストールする</p></td>
<td><p>Lync Server のセットアップ</p>
<div>

> [!NOTE]  
> Lync Server のインストールフォルダーまたは¥の場合は、「¥の場合」をご覧ください。


</div></td>
</tr>
<tr class="odd">
<td><p>位置情報 (E9-1) データ (Lis) を復元する</p></td>
<td><p>Import-CsLisConfiguration</p></td>
</tr>
<tr class="even">
<td><p>永続的なユーザーデータ (Rtcxds) を復元する</p></td>
<td><p>インポート-CsUserData</p></td>
</tr>
<tr class="odd">
<td><p>応答グループの構成データ (RgsConfig) を復元する</p></td>
<td><p>Import-CsRgsConfiguration</p>
<div>

> [!NOTE]  
> データベースに応答グループデータがない、新しく展開されたプールで構成を復元する場合は、– OverwriteOwner オプションを使用する必要があります。 復元されるデータが、同じ完全修飾ドメイン名 (FQDN) を持つプールにある場合でも、このオプションを使用します。 そうしないと、アクティブディレクトリに既に存在する返信グループに連絡先オブジェクトが存在するため、インポートは成功しません。


</div></td>
</tr>
<tr class="even">
<td><p>次のデータベースを復元します。</p>
<ul>
<li><p>アーカイブデータベース (LcsLog)</p></li>
<li><p>監視データベース: call detail レコードデータベース (LcsCDR mdf) と QoE データベース (QoEMetrics)</p></li>
</ul></td>
<td><p>SQL Server データベース管理ツール</p></td>
</tr>
<tr class="odd">
<td><p>常設チャットデータベース (Mgs)</p></td>
<td><p>SQL Server の復元手順またはインポート-CsPersistentChatData。 CsPersistentChatData で作成されたファイルと共に CsPersistentChatData を使用すると、データは永続的なチャットデータベースにインポートされます。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="required-permissions"></a>必要なアクセス許可

このトピックで説明されているすべてのコマンドを実行するには、ユーザーが**RTCUniversalServerAdmins** group のメンバーである必要があります。 ほとんどのバックアップと復元コマンドは、役割ベースのアクセス制御 (RBAC) をサポートしていません。 2つの例外は、常設チャットコマンドレットのエクスポート-CsPersistentChatData と CsPersistentChatData を使用することです。これは、CsPersistentChatAdministrator グループのメンバーであるユーザーが実行する必要があります。 Lync Server 展開ウィザードを実行するには、ユーザーはローカルの [電話番号] グループのメンバーでもある必要があります。

</div>

</div>

<span> </span>

</div>

</div>

</div>

