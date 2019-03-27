---
title: サイトの呼受付制御を管理します。
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ネットワーク サイトは、オフィスや受付制御 (CAC)、~ 9-1-1、およびメディア バイ パスの展開の場合は、各ネットワーク地域内の場所を呼び出します。
ms.openlocfilehash: 53140cf03110991f2c757e5d52e30a6c7db1d7de
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895420"
---
# <a name="managing-call-admission-control-for-sites-in-skype-for-business-server"></a>Skype for Business Server でのサイトの通話受付管理サービスの管理

ネットワーク サイトは、オフィスや受付制御 (CAC)、~ 9-1-1、およびメディア バイ パスの展開の場合は、各ネットワーク地域内の場所を呼び出します。 ネットワーク サイトの呼受付制御を構成するのには、この資料の手順を使用します。

## <a name="configure-network-site-links"></a>ネットワーク サイト リンクを構成します。

呼び出し受付制御 (CAC) 構成では、内では、ネットワークに直接リンクされているサイト間の帯域幅の制限を定義するサイト間ポリシーを作成できます。 ネットワークのサイトでは、直接リンクを共有する場合は、これら 2 つのサイト間でオーディオとビデオ接続の帯域幅の制限を定義できます。 ネットワーク サイト ポリシーを構成するビジネス サーバーのコントロール パネルの Skype を使用することはできません、これビジネス サーバー管理シェルのコマンドレット、Skype からを使用するだけです。 作成、変更、およびビジネス サーバー管理シェルには、Skype のネットワーク サイト リンク (ネットワーク サイト間ポリシーとも呼ばれます) を削除することができます。

### <a name="to-create-a-network-site-link"></a>ネットワーク サイト リンクを作成するには

1.  RTCUniversalServerAdmins グループのまたは必要なユーザー権限を持つメンバーとしてビジネス サーバー管理シェルの Skype がインストールされているコンピューターにログオンします。

2.  ビジネス サーバー管理シェルには、Skype を起動する: [**スタート**] ボタン、[**すべてのプログラム**] をクリックして、 **Skype**ビジネス サーバーをクリック**ビジネス サーバー管理シェルの Skype**です。

3.  コマンド プロンプトで、構成に対して有効な値を代入する、次のコマンドを入力します。
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    Reno をという名前の新しいネットワーク サイト リンクを作成する次の使用例\_ポートランド、リノ、ポートランドのネットワーク サイト間で帯域幅の制限を設定します。 ネットワーク サイトと帯域幅ポリシーのプロファイルが、このコマンドを実行する前に存在する必要があります。

詳細なパラメーターの説明については、[新規 CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)を参照してください。 サイトのネットワーク リンクに適用可能な帯域幅ポリシー プロファイルの一覧を取得するには、 **Get CsNetworkBandwidthPolicyProfile**コマンドレットを呼び出します。 詳細については、 [Get CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)を参照してください。

### <a name="to-modify-a-network-site-link"></a>ネットワーク サイト リンクを変更するのには

1.  RTCUniversalServerAdmins グループのまたは必要なユーザー権限を持つメンバーとしてビジネス サーバー管理シェルの Skype がインストールされているコンピューターにログオンします。

2.  ビジネス サーバー管理シェルには、Skype を起動する: [**スタート**] ボタン、[**すべてのプログラム**] をクリックして、 **Skype**ビジネス サーバーをクリック**ビジネス サーバー管理シェルの Skype**です。

3.  **セット CsNetworkInterSitePolicy**コマンドレットを使用して、特定のネットワーク サイト リンクのプロパティを変更します。 いずれか (または両方) を変更することができますか、接続先のサイトがあり、リンクに関連付けられている帯域幅ポリシーのプロファイルを変更できます。 Reno をという名前のサイト リンクの帯域幅ポリシーのプロファイルを変更する例を次のとおりです\_ポートランド。
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

詳細なパラメーターの説明については、[一連の CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)を参照してください。


### <a name="to-delete-a-network-site-link"></a>ネットワーク サイト リンクを削除するには

1.  RTCUniversalServerAdmins グループのまたは必要なユーザー権限を持つメンバーとしてビジネス サーバー管理シェルの Skype がインストールされているコンピューターにログオンします。

