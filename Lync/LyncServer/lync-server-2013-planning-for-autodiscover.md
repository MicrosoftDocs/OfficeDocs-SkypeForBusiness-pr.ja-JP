---
title: 自動検出の計画
TOCTitle: 自動検出の計画
ms:assetid: 51f1ff94-1d64-4e6d-a878-b86fa07edc2d
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ945628(v=OCS.15)
ms:contentKeyID: 52056595
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 自動検出の計画

 

_**トピックの最終更新日:** 2013-02-16_

自動検出は、Lync Server 2010 の累積的な更新プログラム: 2011 年 11 月で Lync Server を対象に導入されました。自動検出を最初に実装した主な目的は、Mobility Service (Mcx) を特定する手段を Lync Mobile に提供することでした。Lync Server 2013 の自動検出サービスは、すべてのクライアントが、サーバーとユーザー サービスを特定する目的で使用されます。この Microsoft Lync Server 2013 自動検出サービスは、ディレクターおよびフロント エンド サーバーで実行されます。


> [!TIP]
> 自動検出とクライアントへの通知内容を技術的な側面からさらに理解するには、「<A href="lync-server-2013-understanding-autodiscover.md">自動検出について</A>」を参照してください。<BR>モビリティのシナリオは、以前と同様に他とは異なっています。また、モビリティ サービスには引き続き特別な計画が必要です。詳細については、「<A href="lync-server-2013-planning-for-mobility.md">Lync Server 2013 でのモビリティの計画</A>」を参照してください。



Lync Server 2010 で自動検出が導入されたとき、既存のサーバー展開に対して証明書を変更しなければならない可能性があるサービスを実装するには妥協が必要でした。自動検出は、HTTPS の場合はポート TCP 443 経由で、HTTP の場合はポート TCP 80 経由で使用できました。HTTPS を使用する場合、リバース プロキシ、ディレクター、およびフロント エンド サーバーに必要な `lyncdiscover.<domain>` および `lyncdiscoverinternal.<domain>` DNS レコードに対応するには、これらの証明書を再発行する必要がありました。HTTP を使用すれば、DNS CNAME (エイリアス) レコードを使用することで、証明書を再発行せずにその証明書の既存の名前を使用できましたが、HTTP を使用するということは、最初の通信が暗号化されないことを意味します。

Lync Server 2013 では、すべてのクライアントに対して自動検出を使用するので、HTTPS のみを使用し、リバース プロキシ、ディレクター、およびフロント エンド サーバーの構成の一部として lyncdiscover.\<domain\> で証明書を作成するのが主なシナリオです。Lync Server 2010 からアップグレードされた展開に自動検出を実装する場合は、証明書の再発行の手間を省くために HTTP を使用することをお勧めします。両方のシナリオのガイダンスについては、以下のセクションを参照してください。


> [!IMPORTANT]
> 外部 Web サービス公開ルールで使用される証明書上のサブジェクトの別名リストには、組織内の各 SIP ドメインの lyncdiscover.&lt;sipdomain&gt; エントリが含まれる必要があります。ディレクター、フロントエンド サーバー、およびリバース プロキシで必要とされるサブジェクトの別名エントリの詳細については、「<A href="lync-server-2013-certificate-summary-autodiscover.md">証明書の概要 - 自動検出</A>」を参照してください。



## このセクション中

  - [証明書の概要 - 自動検出](lync-server-2013-certificate-summary-autodiscover.md)

  - [Lync Server 2013 でのポートの概要 - 自動検出](lync-server-2013-port-summary-autodiscover.md)

  - [Lync Server 2013 での DNS 概要 - 自動検出](lync-server-2013-dns-summary-autodiscover.md)

  - [ハイブリッドおよび分割ドメイン - 自動検出](lync-server-2013-hybrid-and-split-domain-autodiscover.md)

