---
title: ネットワーク地域のリンク
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: '通話受付管理 (CAC) の一環として、2 つのネットワーク地域間のリンクを公正できます。 '
ms.openlocfilehash: 0a4f5c63b4470fbfe6d2677f0e9e6f52841f7ebb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816467"
---
# <a name="linking-network-regions-in-skype-for-business-server"></a>Skype for Business Server でのネットワーク領域のリンクの設定

通話受付管理 (CAC) の一環として、2 つのネットワーク地域間のリンクを公正できます。 この記事のセクションを使用して、新しい作業領域リンク情報を表示したり、netwrok 地域リンクを構成または削除したりします。 

## <a name="view-network-region-link-information"></a>ネットワーク地域リンク情報の表示 

通話受付管理 (CAC) の一環として、2 つのネットワーク地域間のリンクを表示できます。 ネットワーク内の地域は、物理的なワイド エリア ネットワーク (WAN) 接続を経由してリンクされます。 Skype for Business Server コントロール パネルを使用して、2 つのネットワーク地域間の既存のリンクを表示できます。 


### <a name="to-view-a-network-region-link-in-skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネルでネットワーク地域リンクを表示するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。 

3.  左側のナビゲーション バーで、[ネットワーク構成] **をクリック** し、[地域リンク] **をクリックします**。

4.  [**地域リンク**] ページで、表示する地域リンクをクリックします。
    
    > [!NOTE]  
    > 一度に情報を表示できる地域リンクは 1 つだけです。

5.  [**編集**] メニューの [**詳細の表示**] を選択します。

### <a name="view-network-region-link-information-by-using-windows-powershell-cmdlets"></a>次のコマンドレットを使用してネットワーク地域Windows PowerShell表示する

ネットワーク地域リンクを表示するには、Windows PowerShell **Get-CsNetworkRegionLink コマンドレットを使用** します。 このコマンドレットは、Skype for Business Server 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。 


### <a name="to-view-network-region-link-information"></a>ネットワーク地域リンク情報を表示するには

  - すべてのネットワーク地域リンクに関する情報を表示するには、Skype for Business Server 管理シェルで次のコマンドを入力し、Enter キーを押します。
    
        Get-CsNetworkRegionLink
    
    このコマンドは、次のような情報を返します。
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California


詳細については、「[Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)」を参照してください。


## <a name="configure-network-region-links"></a>ネットワーク地域リンクを構成する 

通話受付管理 (CAC) の一環として、2 つのネットワーク地域間のリンクを公正できます。 ネットワーク内の地域は、物理的なワイド エリア ネットワーク (WAN) 接続を経由してリンクされます。 Skype for Business Server コントロール パネルを使用して、2 つのネットワーク地域間のリンクを定義し、これらの地域間の音声接続とビデオ接続の帯域幅制限を設定できます。

### <a name="to-create-a-network-region-link"></a>ネットワーク地域リンクを作成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。 

3.  左側のナビゲーション バーで、[ネットワーク構成] **をクリック** し、[地域リンク] **をクリックします**。

4.  [地域リンク **] ページで、[** 新規] を **クリックします**。

5.  [ **新しい地域リンク] で**、[名前] フィールドに値 **を入力** します。
 
    > [!NOTE]  
    > この値は、Skype for Business Server 展開内で一意である必要があります。

6.  [ **ネットワーク地域 \# 1]** ドロップダウン リストから、リンクする 2 つの地域のいずれかを選択します。

7.  [ **ネットワーク地域 \# 2]** ドロップダウン リストから、リンクする他の地域を選択します。 この地域は、ネットワーク地域 1 で選択した地域とは異なる \# 必要があります。

8.  (省略可能)これらの地域間の音声通話またはビデオ通話に帯域幅制限を設定する場合は、[帯域幅ポリシー] ドロップダウン リストから帯域幅ポリシー プロファイルを選択します。

9.  [**確定**] をクリックします。

### <a name="to-modify-a-network-region-link"></a>ネットワーク地域リンクを変更するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。 

3.  左側のナビゲーション バーで、[ネットワーク構成] **をクリック** し、[地域リンク] **をクリックします**。

4.  [地域 **リンク] ページ** で、変更する地域リンクをクリックします。

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。

6.  [ **地域リンクの** 編集] では、リンクされている地域またはこのリンクの帯域幅ポリシー プロファイルを変更できます。

7.  [**確定**] をクリックします。


## <a name="delete-network-region-links"></a>ネットワーク地域リンクを削除する

通話受付管理 (CAC) の一環として、2 つのネットワーク地域間のリンクを公正できます。 ネットワーク内の地域は、物理的なワイド エリア ネットワーク (WAN) 接続を経由してリンクされます。 Skype for Business Server コントロール パネルを使用して、2 つのネットワーク地域間の既存のリンクを削除できます。 

### <a name="to-delete-a-network-region-link"></a>ネットワーク地域リンクを削除するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。 

3.  左側のナビゲーション バーで、[ネットワーク構成] **をクリック** し、[地域リンク] **をクリックします**。

4.  [**地域リンク**] ページで、削除する地域リンクをクリックします。
 
    > [!NOTE]  
    > 1 つ以上の地域リンクを一度に削除できます。これを実行するには、Ctrl キーを押しながら、複数の地域リンクを選択します。また、すべての地域リンクを選択するには、[<STRONG>編集</STRONG>] メニューの [<STRONG>すべて選択</STRONG>] をクリックします。

5.  [**編集**] メニューの [**削除**] を選択します。

6.  [**OK**] をクリックします。


## <a name="see-also"></a>関連項目

[New-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  

[Set-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  

[Remove-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  

[Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
