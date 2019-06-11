---
title: 'Lync Server 2013: モビリティの証明書の要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate requirements for mobility
ms:assetid: bb0e97af-cf60-4271-a0ab-654429d884ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690044(v=OCS.15)
ms:contentKeyID: 48185251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f62b05fd77151250e352c62cad7084d1bb90926
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840651"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-mobility-in-lync-server-2013"></a>Lync Server 2013 のモビリティの証明書の要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-06-24_

モバイルクライアントの自動検出をサポートし、モバイルクライアントの自動検出をサポートしている場合は、モバイルクライアントからのセキュリティで保護された接続をサポートするために、証明書に特定のサブジェクト代替名エントリを含める必要があります。

次の証明書に対して自動検出を行うには、サブジェクトの代替名エントリを含める必要があります。

  - ディレクター プール

  - フロントエンド プール

  - リバース プロキシ

このセクションでは、自動検出用に証明書に必要なサブジェクトの代替名エントリについて説明します。

<div>


> [!NOTE]  
> 内部証明機関を使った証明書の再発行は、通常は単純なプロセスですが、複数のサブジェクト代替名エントリをリバースプロキシによって使用されるパブリック証明書に追加するのはコストがかかることがあります。 多数の SIP ドメインがあり、サブジェクトの代替名を追加した場合は、HTTPS (既定の構成) を使う代わりに、最初の自動検出サービス要求に対して HTTP を使うようにリバースプロキシを構成できます。 詳細については、「 <A href="lync-server-2013-technical-requirements-for-mobility.md">Lync Server 2013 でのモビリティの技術要件</A>」を参照してください。



</div>

### <a name="director-pool-certificate-requirements"></a>ディレクタープール証明書の要件

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>説明</th>
<th>サブジェクトの代替名エントリ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>内部自動検出サービス URL</p></td>
<td><p>SAN = lyncdiscoverinternal。&lt;sipdomain&gt;</p></td>
</tr>
<tr class="even">
<td><p>外部自動検出サービスの URL</p></td>
<td><p>SAN = lyncdiscover。&lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> または、SAN = * を使用することもできます。&lt;sipdomain&gt;



</div>

### <a name="front-end-pool-certificate-requirements"></a>フロントエンドプール証明書の要件

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>説明</th>
<th>サブジェクトの代替名エントリ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>内部自動検出サービス URL</p></td>
<td><p>SAN = lyncdiscoverinternal。&lt;sipdomain&gt;</p></td>
</tr>
<tr class="even">
<td><p>外部自動検出サービスの URL</p></td>
<td><p>SAN = lyncdiscover。&lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> または、SAN = * を使用することもできます。&lt;sipdomain&gt;



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a>リバースプロキシ (パブリック CA) 証明書の要件

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>説明</th>
<th>サブジェクトの代替名エントリ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部自動検出サービスの URL</p></td>
<td><p>SAN = lyncdiscover。&lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> この SAN を、リバースプロキシの SSL リスナーに割り当てられている証明書に割り当てます。



</div>

<div>


> [!NOTE]  
> リバースプロキシリスナーには、外部 Web サービスの URL (たとえば、オプションのディレクターを展開した場合は、SAN = lyncwebextpool01、dirwebexternal.contoso.com など) のサブジェクト代替名があります。



</div>

</div>

<span> </span>

</div>

</div>

</div>

