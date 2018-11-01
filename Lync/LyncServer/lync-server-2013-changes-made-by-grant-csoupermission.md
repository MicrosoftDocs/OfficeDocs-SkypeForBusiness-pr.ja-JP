---
title: Lync Server 2013 での Grant-CsOUPermission によって行われる変更
TOCTitle: Lync Server 2013 での Grant-CsOUPermission によって行われる変更
ms:assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205310(v=OCS.15)
ms:contentKeyID: 48273793
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での Grant-CsOUPermission によって行われる変更

 

_**トピックの最終更新日:** 2015-03-09_

Lync Server 2013 の管理を委任する場合は、指定された組織単位 (OU) にアクセス許可を追加することで、フォレストの準備によって作成された RTC ユニバーサル グループのメンバーは、Domain Admins グループのメンバーでなくてもその OU にアクセスできます。

**Grant-CsOuPermission** コマンドレットは、次の表で指定されているように、指定された OU 内のオブジェクトへのアクセス許可を付与します。

## ユーザー オブジェクトに対するアクセス許可の付与

OU 上のユーザー オブジェクトに対して **Grant-CsOuPermission** コマンドレットを実行すると、次の表で示すように、グループにアクセス許可が付与されます。

### ユーザー オブジェクトに対して付与されるアクセス許可

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>グループ</th>
<th>アクセス許可</th>
<th>適用対象</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>ディレクトリ変更のレプリケート</p></td>
<td><p>このオブジェクトのみ</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>内容の一覧表示</p>
<p>すべてのプロパティの読み取り</p>
<p>アクセス許可の読み取り</p></td>
<td><p>このオブジェクトのみ</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>内容の一覧表示</p>
<p>すべてのプロパティの読み取り</p>
<p>アクセス許可の読み取り</p></td>
<td><p>このオブジェクトのみ</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>RTCUserSearchPropertySet の読み取り</p>
<p>RTCUserProvisioningPropertySet の読み取り</p>
<p>RTCPropertySet の読み取り</p>
<p>Public-Information の読み取り</p>
<p>General-Information の読み取り</p>
<p>User-Account-Restrictions の読み取り</p></td>
<td><p>子ユーザー オブジェクト</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>RTCUserSearchPropertySet の書き込み</p>
<p>msExchUCVoiceMailSettings の書き込み</p>
<p>RTCUserProvisioningPropertySet の書き込み</p>
<p>RTCPropertySet の書き込み</p>
<p>proxyAddresses の書き込み</p></td>
<td><p>子ユーザー オブジェクト</p></td>
</tr>
</tbody>
</table>


## コンピューター オブジェクトに対するアクセス許可の付与

OU 上のコンピューター オブジェクトに対して **Grant-CsOuPermission** コマンドレットを実行すると、次の表で示すように、グループにアクセス許可が付与されます。

### コンピューター オブジェクトに対して付与されるアクセス許可

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>グループ</th>
<th>アクセス許可</th>
<th>適用対象</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>ディレクトリ変更のレプリケート</p></td>
<td><p>このオブジェクトのみ</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>内容の一覧表示</p>
<p>すべてのプロパティの読み取り</p>
<p>アクセス許可の読み取り</p></td>
<td><p>このオブジェクトのみ</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>内容の一覧表示</p>
<p>すべてのプロパティの読み取り</p>
<p>アクセス許可の読み取り</p></td>
<td><p>このオブジェクトのみ</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Public-Information の読み取り</p>
<p>Validated-DNS-Host-Name の読み取り</p></td>
<td><p>子のコンピューター オブジェクト</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Public-Information の読み取り</p>
<p>Validated-DNS-Host-Name の読み取り</p></td>
<td><p>子のコンピューター オブジェクト</p></td>
</tr>
</tbody>
</table>


## 連絡先または AppContact オブジェクトに対するアクセス許可の付与

OU 上の連絡先オブジェクトまたは AppContact オブジェクトに対して **Grant-CsOuPermission** コマンドレットを実行すると、次の表で示すように、グループにアクセス許可が付与されます。

