---
title: 'Lync Server 2013: IPv6 の移行および共存の検討事項'
TOCTitle: IPv6 の移行および共存の検討事項
ms:assetid: 8c769c4f-c8a9-4cbf-9080-beee3be9848a
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205068(v=OCS.15)
ms:contentKeyID: 48272821
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 における IPv6 の移行および共存の検討事項

 

_**トピックの最終更新日:** 2012-06-14_

IP バージョン 6 (IPv6) は、Lync Server 2010 または Office Communications Server ではサポートされません。実験的に使用する場合は、Lync Server 2010 と Lync Server 2013 のデュアルスタックの共存をテストできます。プールで IPv6 (デュアルスタック ネットワーク) を有効にする場合は、その前に、特定のセントラル サイトのすべてのプールを Lync Server 2013 にアップグレードすることをお勧めします。IPv6 に対応したプールのみを構成する必要がある場合は、テスト用のラボ環境に IPv6 専用のプールを設定することをお勧めします。

次のシナリオは、移行と共存でサポートされます。

  - IPv4 モードの Lync Server 2013、Lync Server 2010、および Office Communications Server 2007 R2 プールと、デュアルスタック モードの Lync Server 2013 が共存する。

  - IPv6 専用モードの Lync Server 2013 プール (サイロ型の IPv6 専用プールの場合)。

