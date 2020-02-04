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
ms.openlocfilehash: e55e2471a71c985861c35c4ec2e07582dbfa0f23
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740757"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-archiving-in-lync-server-2013"></a>Lync Server 2013 のアーカイブの展開チェックリスト

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-18_

アーカイブは、Lync Server 2013 展開の各フロントエンドサーバーに自動的にインストールされますが、使用する前に設定する必要があります。 このセクションで概要を設定するために必要な手順は、アーカイブの展開を構成するものです。

<div>

## <a name="deployment-sequence"></a>展開シーケンス

アーカイブの設定方法は、選択したストレージオプションによって異なります。

  - 展開のすべてのユーザーに対して Microsoft Exchange 統合を使用している場合は、ユーザーの Lync Server 2013 アーカイブポリシーを構成する必要はありません。 代わりに、exchange 2013 を使用しているユーザーのアーカイブをサポートするように Exchange のインプレースホールドポリシーを構成し、メールボックスがインプレース保持されるようにします。 これらのポリシーの構成の詳細については、Exchange 2013 の製品に関するドキュメントを参照してください。

  - 展開内のすべてのユーザーに対して Microsoft Exchange 統合を使用していない場合は、お客様のトポロジに Lync Server アーカイブデータベース (SQL Server データベース) を追加し、それを公開して、ユーザーのポリシーと設定を構成する必要があります。それらのユーザーのデータをアーカイブします。 最初のトポロジを展開するとき、または少なくとも1つのフロントエンドプールまたは Standard Edition サーバーを展開した後で、アーカイブデータベースを展開することができます。 このドキュメントでは、アーカイブデータベースを既存の展開に追加して展開する方法について説明します。

1つのフロントエンドプールまたは Standard Edition サーバーでアーカイブを有効にしている場合、展開内の他のすべてのフロントエンドプールおよび Standard Edition サーバーでアーカイブを有効にする必要があります。 その理由は、通信のアーカイブが必要なユーザーは、別のプールでホストされるグループ IM 会話や会議に招待される可能性があるからです。 会話や会議がホストされているプールでアーカイブが有効になっていない場合は、セッション全体をアーカイブすることはできません。 このような場合、アーカイブが有効なユーザーの IM はアーカイブできますが、会議コンテンツ ファイルや会議参加または退出イベントはアーカイブできません。

<div>


> [!IMPORTANT]  
> コンプライアンス上の理由からアーカイブが重要である場合は、アーカイブを展開し、ポリシーおよびその他のオプションを適切なレベルで構成して、適切なユーザー全員に対して有効にしてから、Lync Server 2013 のユーザーを有効にする必要があります。



</div>

</div>

<div>

## <a name="archiving-deployment-process"></a>アーカイブ展開プロセス

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
<th>段階</th>
<th>手順</th>
<th>役割とグループ メンバーシップ</th>
<th>ドキュメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>必要なハードウェアとソフトウェアのインストール</strong></p></td>
<td><ul>
<li><p>Microsoft Exchange 統合 (一部またはすべてのユーザーのアーカイブストレージに Exchange 2013 を使用) を使用するには、既存の Exchange 2013 の展開が必要です。</p></li>
<li><p>一部またはすべてのユーザーのアーカイブストレージに個別のアーカイブデータベース (SQL Server データベースを使用) を使用するには、アーカイブデータを格納するサーバー上の SQL Server。</p></li>
</ul>
<div>

> [!NOTE]  
> アーカイブは、エンタープライズプールと Standard Edition サーバーのフロントエンドサーバー上で実行されます。 これらのサーバーのインストールに必要なもの以外には、追加のハードウェア要件やソフトウェア要件はありません。


