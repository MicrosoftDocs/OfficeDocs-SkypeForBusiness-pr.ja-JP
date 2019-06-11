---
title: 'Lync Server 2013: Grant-CsSetupPermission による変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changes made by Grant-CsSetupPermission
ms:assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205250(v=OCS.15)
ms:contentKeyID: 48185360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc63cf814f2bd901ab9753fe0f4501e7f44e2189
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840593"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a>Lync Server 2013 での権限の付与によって行われる変更

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-06-20_

設定を委任するには、特定の Active Directory 組織単位 (OU) に対して RTCUniversalServerAdmins ユニバーサルグループへのアクセス許可を付与し、その OU の RTCUniversalServerAdmins グループのメンバーが指定した Lync Server 2013 をインストールできるようにすることができます。domain Admins グループのメンバーになりません。

**グラント setuppermissions**コマンドレットは、次の表で指定されているように、OU に対して RTCUniversalServerAdmins group アクセス許可を付与します。

### <a name="permissions-granted-to-objects-in-the-ou"></a>OU 内のオブジェクトに付与されているアクセス許可

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>権限の対象:</th>
<th>付与されるアクセス許可:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCUniversalServerAdmins</p></td>
<td><p>特殊なアクセス:</p>
<ul>
<li><p>ServicePrincipalName を読み上げる</p></li>
<li><p>ServicePrincipalName の書き込み</p></li>
<li><p>ツリーの削除</p></li>
<li><p>ディレクトリの変更の複製</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>子孫の serviceConnectionPoint オブジェクト</p></td>
<td><p>特殊なアクセス:</p>
<ul>
<li><p>読み取りアクセス許可</p></li>
<li><p>書き込み権限</p></li>
<li><p>子の作成</p></li>
<li><p>子の削除</p></li>
<li><p>リストの内容</p></li>
<li><p>プロパティの書き込み</p></li>
<li><p>プロパティの読み取り</p></li>
<li><p>ツリーの削除</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>下位の Msrtcsip-userenabled true オブジェクト</p></td>
<td><p>特殊なアクセス:</p>
<ul>
<li><p>プロパティの書き込み</p></li>
<li><p>プロパティの読み取り</p></li>
<li><p>ツリーの削除</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>下位の Msrtcsip-userenabled true-WebComponents オブジェクト</p></td>
<td><p>特殊なアクセス:</p>
<ul>
<li><p>プロパティの書き込み</p></li>
<li><p>プロパティの読み取り</p></li>
<li><p>ツリーの削除</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>子孫の Msrtcsip-userenabled true-MCU オブジェクト</p></td>
<td><p>特殊なアクセス:</p>
<ul>
<li><p>プロパティの書き込み</p></li>
<li><p>プロパティの読み取り</p></li>
<li><p>ツリーの削除</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>子孫の Msrtcsip-userenabled true-MediationServer オブジェクト</p></td>
<td><p>特殊なアクセス:</p>
<ul>
<li><p>プロパティの書き込み</p></li>
<li><p>プロパティの読み取り</p></li>
<li><p>ツリーの削除</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>子 Msrtcsip-userenabled true ApplicationServer オブジェクト</p></td>
<td><p>特殊なアクセス:</p>
<ul>
<li><p>プロパティの書き込み</p></li>
<li><p>プロパティの読み取り</p></li>
<li><p>ツリーの削除</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>子 Msrtcsip-userenabled true ConnectionPoint オブジェクト</p></td>
<td><p>特殊なアクセス:</p>
<ul>
<li><p>プロパティの書き込み</p></li>
<li><p>プロパティの読み取り</p></li>
<li><p>ツリーの削除</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>子コンピューターオブジェクト</p></td>
<td><p>ServiceConnectionPoint の特殊なアクセス:</p>
<ul>
<li><p>子オブジェクトを作成する</p></li>
<li><p>子オブジェクトを削除する</p></li>
<li><p>ツリーの削除</p></li>
</ul>
<p>パブリック情報への特別なアクセス:</p>
<ul>
<li><p>プロパティの読み取り</p></li>
</ul>
<p>DNS ホスト名の特殊なアクセス:</p>
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

