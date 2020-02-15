---
title: 'Lync Server 2013: ネットワークサイトを作成または変更する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a network site
ms:assetid: 14e24856-9996-4da4-9f31-300940bdf5aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398218(v=OCS.15)
ms:contentKeyID: 48183488
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce676c4e86d6bceae81d60897846e3005780eb58
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046020"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-network-site-in-lync-server-2013"></a>Lync Server 2013 でのネットワークサイトの作成または変更

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-24_

通話受付管理 (CAC)、E9-1-1、およびメディアバイパスの展開は、で定義され、常にネットワーク地域に関連付けられている*ネットワークサイト*の構成に依存します。 ネットワークサイトは、ブランチオフィスの場所、建物のセット、またはキャンパスを表します。 ネットワークサイトは、帯域幅が類似しているサブネットの集合を表します。

ネットワーク サイトを作成または変更するには、以下の手順を使用します。 たとえば、1 つの音声機能について既にネットワーク サイトを作成している場合は、新しいネットワーク サイトを作成する必要はありません。他の音声機能も既存の同じサイトを使用します。 ただし、既存のネットワーク サイトの定義を変更して機能固有の設定を適用しなければならない場合があります。 たとえば、E9-1-1 用のネットワーク サイトを作成している場合、通話受付管理の展開時にネットワーク サイトを変更して、帯域幅ポリシー プロファイルを適用する必要があります。

<div>


> [!NOTE]  
> 機能固有の設定が存在する場合、機能ごとに「展開」のドキュメントに記載されている高度な音声機能に関連するネットワーク サイトの具体的な例と要件については、次を参照してください。 
> <UL>
> <LI>
> <P><A href="lync-server-2013-configure-network-sites-for-cac.md">Lync Server 2013 で CAC のネットワークサイトを構成する</A></P></LI></UL>



</div>

ネットワークサイトの使用の詳細については、以下のコマンドレットの Lync Server Management Shell のドキュメントを参照してください。

  - [新しい-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

  - [-CsNetworkSite の取得](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)

  - [設定-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

  - [-CsNetworkSite の削除](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)

<div>

## <a name="create-a-network-site"></a>ネットワーク サイトの作成

通話受付管理、E9-1-1、またはメディア バイパスで使用できるネットワーク地域を作成します。

<div>

## <a name="to-create-a-network-site-by-using-management-shell"></a>管理シェルを使用して、ネットワーク サイトを作成するには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  New-CsNetworkSite コマンドレットを実行して、ネットワーク サイトを作成します。
    
        New-CsNetworkSite -NetworkSiteID <string>
    
    例:
    
        New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
    
    この例では、"NorthAmerica" ネットワーク地域に "Chicago" という名前のネットワーク サイトが作成されました。
    
    <div>
    

    > [!NOTE]  
    > このコマンドを正常に実行するには、NorthAmerica ネットワーク地域があらかじめ存在する必要があります。

    
    </div>

3.  トポロジのネットワーク サイトを作成するには、他のサイトの設定に関してステップ 2 を繰り返します。

</div>

<div>

## <a name="to-create-a-network-site-by-using-lync-server-control-panel"></a>Lync Server コントロール パネルを使用して、ネットワーク サイトを作成するには

1.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

2.  左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。

3.  [**サイト**] ナビゲーション ボタンをクリックします。

4.  [**新規**] をクリックします。

5.  [**新しいサイト**] ページで、[**名前**] をクリックしてネットワーク サイトの名前を入力します。

6.  [**地域**] をクリックして、リストで地域をクリックします。

7.  オプションで、[**帯域幅ポリシー**] をクリックして、リストで帯域幅ポリシーをクリックします。
    
    <div>
    

    > [!NOTE]  
    > 帯域幅ポリシーが必要なのは、サイトで通話受付管理を展開する場合だけです。

    
    </div>

8.  オプションで、[**場所のポリシー**] をクリックして、リストで場所のポリシーをクリックします。
    
    <div>
    

    > [!NOTE]  
    > 場所のポリシーが必要なのは、サイトで E9-1-1 を展開する場合だけです。

    
    </div>

9.  オプションで、[**説明**] をクリックして、このネットワーク サイトを説明する追加情報を入力します。

10. [**確定**] をクリックします。

11. 他のサイトについての設定に関してステップ 4 ～ 10 を繰り返し、ご使用のトポロジのネットワーク サイトの作成を完了します。

</div>

</div>

<div>

## <a name="modify-a-network-site"></a>ネットワーク サイトの変更

通話受付管理、E9-1-1、またはメディア バイパスで使用できるネットワーク地域を変更します。

<div>

## <a name="to-modify-a-network-site"></a>ネットワーク サイトを変更するには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  Set-CsNetworkSite コマンドレットを実行して、ネットワーク サイトを変更します。
    
        Set-CsNetworkSite -Identity <string>
    
    次にその例を示します。
    
        Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
    
    この例では、"Albuquerque" という名前のサイトが "NorthAmerica" ネットワーク地域に移動されます。 ネットワーク サイトの構成を変更して、通話受付管理、E9-1-1、またはメディア バイパスを展開するには、Set-CsNetworkSite コマンドレットをそれぞれ BWPolicyProfileID または LocationPolicy パラメーターと組み合わせて実行し、ネットワーク サイトの設定を変更します。
    
    <div>
    

    > [!NOTE]  
    > メディア バイパス用に BypassID パラメーターが用意されていますが、自動生成されるバイパス ID を無効にしないことを強くお勧めします。 メディア バイパス用にネットワーク サイトを構成するために、追加パラメーターを指定する必要はありません。

    
    </div>

3.  他のサイトについての設定に関してステップ 2 を繰り返し、ご使用のトポロジのネットワーク サイトの変更を完了します。

</div>

<div>

## <a name="to-modify-a-network-site-by-using-lync-server-control-panel"></a>Lync Server コントロール パネルを使用して、ネットワーク サイトを変更するには

1.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

2.  左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。

3.  [**サイト**] ナビゲーション ボタンをクリックします。

4.  表内で、変更するネットワーク サイトをクリックします。

5.  [**編集**] をクリックして、[**詳細の表示...**] をクリックします。

6.  [**サイトの編集**] ページで、このネットワーク サイトの設定値を必要に応じて変更します。

7.  [**確定**] をクリックします。

8.  他のサイトについての設定に関してステップ 4 ～ 7 を繰り返し、ネットワーク サイトの変更を完了します。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

