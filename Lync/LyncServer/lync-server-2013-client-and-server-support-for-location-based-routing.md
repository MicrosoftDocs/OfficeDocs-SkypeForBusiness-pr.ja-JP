---
title: 'Lync Server 2013: 場所に基づくルーティングのためのクライアントとサーバーのサポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Client and server support for Location-Based Routing
ms:assetid: 26c2ca3d-026d-4dd7-94fa-15ebb4406953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994024(v=OCS.15)
ms:contentKeyID: 51803933
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d78ae3fcfe9bd834fbddced1bdeccc20be45481
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134083"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a>Lync Server 2013 での場所に基づくルーティングに対するクライアントとサーバーのサポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-06-18_

場所に基づくルーティングは、Lync Server によって適用されます。 Lync Server は、ユーザーが企業ネットワーク内から接続しているネットワークサイトを識別できます。 リモートユーザーは企業ネットワークの外部に存在するため、その場所は不明と見なされます。

<div>

## <a name="lync-server-support"></a>Lync Server のサポート

場所に基づくルーティングでは、Lync Server 2013 CU1 が、特定のトポロジ内のすべてのフロントエンドプールおよび Standard Edition サーバーに展開されている必要があります。 Lync Server 2013 CU1 がトポロジ内の特定の Lync コンポーネントにインストールされていない場合、場所に基づいたルーティング制限を完全に適用することはできません。

次の表は、場所に基づくルーティングでサポートされているサーバーの役割とバージョンの組み合わせを示しています。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>プールバージョン</th>
<th>仲介サーバーのバージョン</th>
<th>サポート済み</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 2013 年2月2013累積的な更新プログラム</p></td>
<td><p>Lync Server 2013 年2月2013累積的な更新プログラム</p></td>
<td><p>はい</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 年2月2013累積的な更新プログラム</p></td>
<td><p>Lync Server 2013</p></td>
<td><p>いいえ</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 年2月2013累積的な更新プログラム</p></td>
<td><p>Lync Server 2010</p></td>
<td><p>いいえ</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 年2月2013累積的な更新プログラム</p></td>
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>いいえ</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013</p></td>
<td><p>any</p></td>
<td><p>いいえ</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010</p></td>
<td><p>any</p></td>
<td><p>いいえ</p></td>
</tr>
<tr class="odd">
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>any</p></td>
<td><p>いいえ</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a>Lync クライアントのサポート

次の表は、場所に基づくルーティングがサポートするクライアントを示しています。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>クライアントの種類</th>
<th>サポート済み</th>
<th>詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>はい</p></td>
<td><p>Lync 2013 年2月2013の累積的な更新プログラムを含む</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010</p></td>
<td><p>はい</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>いいえ</p></td>
<td> </td>
</tr>
<tr class="even">
<td><p>Lync Phone Edition</p></td>
<td><p>はい</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Lync Attendant</p></td>
<td><p>はい</p></td>
<td> </td>
</tr>
<tr class="even">
<td><p>Lync for Windows 8</p></td>
<td><p>いいえ</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Lync Mobile 2013</p></td>
<td><p>いいえ</p></td>
<td><p>場所に基づくルーティングが有効になっているユーザーが使用している場合は、Lync Mobile 2013 クライアントで VoIP を無効にする必要があります。</p></td>
</tr>
<tr class="even">
<td><p>Lync Mobile 2010</p></td>
<td><p>はい</p></td>
<td> </td>
</tr>
</tbody>
</table>

  

<div>


> [!NOTE]  
> Lync Mobile 2013 クライアントの VoIP を無効にするには、場所に基づくルーティングが有効になっているすべてのユーザーに対して、[IP Audio/ビデオ] を設定したモビリティポリシーを割り当てます。 モビリティポリシーの詳細については、「 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">get-csmobilitypolicy</A>」を参照してください。



</div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での場所に基づくルーティングの計画](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

