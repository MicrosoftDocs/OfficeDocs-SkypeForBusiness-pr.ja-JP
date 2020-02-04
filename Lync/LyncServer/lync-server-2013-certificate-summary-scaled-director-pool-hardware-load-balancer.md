---
title: 証明書の概要 - 拡張ディレクター プール、ハードウェア ロード バランサー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Scaled Director pool, hardware load balancer
ms:assetid: 45940add-8027-418d-b79a-9033b494762f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204846(v=OCS.15)
ms:contentKeyID: 48183992
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: efcecbd1ec0c486e888a8c7303e450f75abf05bc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736587"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a>証明書の概要 - Lync Server 2013 の拡張ディレクター プール、ハードウェア ロード バランサー

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-20_

ハードウェアロードバランサーを備えたディレクターの証明書要件は、ディレクタープールが受け取ることのできるサービスのサブジェクト名とサブジェクトの代替名を持つ既定の証明書を使います。 プール内の各ディレクターに対して証明書が要求されます。 また、各サーバーにインストールされるサーバー認証用の OAuth トークン証明書もあります。

### <a name="certificates-for-a-scaled-director-using-a-hardware-load-balancer"></a>ハードウェアロードバランサーを使用した、スケーリングされたディレクター用の証明書

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>コンポーネント</th>
<th>サブジェクト名 (SN)</th>
<th>サブジェクトの代替名 (SAN)</th>
<th>コメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Default</p></td>
<td><p>dirpool01.contoso.net</p></td>
<td><p>dirpool01.contoso.net</p>
<p>dir01.contoso.net</p>
<p>dialin.contoso.com</p>
<p>meet.contoso.com</p>
<p>lyncdiscoverinternal.contoso.com</p>
<p>lyncdiscover.contoso.com</p>
<p>(必要に応じて) *. contoso.com</p></td>
<td><p>ディレクター証明書は、内部管理の証明機関 (CA) またはパブリック CA から要求することができます。</p>
<p>ディレクターは、境界サーバーまたはエッジサーバーのリバースプロキシからの要求に応答します。</p>
<p>または、単純な Url のワイルドカードエントリ</p></td>
</tr>
<tr class="even">
<td><p>OAuthTokenIssuer</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>エントリがありません</p></td>
<td>


> [!IMPORTANT]
> 最小のキー長は1024ですが、最小の推奨されるキーの長さは2048ビットであるという警告が表示されることがあります。


<p>OAuthTokenIssuer 証明書は、大規模な環境でサーバーを認証することを目的とした単一目的の証明書であり、内部 CA またはパブリック CA から要求することができます。 証明書が必要です。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

