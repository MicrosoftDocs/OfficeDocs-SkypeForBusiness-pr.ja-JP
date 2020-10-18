---
title: 'Lync Server 2013: DNS の概要-自動検出'
description: 'Lync Server 2013: DNS の概要-自動検出。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Autodiscover
ms:assetid: b336a2ae-0e58-4b74-b606-aedbbd411587
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945644(v=OCS.15)
ms:contentKeyID: 51541504
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eef9bd6a2489561145718c7bbf2f710ab0b1f248
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574283"
---
# <a name="dns-summary---autodiscover-in-lync-server-2013"></a>DNS の概要-Lync Server 2013 での自動検出

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-13_

自動検出は、HTTP または HTTPS を経由した通信を受け付ける、柔軟なサービスです。 これを実現するには、ドメインネームシステム (DNS) と自動検出サービスをホストするサーバーで使用される証明書が正しく構成されている必要があります。 証明書の要件は [、「証明書の概要-Lync Server 2013 での自動検出](lync-server-2013-certificate-summary-autodiscover.md)」で説明されています。

<div>


> [!IMPORTANT]  
> Lync Server クライアントの DNS 参照ロジックでは、特定の順序で解決されます。 常に lyncdiscoverinternal を含める必要があります。 &lt;ドメイン &gt; および lyncdiscover。 &lt;&gt;DNS のドメイン。 Lyncdiscoverinternal を除外します。 &lt;ドメインレコードを使用すると &gt; 、内部クライアントは、目的のサービスへの接続を失敗させたり、誤った自動検出応答を受信したりします。



</div>

### <a name="internal-dns-records"></a>内部 DNS レコード

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>レコードの種類</th>
<th>ホスト名</th>
<th>解決先</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>Lyncdiscoverinternal。 &lt;内部ドメイン名&gt;</p></td>
<td><p>ディレクターを所有していない場合は、ディレクタープールの内部 Web サービスの FQDN、またはディレクターを持っていない場合はフロントエンドプール用。</p></td>
</tr>
<tr class="even">
<td><p>A (IPv6 の場合は host、AAAA の場合)</p></td>
<td><p>lyncdiscoverinternal。 &lt;内部ドメイン名&gt;</p></td>
<td><p>ディレクタープールがある場合、ディレクタープールの内部 Web サービス IP アドレス (ロードバランサーを使用する場合は仮想 IP (VIP) アドレス) (ディレクターを持っていない場合は、フロントエンドプールがある場合)。</p></td>
</tr>
</tbody>
</table>


次の外部 DNS レコードの 1 つを作成する必要があります。

### <a name="external-dns-records"></a>外部 DNS レコード

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>レコードの種類</th>
<th>ホスト名</th>
<th>解決先</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>lyncdiscover。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</p></td>
<td><p>ディレクターが存在しない場合は、ディレクタープールの外部 Web サービスの FQDN、またはディレクターを持っていない場合はフロントエンドプール。</p></td>
</tr>
<tr class="even">
<td><p>A (IPv6 の場合は host、AAAA の場合)</p></td>
<td><p>lyncdiscover。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</p></td>
<td><p>リバースプロキシの外部またはパブリック IP アドレス。</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 外部トラフィックはリバース プロキシを経由します。



</div>

<div>


> [!NOTE]  
> モバイル デバイスのクライアントでは、異なるドメインからの複数の SSL (Secure Sockets Layer) 証明書がサポートされません。 つまり、HTTPS では、異なるドメインへの CNAME のリダイレクトがサポートされません。 たとえば、director.contoso.net のアドレスにリダイレクトされる lyncdiscover.contoso.com の DNS CNAME レコードは、HTTPS ではサポートされません。 このようなトポロジでは、CNAME のリダイレクトが HTTP で解決されるように、モバイル デバイスのクライアントは、最初の要求に対して HTTP を使用する必要があります。 その後、以降の要求については HTTPS を使用します。 このシナリオをサポートするには、ポート 80 (HTTP) の Web 公開ルールを使用して、リバース プロキシを構成する必要があります。 詳細については、「 <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Lync Server 2013 でモビリティのリバースプロキシを構成</A>する」の「ポート80の web 公開ルールを作成するには」を参照してください。 HTTPS では、同じドメインへの CNAME のリダイレクトはサポートされます。 この例では、宛先ドメインの証明書が元のドメインを対象としています。



</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのモビリティのリバースプロキシの構成](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)  


[証明書の概要-Lync Server 2013 での自動検出](lync-server-2013-certificate-summary-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

