---
title: ネットワーク地域ルートの管理
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: ネットワーク地域ルートでは、ネットワーク地域のペア間のルートを定義します。 通話受付管理展開のネットワーク地域の各ペアには、ネットワーク地域間ルートが必要です。
ms.openlocfilehash: a5808a7b3ffdfb860723bf0f84dc32239a9b08ae
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62395239"
---
# <a name="managing-network-region-routes-in-skype-for-business-server"></a>Skype for Business Server でのネットワーク領域ルートの管理

** ネットワーク地域ルートでは、ネットワーク地域のペア間のルートを定義します。 通話受付管理展開のネットワーク地域の各ペアには、ネットワーク地域間ルートが必要です。 これにより、展開内の各ネットワーク地域が他のすべての地域にアクセスできるようになります。 ネットワーク地域ルートを表示、作成、変更、または削除するには、この artilce の手順を使用します。

## <a name="view-network-region-route-information"></a>ネットワーク地域のルート情報を表示する 

通話受付管理 (CAC) 構成内のすべての地域には、他のすべての地域へのアクセス方法がいくつかある必要があります。 地域のリンクが地域間の接続に対する帯域幅制限を設定し、物理リンクも表す一方、ルートはある地域から別の地域へ接続が通過するリンクされたパスを決定します。 次の手順を使用して、コントロール パネルまたは管理シェルのSkype for Business Serverネットワーク地域ルートSkype for Business Server表示します。 

### <a name="to-view-network-region-route-information-in-skype-for-business-server-control-panel"></a>[コントロール パネル] でネットワーク地域のルートSkype for Business Server表示するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。 

3.  左側のナビゲーション バーで、[ネットワーク構成] **をクリックし**、[地域ルート] **をクリックします**。

4.  [**地域ルート**] ページで、変更する地域ルートをクリックします。


    > [!NOTE]
    > 一度に表示できる地域ルートは 1 つだけです。


5.  [**編集**] メニューの [**詳細の表示**] をクリックします。


### <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a>ネットワーク地域のルート情報を表示するには、Windows PowerShellコマンドレットを使用します。

ネットワーク地域のルート情報は、ネットワーク と Windows PowerShellコマンドレットをGet-CsNetworkInterRegionRouteできます。 このコマンドレットは、管理シェルから、またはSkype for Business Serverのリモート セッションから実行Windows PowerShell。 

### <a name="to-view-network-region-route-information"></a>ネットワーク地域のルート情報を表示するには

  - すべてのネットワーク地域ルートに関する情報を表示するには、次のコマンドを [管理シェル] Skype for Business Server入力し、Enter キーを押します。
    
    **Get-CsNetworkInterRegionRoute**
    
    次のような情報が表示されます。
    
    Identity : TransAmericaRoute<br/>
    NetworkRegionLinks : {NorthwestToNortheast}<br/>
    InterNetworkRegionRouteID : TransAmericaRoute<br/>
    NetworkRegionID1 : 太平洋北西部<br/>
    NetworkRegionID2 : ノースイースト<br/>

詳細については、[Get-CsNetworkInterRegionRoute](/powershell/module/skype/Get-CsNetworkInterRegionRoute) コマンドレットのヘルプ トピックを参照してください。


## <a name="create-or-modify-network-region-routes"></a>ネットワーク地域ルートの作成または変更

通話受付管理 (CAC) 構成内のすべての地域には、他のすべての地域へのアクセス方法がいくつかある必要があります。 地域のリンクが地域間の接続に対する帯域幅制限を設定し、物理リンクも表す一方、ルートはある地域から別の地域へ接続が通過するリンクされたパスを決定します。 [コントロール パネル] Skype for Business Serverを使用して、ネットワーク地域ルートを構成できます。 [コントロール Skype for Business Serverから、ネットワーク地域ルートを作成、変更、または削除できます。 このトピックでは、ネットワーク地域ルートの作成または変更について説明します。 

### <a name="to-create-a-network-region-route"></a>ネットワーク地域ルートを作成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。 

3.  左側のナビゲーション バーで、[ネットワーク構成] **をクリックし**、[地域ルート] **をクリックします**。

4.  [**地域ルート**] ページで、[**新規**] をクリックします。

5.  [**新しい地域ルート**] で、[**名前**] フィールドに値を入力します。
   
    > [!NOTE]  
    > この値は、展開内で一意Skype for Business Server必要があります。

6.  [ネットワーク **領域 \#1]** ドロップダウン リストから、このルートで接続する 2 つの領域のいずれかを選択します。

7.  [ネットワーク **領域 2] \#** ドロップダウン リストから、このルートの他の領域を選択します。 この領域は、ネットワーク領域 1 で選択した地域とは異なる必要 \#があります。

8.  [**ネットワーク地域リンク**] リスト ボックスを使用して、地域リンクをルートに追加します。 [**追加**] ボタンをクリックし、[**地域リンク**] ページを表示します。 このルートに追加する地域リンクをクリックして、[**OK**] をクリックします。
    
    > [!NOTE]  
    > [**追加**] ボタンのクリックを続けて、さらにリンクを追加できます。また、リンクを選択して [**削除**] をクリックすると、リンクを削除できます。

9.  [**確定**] をクリックします。


### <a name="to-modify-a-network-region-route"></a>ネットワーク地域ルートを変更するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。 

3.  左側のナビゲーション バーで、[ネットワーク構成] **をクリックし**、[地域ルート] **をクリックします**。

4.  [**地域ルート**] ページで、変更する地域ルートをクリックします。

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。

6.  [**地域ルートの編集**] で、このルートが接続する地域やこのルートに関連付ける地域リンクを変更できます。

7.  [**確定**] をクリックします。


## <a name="delete-existing-network-region-routes"></a>既存のネットワーク地域ルートの削除

通話受付管理 (CAC) 構成内のすべての地域には、他のすべての地域へのアクセス方法がいくつかある必要があります。 地域のリンクが地域間の接続に対する帯域幅制限を設定し、物理リンクも表す一方、ルートはある地域から別の地域へ接続が通過するリンクされたパスを決定します。 [コントロール パネル] Skype for Business Serverを使用して、ネットワーク地域ルートを構成できます。 [コントロール Skype for Business Serverから、ネットワーク地域ルートを作成、変更、または削除できます。 このトピックを使用して、既存のネットワーク地域ルートを削除できます。 

### <a name="to-delete-a-network-region-route"></a>ネットワーク地域ルートを削除するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。 

3.  左側のナビゲーション バーで、[ネットワーク構成] **をクリックし**、[地域ルート] **をクリックします**。

4.  [**地域ルート**] ページで、削除する地域ルートをクリックします。

    > [!NOTE]  
    > 1 つ以上の地域ルートを一度に削除できます。これを実行するには、Ctrl キーを押しながら、複数のルートを選択します。また、すべての地域ルートを選択するには、[**編集**] メニューの [**すべて選択**] をクリックします。

5.  [**編集**] メニューの [**削除**] をクリックします。

6.  [**OK**] をクリックします。



## <a name="see-also"></a>関連項目

[Skype for Business Server でのネットワーク領域の管理](managing-network-regions.md)

[New-CsNetworkInterRegionRoute](/powershell/module/skype/New-CsNetworkInterRegionRoute)  

[Set-CsNetworkInterRegionRoute](/powershell/module/skype/Set-CsNetworkInterRegionRoute) 
 
[Remove-CsNetworkInterRegionRoute](/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  

[Get-CsNetworkInterRegionRoute](/powershell/module/skype/Get-CsNetworkInterRegionRoute)