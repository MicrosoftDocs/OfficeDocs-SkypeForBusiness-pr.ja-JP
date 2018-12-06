---
title: Lync Server 2013 での Grant-CsSetupPermission によって行われる変更
TOCTitle: Lync Server 2013 での Grant-CsSetupPermission によって行われる変更
ms:assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205250(v=OCS.15)
ms:contentKeyID: 48273514
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での Grant-CsSetupPermission によって行われる変更

 

_**トピックの最終更新日:** 2015-03-09_

セットアップを委任するには、特定の Active Directory 組織単位 (OU) の RTCUniversalServerAdmins ユニバーサル グループにアクセス許可を付与できます。これにより、その OU の RTCUniversalServerAdmins グループのメンバーは、Domain Admins グループのメンバーでなくても、指定されたドメインで Lync Server 2013 をインストールできます。

**Grant-CsSetupPermission** コマンドレットは、次の表で指定されているように、RTCUniversalServerAdmins グループに OU に対するアクセス許可を付与します。

### OU 内のオブジェクトに対して付与されるアクセス許可

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>アクセス許可の適用先:</th>
<th>付与されるアクセス許可:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCUniversalServerAdmins</p></td>
<td><p>特別なアクセス権:</p>
<ul>
<li><p>servicePrincipalName の読み込み</p></li>
<li><p>servicePrincipalName の書き込み</p></li>
<li><p>ツリーの削除</p></li>
<li><p>ディレクトリ変更のレプリケート</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>子の serviceConnectionPoint オブジェクト</p></td>
<td><p>特別なアクセス権:</p>
<ul>
<li><p>アクセス許可の読み取り</p></li>
<li><p>アクセス許可の書き込み</p></li>
<li><p>子の作成</p></li>
<li><p>子の削除</p></li>
<li><p>内容の一覧表示</p></li>
<li><p>プロパティの書き込み</p></li>
<li><p>プロパティの読み取り</p></li>
<li><p>ツリーの削除</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>子の msRTCSIP-Server オブジェクト</p></td>
<td><p>特別なアクセス権:</p>
<ul>
<li><p>プロパティの書き込み</p></li>
<li><p>プロパティの読み取り</p></li>
<li><p>ツリーの削除</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>子の msRTCSIP-WebComponents オブジェクト</p></td>
<td><p>特別なアクセス権:</p>
<ul>
<li><p>プロパティの書き込み</p></li>
<li><p>プロパティの読み取り</p></li>
<li><p>ツリーの削除</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>子の msRTCSIP-MCU オブジェクト</p></td>
<td><p>特別なアクセス権:</p>
<ul>
<li><p>プロパティの書き込み</p></li>
<li><p>プロパティの読み取り</p></li>
<li><p>ツリーの削除</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>子の msRTCSIP-MediationServer オブジェクト</p></td>
<td><p>特別なアクセス権:</p>
<ul>
<li><p>プロパティの書き込み</p></li>
<li><p>プロパティの読み取り</p></li>
<li><p>ツリーの削除</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>子の msRTCSIP-ApplicationServer オブジェクト</p></td>
<td><p>特別なアクセス権:</p>
<ul>
<li><p>プロパティの書き込み</p></li>
<li><p>プロパティの読み取り</p></li>
<li><p>ツリーの削除</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>子の msRTCSIP-ConnectionPoint オブジェクト</p></td>
<td><p>特別なアクセス権:</p>
<ul>
<li><p>プロパティの書き込み</p></li>
<li><p>プロパティの読み取り</p></li>
<li><p>ツリーの削除</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>子のコンピューター オブジェクト</p></td>
<td><p>serviceConnectionPoint に対する特別なアクセス:</p>
<ul>
<li><p>子オブジェクトの作成</p></li>
<li><p>子オブジェクトの削除</p></li>
<li><p>ツリーの削除</p></li>
</ul>
<p>パブリック情報に対する特別なアクセス:</p>
<ul>
<li><p>プロパティの読み取り</p></li>
</ul>
<p>DNS ホスト名に対する特別なアクセス:</p>
<ul>
<li><p>プロパティの読み取り</p></li>
</ul></td>
</tr>
</tbody>
</table>

