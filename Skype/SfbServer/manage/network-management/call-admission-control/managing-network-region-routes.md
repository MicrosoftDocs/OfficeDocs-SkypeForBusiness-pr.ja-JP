---
title: ネットワーク領域ルートの管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ネットワーク領域ルートは、ネットワーク領域のペア間のルートを定義します。 通話受付制御の展開におけるネットワーク領域の各ペアには、ネットワーク領域ルートが必要です。
ms.openlocfilehash: 174fdd021655f3e338001582a1409107b266582e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279509"
---
# <a name="managing-network-region-routes-in-skype-for-business-server"></a>Skype for Business Server でのネットワーク領域ルートの管理

*ネットワーク領域ルート*は、ネットワーク領域のペア間のルートを定義します。 通話受付制御の展開におけるネットワーク領域の各ペアには、ネットワーク領域ルートが必要です。 これにより、展開内の各ネットワーク地域が他のすべての地域にアクセスできるようになります。 ネットワーク領域ルートを表示、作成、変更、または削除するには、この artilce の手順を使用します。

## <a name="view-network-region-route-information"></a>ネットワーク領域ルート情報を表示する 

通話受付制御 (CAC) 構成内のすべての領域は、他のすべての領域にアクセスするための何らかの手段を持っている必要があります。 地域のリンクでは、地域間の接続について帯域幅の制限を設定していますが、物理的なリンクも示しています。ルートによって、ある領域から別の領域に接続するリンク先のパスが決定されます。 次の手順を使用して、Skype for Business Server コントロールパネルまたは Skype for Business Server Management Shell で既存のネットワーク領域ルートを表示します。 

### <a name="to-view-network-region-route-information-in-skype-for-business-server-control-panel"></a>Skype for Business Server コントロールパネルのネットワーク領域ルート情報を表示するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 

3.  左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**地域ルート**] をクリックします。

4.  [**地域ルート**] ページで、表示する地域ルートをクリックします。


    > [!NOTE]  
    > 表示できる地域ルートは一度に1つだけです。


5.  [**編集**] メニューの [**詳細の表示**] をクリックします。


### <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用したネットワーク領域ルート情報の表示

ネットワーク領域のルート情報を表示するには、Windows PowerShell を使用するか、または CsNetworkInterRegionRoute コマンドレットを使用します。 このコマンドレットは、Skype for Business Server 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 

### <a name="to-view-network-region-route-information"></a>ネットワーク領域ルート情報を表示するには

  - すべてのネットワーク領域ルートに関する情報を表示するには、Skype for Business Server 管理シェルで次のコマンドを入力して、enter キーを押します。
    
        Get-CsNetworkInterRegionRoute
    
    次のような情報が表示されます。
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

詳細については、「 [CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)コマンドレット」のヘルプトピックを参照してください。


## <a name="create-or-modify-network-region-routes"></a>ネットワーク領域ルートを作成または変更する

通話受付制御 (CAC) 構成内のすべての領域は、他のすべての領域にアクセスするための何らかの手段を持っている必要があります。 地域のリンクでは、地域間の接続について帯域幅の制限を設定していますが、物理的なリンクも示しています。ルートによって、ある領域から別の領域に接続するリンク先のパスが決定されます。 Skype for Business Server コントロールパネルを使用して、ネットワーク領域ルートを構成することができます。 Skype for Business Server コントロールパネルでは、ネットワーク領域ルートの作成、変更、または削除を行うことができます。 ネットワーク領域ルートを作成または変更するには、このトピックを使用します。 

### <a name="to-create-a-network-region-route"></a>ネットワーク領域ルートを作成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 

3.  左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**地域ルート**] をクリックします。

4.  [**地域ルート**] ページで、[**新規**] をクリックします。

5.  [**新しい地域ルート**] で、[**名前**] フィールドに値を入力します。
   
    > [!NOTE]  
    > この値は、Skype for Business Server の展開内で一意である必要があります。

6.  [ **Network region \#1** ] ドロップダウンリストから、このルートによって接続される2つの領域のいずれかを選択します。

7.  [ **Network region \#2** ] ドロップダウンリストから、このルートの他の地域を選択します。 この領域は、ネットワーク領域\#1 で選択した地域とは異なる必要があります。

8.  [**ネットワークの領域のリンク**] リストボックスを使って、そのルートに地域のリンクを追加します。 [**追加**] ボタンをクリックして、[**地域] リンク**ページを表示します。 このルートに追加する地域のリンクをクリックして、[ **OK]** をクリックします。
    
    > [!NOTE]  
    > [**追加**] ボタンをクリックして、さらにリンクを追加するか、リンクを選択して [**削除**] をクリックし、リンクを削除します。

9.  [**コミット**] をクリックします。


### <a name="to-modify-a-network-region-route"></a>ネットワークの領域ルートを変更するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 

3.  左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**地域ルート**] をクリックします。

4.  [**地域ルート**] ページで、変更する地域ルートをクリックします。

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。

6.  [**範囲ルートの編集**] で、このルートによって参加している地域と、ルートに関連付けられている地域リンクを変更することができます。

7.  [**コミット**] をクリックします。


## <a name="delete-existing-network-region-routes"></a>既存のネットワーク領域ルートを削除する

通話受付制御 (CAC) 構成内のすべての領域は、他のすべての領域にアクセスするための何らかの手段を持っている必要があります。 地域のリンクでは、地域間の接続について帯域幅の制限を設定していますが、物理的なリンクも示しています。ルートによって、ある領域から別の領域に接続するリンク先のパスが決定されます。 Skype for Business Server コントロールパネルを使用して、ネットワーク領域ルートを構成することができます。 Skype for Business Server コントロールパネルでは、ネットワーク領域ルートの作成、変更、または削除を行うことができます。 このトピックを使用して、既存のネットワーク領域ルートを削除します。 

### <a name="to-delete-a-network-region-route"></a>ネットワーク領域ルートを削除するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 

3.  左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**地域ルート**] をクリックします。

4.  [**地域ルート**] ページで、削除する地域ルートをクリックします。

    > [!NOTE]  
    > 複数の地域のルートを一度に削除できます。 これを行うには、ctrl キーを押しながら、CTRL キーを押しながら複数の領域ルートを選択します。 または、すべての地域ルートを選択するには、[**編集**] メニューの [**すべて選択**] をクリックします。

5.  [**編集**] メニューの [**削除**] をクリックします。

6.  **[OK]** をクリックします。



## <a name="see-also"></a>関連項目

[Skype for Business Server でのネットワーク領域の管理](managing-network-regions.md)

[新しい (CsNetworkInterRegionRoute)](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  

[設定-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute) 
 
[CsNetworkInterRegionRoute の削除](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  

[Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
