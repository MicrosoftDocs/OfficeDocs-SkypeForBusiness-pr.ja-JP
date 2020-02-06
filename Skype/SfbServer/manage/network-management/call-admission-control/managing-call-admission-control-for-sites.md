---
title: サイトの通話受付制御の管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: '[ネットワークサイト] は、通話受付制御 (CAC)、E9、および media バイパスの展開の各ネットワーク領域内の事業所または場所です。'
ms.openlocfilehash: ec2a3dda70bdd4b952169ca663ca271b76f98481
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817516"
---
# <a name="managing-call-admission-control-for-sites-in-skype-for-business-server"></a>Skype for Business Server でのサイトの通話受付管理サービスの管理

[ネットワークサイト] は、通話受付制御 (CAC)、E9、および media バイパスの展開の各ネットワーク領域内の事業所または場所です。 この記事の手順を使用して、ネットワークサイトの通話受付制御を構成します。

## <a name="configure-network-site-links"></a>ネットワークサイトリンクを構成する

通話受付制御 (CAC) 構成では、直接リンクされているサイト間の帯域幅の制限を定義するネットワーク間ポリシーを作成できます。 ネットワークサイトが直接リンクを共有している場合、オーディオおよびビデオ接続の帯域幅の制限は、これら2つのサイト間で定義できます。 Skype for Business Server コントロールパネルを使ってネットワークサイトポリシーを構成することはできません。これは、Skype for Business Server 管理シェルからコマンドレットを使用することによってのみ実行できます。 Skype for Business Server 管理シェルからネットワークサイトリンク (ネットワーク間ポリシーとも呼ばれます) の作成、変更、削除を行うことができます。

### <a name="to-create-a-network-site-link"></a>ネットワークサイトのリンクを作成するには

1.  Skype for Business Server 管理シェルが RTCUniversalServerAdmins グループのメンバーとして、または必要なユーザー権限を持つコンピューターにログオンします。

2.  Skype for Business Server 管理シェルを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**] をクリックします。次に、[skype **for business server**] をクリックし、[ **skype for business server 管理シェル**] をクリックします。

3.  コマンドプロンプトで、次のコマンドを入力します。これは、構成に対して有効な値に置き換えます。
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    この例では、Reno とポートランドのネットワーク\_サイト間の帯域幅の制限を設定する Reno ポートランドという名前の新しいネットワークサイトリンクを作成します。 このコマンドを実行する前に、ネットワークサイトと帯域幅ポリシーのプロファイルが既に存在している必要があります。

パラメーターの詳細については、「 [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)」を参照してください。 ネットワークサイトリンクに適用できる帯域幅ポリシープロファイルの一覧を取得するには、 **CsNetworkBandwidthPolicyProfile**コマンドレットを呼び出します。 詳細については、「 [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)」を参照してください。

### <a name="to-modify-a-network-site-link"></a>ネットワークサイトのリンクを変更するには

1.  Skype for Business Server 管理シェルが RTCUniversalServerAdmins グループのメンバーとして、または必要なユーザー権限を持つコンピューターにログオンします。

2.  Skype for Business Server 管理シェルを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**] をクリックします。次に、[skype **for business server**] をクリックし、[ **skype for business server 管理シェル**] をクリックします。

3.  指定のネットワークサイトリンクのプロパティを変更するには、 **CsNetworkInterSitePolicy**コマンドレットを使用します。 いずれか (または両方) または接続されたサイトを変更することができます。また、リンクに関連付けられている帯域幅ポリシープロファイルを変更することもできます。 Reno\_ポートランドという名前のサイトリンクの帯域幅ポリシープロファイルを変更する例を次に示します。
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

パラメーターの詳細については、「 [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)」を参照してください。


### <a name="to-delete-a-network-site-link"></a>ネットワークサイトのリンクを削除するには

