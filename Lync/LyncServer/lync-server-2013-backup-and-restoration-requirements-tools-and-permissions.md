---
title: 'Lync Server 2013: バックアップと復元の要件: ツールとアクセス許可'
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
ms.openlocfilehash: b273674d1f2ad20a0379c65e35e85ae0300df3dc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135734"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-requirements-in-lync-server-2013-tools-and-permissions"></a>Lync Server 2013 のバックアップと復元の要件: ツールとアクセス許可

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-17_

このトピックでは、Lync Server 2013 のバックアップおよび復元に使用できるツール、必要なアクセス許可、およびリモートまたはローカルでコマンドを実行できるかどうかを示します。 具体的には、このトピックでは、バックアップと復元のために Lync Server に用意されているツールを中心に説明します。

<div>

## <a name="backups"></a>バックアップ

Lync Server をバックアップするには、次の表に示されているツールを使用します。 Lync Server をバックアップするために必要なすべてのコマンドをスクリプト化して、リモートで実行することができます。

### <a name="tools-for-backing-up-lync-server"></a>Lync Server をバックアップするためのツール

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
<td><p>エクスポート-CsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>Location Information Service (E9-1-1) データ (Lis.mdf)</p></td>
<td><p>Export-cslisconfiguration</p></td>
</tr>
<tr class="odd">
<td><p>応答グループ構成データ (RgsConfig.mdf)</p></td>
<td><p>Export-CsRgsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>永続的なユーザーデータ (Rtcxds. .mdf データベース)</p>
<p>会議 ID</p></td>
<td><p>エクスポート-CsUserData</p></td>
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
<td><p>常設チャットデータベース (Mgc)</p></td>
<td><p>SQL Server のバックアップ手順または Export-cspersistentchatdata。 Export-cspersistentchatdata は、常設チャットデータをファイルとしてエクスポートします。</p></td>
</tr>
<tr class="odd">
<td><p>すべてのファイルストア: Lync Server ファイルストア、アーカイブファイルストア</p>
<div>

> [!NOTE]  
> <STRONG>Meeting.Active</STRONG> という名前のファイルはバックアップしないでください。 これらのファイルは、会議の開催中に使用されており、ロックされています。


</div></td>
<td><p>標準のファイルシステム管理ツール (Robocopy など)。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="restoration"></a>復元

Lync Server を復元するには、次の表のツールを使用します。 Lync Server を復元するために必要なすべてのコマンドをスクリプト化できます。 一部はリモートで実行できますが、次の表で指定されているように、ローカルで実行する必要があります。

### <a name="tools-for-restoring-lync-server"></a>Lync Server を復元するためのツール

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
<td><p>-CsDatabase をインストールする</p></td>
</tr>
<tr class="even">
<td><p>Active Directory ドメインサービスのポインターを中央管理ストアに復元する</p>
<div>

> [!NOTE]  
> サービス接続ポイントを失った場合は、このコマンドレットをいつでも再実行できます。


</div></td>
<td><p>Remove-csconfigurationstorelocation</p></td>
</tr>
<tr class="odd">
<td><p>トポロジ、ポリシー、および構成設定を中央管理ストア (Xds) にインポートします。</p></td>
<td><p>インポート-CsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>トポロジを公開して有効にする</p></td>
<td><p>トポロジ ビルダー</p>
<p>または</p>
<p>発行-CsTopology た機能と Enable-CsTopology たテクノロジー</p></td>
</tr>
<tr class="odd">
<td><p>最後に公開したトポロジを有効にする</p></td>
<td><p>Enable-CsTopology</p></td>
</tr>
<tr class="even">
<td><p>Lync Server コンポーネントを再インストールする</p></td>
<td><p>Lync Server のセットアップ</p>
<div>

> [!NOTE]  
> Lync Server のインストールフォルダーまたは¥にあるメディアにあります。


</div></td>
</tr>
<tr class="odd">
<td><p>位置情報 (E9-1-1) データ (Lis.mdf) を復元する</p></td>
<td><p>Export-cslisconfiguration</p></td>
</tr>
<tr class="even">
<td><p>永続的なユーザーデータ (Rtcxds) を復元する</p></td>
<td><p>インポート-CsUserData</p></td>
</tr>
<tr class="odd">
<td><p>応答グループ構成データ (RgsConfig.mdf) を復元する</p></td>
<td><p>Import-CsRgsConfiguration</p>
<div>

> [!NOTE]  
> データベースに応答グループデータがない状態で、新たに展開されたプールで構成を復元する場合は、– OverwriteOwner オプションを使用する必要があります。 復元されるデータが同じ完全修飾ドメイン名 (FQDN) を持つプールにある場合でも、このオプションを使用します。 それ以外の場合は、Active Directory 内に既に存在している応答グループに連絡先オブジェクトがあるため、インポートに失敗します。


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
<td><p>常設チャットデータベース (Mgs)</p></td>
<td><p>SQL Server の復元手順または Export-cspersistentchatdata。 Export-cspersistentchatdata を使用して、Export-cspersistentchatdata で作成されたファイルを使用して、データを常設チャットデータベースにインポートすることができます。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="required-permissions"></a>必要なアクセス許可

このトピックで説明されているすべてのコマンドを実行するには、ユーザーは**RTCUniversalServerAdmins**グループのメンバーである必要があります。 ほとんどのバックアップおよび復元コマンドは、役割ベースのアクセス制御 (RBAC) をサポートしていません。 2つの例外として、常設チャットのコマンドレット Export-cspersistentchatdata および Export-cspersistentchatdata があります。これは、CsPersistentChatAdministrator グループのメンバーであるユーザーが実行する必要があります。 Lync Server 展開ウィザードを実行するには、ユーザーがローカルの administrators グループのメンバーでもある必要があります。

</div>

</div>

<span> </span>

</div>

</div>

</div>

