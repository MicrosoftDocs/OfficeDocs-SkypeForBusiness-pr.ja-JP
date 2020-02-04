---
title: 'Lync Server 2013: サーバーのメモリ容量の上限を監視する'
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
ms.openlocfilehash: e5c9746240335b1c66606da24edf6ffa2a0e7bda
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765978"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-for-server-memory-capacity-limits-in-lync-server-2013"></a>Lync Server 2013 でのサーバーメモリ容量の上限を監視する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2016-12-08_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<div>


> [!WARNING]  
> このトピックでは、キャパシティ計画を参照している情報は、Lync 2010 モバイルクライアントとモビリティサービス (Mcx) のみに関連しています。 Lync 2013 モバイルクライアントで使用されるユニファイドコミュニケーション Web API (UCWA) のキャパシティ計画は、Lync Server 2013、計画ツールによって提供されます。



</div>

2つのモバイルパフォーマンスカウンターは、現在の使用状況を特定し、Lync Server 2013 Mobility Service (Mcx) のキャパシティを計画し、UCWA のメモリ使用量を監視するのに役立ちます。 UCWA では、カウンターカテゴリは**LS: WEB – UCWA**です。 モバイルサービス (Mcx) については、カウンターは "カテゴリ**LS: WEB モバイル通信サービス**" の下にあります。 監視するカウンターは次のとおりです。

  - **Currently Active Session Count with Active Presence Subscriptions**。これは、UCWA または Mobility Service (Mcx) 経由で登録されたエンドポイントのうち、アクティブなプレゼンス サブスクリプションを持つエンドポイントの現在数 (常時接続されたモバイル ユーザーの数) です。

  - **Currently Active Session Count**。これは、UCWA または Mobility Service 経由で登録されたエンドポイントの現在数です。

**アクティブなセッション数と**現在アクティブな**セッション数**の差が時間の経過と共に小さい場合は、モバイルデバイスを使用しているデバイス (Android や Nokia モバイルデバイスなど) が常に接続されていることを意味します (mcx のみ)。 UCWA 常に接続されたデバイスには、Lync 2013 モバイルクライアントを実行している Apple と Android デバイスが含まれます。 現在アクティブな**セッション数**が **、アクティブなプレゼンスのサブスクリプションによって現在アクティブなセッション数**を超えている場合は、Apple IOS デバイスや Mcx での Windows Phone などのバックグラウンドエンドポイントデバイスを使用しているユーザーが多いことを示します。 (Windows Phone は、これとして登録される唯一の Lync 2013 モバイルクライアントです)。

現在アクティブになっている**セッション数**の上限を設定する必要があります。これには、想定される使用状況、キャパシティ計画の結果、モビリティサービスおよびその他のフロントエンドサーバーカウンターの継続的な監視に基づいて、現在のアクティブなセッション数**のパフォーマンスカウンター**が使用されます。 制限を設定することで、キャパシティを超えたときにサーバーの容量を評価し、警告を発生させることができるようになります。

適切な制限を決定するには、まず、モビリティサービスのフロントエンドサーバーで利用可能なメモリ量を決定する必要があります。 カウンターを監視し、次の式に従って、追加容量の計画が必要な時期を確認します。

Mcx Mobility Service (MB) = 164 + (400 + 134)/1024 \* **現在アクティブなセッション数**(現在のアクティブな\* **セッションカウント**–現在アクティブな**プレゼンスサブスクリプションに**よるアクティブなセッションカウント) 400 が使用されている合計メモリ

<div>


> [!IMPORTANT]  
> Microsoft Lync Server 2010 容量計算ツールは、CPU、メモリ、ハードドライブなど、プランナーでサーバーの要件を決定するためのすべての数式で事前に用意されたスプレッドシートです。 スプレッドシートと関連ドキュメントをダウンロードするには、次の操作を行います。<A href="https://go.microsoft.com/fwlink/p/?linkid=212657">https://go.microsoft.com/fwlink/p/?LinkID=212657</A>



</div>

フロントエンドサーバーには、フェールオーバーの状況でモビリティサービスをサポートするための十分なメモリが必要です。 フロントエンドサーバーで利用可能な現在のメモリを監視するには **、\\memory available m**カウンターを使用するか、前に説明した式を使用して、モビリティサービスで使用する必要のあるメモリ量を計画します。

フロントエンドサーバーで利用可能なメモリの量が 1500 MB よりも小さい場合は、モビリティユーザーの想定される数を計画するときに、モビリティサービスをサポートするためにハードウェアを追加する必要があります。 詳細については、操作のドキュメントで「 [Lync Server 2013 のパフォーマンスを監視する](lync-server-2013-monitoring-mobility-for-performance.md)」を参照してください。

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのモバイルパフォーマンスの監視](lync-server-2013-monitoring-mobility-for-performance.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

