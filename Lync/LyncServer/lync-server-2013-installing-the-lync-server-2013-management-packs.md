---
title: 'Lync Server 2013: Lync Server 2013 管理パックのインストール'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: nstalling the Lync Server 2013 management packs
ms:assetid: b800d4ab-fdc8-4c72-a76a-b78932779fe3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205202(v=OCS.15)
ms:contentKeyID: 48185233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a0a51d263628e4a2bb7d7ac08f7a4c8d1580420
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144964"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-server-2013-management-packs"></a>Lync Server 2013 管理パックのインストール

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-22_

System Center Operations Manager は単独で、Windows オペレーティングシステムのごく一部のみを監視することができます。 ただし、system center operations manager の機能を拡張するには、System center Operations Manager が監視できるアイテムを指定するソフトウェアをインストールします。これにより、これらのアイテムを監視する方法や、アラートの方法を指定することもできます。トリガーおよびレポート。 Microsoft Lync Server 2013 には、次の機能を提供する2つの System Center Operations Manager 管理パックが含まれています。

  - コンポーネントおよびユーザー管理パック (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) は、イベントログに記録された Lync Server の問題を追跡し、パフォーマンスカウンターで登録するか、または通話詳細記録 (CDR) または QoE (Quality of Experience) に記録します。databases. 重大な問題については、System Center Operations Manager を構成して、電子メール、インスタントメッセージ、またはショートメッセージサービス (SMS) のメッセージングを介して管理者に即座に通知できます。 SMS とは、テキスト メッセージをモバイル デバイス間で送信するために使用されるテクノロジです。
    
    <div>
    

    > [!NOTE]  
    > Operations Manager 通知の構成の詳細については、TechNet ライブラリの「通知<A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=268785">https://go.microsoft.com/fwlink/p/?linkid=268785</A>の構成」を参照してください。

    
    </div>

  - アクティブな監視パック (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) は、システムへのログオン、インスタントメッセージの交換、または公衆交換電話機にある電話機への通話の作成などの主要な Lync Server コンポーネントを事前にテストします。ネットワーク (PSTN)。 これらのテストは、Lync Server 代理トランザクションコマンドレットを使用して行われます。 たとえば、**Test-CsIM** コマンドレットは、1 組のテスト ユーザー間でインスタント メッセージングの会話をシミュレートするために使用されます。 シミュレートされたメッセージングの会話が失敗した場合、通知が生成されます。

Lync Server 2013 に含まれている2つの管理パックには、Microsoft Lync Server 2010 で使用される管理パックに対して多くの拡張機能が含まれています。 たとえば、Lync server 2013 コンポーネント管理パックは、Lync Server 自体の監視に制限されていません。 Lync Server のイベントログとパフォーマンスカウンターの監視に加えて、コンポーネント管理パックは次のような重要なアイテムのパフォーマンスを追跡し、通知を発行することもできます。

  - **インターネットインフォメーションサービス (IIS)**   がオフラインになった場合は、インターネットインフォメーションサービス (IIS) の警告が発行されます。 これは、Lync Server web サービスが IIS に依存しているためです。

  - **プロセス使用状況**   の警告は、システムリソース (利用可能なメモリなど) が不足し始めたときに発行されます。 これらのアラートは、Lync Server がシステムの高使用率を担当していない場合でも発行されます。

  - **コンピューターエラーイベント**   アラートは、ハードウェアまたはソフトウェアの問題によって、サーバーの使用可能性を阻むことがある場合に、発行されます。 たとえば、Lync Server 管理者は、ハードディスク障害が発生する危険性があると思われる場合に、そのサーバーに通知されます。

新しい管理パックは、拡張されたレポート機能も備えています。 Lync Server 2013 の新しいレポートは次のとおりです。

  - **エンドツーエンドシナリオの可用性レポート**   このレポートでは、登録やプレゼンスなど、主要な Lync Server サービスの可用性/稼働時間を詳細に説明します。

  - **処理能力レポート**   このレポートは、パフォーマンスカウンターの情報を使用して、メモリの可用性やプロセッサの使用率などのシステムコンポーネントの傾向を示します。

  - **コンポーネントレポート**   このレポートには、Lync Server コンポーネントによってグループ化された上位の通知ジェネレーターが一覧表示されます。

これらの設計済みレポートに加えて、Lync Server 2013 用の管理パックは、通話の信頼性 (通話詳細記録で測定された測定基準) と QoE の状態 (品質不足の測定基準) の両方に関する通知を自動的に報告します。 通話詳細記録を有効にしている場合は、System Center Operations Manager コンソールから次の手順を実行して、通話の信頼性に関する警告を確認できます。

  - [**監視**]、[**Microsoft Lync Server 2013 Health**]、[**Call Reliability and Media Quality**] の順に展開し、[**Call Reliability**] をクリックします。

Qoe (Quality of Experience) の警告を表示するには、System Center Operations Manager コンソールから次の手順を実行します。

  - [**監視**]、[**Microsoft Lync Server 2013 Health**]、[**Call Reliability and Media Quality**]、[**Media Quality**] の順に展開します。

Lync Server 2013 用の管理パックは、Microsoft Lync Server 2010 で使用される中央の検出メカニズムではなく、マシンレベルの検出を使用するようになりました。 つまり、各システムセンターエージェントは本質的に自分自身を検出し、その存在を中央管理サーバーに報告します。 コンピューターレベルの検出を使用すると、システムセンターインフラストラクチャの管理が簡単になり、Lync server 管理パックのさまざまなバージョン (lync server 2010 用の管理パック、Lync Server 2013 用の管理パックなど) も可能になります。混在.

</div>

<span> </span>

</div>

</div>

</div>

