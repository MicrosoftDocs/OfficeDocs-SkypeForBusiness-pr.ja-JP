---
title: ネットワーク領域の管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ネットワーク領域 * は、通話受付制御、E9-1、メディアバイパスの構成で使用されるネットワークハブまたはバックボーンです。
ms.openlocfilehash: 8d1d60389fe910e2b5c2b8b1c357520aad30db96
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279530"
---
# <a name="managing-network-regions-in-skype-for-business-server"></a>Skype for Business Server でのネットワーク領域の管理

*ネットワーク領域*とは、通話受付制御、E9-1、メディアバイパスの構成で使用されるネットワークハブまたはバックボーンのことです。 ネットワーク領域を表示、作成、または変更するには、次の手順を使用します。 たとえば、1つの音声機能のネットワーク領域を既に作成している場合は、新しいネットワークの領域を作成する必要はありません。その他の高度なエンタープライズ Voip 機能でも、同じネットワーク領域が使用されます。 ただし、機能固有の設定を適用するために、ネットワーク地域に関する既存の定義に変更を加える必要が生じることがあります。 たとえば、E9-1-1 用のネットワーク地域を作成し (この場合は関連付けられた中央サイトは必要ありません)、次に通話受付管理を展開する場合は、中央サイトを指定するためにネットワーク地域の定義を変更する必要があります。 

この記事の手順を使用して、ネットワークの地域情報を表示したり、ネットワーク領域を作成、変更、または削除したりします。 

## <a name="view-network-region-information"></a>ネットワークの地域情報を表示する 


ネットワーク領域は、ネットワークのさまざまな部分を複数の地域で相互接続します。 すべてのネットワーク領域はセントラルサイトと関連付けられている必要があります。 セントラルサイトは、通話受付制御 (CAC) 帯域幅ポリシーサービスが実行されているデータセンターサイトです。 Skype for Business Server コントロールパネルを使用して、ネットワークの領域を表示することができます。 [ネットワーク] 領域には、インターネット経由の代替パスが音声とビデオに接続できるかどうかを決定する設定が含まれます。 既存のネットワーク領域を表示するには、このトピックを参照してください。 

### <a name="to-view-information-about-a-network-region-with-skype-for-business-server-control-panel"></a>Skype for Business Server コントロールパネルでネットワーク領域に関する情報を表示するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 

3.  左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**地域**] をクリックします。

4.  [**領域**] ページで、表示する地域をクリックします。
  
    > [!NOTE]  
    > 表示できる領域は一度に1つだけです。

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。


### <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用したネットワーク領域情報の表示

ネットワークの地域情報は、Windows PowerShell と、ユーザーの**入手用の Networkregion**コマンドレットを使って表示できます。 このコマンドレットは、Skype for Business Server 管理シェルから、または Windows PowerShell のリモートセッションからでも実行できます。 

### <a name="to-view-network-region-information"></a>ネットワークの地域情報を表示するには

  - すべてのネットワーク領域に関する情報を表示するには、Skype for Business Server 管理シェルで次のコマンドを入力し、enter キーを押します。
    
        Get-CsNetworkRegion
    
    次のような情報が表示されます。
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

詳細については、「 [CsNetworkRegion の取得](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)」コマンドレットのヘルプトピックを参照してください。


## <a name="create-or-modify-network-regions"></a>ネットワーク領域を作成または変更する 

ネットワーク領域は、ネットワークのさまざまな部分を複数の地域で相互接続します。 すべてのネットワーク領域はセントラルサイトと関連付けられている必要があります。 セントラルサイトは、通話受付制御 (CAC) 帯域幅ポリシーサービスが実行されているデータセンターサイトです。 Skype for Business Server コントロールパネルを使用して、ネットワークの領域を構成することができます。 [ネットワーク] 領域には、インターネット経由の代替パスが音声とビデオに接続できるかどうかを決定する設定が含まれます。 Skype for Business Server コントロールパネルから、ネットワークの領域を作成、変更、または削除することができます。 このトピックは、ネットワーク領域の作成と変更に使用します。 

### <a name="to-create-a-network-region"></a>ネットワークの領域を作成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 

3.  左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**地域**] をクリックします。

4.  [**領域**] ページで、[**新規**] をクリックします。

