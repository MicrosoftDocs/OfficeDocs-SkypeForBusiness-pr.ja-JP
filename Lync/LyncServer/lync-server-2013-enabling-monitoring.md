---
title: 'Lync Server 2013: 監視の有効化'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling monitoring
ms:assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687994(v=OCS.15)
ms:contentKeyID: 49733584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e0b637ea06d0255d53f73eef0385c3e929045071
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528534"
---
# <a name="enabling-monitoring-in-lync-server-2013"></a>Lync Server 2013 での監視の有効化

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-17_

統合データ収集エージェントは各フロントエンドサーバーに自動的にインストールされ、アクティブ化されますが、Microsoft Lync Server 2013 のインストールが完了すると、自動的に監視データの収集が開始されるということではありません。 その代わりに、フロントエンドサーバーとフロントエンドプールを監視データベースに関連付ける必要があります。また、通話詳細記録 (CDR) および Quality of Experience (QoE) の監視をグローバルスコープまたはサイトスコープで有効にする必要があります。

フロントエンドサーバーまたはフロントエンドプールを監視データベースに関連付ける詳細な手順については、「展開ガイド」の「 [Lync Server 2013 でのフロントエンドプールへの監視ストアの関連付け](lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md) 」を参照してください。 これらの関連付けが終わり、新しい Lync Server トポロジを公開しても、まだ監視データを収集することはできません。 これは、既定では、Lync Server 2013 をインストールすると、CDR と QoE のデータ収集の両方が無効になるためです。

データ収集を開始するには、CDR 監視と QoE 監視のどちらかまたは両方を有効にする必要があります (CDR 監視と QoE 監視を両方とも有効にする必要はありません。 (必要に応じて、1つの種類の監視を有効にして、もう一方の種類を無効のままにすることができます)。グローバルスコープで CDR 監視を有効にするには、Lync Server 管理シェルで次のコマンドを実行します。

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

または、Lync Server 2013 コントロールパネル内から CDR の監視を有効にすることもできます。 Lync Server コントロールパネル内から、次の手順を実行します。

1.  [**監視**] をクリックします。

2.  [**通話詳細記録**] タブで、[**グローバル**] 設定をダブルクリックします。

3.  [**編集 通話詳細記録 (CDR) 設定**] ウィンドウで、[**CDR の監視を有効にする**] を選択し、[**コミット**] をクリックします。

グローバルスコープで QoE 監視を有効にするには、Lync Server 管理シェルで次のコマンドを実行します。

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $True

必要に応じて、Lync Server コントロールパネル内から QoE 監視を有効にすることもできます。 コントロール パネル内で、次の手順を実行します。

1.  [**監視**] をクリックします。

2.  [**QoE データ**] タブで、[**グローバル**] 設定をダブルクリックします。

3.  [**編集 Quality of Experience (QoE) 設定**] ウィンドウで、[**QoE データの監視を有効にする**] を選択し、[**コミット**] をクリックします。

前述したように、前述の例では、グローバルスコープで監視を有効にします。つまり、組織全体での CDR と QoE の監視を有効にします。 または、サイトスコープで個別の CDR と QoE の構成設定を作成してから、各サイトの監視を選択的に有効または無効にすることもできます。 たとえば、Redmond サイトで CDR 監視を有効にしても、ダブリンサイトの CDR 監視を無効にすることができます。 監視構成設定の管理の詳細については、「 [Lync Server 2013 の通話詳細記録と qoe (Quality Of Experience) の設定を構成する](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md)」トピックを参照してください。

</div>

<span> </span>

</div>

</div>

</div>