</div></td>
<td><p>ローカルの Administrators グループのメンバーであるドメイン ユーザー。</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">サポートされているドキュメントの Lync Server 2013 でサポートされているハードウェア</a>。</p>
<p>サポートドキュメントの<a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync server 2013 でのサーバーソフトウェアとインフラストラクチャのサポート</a>。</p>
<p>計画ドキュメントの<a href="lync-server-2013-technical-requirements-for-archiving.md">Lync Server 2013 でのアーカイブの技術要件</a>。</p>
<p>展開ドキュメントの<a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">Lync Server 2013 でアーカイブ用にシステムとインフラストラクチャ</a>をセットアップします。</p>
<p>サポートドキュメントの<a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Lync server 2013 での Exchange Server と SharePoint の統合のサポート</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>アーカイブをサポートする適切な内部トポロジを作成します (展開のすべてのユーザーに対して Microsoft Exchange 統合を使用していない場合のみ)。</strong></p></td>
<td><p>トポロジビルダーを実行して、Lync Server 2013 アーカイブデータベース (SQL Server データベース) をトポロジに追加してから、トポロジを公開します。</p></td>
<td><p>アーカイブデータベースを取り込むためのトポロジを定義するには、ローカルユーザーグループのメンバーであるアカウント。</p>
<p>トポロジを公開するには、ドメイン管理者グループと RTCUniversalServerAdmins グループのメンバーであり、Lync Server 2013 ファイルストアに使用するフルコントロール権限 (読み取り/書き込み/変更) を持つアカウント (トポロジビルダーが必要な Dacl を構成できるようにします) を公開します。</p></td>
<td><p>展開ドキュメントの<a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">既存の Lync Server 2013 展開にアーカイブデータベースを追加する</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>サーバー間認証を構成する (Microsoft Exchange 統合を使用している場合のみ)</strong></p></td>
<td><p>Lync Server 2013 と Exchange 2013 の間の認証を有効にするようにサーバーを構成します。 アーカイブを有効にする前に<strong>、CsExchangeStorageConnectivity testuser_sipUri –フォルダー収集</strong>を実行して、Exchange アーカイブストレージの接続を検証することをお勧めします。</p></td>
<td><p>サーバーで証明書を管理するための適切なアクセス許可のあるアカウント。</p></td>
<td><p>展開ドキュメントまたは運用ドキュメントの<a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">Lync server 2013 でサーバー間認証 (OAuth) とパートナーアプリケーションを管理</a>します。</p></td>
</tr>
<tr class="even">
<td><p><strong>アーカイブポリシーと構成を構成する</strong></p></td>
<td><p>Microsoft Exchange 統合を使用するかどうか、グローバルポリシー、サイトとユーザーのポリシー (すべてのデータストレージに対して Microsoft Exchange の統合を使用していない場合)、および重要なモードやデータなどの特定のアーカイブオプションを含むアーカイブを構成します。エクスポートと削除。</p>
<p>Microsoft Exchange 統合を使用している場合は、必要に応じて、Exchange のインプレースホールドポリシーを構成します。</p></td>
<td><p>RTCUniversalServerAdmins グループ (Windows PowerShell のみ)。または、CSArchivingAdministrator の役割または CSAdministrator の役割にユーザーを割り当てます。</p></td>
<td><p>展開ドキュメントの<a href="lync-server-2013-configuring-support-for-archiving.md">Lync Server 2013 でアーカイブのサポートを構成</a>します。</p>
<p>Exchange 製品ドキュメント (Microsoft Exchange 統合を使用している場合)。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="deploying-lync-server-and-microsoft-exchange-in-different-forests"></a>さまざまなフォレストでの Lync Server と Microsoft Exchange の展開

Microsoft Exchange Server が Lync Server と同じフォレストに展開されていない場合は、次の Exchange Active Directory 属性が Lync Server が展開されているフォレストと同期されていることを確認する必要があります。

1.  msExchUserHoldPolicies

2.  proxyAddresses

これは複数値の属性です。この属性を同期するときは、値を置き換えるのではなく値をマージして、既存の値が失われないようにする必要があります。

</div>

</div>

<span> </span>

</div>

</div>

</div>

