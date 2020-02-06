---
title: ネットワークサブネットの管理
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
description: 通話受付制御 (CAC) が実装されている Skype for Business Server の大半の展開では、通常、多数のサブネットが存在します。 このため、多くの場合、Skype for Business Server 管理シェルからサブネットを構成することをお勧めします。
ms.openlocfilehash: fd7d71b3971b176939967830ca3e071ef4c77dbf
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817466"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a>Skype for Business Server でのネットワーク サブネットの管理

Skype for Business Server コントロールパネルまたは Skype for Business Server 管理シェルを使って、ネットワークサブネットを管理することができます。 通話受付制御 (CAC) が実装されている Skype for Business Server の大半の展開では、通常、多数のサブネットが存在します。 このため、多くの場合、Skype for Business Server 管理シェルからサブネットを構成することをお勧めします。

この記事のセクションを使用して、ネットワークサブネット情報の表示、またはネットワークサブネットの作成、変更、または削除を行います。 

## <a name="view-network-subnet-information"></a>ネットワークサブネット情報を表示する 

次の手順を使用して、ネットワークサブネットを表示できます。 Skype for Business Server コントロールパネルから、ネットワークサブネットの作成、変更、または削除を行うことができます。 

### <a name="to-view-a-network-subnet"></a>ネットワークサブネットを表示するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 

3.  左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**サブネット**] をクリックします。

4.  [ **Subnet** ] ページで、表示するサブネットをクリックします。
 
    > [!NOTE]  
    > 一度に1つのサブネットしか表示できません。

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してネットワークサブネット構成情報を表示する

ネットワークサブネットの情報を表示するには、Windows PowerShell を使用するか、または CsNetworkSubnet コマンドレットを使用します。 このコマンドレットは、Skype for Business Server 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 

### <a name="to-view-network-subnet-information"></a>ネットワークサブネット情報を表示するには

  - すべてのネットワークサブネットに関する情報を表示するには、Skype for Business Server 管理シェルで次のコマンドを入力して、enter キーを押します。
    
        Get-CsNetworkSubnet
    
    次のような情報が表示されます。
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0


詳細については、「 [CsNetworkSubnet の取得](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)」コマンドレットのヘルプトピックを参照してください。


## <a name="create-or-modify-network-subnets"></a>ネットワークサブネットを作成または変更する 

ネットワークサブネットは、このサブネットに属しているホストの地理的な場所を判断するために、ネットワークサイトと関連付けられている必要があります。 Skype for Business Server コントロールパネルを使用して、サブネットを構成することができます。 Skype for Business Server コントロールパネルから、ネットワークサブネットの作成、変更、または削除を行うことができます。 

通話受付制御 (CAC) が実装されている Skype for Business Server の大半の展開では、通常、多数のサブネットが存在します。 このため、多くの場合、Skype for Business Server 管理シェルからサブネットを構成することをお勧めします。 そこから、Windows PowerShell コマンドレットの**Import-CSV**と組み合わせて、**新しい csnetworksubnet**を呼び出すことができます。 これらのコマンドレットを一緒に使用することで、サブネットの設定をコンマ区切り値 (.csv) ファイルから読み取り、複数のサブネットを同時に作成することができます。 .Csv ファイルからサブネットを作成する方法の例については、「[新しい-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)」を参照してください。


### <a name="to-create-a-network-subnet"></a>ネットワークサブネットを作成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 

3.  左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**サブネット**] をクリックします。

4.  [**サブネット**] ページで、[**新規**] をクリックします。

5.  [**新しいサブネット**] で、[**サブネット ID** ] フィールドに値を入力します。 これは IP アドレス (たとえば、174.11.12.0) である必要があり、サブネットで定義された IP アドレス範囲の最初のアドレスである必要があります。

6.  [**マスク**] フィールドに、1 ~ 32 の数値を入力します。

    > [!NOTE]  
    > この値は、作成されるサブネットに適用されるビットマスクです。

7.  [**ネットワークサイト ID**] で、このサブネットが所属するサイトを選びます。

8.  省略[**説明**] フィールドに値を入力して、このサブネットについて、名前だけでは表現できない詳細情報を入力します。

9.  [**コミット**] をクリックします。


### <a name="to-modify-a-network-subnet"></a>ネットワークサブネットを変更するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 

3.  左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**サブネット**] をクリックします。

4.  [ **Subnet** ] ページで、変更するサブネットをクリックします。

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。

6.  [**サブネットの編集**] ページでは、ビットマスク、関連付けられたネットワークサイト、または説明を変更できます。 ビットマスクを変更する場合は、サブネット ID が、サブネットで定義されている IP アドレス範囲の最初のアドレスである必要があることに注意してください。

7.  [**コミット**] をクリックします。

## <a name="delete-network-subnets"></a>ネットワークサブネットを削除する

次の手順を使用して、サブネットを削除することができます。 Skype for Business Server コントロールパネルから、ネットワークサブネットの作成、変更、または削除を行うことができます。 

通話受付制御 (CAC) が実装されている Skype for Business Server の大半の展開では、通常、多数のサブネットが存在します。 このため、多くの場合、Skype for Business Server 管理シェルからサブネットを構成することをお勧めします。 そこから、Windows PowerShell コマンドレットの**Import-CSV**と組み合わせて、**新しい csnetworksubnet**を呼び出すことができます。 これらのコマンドレットを一緒に使用することで、サブネットの設定をコンマ区切り値 (.csv) ファイルから読み取り、複数のサブネットを同時に作成することができます。 .Csv ファイルからサブネットを作成する方法の例については、「[新しい-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)」を参照してください。


### <a name="to-delete-a-network-subnet"></a>ネットワークサブネットを削除するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 

3.  左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**サブネット**] をクリックします。

4.  [ **Subnet** ] ページで、削除するサブネットをクリックします。
 
    > [!NOTE]  
    > 一度に複数のサブネットを削除することができます。 これを行うには、ctrl キーを押しながら、CTRL キーを押しながら複数のサブネットを選択します。 または、すべてのサブネットを選択するには、[**編集**] メニューの [**すべて選択**] をクリックします。

5.  [**編集**] メニューの [**削除**] をクリックします。

6.  **[OK]** をクリックします。


## <a name="see-also"></a>関連項目

[新しい-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  

[Set-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  

[CsNetworkSubnet の削除](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  

[Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
