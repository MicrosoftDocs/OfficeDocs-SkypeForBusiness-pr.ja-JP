---
title: ネットワークの領域をリンクします。
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: '呼受付制御 (CAC) の一環として 2 つのネットワーク領域間のリンクを構成することができます。 '
ms.openlocfilehash: 4ea6ddcc72d2cadea32608288d1db93ba8505aee
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884685"
---
# <a name="linking-network-regions-in-skype-for-business-server"></a>Skype for Business Server でのネットワーク領域のリンクの設定

呼受付制御 (CAC) の一環として 2 つのネットワーク領域間のリンクを構成することができます。 Newtwork 領域のリンク情報を表示または構成するネットワーク地域リンクを削除するには、この資料のセクションを使用します。 

## <a name="view-network-region-link-information"></a>ネットワーク地域リンク情報の表示 

呼受付制御 (CAC) の一環として 2 つのネットワーク領域間のリンクを表示できます。 ネットワーク内の領域は、物理的なワイド エリア ネットワーク (WAN) 接続を介してリンクされます。 ビジネス サーバーのコントロール パネルの Skype を使用するには 2 つのネットワーク領域間の既存のリンクを表示するのには。 


### <a name="to-view-a-network-region-link-in-skype-for-business-server-control-panel"></a>Skype のビジネス サーバーのコントロール パネルの地域のネットワーク リンクを表示するのには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。 

3.  左側のナビゲーション ・ バーでは、**ネットワーク構成**をクリックし、**地域のリンク**をクリックします。

4.  [**地域リンク**] ページで、表示する領域のリンクをクリックします。
    
    > [!NOTE]  
    > のみ、一度に 1 つの領域のリンク情報を表示できます。

5.  **[編集**] メニュー**の詳細を表示**を選択します。

### <a name="view-network-region-link-information-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してネットワーク地域リンク情報の表示

Windows PowerShell と**Get CsNetworkRegionLink**コマンドレットを使用してネットワーク地域リンクを表示します。 ビジネス サーバー管理シェルの Skype とは Windows PowerShell のリモート セッションからは、このコマンドレットを実行することができます。 


### <a name="to-view-network-region-link-information"></a>ネットワーク地域リンク情報を表示するのには

  - すべてのネットワーク地域リンクに関する情報を表示するのには、Skype のビジネス サーバー管理シェルには、次のコマンドを入力し、し、ENTER キーを押します。
    
        Get-CsNetworkRegionLink
    
    このコマンドは、次のような情報を返します。
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California


詳細については、 [Get CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)を参照してください。


## <a name="configure-network-region-links"></a>ネットワーク地域リンクを構成します。 

呼受付制御 (CAC) の一環として 2 つのネットワーク領域間のリンクを構成することができます。 ネットワーク内の領域は、物理的なワイド エリア ネットワーク (WAN) 接続を介してリンクされます。 ビジネス サーバーのコントロール パネルの Skype を使用するには 2 つのネットワーク領域間のリンクを定義し、これらの領域間でのオーディオおよびビデオ接続の帯域幅の制限を設定します。

### <a name="to-create-a-network-region-link"></a>ネットワーク地域リンクを作成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。 

3.  左側のナビゲーション ・ バーでは、**ネットワーク構成**をクリックし、**地域のリンク**をクリックします。

4.  [**地域リンク**] ページで [**新規**を] をクリックします。

5.  **新しい地域リンク**] で **[名前**] フィールドに値を入力します。
 
    > [!NOTE]  
    > この値は、ビジネスのサーバーの展開に、Skype 内で一意である必要があります。

6.  **ネットワークの領域\#1** 」ドロップ ダウン リスト、リンクする 2 つの領域のいずれかを選択します。

7.  **ネットワークの領域\#2** 」ドロップ ダウン リストで、リンクするその他の地域を選択します。 この領域は、ネットワークの領域を選択した領域とは異なるである必要があります\#1 です。

8.  (省略可能)これらの領域の間のオーディオまたはビデオ通話に帯域幅の制限を配置する場合は、**帯域幅ポリシー**のドロップダウン リストから、帯域幅ポリシーのプロファイルを選択します。

9.  [**コミット**] をクリックします。

### <a name="to-modify-a-network-region-link"></a>ネットワーク地域リンクを変更するのには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。 

3.  左側のナビゲーション ・ バーでは、**ネットワーク構成**をクリックし、**地域のリンク**をクリックします。

4.  [**地域リンク**] ページで、変更する地域リンクをクリックします。

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。

6.  **地域リンクの編集**] で、リンクされている地域やこのリンクの帯域幅ポリシーのプロファイルを変更できます。

7.  [**コミット**] をクリックします。


## <a name="delete-network-region-links"></a>ネットワーク地域リンクを削除します。

呼受付制御 (CAC) の一環として 2 つのネットワーク領域間のリンクを構成することができます。 ネットワーク内の領域は、物理的なワイド エリア ネットワーク (WAN) 接続を介してリンクされます。 ビジネス サーバーのコントロール パネルの Skype を使用するには 2 つのネットワーク領域間の既存のリンクを削除します。 

### <a name="to-delete-a-network-region-link"></a>ネットワーク地域リンクを削除するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。 

3.  左側のナビゲーション ・ バーでは、**ネットワーク構成**をクリックし、**地域のリンク**をクリックします。

4.  [**地域リンク**] ページで、削除する地域リンクをクリックします。
 
    > [!NOTE]  
    > 一度に複数の地域のリンクを削除できます。 これを行うには、CTRL キーを押し、CTRL キーを押しながら複数の地域のリンクを選択します。 または、地域のすべてのリンクを選択するに<STRONG>[すべて選択</STRONG>] をクリックして<STRONG>[編集</STRONG>] メニューです。

5.  **[編集**] メニューから [**削除**] を選択します。

6.  [**OK**] をクリックします。


## <a name="see-also"></a>関連項目

[新しい-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  

[セット CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  

[削除 CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  

[Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
