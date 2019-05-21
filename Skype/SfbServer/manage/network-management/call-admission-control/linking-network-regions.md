---
title: ネットワーク領域のリンク
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: '通話受付制御 (CAC) の一部として、2つのネットワーク領域間のリンクを構成することができます。 '
ms.openlocfilehash: b9ffa45c8a0a09ba4a7f9f0ebf6402b87116f01f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279558"
---
# <a name="linking-network-regions-in-skype-for-business-server"></a>Skype for Business Server でのネットワーク領域のリンクの設定

通話受付制御 (CAC) の一部として、2つのネットワーク領域間のリンクを構成することができます。 この記事のセクションを使用して、newtwork region リンク情報を表示したり、netwrok region リンクを構成または削除したりします。 

## <a name="view-network-region-link-information"></a>ネットワーク領域のリンク情報を表示する 

通話受付制御 (CAC) の一部として、2つのネットワーク領域間のリンクを表示することができます。 ネットワーク内の領域は、物理ワイドエリアネットワーク (WAN) 接続によってリンクされています。 Skype for Business Server コントロールパネルを使用して、2つのネットワーク領域間の既存のリンクを表示することができます。 


### <a name="to-view-a-network-region-link-in-skype-for-business-server-control-panel"></a>Skype for Business Server コントロールパネルでネットワーク領域のリンクを表示するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 

3.  左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**地域] リンク**をクリックします。

4.  [**地域] リンク**ページで、表示する地域のリンクをクリックします。
    
    > [!NOTE]  
    > 一度に表示できるのは、1つの地域のリンクに関する情報だけです。

5.  [**編集**] メニューの [**詳細の表示**] を選択します。

### <a name="view-network-region-link-information-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してネットワーク領域のリンク情報を表示する

ネットワークの領域のリンクを表示するには、Windows PowerShell を使用するか、または**CsNetworkRegionLink**コマンドレットを使用します。 このコマンドレットは、Skype for Business Server 管理シェルまたは Windows PowerShell のリモートセッションから実行できます。 


### <a name="to-view-network-region-link-information"></a>ネットワーク領域のリンク情報を表示するには

  - すべてのネットワーク領域のリンクに関する情報を表示するには、Skype for Business Server 管理シェルで次のコマンドを入力し、enter キーを押します。
    
        Get-CsNetworkRegionLink
    
    このコマンドは、次のような情報を返します。
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California


詳細については、「 [CsNetworkRegionLink の入手](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)」を参照してください。


## <a name="configure-network-region-links"></a>ネットワーク領域のリンクを構成する 

通話受付制御 (CAC) の一部として、2つのネットワーク領域間のリンクを構成することができます。 ネットワーク内の領域は、物理ワイドエリアネットワーク (WAN) 接続によってリンクされています。 Skype for Business Server コントロールパネルを使用して、2つのネットワーク領域間のリンクを定義し、これらの地域間の音声およびビデオ接続の帯域幅の制限を設定することができます。

### <a name="to-create-a-network-region-link"></a>ネットワーク領域のリンクを作成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 

3.  左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**地域] リンク**をクリックします。

4.  [**地域] リンク**ページで、[**新規**] をクリックします。

5.  [**新しい地域] リンク**で、[**名前**] フィールドに値を入力します。
 
    > [!NOTE]  
    > この値は、Skype for Business Server の展開内で一意である必要があります。

6.  [ **Network region \#1** ] ボックスの一覧で、リンクする2つの領域のいずれかを選択します。

7.  [ **Network region \#2** ] ボックスの一覧で、リンクする他の地域を選択します。 この領域は、ネットワーク領域\#1 で選択した地域とは異なる必要があります。

8.  省略これらの地域間の音声通話やビデオ通話に帯域幅の制限を設定する場合は、[**帯域幅ポリシー** ] ドロップダウンリストから帯域幅ポリシーのプロファイルを選択します。

9.  [**コミット**] をクリックします。

### <a name="to-modify-a-network-region-link"></a>ネットワーク領域のリンクを変更するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 

3.  左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**地域] リンク**をクリックします。

4.  [**地域] リンク**ページで、変更する地域のリンクをクリックします。

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。

6.  [**範囲の編集] リンク**では、リンクされている地域、またはこのリンクの帯域幅ポリシープロファイルを変更することができます。

7.  [**コミット**] をクリックします。


## <a name="delete-network-region-links"></a>ネットワーク領域のリンクを削除する

通話受付制御 (CAC) の一部として、2つのネットワーク領域間のリンクを構成することができます。 ネットワーク内の領域は、物理ワイドエリアネットワーク (WAN) 接続によってリンクされています。 Skype for Business Server コントロールパネルを使用して、2つのネットワーク領域間の既存のリンクを削除することができます。 

### <a name="to-delete-a-network-region-link"></a>ネットワーク領域のリンクを削除するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 

3.  左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**地域] リンク**をクリックします。

4.  [**領域のリンク**] ページで、削除する地域のリンクをクリックします。
 
    > [!NOTE]  
    > 一度に複数の領域のリンクを削除することができます。 これを行うには、ctrl キーを押しながら、CTRL キーを押しながら複数の領域のリンクを選択します。 または、すべての地域リンクを選択するには、[<STRONG>編集</STRONG>] メニューの [<STRONG>すべて選択</STRONG>] をクリックします。

5.  [**編集**] メニューの [**削除**] を選択します。

6.  **[OK]** をクリックします。


## <a name="see-also"></a>関連項目

[新しい-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  

[Set-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  

[CsNetworkRegionLink を削除する](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  

[Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
