---
title: 'Lync Server 2013: IP とネットワーク プロトコルのサポート'
TOCTitle: IP とネットワーク プロトコルのサポート
ms:assetid: b0cffb10-3478-445c-89c7-8cb8b5027424
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412848(v=OCS.15)
ms:contentKeyID: 48273293
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での IP とネットワーク プロトコルのサポート

 

_**トピックの最終更新日:** 2016-12-08_

Lync Server 2013 は、次の IP プロトコルおよびネットワーク プロトコルをサポートします。

  - **IP プロトコル。**   Lync Server 2013 は、サーバー ネットワークに対して IP version 4 (IPv4) または IP version 6 (IPv6) をサポートします。
    
    > [!NOTE]
    > Lync Server 2013 は、デュアル IP スタックが有効になっているネットワークで動作できます。


  - **SIP 転送プロトコル。** 通常、SIP では、ユーザー データグラム プロトコル (UDP)、伝送制御プロトコル (TCP)、およびトランスポート層セキュリティ (TLS) の少なくとも 3 つの転送タイプを使用できます。既定の SIP 転送構成では、TLS は TCP 上で動作します。TLS は Lync Server 2013 ネットワーク内で使用されます。ネットワーク境界では、 Lync Server 2013 は TCP 上で同時に運用できます。しかし、企業の通信のセキュリティ、信頼性、スケーラビリティの最低基準を満たさないため、 Lync Server 2013 では SIP 転送用の UDP をサポートしません。詳細については、NextHop のブログ記事「UDP 対応か UDP 非対応か、それが問題だ」( [http://go.microsoft.com/fwlink/?linkid=185369\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=185369%26clcid=0x411)) を参照してください。
    
    > [!NOTE]
    > 各ブログの内容と URL は、将来予告なしに変更されることがあります。

