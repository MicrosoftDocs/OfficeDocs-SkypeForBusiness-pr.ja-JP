---
title: ネットワーク帯域幅ポリシーのプロファイルを管理します。
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: この資料の表示、作成、変更、またはネットワークの帯域幅ポリシーのプロファイルを削除する手順を使用します。
ms.openlocfilehash: 58a73774a55a64ac6cb81f0bdf887eb0d1493a35
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222941"
---
# <a name="managing-network-bandwidth-policy-profiles-in-skype-for-business-server"></a>ビジネス サーバーの Skype では、ネットワーク帯域幅ポリシー プロファイルを管理します。

この資料の表示、作成、変更、またはネットワークの帯域幅ポリシーのプロファイルを削除する手順を使用します。

## <a name="view-network-bandwidth-policy-profile-information"></a>ネットワークの帯域幅のポリシー プロファイルの情報を表示します。

呼受付制御 (CAC) の一環として、帯域幅ポリシーを使用して、特定のモダリティの帯域幅の制限を定義します。 ビジネス サーバーの Skype にのみオーディオおよびビデオのモダリティ割り当てることができる帯域幅の制限です。 全体的な帯域幅の制限とセッション制限を設定することができます。 ビジネス サーバーのコントロール パネルの Skype を使用するには作成、変更、またはこれらのポリシーのコンテナー プロファイルを削除します。 各帯域幅ポリシーのプロファイルは、1 つまたは複数のネットワーク サイトと関連付けることができます。 帯域幅ポリシーのプロファイルを表示するのにには、次の手順を使用します。 

### <a name="to-view-a-bandwidth-policy-profile"></a>帯域幅ポリシーのプロファイルを表示するのには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。 

3.  左側のナビゲーション ・ バーで**ネットワークの構成**] をクリックし、**帯域幅ポリシー**] をクリックします。

4.  [**帯域幅ポリシー** ] ページでは、帯域幅ポリシーのプロファイルを表示するをクリックします。

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。


### <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して、ネットワーク帯域幅ポリシーのプロファイル情報を表示します。

ネットワーク帯域幅のプロファイルは、Windows PowerShell と Get CsNetworkBandwidthPolicyProfile コマンドレットを使用して表示できます。 ビジネス サーバー管理シェルの Skype とは Windows PowerShell のリモート セッションからは、このコマンドレットを実行できます。 


### <a name="to-view-network-bandwidth-policy-profile-information"></a>ネットワーク帯域幅ポリシーのプロファイル情報を表示するのには

  - すべてのネットワーク帯域幅ポリシー プロファイルに関する情報を表示するのには、Skype のビジネス サーバー管理シェルには、次のコマンドを入力し、ENTER キーを押します。
    
        Get-CsNetworkBandwidthPolicyProfile
    
    次のような情報が表示されます。
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :


詳細については、 [Get CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)コマンドレットのヘルプ トピックを参照してください。


## <a name="create-or-modify-bandwidth-policy-profiles"></a>作成または帯域幅ポリシーのプロファイルを変更します。

呼受付制御 (CAC) の一環として、帯域幅ポリシーを使用して、特定のモダリティの帯域幅の制限を定義します。 ビジネス サーバーの Skype にのみオーディオおよびビデオのモダリティ割り当てることができる帯域幅の制限です。 全体的な帯域幅の制限とセッション制限を設定することができます。 ビジネス サーバーのコントロール パネルの Skype を使用するには作成、変更、またはこれらのポリシーのコンテナー プロファイルを削除します。 各帯域幅ポリシーのプロファイルは、1 つまたは複数のネットワーク サイトと関連付けることができます。 作成または帯域幅ポリシーのプロファイルを変更するには、次の手順を使用します。 

### <a name="to-create-a-new-bandwidth-policy-profile"></a>新しい帯域幅ポリシー プロファイルを作成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。 

3.  左側のナビゲーション ・ バーでは、**ネットワーク構成**をクリックし、**帯域幅ポリシー**] をクリックします。

4.  [**帯域幅ポリシー** ] ページで [**新規**を] をクリックします。

