---
title: ネットワーク地域の管理
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
description: ネットワーク領域* は、通話受付管理、E9-1-1、およびメディア バイパスの構成で使用されるネットワーク ハブまたはバックボーンです。
ms.openlocfilehash: 2020eea2cf8bf85c915ebf88de6f86cb3a0ee9ca
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122451"
---
# <a name="managing-network-regions-in-skype-for-business-server"></a>Skype for Business Server でのネットワーク領域の管理

*ネットワーク領域は* 、通話受付管理、E9-1-1、およびメディア バイパスの構成で使用されるネットワーク ハブまたはバックボーンです。 ネットワーク領域を表示、作成、または変更するには、次の手順を実行します。 たとえば、1 つの Voice 機能のネットワーク領域を既に作成している場合は、新しいネットワーク領域を作成する必要があります。その他の高度エンタープライズ VoIP機能は、同じネットワーク領域を使用します。 ただし、機能固有の設定を適用するために、既存のネットワーク地域定義を変更することが必要になる場合があります。 たとえば、E9-1-1 のネットワーク領域 (関連付けられたセントラル サイトを必要としない) を作成し、通話受付管理を展開する場合は、ネットワーク領域定義を変更して中央サイトを指定する必要があります。 

この記事の手順を使用して、ネットワーク地域情報を表示したり、ネットワーク領域を作成、変更、または削除したりします。 

## <a name="view-network-region-information"></a>ネットワーク地域情報の表示 


ネットワーク地域は、複数の地理的な領域にまたがるネットワークのさまざまな部分を相互接続します。 すべてのネットワーク地域は、セントラル サイトと関連付ける必要があります。 このセントラル サイトは、通話受付管理 (CAC) 帯域幅ポリシー サービスが実行されているデータ センター サイトです。 Skype for Business Server コントロール パネルを使用して、ネットワーク領域を表示できます。 ネットワーク地域には、音声とビデオの接続にインターネットを使用する代替パスを許可するかどうかの設定が含まれます。 このトピックを使用して、既存のネットワーク地域を表示します。 

### <a name="to-view-information-about-a-network-region-with-skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネルを使用してネットワーク地域に関する情報を表示するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。 

3.  左側のナビゲーション バーで、[ネットワーク構成] **をクリックし**、[地域] を **クリックします**。

4.  [**地域**] ページで、表示する地域をクリックします。
  
    > [!NOTE]  
    > 一度に 1 つの地域のみを表示できます。

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。


### <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a>コマンドレットを使用したネットワーク地域Windows PowerShell表示

ネットワーク地域の情報を表示するには、Windows PowerShell **Get-CsNetworkRegion コマンドレットを使用** します。 このコマンドレットは、Skype for Business Server 管理シェルから、またはサーバーのリモート セッションから実行Windows PowerShell。 

### <a name="to-view-network-region-information"></a>ネットワーク地域情報を表示するには

  - すべてのネットワーク地域に関する情報を表示するには、Skype for Business Server 管理シェルに次のコマンドを入力し、Enter キーを押します。
    
        Get-CsNetworkRegion
    
    次のような情報が表示されます。
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

詳細については、[Get-CsNetworkRegion](/powershell/module/skype/Get-CsNetworkRegionLink) コマンドレットのヘルプ トピックを参照してください。.


## <a name="create-or-modify-network-regions"></a>ネットワーク地域を作成または変更する 

ネットワーク地域は、複数の地理的な領域にまたがるネットワークのさまざまな部分を相互接続します。 すべてのネットワーク地域は、セントラル サイトと関連付ける必要があります。 このセントラル サイトは、通話受付管理 (CAC) 帯域幅ポリシー サービスが実行されているデータ センター サイトです。 Skype for Business Server コントロール パネルを使用して、ネットワーク領域を構成できます。 ネットワーク地域には、オーディオとビデオの接続でインターネット経由の代替パスを許可するかどうかを決定する設定が含まれます。 Skype for Business Server コントロール パネルから、ネットワーク領域を作成、変更、または削除できます。 ネットワーク地域を作成および変更するには、このトピックを参考にしてください。 

### <a name="to-create-a-network-region"></a>ネットワーク地域を作成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。 

3.  左側のナビゲーション バーで、[ネットワーク構成] **をクリックし**、[地域] を **クリックします**。

4.  [**地域**] ページで [**新規**] をクリックします。

5.  [**新しい地域**] ページで、[**名前**] フィールドに値を入力します。 この値は、Skype for Business Server 展開内で一意である必要があります。

