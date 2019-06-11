---
title: 'Lync Server 2013: アクセス許可によって行われた変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changes made by Grant-CsOUPermission
ms:assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205310(v=OCS.15)
ms:contentKeyID: 48185564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ce6b16dff48afeeec848024d763655695905008
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840604"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a>Lync Server 2013 のアクセス許可によって行われた変更

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-06-20_

Lync Server 2013 管理を委任するために、フォレストの準備によって作成された RTC ユニバーサルグループのメンバーが、Domain Admins グループのメンバーにならずに Ou にアクセスできるように、指定された組織単位 (Ou) にアクセス許可を追加できます。

**Grant-CsOuPermission**コマンドレットは、次の表に示すように、指定した OU 内のオブジェクトへのアクセス許可を付与します。

<div>

## <a name="granting-permission-for-user-objects"></a>ユーザーオブジェクトのアクセス許可の付与

OU 上のユーザーオブジェクトに対して**Grant-CsOuPermission**コマンドレットを実行すると、次の表に示すように、グループにアクセス許可が付与されます。

### <a name="permissions-granted-for-user-objects"></a>ユーザーオブジェクトに付与される権限

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>化</th>
<th>アクセス許可</th>
<th>適用対象</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>ディレクトリの変更の複製</p></td>
<td><p>このオブジェクトのみ</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>リストの内容</p>
<p>すべてのプロパティを読み上げる</p>
<p>読み取りアクセス許可</p></td>
<td><p>このオブジェクトのみ</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>リストの内容</p>
<p>すべてのプロパティを読み上げる</p>
<p>読み取りアクセス許可</p></td>
<td><p>このオブジェクトのみ</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>RTCUserSearchPropertySet を読む</p>
<p>RTCUserProvisioningPropertySet を読む</p>
<p>RTCPropertySet を読む</p>
<p>公開-情報を読む</p>
<p>一般的な情報を読む-情報</p>
<p>ユーザーアカウントの制限を読む</p></td>
<td><p>子孫のユーザーオブジェクト</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>RTCUserSearchPropertySet の書き込み</p>
<p>MsExchUCVoiceMailSettings の書き込み</p>
<p>RTCUserProvisioningPropertySet の書き込み</p>
<p>RTCPropertySet の書き込み</p>
<p>ProxyAddresses の書き込み</p></td>
<td><p>子孫のユーザーオブジェクト</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a>コンピューターオブジェクトへのアクセス許可の付与

OU 上のコンピューターオブジェクトに対して**Grant-CsOuPermission**コマンドレットを実行すると、次の表に示すように、グループにアクセス許可が付与されます。

### <a name="permissions-granted-for-computer-objects"></a>コンピューターオブジェクトに付与される権限

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>化</th>
<th>アクセス許可</th>
<th>適用対象</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>ディレクトリの変更の複製</p></td>
<td><p>このオブジェクトのみ</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>リストの内容</p>
<p>すべてのプロパティを読み上げる</p>
<p>読み取りアクセス許可</p></td>
<td><p>このオブジェクトのみ</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>リストの内容</p>
<p>すべてのプロパティを読み上げる</p>
<p>読み取りアクセス許可</p></td>
<td><p>このオブジェクトのみ</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>公開-情報を読む</p>
<p>読み取り済みの DNS ホスト名</p></td>
<td><p>子コンピューターオブジェクト</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>公開-情報を読む</p>
<p>読み取り済みの DNS ホスト名</p></td>
<td><p>子コンピューターオブジェクト</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a>Contact オブジェクトまたは AppContact オブジェクトのアクセス許可を付与する