5.  **新しい帯域幅ポリシー プロファイル**の **[名前**] フィールドに名前を入力します。 この名前は、すべての帯域幅ポリシー プロファイルの中で一意である必要があります。

6.  **オーディオの制限**] フィールドに数値を入力します。 この値は、帯域幅を kbps 単位で表されるすべてのオーディオ接続に割り当てることの最大量です。

7.  **オーディオ セッションの制限**] フィールドに数値を入力します。 この値は、帯域幅を kbps 単位で表される、個々 のオーディオ接続に割り当てることの最大量です。 この値は、40 以上である必要があります。

8.  **ビデオの制限**] フィールドに数値を入力します。 この値は、帯域幅を kbps 単位で表されるすべてのビデオ接続に割り当てることの最大量です。

9.  **ビデオ セッションの制限**] フィールドに数値を入力します。 この値は、最大限の帯域幅を kbps 単位で表される、個々 のビデオ接続に割り当てることです。 この値は、100 以上にする必要があります。

10. (省略可能)表すことのできない名前だけで、この帯域幅ポリシー プロファイルの詳細については、[**説明**] フィールドに値を入力します。

11. [**確定**] をクリックします。

    > [!NOTE]  
    > 新しい帯域幅ポリシー プロファイルを作成するも、帯域幅の制限は自動的に適用されません。 サイト ポリシーのプロファイルを関連付ける必要があります最初。 


### <a name="to-modify-a-bandwidth-policy-profile"></a>帯域幅ポリシーのプロファイルを変更するのには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。 

3.  左側のナビゲーション ・ バーでは、**ネットワーク構成**をクリックし、**帯域幅ポリシー**] をクリックします。

4.  [**帯域幅ポリシー** ] ページで、変更する帯域幅ポリシーのプロファイルをクリックします。

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。

6.  [**帯域幅ポリシーのプロファイルの編集**] ページで、必要に応じてフィールドを変更します (詳細についてを参照してください[新しい帯域幅ポリシー プロファイルを作成する](#to-create-a-new-bandwidth-policy-profile))。

7.  [**確定**] をクリックします。

    > [!NOTE]  
    > 帯域幅ポリシーのプロファイルを変更すると、この帯域幅ポリシー プロファイルに関連付けられているすべてのネットワーク サイトの帯域幅の制限が即座に更新されます。

  
## <a name="delete-network-bandwidth-policy-profiles"></a>ネットワーク帯域幅ポリシー プロファイルを削除します。

呼受付制御 (CAC) の一環として、帯域幅ポリシーを使用して、特定のモダリティの帯域幅の制限を定義します。 ビジネス サーバーの Skype にのみオーディオおよびビデオのモダリティ割り当てることができる帯域幅の制限です。 全体的な帯域幅の制限とセッション制限を設定することができます。 ビジネス サーバーのコントロール パネルの Skype を使用するには作成、変更、またはこれらのポリシーのコンテナー プロファイルを削除します。 ネットワークの帯域幅ポリシー プロファイルを削除するのにには、次の手順を使用します。 

### <a name="to-delete-a-bandwidth-policy-profile"></a>帯域幅ポリシー プロファイルを削除するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。 

3.  左側のナビゲーション ・ バーでは、**ネットワーク構成**をクリックし、**帯域幅ポリシー**] をクリックします。

4.  [**帯域幅ポリシー** ] ページで、削除する帯域幅ポリシーのプロファイルをクリックします。

    > [!NOTE]  
    > 同時に複数のプロファイルを削除できます。 これを行うには、CTRL キーを押し、CTRL キーを押しながら複数のプロファイルを選択します。 または、すべてのプロファイルを選択するに **[すべて選択**] をクリックして **[編集**] メニューです。

5.  [**編集**] メニューの [**削除**] をクリックします。
   

    > [!WARNING]  
    > ネットワーク サイトに関連付けられている帯域幅ポリシーのプロファイルを削除することはできません。 プロファイルを削除する前に、ネットワーク サイトとの関連付けを削除する必要があります。 


## <a name="see-also"></a>関連項目

[サイトの呼受付制御を管理します。](managing-call-admission-control-for-sites.md)
 
[New-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  

[Set-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  

[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[Remove-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

