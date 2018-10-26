---
title: 'Lync Server 2013: 通話受付管理の展開チェックリスト'
TOCTitle: 通話受付管理の展開チェックリスト
ms:assetid: 7e56a169-3e63-44ab-bf28-1fdeb52381c8
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398631(v=OCS.15)
ms:contentKeyID: 48272653
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の通話受付管理の展開チェックリスト

 

_**トピックの最終更新日:** 2016-12-08_

通話受付管理 (CAC) を効率的に計画するには、以下のことを考慮する必要があります。

  - CAC を展開するための前提条件

  - CAC および展開前に行う必要がある構成上の意思決定に必要な情報

## 通話受付管理の展開の前提条件

通話受付管理を展開する前に、フロント エンド プールまたは Standard Edition サーバーのいずれかを含め、Lync Server 2013 内部サーバーを既に展開している必要があります。

## 通話受付管理の情報要件

次の表は、通話受付管理を展開するために必要な情報の概要を示しています。

### 通話受付管理の展開の情報要件

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
<td><p>組織で必要な Lync Server の機能</p></td>
<td><ul>
<li><p>組織でサポートされる機能</p></li>
<li><p>個々のユーザーに対して有効にする機能</p></li>
</ul></td>
<td><p><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Lync Server 2013 での通話受付管理サービス要件の定義</a></p></td>
</tr>
<tr class="even">
<td><p>展開するトポロジとコンポーネント</p></td>
<td><ul>
<li><p>CAC 関連のコンポーネントは、Lync Server 2013 の一部として自動的にインストールされます</p></li>
</ul>
<p></p></td>
<td><p><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Lync Server 2013 での通話受付管理サービス要件の定義</a></p></td>
</tr>
<tr class="odd">
<td><p>システム要件</p></td>
<td><ul>
<li><p>ハードウェア要件</p></li>
<li><p>ソフトウェア要件</p></li>
<li><p>併置要件</p></li>
</ul>
<p></p></td>
<td><p><a href="lync-server-2013-determining-your-system-requirements.md">Lync Server 2013 システム要件の決定</a></p></td>
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
<li><p>ルーティング情報 (Microsoft Lync Server チームがお客様の疑問にお答えする NextHop ブログ (<a href="http://go.microsoft.com/fwlink/?linkid=203149%26clcid=0x411" class="uri">http://go.microsoft.com/fwlink/?linkid=203149&amp;clcid=0x411</a>) の情報を含みます)</p></li>
</ul></td>
<td><p><a href="lync-server-2013-deploying-external-user-access.md">Lync Server 2013 での外部ユーザー アクセスの展開</a></p></td>
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
<td><p><a href="lync-server-2013-best-practices-for-call-admission-control.md">Lync Server 2013 の通話受付管理のベスト プラクティス</a></p></td>
</tr>
<tr class="odd">
<td><p>展開プロセス</p></td>
<td><ul>
<li><p>必要条件</p></li>
<li><p>情報要件</p></li>
<li><p>プロセスと手順</p></li>
</ul></td>
<td><p><a href="lync-server-2013-configure-call-admission-control.md">Lync Server 2013 での通話管理受付の構成</a></p></td>
</tr>
</tbody>
</table>

