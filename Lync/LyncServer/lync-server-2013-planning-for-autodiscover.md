---
title: 'Lync Server 2013: 自動検出の計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Autodiscover
ms:assetid: 51f1ff94-1d64-4e6d-a878-b86fa07edc2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945628(v=OCS.15)
ms:contentKeyID: 51541474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 709b27059e1908a45b4b473f5380215bbd499d27
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725527"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-autodiscover-in-lync-server-2013"></a>Lync Server 2013 での自動検出の計画

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-16_

自動検出は、Lync server 2010 向けの累積的な更新プログラム (2011 年11月) で Lync Server に導入されました。 自動検出の最初の実装の主な目的は、モバイルサービス (Mcx) を見つけるために Lync Mobile の手段を提供することでした。 Lync Server 2013 の自動検出サービスは、すべてのクライアントがサーバーおよびユーザーサービスを検索するために使用するサービスになりました。 Microsoft Lync Server 2013 自動検出サービスは、取締役およびフロントエンドサーバーで実行されます。

<div>


> [!TIP]  
> 自動検出とクライアントへの伝達についての技術的な理解については、「 <A href="lync-server-2013-understanding-autodiscover.md">Lync Server 2013 での自動検出につい</A>て」を参照してください。<BR>機動性は、依然として個別のシナリオであり、モビリティサービスでは引き続き特別な計画が必要です。 詳細については、「 <A href="lync-server-2013-planning-for-mobility.md">Lync Server 2013 でのモビリティの計画</A>」を参照してください。



</div>

Lync Server 2010 で自動検出が導入された場合、既存のサーバー展開に対して証明書の変更が必要になるサービスを実装するために必要な侵害がありました。 自動検出は、HTTPS のポート TCP 443 または HTTP のポート TCP 80 経由で使うことができます。 HTTPS を使用することに決められた場合、リバースプロキシ、監督、フロントエンドサーバー上の証明書は、必要な`lyncdiscover.<domain>` `lyncdiscoverinternal.<domain>` DNS レコードと DNS レコードに対応するために再発行する必要があります。 HTTP を使用すると判断された場合は、証明書の既存の名前を使用するために DNS CNAME (エイリアス) レコードを使用することで、証明書の再発行を回避することができます。 HTTP では、最初の通信が暗号化されていないことを意味します。

Lync Server 2013 ではすべてのクライアントに対して自動検出が使用されるため、主なシナリオとしては、HTTPS のみを使用し、lyncdiscover で証明書を作成することをお勧めします。\<リバース\>プロキシ、ディレクター、フロントエンドサーバーの構成の一部としてのドメイン。 自動検出を Lync Server 2010 からアップグレードされた展開に実装する場合は、HTTP を使用して、証明書の再発行を回避することができます。 両方のシナリオに関するガイダンスについては、次のセクションで説明します。

<div>


> [!IMPORTANT]  
> 外部 web サービス公開ルールによって使用される証明書のサブジェクト代替名リストには、lyncdiscover が含まれている必要があり<EM>ます。&lt;組織&gt; </EM>内の各 SIP ドメインの sipdomain エントリ。 ディレクター、フロントエンドサーバー、リバースプロキシに必要な件名の代替名エントリの詳細については、「<A href="lync-server-2013-certificate-summary-autodiscover.md">証明書の概要-Lync Server 2013 での自動検出</A>」を参照してください。



</div>

<div>

## <a name="in-this-section"></a>このセクション中

  - [証明書の概要-Lync Server 2013 での自動検出](lync-server-2013-certificate-summary-autodiscover.md)

  - [ポートの概要-Lync Server 2013 での自動検出](lync-server-2013-port-summary-autodiscover.md)

  - [DNS 概要-Lync Server 2013 での自動検出](lync-server-2013-dns-summary-autodiscover.md)

  - [ハイブリッドおよび分割ドメイン-Lync Server 2013 での自動検出](lync-server-2013-hybrid-and-split-domain-autodiscover.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

