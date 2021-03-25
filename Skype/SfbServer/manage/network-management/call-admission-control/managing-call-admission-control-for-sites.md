---
title: サイトの通話受付管理の管理
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
description: ネットワーク サイトは、通話受付管理 (CAC)、E9-1-1、およびメディア バイパスが展開される各ネットワーク地域内のオフィスまたは拠点です。
ms.openlocfilehash: 0b339f15e53dd94bda655884f70c041f9da9e5a8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118566"
---
# <a name="managing-call-admission-control-for-sites-in-skype-for-business-server"></a>Skype for Business Server でのサイトの通話受付管理サービスの管理

ネットワーク サイトは、通話受付管理 (CAC)、E9-1-1、およびメディア バイパスが展開される各ネットワーク地域内のオフィスまたは拠点です。 この記事の手順を使用して、ネットワーク サイトの通話受付管理を構成します。

## <a name="configure-network-site-links"></a>ネットワーク サイト リンクの構成

通話受付管理 (CAC) 構成内に、直接リンクされているサイト間の帯域幅制限を定義するネットワークサイト間ポリシーを作成できます。 ネットワーク サイトが直接リンクを共有している場合、これらの 2 つのサイト間にオーディオ接続およびビデオ接続の帯域幅制限を定義できます。 Skype for Business Server コントロール パネルを使用してネットワーク サイト ポリシーを構成することはできません。これは、Skype for Business Server 管理シェルのコマンドレットを使用する場合にのみ実行できます。 Skype for Business Server 管理シェルからネットワーク サイト リンク (ネットワークサイト間ポリシーとも呼ばれる) を作成、変更、および削除できます。

### <a name="to-create-a-network-site-link"></a>ネットワーク サイト リンクを作成するには

1.  Skype for Business Server 管理シェルがインストールされているコンピューターに RTCUniversalServerAdmins グループのメンバーとして、または必要なユーザー権限でログオンします。

2.  Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business Server]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。

3.  コマンド プロンプトで、使用している構成で有効な値に置き換えて、次のコマンドを入力します。
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    次の使用例は、Reno とポートランドのネットワーク サイト間の帯域幅制限を設定する、Reno Portland という名前の新しいネットワーク サイト \_ リンクを作成します。 ネットワーク サイトと帯域幅ポリシーのプロファイルが、このコマンドを実行する前に既に存在している必要があります。

パラメーターの詳細については [、「New-CsNetworkInterSitePolicy」を参照してください](/powershell/module/skype/New-CsNetworkInterSitePolicy)。 ネットワーク サイト リンクに適用できる帯域幅ポリシーのプロファイルの一覧を取得するには、**Get-CsNetworkBandwidthPolicyProfile** コマンドレットを呼び出します。 詳細については [、「Get-CsNetworkBandwidthPolicyProfile」を参照してください](/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)。

### <a name="to-modify-a-network-site-link"></a>ネットワーク サイト リンクを変更するには

1.  Skype for Business Server 管理シェルがインストールされているコンピューターに RTCUniversalServerAdmins グループのメンバーとして、または必要なユーザー権限でログオンします。

2.  Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business Server]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。

3.  特定のネットワーク サイト リンクのプロパティを変更するには、**Set-CsNetworkInterSitePolicy** コマンドレットを使用します。 接続されたサイトの一方 (または両方) を変更したり、リンクに関連付けられた帯域幅ポリシーのプロファイルを変更したりできます。 Reno Portland という名前のサイト リンクの帯域幅ポリシー プロファイルを変更する例を \_ 次に示します。
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

パラメーターの詳細については [、「Set-CsNetworkInterSitePolicy」を参照してください](/powershell/module/skype/Set-CsNetworkInterSitePolicy)。


### <a name="to-delete-a-network-site-link"></a>ネットワーク サイト リンクを削除するには

1.  Skype for Business Server 管理シェルがインストールされているコンピューターに RTCUniversalServerAdmins グループのメンバーとして、または必要なユーザー権限でログオンします。

2.  Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business Server]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。

3.  ネットワーク サイト リンクを削除するには、**Remove-CsNetworkInterSitePolicy** コマンドレットを使用します。 次の例では、Reno \_ Portland ネットワーク サイト リンクを削除します。
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

