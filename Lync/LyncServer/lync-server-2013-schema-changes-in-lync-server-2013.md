---
title: Lync Server 2013 のスキーマの変更
TOCTitle: Lync Server 2013 のスキーマの変更
ms:assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398944(v=OCS.15)
ms:contentKeyID: 48273791
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 のスキーマの変更

 

_**トピックの最終更新日:** 2015-03-09_

Lync Server 2013 を展開して稼動させる前に、スキーマを拡張して Active Directory ドメイン サービス を準備する必要があります。 スキーマを拡張することにより、Lync Server 2013 に必要なクラスと属性を追加します。

Lync Server 2013 では、いくつかの新規クラスと属性が必要となり、一部の既存クラスと属性が変更されます。 また、Lync Server 2013 のほとんどの構成情報は、以前のバージョンで構成情報が格納されていた AD DS ではなく、中央管理ストアに格納されています。 以下の情報は、現在も Lync Server 2013 の AD DS に格納されています。

  - **スキーマ拡張**:
    
      - ユーザー オブジェクトの拡張
    
      - 以前のサポートされるバージョンとの下位互換性を確保するための Office Communications Server 2007 クラスと Office Communications Server 2007 R2 クラスの拡張

<!-- end list -->

  - **データ** (Lync Server 拡張スキーマ クラスと既存のスキーマ クラスに保存):
    
      - ユーザーの SIP URI (Uniform Resource Identifier) と他のユーザー設定
    
      - リソース グループや会議アテンダントなどのアプリケーションの連絡先オブジェクト
    
      - 中央管理ストアへのポインター
    
      - Kerberos 認証のアカウント (オプションのコンピューター オブジェクト)

このトピックでは、Lync Server 2013 に必要な Active Directory スキーマの変更について説明します。Office Communications Server の以前のバージョンで導入されたスキーマの変更については説明しません。 クラスとその説明の一覧については、「[Lync Server 2013 でのスキーマのクラスと説明](lync-server-2013-schema-classes-and-descriptions.md)」を参照してください。 属性とその説明の一覧については、「[Lync Server 2013 でのスキーマの属性と説明](lync-server-2013-schema-attributes-and-descriptions.md)」を参照してください。 クラスおよびクラスに含まれる可能性のある属性の一覧については、「[Lync Server 2013 でのクラスごとのスキーマの属性](lync-server-2013-schema-attributes-by-class.md)」を参照してください。

Lync Server に固有のクラスと属性を識別するプレフィックスは msRTCSIP です。

## 新規 Active Directory 属性

次の表では、Lync Server 2013 で追加された Active Directory 属性について説明します。

### Lync Server 2013で追加された属性

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
<td><p>この複数値の属性には、ユーザーに適用される保持ポリシーの識別子が保持されます。この保持の間は、ユーザーのメールボックス アイテムが保持ポリシーに保存されます。この属性は、Exchange 2013 と共有されます。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserRoutingGroupId</p></td>
<td><p>SIP ルーティング グループ ID。同じグループのユーザーは、同じフロントエンド サーバーに登録します。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MirrorBackEndServer</p></td>
<td><p>この属性は、フロント エンド プールが使用するミラーリングされた SQL Server バックエンドを格納するために使用します。</p></td>
</tr>
</tbody>
</table>


## 変更された Active Directory クラス

次の表では、Lync Server 2013で変更された Active Directory クラスについて説明します。

### Lync Server 2013 で変更されたクラス

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
<td><p>add: mayContain</p></td>
<td><p>msExchUserHoldPolicies</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalTopologySetting</p></td>
<td><p>add: mayContain</p></td>
<td><p>msRTCSIP-MirrorBackEndServer</p></td>
</tr>
</tbody>
</table>

