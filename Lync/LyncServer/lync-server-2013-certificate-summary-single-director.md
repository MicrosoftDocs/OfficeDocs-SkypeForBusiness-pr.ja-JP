---
title: 'Lync Server 2013: 証明書の概要 - 単一ディレクター'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - Single Director
ms:assetid: 1b769a76-cbf3-46e9-a955-f6cde5faff93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204720(v=OCS.15)
ms:contentKeyID: 48183546
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e44be0ca76a1926a1515657a9d7d5646a49390c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840622"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---single-director-in-lync-server-2013"></a>証明書の概要 - Lync Server 2013 の単一ディレクター

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-08_

1つのディレクターの証明書要件は、監督が受信できるサービスのサブジェクト名とサブジェクトの代替名を持つ既定の証明書で構成されます。 さらに、サーバー間認証のための OAuth トークン証明書も用意されています。

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
<td><p>dir01.contoso.net</p></td>
<td><p>dir01.contoso.net</p>
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

