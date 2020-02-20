---
title: 'Lync Server 2013: ドメインの準備によって加えられた変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by domain preparation
ms:assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398742(v=OCS.15)
ms:contentKeyID: 48184845
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e02224636b3e5179a8834e5dd59c0218956e6eb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151047"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a>Lync Server 2013 のドメインの準備によって加えられた変更

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2010-10-18_

次の表は、ドメインを準備する際にドメイン ルートに作成されるアクセス制御エントリ (ACE) を示しています。特に注記のない限り、これらの ACE はすべて継承されます。

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a>ドメイン ルートに追加された ACE

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
<th>RTCUniversal-UserReadOnly-グループ</th>
<th>RTCUniversal-ServerReadOnly-グループ</th>
<th>RTCUniversal-UserAdmins</th>
<th>RTCHSUniversal-サービス</th>
<th>認証されたユーザー</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>コンテナーの読み取り (継承されない)</p></td>
<td><p><strong>はい</strong></p></td>
<td><p><strong>○</strong></p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
</tr>
<tr class="even">
<td><p>User-Account-Restrictions ユーザー プロパティ セットの読み取り</p></td>
<td><p><strong>○</strong></p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
</tr>
<tr class="odd">
<td><p>Personal-Information ユーザー プロパティ セットの読み取り</p></td>
<td><p><strong>○</strong></p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
</tr>
<tr class="even">
<td><p>General-Information ユーザー プロパティ セットの読み取り</p></td>
<td><p><strong>○</strong></p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
</tr>
<tr class="odd">
<td><p>Public-Information ユーザー プロパティ セットの読み取り</p></td>
<td><p><strong>○</strong></p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
</tr>
<tr class="even">
<td><p>RTCUserSearchProperty-Set ユーザー プロパティ セットの読み取り</p></td>
<td><p><strong>○</strong></p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p><strong>はい</strong></p></td>
</tr>
<tr class="odd">
<td><p>RTCPropertySet ユーザー プロパティ セットの読み取り</p></td>
<td><p><strong>○</strong></p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
</tr>
<tr class="even">
<td><p>Proxy-Addresses ユーザー プロパティの書き込み</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p><strong>○</strong></p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
</tr>
<tr class="odd">
<td><p>RTCUserSearchProperty-Set ユーザー プロパティ セットの書き込み</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p><strong>○</strong></p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
</tr>
<tr class="even">
<td><p>RTCPropertySet ユーザー プロパティ セットの書き込み</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p><strong>○</strong></p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
</tr>
<tr class="odd">
<td><p>すべての Active Directory オブジェクトの DS-Replication-Get-Changes プロパティ セットの読み取り</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p>いいえ</p></td>
<td><p><strong>○</strong></p></td>
<td><p>×</p></td>
</tr>
</tbody>
</table>


次の表は、ドメインを準備する際に 3 つの組み込みコンテナー (Users、Computers、および Domain Controllers) に作成される ACE を示しています。特に注記のない限り、これらの ACE はすべて継承されます。

### <a name="aces-added-to-built-in-containers"></a>組み込みコンテナーに追加された ACE

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>ACE</th>
<th>RTCUniversal-UserReadOnly-グループ</th>
<th>RTCUniversal-ServerReadOnly-グループ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>コンテナーの読み取り (継承されない)</p></td>
<td><p><strong>はい</strong></p></td>
<td><p><strong>○</strong></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

