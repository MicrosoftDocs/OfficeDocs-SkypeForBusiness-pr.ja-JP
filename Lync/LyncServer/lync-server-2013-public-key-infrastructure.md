---
title: 'Lync Server 2013: 公開キー基盤'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Public Key Infrastructure for Lync Server 2013
ms:assetid: 737c8a25-23e9-4494-ab76-5a7b729b44ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481131(v=OCS.15)
ms:contentKeyID: 59893870
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63ba5224d6663050295c5fddf9ea08e230f78506
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152291"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="public-key-infrastructure-for-lync-server-2013"></a>Lync Server 2013 の公開キー基盤

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-11-13_

Microsoft Lync Server 2013 は、サーバー認証に証明書を使用し、クライアントとサーバーの間、およびさまざまなサーバーの役割間の信頼チェーンを確立します。 Windows Server 2012 R2、Windows server 2012、Windows Server 2008 R2、Windows Server 2008、および Windows Server 2003 公開キー基盤 (PKI) は、この信頼チェーンを確立して検証するためのインフラストラクチャを提供します。

証明書とはデジタル ID です。 証明書は、名前によってサーバーを識別し、そのプロパティを指定します。 証明書の情報が有効であることを確認するには、サーバーに接続するクライアントまたは他のサーバーによって信頼されている CA が証明書を発行する必要があります。 サーバーがプライベート ネットワーク上の他のクライアントおよびサーバーとのみ接続する場合は、CA はエンタープライズ CA で問題ありません。 サーバーがプライベート ネットワーク外のエンティティと対話する場合は、パブリック CA が必要な可能性があります。

証明書の情報が有効であっても、証明書を提示しているサーバーが、実際に証明書によって提示されているサーバーであることを確認する手段が必要です。ここで Windows PKI が役立ちます。

各証明書は、公開キーにリンクされています。証明書で名前が指定されているサーバーには、そのサーバーのみが知る、対応する秘密キーがあります。接続しようとしているクライアントまたはサーバーは、公開キーを使用して無作為な情報の断片を暗号化し、それをサーバーに送信します。サーバーがその情報を復号化し、プレーン テキストに戻すと、接続しようとしているエンティティは、証明書の秘密キーをサーバーが保持していること、つまり、そのサーバーが証明書で指定されていることを確認できます。

<div>


> [!NOTE]  
> すべてのパブリック Ca が Lync Server 2013 証明書の要件に準拠しているわけではありません。 認定されているパブリック CA ベンダーの一覧を参照して、パブリック証明書のニーズに合ったベンダーを探すことをお勧めします。 詳細については、「統合コミュニケーション<A href="https://go.microsoft.com/fwlink/p/?linkid=140898">https://go.microsoft.com/fwlink/p/?LinkId=140898</A>証明書パートナー」を参照してください。



</div>

<div>

## <a name="crl-distribution-points"></a>CRL 配布ポイント

Lync Server 2013 には、すべてのサーバー証明書に1つ以上の証明書失効リスト (CRL) 配布ポイントが含まれている必要があります。 CRL 配布ポイント (Cdp) は、発行後に証明書が失効しておらず、証明書が有効期間内にあることを確認するために、Crl をダウンロードできる場所です。 CRL 配布ポイントは、証明書のプロパティに URL として記載されています。通常、HTTP はセキュリティで保護されています。

</div>

<div>

## <a name="enhanced-key-usage"></a>拡張キー使用法

Lync Server 2013 では、サーバー認証のために拡張キー使用法 (EKU) をサポートするすべてのサーバー証明書が必要です。 サーバー認証の EKU フィールドを構成することは、証明書がサーバーの認証を目的として有効であることを意味します。 この EKU は、MTLS にとって不可欠です。 EKU に複数のエントリを含めることができます。これにより、複数の目的に対して証明書を有効にできます。

<div>


> [!NOTE]  
> Live Communications Server 2003 および Live Communications Server 2005 からの送信 MTLS 接続には、クライアント認証 EKU が必要ですが、これは不要になりました。 ただし、この EKU は、パブリック IM 接続を使用して AOL に接続するエッジサーバー上に存在する必要があります。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

