---
title: ネットワーク帯域幅ポリシー プロファイルの管理
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
description: この記事の手順を使用して、ネットワーク帯域幅ポリシー プロファイルを表示、作成、変更、または削除します。
ms.openlocfilehash: a360bd05ac3ee9cbd4d5a8d8d6578389dfc3068c
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62388125"
---
# <a name="managing-network-bandwidth-policy-profiles-in-skype-for-business-server"></a>Skype for Business Server でのネットワーク帯域幅ポリシー プロファイルの管理

この記事の手順を使用して、ネットワーク帯域幅ポリシー プロファイルを表示、作成、変更、または削除します。

## <a name="view-network-bandwidth-policy-profile-information"></a>ネットワーク帯域幅ポリシー プロファイル情報の表示

帯域幅ポリシーは、通話受付管理 (CAC) の一部として、特定のモダリティの帯域幅制限を定義する際に使用します。 このSkype for Business Server、オーディオとビデオのモダリティにのみ帯域幅の制限を割り当てることができます。 全体の帯域幅制限とセッション制限を設定できます。 [コントロール パネル] Skype for Business Serverを使用して、これらのポリシーのコンテナー プロファイルを作成、変更、または削除できます。 各帯域幅ポリシー プロファイルは、1 つ以上のネットワーク サイトに関連付けることができます。 以下の手順に従って、帯域幅ポリシー プロファイルを表示します。 

### <a name="to-view-a-bandwidth-policy-profile"></a>帯域幅ポリシー プロファイルを表示するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。 

3.  左側のナビゲーション バーで [**ネットワーク構成**] をクリックし、[**帯域幅ポリシー**] をクリックします。

4.  [帯域幅 **ポリシー] ページ** で、表示する帯域幅ポリシー プロファイルをクリックします。

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。


### <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a>ネットワーク帯域幅ポリシー プロファイル情報の表示 (Windows PowerShellコマンドレットを使用)

ネットワーク帯域幅プロファイルは、ネットワーク帯域幅とWindows PowerShellコマンドレットをGet-CsNetworkBandwidthPolicyProfileできます。 このコマンドレットは、管理シェルから、またはSkype for Business Serverのリモート セッションから実行Windows PowerShell。 


### <a name="to-view-network-bandwidth-policy-profile-information"></a>ネットワーク帯域幅ポリシー プロファイル情報を表示するには

  - すべてのネットワーク帯域幅ポリシー プロファイルに関する情報を表示するには、次のコマンドを [管理シェル] Skype for Business Server入力し、Enter キーを押します。
    
    **Get-CsNetworkBandwidthPolicyProfile**
    
    次のような情報が表示されます。
    
    Identity : RedmondBandwidthPolicy<br/>
    BWPolicy : {BWLimit=200;BWSessionLimit=200;<br/>
                        BWPolicyModality=Audio, <br/>
                        BWLimit=1400;BWSessionLimit=500;<br/>
                        BWPolicyModality=Video}<br/>
    BWPolicyProfileID : RedmondBandwidthPolicy<br/>
    説明 :

詳細については、[Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) コマンドレットのヘルプ トピックを参照してください。


## <a name="create-or-modify-bandwidth-policy-profiles"></a>帯域幅ポリシー プロファイルの作成または変更

帯域幅ポリシーは、通話受付管理 (CAC) の一部として、特定のモダリティの帯域幅制限を定義する際に使用します。 このSkype for Business Server、オーディオとビデオのモダリティにのみ帯域幅の制限を割り当てることができます。 全体の帯域幅制限とセッション制限を設定できます。 [コントロール パネル] Skype for Business Serverを使用して、これらのポリシーのコンテナー プロファイルを作成、変更、または削除できます。 各帯域幅ポリシー プロファイルは、1 つ以上のネットワーク サイトに関連付けることができます。 帯域幅ポリシー プロファイルを作成または変更するには、次の手順を実行します。 

### <a name="to-create-a-new-bandwidth-policy-profile"></a>新しい帯域幅ポリシー プロファイルを作成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。 

3.  左側のナビゲーション バーで、[ネットワーク構成] **をクリックし**、[帯域幅ポリシー] **をクリックします**。

