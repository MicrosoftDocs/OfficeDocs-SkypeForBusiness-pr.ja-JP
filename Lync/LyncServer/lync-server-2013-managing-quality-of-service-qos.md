---
title: サービスの品質 (QoS) の管理
TOCTitle: サービスの品質 (QoS) の管理
ms:assetid: ab1051c3-8380-4d72-86df-37a61b1e4a41
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg405409(v=OCS.15)
ms:contentKeyID: 48273234
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# サービスの品質 (QoS) の管理

 

_**トピックの最終更新日:** 2016-12-08_

サービスの品質 (QoS) は、一部の組織で使用されているネットワーク テクノロジであり、音声やビデオによる通信で最適なエンドユーザー エクスペリエンスを提供するために役立ちます。QoS は、帯域幅が制限されているネットワークで特によく使用されます。大量のネットワーク パケットが比較的少量の使用可能な帯域幅を取り合うため、サービスの品質によって、管理者が音声またはビデオのデータを伝送するパケットに高い優先順位を割り当てる方法が提供されます。このようなパケットに高い優先順位を付与すると、音声やビデオによる通信は、ファイルの転送、Web 閲覧、またはデータベース バックアップのようなネットワーク セッションよりも迅速かつ少ない中断で完了する可能性が高まります。このため、ファイルの転送またはデータベース バックアップに使用されるネットワーク パケットには "ベスト エフォート型" の優先順位が割り当てられます。

> [!NOTE]
> 一般に、サービスの品質は、内部ネットワーク上のセッションとの通信にのみ適用されます。QoS を実装する場合は、パケットのマーキングをサポートするようにサーバーおよびルーターを構成します。ただし、これらのデバイスの構成では、特定の方法でパケットのマーキングをサポートするようにします。サービスの品質はインターネットまたはその他のネットワークでサポートされることを前提にしてはいけません。サービスの品質がその他のネットワークでサポートされる場合であっても、ネットワークでサービスを構成した方法と同じ方法で QoS が構成される保証はありません。


Microsoft Lync Server 2013 はサービスの品質を必要としません。QoS を現在使用していない場合、Lync Server 2013 をインストールする前にこのサービスをインストールする必要はありません。ネットワーク上にかなりの量のパケット損失がある場合、この問題を改善するために推奨される方法は、帯域幅をさらに追加することです。さらに帯域幅を追加することができない場合は、代わりにサービスの品質を実装することができます。

Lync Server 2013 では、サービスの品質を完全にサポートしています。このため、QoS を既に使用している組織は Lync Server を簡単に既存のネットワーク インフラストラクチャに統合できます。この統合を実行するためには、次のタスクを実行する必要があります。

  - [Windows に基づかないデバイスの QoS の有効化](lync-server-2013-enabling-qos-for-devices-that-are-not-based-on-windows.md)。既定では、その他のオペレーティング システムを実行するコンピューターおよびその他のデバイス (iPhone など) では QoS は無効です。Lync Server を使用してデバイスのサービスの品質を有効にしたり無効にしたりすることはできますが、通常、これらのデバイスによって使用される DSCP コードをこの製品を使用して変更することはできません。

  - [電話会議、アプリケーションおよび仲介サーバーのポート範囲の構成](lync-server-2013-configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md)。音声とビデオなどの異なるパケットの種類に対して独自のポート セットを予約する必要があります。Lync Server 2013 では、プロパティ値を True または False に設定することによってサービスの品質を有効にしたり無効にしたりすることはしません。そうではなく、ポート範囲を構成してからグループ ポリシーを作成および適用することによってサービスの品質を有効にします。後で QoS を使用しないことにする場合は、単に該当するグループ ポリシー オブジェクトを削除することによってサービスの品質を無効にすることができます。

  - [エッジ サーバー のポート範囲の構成](lync-server-2013-configuring-port-ranges-for-your-edge-servers.md)。必須ではありませんが、その他のサーバーと同じポート範囲を使用するようにエッジ サーバーを構成することができます。

  - [Microsoft Lync クライアントのポート範囲の構成](lync-server-2013-configuring-port-ranges-for-your-microsoft-lync-clients.md)。これらのポート範囲はクライアント コンピューターにのみ適用され、通常、サーバーで構成されたポート範囲とは異なります。

  - [電話会議、アプリケーションおよび仲介サーバーの Lync Server 2013 における QoS (Quality of Service) ポリシーの構成](lync-server-2013-configuring-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers.md)。これらのポリシーでは、異なるパケットの種類に適用される DSCP コードを決定します。

  - [音声ビデオ エッジ サーバーの QoS (Quality of Service) ポリシーの構成](lync-server-2013-configuring-a-quality-of-service-policy-for-your-a-v-edge-servers.md)。これは、エッジ サーバーの内側でのみ行う必要があります。サービスの品質はインターネットではなく内部ネットワークで使用するために設計されているためです。

  - [Windows 7 または Windows 8 で実行しているクライアントのサービス品質 (QoS) ポリシーの構成](lync-server-2013-configuring-quality-of-service-policies-for-clients-running-on-windows-7-or-windows-8.md)。Microsoft Lync Server 2013 は Windows Vista や Windows XP などのその他の Windows オペレーティング システムで QoS をサポートしないことに注意してください。

  - [Microsoft Lync Phone Edition デバイスにおけるサービスの品質 (QoS) の構成](lync-server-2013-configuring-quality-of-service-on-microsoft-lync-phone-edition-devices.md)。既定では、QoS は Lync Phone Edition デバイスで有効になっています。ただし、組織内のすべての音声パケットが同じ DSCP コードを使用するようにするために、既定の DSCP 値を変更することもできます。

> [!NOTE]
> Microsoft Windows Server 2012 または Windows Server 2012 R2 をご使用の場合、そのプラットフォームでサービス品質の管理に使用できる新しいバージョンの Windows PowerShell コマンドレットをご利用いただけます。詳しくは、「Windows PowerShell のネットワーク サービス品質コマンドレット (Network Quality of Service Cmdlets in Windows PowerShell)」(<a href="http://go.microsoft.com/fwlink/p/?linkid=285379">http://go.microsoft.com/fwlink/p/?LinkId=285379</a>) をご覧ください。

