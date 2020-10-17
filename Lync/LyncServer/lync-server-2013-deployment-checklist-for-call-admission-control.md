---
title: 'Lync Server 2013: 通話受付管理の展開チェックリスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for call admission control
ms:assetid: 7e56a169-3e63-44ab-bf28-1fdeb52381c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398631(v=OCS.15)
ms:contentKeyID: 48184621
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13d9591ad8dfed90373fedc8adfb3a3c3c44eb57
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529144"
---
# <a name="deployment-checklist-for-call-admission-control-in-lync-server-2013"></a>Lync Server 2013 での通話受付管理の展開チェックリスト

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-08_

通話受付管理 (CAC) を効率的に計画するには、以下のことを考慮する必要があります。

  - CAC を展開するための前提条件

  - CAC および展開前に行う必要がある構成上の意思決定に必要な情報

<div>

## <a name="deployment-prerequisites-for-call-admission-control"></a>通話受付管理の展開の前提条件

通話受付管理を展開する前に、既に、フロントエンドプールまたは Standard Edition サーバーのいずれかを含む Lync Server 2013 内部サーバーを展開しておく必要があります。

</div>

<div>

## <a name="information-requirements-for-call-admission-control"></a>通話受付管理の情報要件

次の表は、通話受付管理を展開するために必要な情報の概要を示しています。

### <a name="information-requirements-for-call-admission-control-deployment"></a>通話受付管理の展開の情報要件

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
<td><p>組織が必要とする Lync Server の機能</p></td>
<td><ul>
<li><p>組織でサポートされる機能</p></li>
<li><p>個々のユーザーに対して有効にする機能</p></li>
</ul></td>
<td><p><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Lync Server 2013 での通話受付管理の要件の定義</a></p></td>
</tr>
<tr class="even">
<td><p>展開するトポロジとコンポーネント</p></td>
<td><ul>
<li><p>CAC 関連のコンポーネントは、Lync Server 2013 の一部として自動的にインストールされます。</p></li>
</ul></td>
<td><p><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Lync Server 2013 での通話受付管理の要件の定義</a></p></td>
</tr>
<tr class="odd">
<td><p>システム要件</p></td>
<td><ul>
<li><p>ハードウェア要件</p></li>
<li><p>ソフトウェア要件</p></li>
<li><p>併置要件</p></li>
</ul></td>
<td><p><a href="lync-server-2013-determining-your-system-requirements.md">Lync Server 2013 のシステム要件を決定する</a></p></td>
</tr>
<tr class="even">
<td><p>インフラストラクチャ要件</p></td>
<td><ul>
<li><p>CAC に必要なインフラストラクチャ要件は特にありません</p></li>
</ul></td>
<td><p><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Lync Server 2013 での通話受付管理のインフラストラクチャ要件</a></p></td>
</tr>
<tr class="odd">
<td><p>ネットワーク インターフェイス要件</p></td>
<td><ul>
<li><p>内部インターフェイスと外部インターフェイスの情報</p></li>
<li><p>ルーティング情報 (NextHop ブログの情報 <a href="https://go.microsoft.com/fwlink/p/?linkid=203149">https://go.microsoft.com/fwlink/p/?LinkId=203149</a> を含む、Microsoft Lync Server チームの顧客対応チャネル)</p></li>
</ul></td>
<td><p><a href="lync-server-2013-deploying-external-user-access.md">Lync Server 2013 での外部ユーザーアクセスの展開</a></p></td>
</tr>
<tr class="even">
<td><p>展開戦略</p></td>
<td><ul>
<li><p>展開順序</p></li>
<li><p>ワークグループかドメインか</p></li>
<li><p>セキュリティ</p></li>
<li><p>監視と監査</p></li>
<li><p>ハードウェアに関する考慮事項</p></li>
</ul></td>
<td><p><a href="lync-server-2013-best-practices-for-call-admission-control.md">Lync Server 2013 での通話受付管理のベストプラクティス</a></p></td>
</tr>
<tr class="odd">
<td><p>展開プロセス</p></td>
<td><ul>
<li><p>必要条件</p></li>
<li><p>情報要件</p></li>
<li><p>プロセスと手順</p></li>
</ul></td>
<td><p><a href="lync-server-2013-configure-call-admission-control.md">Lync Server 2013 で通話受付管理を構成する</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

