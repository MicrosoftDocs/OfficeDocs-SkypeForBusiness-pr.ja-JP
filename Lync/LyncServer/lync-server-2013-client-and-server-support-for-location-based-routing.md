---
title: 'Lync Server 2013: 場所に基づくルーティングに対するクライアントとサーバーのサポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Client and server support for Location-Based Routing
ms:assetid: 26c2ca3d-026d-4dd7-94fa-15ebb4406953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994024(v=OCS.15)
ms:contentKeyID: 51803933
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3791b359422c4b5bef463a612db6f0b74c07f096
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840565"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a>Lync Server 2013 での場所に基づくルーティングに対するクライアントとサーバーのサポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-06-18_

場所に基づくルーティングは、Lync Server によって適用されます。 Lync Server は、企業ネットワーク内からユーザーが接続するネットワークサイトを特定できます。 リモート ユーザーは企業ネットワークの外部に存在するため、リモート ユーザーの場所は不明と見なされます。

<div>

## <a name="lync-server-support"></a>Lync Server のサポート

位置情報に基づくルーティングを行うには、Lync Server 2013 CU1 が、特定のトポロジに含まれるすべてのフロントエンドプールおよび標準エディションのサーバーに展開されている必要があります。 トポロジで特定の Lync コンポーネントに Lync Server 2013 CU1 がインストールされていない場合、場所に基づくルーティングの制限を完全に適用することはできません。

次の表は、位置情報に基づくルーティングでサポートされているサーバーの役割とバージョンの組み合わせを示しています。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>プールのバージョン</th>
<th>仲介サーバーのバージョン</th>
<th>サポート対象</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 2013 (2013 年2月の累積更新プログラム)</p></td>
<td><p>Lync Server 2013 (2013 年2月の累積更新プログラム)</p></td>
<td><p>はい</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 (2013 年2月の累積更新プログラム)</p></td>
<td><p>Lync Server 2013</p></td>
<td><p>いいえ</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 (2013 年2月の累積更新プログラム)</p></td>
<td><p>Lync Server 2010</p></td>
<td><p>いいえ</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 (2013 年2月の累積更新プログラム)</p></td>
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>いいえ</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013</p></td>
<td><p>任意</p></td>
<td><p>いいえ</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010</p></td>
<td><p>任意</p></td>
<td><p>いいえ</p></td>
</tr>
<tr class="odd">
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>任意</p></td>
<td><p>いいえ</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a>Lync クライアントのサポート

次の表は、場所に基づくルーティングでサポートされているクライアントを示しています。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>クライアントの種類</th>
<th>サポート対象</th>
<th>詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>はい</p></td>
<td><p>2013年 2 2013 月の累積更新プログラム (Lync)</p></td>
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
<td><p>Windows 8 版 Lync</p></td>
<td><p>いいえ</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Lync Mobile 2013</p></td>
<td><p>いいえ</p></td>
<td><p>場所に基づくルーティングが有効になっているユーザーが使用した場合、Lync Mobile 2013 クライアントで VoIP を無効にする必要があります。</p></td>
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
> Lync Mobile 2013 クライアントで VoIP を無効にするには、位置情報に基づくルーティングが有効になっているすべてのユーザーに対して、設定、[IP Audio/ビデオ] の順に移動して、モビリティポリシーを割り当てます。 モビリティ ポリシーの詳細については、「<A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>」を参照してください。



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

