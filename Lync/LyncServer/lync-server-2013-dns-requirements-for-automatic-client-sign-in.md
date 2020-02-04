---
title: 'Lync Server 2013: 自動クライアントサインインの DNS 要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for automatic client sign-in
ms:assetid: 3bcd4bb3-a022-4ffa-b005-1a95ad2b1796
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425884(v=OCS.15)
ms:contentKeyID: 48183873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d033621382587367630d9119c2176e976cb2c2d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739157"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-automatic-client-sign-in-in-lync-server-2013"></a>Lync Server 2013 での自動クライアントサインインの DNS 要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-06-19_

このセクションでは、自動クライアントサインインに必要なドメインネームシステム (DNS) レコードについて説明します。 Standard Edition サーバーまたはフロントエンドプールを展開するときに、自動検出を使用して適切な Standard Edition サーバーまたはフロントエンドプールにサインインするようにクライアントを構成することができます。 クライアントが Lync Server 2013 に手動で接続することを計画している場合は、このトピックをスキップできます。

自動クライアントサインインをサポートするには、次のことを行う必要があります。

  - クライアントのサインイン要求の配布と認証を行う単一のサーバーまたはプールを指定します。 組織内のユーザーをホストしている既存のサーバーまたはプールの場合もあれば、ユーザーをホストしない場合は、専用のサーバーまたはプールを指定することもできます。 高可用性を実現するには、この関数のフロントエンドプールを指定することをお勧めします。

  - このサーバーまたはプールの自動クライアントサインインをサポートするための内部 DNS SRV レコードを作成します。
    
    <div>
    

    > [!NOTE]  
    > 次のレコード要件では、SIP ドメインは、ユーザーに割り当てられている SIP Uri のホスト部分を指します。 たとえば、SIP Uri の形式が * @contoso の場合は、contoso.com が SIP ドメインです。 SIP ドメインは、多くの場合、内部の Active Directory ドメインとは異なります。 組織では、複数の SIP ドメインをサポートすることもできます。

    
    </div>

クライアントの自動構成を有効にするには、次のレコードのいずれかを、Lync からのサインイン要求を配信するフロントエンドプールまたは Standard Edition サーバーの完全修飾ドメイン名 (FQDN) にマップする内部 DNS SRV レコードを作成する必要があります。客

  - \_sipinternaltls.\_tcp。\<ドメイン\> -内部 TLS 接続の場合

フロントエンドプールまたは Standard Edition サーバー用の SRV レコードを1つだけ作成する必要があります。また、その場合は、サインイン要求を配布します。

次の表では、contoso.com と retail.contoso.com の SIP ドメインをサポートする架空の会社の Contoso に必要なレコードの例を示します。

### <a name="example-of-dns-records-required-for-automatic-client-sign-in-with-multiple-sip-domains"></a>複数の SIP ドメインでの自動クライアントサインインに必要な DNS レコードの例

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>サインイン要求の配布に使用するフロントエンドプールの FQDN</th>
<th>SIP ドメイン</th>
<th>DNS SRV レコード</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>pool01.contoso.com</p></td>
<td><p>contoso.com</p></td>
<td><p>Pool01.contoso.com にマップされる、ポート5061経由の _sipinternaltls _tcp の SRV レコード</p></td>
</tr>
<tr class="even">
<td><p>pool01.contoso.com</p></td>
<td><p>retail.contoso.com</p></td>
<td><p>Pool01.contoso.com にマップされる、ポート5061経由の _sipinternaltls の _tcp の SRV レコード</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 既定では、DNS レコードのクエリは、ユーザー名と SRV レコードのドメイン間の厳密なドメイン名の照合に従います。 クライアントの DNS クエリでサフィックスの照合を使う場合は、DisableStrictDNSNaming グループポリシーを構成できます。 詳細については、計画ドキュメントの「 <A href="lync-server-2013-planning-for-clients-and-devices.md">Lync Server 2013 でのクライアントとデバイスの計画</A>」を参照してください。



</div>

<div>

## <a name="example-of-the-certificates-and-dns-records-required-for-automatic-client-sign-in"></a>自動クライアントサインインに必要な証明書と DNS レコードの例

この例では、前の表に示した例と同じ名前を使用します。 Contoso 組織では、contoso.com と retail.contoso.com の SIP ドメインをサポートしており、すべてのユーザーが SIP URI を次のいずれかの形式で使用しています。

  - \<ユーザー\>@retail contoso.com

  - \<ユーザー\>@contoso .com

</div>

</div>

<span> </span>

</div>

</div>

</div>