2.  ビジネス サーバー管理シェルには、Skype を起動する: [**スタート**] ボタン、[**すべてのプログラム**] をクリックして、 **Skype**ビジネス サーバーをクリック**ビジネス サーバー管理シェルの Skype**です。

3.  ネットワーク サイト リンクを削除するのに**削除 CsNetworkInterSitePolicy**コマンドレットを使用します。 Reno を削除する例を次\_ポートランド ネットワーク サイト リンク。
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

詳細なパラメーターの説明については、[削除 CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)を参照してください。


## <a name="view-network-site-information"></a>ネットワーク サイトの情報を表示します。

ネットワーク サイトは、オフィスまたは呼受付制御 (CAC) または拡張 9-1-1 の展開の各領域内で構成されている場所です。 ビジネス サーバー管理シェルのいずれか、Skype のビジネス サーバーのコントロール パネルまたは、Skype のネットワーク サイトの情報を表示できます。 

### <a name="to-view-network-site-information-in-skype-for-business-server-control-panel"></a>Skype のビジネス サーバーのコントロール パネルのネットワーク サイトの情報を表示するのには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。 

3.  左側のナビゲーション ・ バーでは、**ネットワーク構成**をクリックし、し、[**サイト**] をクリックします。

4.  [**サイト**] ページで、表示するサイトをクリックします。
 
    > [!NOTE]  
    > のみ、一度に 1 つのサイトの情報を表示できます。

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。


### <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してネットワーク サイトの情報を表示します。

Windows PowerShell と Get CsNetworkSite コマンドレットを使用してネットワーク サイトの情報を表示できます。 ビジネス サーバー管理シェルの Skype とは Windows PowerShell のリモート セッションからは、このコマンドレットを実行できます。 

### <a name="to-view-network-site-information"></a>ネットワーク サイトの情報を表示するのには

  - ネットワークのすべてのサイトに関する情報を表示するのには、Skype のビジネス サーバー管理シェルには、次のコマンドを入力し、し、ENTER キーを押します。
    
        Get-CsNetworkSite
    
    次のような情報が表示されます。
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

詳細については、 [Get CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)コマンドレットのヘルプ トピックを参照してください。


## <a name="create-or-modify-network-sites"></a>作成またはネットワーク サイトを変更します。 

ネットワーク サイトは、オフィスまたは呼受付制御 (CAC) または拡張 9-1-1 の展開の各領域内で構成されている場所です。 サイトを構成し、地域に関連付けるには、ビジネス サーバーのコントロール パネルの Skype を使用できます。 たとえば、北アメリカのネットワーク領域は、シカゴ、レドモンド、バンクーバーなどのネットワーク サイトに関連付けられている可能性があります。 CAC ネットワーク サイトは、そのサイトには、帯域幅の制限があるない場合でも、組織内のすべてのサイトを作成しなければなりません。 ビジネス サーバーのコントロール パネルの Skype から作成、変更、およびネットワークのサイトを削除することができます。 作成またはネットワーク サイトを変更するには、次の手順を使用します。 

### <a name="to-create-a-network-site"></a>ネットワーク サイトを作成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。 

3.  左側のナビゲーション ・ バーでは、**ネットワーク構成**をクリックし、し、[**サイト**] をクリックします。

4.  [**サイト**] ページで [**新規**を] をクリックします。

5.  **新しいサイト**では、 **[名前**] フィールドで、このサイトの名前を入力します。

    > [!NOTE]  
    > サイト名は、ビジネス サーバー配置の Skype 内で一意である必要があります。

6.  [**地域**] ドロップダウン リストで、このサイトに関連付けるネットワーク領域を選択します。

7.  (省略可能)このサイトへのオーディオまたはビデオ通話に帯域幅の制限を配置する場合は、**帯域幅ポリシー**のドロップダウン リストから適切な設定を使用して帯域幅ポリシーのプロファイルを選択します。
 
    > [!NOTE]  
    > 使用可能な帯域幅ポリシーのプロファイルの詳細を表示したり、**ネットワークのコンフィギュレーション**グループの**ポリシー Profil** ] ページで新しい帯域幅ポリシーのプロファイルを作成できます。 詳細については、[ネットワーク帯域幅ポリシー プロファイルの管理](managing-network-bandwidth-policy-profiles.md)を参照してください。

