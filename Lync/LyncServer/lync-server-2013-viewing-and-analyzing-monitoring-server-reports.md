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
ms.openlocfilehash: 7416b54e7b1ddb5bfc41c07502802c7c120a93ba
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523574"
---
# <a name="viewing-and-analyzing-monitoring-server-reports-in-lync-server-2013"></a>Lync Server 2013 での監視サーバーレポートの表示と分析

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-05-19_

監視サーバーレポートでは、エンドユーザーに配信されている QoE を監視するために、さまざまな音声品質の測定を行うことができます。 さらに、監視サーバーには、組織のネットワークで利用状況やメディア品質の傾向を監視し、発生したメディア品質の問題のトラブルシューティングに使用できる組み込みのレポートがいくつか含まれています。

毎日および毎週の操作について監視サーバーレポートを保持する主な部分は、特にメディア品質レポートを表示および分析することです。

  - QoE の概要/傾向レポート

  - QoE パフォーマンスレポート

<div>

## <a name="view-reports-from-the-monitoring-server"></a>監視サーバーからレポートを表示する

1.  Web ブラウザーから、SQL reporting services をホストしているサーバーを見つけます。

2.  ブラウザーの画面から必要なレポートを表示します。

3.  オプションエクスポートオプションと必要な出力形式を選択して、レポートをエクスポートします。

</div>

<div>

## <a name="configure-call-detail-recording-cdr"></a>通話詳細記録 (CDR) を構成する

1.  RTCUniversalServerAdmins グループのメンバーである (またはそれと同等のアクセス許可を持つ) ユーザーアカウント、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントから、Lync Server 2013 を展開したネットワーク内の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。

3.  左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**通話詳細記録**] をクリックします。

4.  [**通話詳細記録**] ページで、表から適切なサイトをクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。

5.  削除を有効にするには、[ **監視サーバーの削除を有効**にする] を選択します。

6.  [ **通話詳細記録の最大保持期間** (日)] で、通話詳細記録を保持する最大日数を選択します。

7.  [**エラー報告データの最大保持期間 (日)**] で、 エラー報告を保持する必要のある最大日数を選択します。

8.  [**確定**] をクリックします。

</div>

<div>

## <a name="configure-qoe"></a>QoE を構成する

1.  RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。 詳細については、「セットアップのアクセス許可の委任」を参照してください。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。

3.  左側のナビゲーション バーで [**監視とアーカイブ**] をクリックし、[**QoE データ**] をクリックします。

4.  [**QoE データ**] ページで、表から該当するサイトをクリックして、[**編集**] をクリックし、[**詳細の表示**] をクリックします。

5.  削除を有効にするには、[ **監視サーバーの削除を有効**にする] を選択します。

6.  [ **通話詳細記録の最大保持期間** (日)] で、qoe データを保持する最大日数を選択します。

7.  [確定] をクリックします。

</div>

<div>

## <a name="change-the-archiving-policy"></a>アーカイブポリシーを変更する

1.  CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。

3.  左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ ポリシー**] をクリックします。

4.  ポリシー一覧の **[グローバル]** をクリックし、**[編集]** をクリックしてから、**[詳細の表示]** をクリックします。

5.  **[アーカイブ ポリシーの編集 - グローバル]** で、以下の手順を実行します。

6.  展開の内部アーカイブを有効または無効にするには、[ **内部通信をアーカイブ** する] チェックボックスをオンまたはオフにします。

7.  展開の外部アーカイブを有効または無効にするには、[ **外部通信をアーカイブ** する] チェックボックスをオンまたはオフにします。

8.  [**確定**] をクリックします。

</div>

<div>

## <a name="apply-an-archiving-policy-to-a-user"></a>ユーザーへのアーカイブポリシーの適用

1.  CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。

3.  左側のナビゲーション バーで [**ユーザー**] をクリックし、構成するユーザー アカウントを検索します。

4.  検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。

5.  [ **Lync Server ユーザーの編集** ] の [ **アーカイブポリシー**] で、適用するアーカイブユーザーポリシーを選択します。

6.  [**確定**] をクリックします。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での監視レポートの使用](lync-server-2013-using-monitoring-reports.md)  
[Lync Server 2013 のサーバーパフォーマンスレポート](lync-server-2013-server-performance-report.md)  
[Lync Server 2013 のメディア品質比較レポート](lync-server-2013-media-quality-comparison-report.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

