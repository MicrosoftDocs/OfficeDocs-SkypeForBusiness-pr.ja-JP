---
title: 'Lync Server 2013: アーカイブの展開チェックリスト'
TOCTitle: アーカイブの展開チェックリスト
ms:assetid: 7479734d-be01-40d9-ad82-320a09d19d04
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205009(v=OCS.15)
ms:contentKeyID: 48272468
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 のアーカイブの展開チェックリスト

 

_**トピックの最終更新日:** 2015-03-09_

アーカイブは Lync Server 2013 の展開の各フロントエンド サーバーに自動的にインストールされますが、使用するにはセットアップを行う必要があります。ここで説明するセットアップに必要な手順では、アーカイブの展開を構成します。

## 展開順序

アーカイブのセットアップ方法は、選択するストレージ オプションによって異なります。

  - 展開のすべてのユーザーに対して Microsoft Exchange 統合を使用する場合は、ユーザーのために Lync Server 2013 アーカイブ ポリシーを構成する必要はありません。代わりに、 Exchange インプレース保持ポリシーを構成して、 Exchange 2013 に所属しているユーザーのアーカイブをサポートします。ユーザーのメールボックスはインプレース保持に格納されます。これらのポリシーの構成の詳細については、 Exchange 2013 製品のドキュメントを参照してください。

  - 展開のすべてのユーザーに対して Microsoft Exchange 統合を使用していない場合は、 Lync Server アーカイブ データベース ( SQL Server データベース) をトポロジに追加して発行し、併せてユーザーのポリシーと設定を構成する必要があります。これを行わないと、ユーザーのデータをアーカイブできません。アーカイブ データベースは、最初のトポロジを展開するのと同時に展開するか、または少なくとも 1 つのフロントエンド プールまたは Standard Edition サーバーを展開した後で展開できます。このドキュメントでは、既存の展開に追加することでアーカイブ データベースを展開する方法について説明します。

1 つのフロントエンド プールまたは Standard Edition サーバーでアーカイブを有効にする場合、展開内の他のすべてのフロントエンド プールおよび Standard Edition サーバーに対してアーカイブを有効にする必要があります。これは、通信をアーカイブする必要があるユーザーは、別のプールでホストされるグループ IM 会話やミーティングに招待される可能性があるためです。会話やミーティングがホストされているプールでアーカイブが有効になっていない場合は、完全なセッションをアーカイブすることはできません。このような場合、アーカイブが有効なユーザーの IM はアーカイブできますが、会議コンテンツ ファイルおよび会議参加または退出イベントはアーカイブできません。


> [!IMPORTANT]
> コンプライアンス上の理由で、組織にとってアーカイブが重要な場合は、アーカイブの展開、適切なレベルでのポリシーおよびその他のオプションの構成、適切なすべてのユーザーに対するアーカイブの有効化を行ってから、 Lync Server 2013 でこうしたユーザーを有効にするようにしてください。



## アーカイブの展開プロセス

次の表に、既存のトポロジにアーカイブを展開するために必要な手順の概要を示します。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>フェーズ</th>
<th>ステップ</th>
<th>役割とグループ メンバーシップ</th>
<th>ドキュメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>必要なハードウェアとソフトウェアのインストール</strong></p></td>
<td><ul>
<li><p>Microsoft Exchange 統合を使用するには (一部またはすべてのユーザーのストレージのアーカイブに Exchange 2013 を使用する場合)、 Exchange 2013 の既存の展開が必要です。</p></li>
<li><p>一部またはすべてのユーザーのストレージをアーカイブするために別のアーカイブ データベースを使用するには (SQL Server データベースを使用する場合)、アーカイブ データを格納するサーバーに SQL Server が必要です。</p></li>
</ul>

> [!NOTE]
> アーカイブは、エンタープライズ プールのフロントエンド サーバーと Standard Edition サーバー上で実行されます。これらのサーバーのインストールに必要なもの以外には、追加のハードウェア要件やソフトウェア要件はありません。

