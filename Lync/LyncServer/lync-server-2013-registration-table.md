---
title: 'Lync Server 2013: Registration テーブル'
TOCTitle: Registration テーブル
ms:assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398114(v=OCS.15)
ms:contentKeyID: 48271131
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の Registration テーブル

 

_**トピックの最終更新日:** 2015-03-09_

各レコードは 1 つのユーザー登録イベントを表します。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>データ型</th>
<th>キー/インデックス</th>
<th>詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>主/プライマリ、外部</p></td>
<td><p>セッション要求の時間。<strong>SessionIdSeq</strong> と合わせて使用して、セッションを一意に識別します。詳細については、「<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 の Dialogs テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ、外部</p></td>
<td><p>セッションを識別するための ID 番号。セッションを一意に識別するために <strong>SessionIdTime</strong> と併用されます。詳細については、「<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 の Dialogs テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>ユーザー ID。詳細については「<a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>EndpointId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p></p></td>
<td><p>登録エンドポイントを識別するための GUID。通常、同じユーザーの同じコンピューターからの登録イベントは、同じエンドポイント ID になります。コンピューターが異なると、エンドポイント ID も異なります。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndpointEra</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td><p></p></td>
<td><p>同じユーザーと同じエンドポイントを含む登録を区別するために使用される ID。</p>
<p>このフィールドは Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>ClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>現在のユーザーのクライアントのバージョン。詳細については「<a href="lync-server-2013-clientversions-table.md">Lync Server 2013 の ClientVersions テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RegistrarId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>登録に使用されたレジストラー サーバーの ID。詳細については「<a href="lync-server-2013-servers-table.md">Lync Server 2013 の Servers テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>セッションが取得されたプールの ID。詳細については、「<a href="lync-server-2013-pools-table.md">Lync Server 2013 の Pools テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EdgeServerId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>登録が通過するエッジ サーバー。詳細については「<a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 の EdgeServers テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>IsInternal</strong></p></td>
<td><p>Bit</p></td>
<td><p></p></td>
<td><p>ユーザーが内部からログオンしているかどうか。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsUserServiceAvailable</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>UserService が利用できるかどうか。</p></td>
</tr>
<tr class="even">
<td><p><strong>IsPrimaryRegistrar</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>プライマリ レジストラーに対する登録かどうか。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsPrimaryRegistrarCentral</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>ユーザーが存続可能ブランチ アプライアンスに登録されているかどうかを示します。</p>
<p>このフィールドは Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>RegisterTime</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>登録日時。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeRegisterTime</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>登録解除日時。</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>登録要求の応答コード。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>登録要求の診断 ID。その診断情報の種類を示します。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>登録要求の送信元のデバイス。詳細については「<a href="lync-server-2013-devices-table.md">Lync Server 2013 の Devices テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeRegisterTypeId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>外部</p></td>
<td><p>登録解除の理由 (&quot;ユーザー開始済み&quot;、&quot;登録期限切れ&quot;、&quot;クライアント障害&quot; など)。詳細については「<a href="lync-server-2013-deregistertype-table.md">Lync Server 2013 の DeRegisterType テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>IPAddress</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p></p></td>
<td><p>ユーザーが登録されているエンドポイントの IP アドレス。IPv4 アドレスまたは IPv6 アドレスのどちらかになります。</p>
<p>このフィールドは Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
</tbody>
</table>

