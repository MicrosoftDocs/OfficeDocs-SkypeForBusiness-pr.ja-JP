---
title: 'Lync Server 2013: IPv6 の技術要件'
TOCTitle: IPv6 の技術要件
ms:assetid: caff0123-ce41-4a62-87a0-00b1d118b72b
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205278(v=OCS.15)
ms:contentKeyID: 48273606
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の IPv6 の技術要件

 

_**トピックの最終更新日:** 2016-12-08_

Lync Server 2013 を IPv6 向けに構成する予定の場合は、以下の要件を考慮します。

  - Lync Server で IPv6 アドレスを使用するには、検出されて IPv6 アドレスに解決される必要のあるレコード用にドメイン ネーム システム (DNS) レコードを作成する必要があります。IPv6 DNS はホスト AAAA (クアッド A) レコードを使用します。展開内で IPv4 と IPv6 の両方を使用する場合は、IPv4 用のホスト A レコードと IPv6 用のホスト AAAA レコードの両方を構成し保持するのが最善の方法です。自身の展開を IPv6 に完全に移行した場合でも、IPv4 を使用する外部ユーザーのために IPv4 DNS ホスト レコードが引き続き必要となる場合があります。
    
    IPv6 DNS ホスト レコードは IPv6 の使用を始める前から展開できます。クライアントまたはサーバーが IPv6 を使用しない場合、そのレコードは参照されません。移行時のテクノロジは、どのレコードを使用するかを、移行テクノロジの構成およびポリシーに基づいて判断します。

  - 各 IPv6 アドレスはスコープを持ちます。IPv6 アドレス指定では 3 つのスコープを使用できます。IPv6 グローバル アドレス (パブリック IPv4 アドレスと同様)、IPv6 ユニーク ローカル アドレス (プライベート IPv4 アドレス範囲と同様)、IPv6 リンクローカル アドレス (IPv4 の Windows Server における自動プライベート IP アドレスと同様) の 3 つです。同一プール内のすべてのサーバーは同じスコープの IPv6 アドレスを持つ必要があります。


> [!IMPORTANT]
> IPv6 は複雑なトピックです。ネットワーク チームやインターネット プロバイダーと協力して慎重に計画し、 Windows Server レベル、および Lync Server 2013 レベルで割り当てるアドレスが想定どおりに機能するようにしてください。IPv6 のアドレス指定および計画に関する追加資料については、このトピックの最後にあるリンクを参照してください。



## 関連項目

#### その他のリソース

[IP Version 6 アドレス指定アーキテクチャ](http://tools.ietf.org/html/rfc4291)  
[IPv6 グローバル ユニキャスト アドレス形式](http://tools.ietf.org/html/rfc3587)  
[一意のローカル IPv6 ユニキャスト アドレス](http://tools.ietf.org/html/rfc4193)

