---
title: ネットワーク サブネットの管理
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
description: 通話受付管理 (CAC) が実装されている Skype for Business Server のほとんどの展開では、通常、多数のサブネットがあります。 このため、多くの場合、Skype for Business Server 管理シェルからサブネットを構成する方が最適です。
ms.openlocfilehash: ef771ad78f00085374038203e1049790a9179e88
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122441"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a>Skype for Business Server でのネットワーク サブネットの管理

Skype for Business Server コントロール パネルまたは Skype for Business Server 管理シェルのいずれかを使用して、ネットワーク サブネットを管理できます。 通話受付管理 (CAC) が実装されている Skype for Business Server のほとんどの展開では、通常、多数のサブネットがあります。 このため、多くの場合、Skype for Business Server 管理シェルからサブネットを構成する方が最適です。

この記事のセクションを使用して、ネットワーク サブネット情報を表示するか、ネットワーク サブネットを作成、変更、または削除します。 

## <a name="view-network-subnet-information"></a>ネットワーク サブネット情報の表示 

次の手順を使用して、ネットワーク サブネットを表示できます。 Skype for Business Server コントロール パネルから、ネットワーク サブネットを作成、変更、または削除できます。 

### <a name="to-view-a-network-subnet"></a>ネットワーク サブネットを表示するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。 

3.  左側のナビゲーション バーで、[ネットワーク構成] **をクリックし**、[サブネット] を **クリックします**。

4.  [**サブネット**] ページで、表示するサブネットをクリックします。
 
    > [!NOTE]  
    > 一度に表示できるのは 1 つのサブネットのみです。

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a>ネットワーク サブネット構成情報を表示するには、コマンドレットを使用Windows PowerShellします。

ネットワーク サブネットの情報は、ネットワーク と Windows PowerShellコマンドレットをGet-CsNetworkSubnetできます。 このコマンドレットは、Skype for Business Server 管理シェルから、またはサーバーのリモート セッションから実行Windows PowerShell。 

### <a name="to-view-network-subnet-information"></a>ネットワーク サブネット情報を表示するには

  - すべてのネットワーク サブネットに関する情報を表示するには、Skype for Business Server 管理シェルに次のコマンドを入力し、Enter キーを押します。
    
        Get-CsNetworkSubnet
    
    次のような情報が表示されます。
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0


詳細については、[Get-CsNetworkSubnet](/powershell/module/skype/Get-CsNetworkSubnet) コマンドレットのヘルプ トピックを参照してください。


## <a name="create-or-modify-network-subnets"></a>ネットワーク サブネットの作成または変更 

ネットワーク サブネットは、そのサブネットに所属するホストの地理的な場所を指定するために、ネットワーク サイトに関連付ける必要があります。 Skype for Business Server コントロール パネルを使用してサブネットを構成できます。 Skype for Business Server コントロール パネルから、ネットワーク サブネットを作成、変更、または削除できます。 

通話受付管理 (CAC) が実装されている Skype for Business Server のほとんどの展開では、通常、多数のサブネットがあります。 このため、多くの場合、Skype for Business Server 管理シェルからサブネットを構成する方が最適です。 そこから **New-CsNetworkSubnet** を呼び出し、Windows PowerShell **Import-CSV コマンドレットと組み合わせて呼び出すことができます**。 これらのコマンドレットを使用すると、コンマ区切り値 (.csv) ファイルからサブネット設定を読み込み、同時に複数のサブネットを作成することができます。 csv ファイルからサブネットを作成する方法の例については、「[New-CsNetworkSubnet](/powershell/module/skype/New-CsNetworkSubnet)」を参照してください。


### <a name="to-create-a-network-subnet"></a>ネットワーク サブネットを作成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。 

3.  左側のナビゲーション バーで、[ネットワーク構成] **をクリックし**、[サブネット] を **クリックします**。

4.  [**サブネット**] ページで、[**新規**] をクリックします。

5.  [**新しいサブネット**] で、[**サブネット ID**] フィールドに値を入力します。 これは、IP アドレス (174.11.12.0 など) である必要があります。また、サブネットで定義される IP アドレス範囲の最初のアドレスである必要があります。

6.  [**マスク**] フィールドで、1 ～ 32 の数値を入力します。

    > [!NOTE]  
    > この値は、作成するサブネットに適用するビットマスクです。

7.  [**ネットワーク サイト ID**] で、このサブネットが所属するサイトを選択します。

8.  (オプション) [**説明**] フィールドに値を入力して、名前だけでは表現することのできないこのサブネットの詳細情報を提供します。

9.  [**確定**] をクリックします。


### <a name="to-modify-a-network-subnet"></a>ネットワーク サブネットを変更するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。 

3.  左側のナビゲーション バーで、[ネットワーク構成] **をクリックし**、[サブネット] を **クリックします**。

4.  [**サブネット**] ページで、変更するサブネットをクリックします。

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。

6.  [**サブネットの編集**] ページでは、ビットマスク、関連付けられたネットワーク サイト、または説明を変更できます。 ビットマスクを変更する場合は、変更後もサブネット ID がサブネットで定義される IP アドレス範囲の最初のアドレスでなければならないことに注意してください。

7.  [**確定**] をクリックします。

## <a name="delete-network-subnets"></a>ネットワーク サブネットの削除

次の手順を使用して、サブネットを削除できます。 Skype for Business Server コントロール パネルから、ネットワーク サブネットを作成、変更、または削除できます。 

通話受付管理 (CAC) が実装されている Skype for Business Server のほとんどの展開では、通常、多数のサブネットがあります。 このため、多くの場合、Skype for Business Server 管理シェルからサブネットを構成する方が最適です。 そこから **New-CsNetworkSubnet** を呼び出し、Windows PowerShell **Import-CSV コマンドレットと組み合わせて呼び出すことができます**。 これらのコマンドレットを使用すると、コンマ区切り値 (.csv) ファイルからサブネット設定を読み込み、同時に複数のサブネットを作成することができます。 .csv ファイルからサブネットを作成する方法の例は、「[New-CsNetworkSubnet](/powershell/module/skype/New-CsNetworkSubnet)」を参照してください。


### <a name="to-delete-a-network-subnet"></a>ネットワーク サブネットを削除するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。 

3.  左側のナビゲーション バーで、[ネットワーク構成] **をクリックし**、[サブネット] を **クリックします**。

4.  [**サブネット**] ページで、削除するサブネットをクリックします。
 
    > [!NOTE]  
    > 1 つ以上のサブネットを一度に削除できます。これを実行するには、Ctrl キーを押しながら、複数のサブネットを選択します。または、すべてのサブネットを選択するには、[**編集**] メニューの [**すべて選択**] をクリックします。

5.  [**編集**] メニューの [**削除**] をクリックします。

6.  [**OK**] をクリックします。


## <a name="see-also"></a>関連項目

[New-CsNetworkSubnet](/powershell/module/skype/New-CsNetworkSubnet)  

[Set-CsNetworkSubnet](/powershell/module/skype/Set-CsNetworkSubnet)  

[Remove-CsNetworkSubnet](/powershell/module/skype/Remove-CsNetworkSubnet)  

[Get-CsNetworkSubnet](/powershell/module/skype/Get-CsNetworkSubnet)