---
title: 'Lync Server 2013: グループ通話ピックアップの展開プロセス'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Group Call Pickup
ms:assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945615(v=OCS.15)
ms:contentKeyID: 51541444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20f583b330812eab8ea32ecd3c545445b0640fae
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038149"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-group-call-pickup-in-lync-server-2013"></a>Lync Server 2013 でのグループ通話ピックアップの展開プロセス

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-25_

このセクションでは、グループ通話ピックアップの展開に必要な手順の概要について説明します。 グループ通話ピックアップを構成する前に、エンタープライズ Voip を使用して Enterprise Edition または Standard Edition を展開する必要があります。 グループ通話ピックアップで必要なコンポーネントは、エンタープライズ Voip を展開するときにインストールされて有効にされます。

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
<th>手順</th>
<th>必要なグループおよび役割</th>
<th>展開のドキュメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>トポロジで SEFAUtil リソースキットツールを有効にする</p></td>
<td><ol>
<li><p>新しい信頼されたアプリケーションプールを作成するには、 <strong>「new-cstrustedapplicationpool</strong>コマンドレットを使用します。</p></li>
<li><p><strong>「New-cstrustedapplication</strong>コマンドレットを使用して、SEFAUtil ツールを信頼済みアプリケーションとして指定します。</p></li>
<li><p><strong>Enable-CsTopology</strong>コマンドレットを実行してトポロジを有効にします。</p></li>
<li><p>手順1で作成した信頼されたアプリケーションプールにあるフロントエンドサーバーに、リソースキットツールをインストールします。</p></li>
<li><p>SEFAUtil を実行して、展開内のユーザーの着信転送設定を表示することによって、正しく動作していることを確認します。</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploy-the-sefautil-tool.md">SEFAUtil ツールを Lync Server 2013 に展開する</a></p></td>
</tr>
<tr class="even">
<td><p>コールパークオービットテーブルでの通話ピックアップ番号の範囲の構成</p></td>
<td><p><strong>Get-cscallparkorbit</strong>コマンドレットを使用して、コールパークオービットテーブルに通話ピックアップ番号の範囲を作成し、通話ピックアップの範囲を [種類] grouppickup に割り当てます。</p>
<div>

> [!NOTE]  
> 通話パークオービットテーブルでグループ通話ピックアップ番号の範囲を作成、変更、削除、表示するには、Lync Server 管理シェルを使用する必要があります。 グループ通話ピックアップ番号の範囲は、Lync Server コントロールパネルでは使用できません。


</div>
<div>

> [!NOTE]  
> 既存のダイヤルプランとシームレスに統合するために、通常、番号範囲は仮想内線のブロックとして構成されます。 コールパークオービットテーブルで、直接内向きダイヤル (DID) 番号を範囲番号として割り当てることはサポートされていません。


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Lync Server 2013 での通話ピックアップグループ番号の構成</a></p></td>
</tr>
<tr class="odd">
<td><p>通話ピックアップ番号をユーザーに割り当て、ユーザーのグループ通話ピックアップを有効にする</p></td>
<td><p>グループ通話ピックアップを有効にし、ユーザーの通話ピックアップ番号を割り当てるには、SEFAUtil リソースキットツールの/enablegrouppickup パラメーターを使用します。</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Lync Server 2013 のユーザーのグループ通話ピックアップを有効にし、グループ番号を割り当てる</a></p></td>
</tr>
<tr class="even">
<td><p>割り当てられた通話ピックアップ番号およびその他の任意の数のユーザーに通知する</p></td>
<td><p>グループ通話ピックアップユーザーに対して行われた通話はすべてのユーザーが取得できるため、ユーザーは複数のグループを監視する必要があります。</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">グループ通話ピックアップの割り当てを Lync Server 2013 のユーザーに伝達する</a></p></td>
</tr>
<tr class="odd">
<td><p>グループ通話ピックアップの展開を確認する</p></td>
<td><p>呼び出しを発信および取得して、構成が予想どおりに動作することを確認します。</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">オプションLync Server 2013 でのグループ通話ピックアップの展開の確認</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

