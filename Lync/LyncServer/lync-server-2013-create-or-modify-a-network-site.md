---
title: 'Lync Server 2013: ネットワーク サイトの作成または変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a network site
ms:assetid: 14e24856-9996-4da4-9f31-300940bdf5aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398218(v=OCS.15)
ms:contentKeyID: 48183488
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1afb986f88af11ee2020b760e0a6d65aabed838c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833804"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-network-site-in-lync-server-2013"></a>Lync Server 2013 でのネットワーク サイトの作成または変更

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-24_

通話受付制御 (CAC)、E9、および media バイパスの展開は、ネットワークの領域に定義され、常に関連付けられている*ネットワークサイト*の構成に依存します。 ネットワークサイトは、支社の場所、建物のセット、またはキャンパスを表します。 ネットワークサイトは、同様の帯域幅のサブネットのコレクションを表します。

ネットワークサイトを作成または変更するには、次の手順を使用します。 たとえば、1つの音声機能のネットワークサイトを既に作成している場合、新しいネットワークサイトを作成する必要はありません。その他の音声機能でも同じサイトが使用されます。 ただし、機能固有の設定を適用するには、既存のネットワークサイト定義を変更する必要がある場合があります。 たとえば、E9 のネットワークサイトを作成した場合、通話受付制御の展開中にネットワークサイトを変更して、帯域幅ポリシープロファイルを適用する必要があります。

<div>


> [!NOTE]  
> これらが存在する場合は、各機能の展開ドキュメントの高度な音声機能に関連するネットワークサイトの具体的な例と要件を見つけることができます。 
> <UL>
> <LI>
> <P><A href="lync-server-2013-configure-network-sites-for-cac.md">Lync Server 2013 での CAC 用のネットワークサイトの構成</A></P></LI></UL>



</div>

ネットワークサイトの操作の詳細については、次のコマンドレットの Lync Server 管理シェルに関するドキュメントを参照してください。

  - [新しい-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

  - [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)

  - [Set-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

  - [CsNetworkSite の削除](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)

<div>

## <a name="create-a-network-site"></a>ネットワークサイトを作成する

通話受付制御、E9、またはメディアバイパスで使用できるネットワーク領域を作成します。

<div>

## <a name="to-create-a-network-site-by-using-management-shell"></a>管理シェルを使用してネットワークサイトを作成するには

1.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  New-CsNetworkSite コマンドレットを実行して、ネットワーク サイトを作成します。
    
        New-CsNetworkSite -NetworkSiteID <string>
    
    次に例を示します。
    
        New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
    
    この例では、"NorthAmerica" ネットワーク地域に "Chicago" という名前のネットワーク サイトが作成されました。
    
    <div>
    

    > [!NOTE]  
    > このコマンドを正常に実行するには、NorthAmerica ネットワーク地域があらかじめ存在する必要があります。

    
    </div>

3.  トポロジのネットワーク サイトを作成するには、他のサイトの設定値を使用してステップ 2 を繰り返します。

</div>

<div>

## <a name="to-create-a-network-site-by-using-lync-server-control-panel"></a>Lync Server コントロールパネルを使用してネットワークサイトを作成するには

1.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

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

10. [**コミット**] をクリックします。

11. 使用しているトポロジのネットワーク サイトの作成を完了するには、他のサイトの設定値を使用してステップ 4 ～ 10 を繰り返します。

</div>

</div>

<div>

## <a name="modify-a-network-site"></a>ネットワークサイトを変更する

通話受付制御、E9、またはメディアバイパスで使用できるネットワークの領域を変更します。

<div>

## <a name="to-modify-a-network-site"></a>ネットワークサイトを変更するには

1.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  Set-CsNetworkSite コマンドレットを実行して、ネットワーク サイトを変更します。
    
        Set-CsNetworkSite -Identity <string>
    
    例:
    
        Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
    
    この例では、"Albuquerque" という名前のサイトが "NorthAmerica" ネットワーク地域に移動されます。ネットワーク サイトの構成を変更して、通話受付管理、E9-1-1、またはメディア バイパスを展開するには、Set-CsNetworkSite コマンドレットをそれぞれ BWPolicyProfileID または LocationPolicy パラメーターと組み合わせて実行し、ネットワーク サイトの設定を変更します。
    
    <div>
    

    > [!NOTE]  
    > メディア バイパス用に BypassID パラメーターが用意されていますが、自動生成されるバイパス ID を上書きしないことを強くお勧めします。 メディア バイパス用にネットワーク サイトを構成するために、追加パラメーターを指定する必要はありません。

    
    </div>

3.  使用しているトポロジのネットワーク サイトの変更を完了するには、他のサイトの設定値を使用してステップ 2 を繰り返します。

</div>

<div>

## <a name="to-modify-a-network-site-by-using-lync-server-control-panel"></a>Lync Server コントロールパネルを使用してネットワークサイトを変更するには

1.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

2.  左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。

3.  [**サイト**] ナビゲーション ボタンをクリックします。

4.  表内で、変更するネットワーク サイトをクリックします。

5.  [**編集**] をクリックして、[**詳細の表示...**] をクリックします。

6.  [**サイトの編集**] ページで、このネットワーク サイトの設定値を必要に応じて変更します。

7.  [**確定**] をクリックします。

8.  ネットワーク サイトの変更を完了するには、他のサイトの設定値を使用してステップ 4 ～ 7 を繰り返します。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

