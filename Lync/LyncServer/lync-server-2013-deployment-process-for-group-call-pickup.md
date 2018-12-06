---
title: グループ通話ピックアップの展開プロセス
TOCTitle: グループ通話ピックアップの展開プロセス
ms:assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ945615(v=OCS.15)
ms:contentKeyID: 52056532
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# グループ通話ピックアップの展開プロセス

 

_**トピックの最終更新日:** 2015-03-09_

このセクションでは、グループ通話ピックアップの展開に含まれる手順の概要を説明します。グループ通話ピックアップを構成する前に、Enterprise Edition または Standard Edition を エンタープライズ VoIP と共に展開する必要があります。グループ通話ピックアップで必要とされるコンポーネントは、エンタープライズ VoIP を展開するときにインストールされ、有効化されます。

### グループ通話ピックアップの展開プロセス

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
<th>展開のドキュメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>トポロジ内で SEFAUtil リソース キット ツールを有効にする</p></td>
<td><ol>
<li><p><strong>New-CsTrustedApplicationPool</strong> コマンドレットを使用して、新しい信頼済みアプリケーション プールを作成します。</p></li>
<li><p><strong>New-CsTrustedApplication</strong> コマンドレットを使用して、SEFAUtil ツールを信頼済みアプリケーションとして指定します。</p></li>
<li><p><strong>Enable-CsTopology</strong> コマンドレットを実行して、トポロジを有効にします。</p></li>
<li><p>ステップ 1. で作成した信頼済みアプリケーション プールに含まれる フロント エンド サーバーにリソース キット ツールをインストールします。</p></li>
<li><p>SEFAUtil を実行し、展開内のユーザーの着信の転送設定を表示して、SEFAUtil が適切に実行されることを確認します。</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploy-the-sefautil-tool.md">SEFAUtil ツールを展開する</a></p></td>
</tr>
<tr class="even">
<td><p>コール パーク オービット テーブルに通話ピックアップの番号範囲を構成する</p></td>
<td><p><strong>New-CSCallParkOrbit</strong> コマンドレットを使用して、コール パーク オービット テーブルに通話ピックアップの番号範囲を構成し、通話ピックアップ範囲に GroupPickup の種類を割り当てます。</p>

> [!NOTE]
> コール パーク オービット テーブルにあるグループ通話ピックアップの番号範囲を作成、変更、削除、および表示するには、Lync Server 管理シェルを使用する必要があります。Lync Server コントロール パネルでは、グループ通話ピックアップの番号範囲を使用できません。

> [!NOTE]
> 既存のダイヤル プランとシームレスに統合するため、番号範囲は、通常、仮想の内線番号のブロックとして構成されます。コール パーク オービット テーブルで Direct Inward Dialing (DID) 番号を範囲番号として指定することはサポートされていません。

<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-call-pickup-group-numbers.md">通話ピックアップ グループ番号の構成</a></p></td>
</tr>
<tr class="odd">
<td><p>通話ピックアップ番号をユーザーに割り当てて、それらのユーザーに対してグループ通話ピックアップを有効にする</p></td>
<td><p>SEFAUtil リソース キット ツールで /enablegrouppickup パラメーターを使用し、グループ通話ピックアップを有効にして、ユーザーに通話ピックアップ番号を割り当てます。</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">ユーザーに対するグループ通話ピックアップの有効化とグループ番号の割り当て</a></p></td>
</tr>
<tr class="even">
<td><p>割り当てられた通話ピックアップ番号をユーザーに通知し、必要な他の番号があるかどうかを確認する</p></td>
<td><p>どのユーザーもグループ通話ピックアップ ユーザーへの通話を取得できるので、ユーザーは複数のグループの監視を望む場合があります。</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">グループ通話ピックアップの割り当てをユーザーに伝える</a></p></td>
</tr>
<tr class="odd">
<td><p>グループ通話ピックアップの展開を確認する</p></td>
<td><p>通話の発信と取得をテストし、構成が予想どおりに動作することを確認します。</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">(省略可) グループ通話ピックアップの展開の確認</a></p></td>
</tr>
</tbody>
</table>

