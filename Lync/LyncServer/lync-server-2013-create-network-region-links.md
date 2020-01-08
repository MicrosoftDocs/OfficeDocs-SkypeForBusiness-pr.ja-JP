---
title: 'Lync Server 2013: ネットワーク領域リンクを作成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create network region links
ms:assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413047(v=OCS.15)
ms:contentKeyID: 48185873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c0f21f599b8afa4f9f31ec16aad82e305c8a08e
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971262"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-network-region-links-in-lync-server-2013"></a>Lync Server 2013 でネットワークの地域リンクを作成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-19_

ネットワーク内の地域は、物理的な WAN 接続を経由してリンクされます。 [*ネットワーク領域] リンク*は、通話受付制御 (CAC) 用に構成された2つの領域間のリンクを作成し、これらの地域間の音声とビデオのトラフィックの帯域幅の制限を設定します。

ネットワーク領域へのリンクの操作の詳細については、次のコマンドレットの Lync Server 管理シェルに関するドキュメントを参照してください。

  - [新しい-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)

  - [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [Set-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)

  - [CsNetworkRegionLink を削除する](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)

トポロジの例では、North America 地域と APAC 地域間のリンク、および EMEA 地域と APAC 地域間のリンクを含みます。 計画ドキュメントの「 [Lync Server 2013 で通話受付制御の要件を収集](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)する」で説明されているように、これらの地域リンクはそれぞれ WAN の帯域幅によって制限されます。

<div>

## <a name="to-create-network-region-links-by-using-lync-server-management-shell"></a>Lync Server 管理シェルを使用してネットワーク領域のリンクを作成するには

1.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  New-CsNetworkRegionLink コマンドレットを実行して、地域リンクを作成し、適切な帯域幅ポリシー プロファイルを適用します。 たとえば、以下を実行します。
    
      ```powershell
        New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
      ```
    
      ```powershell
        New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
      ```

</div>

<div>

## <a name="to-create-network-region-links-by-using-lync-server-control-panel"></a>Lync Server コントロールパネルを使用してネットワーク領域のリンクを作成するには

1.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

2.  左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。

3.  [**地域リンク**] ナビゲーション ボタンをクリックします。

4.  [**新規**] をクリックします。

5.  [**新しい地域リンク**] ページで、[**名前**] をクリックし、ネットワーク地域リンクの名前を入力します。

6.  [**ネットワーク領域\#1**] をクリックし、ネットワーク領域\#2 にリンクさせるリストのネットワーク領域をクリックします。

7.  [**ネットワーク領域\#2**] をクリックし、ネットワーク領域\#1 にリンクさせるリスト内のネットワーク領域をクリックします。

8.  オプションで、[**帯域幅ポリシー**] をクリックし、ネットワーク地域リンクに適用する帯域幅ポリシーのプロファイルを選択します。
    
    <div class=" ">
    

    > [!NOTE]  
    > 帯域幅ポリシーは、ネットワーク地域リンクの帯域幅に制約があり、そのリンクのメディア トラフィックを CAC を使用して操作する場合に限り、適用します。

    
    </div>

9.  [**確定**] をクリックします。

10. 他の地域についての設定でステップ 4 ～ 9 を繰り返し、ご使用のトポロジのネットワーク地域リンクの作成を完了します。

</div>

</div>

<span> </span>

</div>

</div>

</div>
