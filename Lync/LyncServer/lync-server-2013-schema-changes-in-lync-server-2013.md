---
title: 'Lync Server 2013: Lync Server 2013 でのスキーマの変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Schema changes in Lync Server 2013
ms:assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398944(v=OCS.15)
ms:contentKeyID: 48185575
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bbe1c08b7d03042be2c03511103bfa4e43d39d4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822000"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-changes-in-lync-server-2013"></a>Lync Server 2013 でのスキーマの変更

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-18_

Lync Server 2013 を展開して運用する前に、スキーマを拡張して Active Directory ドメインサービスを準備する必要があります。 スキーマ拡張は、Lync Server 2013 に必要なクラスと属性を追加します。

Lync Server 2013 には、いくつかの新しいクラスと属性が必要です。また、既存のクラスと属性もいくつか変更する必要があります。 さらに、Lync Server 2013 の多くの構成情報は、以前のバージョンと同じように、AD DS ではなく中央管理ストアに保存されています。 次の情報は、引き続き Lync Server 2013 の AD DS に保存されています。

  - **スキーマの拡張機能**:
    
      - ユーザー オブジェクトの拡張
    
      - サポートされている以前のバージョンとの下位互換性を維持するための Office Communications Server 2007 と Office Communications Server 2007 R2 のクラスの拡張機能

<!-- end list -->

  - **データ**(Lync Server 拡張スキーマと既存のスキーマクラスに保存されています):
    
      - ユーザー SIP の Uniform Resource Identifier (URI) とその他のユーザー設定
    
      - 返信グループ、会議アテンダントなどのアプリケーションの連絡先オブジェクト
    
      - 中央管理ストアへのポインター
    
      - Kerberos 認証アカウント (オプションのコンピューターオブジェクト)

このトピックでは、Lync Server 2013 で必要な Active Directory スキーマの変更について説明します。 以前のバージョンの Office Communications Server によって導入されたスキーマの変更については説明しません。 クラスとその説明の一覧については、「 [Lync Server 2013 のスキーマクラスと説明](lync-server-2013-schema-classes-and-descriptions.md)」を参照してください。 属性とその説明の一覧については、「 [Lync Server 2013 のスキーマ属性と説明](lync-server-2013-schema-attributes-and-descriptions.md)」を参照してください。 属性が含まれている可能性のあるクラスのリストについては、「 [Lync Server 2013 でのスキーマの属性](lync-server-2013-schema-attributes-by-class.md)」を参照してください。

Msrtcsip-userenabled true プレフィックスは、Lync Server に固有のクラスと属性を指定します。

<div>

## <a name="new-active-directory-attributes"></a>新しい Active Directory の属性

次の表では、Lync Server 2013 によって追加される Active Directory の属性について説明します。

### <a name="attributes-added-by-lync-server-2013"></a>Lync Server 2013 によって追加された属性

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
<td><p>このマルチバリュー属性は、ユーザーに適用される保留ポリシーの識別子を保持します。 保留ポリシーは、保留中のユーザーのメールボックスアイテムを保持します。 この属性は Exchange 2013 と共有されます。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-UserRoutingGroupId</p></td>
<td><p>これは、SIP ルーティンググループの ID です。 同じグループ内のユーザーは、同じフロントエンドサーバーに登録されます。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-MirrorBackEndServer</p></td>
<td><p>この属性は、フロントエンドプールによって使用されるミラー化された SQL Server バックエンドを格納するために使用されます。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="modified-active-directory-classes"></a>変更された Active Directory クラス

次の表では、Lync Server 2013 によって変更される Active Directory クラスについて説明します。

### <a name="classes-modified-by-lync-server-2013"></a>Lync Server 2013 によって変更されたクラス

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
<th>Class または Attribute</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ユーザー</p></td>
<td><p>追加: 指定した値を含む</p>
<p>追加: 指定した値を含む</p></td>
<td><p>ProxyAddresses</p>
<p>Msrtcsip-userenabled true-UserRoutingGroupId</p></td>
</tr>
<tr class="even">
<td><p>問い合わせ</p></td>
<td><p>追加: 指定した値を含む</p>
<p>追加: 指定した値を含む</p></td>
<td><p>ProxyAddresses</p>
<p>Msrtcsip-userenabled true-UserRoutingGroupId</p></td>
</tr>
<tr class="odd">
<td><p>メール受信者</p></td>
<td><p>追加: 指定した値を含む</p></td>
<td><p>msExchUserHoldPolicies</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-GlobalTopologySetting</p></td>
<td><p>追加: 指定した値を含む</p></td>
<td><p>Msrtcsip-userenabled true-MirrorBackEndServer</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

