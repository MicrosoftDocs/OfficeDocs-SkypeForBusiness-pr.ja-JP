---
title: 'Lync Server 2013: 監視サーバーレポートの表示と分析'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing and analyzing monitoring server reports
ms:assetid: 4dd448f1-01d2-49b2-b109-0728f36566b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720332(v=OCS.15)
ms:contentKeyID: 63969599
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e4fce6cf17601d2a68a07a3b832e6b50c10b759
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757361"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-and-analyzing-monitoring-server-reports-in-lync-server-2013"></a>Lync Server 2013 で監視サーバーレポートを表示および分析する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-05-19_

サーバーレポートを監視すると、音声品質のさまざまな測定が行われ、エンドユーザーに配信される QoE が監視されます。 さらに、Monitoring Server には、組織のネットワークの使用状況やメディア品質の傾向を監視したり、発生したメディアの品質に関する問題のトラブルシューティングに使用できる、いくつかの組み込みレポートが含まれています。

毎日および毎週の操作でサーバーレポートの監視を行う主な部分は、次のようにメディア品質レポートを表示して分析することです。

  - QoE サマリー/トレンドレポート

  - QoE のパフォーマンスレポート

<div>

## <a name="view-reports-from-the-monitoring-server"></a>監視サーバーからレポートを表示する

1.  Web ブラウザーから、SQL reporting services をホストしているサーバーを見つけます。

2.  ブラウザー画面から必要なレポートを表示します。

3.  省略エクスポートオプションと必要な出力形式を選択して、レポートをエクスポートします。

</div>

<div>

## <a name="configure-call-detail-recording-cdr"></a>通話の詳細記録 (CDR) を構成する

1.  RTCUniversalServerAdmins グループのメンバーであるか (同等の権限を持つ)、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントから、Lync Server 2013 を展開したネットワーク内の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。

3.  左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**通話詳細記録**] をクリックします。

4.  [**通話詳細記録**] ページで、表から適切なサイトをクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。

5.  [削除] を有効にするには、[**監視サーバーに対して消去を有効**にする] を選択します。

6.  [**通話の詳細記録を保持する期間 (日数)]:** 通話の詳細レコーディングの保持期間の最大値を選びます。

7.  [**エラー報告データの最大保持期間 (日)**] で、 エラー報告を保持する必要のある最大日数を選択します。

8.  [**確定**] をクリックします。

</div>

<div>

## <a name="configure-qoe"></a>QoE の構成

1.  RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。 詳細については、「Delegate Setup Permissions」を参照してください。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。

3.  左側のナビゲーション バーで [**監視とアーカイブ**] をクリックし、[**QoE データ**] をクリックします。

4.  [**QoE データ**] ページで、表から該当するサイトをクリックして、[**編集**] をクリックし、[**詳細の表示**] をクリックします。

5.  [削除] を有効にするには、[**監視サーバーに対して消去を有効**にする] を選択します。

6.  [**通話を継続する] の [最長時間 (日数)]:** qoe データを保持する最大日数を選びます。

7.  [コミット] をクリックします。

</div>

<div>

## <a name="change-the-archiving-policy"></a>アーカイブポリシーを変更する

1.  CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。

3.  左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ ポリシー**] をクリックします。

4.  ポリシーの一覧の [**グローバル**] をクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。

5.  [**アーカイブ ポリシーの編集 - グローバル**] で、以下の手順を実行します。

6.  展開の内部アーカイブを有効または無効にするには、[**内部通信をアーカイブ**する] チェックボックスをオンまたはオフにします。

7.  展開の外部アーカイブを有効または無効にするには、[**外部の通信をアーカイブ**する] チェックボックスをオンまたはオフにします。

8.  [**コミット**] をクリックします。

</div>

<div>

## <a name="apply-an-archiving-policy-to-a-user"></a>ユーザーにアーカイブポリシーを適用する

1.  CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。

3.  左側のナビゲーション バーで [**ユーザー**] をクリックし、構成するユーザー アカウントを検索します。

4.  検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。

5.  [**アーカイブポリシー**] の [ **Lync Server ユーザーの編集**] で、適用するアーカイブユーザーポリシーを選択します。

6.  [**コミット**] をクリックします。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 で監視レポートを使用する](lync-server-2013-using-monitoring-reports.md)  
[Lync Server 2013 のサーバーパフォーマンスレポート](lync-server-2013-server-performance-report.md)  
[Lync Server 2013 のメディア品質比較レポート](lync-server-2013-media-quality-comparison-report.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

