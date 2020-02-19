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
ms.openlocfilehash: d8115cb68638e2db1db93c1afb96d12d96d2ed78
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139920"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-autodiscover-in-lync-server-2013"></a>Lync Server 2013 での自動検出の計画

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-16_

Lync server 2010 の累積的な更新プログラムで、Lync Server の自動検出が導入されました。11月2011。 この自動検出の初期実装の主な目的は、Lync Mobile が Mobility service (Mcx) を特定する手段を提供することでした。 Lync Server 2013 の自動検出サービスは、サーバーとユーザーのサービスを検索するためにすべてのクライアントが使用するサービスになりました。 Microsoft Lync Server 2013 自動検出サービスは、ディレクターおよびフロントエンドサーバー上で実行されます。

<div>


> [!TIP]  
> 自動検出とクライアントへの通知についてのより技術的な知識については、「 <A href="lync-server-2013-understanding-autodiscover.md">Lync Server 2013 の自動検出につい</A>て」を参照してください。<BR>モビリティは依然として別個のシナリオであり、Mobility service ではまだ特別な計画が必要です。 詳細については、「 <A href="lync-server-2013-planning-for-mobility.md">Lync Server 2013 でのモビリティの計画</A>」を参照してください。



</div>

Lync Server 2010 で自動検出が導入された場合、既存のサーバー展開に対する証明書の変更を必要とするサービスを実装するために必要な妥協が行われました。 HTTPS のポート TCP 443、または HTTP のポート TCP 80 経由で自動検出を使用することができます。 HTTPS を使用することを決定した場合は、必要な`lyncdiscover.<domain>`および`lyncdiscoverinternal.<domain>` DNS レコードを格納するために、リバースプロキシ、ディレクター、フロントエンドサーバーの証明書を再発行する必要がありました。 HTTP を使用することを決定した場合は、証明書の既存の名前を使用するために DNS の CNAME (またはエイリアス) レコードを使用して、証明書の再発行を回避することができます。 HTTP を使用することは、初期通信が暗号化されていなかったことを意味します。

Lync Server 2013 はすべてのクライアントに対して自動検出を使用するため、主なシナリオは、HTTPS のみを使用して lyncdiscover で証明書を作成することです。\<リバース\>プロキシ、ディレクター、フロントエンドサーバーの構成の一部としてのドメイン。 Lync Server 2010 からアップグレードされた展開に自動検出を実装する場合、HTTP を使用して証明書の再発行を回避することができます。 両方のシナリオのガイダンスについては、以下のセクションで説明します。

<div>


> [!IMPORTANT]  
> 外部 web サービス公開ルールで使用される証明書のサブジェクトの別名リストには、lyncdiscover が含まれている必要があり<EM>ます。&lt;組織&gt; </EM>内の各 SIP ドメインの microsoft.rtc.management.xds.sipdomain エントリ。 ディレクター、フロントエンドサーバー、およびリバースプロキシで必要とされるサブジェクトの別名エントリの詳細については、「<A href="lync-server-2013-certificate-summary-autodiscover.md">証明書の概要-Lync Server 2013 での自動検出</A>」を参照してください。



</div>

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [証明書の概要-Lync Server 2013 での自動検出](lync-server-2013-certificate-summary-autodiscover.md)

  - [ポートの概要-Lync Server 2013 での自動検出](lync-server-2013-port-summary-autodiscover.md)

  - [DNS の概要-Lync Server 2013 での自動検出](lync-server-2013-dns-summary-autodiscover.md)

  - [Lync Server 2013 でのハイブリッドおよびスプリットドメインの自動検出](lync-server-2013-hybrid-and-split-domain-autodiscover.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

