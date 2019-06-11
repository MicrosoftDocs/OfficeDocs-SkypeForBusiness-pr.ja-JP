---
title: 'Lync Server 2013: 常設チャット サーバーの展開チェックリスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for Persistent Chat Server
ms:assetid: b1108f8f-88a2-4660-8086-d25ba76f7239
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412851(v=OCS.15)
ms:contentKeyID: 48185155
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e539a1aa6883863228aaab19ddaa38300ae45591
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833506"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-persistent-chat-server-in-lync-server-2013"></a>Lync Server 2013 の常設チャット サーバーの展開チェックリスト

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-16_

Lync Server 2013、常設チャットサーバーを展開するには、正しい順序で展開し、必要なすべての展開手順を完了する必要があります。

<div>

## <a name="deployment-sequence"></a>展開シーケンス

少なくとも1つの Lync Server 2013、フロントエンドプール、または1つの Lync Server 2013、Standard Edition server を含む、最初のトポロジを展開した後、常設チャットサーバーを展開することができます。 このトピックでは、既存の展開に追加して、常設チャットサーバーを展開する方法について説明します。

</div>

<div>

## <a name="deployment-process"></a>展開プロセス

次の表は、常設チャットサーバーを展開するための基本的な手順と、詳細情報のリンクを示しています。

### <a name="persistent-chat-server-deployment-process"></a>常設チャットサーバーの展開プロセス

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>タスク</th>
<th>ステップ</th>
<th>必要な役割とグループ メンバーシップ</th>
<th>関連トピック</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>必要なハードウェアとソフトウェアのインストール</strong></p></td>
<td><p>システム要件を満たすハードウェアに、次をインストールします。</p>
<ul>
<li><p>常設チャットサーバーのフロントエンドサーバーで、次の操作を行います。</p></li>
</ul>
<ul>
<li><p>システム要件を満たすオペレーティング システム</p></li>
<li><p>Lync Server 2013 を実行しているコンピューターのソフトウェアの前提条件</p></li>
<li><p>常設チャットサーバーデータベースをホストするサーバー上の SQL Server</p></li>
</ul>
<p>常設チャットサーバーのコンプライアンスが必要な場合:</p>
<ul>
<li><p>常設チャットサーバーのコンプライアンスデータベースをホストするサーバー上の SQL Server</p></li>
</ul></td>
<td><p>ローカルの Administrators グループのメンバーであるユーザー。</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">サポートされているドキュメントの Lync Server 2013 でサポートされているハードウェア</a></p>
<p>サポートドキュメントの<a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync server 2013 でのサーバーソフトウェアとインフラストラクチャのサポート</a></p>
<p><a href="lync-server-2013-determining-your-system-requirements.md">Lync Server 2013 システム要件の決定</a></p>
<p><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Lync Server 2013 の常設チャットサーバーの技術要件</a></p></td>
</tr>
<tr class="even">
<td><p><strong>常設チャットサーバーをサポートするための適切な内部トポロジを作成します (また、必要に応じて常設チャットのコンプライアンスも可能)。</strong></p></td>
<td><p>トポロジビルダーを実行して、常設チャットサーバープールをトポロジに追加します。</p>
<ul>
<li><p>常設チャットサーバーコンポーネントをトポロジに追加する</p></li>
<li><p>常設チャットサーバーストア用の SQL Server データベースを作成します (および障害回復用のバックアップ SQL Server)。</p></li>
<li><p>新しい Lync ファイルストアを定義するか、既存の Lync ファイルストアで常設チャットサーバーファイルを使用する</p></li>
<li><p>要求をこの常設チャットサーバープールにルーティングできる Lync Server 2013 プールを関連付ける</p></li>
</ul>
<p>常設チャット コンプライアンスが必要な場合</p>
<ul>
<li><p>常設チャットのコンプライアンスストアを追加する</p></li>
<li><p>コンプライアンスを有効にするには、[常設チャットサーバープールの定義] チェックボックスをオンにします。</p></li>
<li><p>トポロジを公開する</p></li>
</ul>
<p>標準エディションに常設チャットサーバーをインストールする場合は、常設チャットサーバープールの完全修飾ドメイン名 (FQDN) が standard Edition サーバーと一致する必要があります。 SQL Server データベースは、標準の SQL Server Express インスタンスに併置されています。エディションサーバー</p></td>
<td><p>トポロジを定義するには、ローカルの Users グループのメンバーであるアカウント。</p>
<p>トポロジを公開するには、ドメイン管理者グループと RTCUniversalServerAdmins グループのメンバーであるアカウントであり、ユーザーは、常設チャットサーバーファイル用の Lync ファイルストアでもフルコントロールのアクセス許可 (読み取り/書き込み/変更) を付与する必要があります (そのため、トポロジビルダーは、必要な Dacl を構成できます。</p></td>
<td><p>展開ドキュメントの<a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync server 2013 での展開への常設チャットサーバーの追加</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>常設チャット サーバーの展開</strong></p></td>
<td><p>常設チャットサーバーを実行しているすべてのコンピューターで Lync Server のセットアップを実行します。 常設チャットサーバーのセットアップは Lync Server 2013 展開ウィザードに統合されているため、次の手順で行うことができます。</p>
<ul>
<li><p>ローカル管理ストアを展開する。</p></li>
<li><p>常設チャットサーバーサービスをインストールする</p></li>
<li><p>証明書を要求および割り当てる。</p></li>
<li><p>サービスを実行および開始する。</p></li>
</ul></td>
<td><p>ローカルの Administrators グループのメンバーであるユーザー。</p></td>
<td><p>展開ドキュメントの<a href="lync-server-2013-deploying-persistent-chat-server.md">Lync server 2013 での常設チャットサーバーの展開</a></p></td>
</tr>
<tr class="even">
<td><p><strong>常設チャット管理者の作成</strong></p></td>
<td><p>ユーザーを CsPersistentChatAdministrator セキュリティ グループに追加します。</p></td>
<td><p>ドメイン管理者のメンバーであるユーザー。</p></td>
<td><p>展開ドキュメントの<a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Lync Server 2013 での常設チャット管理者の追加</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>常設チャット サーバーの構成</strong></p></td>
<td><p>次のようにユーザーを構成します。</p>
<ul>
<li><p>ユーザは、常設チャットサーバにアクセスするためにポリシーによって有効になっている必要があります。 既定では、ポリシーはすべてのユーザーに対してオフになっており、グローバル/サイト/プール/ユーザー スコープで定義できます。</p></li>
<li><p>設定の構成</p></li>
</ul></td>
<td><p>ユーザーは CsPersistentChatAdministrator のメンバーであることが必要です。ポリシーを変更するには、ユーザーは最低でも CsUserAdministrator であることが必要です。</p></td>
<td><p>展開ドキュメントの<a href="lync-server-2013-configuring-persistent-chat-server.md">Lync server 2013 での常設チャットサーバーの構成</a></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> 1つ以上の常設チャットサーバープールを展開できます。 複数の常設チャットサーバープールをサポートしており、特定の地域で生成されたデータをその地域内に維持する必要があります。 たとえば、Zurich で常設チャットサーバープールを展開し、スイスのデータに関する規制に準拠するために、ユーザーは、アクセス権を持っている常設チャットサーバープールの会議室に接続できます。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