4.  [帯域幅ポリシー **] ページで、[** 新規] を **クリックします**。

5.  [ **新しい帯域幅ポリシー プロファイル]** で、[名前] フィールドに名前 **を入力** します。 この名前は、すべての帯域幅ポリシー プロファイル間で一意である必要があります。

6.  [オーディオ **の制限] フィールド** に数値を入力します。 この値は、すべてのオーディオ接続に割り当てる最大帯域幅量を kbps で表します。

7.  [オーディオ セッションの制限] フィールド **に数値を入力** します。 この値は、kbps で表される、個々のオーディオ接続に割り当てる最大帯域幅量です。 この値は 40 以上である必要があります。

8.  [ビデオの制限] フィールドに数値 **を入力** します。 この値は、kbps で表される、すべてのビデオ接続に割り当てる最大帯域幅量です。

9.  [ビデオ セッションの制限] フィールド **に数値を入力** します。 この値は、kbps で表される、個々のビデオ接続に割り当てる最大帯域幅量です。 この値は 100 以上である必要があります。

10. (省略可能)[説明] フィールド **に値を入力** して、名前だけでは表現できないこの帯域幅ポリシー プロファイルの詳細を入力します。

11. [**確定**] をクリックします。

    > [!NOTE]  
    > 新しい帯域幅ポリシー プロファイルを作成しても、帯域幅の制限は自動的には適用されません。 最初にポリシー プロファイルをサイトに関連付ける必要があります。 


### <a name="to-modify-a-bandwidth-policy-profile"></a>帯域幅ポリシー プロファイルを変更するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。 

3.  左側のナビゲーション バーで、[ネットワーク構成] **をクリックし**、[帯域幅ポリシー] **をクリックします**。

4.  [**帯域幅ポリシー**] ページで、変更する帯域幅ポリシー プロファイルをクリックします。

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。

6.  [帯域幅ポリシー **プロファイルの編集** ] ページで、必要に応じてフィールドを変更します (詳細については、「新しい帯域幅ポリシー プロファイルを作成するには [」を参照してください](#to-create-a-new-bandwidth-policy-profile))。

7.  [**確定**] をクリックします。

    > [!NOTE]  
    > 帯域幅ポリシー プロファイルを変更すると、この帯域幅ポリシー プロファイルに関連付けられているすべてのネットワーク サイトの帯域幅制限が直ちに更新されます。

  
## <a name="delete-network-bandwidth-policy-profiles"></a>ネットワーク帯域幅ポリシー プロファイルの削除

帯域幅ポリシーは、通話受付管理 (CAC) の一部として、特定のモダリティの帯域幅制限を定義する際に使用します。 このSkype for Business Server、オーディオとビデオのモダリティにのみ帯域幅の制限を割り当てることができます。 全体の帯域幅制限とセッション制限を設定できます。 [コントロール パネル] Skype for Business Serverを使用して、これらのポリシーのコンテナー プロファイルを作成、変更、または削除できます。 ネットワーク帯域幅ポリシー プロファイルを削除するには、次の手順を使用します。 

### <a name="to-delete-a-bandwidth-policy-profile"></a>帯域幅ポリシー プロファイルを削除するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。 

3.  左側のナビゲーション バーで、[ネットワーク構成] **をクリックし**、[帯域幅ポリシー] **をクリックします**。

4.  [帯域幅 **ポリシー] ページ** で、削除する帯域幅ポリシー プロファイルをクリックします。

    > [!NOTE]  
    > 一度に複数のプロファイルを削除できます。 これを行うには、Ctrl キーを押しながら複数のプロファイルを選択します。 または、すべてのプロファイルを選択するには、[編集] メニュー **の [すべて** 選択] **をクリック** します。

5.  [**編集**] メニューの [**削除**] をクリックします。
   

    > [!WARNING]  
    > ネットワーク サイトに関連付けられている帯域幅ポリシー プロファイルを削除することはできません。 プロファイルを削除するには、まずネットワーク サイトとの関連付けを削除する必要があります。 


## <a name="see-also"></a>関連項目

[サイトの通話受付管理の管理](managing-call-admission-control-for-sites.md)
 
[New-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  

[Set-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  

[Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[Remove-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
