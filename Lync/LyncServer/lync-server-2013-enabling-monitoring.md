---
title: 'Lync Server 2013: 監視を有効にする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling monitoring
ms:assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687994(v=OCS.15)
ms:contentKeyID: 49733584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2b13028390328e93a9e90636962dedea8ea8ec9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833257"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-monitoring-in-lync-server-2013"></a>Lync Server 2013 で監視を有効にする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-17_

統合データ収集エージェントは、各フロントエンドサーバーに自動的にインストールされ、アクティブ化されますが、Microsoft Lync Server 2013 のインストールが完了した時点で自動的に監視データの収集が開始されるとは限りません。 代わりに、フロントエンドサーバー/フロントエンドプールを監視データベースに関連付ける必要があります。また、グローバルスコープまたはサイトの範囲で、通話の詳細記録 (CDR) および品質のエクスペリエンス (QoE) の監視を有効にする必要があります。

フロントエンドサーバーまたはフロントエンドプールと監視データベースの関連付けの詳細な手順については、展開ガイドの「 [Lync Server 2013 でのフロントエンドプールへの監視ストアの関連付け](lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md)」を参照してください。 この関連付けが行われた後、新しい Lync サーバートポロジが公開された後でも、監視データを収集することはできません。 これは、Lync Server 2013 をインストールしたときに、既定では CDR と QoE のデータ収集が無効になるためです。

データの収集を開始するには、CDR または QoE の監視を有効にする必要があります。 (CDR と QoE の両方の監視を有効にする必要はありません。必要に応じて、他の種類を無効のままにして、1つの種類の監視を有効にすることができます)。グローバルスコープで CDR の監視を有効にするには、Lync Server 管理シェルで次のコマンドを実行します。

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

または、Lync Server 2013 コントロールパネル内から CDR の監視を有効にすることもできます。 Lync Server コントロールパネル内で、次の手順を実行します。

1.  [**モニタリング**] をクリックします。

2.  [**通話の詳細記録**] タブで、[**グローバル**設定] をダブルクリックします。

3.  [**通話の詳細記録 (CDR) の設定**] ウィンドウで、[ **CDRs の監視を有効にする**] を選び、[**コミット**] をクリックします。

グローバルスコープで QoE の監視を有効にするには、Lync Server 管理シェルで次のコマンドを実行します。

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $True

必要に応じて、Lync Server コントロールパネル内から QoE の監視を有効にすることもできます。 コントロールパネルで、次の手順を実行します。

1.  [**モニタリング**] をクリックします。

2.  [**エクスペリエンスの品質データ**] タブで、[**グローバル**設定] をダブルクリックします。

3.  [ **Quality Of Experience (qoe) の設定**] ウィンドウで、[ **qoe データの監視を有効にする**] を選び、[**コミット**] をクリックします。

既に説明したように、上の例ではグローバルスコープで監視を有効にします。つまり、ユーザーは組織全体で CDR と QoE の監視を行うことができます。 または、サイトのスコープで個別の CDR と QoE の構成設定を作成して、各サイトの監視を個別に有効または無効にすることもできます。 たとえば、Redmond サイトで CDR の監視を有効にしていても、ダブリンサイトの CDR 監視を無効にすることができます。 監視構成の設定を管理する方法について詳しくは、「 [Lync Server 2013 での通話の詳細の記録と音質の設定](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md)」を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

