---
title: 'Lync Server 2013: 通話受付制御を有効にする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling call admission control
ms:assetid: 015f5c8f-2f90-4b9e-8149-b33767e90582
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520942(v=OCS.15)
ms:contentKeyID: 48183228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b89c9b888dc610d60b2abbcefd4c9c67e9b0572e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735837"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-call-admission-control-in-lync-server-2013"></a>Lync Server 2013 での通話受付制御の有効化

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

通話受付管理 (CAC) は、地域、サイト、およびサブネットで構成されるネットワークで、使用可能な帯域幅に基づいてオーディオおよびビデオ伝送に制限を課すことができます。 CAC ネットワークを構成したら、CAC を有効にして帯域幅の制限を適用する必要があります。 Lync Server コントロールパネルを使うと、この操作を行うことができます。

<div>

## <a name="to-enable-cac-from-lync-server-control-panel"></a>Lync Server コントロールパネルで CAC を有効にするには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**グローバル**] をクリックします。

4.  [**グローバル**] ページで、[**グローバル**構成] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > Microsoft Lync Server 2013 の展開用に1つのネットワークのみを構成できます。そのため、リストには複数のネットワーク構成を設定することはできません。 グローバル構成の名前を変更することはできません。

    
    </div>

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。

6.  [**グローバル設定の編集**] ページで、[**通話受付制御を有効にする**] チェックボックスをオンにし、[**コミット**] をクリックします。

[**コミット**] をクリックすると、構成のテストが実行されます。 [**グローバル設定の編集**] ダイアログボックスが閉じ、**グローバル**ページに戻ります。 ネットワーク構成でエラーや不整合が検出された場合、そのエラーや不整合が正常に動作しなくなる場合 (たとえば、すべての地域が相互に接続されているルートを介してすべての地域に接続されていない場合) は、警告が表示されます。

ネットワーク構成を変更した場合は、[グローバル構成] を開き、[**コミット**] をクリックして、検証チェックをもう一度実行できます。 まず、CAC を無効にする必要はありません。チェックボックスをオンのままにして、[**コミット**] をクリックします。 この操作は、構成を変更することなくいつでも行うことができます。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 の通話受付制御の概要](lync-server-2013-overview-of-call-admission-control.md)  


[Lync Server 2013 での通話受付管理の計画](lync-server-2013-planning-for-call-admission-control.md)  
[Lync Server 2013 での通話受付制御の構成](lync-server-2013-configure-call-admission-control.md)  
[Get-Set-csnetworkconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  
[Set-Set-csnetworkconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  
[Remove-Set-csnetworkconfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