1.  Skype for Business Server 管理シェルが RTCUniversalServerAdmins グループのメンバーとして、または必要なユーザー権限を持つコンピューターにログオンします。

2.  Skype for Business Server 管理シェルを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**] をクリックします。次に、[skype **for business server**] をクリックし、[ **skype for business server 管理シェル**] をクリックします。

3.  ネットワークサイトへのリンクを削除するには、 **CsNetworkInterSitePolicy**コマンドレットを使用します。 次の例では、\_Reno ポートランドネットワークサイトのリンクを削除します。
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

パラメーターの詳細については、「 [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)」を参照してください。


## <a name="view-network-site-information"></a>ネットワークサイトの情報を表示する

[ネットワークサイト] は、通話受付制御 (CAC) または拡張9-1-1 展開の各領域内に構成されているオフィスまたは場所です。 ネットワークサイトの情報は、Skype for Business Server コントロールパネルまたは Skype for Business Server 管理シェルで確認できます。 

### <a name="to-view-network-site-information-in-skype-for-business-server-control-panel"></a>Skype for Business Server コントロールパネルでネットワークサイトの情報を表示するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 

3.  左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**サイト**] をクリックします。

4.  [**サイト**] ページで、表示するサイトをクリックします。
 
    > [!NOTE]  
    > 一度に1つのサイトの情報のみを表示できます。

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。


### <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用したネットワークサイト情報の表示

ネットワークサイトの情報を表示するには、Windows PowerShell を使用するか、または CsNetworkSite コマンドレットを使用します。 このコマンドレットは、Skype for Business Server 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 

### <a name="to-view-network-site-information"></a>ネットワークサイトの情報を表示するには

  - すべてのネットワークサイトに関する情報を表示するには、Skype for Business Server 管理シェルで次のコマンドを入力して、enter キーを押します。
    
        Get-CsNetworkSite
    
    次のような情報が表示されます。
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

詳細については、「 [CsNetworkSite site](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) 」コマンドレットのヘルプトピックを参照してください。


## <a name="create-or-modify-network-sites"></a>ネットワークサイトを作成または変更する 

[ネットワークサイト] は、通話受付制御 (CAC) または拡張9-1-1 展開の各領域内に構成されているオフィスまたは場所です。 Skype for Business Server コントロールパネルを使用して、サイトを構成し、それらを地域に関連付けることができます。 たとえば、北米向けのネットワーク領域は、シカゴ、Redmond、バンクーバーなどのネットワークサイトに関連付けられている場合があります。 サイト内のすべてのサイトに対して、CAC ネットワークサイトを作成する必要があります。このサイトには帯域幅の制限がありません。 Skype for Business Server コントロールパネルから、ネットワークサイトの作成、変更、削除を行うことができます。 ネットワークサイトを作成または変更するには、次の手順を使用します。 

### <a name="to-create-a-network-site"></a>ネットワークサイトを作成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 

3.  左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**サイト**] をクリックします。

4.  [**サイト**] ページで、[**新規**] をクリックします。

5.  [**新しいサイト**] の [**名前**] フィールドに、このサイトの名前を入力します。

    > [!NOTE]  
    > サイト名は、Skype for Business Server の展開内で一意である必要があります。

6.  [ **Region** ] ドロップダウンリストで、このサイトに関連付けるネットワーク領域を選びます。

7.  省略このサイトへの音声通話またはビデオ通話に帯域幅の制限を設定する場合は、[**帯域幅ポリシー** ] ドロップダウンリストから適切な設定を使用して、帯域幅ポリシーのプロファイルを選択します。
 
    > [!NOTE]  
    > 利用可能な帯域幅ポリシープロファイルの詳細を表示したり、新しい帯域幅ポリシープロファイルを作成したりするには、**ネットワーク構成**グループの [**ポリシー Profil** ] ページを使用します。 詳細については、「[ネットワーク帯域幅ポリシープロファイルを管理する](managing-network-bandwidth-policy-profiles.md)」を参照してください。

