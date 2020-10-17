---
title: 'Lync Server 2013: 以前の展開からサポートされているクライアント'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported clients from previous deployments
ms:assetid: 69d427f8-57a5-4244-b2ed-f2eb7600285e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398499(v=OCS.15)
ms:contentKeyID: 48184390
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f404dad679eeffa91465f3f8547fbe86ce74b0c1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524134"
---
# <a name="supported-clients-from-previous-deployments-in-lync-server-2013"></a>Lync Server 2013 での以前の展開からサポートされているクライアント

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-12-14_

共存シナリオでは、Lync server 2013 クライアントは、以前のバージョンの Lync Server および Office Communications Server のクライアントと対話できます。 以前のリリースとは異なり、Lync Server 2010 は新しい Lync 2013 クライアントをサポートしています。 これにより、Lync server 2010 からアップグレードする組織は、Lync Server のアップグレードに関係なく新しいクライアントをロールアウトすることができます。

<div>

## <a name="supported-server-and-client-combinations"></a>サポートされるサーバーとクライアントの組み合わせ

次の表に、サポートされるクライアント バージョンとサーバー バージョンの組み合わせを示します。 Lync Server 2013 は、2つの以前のクライアントバージョンをサポートしており、Lync Server 2010 は新しい Lync 2013 クライアントをサポートしています。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>クライアント</th>
<th>Lync Server 2013</th>
<th>Lync Server 2010</th>
<th>Office Communications Server 2007 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>サポート</p></td>
<td><p>サポートされている</p></td>
<td><p>サポート対象外</p></td>
</tr>
<tr class="even">
<td><p>Lync Web App 2013</p></td>
<td><p>サポートされている</p></td>
<td><p>サポート対象外</p></td>
<td><p>サポート対象外</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010</p></td>
<td><p>サポート</p></td>
<td><p>サポートされている</p></td>
<td><p>サポート対象外</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 Attendant</p></td>
<td><p>サポート</p></td>
<td><p>サポートされている</p></td>
<td><p>サポート対象外</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 グループ チャット</p></td>
<td><p>該当なし</p></td>
<td><p>1</p></td>
<td><p>該当なし</p></td>
</tr>
<tr class="even">
<td><p>Lync Web App 2010</p></td>
<td><p>サポート対象外</p></td>
<td><p>サポートされている</p></td>
<td><p>サポート対象外</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 Attendee</p></td>
<td><p>Not Supported2</p></td>
<td><p>サポートされている</p></td>
<td><p>サポート対象外</p></td>
</tr>
<tr class="even">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Interoperable3</p></td>
<td><p>サポート</p></td>
<td><p>サポート</p></td>
</tr>
<tr class="odd">
<td><p>Microsoft Office Communications Server 2007 R2 Attendant</p></td>
<td><p>サポート対象外</p></td>
<td><p>サポートされます</p></td>
<td><p>サポート</p></td>
</tr>
<tr class="even">
<td><p>Office Communicator 2007</p></td>
<td><p>サポート対象外</p></td>
<td><p>サポートされます</p></td>
<td><p>サポート</p></td>
</tr>
<tr class="odd">
<td><p>Office Live Meeting 2007</p></td>
<td><p>サポート対象外</p></td>
<td><p>サポートされます</p></td>
<td><p>サポート</p></td>
</tr>
</tbody>
</table>


1 Microsoft Lync Server 2010、グループチャットの機能は、Lync Server 2010 用のサードパーティの信頼されたアプリケーションであるグループチャットサーバーで利用できました。 Lync 2013 クライアントは、Lync Server 2010、グループチャットと互換性がありません。

2Lync Web App 2013 は、コンピューターの音声とビデオを含む完全な会議機能を提供しており、Lync 2010 の出席者に代わるものと見なされました。

3The Communicator 2007 R2 のプレゼンスおよび IM 機能は Lync Server 2013 と互換性がありますが、会議機能はサポートされていません。 Office Communications Server 2007 R2 からの移行時に、Office Communicator 2007 R2 はプレゼンスおよび IM の相互運用性に適していますが、ユーザーは lync Server の2013会議に参加するために Lync Web App 2013 を使用する必要があります。

<div>


> [!NOTE]  
> Lync server 2013 クライアントが以前のバージョンの Lync Server および Office Communications Server のクライアントと共存して対話する機能の詳細については、「計画」のドキュメントの「 <A href="lync-server-2013-client-interoperability-in-lync-2013.md">lync 2013 でのクライアントの相互運用性</A> 」を参照してください。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

