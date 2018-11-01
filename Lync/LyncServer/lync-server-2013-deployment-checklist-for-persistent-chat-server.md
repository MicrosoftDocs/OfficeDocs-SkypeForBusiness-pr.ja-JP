---
title: 'Lync Server 2013: 常設チャット サーバーの展開チェックリスト'
TOCTitle: 常設チャット サーバーの展開チェックリスト
ms:assetid: b1108f8f-88a2-4660-8086-d25ba76f7239
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412851(v=OCS.15)
ms:contentKeyID: 48273296
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の常設チャット サーバーの展開チェックリスト

 

_**トピックの最終更新日:** 2015-03-09_

Lync Server 2013 の展開では、 常設チャット サーバー を正しい順序で展開し、必要な展開ステップをすべて完了する必要があります。

## 展開順序

常設チャット サーバーは、少なくとも 1 つの Lync Server 2013、 フロント エンド プール、または 1 つの Lync Server 2013、 Standard Edition サーバーを含む最初のトポロジを展開した後に展開できます。このトピックでは、既存の展開に追加することによって 常設チャット サーバーを展開する方法を説明します。

## 展開プロセス

次の表に、 常設チャット サーバーを展開する基本的なステップと、詳細情報へのリンクを示します。

### 常設チャット サーバーの展開プロセス

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
<th>必要な役割およびグループ メンバーシップ</th>
<th>関連トピック</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>必要なハードウェアとソフトウェアのインストール</strong></p></td>
<td><p>システム要件を満たすハードウェアに、次のものをインストールします。</p>
<ul>
<li><p>常設チャット サーバーフロント エンド サーバー上:</p></li>
</ul>
<ul>
<li><p>システム要件を満たすオペレーティング システム</p></li>
<li><p>Lync Server 2013 を実行するコンピューターのソフトウェア要件</p></li>
<li><p>常設チャット サーバー データベースをホストするサーバー上の SQL Server</p></li>
</ul>
<p>常設チャット サーバー Compliance が必要な場合</p>
<ul>
<li><p>常設チャット サーバー コンプライアンス データベースをホストするサーバー上の SQL Server</p></li>
</ul></td>
<td><p>ローカルの Administrators グループのメンバーであるユーザー。</p></td>
<td><p>「サポート」のドキュメントの「<a href="lync-server-2013-supported-hardware.md">Lync Server 2013 でサポートされるハードウェア</a>」</p>
<p>「サポート」のドキュメントの「<a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync Server 2013 でのサーバーのソフトウェアおよびインフラストラクチャ サポート</a>」</p>
<p><a href="lync-server-2013-determining-your-system-requirements.md">Lync Server 2013 システム要件の決定</a></p>
<p><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Lync Server 2013 常設チャット サーバーの技術要件</a></p></td>
</tr>
<tr class="even">
<td><p><strong>常設チャット サーバー (およびオプションで常設チャット コンプライアンス) をサポートするために適切な内部トポロジの作成</strong></p></td>
<td><p>トポロジ ビルダーを実行して 常設チャット サーバー プールをトポロジに追加します。</p>
<ul>
<li><p>常設チャット サーバー コンポーネントをトポロジに追加する。</p></li>
<li><p>常設チャット サーバー ストア用の SQL Server データベース (および障害復旧用のバックアップ SQL Server) を作成する。</p></li>
<li><p>常設チャット サーバー ファイル用に新しい Lync ファイル ストアを定義するか、既存の Lync ファイル ストアを使用する。</p></li>
<li><p>この 常設チャット サーバー プールに要求をルーティングできる Lync Server 2013 プールを関連付ける。</p></li>
</ul>
<p>常設チャット Compliance が必要な場合</p>
<ul>
<li><p>常設チャット Compliance ストアを追加する。</p></li>
<li><p>常設チャット サーバー プール 定義のチェック ボックスをオンにしてコンプライアンスを有効にする。</p></li>
<li><p>トポロジを公開する。</p></li>
</ul>
<p>常設チャット サーバーを Standard Edition にインストールする場合、 常設チャット サーバー プールの完全修飾ドメイン名 (FQDN) は Standard Edition サーバーと一致する必要があり、 SQL Server データベースは Standard Edition サーバー上の SQL Server Express インスタンスに併置されています。</p></td>
<td><p>トポロジを定義するには、ローカルの Users グループのメンバーであるアカウント。</p>
<p>トポロジを公開するには、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーであるアカウント。また、ユーザーは 常設チャット サーバー ファイル用の Lync ファイル ストアに対してフル コントロールのアクセス許可 (読み取り/書き込み/変更) が必要 (トポロジ ビルダーが必要な DACL を構成できるようにするため)。</p></td>
<td><p>「展開」のドキュメントの「<a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync Server 2013 での展開への常設チャットサーバーの追加</a>」</p></td>
</tr>
<tr class="odd">
<td><p><strong>常設チャット サーバーの展開</strong></p></td>
<td><p>常設チャット サーバー を実行しているすべてのコンピューターで Lync Server セットアップを実行します。 常設チャット サーバー セットアップは、 Lync Server 2013 展開ウィザードに組み込まれていて、次の手順が示されます。</p>
<ul>
<li><p>ローカル管理ストアを展開する。</p></li>
<li><p>常設チャット サーバー サービスをインストールする。</p></li>
<li><p>証明書を要求および割り当てる。</p></li>
<li><p>サービスを実行および開始する。</p></li>
</ul></td>
<td><p>ローカルの Administrators グループのメンバーであるユーザー。</p></td>
<td><p>「展開」のドキュメントの「<a href="lync-server-2013-deploying-persistent-chat-server.md">Lync Server 2013 での常設チャット サーバーの展開</a>」</p></td>
</tr>
<tr class="even">
<td><p><strong>常設チャット管理者の作成</strong></p></td>
<td><p>ユーザーを CsPersistentChatAdministrator セキュリティ グループに追加します。</p></td>
<td><p>ドメイン管理者のメンバーであるユーザー。</p></td>
<td><p>「展開」のドキュメントの「<a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Lync Server 2013 での常設チャット管理者の追加</a>」</p></td>
</tr>
<tr class="odd">
<td><p><strong>常設チャット サーバーの構成</strong></p></td>
<td><p>次のようにユーザーを構成します。</p>
<ul>
<li><p>常設チャット サーバーにアクセスするため、ポリシーによってユーザーを有効にする必要があります。既定では、ポリシーはすべてのユーザーに対してオフになっており、グローバル/サイト/プール/ユーザー スコープで定義できます。</p></li>
<li><p>設定の構成</p></li>
</ul></td>
<td><p>ユーザーは CsPersistentChatAdministrator のメンバーである必要がある。ポリシーを変更するには、ユーザーは最低でも CsUserAdministrator である必要がある。</p></td>
<td><p>「展開」のドキュメントの「<a href="lync-server-2013-configuring-persistent-chat-server.md">Lync Server 2013 での常設チャット サーバーの構成</a>」</p></td>
</tr>
</tbody>
</table>



> [!IMPORTANT]
> 常設チャット サーバー プールは 1 つまたは複数展開できます。特定の領域で生成されたデータがその領域に留まる必要があるという法令上の理由により、複数の 常設チャット サーバー プールをサポートしています。たとえば、シカゴに 1 つ、チューリヒにもう 1 つの 常設チャット サーバー プールを展開してスイスのデータ規制に従う場合、ユーザーはアクセスできるのであれば両方の 常設チャット サーバー プール内のルームに接続できます。