パラメーターの詳細については [、「Remove-CsNetworkInterSitePolicy」を参照してください](/powershell/module/skype/Remove-CsNetworkInterSitePolicy)。


## <a name="view-network-site-information"></a>ネットワーク サイト情報の表示

ネットワーク サイトは、通話受付管理 (CAC) または Enhanced 9-1-1 展開の各地域内で構成されるオフィスまたは拠点です。 ネットワーク サイト情報は、Skype for Business Server コントロール パネルまたは Skype for Business Server 管理シェルで表示できます。 

### <a name="to-view-network-site-information-in-skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネルでネットワーク サイト情報を表示するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。 

3.  左側のナビゲーション バーで、[ネットワーク構成] **をクリックし**、[サイト] を **クリックします**。

4.  [**サイト**] ページで、表示するサイトをクリックします。
 
    > [!NOTE]  
    > 一度に表示できるのは 1 つのサイトの情報だけです。

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。


### <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a>コマンドレットを使用したネットワーク サイト情報Windows PowerShell表示する

ネットワーク サイトの情報を表示するには、Windows PowerShellコマンドレットをGet-CsNetworkSiteします。 このコマンドレットは、Skype for Business Server 管理シェルから、またはサーバーのリモート セッションから実行Windows PowerShell。 

### <a name="to-view-network-site-information"></a>ネットワーク サイトの情報を表示するには

  - すべてのネットワーク サイトに関する情報を表示するには、Skype for Business Server 管理シェルに次のコマンドを入力し、Enter キーを押します。
    
        Get-CsNetworkSite
    
    次のような情報が表示されます。
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

詳細については、[Get-CsNetworkSite](/powershell/module/skype/Get-CsNetworkSite) コマンドレットのヘルプ トピックを参照してください。


## <a name="create-or-modify-network-sites"></a>ネットワーク サイトを作成または変更する 

ネットワーク サイトは、通話受付管理 (CAC) または Enhanced 9-1-1 展開の各地域内で構成されるオフィスまたは拠点です。 Skype for Business Server コントロール パネルを使用してサイトを構成し、それらを地域に関連付けできます。 たとえば、北アメリカのネットワーク地域は、シカゴ、レドモンド、バンクーバーなどのネットワーク サイトと関連付けられます。 CAC ネットワーク サイトは、サイトに帯域幅制限がない場合でも、組織内の各サイトに作成する必要があります。 Skype for Business Server コントロール パネルから、ネットワーク サイトを作成、変更、および削除できます。 ネットワーク サイトを作成または変更するには、以下の手順を使用します。 

### <a name="to-create-a-network-site"></a>ネットワーク サイトを作成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。 

3.  左側のナビゲーション バーで、[ネットワーク構成] **をクリックし**、[サイト] を **クリックします**。

4.  [**サイト**] ページで、[**新規**] をクリックします。

5.  [**新しいサイト**] で、[**名前**] フィールドにサイトの名前を入力します。

    > [!NOTE]  
    > サイト名は、Skype for Business Server 展開内で一意である必要があります。

6.  [**地域**] ドロップダウン リストで、このサイトに関連付けるネットワーク地域を選択します。

7.  (オプション) このサイトに対する音声またはビデオ通話に帯域幅制限を設定する場合は、[**帯域幅ポリシー**] ドロップダウン リストで該当する設定値を備える帯域幅ポリシー プロファイルを選択します。
 
    > [!NOTE]  
    > ネットワーク構成グループの [ポリシー プロファイル] ページで、使用可能な帯域幅ポリシー プロファイルの詳細を表示するか、新しい帯域幅ポリシー プロファイル **を作成** できます。 詳細については、「 [ネットワーク帯域幅ポリシー プロファイルの管理」を参照してください](managing-network-bandwidth-policy-profiles.md)。

8.  (オプション) このサイトに、場所に関する設定を提供する場合は、[**場所のポリシー**] ドロップダウン リストで場所のポリシーを選択します。

    > [!NOTE]  
    > 場所のポリシーは、特定の Enhanced 9-1-1 (E9-1-1) とクライアントの場所に関連する設定をサイトに割り当てます。 [**ネットワーク構成**] グループの [**場所のポリシー**] ページでは、利用可能な場所のポリシーの詳細を表示したり、新しい場所のポリシーを作成したりできます。 

