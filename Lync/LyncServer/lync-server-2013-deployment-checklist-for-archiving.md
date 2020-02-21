---
title: 'Lync Server 2013: アーカイブの展開チェックリスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for Archiving
ms:assetid: 7479734d-be01-40d9-ad82-320a09d19d04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205009(v=OCS.15)
ms:contentKeyID: 48184516
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2df74bda74f1b9af01e1c4e73fa2f21b7119363f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188160"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-archiving-in-lync-server-2013"></a>Lync Server 2013 でのアーカイブの展開チェックリスト

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-18_

アーカイブは、Lync Server 2013 展開の各フロントエンドサーバーに自動的にインストールされますが、使用する前に設定する必要があります。 ここで説明するセットアップに必要な手順では、アーカイブの展開を構成します。

<div>

## <a name="deployment-sequence"></a>展開の順序

アーカイブのセットアップ方法は、選択するストレージ オプションによって異なります。

  - 展開内のすべてのユーザーに対して Microsoft Exchange 統合を使用する場合は、Lync Server 2013 アーカイブポリシーをユーザーに対して構成する必要はありません。 代わりに、exchange 2013 に所属するユーザーのアーカイブをサポートするように Exchange のインプレース保持ポリシーを構成します。メールボックスはインプレース保持に配置されています。 これらのポリシーの構成の詳細については、「Exchange 2013 製品のドキュメント」を参照してください。

  - 展開内のすべてのユーザーに対して Microsoft Exchange 統合を使用しない場合は、Lync Server アーカイブデータベース (SQL Server データベース) をトポロジに追加してから発行し、ユーザーのポリシーと設定を構成する必要があります。その前に、これらのユーザーのデータをアーカイブします。 アーカイブデータベースは、初期トポロジを展開するとき、または少なくとも1つのフロントエンドプールまたは Standard Edition サーバーを展開した後に展開できます。 このドキュメントでは、アーカイブデータベースを既存の展開に追加して展開する方法について説明します。

1 つのフロントエンド プールまたは Standard Edition サーバーでアーカイブを有効にする場合、展開内の他のすべてのフロントエンド プールおよび Standard Edition サーバーに対してアーカイブを有効にする必要があります。これは、通信をアーカイブする必要があるユーザーは、別のプールでホストされるグループ IM 会話やミーティングに招待される可能性があるためです。会話やミーティングがホストされているプールでアーカイブが有効になっていない場合は、完全なセッションをアーカイブすることはできません。このような場合、アーカイブが有効なユーザーの IM はアーカイブできますが、会議コンテンツ ファイルおよび会議参加または退出イベントはアーカイブできません。

<div>


> [!IMPORTANT]  
> コンプライアンス上の理由からアーカイブが重要な場合は、アーカイブを展開し、ポリシーおよびその他のオプションを適切なレベルで構成して、適切なユーザーすべてに対して有効にしてから、Lync Server 2013 のユーザーを有効にする必要があります。



</div>

</div>

<div>

## <a name="archiving-deployment-process"></a>アーカイブの展開プロセス

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
<th>手順</th>
<th>役割とグループ メンバーシップ</th>
<th>ドキュメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>必要なハードウェアとソフトウェアのインストール</strong></p></td>
<td><ul>
<li><p>Microsoft Exchange 統合 (Exchange 2013 を使用して一部またはすべてのユーザーのストレージをアーカイブする) を使用するには、既存の Exchange 2013 展開が必要です。</p></li>
<li><p>一部またはすべてのユーザーのストレージをアーカイブするために別のアーカイブ データベースを使用するには (SQL Server データベースを使用する場合)、アーカイブ データを格納するサーバーに SQL Server が必要です。</p></li>
</ul>
<div>

> [!NOTE]  
> アーカイブは、エンタープライズ プールのフロントエンド サーバーと Standard Edition サーバー上で実行されます。これらのサーバーのインストールに必要なもの以外には、追加のハードウェア要件やソフトウェア要件はありません。


