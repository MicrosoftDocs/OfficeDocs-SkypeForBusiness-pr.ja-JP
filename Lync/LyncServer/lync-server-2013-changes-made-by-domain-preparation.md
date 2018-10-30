---
title: Lync Server 2013 でのドメインの準備によって加えられる変更
TOCTitle: Lync Server 2013 でのドメインの準備によって加えられる変更
ms:assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398742(v=OCS.15)
ms:contentKeyID: 48272855
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのドメインの準備によって加えられる変更

 

_**トピックの最終更新日:** 2015-03-09_

次の表は、ドメインを準備する際にドメイン ルートに作成されるアクセス制御エントリ (ACE) を示しています。特に注記のない限り、これらの ACE はすべて継承されます。

### ドメイン ルートに追加された ACE

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>ACE</th>
<th>RTCUniversal-UserReadOnly-Group</th>
<th>RTCUniversal-ServerReadOnly-Group</th>
<th>RTCUniversal-UserAdmins</th>
<th>RTCHSUniversal-Services</th>
<th>Authenticated-Users</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>コンテナーの読み取り (継承されない)</p></td>
<td><p><strong>はい</strong></p></td>
<td><p><strong>はい</strong></p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
</tr>
<tr class="even">
<td><p>User-Account-Restrictions ユーザー プロパティ セットの読み取り</p></td>
<td><p><strong>はい</strong></p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
</tr>
<tr class="odd">
<td><p>Personal-Information ユーザー プロパティ セットの読み取り</p></td>
<td><p><strong>はい</strong></p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
</tr>
<tr class="even">
<td><p>General-Information ユーザー プロパティ セットの読み取り</p></td>
<td><p><strong>はい</strong></p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
</tr>
<tr class="odd">
<td><p>Public-Information ユーザー プロパティ セットの読み取り</p></td>
<td><p><strong>はい</strong></p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
</tr>
<tr class="even">
<td><p>RTCUserSearchProperty-Set ユーザー プロパティ セットの読み取り</p></td>
<td><p><strong>はい</strong></p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p><strong>はい</strong></p></td>
</tr>
<tr class="odd">
<td><p>RTCPropertySet ユーザー プロパティ セットの読み取り</p></td>
<td><p><strong>はい</strong></p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
</tr>
<tr class="even">
<td><p>Proxy-Addresses ユーザー プロパティの書き込み</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p><strong>はい</strong></p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
</tr>
<tr class="odd">
<td><p>RTCUserSearchProperty-Set ユーザー プロパティ セットの書き込み</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p><strong>はい</strong></p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
</tr>
<tr class="even">
<td><p>RTCPropertySet ユーザー プロパティ セットの書き込み</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p><strong>はい</strong></p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
</tr>
<tr class="odd">
<td><p>すべての Active Directory オブジェクトの DS-Replication-Get-Changes プロパティ セットの読み取り</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p><strong>はい</strong></p></td>
<td><p>いいえ</p></td>
</tr>
</tbody>
</table>


次の表は、ドメインを準備する際に 3 つの組み込みコンテナー (Users、Computers、および Domain Controllers) に作成される ACE を示しています。特に注記のない限り、これらの ACE はすべて継承されます。

### 組み込みコンテナーに追加された ACE

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>ACE</th>
<th>RTCUniversal-UserReadOnly-Group</th>
<th>RTCUniversal-ServerReadOnly-Group</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>コンテナーの読み取り (継承されない)</p></td>
<td><p><strong>はい</strong></p></td>
<td><p><strong>はい</strong></p></td>
</tr>
</tbody>
</table>