5.  [**新しい領域**] ページで、[**名前**] フィールドに値を入力します。 この値は、Skype for Business Server の展開内で一意である必要があります。

6.  [**セントラルサイト**] ドロップダウンリストから、このネットワーク領域のセントラルサイトを選びます。

7.  [**オーディオ代替パスを有効にする**] チェックボックスは、既定でオンになっています。 このフィールドは、十分な帯域幅がプライマリパスに存在しない場合に、代替パスを介して音声通話をルーティングするかどうかを決定します。 オフロードをインターネットにオフにする必要がある場合にのみ、このチェックボックスをオフにします。 いずれかの通話がインターネット通話の場合は、帯域幅の設定に関係なく、このチェックボックスをオンにする必要があります。

8.  [**ビデオの代替パスを有効にする**] チェックボックスは、既定でオンになっています。 このフィールドは、ビデオ通話が、プライマリパスに十分な帯域幅が存在しない場合に、代替パスを使用してビデオ通話をルーティングするかどうかを決定します。 オフロードをインターネットにオフにする必要がある場合にのみ、このチェックボックスをオフにします。 いずれかの通話がインターネット通話の場合は、帯域幅の設定に関係なく、このチェックボックスをオンにする必要があります。

9.  省略[**説明**] フィールドに値を入力して、この領域について、名前だけでは表現できない詳細情報を入力します。

10. [**コミット**] をクリックします。

**関連付けら**れたサイトテーブルは、ネットワーク領域の作成には使用されません。 サイトを作成または変更するときに、サイトを地域に関連付けます。 詳しくは、「[サイトの通話受付制御を管理する](managing-call-admission-control-for-sites.md)」をご覧ください。

### <a name="to-modify-a-network-region"></a>ネットワークの領域を変更するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 

3.  左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**地域**] をクリックします。

4.  [**領域**] ページで、変更する領域をクリックします。

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。

6.  [**領域の編集**] ページで、オーディオおよびビデオの代替パスを有効または無効にする設定を変更したり、説明を変更したりすることができます (詳細については、このトピックの「ネットワーク領域を作成する」セクションを参照してください)。

7.  [**コミット**] をクリックします。

このページでは、**関連付けられたサイト**を変更することはできません。 関連付けられたサイトの一覧は参照用に提供されるため、地域設定を変更したときに影響を受けるサイトがわかります。


## <a name="delete-existing-network-regions"></a>既存のネットワーク領域を削除する 

ネットワーク領域は、ネットワークのさまざまな部分を複数の地域で相互接続します。 すべてのネットワーク領域はセントラルサイトと関連付けられている必要があります。 セントラルサイトは、通話受付制御 (CAC) 帯域幅ポリシーサービスが実行されているデータセンターサイトです。 Skype for Business Server コントロールパネルを使用して、ネットワークの領域を構成することができます。 [ネットワーク] 領域には、インターネット経由の代替パスが音声とビデオに接続できるかどうかを決定する設定が含まれます。 Skype for Business Server コントロールパネルから、ネットワークの領域を作成、変更、または削除することができます。 既存のネットワーク領域を削除するには、このトピックを使用します。 

### <a name="to-delete-a-network-region"></a>ネットワークの領域を削除するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 

3.  左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**地域**] をクリックします。

4.  [**領域**] ページで、削除する地域をクリックします。
  
    > [!NOTE]  
    > 一度に複数の領域を削除することができます。 これを行うには、ctrl キーを押しながら、CTRL キーを押しながら複数の領域を選択します。 または、すべての領域を選択するには、[**編集**] メニューの [**すべて選択**] をクリックします。

5.  [**編集**] メニューの [**削除**] をクリックします。

6.  **[OK]** をクリックします。


    > [!WARNING]  
    > ネットワーク領域がネットワークサイトに関連付けられている場合、その領域を削除することはできません。 サイトに関連付けられている領域を削除しようとすると、エラーメッセージが表示されます。 領域がいずれかのサイトに関連付けられているかどうかを確認するには、地域を選択し、[**編集**] メニューの [**詳細の表示**] をクリックします。


## <a name="see-also"></a>関連項目

[ネットワーク領域ルートの管理](managing-network-region-routes.md)

[新しい CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  

[Set-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  

[CsNetworkRegion の削除](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  

[Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
