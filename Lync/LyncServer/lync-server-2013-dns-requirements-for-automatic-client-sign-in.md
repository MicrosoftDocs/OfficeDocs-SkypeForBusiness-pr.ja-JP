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
ms.openlocfilehash: e49d50173439e36bd5bb7f35f668837fe04b46b7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204843"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-automatic-client-sign-in-in-lync-server-2013"></a>Lync Server 2013 での自動クライアントサインインの DNS 要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-06-19_

ここでは、自動クライアント サインインに必要なドメイン ネーム システム (DNS) レコードについて説明します。 Standard Edition サーバーまたはフロントエンド プールを展開するときに、クライアントが自動検出を使用して適切な Standard Edition サーバーまたはフロントエンド プールにサインインするように構成できます。 クライアントが Lync Server 2013 に手動で接続することを計画している場合は、このトピックを省略できます。

自動クライアント サインインをサポートするには、次のことを行う必要があります。

  - クライアントのサインイン要求を分散および認証する 1 つのサーバーまたはプールを指定します。 組織内のユーザーをホストする既存のサーバーまたはプールを使用できます。ユーザーをホストしない、この目的専用のサーバーまたはプールを指定することもできます。 可用性を高めるには、この機能用のフロントエンド プールを指定することをお勧めします。

  - このサーバーまたはプールで自動クライアント サインインをサポートする内部 DNS SRV レコードを作成します。
    
    <div>
    

    > [!NOTE]  
    > 次のレコード要件では、SIP ドメインは、ユーザーに割り当てられる SIP URI のホスト部分です。たとえば、SIP URI が *@contoso.com という形式の場合は、contoso.com が SIP ドメインです。SIP ドメインは、内部 Active Directory ドメインと異なる場合がよくあります。また、1 つの組織が複数の SIP ドメインをサポートする場合もあります。

    
    </div>

クライアントの自動構成を有効にするには、次のレコードのいずれかを、Lync からのサインイン要求を配布するフロントエンドプールまたは Standard Edition サーバーの完全修飾ドメイン名 (FQDN) にマップする内部 DNS SRV レコードを作成する必要があります。クライアント

  - \_sipinternaltls.\_tcp。\<ドメイン\> -内部 TLS 接続の場合

SRV レコードは、サインイン要求を分散させるフロントエンド プールまたは Standard Edition サーバーに対して 1 つだけ作成します。

次の表は、架空の Contoso という会社に必要なレコードの例をいくつか示しています。この会社では、contoso.com と retail.contoso.com という SIP ドメインをサポートしています。

### <a name="example-of-dns-records-required-for-automatic-client-sign-in-with-multiple-sip-domains"></a>複数の SIP ドメインを持つクライアントの自動サインインに必要な DNS レコードの例

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>サインイン要求の分散に使用されるフロントエンド プールの FQDN</th>
<th>SIP ドメイン</th>
<th>DNS SRV レコード</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>pool01.contoso.com</p></td>
<td><p>contoso.com</p></td>
<td><p>pool01.contoso.com にマップするポート 5061 経由の _sipinternaltls._tcp.contoso.com ドメイン用の SRV レコード</p></td>
</tr>
<tr class="even">
<td><p>pool01.contoso.com</p></td>
<td><p>retail.contoso.com</p></td>
<td><p>pool01.contoso.com にマップするポート 5061 経由の _sipinternaltls._tcp.retail.contoso.com ドメイン用 SRV レコード</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 既定では、DNS レコードのクエリは、ユーザー名のドメインと SRV レコードの間で一致する厳密なドメイン名に従います。 サフィックスの一致を使用するクライアント DNS クエリを使用する場合は、DisableStrictDNSNaming グループ ポリシーを構成できます。 詳細については、「計画」のドキュメントの「 <A href="lync-server-2013-planning-for-clients-and-devices.md">planning for clients and devices In Lync Server 2013</A> 」を参照してください。



</div>

<div>

## <a name="example-of-the-certificates-and-dns-records-required-for-automatic-client-sign-in"></a>自動クライアント サインインに必要な証明書および DNS レコードの例

この例では、前の表と同じ例の名前を使用します。 Contoso 社の組織は contoso.com および retail.contoso.com の SIP ドメインをサポートし、そのユーザー全員の SIP URI が次のいずれかの形式となります。

  - \<ユーザー\>@retail contoso.com

  - \<ユーザー\>@contoso .com

</div>

</div>

<span> </span>

</div>

</div>

</div>

