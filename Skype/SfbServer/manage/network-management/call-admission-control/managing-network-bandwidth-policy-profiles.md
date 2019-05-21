---
title: ネットワーク帯域幅ポリシープロファイルの管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ネットワーク帯域幅ポリシープロファイルを表示、作成、変更、または削除するには、この記事の手順を使用します。
ms.openlocfilehash: 3b2b62e5e823a9d86f1884d79b67483bce38a39f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279523"
---
# <a name="managing-network-bandwidth-policy-profiles-in-skype-for-business-server"></a>Skype for Business Server でのネットワーク帯域幅ポリシー プロファイルの管理

ネットワーク帯域幅ポリシープロファイルを表示、作成、変更、または削除するには、この記事の手順を使用します。

## <a name="view-network-bandwidth-policy-profile-information"></a>ネットワーク帯域幅ポリシーのプロファイル情報を表示する

通話受付制御 (CAC) の一部として、帯域幅ポリシーを使って、特定のモダリティの帯域幅の制限を定義します。 Skype for Business Server では、オーディオとビデオのモダリティのみに帯域幅の制限を割り当てることができます。 全体的な帯域幅の制限とセッションの制限を設定できます。 Skype for Business Server コントロールパネルを使って、これらのポリシーのコンテナープロファイルを作成、変更、または削除することができます。 各帯域幅ポリシーのプロファイルは、1つ以上のネットワークサイトに関連付けることができます。 帯域幅ポリシーのプロファイルを表示するには、次の手順を使用します。 

### <a name="to-view-a-bandwidth-policy-profile"></a>帯域幅ポリシーのプロファイルを表示するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 

3.  左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**帯域幅ポリシー**] をクリックします。

4.  [**帯域幅ポリシー** ] ページで、表示する帯域幅ポリシープロファイルをクリックします。

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。


### <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してネットワーク帯域幅ポリシーのプロファイル情報を表示する

ネットワーク帯域幅プロファイルを表示するには、Windows PowerShell と CsNetworkBandwidthPolicyProfile コマンドレットを使用します。 このコマンドレットは、Skype for Business Server 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 


### <a name="to-view-network-bandwidth-policy-profile-information"></a>ネットワーク帯域幅ポリシーのプロファイル情報を表示するには

  - すべてのネットワーク帯域幅ポリシープロファイルに関する情報を表示するには、Skype for Business Server 管理シェルで次のコマンドを入力して、enter キーを押します。
    
        Get-CsNetworkBandwidthPolicyProfile
    
    次のような情報が表示されます。
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :


詳細については、 [CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)コマンドレットのヘルプトピックを参照してください。


## <a name="create-or-modify-bandwidth-policy-profiles"></a>帯域幅ポリシープロファイルを作成または変更する

通話受付制御 (CAC) の一部として、帯域幅ポリシーを使って、特定のモダリティの帯域幅の制限を定義します。 Skype for Business Server では、オーディオとビデオのモダリティのみに帯域幅の制限を割り当てることができます。 全体的な帯域幅の制限とセッションの制限を設定できます。 Skype for Business Server コントロールパネルを使って、これらのポリシーのコンテナープロファイルを作成、変更、または削除することができます。 各帯域幅ポリシーのプロファイルは、1つ以上のネットワークサイトに関連付けることができます。 帯域幅ポリシープロファイルを作成または変更するには、次の手順を使用します。 

### <a name="to-create-a-new-bandwidth-policy-profile"></a>新しい帯域幅ポリシープロファイルを作成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 

3.  左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**帯域幅ポリシー**] をクリックします。

4.  [**帯域幅ポリシー** ] ページで、[**新規**] をクリックします。

5.  **新しい帯域幅ポリシープロファイル**で、[**名前**] フィールドに名前を入力します。 この名前は、すべての帯域幅ポリシープロファイルの間で一意である必要があります。

6.  [**オーディオ制限**] フィールドに数値を入力します。 この値は、すべてのオーディオ接続に割り当てることができる最大帯域幅です。 kbps で表されます。

7.  [**オーディオセッションの制限**] フィールドに数値を入力します。 この値は、個々の音声接続に割り当てられる帯域幅の上限です。 kbps で表されます。 この値は40以上である必要があります。

8.  [**ビデオの制限**] フィールドに数値を入力します。 この値は、すべてのビデオ接続に割り当てることができる最大帯域幅です。 kbps で表されます。

9.  [**ビデオセッションの制限**] フィールドに数値を入力します。 この値は、個々のビデオ接続に割り当てることができる最大帯域幅です。 kbps で表されます。 この値は100以上である必要があります。

10. 省略[**説明**] フィールドに値を入力して、この帯域幅ポリシープロファイルの詳細情報を指定します。

11. [**コミット**] をクリックします。

    > [!NOTE]  
    > 新しい帯域幅ポリシープロファイルを作成しても、帯域幅の制限は自動的に適用されません。 最初にポリシープロファイルをサイトに関連付ける必要があります。 


### <a name="to-modify-a-bandwidth-policy-profile"></a>帯域幅ポリシーのプロファイルを変更するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 

3.  左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**帯域幅ポリシー**] をクリックします。

4.  [**帯域幅ポリシー** ] ページで、変更する帯域幅ポリシープロファイルをクリックします。

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。

6.  [**帯域幅ポリシープロファイルの編集**] ページで、必要に応じてフィールドを変更します (詳細については、「[新しい帯域幅ポリシープロファイルを作成する」を](#to-create-a-new-bandwidth-policy-profile)参照してください)。

7.  [**コミット**] をクリックします。

    > [!NOTE]  
    > 帯域幅ポリシーのプロファイルを変更すると、この帯域幅ポリシープロファイルに関連付けられたすべてのネットワークサイトの帯域幅の制限がすぐに更新されます。

  
## <a name="delete-network-bandwidth-policy-profiles"></a>ネットワーク帯域幅ポリシープロファイルを削除する

通話受付制御 (CAC) の一部として、帯域幅ポリシーを使って、特定のモダリティの帯域幅の制限を定義します。 Skype for Business Server では、オーディオとビデオのモダリティのみに帯域幅の制限を割り当てることができます。 全体的な帯域幅の制限とセッションの制限を設定できます。 Skype for Business Server コントロールパネルを使って、これらのポリシーのコンテナープロファイルを作成、変更、または削除することができます。 ネットワーク帯域幅ポリシーのプロファイルを削除するには、次の手順を使用します。 

### <a name="to-delete-a-bandwidth-policy-profile"></a>帯域幅ポリシーのプロファイルを削除するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 

3.  左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**帯域幅ポリシー**] をクリックします。

4.  [**帯域幅ポリシー** ] ページで、削除する帯域幅ポリシープロファイルをクリックします。

    > [!NOTE]  
    > 一度に複数のプロファイルを削除できます。 これを行うには、ctrl キーを押しながら、CTRL キーを押しながら複数のプロファイルを選択します。 または、すべてのプロファイルを選択するには、[**編集**] メニューの [**すべて選択**] をクリックします。

5.  [**編集**] メニューの [**削除**] をクリックします。
   

    > [!WARNING]  
    > ネットワークサイトに関連付けられている帯域幅ポリシープロファイルを削除することはできません。 プロファイルを削除するには、最初にネットワークサイトとの関連付けを削除する必要があります。 


## <a name="see-also"></a>関連項目

[サイトの通話受付制御の管理](managing-call-admission-control-for-sites.md)
 
[新規-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  

[Set-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  

[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[Remove-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

