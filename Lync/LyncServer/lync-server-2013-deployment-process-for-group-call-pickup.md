---
title: 'Lync Server 2013: グループ通話のピックアップの展開プロセス'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for Group Call Pickup
ms:assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945615(v=OCS.15)
ms:contentKeyID: 51541444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04ff5eda01c5436240c0baca2b1711bba8e9c996
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833472"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-group-call-pickup-in-lync-server-2013"></a>Lync Server 2013 でのグループ通話のピックアップの展開プロセス

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-25_

このセクションでは、グループ通話のピックアップの展開に関連する手順の概要について説明します。 グループ通話のピックアップを構成する前に、enterprise Edition または Standard Edition をエンタープライズボイスと共に展開する必要があります。 エンタープライズ Voip を展開すると、グループ通話のピックアップに必要なコンポーネントがインストールされて有効になります。

### <a name="group-call-pickup-deployment-process"></a>グループ通話ピックアップの展開プロセス

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
<th>必要なグループおよび役割</th>
<th>「展開」のドキュメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>トポロジで SEFAUtil リソースキットツールを有効にする</p></td>
<td><ol>
<li><p><strong>New-CsTrustedApplicationPool</strong> コマンドレットを使用して、新しい信頼済みアプリケーション プールを作成します。</p></li>
<li><p><strong>New-CsTrustedApplication</strong> コマンドレットを使用して、SEFAUtil ツールを信頼済みアプリケーションとして指定します。</p></li>
<li><p><strong>Enable-CsTopology</strong> コマンドレットを実行して、トポロジを有効にします。</p></li>
<li><p>手順1で作成した信頼されたアプリケーションプール内のフロントエンドサーバーにリソースキットツールをインストールします。</p></li>
<li><p>SEFAUtil を実行し、展開内のユーザーの着信の転送設定を表示して、SEFAUtil が適切に実行されることを確認します。</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploy-the-sefautil-tool.md">Deploy the SEFAUtil tool in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>コール パーク オービット テーブルに通話ピックアップの番号範囲を構成する</p></td>
<td><p><strong>CSCallParkOrbit</strong>コマンドレットを使用して、通話パークの番号の範囲を作成し、通話のピックアップの範囲を「grouppickup」として割り当てます。</p>
<div>

> [!NOTE]  
> 通話パークの軌道の番号範囲を作成、変更、削除、および表示するには、Lync Server 管理シェルを使用する必要があります。 グループ通話の集配番号の範囲は Lync Server コントロールパネルでは利用できません。


</div>
<div>

> [!NOTE]  
> 既存のダイヤル プランとシームレスに統合するため、番号範囲は、通常、仮想の内線番号のブロックとして構成されます。コール パーク オービット テーブルで Direct Inward Dialing (DID) 番号を範囲番号として指定することはサポートされていません。


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Lync Server 2013 での通話ピックアップグループ番号の設定</a></p></td>
</tr>
<tr class="odd">
<td><p>通話集配番号をユーザーに割り当てて、ユーザーに対してグループ通話のピックアップを有効にする</p></td>
<td><p>SEFAUtil リソースキットツールの/enablegrouppickup パラメーターを使用して、グループ通話のピックアップを有効にし、ユーザーに通話の集配番号を割り当てることができます。</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Lync Server 2013 のユーザーに対してグループ通話のピックアップを有効にし、グループ番号を割り当てる</a></p></td>
</tr>
<tr class="even">
<td><p>割り当てられた通話ピックアップ番号をユーザーに通知し、必要な他の番号があるかどうかを確認する</p></td>
<td><p>グループ通話のピックアップユーザーに発信された通話は、ユーザーが取得することができるため、ユーザーは複数のグループを監視する必要がある場合があります。</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">グループ通話の集配の課題を Lync Server 2013 のユーザーに伝える</a></p></td>
</tr>
<tr class="odd">
<td><p>グループ通話の集配の展開を確認する</p></td>
<td><p>通話の発信と取得をテストし、構成が予想どおりに動作することを確認します。</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">省略Lync Server 2013 でグループ通話のピックアップの展開を確認する</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

