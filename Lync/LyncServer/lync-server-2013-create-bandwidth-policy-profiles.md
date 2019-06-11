---
title: 'Lync Server 2013: 帯域幅ポリシープロファイルを作成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create bandwidth policy profiles
ms:assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412785(v=OCS.15)
ms:contentKeyID: 48185086
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9464e83370690e018374c4ffb60e0b61c30fe300
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833854"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-bandwidth-policy-profiles-in-lync-server-2013"></a>Lync Server 2013 で帯域幅ポリシープロファイルを作成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-19_

*帯域幅ポリシー*は、リアルタイムのオーディオおよびビデオのモダリティについて、帯域幅使用量の制限を定義します。帯域幅ポリシーは*帯域幅ポリシーのプロファイル*に適用され、帯域幅ポリシーのプロファイルは通話受付管理のために複数のネットワーク サイトに適用することができます。

CAC 展開で設定する必要がある帯域幅制限のガイドラインについては、「計画ドキュメントの[Lync Server 2013 での通話受付制御の要件の定義](lync-server-2013-defining-your-requirements-for-call-admission-control.md)」を参照してください。

帯域幅ポリシーおよびポリシープロファイルの使用について詳しくは、次のコマンドレットの Lync Server 管理シェルに関するドキュメントをご覧ください。

  - [新規-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)

  - [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)

  - [Set-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)

  - [Remove-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)

次の手順で作成されるポリシーの例は、オーディオ トラフィック全体、個々のオーディオ セッション、ビデオ トラフィック全体、および個々のビデオ セッションに制限を設定します。 たとえば、5Mb\_のリンク帯域幅ポリシープロファイルは、次の制限を設定します。

  - オーディオ リミット: 2,000 kbps

  - オーディオ セッション リミット: 200 kbps

  - ビデオ リミット: 1,400 kbps

  - ビデオ セッション リミット: 700 kbps

<div class=" ">


> [!NOTE]  
> オーディオ セッション リミットの最小値は 40 kbps です。 ビデオ セッション リミットの最小値は 100 kbps です。



</div>

<div>

## <a name="to-create-bandwidth-policy-profiles-by-using-management-shell"></a>管理シェルを使用して帯域幅ポリシープロファイルを作成するには

1.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  作成する帯域幅ポリシーのプロファイルごとに、New-CsNetworkBandwidthPolicyProfile コマンドレットを実行します。 たとえば、以下を実行します。
    
       ```
        New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400  -VideoBWSessionLimit 700
       ```
    
       ```
        New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
       ```
    
       ```
        New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
       ```
    
       ```
        New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
       ```

</div>

<div>

## <a name="to-create-bandwidth-policy-profiles-by-using-lync-server-control-panel"></a>Lync Server コントロールパネルを使用して帯域幅ポリシープロファイルを作成するには

1.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

2.  左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。

3.  [**ポリシーのプロファイル**] ナビゲーション ボタンをクリックします。

4.  [**新規**] をクリックします。

5.  [**新しいポリシーのプロファイル**] ページで、[**名前**] をクリックし、帯域幅ポリシー プロファイルの名前を入力します。

6.  [**オーディオ リミット**] をクリックし、すべてのオーディオ セッションを組み合わせた合計に対して許可する最大値 (kbps) を入力します。

7.  [**オーディオ セッション リミット**] をクリックし、個々のオーディオ セッションに対して許可する最大値 (kbps) を入力します。

8.  [**ビデオ リミット**] をクリックし、すべてのビデオ セッションを組み合わせた合計に対して許可する最大値 (kbps) を入力します。

9.  [**ビデオ セッション リミット**] をクリックし、個々のビデオ セッションに対して許可する最大値 (kbps) を入力します。

10. 必要に応じて、[**説明**] をクリックし、この帯域幅ポリシーのプロファイルを説明する追加情報を入力します。

11. [**確定**] をクリックします。

12. トポロジの帯域幅ポリシーのプロファイル作成を完了するには、他の帯域幅ポリシーのプロファイルの設定値を使用してステップ 4 ～ 11 を繰り返します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

