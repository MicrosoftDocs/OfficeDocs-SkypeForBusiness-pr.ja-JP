---
title: 'Lync Server 2013: 以前の展開からサポートされるクライアント'
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
ms.openlocfilehash: 38d4fe00b834778f1ad87f021656ed08488c1ba2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731727"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-clients-from-previous-deployments-in-lync-server-2013"></a>Lync Server 2013 で以前の展開からサポートされるクライアント

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-12-14_

共存シナリオでは、Lync Server 2013 クライアントは、以前のバージョンの Lync Server と Office Communications Server のクライアントと対話することができます。 以前のリリースとは異なり、Lync Server 2010 では新しい Lync 2013 クライアントがサポートされています。 これにより、Lync Server 2010 からアップグレードしている組織は、Lync Server のアップグレードに関係なく、新しいクライアントを展開することができます。

<div>

## <a name="supported-server-and-client-combinations"></a>サポートされているサーバーとクライアントの組み合わせ

次の表は、クライアントバージョンとサーバーバージョンのサポートされる組み合わせを示しています。 Lync Server 2013 では、2つの以前のクライアントバージョンがサポートされています。 Lync Server 2010 では、新しい Lync 2013 クライアントがサポートされています。


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
<td><p>サポート対象</p></td>
<td><p>サポート対象</p></td>
<td><p>サポート対象外</p></td>
</tr>
<tr class="even">
<td><p>Lync Web App 2013</p></td>
<td><p>サポート対象</p></td>
<td><p>サポート対象外</p></td>
<td><p>サポート対象外</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010</p></td>
<td><p>サポート対象</p></td>
<td><p>サポート対象</p></td>
<td><p>サポート対象外</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 Attendant</p></td>
<td><p>サポート対象</p></td>
<td><p>サポート対象</p></td>
<td><p>サポート対象外</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 グループ チャット</p></td>
<td><p>該当なし</p></td>
<td><p>Supported1</p></td>
<td><p>該当なし</p></td>
</tr>
<tr class="even">
<td><p>Lync Web App 2010</p></td>
<td><p>サポート対象外</p></td>
<td><p>サポート対象</p></td>
<td><p>サポート対象外</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 Attendee</p></td>
<td><p>Supported2 しない</p></td>
<td><p>サポート対象</p></td>
<td><p>サポート対象外</p></td>
</tr>
<tr class="even">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Interoperable3</p></td>
<td><p>サポート対象</p></td>
<td><p>サポート対象</p></td>
</tr>
<tr class="odd">
<td><p>Microsoft Office Communications Server 2007 R2 Attendant</p></td>
<td><p>サポート対象外</p></td>
<td><p>サポート対象</p></td>
<td><p>サポート対象</p></td>
</tr>
<tr class="even">
<td><p>Office Communicator 2007</p></td>
<td><p>サポート対象外</p></td>
<td><p>サポート対象</p></td>
<td><p>サポート対象</p></td>
</tr>
<tr class="odd">
<td><p>Office Live Meeting 2007</p></td>
<td><p>サポート対象外</p></td>
<td><p>サポート対象</p></td>
<td><p>サポート対象</p></td>
</tr>
</tbody>
</table>


1 Microsoft Lync Server 2010、グループチャット機能は、Lync Server 2010 用のサードパーティの信頼済みアプリケーションであるグループチャットサーバーで利用できました。 Lync 2013 クライアントは、Lync Server 2010、グループチャットとは互換性がありません。

2Lync Web App 2013 では、コンピューターの音声やビデオなどの完全な会議エクスペリエンスを提供しており、Lync 2010 の出席者の代わりと見なされています。

3The Communicator 2007 R2 のプレゼンス機能と IM 機能は Lync Server 2013 と互換性がありますが、会議機能は使用できません。 Office Communications Server 2007 R2 からの移行中、Office Communicator 2007 R2 はプレゼンスと IM の相互運用性に適していますが、ユーザーは Lync Web App 2013 を使って Lync Server 2013 会議に参加する必要があります。

<div>


> [!NOTE]  
> Lync server 2013 クライアントが以前のバージョンの Lync Server と Office Communications Server のクライアントを共存させて操作する機能の詳細については、計画ドキュメントの「 <A href="lync-server-2013-client-interoperability-in-lync-2013.md">lync 2013 でのクライアントの相互運用性</A>」を参照してください。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