9.  (オプション) [**説明**] フィールドに値を入力して、名前だけでは表現することのできないこのサイトの詳細情報を提供します。

10. [**確定**] をクリックします。

    > [!NOTE]  
    > 新しいネットワーク サイトを作成するとき、[**関連付けられたサブネット**] テーブルは使用しません。 サブネットの作成または変更時に、サブネットをサイトに関連付けます。 詳細については、「ネットワーク サブネット [の管理」を参照してください](managing-network-subnets.md)。

### <a name="to-modify-a-network-site"></a>ネットワーク サイトを変更するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。 

3.  左側のナビゲーション バーで、[ネットワーク構成] **をクリックし**、[サイト] を **クリックします**。

4.  [**サイト**] ページで、変更するサイトをクリックします。

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。

6.  [**サイトの編集**] ページでは、サイトに関連付けられた、説明、地域、帯域幅ポリシー プロファイル、および場所のポリシーを変更できます。 詳細については、「上記の [ネットワーク サイトを作成するには」を参照](#to-create-a-network-site) してください。

7.  [**確定**] をクリックします。

このページの [**関連付けられたサブネット**] テーブルを変更することはできません。 関連付けられたサブネットの一覧は、参照のために用意されており、サイトの設定を変えるとどのサブネットが影響を受けるかを確認できます。


## <a name="delete-an-existing-network-site"></a>既存のネットワーク サイトを削除する

ネットワーク サイトは、通話受付管理 (CAC) または Enhanced 9-1-1 展開の各地域内で構成されるオフィスまたは拠点です。 Skype for Business Server コントロール パネルを使用してサイトを構成し、それらを地域に関連付けできます。 たとえば、北アメリカのネットワーク地域は、シカゴ、レドモンド、バンクーバーなどのネットワーク サイトと関連付けられます。 CAC ネットワーク サイトは、サイトに帯域幅制限がない場合でも、組織内の各サイトに作成する必要があります。 Skype for Business Server コントロール パネルから、ネットワーク サイトを作成、変更、および削除できます。 既存のネットワーク サイトを削除するには、次の手順を実行します。 ネットワーク サイトの作成または変更の詳細については、「サイトの通話受付管理の管理 [」を参照してください](managing-call-admission-control-for-sites.md)。


### <a name="to-delete-a-network-site"></a>ネットワーク サイトを削除するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。 

3.  左側のナビゲーション バーで、[ネットワーク構成] **をクリックし**、[サイト] を **クリックします**。

4.  [**サイト**] ページで、削除するサイトをクリックします。

    > [!NOTE]  
    > 1 つ以上のサイトを一度に削除できます。 これを実行するには、Ctrl キーを押しながら、複数のサイトを選択します。 また、すべてのサイトを選択するには、[**編集**] メニューの [**すべて選択**] をクリックします。

5.  [**編集**] メニューの [**削除**] をクリックします。

6.  [**OK**] をクリックします。
    

    > [!WARNING]  
    > ただし、ネットワーク サイトがネットワーク サブネットに関連付けられている場合は、サイトを削除することはできません。 サブネットに関連付けられているサイトを削除しようとすると、エラー メッセージが表示されます。 サイトがサブネットに関連付けられているかどうかを確認するには、そのサイトをクリックして、[**編集**] メニューの [**詳細の表示**] をクリックします。


## <a name="see-also"></a>関連項目


[New-CsNetworkInterSitePolicy](/powershell/module/skype/New-CsNetworkInterSitePolicy) 
 
[Set-CsNetworkInterSitePolicy](/powershell/module/skype/Set-CsNetworkInterSitePolicy)  

[Remove-CsNetworkInterSitePolicy](/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  

[Get-CsNetworkInterSitePolicy](/powershell/module/skype/Get-CsNetworkInterSitePolicy)  

[Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[New-CsNetworkSite](/powershell/module/skype/New-CsNetworkSite)

[Set-CsNetworkSite](/powershell/module/skype/Set-CsNetworkSite)

[Remove-CsNetworkSite](/powershell/module/skype/Remove-CsNetworkSite)  

[Get-CsNetworkSite](/powershell/module/skype/Get-CsNetworkSite)