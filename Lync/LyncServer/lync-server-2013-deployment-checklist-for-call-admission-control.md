---
title: 'Lync Server 2013: 通話受付管理の展開チェックリスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for call admission control
ms:assetid: 7e56a169-3e63-44ab-bf28-1fdeb52381c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398631(v=OCS.15)
ms:contentKeyID: 48184621
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3dd425d53a282cc24fed8ad2f8be9acc5bf42209
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833503"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-call-admission-control-in-lync-server-2013"></a>Lync Server 2013 の通話受付管理の展開チェックリスト

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-08_

通話受付制御 (CAC) を効率的に計画するには、次の点を考慮する必要があります。

  - CAC を展開するための前提条件。

  - CAC と構成の決定に必要な情報。展開前に行う必要があります。

<div>

## <a name="deployment-prerequisites-for-call-admission-control"></a>通話受付制御の展開の前提条件

通話受付制御を展開する前に、既に Lync Server 2013 内部サーバー (フロントエンドプールまたは Standard Edition サーバー) を展開している必要があります。

</div>

<div>

## <a name="information-requirements-for-call-admission-control"></a>通話受付制御の情報要件

次の表は、通話受付制御の展開に必要な情報をまとめたものです。

### <a name="information-requirements-for-call-admission-control-deployment"></a>通話受付制御の展開に関する情報要件

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>情報</th>
<th>必要な情報の概要</th>
<th>ドキュメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>組織で必要な Lync Server 機能</p></td>
<td><ul>
<li><p>組織でサポートされる機能</p></li>
<li><p>個々のユーザーに対して有効になる機能</p></li>
</ul></td>
<td><p><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Lync Server 2013 での通話受付管理サービス要件の定義</a></p></td>
</tr>
<tr class="even">
<td><p>展開するトポロジとコンポーネント</p></td>
<td><ul>
<li><p>CAC 関連のコンポーネントは、Lync Server 2013 の一部として自動的にインストールされます。</p></li>
</ul></td>
<td><p><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Lync Server 2013 での通話受付管理サービス要件の定義</a></p></td>
</tr>
<tr class="odd">
<td><p>システム要件</p></td>
<td><ul>
<li><p>ハードウェア要件</p></li>
<li><p>ソフトウェア要件</p></li>
<li><p>Collocation の要件</p></li>
</ul></td>
<td><p><a href="lync-server-2013-determining-your-system-requirements.md">Lync Server 2013 システム要件の決定</a></p></td>
</tr>
<tr class="even">
<td><p>インフラストラクチャの要件</p></td>
<td><ul>
<li><p>CAC では、特定のインフラストラクチャ要件は必要ありません。</p></li>
</ul></td>
<td><p><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Lync Server 2013 での通話受付管理のインフラストラクチャ要件</a></p></td>
</tr>
<tr class="odd">
<td><p>ネットワークインターフェイスの要件</p></td>
<td><ul>
<li><p>内部と外部のインターフェイス情報</p></li>
<li><p>ルーティング情報 (NextHop ブログの情報<a href="http://go.microsoft.com/fwlink/p/?linkid=203149">http://go.microsoft.com/fwlink/p/?LinkId=203149</a>を含む、Microsoft Lync Server チームの顧客対応チャネル)</p></li>
</ul></td>
<td><p><a href="lync-server-2013-deploying-external-user-access.md">Lync Server 2013 での外部ユーザー アクセスの展開</a></p></td>
</tr>
<tr class="even">
<td><p>展開戦略</p></td>
<td><ul>
<li><p>展開シーケンス</p></li>
<li><p>ワークグループまたはドメイン</p></li>
<li><p>セキュリティ</p></li>
<li><p>監視と監査</p></li>
<li><p>ハードウェアに関する考慮事項</p></li>
</ul></td>
<td><p><a href="lync-server-2013-best-practices-for-call-admission-control.md">Lync Server 2013 の通話受付管理のベスト プラクティス</a></p></td>
</tr>
<tr class="odd">
<td><p>展開プロセス</p></td>
<td><ul>
<li><p>前提条件</p></li>
<li><p>情報の要件</p></li>
<li><p>プロセスと手順</p></li>
</ul></td>
<td><p><a href="lync-server-2013-configure-call-admission-control.md">Lync Server 2013 での通話受付制御の構成</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