### 連絡先または AppContact オブジェクトに対して付与されるアクセス許可

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>グループ</th>
<th>アクセス許可</th>
<th>適用対象</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>ディレクトリ変更のレプリケート</p></td>
<td><p>このオブジェクトのみ</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>内容の一覧表示</p>
<p>すべてのプロパティの読み取り</p>
<p>アクセス許可の読み取り</p></td>
<td><p>このオブジェクトのみ</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>内容の一覧表示</p>
<p>すべてのプロパティの読み取り</p>
<p>アクセス許可の読み取り</p></td>
<td><p>このオブジェクトのみ</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>RTCUserSearchPropertySet の読み取り</p>
<p>RTCUserProvisioningPropertySet の読み取り</p>
<p>RTCPropertySet の読み取り</p>
<p>Public-Information の読み取り</p>
<p>General-Information の読み取り</p>
<p>Personal-Information の読み取り</p>
<p>User-Account-Restrictions の読み取り</p></td>
<td><p>子連絡先オブジェクト</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>RTCUserSearchPropertySet の書き込み</p>
<p>otherIpPhone の書き込み</p>
<p>displayName の書き込み</p>
<p>description の書き込み</p>
<p>telephoneNumber の書き込み</p>
<p>msExchUCVoiceMailSettings の書き込み</p>
<p>RTCUserProvisioningPropertySet の書き込み</p>
<p>RTCPropertySet の書き込み</p>
<p>proxyAddresses の書き込み</p></td>
<td><p>子連絡先オブジェクト</p></td>
</tr>
</tbody>
</table>


## デバイス オブジェクトに対するアクセス許可の付与

OU 上のデバイス オブジェクトに対して **Grant-CsOuPermission** コマンドレットを実行すると、次の表で示すように、グループにアクセス許可が付与されます。

### デバイス オブジェクトに対して付与されるアクセス許可

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>グループ</th>
<th>アクセス許可</th>
<th>適用対象</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>ディレクトリ変更のレプリケート</p></td>
<td><p>このオブジェクトのみ</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>内容の一覧表示</p>
<p>すべてのプロパティの読み取り</p>
<p>アクセス許可の読み取り</p></td>
<td><p>このオブジェクトのみ</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>内容の一覧表示</p>
<p>すべてのプロパティの読み取り</p>
<p>アクセス許可の読み取り</p></td>
<td><p>このオブジェクトのみ</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>RTCUserSearchPropertySet の読み取り</p>
<p>RTCUserProvisioningPropertySet の読み取り</p>
<p>RTCPropertySet の読み取り</p>
<p>Public-Information の読み取り</p>
<p>Personal-Information の読み取り</p>
<p>General-Information の読み取り</p>
<p>User-Account-Restrictions の読み取り</p></td>
<td><p>子連絡先オブジェクト</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>子の作成</p>
<p>子の削除</p>
<p>ツリーの削除</p></td>
<td><p>連絡先</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>displayName の書き込み</p>
<p>description の書き込み</p>
<p>telephoneNumber の書き込み</p></td>
<td><p>子ユーザー オブジェクト</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>RTCUserSearchPropertySet の書き込み</p>
<p>otherIpPhone の書き込み</p>
<p>displayName の書き込み</p>
<p>description の書き込み</p>
<p>telephoneNumber の書き込み</p>
<p>msExchUCVoiceMailSettings の書き込み</p>
<p>RTCUserProvisioningPropertySet の書き込み</p>
<p>RTCPropertySet の書き込み</p>
<p>proxyAddresses の書き込み</p></td>
<td><p>子連絡先オブジェクト</p></td>
</tr>
</tbody>
</table>


## InetOrgPerson オブジェクトに対するアクセス許可の付与

OU 上の InetOrgPerson オブジェクトに対して **Grant-CsOuPermission** コマンドレットを実行すると、次の表で示すように、グループにアクセス許可が付与されます。

### InetOrgPerson オブジェクトに対して付与されるアクセス許可

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>グループ</th>
<th>アクセス許可</th>
<th>適用対象</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>ディレクトリ変更のレプリケート</p></td>
<td><p>このオブジェクトのみ</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>内容の一覧表示</p>
<p>すべてのプロパティの読み取り</p>
<p>アクセス許可の読み取り</p></td>
<td><p>このオブジェクトのみ</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>内容の一覧表示</p>
<p>すべてのプロパティの読み取り</p>
<p>アクセス許可の読み取り</p></td>
<td><p>このオブジェクトのみ</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>RTCUserSearchPropertySet の読み取り</p>
<p>RTCUserProvisioningPropertySet の読み取り</p>
<p>RTCPropertySet の読み取り</p>
<p>Personal-Information の読み取り</p>
<p>Public-Information の読み取り</p>
<p>General-Information の読み取り</p>
<p>User-Account-Restrictions の読み取り</p></td>
<td><p>子 inetOrgPerson オブジェクト</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>RTCUserSearchPropertySet の書き込み</p>
<p>RTCUserProvisioningPropertySet の書き込み</p>
<p>RTCPropertySet の書き込み</p>
<p>proxyAddresses の書き込み</p></td>
<td><p>子 inetOrgPerson オブジェクト</p></td>
</tr>
</tbody>
</table>

