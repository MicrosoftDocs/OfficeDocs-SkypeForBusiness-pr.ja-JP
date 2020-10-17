---
title: 'Lync Server 2013: ルーティングとコンサルティング呼び出しの転送を Location-Based'
description: 'Lync Server 2013: ルーティングとコンサルティング呼び出しの転送を Location-Based します。'
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
ms.openlocfilehash: 0d07cf6a33ff4d6ad57f8913a798fac3bc393a00
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567673"
---
# <a name="location-based-routing-and-consultative-call-transfers-in-lync-server-2013"></a>Lync Server 2013 でのルーティングおよびコンサルティング呼び出しの転送の Location-Based

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-07-31_

Location-Based が Lync 会議にルーティングされるようにすることに加えて、Location-Based ルーティング会議アプリケーションは、PSTN エンドポイントに出てくるコンサルティング呼び出し転送に対して Location-Based ルーティング制限を適用します。 コンサルティング着信転送とは、当事者の一方が新しいユーザーに通話を転送する2つの当事者間で確立された通話のことです。 たとえば、PSTN エンドポイントはユーザー A (Lync 呼び出し先) を呼び出します。 ユーザー A は、PSTN ユーザーが user B (Lync user) に転送される必要があることを決定します。 ユーザー A は、PSTN ユーザーに通話を保留し、ユーザー B を呼び出します。ユーザー B は、PSTN ユーザーに連絡することに同意します。 ユーザー A が通話を保留にして、ユーザー B に転送します。

**コンサルティング呼び出し転送の通話フロー**

![会議図の場所に基づくルーティング](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "会議図の場所に基づくルーティング")

Location-Based ルーティングが有効になっているユーザーが PSTN エンドポイントのコンサルティング呼び出し転送を開始すると (前の図に示すように)、これに Location-Based より、2つのアクティブな通話、PSTN ユーザーと Lync ユーザー A の間の通話、および Lync ユーザー A と Lync ユーザー B 間の他の呼び出しが行われます

  - PSTN 通話をルーティングする SIP トランクが、Lync ユーザー B (つまり転送先) が配置されているネットワークサイトへの PSTN 通話の再ルーティングを承認されている場合は、呼び出し転送が許可されます。それ以外の場合は、コンサルティング呼び出しの転送がブロックされます。 この認証は、PSTN エンドポイントへのアクティブな通話をルーティングしている SIP トランクと同じネットワークサイトにある、転送先のパーティの場所に基づいて実行されます。

  - 着信 PSTN 通話をルーティングする SIP トランクが、転送先 (Lync ユーザー B) がある、または転送先が不明なネットワークサイトにあるネットワークサイトへの呼び出しをルーティングすることを許可されていない場合は、PSTN エンドポイントへのコンサルティング呼び出し転送 (つまり、通話転送ターゲット) はブロックされます。

次の表では、Location-Based ルーティングの制限が、提案型の通話の転送に対して Location-Based ルーティング会議アプリケーションによって適用される方法について説明します。 PBX エンドポイントはネットワークサイトに直接関連付けられていませんが、PBX に接続されている SIP トランクにはネットワークサイトを割り当てることができます。 そのため、PBX エンドポイントは、ネットワークサイトに間接的に関連付けることができます。


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

