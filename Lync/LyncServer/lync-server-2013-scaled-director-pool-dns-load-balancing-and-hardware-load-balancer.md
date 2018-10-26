---
title: 'Lync Server 2013: 拡張ディレクター プール - DNS 負荷分散とロード バランサー機器'
TOCTitle: 拡張ディレクター プール - DNS 負荷分散とロード バランサー機器
ms:assetid: a1f6ffc0-9e6e-4217-a923-025c9679e154
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205142(v=OCS.15)
ms:contentKeyID: 48273036
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 拡張ディレクター プール - Lync Server 2013 の DNS 負荷分散とロード バランサー機器

 

_**トピックの最終更新日:** 2012-10-22_

一般に、拡張 ディレクター プールには、追加キャパシティへの対応と高可用性の実現のために複数の ディレクターが展開されます。このような環境では、クライアントおよびサーバーの通信をプールのすべてのメンバーに分散する負荷分散が必要です。ディレクターは、フロント エンド プールなどの Web サービスをホストします。負荷分散を提供するには、ロード バランサー機器またはドメイン ネーム システム (DNS) 負荷分散とロード バランサー機器のどちらかを使用できます。Web サービスにはロード バランサー機器が必要です。DNS 負荷分散だけでは、Web サービスに必要な機能を提供できません。

次のトピックでは、DNS 負荷分散とロード バランサー機器を使用した ディレクター プールの展開を計画するにあたっての検討事項について説明します。ディレクター プールでロード バランサー機器のみを使用し、DNS 負荷分散を使用しない場合については、そのようなトポロジを計画するにあたっての必要事項について説明する「[拡張ディレクター プール - Lync Server 2013 のハードウェア負荷分散](lync-server-2013-scaled-director-pool-hardware-load-balancer.md)」を参照してください。

![拡張ディレクター プール](images/JJ205142.35a78a7a-b781-4c8f-951e-168451ba6a65(OCS.15).jpg "拡張ディレクター プール")

## このセクション中

  - [証明書の概要 - Lync Server 2013 の DNS および HLB による負荷分散](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [ポートの概要 - Lync Server 2013 における DNS および HLB による負荷分散](lync-server-2013-port-summary-dns-and-hlb-load-balanced.md)

  - [DNS の概要 - Lync Server 2013 での DNS と HLB 負荷分散](lync-server-2013-dns-summary-dns-and-hlb-load-balanced.md)