8.  (省略可能)このサイトの場所を設定する場合は、**場所のポリシー**のドロップ ダウン リストからの場所のポリシーを選択します。

    > [!NOTE]  
    > 場所ポリシー サイトに割り当て拡張 9-1-1 (~ 9-1-1) とクライアントの特定の場所の設定です。 使用可能な場所のポリシーの詳細を表示したり、**ネットワーク構成**グループの [**場所のポリシー** ] ページから、新しい場所のポリシーを作成できます。 

9.  (省略可能)表すことのできない名前だけで、このサイトに関する詳細情報を提供する [**説明**] フィールドに値を入力します。

10. [**コミット**] をクリックします。

    > [!NOTE]  
    > 新しいネットワーク サイトを作成するときは、**サブネットの関連付けられている**テーブルを使用しません。 作成またはサブネットを変更するときは、サブネットをサイトに関連付けます。 詳細については、[ネットワークのサブネットを管理する](managing-network-subnets.md)を参照してください。

### <a name="to-modify-a-network-site"></a>ネットワーク サイトを変更するのには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。 

3.  左側のナビゲーション ・ バーでは、**ネットワーク構成**をクリックし、し、[**サイト**] をクリックします。

4.  [**サイト**] ページで、変更するサイトをクリックします。

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。

6.  [**サイトの編集**] ページで、説明、地域、帯域幅ポリシーのプロファイル、およびサイトに関連付けられている場所のポリシーを変更できます。 詳細について[ネットワーク サイトを作成するのには](#to-create-a-network-site)上記を参照してください。

7.  [**コミット**] をクリックします。

このページに**関連付けられているサブネット**テーブルを変更することはできません。 どのサブネットが影響を受けるサイトの設定を変更するときに注意するように、参照に関連付けられているサブネットの一覧が用意されています。


## <a name="delete-an-existing-network-site"></a>既存のネットワーク サイトを削除します。

ネットワーク サイトは、オフィスまたは呼受付制御 (CAC) または拡張 9-1-1 の展開の各領域内で構成されている場所です。 サイトを構成し、地域に関連付けるには、ビジネス サーバーのコントロール パネルの Skype を使用できます。 たとえば、北アメリカのネットワーク領域は、シカゴ、レドモンド、バンクーバーなどのネットワーク サイトに関連付けられている可能性があります。 CAC ネットワーク サイトは、そのサイトには、帯域幅の制限があるない場合でも、組織内のすべてのサイトを作成しなければなりません。 ビジネス サーバーのコントロール パネルの Skype から作成、変更、およびネットワークのサイトを削除することができます。 既存のネットワーク サイトを削除するのにには、次の手順を使用します。 詳細を作成するか、ネットワーク サイトを変更することについては、[サイトの管理の呼び出しの受付制御](managing-call-admission-control-for-sites.md)を参照してください。


### <a name="to-delete-a-network-site"></a>ネットワーク サイトを削除するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。 

3.  左側のナビゲーション ・ バーでは、**ネットワーク構成**をクリックし、し、[**サイト**] をクリックします。

4.  [**サイト**] ページで、削除するサイトをクリックします。

    > [!NOTE]  
    > 一度に複数のサイトを削除できます。 これを行うには、CTRL キーを押し、CTRL キーを押しながら複数のサイトを選択します。 または、すべてのサイトを選択するには、[**すべて選択****編集**メニューの [します。

5.  [**編集**] メニューの [**削除**] をクリックします。

6.  [**OK**] をクリックします。
    

    > [!WARNING]  
    > ネットワーク サブネットに関連付けられている場合は、ネットワーク サイトを削除することはできません。 サブネットに関連付けられているサイトを削除しようとすると、エラー メッセージが表示されます。 サイトがすべてのサブネットに関連付けられているかどうか、[サイト] をクリックし、[**編集**] メニュー**の詳細を表示**] をクリックします。


## <a name="see-also"></a>関連項目


[新しい-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) 
 
[セット CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  

[削除 CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  

[Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  

[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[新しい-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

[セット CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

[削除 CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  

[Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
