---
title: 'Lync Server 2013: Grant-CsOUPermission によって行われた変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by Grant-CsOUPermission
ms:assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205310(v=OCS.15)
ms:contentKeyID: 48185564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c64c11ba999763a44105a68502e53fc4889af305
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151177"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a>Lync Server 2013 での付与-CsOUPermission による変更

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-06-20_

Lync Server 2013 の管理を委任するには、指定された組織単位 (Ou) にアクセス許可を追加して、フォレストの準備によって作成された RTC ユニバーサルグループのメンバーが Domain Admins グループのメンバーにならずに Ou にアクセスできるようにします。

**Grant-CsOuPermission** コマンドレットは、次の表で指定されているように、指定された OU 内のオブジェクトへのアクセス許可を付与します。

<div>

## <a name="granting-permission-for-user-objects"></a>ユーザー オブジェクトに対するアクセス許可の付与

OU 上のユーザー オブジェクトに対して **Grant-CsOuPermission** コマンドレットを実行すると、次の表で示すように、グループにアクセス許可が付与されます。

### <a name="permissions-granted-for-user-objects"></a>ユーザー オブジェクトに対して付与されるアクセス許可

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Group</th>
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


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a>コンピューター オブジェクトに対するアクセス許可の付与

OU 上のコンピューター オブジェクトに対して **Grant-CsOuPermission** コマンドレットを実行すると、次の表で示すように、グループにアクセス許可が付与されます。

### <a name="permissions-granted-for-computer-objects"></a>コンピューター オブジェクトに対して付与されるアクセス許可

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Group</th>
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


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a>連絡先または AppContact オブジェクトに対するアクセス許可の付与

OU 上の連絡先オブジェクトまたは AppContact オブジェクトに対して **Grant-CsOuPermission** コマンドレットを実行すると、次の表で示すように、グループにアクセス許可が付与されます。

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a>連絡先または AppContact オブジェクトに対して付与されるアクセス許可

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Group</th>
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


</div>

<div>

## <a name="granting-permission-for-device-objects"></a>デバイス オブジェクトに対するアクセス許可の付与

OU 上のデバイス オブジェクトに対して **Grant-CsOuPermission** コマンドレットを実行すると、次の表で示すように、グループにアクセス許可が付与されます。

### <a name="permissions-granted-for-device-objects"></a>デバイス オブジェクトに対して付与されるアクセス許可

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Group</th>
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


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a>InetOrgPerson オブジェクトに対するアクセス許可の付与

OU 上の InetOrgPerson オブジェクトに対して **Grant-CsOuPermission** コマンドレットを実行すると、次の表で示すように、グループにアクセス許可が付与されます。

### <a name="permissions-granted-for-inetorgperson-objects"></a>InetOrgPerson オブジェクトに対して付与されるアクセス許可

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Group</th>
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


</div>

</div>

<span> </span>

</div>

</div>

</div>

