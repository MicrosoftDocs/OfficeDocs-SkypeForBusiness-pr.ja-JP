---
title: 'Lync Server 2013: サーバーのメモリ容量制限の監視'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring for server memory capacity limits
ms:assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689982(v=OCS.15)
ms:contentKeyID: 48183506
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45600ed9c822851c89b13cb776bbc58464decde0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048100"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-for-server-memory-capacity-limits-in-lync-server-2013"></a>Lync Server 2013 でのサーバーのメモリ容量制限の監視

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2016-12-08_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<div>


> [!WARNING]  
> このトピックの容量計画を参照する情報は、Lync 2010 モバイルクライアントおよび Mobility Service (Mcx) にのみ関連しています。 Lync 2013 Mobile クライアントによって使用される統合コミュニケーション Web API (UCWA) の容量計画は、Lync Server 2013、計画ツールによって提供されます。



</div>

2つのモビリティパフォーマンスカウンターは、現在の使用状況を判断し、Lync Server 2013 Mobility Service (Mcx) の容量を計画したり、UCWA のメモリ使用量を監視したりするのに役立ちます。 UCWA では、カウンターカテゴリは**LS: WEB-UCWA**です。 Mobility Service (Mcx) の場合、カウンターはカテゴリ**LS: WEB-モバイル通信サービス**の下にあります。 監視するカウンターは次のとおりです。

  - アクティブなプレゼンスサブスクリプションを**持つ現在アクティブなセッション数**(アクティブなプレゼンスサブスクリプションを使用する現在のエンドポイント数) (常時接続されたモバイルユーザーの数)

  - **現在アクティブなセッション数**。これは、ucwa または Mobility Service で登録されたエンドポイントの現在の数です。

**アクティブなプレゼンスサブスクリプション**と**現在アクティブなセッション数**が少ない状態で、現在アクティブなセッション数の差が少ない場合は、ほとんどのモバイルデバイスユーザーに Android または Nokia モバイルデバイスなどの常時接続デバイスがあることを意味します (mcx のみ)。 UCWA の常時接続デバイスには、Lync 2013 Mobile クライアントを実行している Apple および Android デバイスが含まれます。 **現在アクティブなセッション数**が、アクティブな**プレゼンスサブスクリプションを使用して現在アクティブなセッション数**を超えている場合は、他のユーザーが、Mcx の下で Apple IOS デバイスや Windows Phone などのバックグラウンドエンドポイントデバイスを使用していることを示します。 (これとして登録されるのは、Windows Phone が唯一の Lync 2013 モバイルクライアントです)。

**アクティブなプレゼンスサブスクリプション**と、**現在アクティブなセッション数**のパフォーマンスカウンターに関する制限を設定する必要があります。これには、予想される使用状況、容量計画の結果、モビリティサービスおよびその他のフロントエンドサーバーカウンターの継続的な監視に基づきます。 設定する制限によって、サーバーの容量を評価し、容量を超えたときにアラートを発生させることができます。

適切な制限を決定するには、まず、Mobility Service のフロントエンドサーバーで使用可能なメモリ容量を特定する必要があります。 カウンターを監視して、次の式に従って、容量の増設を計画する必要があるかどうかを判断します。

Mcx Mobility Service (MB) によって使用された合計メモリ = 164 + (400 + \* 134)/1024**現在アクティブなセッション数がアクティブプレゼンスサブスクリプション**+ 400/1024 \* (現在アクティブな**セッション数**がアクティブな**プレゼンスサブスクリプションで現在**アクティブなセッション数)

<div>


> [!IMPORTANT]  
> Microsoft Lync Server 2010 の容量計算機は、スプレッドシートを使用して、サーバーの要件 (CPU、メモリ、ハードドライブなど) を決定するための計画を可能にするすべての式で事前設定されています。 スプレッドシートと関連するドキュメントは、次の場所にダウンロードできます。<A href="https://go.microsoft.com/fwlink/p/?linkid=212657">https://go.microsoft.com/fwlink/p/?LinkID=212657</A>



</div>

フロントエンドサーバーは、フェールオーバー時に Mobility Service をサポートするのに十分な空きメモリを必要とします。 Mobility Service で使用するメモリ容量を計画するには、[**使用可能\\なメモリ mb** ] カウンターを使用するか、前述の式を使用して、フロントエンドサーバーで現在使用可能なメモリを監視できます。

必要な数のモビリティユーザーを計画する場合、フロントエンドサーバーで使用可能なメモリ容量が 1500 MB 未満である場合は、Mobility Service をサポートするためにハードウェアを追加する必要があります。 詳細については、「操作」のドキュメントの「 [Lync Server 2013 でのパフォーマンスを監視する](lync-server-2013-monitoring-mobility-for-performance.md)」を参照してください。

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのパフォーマンスのためのモビリティの監視](lync-server-2013-monitoring-mobility-for-performance.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

