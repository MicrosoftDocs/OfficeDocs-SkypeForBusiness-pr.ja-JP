---
title: 'Lync Server 2013: 証明書の概要 - DNS および HLB による負荷分散'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - DNS and HLB load balanced
ms:assetid: 8318a1a4-b423-47b7-95e6-9541adfad391
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205047(v=OCS.15)
ms:contentKeyID: 48184676
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e145e2f1ac3d331906713584b365adf7cd48aec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840649"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a>証明書の概要 - Lync Server 2013 の DNS および HLB による負荷分散

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-22_

DNS の負荷分散とハードウェアのロードバランサーを備えたディレクターの証明書要件は、監督が受信できるサービスのサブジェクト名とサブジェクトの代替名を持つ既定の証明書を使います。 プール内の各ディレクターに対して証明書が要求されます。 ハードウェアロードバランサーでは、リバースプロキシからのトラフィックだけが負荷分散されることに注意することが重要です。 さらに、サーバー間認証のための OAuth トークン証明書が、各サーバーにインストールされています。

### <a name="certificates-for-director"></a>ディレクター用の証明書

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
<p>ディレクターは、境界サーバーまたはエッジサーバーのリバースプロキシからの要求に応答します。 内部クライアントでは、監督は使用されません。</p>
<p>または、単純な Url のワイルドカードエントリ</p></td>
</tr>
<tr class="even">
<td><p>OAuthTokenIssuer</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>エントリがありません</p></td>
<td><div>

> [!IMPORTANT]  
> 最小のキー長は1024ですが、最小の推奨されるキーの長さは2048ビットであるという警告が表示されることがあります。


</div>
<p>OAuthTokenIssuer 証明書は、大規模な環境でサーバーを認証することを目的とした単一目的の証明書であり、内部 CA またはパブリック CA から要求することができます。 証明書が必要です。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

