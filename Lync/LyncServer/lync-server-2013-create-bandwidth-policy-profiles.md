---
title: 帯域幅ポリシー プロファイルの作成
TOCTitle: 帯域幅ポリシー プロファイルの作成
ms:assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412785(v=OCS.15)
ms:contentKeyID: 48273203
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 帯域幅ポリシー プロファイルの作成

 

_**トピックの最終更新日:** 2012-10-19_

*帯域幅ポリシー*は、リアルタイムのオーディオおよびビデオのモダリティについて、帯域幅使用量の制限を定義します。 帯域幅ポリシーは*帯域幅ポリシーのプロファイル*に適用され、帯域幅ポリシーのプロファイルは通話受付管理のために複数のネットワーク サイトに適用することができます。

CAC の展開にどの程度の帯域幅制限を設定する必要があるかのガイドラインについては、「計画」のドキュメントの「[Lync Server 2013 での通話受付管理サービス要件の定義](lync-server-2013-defining-your-requirements-for-call-admission-control.md)」を参照してください。

帯域幅ポリシーと帯域幅ポリシーのプロファイルの利用についての詳細は、「Lync Server 管理シェル」のドキュメントに記載されている次のコマンドレットを参照してください。

  - [New-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)

  - [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)

  - [Set-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)

  - [Remove-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)

次の手順で作成されるポリシーの例は、オーディオ トラフィック全体、個々のオーディオ セッション、ビデオ トラフィック全体、および個々のビデオ セッションに制限を設けます。 たとえば、5Mb\_Link の帯域幅のポリシーのプロファイルは次の制限値を設定します。

  - オーディオ リミット: 2,000 kbps

  - オーディオ セッション リミット: 200 kbps

  - ビデオ リミット: 1,400 kbps

  - ビデオ セッション リミット: 700 kbps

> [!NOTE]
> オーディオ セッション リミットの最小値は 40 kbps です。 ビデオ セッション リミットの最小値は 100 kbps です。


## 管理シェルを使用して帯域幅ポリシー プロファイルを作成するには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  作成する帯域幅ポリシーのプロファイルごとに、New-CsNetworkBandwidthPolicyProfile コマンドレットを実行します。たとえば、以下を実行します。
    
        New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400  -VideoBWSessionLimit 700

       &nbsp;
    
        New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700

       &nbsp;
    
        New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700

       &nbsp;
    
        New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700

## Lync Server コントロール パネルを使用して帯域幅ポリシーのプロファイルを作成するには

1.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

2.  左側のナビゲーション バーで \[**ネットワーク構成**\] をクリックします。

3.  \[**ポリシーのプロファイル**\] ナビゲーション ボタンをクリックします。

4.  \[**新規**\] をクリックします。

5.  \[**新しいポリシーのプロファイル**\] ページで、\[**名前**\] をクリックし、帯域幅ポリシー プロファイルの名前を入力します。

6.  \[**オーディオ リミット**\] をクリックし、すべてのオーディオ セッションを組み合わせた合計に対して許可する最大値 (kbps) を入力します。

7.  \[**オーディオ セッション リミット**\] をクリックし、個々のオーディオ セッションに対して許可する最大値 (kbps) を入力します。

8.  \[**ビデオ リミット**\] をクリックし、すべてのビデオ セッションを組み合わせた合計に対して許可する最大値 (kbps) を入力します。

9.  \[**ビデオ セッション リミット**\] をクリックし、個々のビデオ セッションに対して許可する最大値 (kbps) を入力します。

10. 必要に応じて、\[**説明**\] をクリックし、この帯域幅ポリシーのプロファイルを説明する追加情報を入力します。

11. \[**確定**\] をクリックします。

12. トポロジの帯域幅ポリシーのプロファイル作成を完了するには、ステップ 4 ～ 11 を繰り返して、他の帯域幅ポリシーのプロファイルを設定します。

