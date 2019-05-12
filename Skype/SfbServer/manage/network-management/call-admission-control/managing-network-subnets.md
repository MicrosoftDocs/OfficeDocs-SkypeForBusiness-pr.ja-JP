---
title: ネットワークのサブネットを管理します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 呼受付制御 (CAC) が実装されているビジネス サーバーの Skype のほとんどの展開では通常あるサブネットの数が多い。 このため、お勧め多くの場合ビジネス サーバー管理シェルには、Skype からサブネットを構成します。
ms.openlocfilehash: 7b09428f3bdc44f8626cac072b5f4838e08f9efc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33913357"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a>Skype for Business Server でのネットワーク サブネットの管理

ビジネス サーバーのコントロール パネルまたはビジネス サーバー管理シェルの Skype のいずれかの Skype を使用するにはネットワークのサブネットを管理します。 呼受付制御 (CAC) が実装されているビジネス サーバーの Skype のほとんどの展開では通常あるサブネットの数が多い。 このため、お勧め多くの場合ビジネス サーバー管理シェルには、Skype からサブネットを構成します。

ネットワーク サブネットの情報を表示または作成、変更、またはネットワークのサブネットを削除するには、この資料のセクションを使用します。 

## <a name="view-network-subnet-information"></a>ネットワークのサブネット情報を表示します。 

ネットワークのサブネットを表示するのには、次の手順を使用できます。 ビジネス サーバーのコントロール パネルの Skype からを作成、変更、またはネットワーク サブネットを削除することができます。 

### <a name="to-view-a-network-subnet"></a>ネットワークのサブネットを表示するのには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。 

3.  左側のナビゲーション ・ バーでは、**ネットワーク構成**をクリックし、[**サブネット**] をクリックします。

4.  [**サブネット**] ページで、表示するサブネットをクリックします。
 
    > [!NOTE]  
    > のみ、一度に 1 つのサブネットを表示できます。

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a>ネットワーク サブネットの構成情報を使用して Windows PowerShell コマンドレットで表示します。

Windows PowerShell と Get CsNetworkSubnet コマンドレットを使用して、ネットワーク サブネットの情報を表示できます。 ビジネス サーバー管理シェルの Skype とは Windows PowerShell のリモート セッションからは、このコマンドレットを実行できます。 

### <a name="to-view-network-subnet-information"></a>ネットワーク サブネットの情報を表示するのには

  - ネットワークのサブネットに関する情報を表示するのには、Skype のビジネス サーバー管理シェルの次のコマンドを入力し、し、ENTER キーを押します。
    
        Get-CsNetworkSubnet
    
    次のような情報が表示されます。
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0


詳細については、 [Get CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)コマンドレットのヘルプ トピックを参照してください。


## <a name="create-or-modify-network-subnets"></a>作成またはネットワークのサブネットを変更します。 

このサブネットに属するホストの地理的位置を決定するためにネットワークのサブネットをネットワーク サイトに関連付けられてする必要があります。 ビジネス サーバーのコントロール パネルの Skype を使用すると、サブネットを構成します。 ビジネス サーバーのコントロール パネルの Skype からを作成、変更、またはネットワーク サブネットを削除することができます。 

呼受付制御 (CAC) が実装されているビジネス サーバーの Skype のほとんどの展開では通常あるサブネットの数が多い。 このため、お勧め多くの場合ビジネス サーバー管理シェルには、Skype からサブネットを構成します。 そこからは、Windows PowerShell コマンドレット**が CSV のインポート**と連携して**新規 CsNetworkSubnet**を呼び出すことができます。 一緒にこれらのコマンドレットを使用して、すると、コンマ区切り値 (.csv) ファイルからサブネットの設定で読み取りでき、同時に複数のサブネットを作成することができます。 .Csv ファイルからサブネットを作成する方法の例については、[新規 CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)を参照してください。


### <a name="to-create-a-network-subnet"></a>ネットワーク サブネットを作成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。 

3.  左側のナビゲーション ・ バーでは、**ネットワーク構成**をクリックし、[**サブネット**] をクリックします。

4.  [**サブネット**] ページで [**新規**を] をクリックします。

5.  **新しいサブネット**の**サブネット ID**フィールドの値を入力します。 これは、IP アドレス (174.11.12.0 など) は、サブネットで定義されている IP アドレスの範囲内の最初のアドレスである必要があります。

6.  **マスク**」フィールドには、1 から 32 までの数値を入力します。

    > [!NOTE]  
    > この値は、作成されているサブネットに適用するのにはビット マスクです。

7.  [**ネットワーク サイト ID**には、このサブネットが所属するサイトを選択します。

8.  (省略可能)表すことのできない、名前だけがこのサブネットの詳細については、[**説明**] フィールドに値を入力します。

9.  [**コミット**] をクリックします。


### <a name="to-modify-a-network-subnet"></a>ネットワーク サブネットを変更するのには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。 

3.  左側のナビゲーション ・ バーでは、**ネットワーク構成**をクリックし、[**サブネット**] をクリックします。

4.  [**サブネット**] ページで、変更するサブネットをクリックします。

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。

6.  [**サブネットの編集**] ページでは、ビットマスク、関連付けられたネットワーク サイト、または説明を変更できます。 ビットマスクを変更する場合は、サブネット ID がサブネットで定義されている IP アドレスの範囲内の最初のアドレスをする必要がありますまだすることに留意してください。

7.  [**コミット**] をクリックします。

## <a name="delete-network-subnets"></a>ネットワーク サブネットを削除します。

サブネットを削除するのには、次の手順を使用できます。 ビジネス サーバーのコントロール パネルの Skype からを作成、変更、またはネットワーク サブネットを削除することができます。 

呼受付制御 (CAC) が実装されているビジネス サーバーの Skype のほとんどの展開では通常あるサブネットの数が多い。 このため、お勧め多くの場合ビジネス サーバー管理シェルには、Skype からサブネットを構成します。 そこからは、Windows PowerShell コマンドレット**が CSV のインポート**と連携して**新規 CsNetworkSubnet**を呼び出すことができます。 一緒にこれらのコマンドレットを使用して、すると、コンマ区切り値 (.csv) ファイルからサブネットの設定で読み取りでき、同時に複数のサブネットを作成することができます。 .Csv ファイルからサブネットを作成する方法の例については、[新規 CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)を参照してください。


### <a name="to-delete-a-network-subnet"></a>ネットワーク サブネットを削除するのには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。 

3.  左側のナビゲーション ・ バーでは、**ネットワーク構成**をクリックし、[**サブネット**] をクリックします。

4.  [**サブネット**] ページで、削除するサブネットをクリックします。
 
    > [!NOTE]  
    > 同時に複数のサブネットを削除できます。 これを行うには、CTRL キーを押し、CTRL キーを押しながら複数のサブネットを選択します。 または、すべてのサブネットを選択するに **[すべて選択**] をクリックして **[編集**] メニューです。

5.  [**編集**] メニューの [**削除**] をクリックします。

6.  **[OK]** をクリックします。


## <a name="see-also"></a>関連項目

[新しい-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  

[セット CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  

[削除 CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  

[Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
