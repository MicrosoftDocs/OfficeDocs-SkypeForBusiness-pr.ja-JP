---
title: 'Lync Server 2013: サービスの品質 (QoS) の管理'
ms.reviewer: ''
f1.keywords:
- NOCSH
TOCTitle: Managing Quality of Service (QoS)
author: lanachin
ms.author: v-lanac
ms.manager: serdars
ms:assetid: ab1051c3-8380-4d72-86df-37a61b1e4a41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg405409(v=OCS.15)
ms:contentKeyID: 48185049
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13d96132357e1981214961f136cf5365cf74907a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185570"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-quality-of-service-qos-in-lync-server-2013"></a>Lync Server 2013 でのサービスの品質 (QoS) の管理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-11-07_

サービスの品質 (QoS) は、一部の組織で使用されているネットワーク テクノロジであり、音声やビデオによる通信で最適なエンドユーザー エクスペリエンスを提供するために役立ちます。QoS は、帯域幅が制限されているネットワークで特によく使用されます。大量のネットワーク パケットが比較的少量の使用可能な帯域幅を取り合うため、サービスの品質によって、管理者が音声またはビデオのデータを伝送するパケットに高い優先順位を割り当てる方法が提供されます。このようなパケットに高い優先順位を付与すると、音声やビデオによる通信は、ファイルの転送、Web 閲覧、またはデータベース バックアップのようなネットワーク セッションよりも迅速かつ少ない中断で完了する可能性が高まります。このため、ファイルの転送またはデータベース バックアップに使用されるネットワーク パケットには "ベスト エフォート型" の優先順位が割り当てられます。

<div>


> [!NOTE]  
> 一般に、サービスの品質は、内部ネットワーク上のセッションとの通信にのみ適用されます。QoS を実装する場合は、パケットのマーキングをサポートするようにサーバーおよびルーターを構成します。ただし、これらのデバイスの構成では、特定の方法でパケットのマーキングをサポートするようにします。サービスの品質はインターネットまたはその他のネットワークでサポートされることを前提にしてはいけません。サービスの品質がその他のネットワークでサポートされる場合であっても、ネットワークでサービスを構成した方法と同じ方法で QoS が構成される保証はありません。



</div>

Microsoft Lync Server 2013 は、サービスの品質を必要としません。現在 QoS を使用していない場合は、Lync Server 2013 をインストールする前にサービスをインストールする必要はありません。 ネットワークで大量のパケット損失が発生した場合、この問題を緩和するために推奨される方法は、追加の帯域幅を追加することです。 帯域幅を追加できない場合は、代わりにサービスの品質を実装することをお勧めします。

Lync Server 2013 ではサービスの品質を完全にサポートしています。これは、既に QoS を使用している組織が Lync Server を既存のネットワークインフラストラクチャに統合することを容易にすることを意味します。 そのためには、次のタスクを実行する必要があります。

  - [Windows に基づかないデバイスに対して Lync Server 2013 で QoS を有効にする](lync-server-2013-enabling-qos-for-devices-that-are-not-based-on-windows.md)。 既定では、その他のオペレーティング システムを実行するコンピューターおよびその他のデバイス (iPhone など) では QoS は無効です。 Lync Server を使用してデバイスのサービスの品質を有効または無効にすることはできますが、通常、製品を使用してこれらのデバイスで使用される DSCP コードを変更することはできません。

  - [Lync Server 2013 での会議、アプリケーション、仲介サーバー用のポート範囲の構成](lync-server-2013-configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md)。 音声とビデオなどの異なるパケットの種類に対して独自のポート セットを予約する必要があります。 Lync Server 2013 を使用すると、サービスの品質を有効または無効にすることはできません。たとえば、プロパティ値を True または False に設定します。 そうではなく、ポート範囲を構成してからグループ ポリシーを作成および適用することによってサービスの品質を有効にします。 後で QoS を使用しないことにする場合は、単に該当するグループ ポリシー オブジェクトを削除することによってサービスの品質を無効にすることができます。

  - [Lync Server 2013 でのエッジサーバーのポート範囲の構成](lync-server-2013-configuring-port-ranges-for-your-edge-servers.md)。 必須ではありませんが、その他のサーバーと同じポート範囲を使用するようにエッジ サーバーを構成することができます。

  - [Lync Server 2013 での Microsoft lync クライアントのポート範囲の構成](lync-server-2013-configuring-port-ranges-for-your-microsoft-lync-clients.md)。 これらのポート範囲はクライアント コンピューターにのみ適用され、通常、サーバーで構成されたポート範囲とは異なります。

  - [Lync Server 2013 での会議、アプリケーション、仲介サーバー用のサービス品質ポリシーの構成](lync-server-2013-configuring-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers.md)。 これらのポリシーでは、異なるパケットの種類に適用される DSCP コードを決定します。

  - [Lync Server 2013 での音声ビデオエッジサーバーの qos (Quality Of Service) ポリシーの構成](lync-server-2013-configuring-a-quality-of-service-policy-for-your-a-v-edge-servers.md)。 これは、エッジ サーバーの内側でのみ行う必要があります。 サービスの品質はインターネットではなく内部ネットワークで使用するために設計されているためです。

  - [Windows 7 または windows 8 で実行しているクライアントの Lync Server 2013 でのサービスの品質ポリシーの構成](lync-server-2013-configuring-quality-of-service-policies-for-clients-running-on-windows-7-or-windows-8.md)。 Microsoft Lync Server 2013 は、Windows Vista や Windows XP などの他の Windows オペレーティングシステムでは QoS をサポートしていないことに注意してください。

  - [Lync Server 2013 の Microsoft Lync Phone Edition デバイスでサービスの品質を構成する](lync-server-2013-configuring-quality-of-service-on-microsoft-lync-phone-edition-devices.md)。 既定では、Lync Phone Edition デバイスでは QoS が有効になっています。 ただし、組織内のすべての音声パケットが同じ DSCP コードを使用するようにするために、既定の DSCP 値を変更することもできます。

<div>


> [!NOTE]  
> Microsoft Windows Server 2012 または Windows Server 2012 R2 を使用している場合は、そのプラットフォームでサービスの品質を管理するために使用できる Windows PowerShell コマンドレットの新しいセットに関心があるかもしれません。 詳細については、「Windows PowerShell のネットワーク品質サービスの[https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps](https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps)コマンドレット」を参照してください。



</div>

</div>

<span> </span>

</div>

</div>

</div>