組織内の連絡先オブジェクトまたは AppContact オブジェクトに対して**Grant-CsOuPermission**コマンドレットを実行すると、次の表に示すように、グループにアクセス許可が付与されます。

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a>Contact オブジェクトまたは AppContact オブジェクトに付与されているアクセス許可

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>化</th>
<th>アクセス許可</th>
<th>適用対象</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>ディレクトリの変更の複製</p></td>
<td><p>このオブジェクトのみ</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>リストの内容</p>
<p>すべてのプロパティを読み上げる</p>
<p>読み取りアクセス許可</p></td>
<td><p>このオブジェクトのみ</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>リストの内容</p>
<p>すべてのプロパティを読み上げる</p>
<p>読み取りアクセス許可</p></td>
<td><p>このオブジェクトのみ</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>RTCUserSearchPropertySet を読む</p>
<p>RTCUserProvisioningPropertySet を読む</p>
<p>RTCPropertySet を読む</p>
<p>公開-情報を読む</p>
<p>一般的な情報を読む-情報</p>
<p>個人情報を読む</p>
<p>ユーザーアカウントの制限を読む</p></td>
<td><p>子孫の連絡先オブジェクト</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>RTCUserSearchPropertySet の書き込み</p>
<p>他の Ip電話を書く</p>
<p>DisplayName を書く</p>
<p>説明の書き込み</p>
<p>TelephoneNumber の書き込み</p>
<p>MsExchUCVoiceMailSettings の書き込み</p>
<p>RTCUserProvisioningPropertySet の書き込み</p>
<p>RTCPropertySet の書き込み</p>
<p>ProxyAddresses の書き込み</p></td>
<td><p>子孫の連絡先オブジェクト</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a>デバイスオブジェクトのアクセス許可の付与

OU 上のデバイスオブジェクトに対して**Grant-CsOuPermission**コマンドレットを実行すると、次の表に示すように、グループにアクセス許可が付与されます。

### <a name="permissions-granted-for-device-objects"></a>デバイスオブジェクトに付与されるアクセス許可

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>化</th>
<th>アクセス許可</th>
<th>適用対象</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>ディレクトリの変更の複製</p></td>
<td><p>このオブジェクトのみ</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>リストの内容</p>
<p>すべてのプロパティを読み上げる</p>
<p>読み取りアクセス許可</p></td>
<td><p>このオブジェクトのみ</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>リストの内容</p>
<p>すべてのプロパティを読み上げる</p>
<p>読み取りアクセス許可</p></td>
<td><p>このオブジェクトのみ</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>RTCUserSearchPropertySet を読む</p>
<p>RTCUserProvisioningPropertySet を読む</p>
<p>RTCPropertySet を読む</p>
<p>公開-情報を読む</p>
<p>個人情報を読む</p>
<p>一般的な情報を読む-情報</p>
<p>ユーザーアカウントの制限を読む</p></td>
<td><p>子孫の連絡先オブジェクト</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>子の作成</p>
<p>子の削除</p>
<p>ツリーの削除</p></td>
<td><p>問い合わせ</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>DisplayName を書く</p>
<p>説明の書き込み</p>
<p>TelephoneNumber の書き込み</p></td>
<td><p>子孫のユーザーオブジェクト</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>RTCUserSearchPropertySet の書き込み</p>
<p>他の Ip電話を書く</p>
<p>DisplayName を書く</p>
<p>説明の書き込み</p>
<p>TelephoneNumber の書き込み</p>
<p>MsExchUCVoiceMailSettings の書き込み</p>
<p>RTCUserProvisioningPropertySet の書き込み</p>
<p>RTCPropertySet の書き込み</p>
<p>ProxyAddresses の書き込み</p></td>
<td><p>子孫の連絡先オブジェクト</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a>InetOrgPerson オブジェクトのアクセス許可を付与する

OU 上の InetOrgPerson オブジェクトに対して**Grant-CsOuPermission**コマンドレットを実行すると、次の表に示すように、グループにアクセス許可が付与されます。

### <a name="permissions-granted-for-inetorgperson-objects"></a>InetOrgPerson オブジェクトに対して付与されるアクセス許可

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>化</th>
<th>アクセス許可</th>
<th>適用対象</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>ディレクトリの変更の複製</p></td>
<td><p>このオブジェクトのみ</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>リストの内容</p>
<p>すべてのプロパティを読み上げる</p>
<p>読み取りアクセス許可</p></td>
<td><p>このオブジェクトのみ</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>リストの内容</p>
<p>すべてのプロパティを読み上げる</p>
<p>読み取りアクセス許可</p></td>
<td><p>このオブジェクトのみ</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>RTCUserSearchPropertySet を読む</p>
<p>RTCUserProvisioningPropertySet を読む</p>
<p>RTCPropertySet を読む</p>
<p>個人情報を読む</p>
<p>公開-情報を読む</p>
<p>一般的な情報を読む-情報</p>
<p>ユーザーアカウントの制限を読む</p></td>
<td><p>子の inetOrgPerson オブジェクト</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>RTCUserSearchPropertySet の書き込み</p>
<p>RTCUserProvisioningPropertySet の書き込み</p>
<p>RTCPropertySet の書き込み</p>
<p>ProxyAddresses の書き込み</p></td>
<td><p>子の inetOrgPerson オブジェクト</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

