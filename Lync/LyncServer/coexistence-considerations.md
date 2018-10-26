---
title: 共存の考慮事項
TOCTitle: 共存の考慮事項
ms:assetid: 9d1a3c0f-492a-4e37-bc2f-63509e328785
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205131(v=OCS.15)
ms:contentKeyID: 48272987
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 共存の考慮事項

 

_**トピックの最終更新日:** 2012-10-06_

移行が完了すると、存在するのは Lync Server 2013、 常設チャット サーバー プールのみになるため、従来の展開を使用停止にすることができます。

移行が完了する前および現在の グループ チャット サーバーの展開を完全に使用停止にする前は、次の展開を使用できます。

  - Lync Server 2013、 常設チャット サーバー プール。 Lync Server 2013 プールに所属している必要があります。

  - Lync Server 2010、グループ チャット プール。 Lync Server 2010 プールに所属している必要があります。

  - Office Communications Server 2007 R2グループ チャット プール。 Office Communications Server 2007 R2 プールに所属している必要があります。

これらの展開は共存できますが、カテゴリ、ルーム、およびアドイン間のやり取りはできません。

手動構成を使用すると、従来のクライアント ( グループ チャット クライアント) で一度に 1 つのプールに接続できます ( Office Communications Server 2007 R2、 Lync Server 2010、グループ チャット、または Lync Server 2013 のプール)。

Lync 2013 (クライアント) がやり取りできるのは、 Lync Server 2013、 常設チャット サーバー プールだけです。従来の グループ チャット サーバー プールとやり取りすることはできません。 Lync 2013 (クライアント) で 常設チャットを使用するには、ユーザーが Lync 2013 に所属していて、ポリシーによって有効になっている必要があります。

