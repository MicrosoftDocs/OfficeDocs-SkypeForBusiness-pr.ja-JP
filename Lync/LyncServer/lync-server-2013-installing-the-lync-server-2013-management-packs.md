---
title: 'Lync Server 2013: Lync Server 2013 管理パックのインストール'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: nstalling the Lync Server 2013 management packs
ms:assetid: b800d4ab-fdc8-4c72-a76a-b78932779fe3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205202(v=OCS.15)
ms:contentKeyID: 48185233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fea443225744bfd0d0e2dfa90a317ffa4cc890ac
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832992"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-server-2013-management-packs"></a>Lync Server 2013 管理パックのインストール

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-22_

System Center Operations Manager は、Windows オペレーティングシステムのわずかな部分のみを監視することができます。 ただし、system center operations Manager の機能を拡張するには、管理パックをインストールします。このソフトウェアは、System Center Operations Manager が監視できる項目を決定するソフトウェア、それらの項目を監視する方法、アラートの表示方法などを行うことができます。トリガーおよび報告されます。 Microsoft Lync Server 2013 には、次の機能を提供する System Center Operations Manager の2つの管理パックが含まれています。

  - コンポーネントとユーザー管理パック (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) は、イベントログに記録された Lync Server の問題を追跡し、パフォーマンスカウンターで登録するか、または通話の詳細レコード (CDR) またはエクスペリエンスの品質 (QoE) に記録します。databases. 重大な問題については、System Center Operations Manager を構成して、メール、インスタントメッセージ、またはショートメッセージサービス (SMS) メッセージングを使って管理者にすぐに通知することができます。 SMS は、あるモバイルデバイスから別のモバイルデバイスにテキストメッセージを送信するために使用されるテクノロジです。
    
    <div>
    

    > [!NOTE]  
    > Operations Manager の通知の構成の詳細については、TechNet ライブラリの「 <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?linkid=268785</A>通知を設定する」を参照してください。

    
    </div>

  - アクティブな監視パック (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) は、システムにログオンしたり、インスタントメッセージを交換したり、公衆交換電話に入っている電話への通話を発信したりするなど、Lync Server の主要なコンポーネントを事前にテストします。ネットワーク (PSTN)。 これらのテストは、Lync Server の代理トランザクションコマンドレットを使用して行われます。 たとえば、テスト用の**cgi**コマンドレットを使って、一連のテストユーザー間のインスタントメッセージの会話をシミュレートします。 このシミュレートされたメッセージの会話に失敗した場合は、警告が生成されます。

Lync Server 2013 に含まれている2つの管理パックには、Microsoft Lync Server 2010 で使用される管理パックに対する多数の拡張機能が含まれています。 たとえば、Lync Server 2013 コンポーネント管理パックは、Lync Server 自体の監視に限定されているわけではありません。 Lync Server のイベントログとパフォーマンスカウンターの監視に加えて、コンポーネント管理パックは、次のような重要な項目についてのパフォーマンスを追跡し、警告を発行することもできます。

  - **インターネットインフォメーションサービス (IIS)**   の警告は、インターネットインフォメーションサービスがオフラインになった場合に発行されます。 Lync Server web サービスは IIS に依存しているため、これは重要です。

  - **プロセスの使用状況**   の警告は、システムリソース (利用可能なメモリなど) を低解像度で開始した場合に発行されます。 これらの通知は、Lync Server が高いシステム使用を担当していない場合でも発行されます。

  - **コンピューターの障害イベント**   アラートは、サーバーの実行可能性を早急に示すハードウェアまたはソフトウェアの問題が発生した場合に発行されます。 たとえば、ハードディスクの障害が発生している可能性があるサーバーが表示された場合は、Lync Server の管理者に通知されます。

新しい管理パックでも、レポート機能が強化されています。 Lync Server 2013 の新しいレポートには、次のようなものがあります。

  - **[終了-終了] シナリオの可用性レポート**   このレポートは、登録やプレゼンスなどの、主要な Lync Server サービスの可用性/稼働時間を詳細に説明します。

  - ****   [パフォーマンスカウンター情報を使用したキャパシティレポート] このレポートには、メモリの可用性やプロセッサ使用率などのシステムコンポーネントの傾向が表示されます。

  - **[コンポーネントレポート**   このレポートには、Lync Server コンポーネントによってグループ化された最上位の通知ジェネレーターが一覧表示されます。

これらのデザイン済みレポートに加えて、Lync Server 2013 用の管理パックは、通話の信頼性 (通話詳細の記録で測定された測度) と QoE の状態 (エクスペリエンスの品質で測定される測度) の両方について、自動的に通知を報告します。 通話の詳細記録を有効にしている場合は、System Center Operations Manager コンソールから次の手順を実行して、通話の信頼性の警告を確認できます。

  - [**監視**]、[ **Microsoft Lync Server 2013 正常性**] の順に展開し、[**通話の信頼性とメディアの品質**] を展開して、[通話の**信頼性**] をクリックします。

エクスペリエンスの警告を表示するには、System Center Operations Manager コンソールから次の手順を実行します。

  - [**監視**]、[ **Microsoft Lync Server 2013 正常性**] の順に展開し、[**通話の信頼性とメディアの品質**] を展開して、[メディアの**品質**] を展開します。

Lync Server 2013 用の管理パックで、Microsoft Lync Server 2010 で使用されるセントラル検出メカニズムではなく、マシンレベルの検出が使用されるようになりました。 つまり、各 System Center agent は基本的に自分自身を検出し、その存在を中央管理サーバーに報告します。 マシンレベルの検出を使うと、System Center インフラストラクチャの管理が簡単になり、さまざまなバージョンの Lync Server 管理パック (たとえば、lync Server 2010 用の管理パックと Lync Server 2013 用の管理パック) を使用することができます。せ.

</div>

<span> </span>

</div>

</div>

</div>

