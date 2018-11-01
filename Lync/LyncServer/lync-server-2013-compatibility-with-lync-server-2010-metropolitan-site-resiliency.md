---
title: Lync Server 2013 と Lync Server 2010 大都市サイト復元の互換性
TOCTitle: Lync Server 2010 大都市サイト復元
ms:assetid: 18673ff6-b664-4a57-a89b-cbda8b129e6a
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204715(v=OCS.15)
ms:contentKeyID: 48271395
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2010 大都市サイト復元

 

_**トピックの最終更新日:** 2014-03-19_

Lync Server 2010 でサポートされていた大都市サイト復元ソリューションは、Lync Server 2013 ではサポートされません。このソリューションでは、1 つのフロントエンド プールを同じ大都市圏内の 2 か所のデータ センターにまたがって展開する必要がありました。

大都市サイト復元ソリューションは、1 つのデータセンターがすべて失われた場合の復旧を目的としています。2 か所のデータセンターにまたがってプールを展開する場合、通常、フロント エンドの半分を 1 つのデータセンターに設定し、残りの半分を 2 つ目のデータセンターに設定します。1 つのデータセンターがすべて失われると、フロント エンド サーバーの半分が失われることになり、それによって、Lync Server 2013 のフロント エンド プールの新しい分散システム モデルに関して問題が発生することがあります。詳細については、「[Lync Server 2013 フロントエンド サーバー、インスタント メッセージングおよびプレゼンスのトポロジおよびコンポーネント](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)」を参照してください。

