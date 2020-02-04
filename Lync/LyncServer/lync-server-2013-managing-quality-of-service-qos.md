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
ms.openlocfilehash: ce88471361c63fde3ebf8a3ea716a140567e722e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725587"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-quality-of-service-qos-in-lync-server-2013"></a>Lync Server 2013 での QoS (Quality of Service) の管理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-11-07_

QoS (Quality of Service) は、音声とビデオの通信に最適なエンドユーザーエクスペリエンスを提供するために、組織内で使用されるネットワークテクノロジです。 QoS は、帯域幅が制限されているネットワークで一般的に使用されています。大量のネットワークパケットが、使用可能な帯域幅が比較的少ない場合は、管理者がより高い優先順位をパケットに割り当てる方法を提供します。オーディオデータまたはビデオデータを伝送する。 これらのパケットの優先度を高くすることで、音声とビデオによる通信は、ファイル転送、web 閲覧、データベースバックアップなどのネットワークセッションよりもずっと速く、中断される可能性が高くなります。 これは、ファイル転送やデータベースバックアップに使用されるネットワークパケットに "最善の努力" の優先度が割り当てられているためです。

<div>


> [!NOTE]  
> 一般的な規則として、サービスの品質は、内部ネットワーク上の通信セッションにのみ適用されます。 QoS を実装するときは、サーバーとルーターがパケットマーキングをサポートするように構成します。ただし、これらのデバイスでは、特定の方法でのパケットマーキングをサポートするように構成します。 サービスの品質は、インターネットやその他のネットワークでサポートされていると想定することはできません。 サービスが他のネットワークでサポートされている場合でも、ネットワーク上のサービスを構成したときと同じ方法で QoS が構成される保証はありません。



</div>

Microsoft Lync Server 2013 では、サービスの品質は必要ありません。現在 QoS を使用していない場合は、Lync Server 2013 をインストールする前に、サービスをインストールする必要はありません。 ネットワークで大量のパケット損失が発生する場合は、この問題を解決するために推奨される方法は、帯域幅を追加することです。 帯域幅を追加できない場合は、代わりにサービスの品質を実現することをお勧めします。

Lync Server 2013 は、サービスの品質を完全にサポートします。これは、既に QoS を使用している組織では、Lync Server を既存のネットワークインフラストラクチャに簡単に統合できることを意味します。 そのためには、次の作業を行う必要があります。

  - [Windows をベースにしていないデバイスの Lync Server 2013 で QoS を有効に](lync-server-2013-enabling-qos-for-devices-that-are-not-based-on-windows.md)します。 既定では、その他のオペレーティング システムを実行するコンピューターおよびその他のデバイス (iPhone など) では QoS は無効です。 Lync Server を使用して、デバイスのサービス品質を有効または無効にすることはできますが、通常は製品を使用して、これらのデバイスで使用される DSCP コードを変更することはできません。

  - [Lync Server 2013 での、会議、アプリケーション、および仲介サーバー用のポート範囲の構成](lync-server-2013-configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md)。 オーディオやビデオなどのさまざまな種類のパケットに対して、専用のポートセットを予約する必要があります。 Lync Server 2013 では、プロパティ値を True または False に設定して、サービスの品質を有効または無効にすることはできません。 代わりに、ポート範囲を構成し、グループポリシーを作成して適用することで、サービスの品質を有効にします。 後で QoS を使用しないことにした場合は、適切なグループポリシーオブジェクトを削除することで、"サービスの品質" を無効にすることができます。

  - [Lync Server 2013 でエッジサーバーのポート範囲を構成](lync-server-2013-configuring-port-ranges-for-your-edge-servers.md)します。 必須ではありませんが、その他のサーバーと同じポート範囲を使用するようにエッジ サーバーを構成することができます。

  - [Lync Server 2013 で Microsoft Lync クライアントのポート範囲を構成](lync-server-2013-configuring-port-ranges-for-your-microsoft-lync-clients.md)します。 これらのポート範囲はクライアントコンピューターにのみ適用され、通常は、サーバーに構成されているポート範囲とは異なります。

  - [Lync Server 2013 で会議、アプリケーション、および仲介サーバー用のサービス品質ポリシーを構成](lync-server-2013-configuring-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers.md)します。 これらのポリシーは、さまざまなパケットの種類に適用される DSCP コードを決定します。

  - [Lync Server 2013 で、a/V エッジサーバーのサービス品質ポリシーを構成](lync-server-2013-configuring-a-quality-of-service-policy-for-your-a-v-edge-servers.md)します。 これは、エッジ サーバーの内側でのみ行う必要があります。 サービスの品質は、インターネット上ではなく、内部ネットワークでの使用を目的として設計されているためです。

  - [Windows 7 または windows 8 で実行されているクライアントのために、Lync Server 2013 でサービスの品質ポリシーを構成](lync-server-2013-configuring-quality-of-service-policies-for-clients-running-on-windows-7-or-windows-8.md)します。 Microsoft Lync Server 2013 は、Windows Vista や Windows XP などの他の Windows オペレーティングシステムでは QoS をサポートしていないことに注意してください。

  - [Lync Server 2013 の Microsoft Lync Phone Edition デバイスでのサービス品質の構成](lync-server-2013-configuring-quality-of-service-on-microsoft-lync-phone-edition-devices.md)。 既定では、Lync Phone Edition デバイスでは QoS が有効になっています。 ただし、組織内のすべてのオーディオパケットで同じ DSCP コードを使用するために、既定の DSCP 値を変更することをお勧めします。

<div>


> [!NOTE]  
> Microsoft Windows Server 2012 または Windows Server 2012 R2 を使用している場合は、そのプラットフォームのサービスの品質を管理するために、新しい Windows PowerShell コマンドレットを使用することをお勧めします。 詳細については、「Windows PowerShell でのネットワーク品質の[https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps](https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps)サービスコマンドレット」を参照してください。



</div>

</div>

<span> </span>

</div>

</div>

</div>

