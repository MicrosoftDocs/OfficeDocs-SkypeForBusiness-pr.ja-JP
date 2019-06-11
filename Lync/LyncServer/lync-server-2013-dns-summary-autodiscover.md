---
title: 'Lync Server 2013: DNS の概要-自動検出'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Autodiscover
ms:assetid: b336a2ae-0e58-4b74-b606-aedbbd411587
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945644(v=OCS.15)
ms:contentKeyID: 51541504
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64e303ebecc42f03197f6502296c8a2708e97ebf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833360"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---autodiscover-in-lync-server-2013"></a>DNS 概要-Lync Server 2013 での自動検出

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-13_

自動検出は、HTTP または HTTPS 経由での通信を受け付ける、柔軟なサービスです。 これを実現するために、ドメインネームシステム (DNS) と自動検出サービスをホストするサーバーによって使われる証明書が正しく構成されている必要があります。 証明書の要件については[、「証明書の概要-Lync Server 2013 での自動検出](lync-server-2013-certificate-summary-autodiscover.md)」で説明します。

<div>


> [!IMPORTANT]  
> Lync Server クライアントの DNS 検索ロジックは、特定の解決方法を使用します。 常に lyncdiscoverinternal の両方が含まれている必要があります。&lt;ドメイン&gt;と lyncdiscover&lt;DNS&gt;でドメインを選びます。 Lyncdiscoverinternal を除外します。&lt;ドメイン&gt;レコードを使用すると、内部クライアントは、目的のサービスに接続できないか、または正しくない自動検出応答を受信します。



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
<td><p>Lyncdiscoverinternal.&lt;内部ドメイン名&gt;</p></td>
<td><p>ディレクタープールがある場合は、そのディレクタープールの内部 Web サービス FQDN。ディレクターを持っていない場合は、フロントエンドプールにも使用できます。</p></td>
</tr>
<tr class="even">
<td><p>A (IPv6 の場合は host、AAAA の場合)</p></td>
<td><p>lyncdiscoverinternal.&lt;内部ドメイン名&gt;</p></td>
<td><p>ディレクターを持っていない場合は、ディレクタープールの内部 Web サービス IP アドレス (ロードバランサーを使用している場合は仮想 IP (VIP) のアドレス)。ディレクターを持っていない場合は、フロントエンドプールを所有している場合は、このアドレスを使用します。</p></td>
</tr>
</tbody>
</table>


次のいずれかの外部 DNS レコードを作成する必要があります。

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
<td><p>lyncdiscover.&lt;sipdomain&gt;</p></td>
<td><p>ディレクタープールを所有している場合は、そのディレクタープールの外部 Web サービス FQDN。ディレクターを持っていない場合は、フロントエンドプールに対応する必要があります。</p></td>
</tr>
<tr class="even">
<td><p>A (IPv6 の場合は host、AAAA の場合)</p></td>
<td><p>lyncdiscover.&lt;sipdomain&gt;</p></td>
<td><p>リバースプロキシの外部またはパブリック IP アドレス。</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 外部トラフィックはリバースプロキシ経由で送信されます。



</div>

<div>


> [!NOTE]  
> モバイルデバイスクライアントは、異なるドメインからの複数の Secure Sockets Layer (SSL) 証明書をサポートしていません。 したがって、異なるドメインへの CNAME リダイレクションは HTTPS 経由ではサポートされません。 たとえば、director.contoso.net のアドレスにリダイレクトされる lyncdiscover.contoso.com の DNS CNAME レコードは HTTPS ではサポートされません。 このようなトポロジでは、モバイルデバイスクライアントは、最初の要求に対して HTTP を使う必要があるため、CNAME リダイレクションが HTTP で解決されます。 それ以降の要求では HTTPS を使用します。 このシナリオをサポートするには、ポート 80 (HTTP) 用の web 公開ルールを使用してリバースプロキシを構成する必要があります。 詳細については、「 <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Lync Server 2013 でモビリティのリバースプロキシを構成</A>する」の「ポート80用の web 公開ルールを作成するには」を参照してください。 同じドメインへの CNAME リダイレクションは HTTPS 経由でサポートされています。 この場合、宛先ドメインの証明書は元のドメインを対象としています。



</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での、モビリティに合わせたリバース プロキシの構成](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)  


[証明書の概要-Lync Server 2013 での自動検出](lync-server-2013-certificate-summary-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