6.  [**セントラル サイト**] ドロップダウン リストで、このネットワーク地域に対応するセントラル サイトを選択します。

7.  既定では、[**オーディオ代替パスを有効にする**] チェック ボックスはオンになっています。このフィールドで、プライマリ パスに適当な帯域幅がない場合に音声通話を代替パスにルーティングするかどうかを設定します。インターネットへの負荷分散を無効する必要がある場合にのみ、このチェック ボックスをオフにします。いずれかの通話をインターネット通話にする場合は、帯域幅設定に関係なく、このチェック ボックスをオンにする必要があります。

8.  既定では、[**ビデオ代替パスを有効にする**] チェック ボックスはオンになっています。このフィールドで、プライマリ パスに適当な帯域幅がない場合にビデオ通話を代替パスにルーティングするかどうかを設定します。インターネットへの負荷分散を無効する必要がある場合にのみ、このチェック ボックスをオフにします。いずれかの通話をインターネット通話にする場合は、帯域幅設定に関係なく、このチェック ボックスをオンにする必要があります。

9.  (オプション) [**説明**] フィールドに値を入力して、名前だけでは表現できないこの地域に関する詳細を設定します。

10. [**コミット**] をクリックします。

[**関連付けられているサイト**] テーブルは、ネットワーク地域の作成では使用しません。 サイトを作成または変更するときに、サイトと地域を関連付けます。 詳細については、「サイトの [通話受付管理の管理」を参照してください](managing-call-admission-control-for-sites.md)。

### <a name="to-modify-a-network-region"></a>ネットワーク地域を変更するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。 

3.  左側のナビゲーション バーで、[ネットワーク構成] **をクリックし**、[地域] を **クリックします**。

4.  [**地域**] ページで、変更する地域をクリックします。

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。

6.  [**編集 地域**] ページで、オーディオとビデオの代替パスを有効または無効に切り替えたり、説明を変更したりできます。詳細については、このトピック前半の「ネットワーク地域を作成するには」のセクションを参照してください。

7.  [**コミット**] をクリックします。

このページでは [**関連付けられているサイト**] を変更できません。関連付けられているサイトの一覧は参考のために表示されています。これにより、地域設定を変更するとどのサイトが影響を受けるか確認することができます。


## <a name="delete-existing-network-regions"></a>既存のネットワーク領域を削除する 

ネットワーク地域は、複数の地理的な領域にまたがるネットワークのさまざまな部分を相互接続します。 すべてのネットワーク地域は、セントラル サイトと関連付ける必要があります。 このセントラル サイトは、通話受付管理 (CAC) 帯域幅ポリシー サービスが実行されているデータ センター サイトです。 Skype for Business Server コントロール パネルを使用して、ネットワーク領域を構成できます。 ネットワーク地域には、オーディオとビデオの接続でインターネット経由の代替パスを許可するかどうかを決定する設定が含まれます。 Skype for Business Server コントロール パネルから、ネットワーク領域を作成、変更、または削除できます。 既存のネットワーク地域を削除するには、このトピックを参考にしてください。 

### <a name="to-delete-a-network-region"></a>ネットワーク地域を削除するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。 

3.  左側のナビゲーション バーで、[ネットワーク構成] **をクリックし**、[地域] を **クリックします**。

4.  [**地域**] ページで、削除する地域をクリックします。
  
    > [!NOTE]  
    > 一度に複数の地域を削除できます。これを実行するには、Ctrl キーを押しながら複数の地域を選択します。また、すべての地域を選択するには、[**編集**] メニューの [**すべて選択**] をクリックします。

5.  [**編集**] メニューの [**削除**] をクリックします。

6.  [**OK**] をクリックします。


    > [!WARNING]  
    > ネットワーク地域がネットワーク サイトに関連付けられている場合は、削除することはできません。 サイトに関連付けられている領域を削除しようとすると、エラー メッセージが表示されます。 地域がサイトに関連付けられているかどうかを確認するには、その地域を選択して [**編集**] メニューの [**詳細の表示**] をクリックします。


## <a name="see-also"></a>関連項目

[ネットワーク地域ルートの管理](managing-network-region-routes.md)

[New-CsNetworkRegion](/powershell/module/skype/New-CsNetworkRegion)  

[Set-CsNetworkRegion](/powershell/module/skype/Set-CsNetworkRegion)  

[Remove-CsNetworkRegion](/powershell/module/skype/Remove-CsNetworkRegion)  

[Get-CsNetworkRegion](/powershell/module/skype/Get-CsNetworkRegionLink)