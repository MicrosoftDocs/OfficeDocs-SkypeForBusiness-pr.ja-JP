---
title: 'Lync Server 2013: 常設チャットサーバーの展開チェックリスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for Persistent Chat Server
ms:assetid: b1108f8f-88a2-4660-8086-d25ba76f7239
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412851(v=OCS.15)
ms:contentKeyID: 48185155
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2399d6ce6fc17a802c8f6bc39730370948ef0253
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522744"
---
# <a name="deployment-checklist-for-persistent-chat-server-in-lync-server-2013"></a>Lync Server 2013 の常設チャットサーバーの展開チェックリスト

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-16_

Lync Server 2013 を展開する場合は、常設チャットサーバーを正しい順序で展開し、必要なすべての展開手順を完了する必要があります。

<div>

## <a name="deployment-sequence"></a>展開順序

最初のトポロジの展開後に常設チャットサーバーを展開できます。これには、少なくとも1つの Lync Server 2013、フロントエンドプール、または1つの Lync Server 2013、Standard Edition サーバーが含まれます。 このトピックでは、既存の展開に追加することによって常設チャットサーバーを展開する方法について説明します。

</div>

<div>

## <a name="deployment-process"></a>展開プロセス

次の表に、常設チャットサーバーを展開するための基本的な手順と、詳細情報へのリンクを示します。

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
<th>手順</th>
<th>必要な役割およびグループ メンバーシップ</th>
<th>関連トピック</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>必要なハードウェアとソフトウェアのインストール</strong></p></td>
<td><p>システム要件を満たすハードウェアに、次のものをインストールします。</p>
<ul>
<li><p>常設チャットサーバーのフロントエンドサーバーで、次のようにします。</p></li>
</ul>
<ul>
<li><p>システム要件を満たすオペレーティング システム</p></li>
<li><p>Lync Server 2013 を実行しているコンピューターのソフトウェア前提条件</p></li>
<li><p>常設チャットサーバーデータベースをホストするサーバー上の SQL Server</p></li>
</ul>
<p>常設チャットサーバーのコンプライアンスが必要な場合:</p>
<ul>
<li><p>常設チャットサーバーコンプライアンスデータベースをホストするサーバー上の SQL Server</p></li>
</ul></td>
<td><p>ローカルの Administrators グループのメンバーであるユーザー。</p></td>
<td><p>「サポート」のドキュメントの「 <a href="lync-server-2013-supported-hardware.md">Lync Server 2013 でサポートされるハードウェア</a>」</p>
<p>「サポート」のドキュメントの「 <a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync server 2013 でのサーバーソフトウェアとインフラストラクチャのサポート」</a></p>
<p><a href="lync-server-2013-determining-your-system-requirements.md">Lync Server 2013 のシステム要件を決定する</a></p>
<p><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Lync Server 2013 の常設チャットサーバーの技術要件</a></p></td>
</tr>
<tr class="even">
<td><p><strong>常設チャットサーバーをサポートするための適切な内部トポロジの作成 (およびオプションで常設チャットコンプライアンス)</strong></p></td>
<td><p>トポロジビルダーを実行して、常設チャットサーバープールをトポロジに追加します。</p>
<ul>
<li><p>常設チャットサーバーコンポーネントをトポロジに追加する</p></li>
<li><p>常設チャットサーバーストア (および障害復旧用のバックアップ SQL Server) 用の SQL Server データベースを作成します。</p></li>
<li><p>新しい Lync ファイルストアを定義するか、既存の Lync ファイルストアを使用して常設チャットサーバーファイルを作成する</p></li>
<li><p>この常設チャットサーバープールに要求をルーティングできる Lync Server 2013 プールを関連付けます。</p></li>
</ul>
<p>常設チャットのコンプライアンスが必要な場合:</p>
<ul>
<li><p>常設チャットコンプライアンスストアの追加</p></li>
<li><p>[常設チャットサーバープールの定義] チェックボックスをオンにして、コンプライアンスを有効にします。</p></li>
<li><p>トポロジを公開する。</p></li>
</ul>
<p>Standard Edition に常設チャットサーバーをインストールする場合は、常設チャットサーバープールの完全修飾ドメイン名 (FQDN) が Standard Edition サーバーと一致している必要があります。また、SQL Server データベースは、Standard Edition サーバー上の SQL Server Express インスタンスに併置されます。</p></td>
<td><p>トポロジを定義するには、ローカルの Users グループのメンバーであるアカウント。</p>
<p>トポロジを公開するには、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーであり、ユーザーは、常設チャットサーバーファイル用の Lync ファイルストアに対するフルコントロールのアクセス許可 (読み取り/書き込み/変更) を所有している必要があります (これにより、トポロジビルダーは必要な Dacl を構成できます)。</p></td>
<td><p>展開のドキュメントの「 <a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync server 2013 での展開への常設チャットサーバーの追加」</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>常設チャット サーバーの展開</strong></p></td>
<td><p>常設チャットサーバーを実行しているすべてのコンピューターで Lync Server セットアップを実行します。 常設チャットサーバーのセットアップは、Lync Server 2013 展開ウィザードに統合され、次の手順を提供します。</p>
<ul>
<li><p>ローカル管理ストアを展開する。</p></li>
<li><p>常設チャットサーバーサービスのインストール</p></li>
<li><p>証明書を要求および割り当てる。</p></li>
<li><p>サービスを実行および開始する。</p></li>
</ul></td>
<td><p>ローカルの Administrators グループのメンバーであるユーザー。</p></td>
<td><p>展開のドキュメントの「 <a href="lync-server-2013-deploying-persistent-chat-server.md">Lync server 2013 での常設チャットサーバーの展開</a>」</p></td>
</tr>
<tr class="even">
<td><p><strong>常設チャット管理者の作成</strong></p></td>
<td><p>ユーザーを CsPersistentChatAdministrator セキュリティ グループに追加します。</p></td>
<td><p>ドメイン管理者のメンバーであるユーザー。</p></td>
<td><p>「展開」のドキュメントの「 <a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Lync Server 2013 での常設チャット管理者の追加」</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>常設チャット サーバーの構成</strong></p></td>
<td><p>次のようにユーザーを構成します。</p>
<ul>
<li><p>常設チャットサーバーにアクセスするには、ポリシーによってユーザーを有効にする必要があります。 既定では、ポリシーはすべてのユーザーに対してオフになっており、グローバル/サイト/プール/ユーザー スコープで定義できます。</p></li>
<li><p>設定の構成</p></li>
</ul></td>
<td><p>ユーザーは CsPersistentChatAdministrator のメンバーである必要がある。ポリシーを変更するには、ユーザーは最低でも CsUserAdministrator である必要がある。</p></td>
<td><p>「展開」のドキュメントの「 <a href="lync-server-2013-configuring-persistent-chat-server.md">Lync server 2013 での常設チャットサーバーの構成</a>」</p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> 1つまたは複数の常設チャットサーバープールを展開できます。 複数の常設チャットサーバープールをサポートしています。規制上の理由から、特定の地域で生成されたデータはその地域にとどまる必要があります。 たとえば、永続的なチャットサーバープールをシカゴに展開し、Zurich フルタの別のユーザーがスイスのデータに対する規則に準拠している場合、ユーザーは、アクセス権を持っている限り、両方の常設チャットサーバープールのルームに接続できます。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

