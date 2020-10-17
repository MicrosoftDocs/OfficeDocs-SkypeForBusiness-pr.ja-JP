---
title: 'Lync Server 2013: 通話受付管理の有効化'
description: 'Lync Server 2013: 通話受付管理を有効にします。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable call admission control
ms:assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398642(v=OCS.15)
ms:contentKeyID: 48184650
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31bd352d407c3b14ac90a76fd6d53ccb312cab7d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551583"
---
# <a name="enable-call-admission-control-in-lync-server-2013"></a>Lync Server 2013 で通話受付管理を有効にする

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-19_

通話受付管理展開のネットワーク設定を構成したら、帯域幅ポリシーを反映させるために CAC を有効にする必要があります。

詳細については、以下のコマンドレットの Lync Server 管理シェルのドキュメントを参照してください。

  - [Get-csnetworkconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)

  - [Get-csnetworkconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)

  - [Get-csnetworkconfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)

<div>

## <a name="to-enable-call-admission-control-by-using-management-shell"></a>管理シェルを使用して通話受付管理を有効にするには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  Set-CsNetworkConfiguration コマンドレットを実行して、ネットワークの CAC を有効にします。たとえば、以下を実行します。
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
    
    ネットワークの CAC を無効にする場合は、次のように実行します。
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0

</div>

<div>

## <a name="to-enable-call-admission-control-by-using-lync-server-control-panel"></a>Lync Server コントロール パネルを使用して通話受付管理を有効にするには

1.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

2.  左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。

3.  [**グローバル**] ナビゲーション ボタンをクリックします。

4.  一覧で [**グローバル**] をクリックし、[**編集**] メニューの [**詳細の表示**] をクリックします。

5.  [**グローバル設定の編集**] ページの [**通話受付管理の有効化**] チェック ボックスをオンにします。
    
    <div>
    

    > [!NOTE]  
    > 展開全体で通話受付管理を無効にする場合は、このチェック ボックスをオフにします。

    
    </div>

6.  [**確定**] をクリックします。

</div>

</div>

<span> </span>

</div>

</div>

</div>

