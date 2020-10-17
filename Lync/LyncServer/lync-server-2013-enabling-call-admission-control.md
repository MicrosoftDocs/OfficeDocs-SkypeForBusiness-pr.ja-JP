---
title: 'Lync Server 2013: 通話受付管理の有効化'
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
ms.openlocfilehash: dfe6ae76fd1f6b89178d101337f24ba0089dd35b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500984"
---
# <a name="enabling-call-admission-control-in-lync-server-2013"></a>Lync Server 2013 での通話受付管理の有効化

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

通話受付管理 (CAC) は、使用可能な帯域幅に基づいてオーディオおよびビデオ伝送に制限を課すことができる地域、サイト、およびサブネットで構成されるネットワークです。 CAC ネットワークの構成後、CAC を有効にして、帯域幅制限を強制的に適用する必要があります。 これを行うには、Lync Server コントロールパネルを使用します。

<div>

## <a name="to-enable-cac-from-lync-server-control-panel"></a>Lync Server コントロールパネルから CAC を有効にするには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**ネットワーク構成**] をクリックし、[**グローバル**] をクリックします。

4.  [**グローバル**] ページで [**グローバル**] 構成をクリックします。
    
    <div>
    

    > [!NOTE]  
    > Microsoft Lync Server 2013 の展開に対して構成できるネットワークは1つだけなので、リストに複数のネットワーク構成が存在することはありません。 グローバル構成の名前は変更できません。

    
    </div>

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。

6.  [**グローバル設定の編集**] ページの [**通話受付管理の有効化**] チェック ボックスをオンにして、[**確定**] をクリックします。

[**確定**] をクリックすると、構成のテストが実行されます。 [**グローバル設定の編集**] ダイアログ ボックスが閉じ、再び、[**グローバル**] ページが表示されます。 ネットワーク構成で、ネットワークの正しい動作を妨げるエラーまたは不整合 (たとえば、すべての地域が他のすべての地域に地域間ルート経由でそれぞれ接続される必要があるがそうなっていない場合) が検出されると、警告が表示されます。

ネットワーク構成に変更を加えた場合は、グローバル構成を開き [**確定**] をクリックすることで、検証チェックを再度実行できます。 最初に、CAC を無効にする必要はありません。 チェック ボックスをオンのままにして、[**確定**] をクリックしてください。 これは、構成に変更を加えていない場合も含め、いつでも実行できます。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での通話受付管理の概要](lync-server-2013-overview-of-call-admission-control.md)  


[Lync Server 2013 での通話受付管理の計画](lync-server-2013-planning-for-call-admission-control.md)  
[Lync Server 2013 で通話受付管理を構成する](lync-server-2013-configure-call-admission-control.md)  
[Get-csnetworkconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  
[Get-csnetworkconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  
[Get-csnetworkconfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