</div></td>
<td><p>ローカルの Administrators グループのメンバーであるドメイン ユーザー。</p></td>
<td><p>「サポート」のドキュメントの「<a href="lync-server-2013-supported-hardware.md">Lync Server 2013 でサポートされるハードウェア</a>」。</p>
<p>「サポート」のドキュメントの「<a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync Server 2013 でのサーバーのソフトウェアおよびインフラストラクチャ サポート</a>」。</p>
<p>「計画」のドキュメントの「<a href="lync-server-2013-technical-requirements-for-archiving.md">Lync Server 2013 のアーカイブの技術要件</a>」。</p>
<p>「展開」のドキュメントの「<a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">アーカイブのシステムおよびインフラストラクチャの設定</a>」。</p>
<p>「サポート」のドキュメントの「<a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Lync Server 2013 の Exchange Server および SharePoint の統合のサポート</a>」。</p></td>
</tr>
<tr class="even">
<td><p><strong>アーカイブをサポートするための適切な内部トポロジの作成 (展開のすべてのユーザーに対して Microsoft Exchange 統合を使用しない場合のみ)</strong></p></td>
<td><p>トポロジ ビルダーを実行して Lync Server 2013 アーカイブ データベース ( SQL Server データベース) をトポロジに追加した後、トポロジを公開します。</p></td>
<td><p>アーカイブ データベースを組み込むためのトポロジを定義する場合は、ローカル ユーザー グループのメンバーであるアカウント。</p>
<p>トポロジを公開する場合は、Domain Admins グループと RTCUniversalServerAdmins グループのメンバーであり、(必要な DACL をトポロジ ビルダーが構成できるように) Lync Server 2013 ファイル ストアで使用されるファイル共有に対してフル コントロール (読み取り/書き込み/変更) のアクセス許可を持つアカウント。</p></td>
<td><p>「展開」のドキュメントの「<a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">既存の Lync Server 2013 展開へのアーカイブ データベースの追加</a>」。</p></td>
</tr>
<tr class="odd">
<td><p><strong>サーバー間認証の構成 ( Microsoft Exchange 統合を使用する場合のみ)</strong></p></td>
<td><p>Lync Server 2013 と Exchange 2013 の間の認証を有効にするようにサーバーを構成します。アーカイブを有効にする前に、 <strong>Test-CsExchangeStorageConnectivity testuser_sipUri –Folder Dumpster</strong> を実行して、 Exchange アーカイブ ストレージの接続を検証することをお勧めします。</p></td>
<td><p>サーバーで証明書を管理するための適切なアクセス許可のあるアカウント。</p></td>
<td><p>「展開」または「操作」のドキュメントの「<a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">Lync Server 2013 でのサーバー間認証 (Oauth) およびパートナー アプリケーションの管理</a>」。</p></td>
</tr>
<tr class="even">
<td><p><strong>アーカイブ ポリシーと設定の構成</strong></p></td>
<td><p>Microsoft Exchange 統合を使用するかどうか、グローバル ポリシー、任意のサイトおよびユーザー ポリシー ( Microsoft Exchange 統合をすべてのデータ ストレージで使用していない場合)、特定のアーカイブ オプション (重要モード、データのエクスポートと削除など) を含む、アーカイブの構成を行います。</p>
<p>Microsoft Exchange 統合を使用する場合は、必要に応じて Exchange インプレース保持ポリシーを構成します。</p></td>
<td><p>RTCUniversalServerAdmins グループ (Windows PowerShell のみ)。あるいは、CSArchivingAdministrator の役割または CSAdministrator の役割にユーザーを割り当てます。</p></td>
<td><p>「展開」のドキュメントの「<a href="lync-server-2013-configuring-support-for-archiving.md">アーカイブのサポートの構成</a>」。</p>
<p>Exchange 製品ドキュメント ( Microsoft Exchange 統合を使用する場合)。</p></td>
</tr>
</tbody>
</table>


## 異なるフォレストへの Lync Server と Microsoft Exchange の展開

Microsoft Exchange Server を Lync Server と同じフォレストに展開しない場合は、以下の Exchange Active Directory 属性が Lync Server の展開されているフォレストと同期されていることを確認する必要があります。

1.  msExchUserHoldPolicies

2.  proxyAddresses

これは複数値の属性です。この属性を同期するときは、値を置き換えるのではなく値をマージして、既存の値が失われないようにする必要があります。