</div></td>
<td><p>ローカルの Administrators グループのメンバーであるドメイン ユーザー。</p></td>
<td><p>「サポート」のドキュメントの「 <a href="lync-server-2013-supported-hardware.md">Lync Server 2013 でサポートされているハードウェア</a>」。</p>
<p>「サポート」のドキュメントの「 <a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync server 2013 でのサーバーソフトウェアとインフラストラクチャのサポート」</a> 。</p>
<p>「計画」のドキュメントの「 <a href="lync-server-2013-technical-requirements-for-archiving.md">Lync Server 2013 でのアーカイブの技術要件</a>」。</p>
<p>「展開」のドキュメントの「 <a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">Lync Server 2013 でのアーカイブのためのシステムとインフラストラクチャの</a>セットアップ」を参照してください。</p>
<p>「サポート」のドキュメントの「 <a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Lync server 2013 での Exchange Server および SharePoint の統合のサポート</a>」。</p></td>
</tr>
<tr class="even">
<td><p><strong>アーカイブをサポートするために適切な内部トポロジを作成します (展開内のすべてのユーザーに対して Microsoft Exchange 統合を使用していない場合のみ)。</strong></p></td>
<td><p>トポロジビルダーを実行して、Lync Server 2013 アーカイブデータベース (SQL Server データベース) をトポロジに追加してから、トポロジを公開します。</p></td>
<td><p>アーカイブ データベースを組み込むためのトポロジを定義する場合は、ローカル ユーザー グループのメンバーであるアカウント。</p>
<p>トポロジを公開するには、domain admins グループおよび RTCUniversalServerAdmins グループのメンバーであり、Lync Server 2013 ファイルストアに対して使用されるファイル共有のフルコントロールアクセス許可 (読み取り/書き込み/変更) を持つアカウント (トポロジビルダーが必要な Dacl を構成できるようにするため)。</p></td>
<td><p>「展開」のドキュメントの「<a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">既存の Lync Server 2013 展開へのアーカイブデータベースの追加」を</a>参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>サーバー間認証を構成する (Microsoft Exchange 統合を使用する場合のみ)</strong></p></td>
<td><p>Lync Server 2013 と Exchange 2013 の間の認証を有効にするようにサーバーを構成します。 アーカイブを有効にする前に、Exchange アーカイブストレージの接続を検証するには、 <strong>CsExchangeStorageConnectivity testuser_sipUri-フォルダー収集</strong>を実行することをお勧めします。</p></td>
<td><p>サーバーで証明書を管理するための適切なアクセス許可のあるアカウント。</p></td>
<td><p>「展開」のドキュメントまたは「操作」のドキュメントの<a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">「Lync server 2013 でのサーバー間認証 (OAuth) およびパートナーアプリケーションの管理」</a>を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>アーカイブ ポリシーと設定の構成</strong></p></td>
<td><p>アーカイブを構成する (Microsoft Exchange 統合を使用するかどうか、グローバルポリシーとサイトポリシーおよびユーザーポリシーを (すべてのデータ記憶域に対して Microsoft Exchange 統合を使用しない場合)、および特定のアーカイブオプション (重要なモードやデータなど) を含む)。エクスポートと削除。</p>
<p>Microsoft Exchange 統合を使用する場合は、必要に応じて Exchange のインプレース保持ポリシーを構成します。</p></td>
<td><p>RTCUniversalServerAdmins グループ (Windows PowerShell のみ)。あるいは、CSArchivingAdministrator の役割または CSAdministrator の役割にユーザーを割り当てます。</p></td>
<td><p>「展開」のドキュメントの「 <a href="lync-server-2013-configuring-support-for-archiving.md">Lync Server 2013 でのアーカイブのサポートの構成</a>」を参照してください。</p>
<p>Exchange 製品ドキュメント (Microsoft Exchange 統合を使用している場合)。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="deploying-lync-server-and-microsoft-exchange-in-different-forests"></a>異なるフォレストへの Lync Server と Microsoft Exchange の展開

Microsoft Exchange Server が Lync Server と同じフォレストに展開されていない場合は、次の Exchange Active Directory 属性が Lync Server が展開されているフォレストに同期されていることを確認する必要があります。

1.  msExchUserHoldPolicies

2.  proxyAddresses

これは複数値の属性です。この属性を同期するときは、値を置き換えるのではなく値をマージして、既存の値が失われないようにする必要があります。

</div>

</div>

<span> </span>

</div>

</div>

</div>

