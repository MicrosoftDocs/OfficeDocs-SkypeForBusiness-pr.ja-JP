---
title: ネットワーク地域リンクの作成
TOCTitle: ネットワーク地域リンクの作成
ms:assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg413047(v=OCS.15)
ms:contentKeyID: 48274102
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ネットワーク地域リンクの作成

 

_**トピックの最終更新日:** 2012-10-19_

ネットワーク内の地域は、物理的な WAN 接続を経由してリンクされます。 *ネットワーク地域リンク*は、通話受付管理 (CAC) 用に構成された 2 つの地域間のリンクを作成し、これらの地域間の音声トラフィックとビデオ トラフィックに帯域幅制限を設定します。

ネットワーク地域リンクの操作の詳細については、「Lync Server 管理シェル」のドキュメントに記載されている次のコマンドレットを参照してください。

  - [New-CsNetworkRegionLink](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkRegionLink)

  - [Get-CsNetworkRegionLink](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkRegionLink)

  - [Set-CsNetworkRegionLink](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkRegionLink)

  - [Remove-CsNetworkRegionLink](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkRegionLink)

トポロジの例では、North America 地域と APAC 地域間のリンク、および EMEA 地域と APAC 地域間のリンクを含みます。 これらの地域リンクは、「計画」のドキュメントの「[例: Lync Server 2013 での通話受付管理の組織要件の収集](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)」セクションの「地域リンクの帯域幅情報」表で説明するように、それぞれ WAN 帯域幅による制約を受けます。

## Lync Server 管理シェルを使用して、ネットワーク地域リンクを作成するには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  New-CsNetworkRegionLink コマンドレットを実行して、地域リンクを作成し、適切な帯域幅ポリシー プロファイルを適用します。たとえば、以下を実行します。
    
        New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link

       &nbsp;
    
        New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link

## Lync Server コントロール パネルを使用して、ネットワーク地域リンクを作成するには

1.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

2.  左側のナビゲーション バーで \[**ネットワーク構成**\] をクリックします。

3.  \[**地域リンク**\] ナビゲーション ボタンをクリックします。

4.  \[**新規**\] をクリックします。

5.  \[**新しい地域リンク**\] ページで、\[**名前**\] をクリックし、ネットワーク地域リンクの名前を入力します。

6.  \[**ネットワーク地域 \#1**\] をクリックし、一覧でネットワーク地域 \#2 にリンクするネットワーク地域をクリックします。

7.  \[**ネットワーク地域 \#2**\] をクリックし、一覧でネットワーク地域 \#1 にリンクするネットワーク地域をクリックします。

8.  オプションで、\[**帯域幅ポリシー**\] をクリックし、ネットワーク地域リンクに適用する帯域幅ポリシーのプロファイルを選択します。
    
    > [!NOTE]
    > 帯域幅ポリシーは、ネットワーク地域リンクの帯域幅に制約があり、そのリンクのメディア トラフィックを CAC を使用して操作する場合に限り、適用します。


9.  \[**確定**\] をクリックします。

10. 他の地域についての設定を二間してステップ 4 ～ 9 を繰り返し、ご使用のトポロジのネットワーク地域リンクの作成を完了します。

