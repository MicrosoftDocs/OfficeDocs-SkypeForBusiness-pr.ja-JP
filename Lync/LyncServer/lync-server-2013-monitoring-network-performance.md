---
title: 'Lync Server 2013: ネットワークパフォーマンスの監視'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring network performance
ms:assetid: bc3a01da-91eb-4c0c-9598-35e5e46b00f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720923(v=OCS.15)
ms:contentKeyID: 63969647
ms.date: 04/27/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8524499737ae1e52a36a80fbc636f005b687a6a0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42047970"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-network-performance-in-lync-server-2013"></a>Lync Server 2013 でのネットワークパフォーマンスの監視

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2016-04-27_

Lync Server 2013 は、ネットワークに大きく依存して、インスタントメッセージング (IM)、音声通話、またはビデオ通信によってユーザー間の通信を可能にするリアルタイム通信テクノロジです。 そのため、ネットワークパフォーマンスを継続的に監視して、ユーザーが選択した通信モダリティが最適な環境を提供することを保証することが重要です。

ネットワークのパフォーマンスは、次の2つのレベルで測定できます。

  - **ネットワークの全体的なパフォーマンス**   このレベルのパフォーマンス測定を使用すると、組織はネットワークの "大きな画像" 表示を作成し、通常はサードパーティのネットワーク監視システムを使用して実装します。 これらのシステムは、パフォーマンスと容量のデータをルーターなどのリモートネットワークデバイスから受け取り、ネットワークを介して切り替えることによって、管理者が任意の時間帯に特定のネットワークコンポーネントの正常性を判断できるようにします。

  - **個々のサーバーのパフォーマンス**   このレベルのパフォーマンス測定値は特定のサーバーに限定され、特定のパフォーマンスの問題のトラブルシューティングや、容量計画プロセスの一環として、特定の期間における個々のサーバーのパフォーマンスを測定するために、特定のサーバーのネットワークパフォーマンスを gauging する管理者に役立ちます。

次のセクションで説明するツールを使用して、ネットワークを監視できます。

<div>

## <a name="tools-for-overall-network-performance-monitoring"></a>ネットワークパフォーマンスの全体的な監視用のツール

<div>

## <a name="system-center-operations-manager-2012"></a>System Center Operations Manager 2012

System Center Operations Manager は、IT 環境全体のサービスレベルを向上させるために、簡単にカスタマイズおよび拡張できる、エンドツーエンドのサービス管理を提供します。 これにより、運用および IT 管理チームは、分散 IT サービスの正常性に影響する問題を特定して解決することができます。 エンドツーエンドのサービス管理は、Microsoft ベースの環境に制限されていません。 Web サービス (WS-MANAGEMENT)、簡易ネットワーク管理プロトコル (SNMP)、およびパートナーソリューションのサポートにより、Microsoft オペレーティングシステムとハードウェアを実行していないシステムを、システムセンター内のサービス監視に含めることができます。Operations Manager 2012。

</div>

<div>

## <a name="system-center-operations-manager-2012-and-third-party-network-management-solutions"></a>System Center Operations Manager 2012 およびサードパーティ製のネットワーク管理ソリューション

**Emc Smarts**   Operations Manager 向け emc ソリューションは、サービスレベルに影響する問題を迅速に解決するのに役立ちます。 Operations Manager 用 EMC ソリューションを使用すると、統合された1つの自動ソリューションで IT サービスチェーン全体を管理および監視できます。 パフォーマンスと可用性の問題の根本原因を簡単に特定し、それらを解決することで、影響とコストを軽減できます。 主な利点は次のとおりです。

  - 高度で使いやすい管理を使用して、手動での並べ替えやフィルター処理を混同せずに、戦略的なビジネス価値を提供することに重点を置いています。

  - **より迅速に解決**   することで、IT 上の問題を解決し、ビジネスニーズに迅速に対応して、影響とコストを軽減します。

  - **合理化**   された操作では、複数の管理ツール、アプリケーション、およびターミナルを組み合わせることによって、IT の複雑さを回避します。

詳細については、以下を参照してください。

