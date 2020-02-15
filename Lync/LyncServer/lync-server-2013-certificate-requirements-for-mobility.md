---
title: 'Lync Server 2013: モビリティの証明書の要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for mobility
ms:assetid: bb0e97af-cf60-4271-a0ab-654429d884ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690044(v=OCS.15)
ms:contentKeyID: 48185251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bbf7dd0f3ce9868fbeac5c757fce5371ad77fba4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038419"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-mobility-in-lync-server-2013"></a>Lync Server 2013 でのモビリティの証明書要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-06-24_

モビリティ機能を展開し、モバイルクライアントの自動検出をサポートする場合は、モバイルクライアントからのセキュリティで保護された接続をサポートするために、証明書に特定のサブジェクトの別名エントリを含める必要があります。

次の証明書に、自動検出のサブジェクトの別名エントリを含める必要があります。

  - ディレクター プール

  - フロント エンド プール

  - リバース プロキシ

このセクションでは、自動検出のために証明書で必要とされるサブジェクトの別名エントリについて説明します。

<div>


> [!NOTE]  
> 通常、内部の証明機関を使用した証明書の再発行は簡単なプロセスですが、サブジェクトの複数の別名エントリを、リバース プロキシで使用されるパブリック証明書に追加するには、高い費用がかかる可能性があります。 多数の SIP ドメインがあり、サブジェクトの別名が非常に高価になっている場合は、HTTPS (既定の構成) ではなく、最初の自動検出サービス要求に HTTP を使用するようにリバースプロキシを構成できます。 詳細については、「 <A href="lync-server-2013-technical-requirements-for-mobility.md">Lync Server 2013 でのモビリティの技術要件</A>」を参照してください。



</div>

### <a name="director-pool-certificate-requirements"></a>ディレクター プールの証明書の要件

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>説明</th>
<th>サブジェクト名の別名エントリ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>内部自動検出サービス URL</p></td>
<td><p>SAN = lyncdiscoverinternal。&lt;microsoft.rtc.management.xds.sipdomain&gt;</p></td>
</tr>
<tr class="even">
<td><p>外部自動検出サービス URL</p></td>
<td><p>SAN = lyncdiscover。&lt;microsoft.rtc.management.xds.sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> または、SAN = * を使用することもできます。&lt;microsoft.rtc.management.xds.sipdomain&gt;



</div>

### <a name="front-end-pool-certificate-requirements"></a>フロント エンド プールの証明書の要件

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>説明</th>
<th>サブジェクト名の別名エントリ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>内部自動検出サービス URL</p></td>
<td><p>SAN = lyncdiscoverinternal。&lt;microsoft.rtc.management.xds.sipdomain&gt;</p></td>
</tr>
<tr class="even">
<td><p>外部自動検出サービス URL</p></td>
<td><p>SAN = lyncdiscover。&lt;microsoft.rtc.management.xds.sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> または、SAN = * を使用することもできます。&lt;microsoft.rtc.management.xds.sipdomain&gt;



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a>リバース プロキシ (パブリック CA) の証明書の要件

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>説明</th>
<th>サブジェクト名の別名エントリ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部自動検出サービス URL</p></td>
<td><p>SAN = lyncdiscover。&lt;microsoft.rtc.management.xds.sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> リバースプロキシ上の SSL リスナーに割り当てられた証明書にこの SAN を割り当てます。



</div>

<div>


> [!NOTE]  
> リバースプロキシリスナーには、外部 Web サービスの URL (たとえば、SAN = lyncwebextpool01.contoso.com、およびオプションのディレクターを展開している場合は dirwebexternal.contoso.com) のサブジェクトの別名があります。



</div>

</div>

<span> </span>

</div>

</div>

</div>

