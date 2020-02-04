---
title: 'Lync Server 2013: コールパークの展開プロセス'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Call Park
ms:assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398283(v=OCS.15)
ms:contentKeyID: 48183586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a00c354aa29a3c9a431b18a686105ab16d94c54
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762645"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-call-park-in-lync-server-2013"></a>Lync Server 2013 でのコールパークの展開プロセス

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-25_

このセクションでは、コールパークアプリケーションの展開に関連する手順の概要について説明します。 コールパークを構成する前に、enterprise Edition または Standard Edition をエンタープライズボイスと共に展開する必要があります。 エンタープライズ Voip を展開すると、コールパークに必要なコンポーネントがインストールされて有効になります。

### <a name="call-park-deployment-process"></a>コール パーク展開プロセス

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
<td><p>オービット テーブルでコール パーク オービット範囲を構成する</p></td>
<td><p>Lync Server コントロールパネルまたは<strong>CSCallParkOrbit</strong>コマンドレットを使用して、呼び出しパークのテーブルに軌道範囲を作成し、それを call パークアプリケーションをホストするアプリケーションサービスと関連付けます。</p>
<div>

> [!NOTE]  
> 既存のダイヤル プランとシームレスに統合するため、一般的にオービット範囲は仮想の内線番号の禁止として構成されます。コール パーク オービット テーブルでオービット番号として Direct Inward Dialing (DID) 番号を指定することは、サポートされていません。


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-create-or-modify-a-call-park-orbit-range.md">通話パークの作成または変更 Lync Server 2013 の範囲の軌道</a></p></td>
</tr>
<tr class="even">
<td><p>コール パーク設定の構成</p></td>
<td><p><strong>CsCpsConfiguration</strong>コマンドレットを使用して、コールパーク設定を構成します。 少なくとも、[ <strong>Ontimeouturi</strong> ] オプションを構成して、保留中の通話がタイムアウトしたときに使うフォールバック先を構成することをお勧めします。次の設定を構成することもできます。</p>
<ul>
<li><p>(オプション) <strong>EnableMusicOnHold</strong> を構成して保留音を有効または無効にします。</p></li>
<li><p>(オプション) <strong>MaxCallPickupAttempts</strong> を構成して、パークされた通話が、代替 Uniform Resource Identifier (URI) に転送されるまでに、応答した電話にかけ直す回数を決定します。</p></li>
<li><p>(オプション) <strong>CallPickupTimeoutThreshold</strong> を構成して、通話がパークされてから、呼び出しに応答した電話にかけ直されるまでの経過時間を決定します。</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-call-park-settings.md">Lync Server 2013 でのコールパーク設定の構成</a></p></td>
</tr>
<tr class="odd">
<td><p>必要に応じて、保留音をカスタマイズする</p></td>
<td><p>既定の保留音を使用しない場合は、<strong>Set-CsCallParkServiceMusicOnHoldFile</strong> コマンドを使用して、音声ファイルをカスタマイズおよびアップロードします。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-customize-call-park-music-on-hold.md">通話パークをカスタマイズする Lync Server 2013 の保留中の音楽</a></p></td>
</tr>
<tr class="even">
<td><p>音声ポリシーを構成してユーザーのコールパークを有効にする</p></td>
<td><p>Lync Server コントロールパネルまたは<strong>CSVoicePolicy</strong>コマンドレットを<strong>Enablecallpark</strong>オプションと共に使用して、ボイスポリシーのユーザーに対してコールパークを有効にします。</p>
<div>

> [!NOTE]  
> 既定では、すべてのユーザーに対して [コールパーク] が無効になっています。


</div>
<div>

> [!NOTE]  
> 複数の音声ポリシーが存在する場合、EnableCallPark プロパティが、既定のポリシーに対してだけでなく、それぞれの音声ポリシーに設定されているのを確認してください。


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsUserAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-enable-call-park-for-users.md">Lync Server 2013 のユーザーに対してコールパークを有効にする</a></p></td>
</tr>
<tr class="odd">
<td><p>コール パーク正規化ルールの確認</p></td>
<td><p>コール パーク オービットを正規化することはできません。正規化ルールにオービット範囲が含まれていないのを確認します。必要に応じて、オービットが正規化されるのを防ぐため、追加の正規化ルールを作成します。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verify-normalization-rules-for-call-park.md">Lync Server 2013 でのコールパークの正規化ルールを確認する</a></p></td>
</tr>
<tr class="even">
<td><p>コールパークの展開を確認する</p></td>
<td><p>通話の保留と取得をテストし、構成が予想どおりに動作することを確認します。</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-call-park-deployment.md">省略Lync Server 2013 でのコールパークの展開を確認する</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

