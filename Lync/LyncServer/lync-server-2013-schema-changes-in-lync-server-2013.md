---
title: 'Lync Server 2013: Lync Server 2013 でのスキーマの変更'
description: 'Lync Server 2013: Lync Server 2013 でのスキーマの変更。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema changes in Lync Server 2013
ms:assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398944(v=OCS.15)
ms:contentKeyID: 48185575
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e914de48ace80fd2611f2d05b092894b11c534a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557153"
---
# <a name="schema-changes-in-lync-server-2013"></a>Lync Server 2013 でのスキーマの変更

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-18_

Lync Server 2013 を展開して運用する前に、スキーマを拡張して Active Directory ドメインサービスを準備する必要があります。 スキーマ拡張機能は、Lync Server 2013 で必要なクラスと属性を追加します。

Lync Server 2013 には、いくつかの新しいクラスと属性が必要であり、一部の既存のクラスおよび属性が変更されています。 さらに、Lync Server 2013 の構成情報の多くは、以前のバージョンとは異なる方法で AD DS ではなく中央管理ストアに格納されます。 次の情報は、引き続き Lync Server 2013 の AD DS に保存されています。

  - **スキーマ拡張**:
    
      - ユーザー オブジェクトの拡張
    
      - サポートされている以前のバージョンとの下位互換性を維持するための Office Communications Server 2007 および Office Communications Server 2007 R2 クラスの拡張機能

<!-- end list -->

  - **データ** (Lync Server 拡張スキーマおよび既存のスキーマクラスに格納されている):
    
      - ユーザーの SIP URI (Uniform Resource Identifier) と他のユーザー設定
    
      - リソース グループ、会議アテンダントなどのアプリケーションの連絡先オブジェクト
    
      - 中央管理ストアへのポインター
    
      - Kerberos 認証のアカウント (オプションのコンピューター オブジェクト)

このトピックでは、Lync Server 2013 で必要な Active Directory スキーマの変更について説明します。 以前のバージョンの Office Communications Server で導入されたスキーマの変更については説明しません。 クラスとその説明の一覧については、「 [Lync Server 2013 のスキーマクラスと説明](lync-server-2013-schema-classes-and-descriptions.md)」を参照してください。 属性とその説明の一覧については、「 [Lync Server 2013 のスキーマの属性と説明](lync-server-2013-schema-attributes-and-descriptions.md)」を参照してください。 含まれる可能性のある属性を持つクラスの一覧については、「 [Lync Server 2013 のクラス別スキーマの属性](lync-server-2013-schema-attributes-by-class.md)」を参照してください。

MsRTCSIP プレフィックスは、Lync Server に固有のクラスと属性を識別します。

<div>

## <a name="new-active-directory-attributes"></a>新規 Active Directory 属性

次の表に、Lync Server 2013 によって追加される Active Directory 属性を示します。

### <a name="attributes-added-by-lync-server-2013"></a>Lync Server 2013 によって追加される属性

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>属性</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>msExchUserHoldPolicies</p></td>
<td><p>この複数値の属性には、ユーザーに適用される保持ポリシーの識別子が保持されます。 この保持の間は、ユーザーのメールボックス アイテムが保持ポリシーに保存されます。 この属性は、Exchange 2013 と共有されます。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserRoutingGroupId</p></td>
<td><p>SIP ルーティング グループ ID。同じグループのユーザーは、同じフロントエンド サーバーに登録します。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MirrorBackEndServer</p></td>
<td><p>この属性は、フロントエンドプールで使用されるミラーリングされた SQL Server バックエンドを格納するために使用されます。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="modified-active-directory-classes"></a>変更された Active Directory クラス

次の表では、Lync Server 2013 によって変更された Active Directory クラスについて説明します。

### <a name="classes-modified-by-lync-server-2013"></a>Lync Server 2013 によって変更されるクラス

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>クラス</th>
<th>変更</th>
<th>クラスまたは属性</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>User</p></td>
<td><p>add: mayContain</p>
<p>add: mayContain</p></td>
<td><p>ProxyAddresses</p>
<p>msRTCSIP-UserRoutingGroupId</p></td>
</tr>
<tr class="even">
<td><p>Contact</p></td>
<td><p>add: mayContain</p>
<p>add: mayContain</p></td>
<td><p>ProxyAddresses</p>
<p>msRTCSIP-UserRoutingGroupId</p></td>
</tr>
<tr class="odd">
<td><p>Mail-Recipient</p></td>
<td><p>add:mayContain</p></td>
<td><p>msExchUserHoldPolicies</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalTopologySetting</p></td>
<td><p>add: mayContain</p></td>
<td><p>msRTCSIP-MirrorBackEndServer</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

