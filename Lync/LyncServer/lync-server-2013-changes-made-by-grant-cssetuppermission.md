---
title: 'Lync Server 2013: Grant-CsSetupPermission によって行われた変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by Grant-CsSetupPermission
ms:assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205250(v=OCS.15)
ms:contentKeyID: 48185360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12c9431e413428080f72d34510cdb3879e26e7cf
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151016"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a>Lync Server 2013 で付与-CsSetupPermission によって加えられた変更

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-06-20_

セットアップを委任するには、特定の Active Directory 組織単位 (OU) の RTCUniversalServerAdmins ユニバーサルグループに対するアクセス許可を付与します。この 2013 OU の RTCUniversalServerAdmins グループのメンバーは、指定されたdomain Admins グループのメンバーではないドメイン。

**Grant-CsSetupPermission** コマンドレットは、次の表で指定されているように、RTCUniversalServerAdmins グループに OU に対するアクセス許可を付与します。

### <a name="permissions-granted-to-objects-in-the-ou"></a>OU 内のオブジェクトに対して付与されるアクセス許可

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


</div>

<span> </span>

</div>

</div>

</div>

