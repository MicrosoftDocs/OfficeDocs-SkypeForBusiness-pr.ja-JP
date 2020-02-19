---
title: 'Lync Server 2013: 場所に基づくルーティングとコンサルティング呼び出しの転送'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location-Based Routing and consultative call transfers
ms:assetid: b12460c2-36c8-481f-b867-fe10dc1c0bdf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362836(v=OCS.15)
ms:contentKeyID: 56335089
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2bf1f9ca57366a3fc5b2ac1d13bd44336f3e2aeb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138188"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="location-based-routing-and-consultative-call-transfers-in-lync-server-2013"></a>Lync Server 2013 での場所に基づくルーティングおよびコンサルティング呼び出しの転送

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-07-31_

場所に基づくルーティングを Lync 会議に適用することに加えて、場所に基づくルーティング会議アプリケーションは、PSTN エンドポイントに出てくるコンサルティング呼び出しの転送に対して、場所に基づくルーティング制限を適用します。 コンサルティング着信転送とは、当事者の一方が新しいユーザーに通話を転送する2つの当事者間で確立された通話のことです。 たとえば、PSTN エンドポイントはユーザー A (Lync 呼び出し先) を呼び出します。 ユーザー A は、PSTN ユーザーが user B (Lync user) に転送される必要があることを決定します。 ユーザー A は、PSTN ユーザーに通話を保留し、ユーザー B を呼び出します。ユーザー B は、PSTN ユーザーに連絡することに同意します。 ユーザー A が通話を保留にして、ユーザー B に転送します。

**コンサルティング呼び出し転送の通話フロー**

![会議図の場所に基づくルーティング](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "会議図の場所に基づくルーティング")

場所に基づくルーティングが有効になっているユーザーが PSTN エンドポイントのコンサルティング呼び出し転送を開始すると (前の図に示すように)、これにより、2つのアクティブな通話、PSTN ユーザーと Lync ユーザー A の間の1回の呼び出し、および Lync ユーザー A と Lync ユーザー B 間の他の通話が作成されます。場所に基づくルーティング会議アプリケーションによって、次の動作が適用されます。

  - PSTN 通話をルーティングする SIP トランクが、Lync ユーザー B (つまり転送先) が配置されているネットワークサイトへの PSTN 通話の再ルーティングを承認されている場合は、呼び出し転送が許可されます。それ以外の場合は、コンサルティング呼び出しの転送がブロックされます。 この認証は、PSTN エンドポイントへのアクティブな通話をルーティングしている SIP トランクと同じネットワークサイトにある、転送先のパーティの場所に基づいて実行されます。

  - 着信 PSTN 通話をルーティングする SIP トランクが、転送先 (Lync ユーザー B) が存在するか、転送先が不明なネットワークサイトに配置されているネットワークサイトへの通話のルーティングを承認されていない場合は、PSTN へのコンサルティングコール転送エンドポイント (つまり、着信転送先) はブロックされます。

次の表に、場所に基づくルーティングの制限が、コンサルティング呼び出しの転送用の場所に基づくルーティング会議アプリケーションによってどのように適用されるかを示します。 PBX エンドポイントはネットワークサイトに直接関連付けられていませんが、PBX に接続されている SIP トランクにはネットワークサイトを割り当てることができます。 そのため、PBX エンドポイントは、ネットワークサイトに間接的に関連付けることができます。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>着信転送された相手のネットワークサイト</p></td>
<td><p>着信転送ターゲットのネットワークサイト</p></td>
<td><p>動作</p></td>
</tr>
<tr class="even">
<td><p>PSTN エンドポイント</p></td>
<td><p>同じネットワークサイト内の Lync ユーザー (つまり、サイト 1)</p></td>
<td><p>提案転送が許可されます。</p></td>
</tr>
<tr class="odd">
<td><p>PSTN エンドポイント</p></td>
<td><p>異なるネットワークサイトにある Lync ユーザー (サイト 2)</p></td>
<td><p>提案転送が許可されない</p></td>
</tr>
<tr class="even">
<td><p>PSTN エンドポイント</p></td>
<td><p>不明なネットワークサイトの Lync ユーザー</p></td>
<td><p>提案転送が許可されない</p></td>
</tr>
<tr class="odd">
<td><p>PSTN エンドポイント</p></td>
<td><p>フェデレーション Lync ユーザー</p></td>
<td><p>提案転送が許可されない</p></td>
</tr>
<tr class="even">
<td><p>PSTN エンドポイント</p></td>
<td><p>同じサイト内の PBX エンドポイント (つまりサイト 1)</p></td>
<td><p>提案転送が許可されます。</p></td>
</tr>
<tr class="odd">
<td><p>PSTN エンドポイント</p></td>
<td><p>別のサイトの PBX エンドポイント (つまりサイト 2)</p></td>
<td><p>提案転送が許可されない</p></td>
</tr>
<tr class="even">
<td><p>同じサイト内の PBX エンドポイント (つまりサイト 1)</p></td>
<td><p>PSTN エンドポイント</p></td>
<td><p>提案転送が許可されます。</p></td>
</tr>
<tr class="odd">
<td><p>別のサイトの PBX エンドポイント (つまりサイト 2)</p></td>
<td><p>PSTN エンドポイント</p></td>
<td><p>提案転送が許可されない</p></td>
</tr>
<tr class="even">
<td><p>任意のサイトの PBX エンドポイント</p></td>
<td><p>同じネットワークサイト内の Lync ユーザー (つまり、サイト 1)</p></td>
<td><p>提案転送が許可されます。</p></td>
</tr>
<tr class="odd">
<td><p>任意のサイトの PBX エンドポイント</p></td>
<td><p>異なるネットワークサイトにある Lync ユーザー (サイト 2)</p></td>
<td><p>提案転送が許可されます。</p></td>
</tr>
<tr class="even">
<td><p>任意のサイトの PBX エンドポイント</p></td>
<td><p>不明なネットワークサイトの Lync ユーザー</p></td>
<td><p>提案転送が許可されます。</p></td>
</tr>
<tr class="odd">
<td><p>任意のサイトの PBX エンドポイント</p></td>
<td><p>フェデレーション Lync ユーザー</p></td>
<td><p>提案転送が許可されます。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

