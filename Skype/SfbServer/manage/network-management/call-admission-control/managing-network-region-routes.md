---
title: ネットワーク地域ルートの管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ネットワーク地域のルートは、ネットワーク地域のペア間のルートを定義します。 通話受付管理展開のネットワーク地域の各ペアには、ネットワーク地域のルートが必要です。
ms.openlocfilehash: 53b6383e08196fb22784f3fcd1e8d797c9b138de
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33888850"
---
# <a name="managing-network-region-routes-in-skype-for-business-server"></a>Skype for Business Server でのネットワーク領域ルートの管理

*地域のネットワーク ルート*は、ネットワーク地域のペア間のルートを定義します。 通話受付管理展開のネットワーク地域の各ペアには、ネットワーク地域のルートが必要です。 これにより、展開内の各ネットワーク地域が他のすべての地域にアクセスできるようになります。 この artilce の表示、作成、変更、またはネットワーク地域ルートを削除する手順を使用します。

## <a name="view-network-region-route-information"></a>ネットワーク地域のルート情報を表示します。 

コール受付制御 (CAC) 構成内のすべての領域には、何らかの方法の他のすべての領域にアクセスする必要があります。 地域リンクでは、領域間の接続の帯域幅の制限を設定して、物理的なリンクを表すも、中に、ルートは、どのリンク先のパスの接続は別に 1 つの領域から走査されますを決定します。 ビジネス サーバー管理シェルのビジネス サーバーのコントロール パネルまたは Skype の Skype で既存のネットワーク地域のルートを表示するのにには、次の手順を使用します。 

### <a name="to-view-network-region-route-information-in-skype-for-business-server-control-panel"></a>Skype のビジネス サーバーのコントロール パネルのネットワーク地域のルート情報を表示するのには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。 

3.  左側のナビゲーション ・ バーでは、**ネットワーク構成**をクリックし、**地域ルート**] をクリックします。

4.  [**地域ルート**] ページで、表示する地域ルートをクリックします。


    > [!NOTE]  
    > のみ一度に 1 つの領域のルートを表示できます。


5.  [**編集**] メニューの [**詳細の表示**] をクリックします。


### <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してネットワーク地域のルート情報の表示

Windows PowerShell と Get CsNetworkInterRegionRoute コマンドレットを使用してネットワーク地域のルート情報を表示できます。 ビジネス サーバー管理シェルの Skype とは Windows PowerShell のリモート セッションからは、このコマンドレットを実行できます。 

### <a name="to-view-network-region-route-information"></a>ネットワーク地域のルート情報を表示するのには

  - すべてのネットワーク地域ルートに関する情報を表示するのには、Skype のビジネス サーバー管理シェルには、次のコマンドを入力し、ENTER キーを押します。
    
        Get-CsNetworkInterRegionRoute
    
    次のような情報が表示されます。
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

詳細については、 [Get CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)コマンドレットのヘルプ トピックを参照してください。


## <a name="create-or-modify-network-region-routes"></a>作成またはネットワーク地域のルートを変更します。

コール受付制御 (CAC) 構成内のすべての領域には、何らかの方法の他のすべての領域にアクセスする必要があります。 地域リンクでは、領域間の接続の帯域幅の制限を設定して、物理的なリンクを表すも、中に、ルートは、どのリンク先のパスの接続は別に 1 つの領域から走査されますを決定します。 ビジネス サーバーのコントロール パネルの Skype を使用すると、ネットワーク地域のルートを構成します。 ビジネス サーバーのコントロール パネルの Skype からを作成、変更、またはネットワーク地域ルートを削除することができます。 作成するか、ネットワーク地域のルートを変更するには、このトピックを使用します。 

### <a name="to-create-a-network-region-route"></a>ネットワーク地域ルートを作成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。 

3.  左側のナビゲーション ・ バーでは、**ネットワーク構成**をクリックし、**地域ルート**] をクリックします。

4.  [**地域ルート**] ページで [**新規**を] をクリックします。

5.  **新しい領域のルート**の**名前**] フィールドの値を入力します。
   
    > [!NOTE]  
    > この値は、ビジネスのサーバーの展開に、Skype 内で一意である必要があります。

6.  **ネットワークの領域\#1** 」ドロップ ダウン リスト、このルートによって接続される 2 つの領域のいずれかを選択します。

7.  **ネットワークの領域\#2** 」ドロップ ダウン リストで、このルートの他の地域を選択します。 この領域は、ネットワークの領域を選択した領域とは異なるである必要があります\#1 です。

8.  地域リンクをルートに追加するのにには、**ネットワーク地域リンク**] リスト ボックスを使用します。 **地域リンク**] ページを表示するのには [**追加**] ボタンをクリックします。 このルートに追加する地域リンクをクリックし、し、[ **OK**] をクリックします。
    
    > [!NOTE]  
    > 個のリンクを追加またはリンクを選択し、リンクを削除する**削除**を] をクリックして [**追加**] ボタンをクリックし続けます。

9.  [**コミット**] をクリックします。


### <a name="to-modify-a-network-region-route"></a>ネットワーク地域ルートを変更するのには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。 

3.  左側のナビゲーション ・ バーでは、**ネットワーク構成**をクリックし、**地域ルート**] をクリックします。

4.  [**地域ルート**] ページで、変更する地域ルートをクリックします。

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。

6.  **編集領域のルート**のこのルートによって結合された領域と、ルートに関連付けられている領域のリンクを変更できます。

7.  [**コミット**] をクリックします。


## <a name="delete-existing-network-region-routes"></a>既存のネットワーク地域のルートを削除します。

コール受付制御 (CAC) 構成内のすべての領域には、何らかの方法の他のすべての領域にアクセスする必要があります。 地域リンクでは、領域間の接続の帯域幅の制限を設定して、物理的なリンクを表すも、中に、ルートは、どのリンク先のパスの接続は別に 1 つの領域から走査されますを決定します。 ビジネス サーバーのコントロール パネルの Skype を使用すると、ネットワーク地域のルートを構成します。 ビジネス サーバーのコントロール パネルの Skype からを作成、変更、またはネットワーク地域ルートを削除することができます。 既存のネットワーク地域のルートを削除するのにには、このトピックを使用します。 

### <a name="to-delete-a-network-region-route"></a>ネットワーク地域ルートを削除するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。 

3.  左側のナビゲーション ・ バーでは、**ネットワーク構成**をクリックし、**地域ルート**] をクリックします。

4.  [**地域ルート**] ページで、削除する地域ルートをクリックします。

    > [!NOTE]  
    > 同時に 2 つ以上の地域ルートを削除できます。 これを行うには、CTRL キーを押し、CTRL キーを押しながら複数の地域のルートを選択します。 または、地域のすべてのルートを選択するに **[すべて選択**] をクリックして **[編集**] メニューです。

5.  [**編集**] メニューの [**削除**] をクリックします。

6.  **[OK]** をクリックします。



## <a name="see-also"></a>関連項目

[Skype for Business Server でのネットワーク領域の管理](managing-network-regions.md)

[新しい-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  

[セット CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute) 
 
[削除 CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  

[Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
