---
title: 'Lync Server 2013: 公開キー基盤'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Public Key Infrastructure for Lync Server 2013
ms:assetid: 737c8a25-23e9-4494-ab76-5a7b729b44ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481131(v=OCS.15)
ms:contentKeyID: 59893870
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0fb79340b29ab4bfa6942d2b2cb62483c79b4ce9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823743"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="public-key-infrastructure-for-lync-server-2013"></a>Lync Server 2013 用の公開キー基盤

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-11-13_

Microsoft Lync Server 2013 は、サーバー認証には証明書を使用し、クライアントとサーバー間、およびサーバーのさまざまな役割間で信頼のチェーンを確立します。 Windows Server 2012 R2、Windows Server 2012、windows Server 2008 R2、windows server 2008、および Windows Server 2003 公開キー基盤 (PKI) は、この信頼チェーンを確立して検証するためのインフラストラクチャを提供します。

証明書とはデジタル ID です。証明書は、名前によってサーバーを識別し、そのプロパティを指定します。証明書の情報が有効であるためには、サーバーに接続するクライアントやその他のサーバーが信頼する CA から証明書が発行されている必要があります。サーバーがプライベート ネットワーク上の他のクライアントおよびサーバーとのみ接続する場合は、CA はエンタープライズ CA で問題ありません。サーバーがプライベート ネットワーク外のエンティティと対話する場合は、パブリック CA が必要な可能性があります。

証明書の情報が有効であっても、証明書を提示しているサーバーが、実際に証明書によって提示されているサーバーであることを確認する手段が必要です。ここで Windows PKI が役立ちます。

各証明書は、公開キーにリンクされています。証明書で名前が指定されているサーバーには、そのサーバーのみが知る、対応する秘密キーがあります。接続しようとしているクライアントまたはサーバーは、公開キーを使用して無作為な情報の断片を暗号化し、それをサーバーに送信します。サーバーがその情報を復号化し、プレーン テキストに戻すと、接続しようとしているエンティティは、証明書の秘密キーをサーバーが保持していること、つまり、そのサーバーが証明書で指定されていることを確認できます。

<div>


> [!NOTE]  
> すべてのパブリック Ca が Lync Server 2013 証明書の要件を満たしているわけではありません。 認定されているパブリック CA ベンダーの一覧を参照して、パブリック証明書のニーズに合ったベンダーを探すことをお勧めします。 詳細については、「ユニファイド<A href="http://go.microsoft.com/fwlink/p/?linkid=140898">http://go.microsoft.com/fwlink/p/?LinkId=140898</A>コミュニケーションの証明書パートナー」を参照してください。



</div>

<div>

## <a name="crl-distribution-points"></a>CRL 配布ポイント

Lync Server 2013 では、すべてのサーバー証明書に1つ以上の証明書失効リスト (CRL) 配布ポイントが含まれている必要があります。 CRL 配布ポイント (CDP) とは、証明書の発行後にそれが失効していないこと、および証明書が有効期限内にあることを確認するために、CRL をダウンロードできる場所です。 CRL 配布ポイントは、URL として証明書のプロパティに記述され、通常、セキュア HTTP です。

</div>

<div>

## <a name="enhanced-key-usage"></a>拡張キー使用法

Lync Server 2013 では、サーバー認証のために、すべてのサーバー証明書で拡張キー使用法 (EKU) がサポートされている必要があります。 サーバー認証用に EKU フィールドを構成することは、サーバーの認証に対して、その証明書が有効であることを意味します。 この EKU は、MTLS には不可欠です。 EKU には、複数のエントリを指定し、複数の目的に対して証明書を有効にできます。

<div>


> [!NOTE]  
> Live Communications Server 2003 および Live Communications Server 2005 からの送信 MTLS 接続には、クライアント認証 EKU が必要ですが、これは不要になりました。 ただし、パブリック IM 接続を使って AOL に接続するエッジサーバーには、この EKU が存在している必要があります。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