[Microsoft System Center Operations Manager](http://go.microsoft.com/fwlink/p/?linkid=243651)

[Microsoft System Center Operations Manager のソリューション](http://www.emc.com/collateral/software/data-sheet/h6135-server-manager-ds.pdf)

</div>

<div>

## <a name="third-party-solutions"></a>サードパーティ製のソリューション

Hp ネットワーク管理**センター (旧称 Hp OpenView)**   [Hp ネットワーク管理センター](http://www8.hp.com/us/en/software-solutions/network-management/index.html?%26zn=bto%26cp=1-11-15-119_4000_100__)では、ネットワークの可用性とパフォーマンスを向上するために、統合された障害およびパフォーマンス管理を提供しています。 ネットワーク管理センターは、障害、パフォーマンス、構成、および変更管理を統合する HP 自動ネットワーク管理ソリューションの一部です。

**Cisco 社の cisco ネットワーク管理と自動化製品**   には、ciscoworks LAN 管理ソリューションと cisco ネットワーク分析モジュールを含むいくつかの管理製品があります。これにより、運用効率を向上させ、ネットワークのダウンタイムを削減できます。 これらの製品の追加データについては、Cisco web [http://www.cisco.com/en/US/products/sw/netmgtsw/index.html](http://www.cisco.com/en/us/products/sw/netmgtsw/index.html)サイト () を参照してください。

簡易ネットワーク管理プロトコル (SNMP) 簡易ネットワーク管理プロトコル (SNMP) は、TCP/IP ネットワークを管理する戦略を定義するネットワーク管理の標準です。 SNMP を使用すると、ネットワークに関する構成および状態に関する情報を取得し、指定されたコンピューターにイベント監視用に情報を送信することができます。 この標準ベースのネットワーク管理プロトコルは、次のものを含む分散アーキテクチャを使用します。

  - 複数の管理ノード。それぞれがエージェントと呼ばれる SNMP エンティティを使用して、管理インストルメンテーションへのリモートアクセスを提供します。

  - 管理要素を監視および制御するために管理アプリケーションを実行する、マネージャーとして知られている少なくとも1つの SNMP エンティティ。 管理要素は、ホスト、ルーターなどのデバイスです。 管理情報にアクセスすることによって監視および制御されます。

  - 管理プロトコル (SNMP) は、管理ステーションとエージェント間で管理情報を通信するために使用されます。 管理情報は、管理情報ベース (MIB) と呼ばれる仮想情報ストア内に存在する管理対象オブジェクトのコレクションを参照します。

<div>


> [!NOTE]  
> サードパーティ製のネットワーク監視ソリューションの例については、前述の説明を参考にしてください。 この一覧は明確ではありません。また、Microsoft は特定のベンダーソリューションを優先していません。 ネットワークサービスプロバイダーまたは各テクノロジプロバイダーと相談して、組織に最適なネットワーク監視ソリューションを決定してください。



</div>

</div>

</div>

<div>

## <a name="tools-for-monitoring-individual-server-network-performance"></a>個々のサーバーネットワークのパフォーマンスを監視するためのツール

<div>

## <a name="system-center-operations-manager-2012"></a>System Center Operations Manager 2012

System Center Operations Manager 2012 では、管理者が Windows Server 2012 管理パックを使用して個々のサーバーのネットワークパフォーマンスを表示することができます。 Windows Server オペレーティングシステム管理パックには、"パフォーマンス" 管理パックが含まれています。これにより、管理者はネットワークアダプターのパフォーマンスとアダプターの正常性を監視できるようになります。

</div>

<div>

## <a name="windows-network-monitor"></a>Windows ネットワークモニター

サーバー上のリソース使用量を収集、表示、分析し、ネットワークトラフィックを測定します。 ネットワークモニターは、ネットワークアクティビティを排他的に監視します。 ネットワークデータを収集して分析し、このデータをパフォーマンスログで使用することで、ネットワークの使用状況を判断し、ネットワークの問題を特定し、今後のネットワークのニーズを予測することができます。

ネットワークモニター3.4 の詳細と、ネットワークモニターのインストールおよび構成方法と、データのキャプチャおよび分析方法については、このセッションを参照してください。ネットワークモニター3.3 の概要。 また、[ネットワークモニターのブログ](http://blogs.technet.com/b/netmon/)を参照してください。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