8.  省略このサイトの場所の設定を指定する場合は、[**場所のポリシー** ] ドロップダウンリストから場所のポリシーを選びます。

    > [!NOTE]  
    > 位置情報ポリシーは、特定の拡張 9-1-1 (E9) およびクライアントの場所の設定をサイトに割り当てます。 利用可能な位置情報ポリシーの詳細を表示するか、[**ネットワーク構成**] グループの [**場所のポリシー** ] ページから新しい場所ポリシーを作成することができます。 

9.  省略[**説明**] フィールドに値を入力して、このサイトについて、名前だけでは表現できない詳細情報を入力します。

10. [**コミット**] をクリックします。

    > [!NOTE]  
    > 新しいネットワークサイトを作成する場合は、**関連するサブネット**テーブルを使用しません。 サブネットを作成または変更するときに、サブネットをサイトに関連付けます。 詳細については、「[ネットワークサブネットを管理する](managing-network-subnets.md)」を参照してください。

### <a name="to-modify-a-network-site"></a>ネットワークサイトを変更するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 

3.  左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**サイト**] をクリックします。

4.  [**サイト**] ページで、変更するサイトをクリックします。

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。

6.  [**サイトの編集**] ページでは、サイトに関連付けられている説明、地域、帯域幅ポリシーのプロファイル、および場所のポリシーを変更できます。 詳細については、「[ネットワークサイトを作成する」を](#to-create-a-network-site)参照してください。

7.  [**コミット**] をクリックします。

このページでは、**関連するサブネット**テーブルを変更することはできません。 関連付けられたサブネットの一覧は参照用に提供されるため、サイトの設定を変更したときに影響を受けるサブネットを認識できます。


## <a name="delete-an-existing-network-site"></a>既存のネットワークサイトを削除する

[ネットワークサイト] は、通話受付制御 (CAC) または拡張9-1-1 展開の各領域内に構成されているオフィスまたは場所です。 Skype for Business Server コントロールパネルを使用して、サイトを構成し、それらを地域に関連付けることができます。 たとえば、北米向けのネットワーク領域は、シカゴ、Redmond、バンクーバーなどのネットワークサイトに関連付けられている場合があります。 サイト内のすべてのサイトに対して、CAC ネットワークサイトを作成する必要があります。このサイトには帯域幅の制限がありません。 Skype for Business Server コントロールパネルから、ネットワークサイトの作成、変更、削除を行うことができます。 既存のネットワークサイトを削除するには、次の手順を使用します。 ネットワークサイトの作成または変更の詳細については、「[サイトの通話受付制御を管理する](managing-call-admission-control-for-sites.md)」を参照してください。


### <a name="to-delete-a-network-site"></a>ネットワークサイトを削除するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 

3.  左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**サイト**] をクリックします。

4.  [**サイト**] ページで、削除するサイトをクリックします。

    > [!NOTE]  
    > 一度に複数のサイトを削除できます。 この操作を行うには、ctrl キーを押しながら複数のサイトを選び、CTRL キーを押しながら選択します。 または、すべてのサイトを選択するには、[**編集**] メニューの [**すべて選択**] をクリックします。

5.  [**編集**] メニューの [**削除**] をクリックします。

6.  **[OK]** をクリックします。
    

    > [!WARNING]  
    > ネットワークサイトがネットワークサブネットに関連付けられている場合は、そのサイトを削除することはできません。 サブネットに関連付けられているサイトを削除しようとすると、エラーメッセージが表示されます。 サイトがいずれかのサブネットに関連付けられているかどうかを確認するには、サイトをクリックし、[**編集**] メニューの [**詳細の表示**] をクリックします。


## <a name="see-also"></a>関連項目


[新規-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) 
 
[Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  

[Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  

[Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  

[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[新しい-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

[Set-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

[CsNetworkSite の削除](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  

[Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
