---
title: 'Lync Server 2013: コール パークの展開プロセス'
TOCTitle: コール パークの展開プロセス
ms:assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398283(v=OCS.15)
ms:contentKeyID: 48271472
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 のコール パークの展開プロセス

 

_**トピックの最終更新日:** 2015-03-09_

このセクションでは、コール パーク アプリケーションの展開に含まれる手順の概要を説明します。コール パークを構成する前に、Enterprise Edition または Standard Edition を エンタープライズ VoIP と共に展開する必要があります。コール パークが必要とするコンポーネントは、エンタープライズ VoIP を展開するときにインストールされ、有効化されます。

### コール パーク展開プロセス

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
<td><p>Lync Server コントロール パネルまたは <strong>New-CSCallParkOrbit</strong> コマンドレットを使用して、コール パーク オービット テーブルでオービット範囲を作成し、コール パーク アプリケーションをホストする アプリケーション サービスと関連付けます。</p>

> [!NOTE]
> 既存のダイヤル プランとシームレスに統合するため、オービット範囲、は通常仮想の内線番号の禁止として構成されます。 コール パーク オービット テーブルでオービット番号として Direct Inward Dialing (DID) 番号を指定することは、サポートされていません。

</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-create-or-modify-a-call-park-orbit-range.md">Lync Server 2013 でのコール パーク オービット範囲の作成または変更</a></p></td>
</tr>
<tr class="even">
<td><p>コール パーク設定を構成する</p></td>
<td><p><strong>Set-CsCpsConfiguration</strong> コマンドレットを使用して、コール パーク設定を構成します。少なくとも、<strong>OnTimeoutURI</strong> オプションを構成して、パークされた通話がタイムアウトしたときに使用するフォールバック先を構成すことをお勧めします。次の設定も構成できます。</p>
<ul>
<li><p>(オプション) <strong>EnableMusicOnHold</strong> を構成して保留音を有効または無効にします。</p></li>
<li><p>(オプション) <strong>MaxCallPickupAttempts</strong> を構成して、パークされた通話が、代替 Uniform Resource Identifier (URI) に転送されるまでに、応答した電話にかけ直す回数を決定します。</p></li>
<li><p>(オプション) <strong>CallPickupTimeoutThreshold</strong> を構成して、通話がパークされてから、呼び出しに応答した電話にかけ直されるまでの経過時間を決定します。</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-call-park-settings.md">コール パーク設定の構成</a></p></td>
</tr>
<tr class="odd">
<td><p>必要に応じて、保留音をカスタマイズする</p></td>
<td><p>既定の保留音を使用しない場合は、<strong>Set-CsCallParkServiceMusicOnHoldFile</strong> コマンドを使用して、音声ファイルをカスタマイズおよびアップロードします。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-customize-call-park-music-on-hold.md">コール パーク保留音のカスタマイズ</a></p></td>
</tr>
<tr class="even">
<td><p>音声ポリシーを構成し、ユーザーに対して コール パークを有効化する</p></td>
<td><p>Lync Server コントロール パネルまたは <strong>Set-CSVoicePolicy</strong> コマンドレットと <strong>EnableCallPark</strong> オプションを使用して、音声ポリシーのユーザーに対して コール パークを有効化します。</p>

> [!NOTE]
> 既定では、コール パークはすべてのユーザーに対して無効になっています。


> [!NOTE]
> 複数の音声ポリシーが存在する場合、EnableCallPark プロパティが、既定のポリシーに対してだけでなく、それぞれの音声ポリシーに設定されているのを確認してください。

</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsUserAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-enable-call-park-for-users.md">Lync Server 2013 でのユーザーに対するコール パークの有効化</a></p></td>
</tr>
<tr class="odd">
<td><p>コール パークの正規化ルールを確認する</p></td>
<td><p>コール パーク オービットを正規化することはできません。 正規化ルールにオービット範囲が含まれていないのを確認します。 必要に応じて、オービットが正規化されるのを防ぐため、追加の正規化ルールを作成します。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verify-normalization-rules-for-call-park.md">Lync Server 2013 でのコール パーク正規化ルールの確認</a></p></td>
</tr>
<tr class="even">
<td><p>コール パーク展開を確認する</p></td>
<td><p>通話の保留と取得をテストし、構成が予想どおりに動作することを確認します。</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-call-park-deployment.md">(オプション) Lync Server 2013 でのコール パーク展開の確認</a></p></td>
</tr>
</tbody>
</table>

