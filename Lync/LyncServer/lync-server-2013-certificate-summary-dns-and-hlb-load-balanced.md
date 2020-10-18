---
title: 'Lync Server 2013: 証明書の概要-DNS と HLB 負荷分散'
description: 'Lync Server 2013: 証明書の概要-DNS と HLB 負荷分散。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - DNS and HLB load balanced
ms:assetid: 8318a1a4-b423-47b7-95e6-9541adfad391
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205047(v=OCS.15)
ms:contentKeyID: 48184676
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97a89975af16b6e39625677f787d3726f00c76c1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575973"
---
# <a name="certificate-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a>証明書の概要-Lync Server 2013 での DNS および HLB の負荷分散

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-22_

ディレクターの証明書要件。 DNS 負荷分散とロードバランサー機器は、ディレクターが受信できるサービスのサブジェクト名とサブジェクトの別名を持つ既定の証明書を使用します。 プール内の各ディレクターに証明書が要求されます。 ハードウェア ロード バランサーはリバース プロキシからのトラフィックだけを負荷分散することを理解しておくことが重要です。 さらに、サーバー間認証のために各サーバーにインストールされる OAuth トークンがあります。

### <a name="certificates-for-director"></a>ディレクターの証明書

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
<th>サブジェクト名の別名 (SAN)</th>
<th>Comments</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>既定値</p></td>
<td><p>dirpool01.contoso.net</p></td>
<td><p>dirpool01.contoso.net</p>
<p>dir01.contoso.net</p>
<p>dialin.contoso.com</p>
<p>meet.contoso.com</p>
<p>lyncdiscoverinternal.contoso.com</p>
<p>lyncdiscover.contoso.com</p>
<p>(オプション) *.contoso.com</p></td>
<td><p>ディレクター証明書は、内部管理の証明機関 (CA) またはパブリック CA のどちらかから要求できます。</p>
<p>ディレクターは、境界サーバーまたはエッジサーバーのリバースプロキシからの要求に応答します。 内部クライアントはディレクターを使用しません。</p>
<p>または、簡易 URL のワイルドカード エントリ</p></td>
</tr>
<tr class="even">
<td><p>OAuthTokenIssuer</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>エントリはありません</p></td>
<td><div>

> [!IMPORTANT]  
> キーの最低の長さは 1024 ですが、キーの推奨される最低の長さが 2048 ビットであるという警告が表示される場合があります。


</div>
<p>OAuthTokenIssuer 証明書は、大規模な環境内のサーバーを認証するための単一目的の証明書であり、社内の CA またはパブリック CA に要求できます。この証明書は必須です。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

