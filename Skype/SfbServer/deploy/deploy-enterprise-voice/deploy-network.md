---
title: Skype for Business でネットワーク地域、サイト、サブネットを展開する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
description: Skype for Business Server でネットワーク領域、ネットワーク サイト、および関連付けネットワーク サブネットを作成または変更します。 これらはすべて、メディア バイパス、通話受付管理、場所ベースのルーティングエンタープライズ VoIP高度な機能に使用されます。
ms.openlocfilehash: adfcf418fd2b1ef607947687afb766fee6b64715
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103523"
---
# <a name="deploy-network-regions-sites-and-subnets-in-skype-for-business"></a>Skype for Business でネットワーク地域、サイト、サブネットを展開する

Skype for Business Server でネットワーク領域、ネットワーク サイト、および関連付けネットワーク サブネットを作成または変更します。 これらはすべて、メディア バイパス、通話受付管理、場所ベースのルーティングエンタープライズ VoIP高度な機能に使用されます。

高度なエンタープライズ VoIP機能は、 [通話受付制御](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)、 [メディア](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)バイパス、 [場所](../../plan-your-deployment/enterprise-voice-solution/location-based-routing.md)ベースのルーティング、 [および E9-1-1 です](../../plan-your-deployment/enterprise-voice-solution/emergency-services.md)。 これらの機能はすべて、ネットワーク領域、ネットワーク サイト、サブネットを作成する必要があります。 たとえば、これらのすべての機能では、トポロジ内の各サブネットを特定のネットワーク サイトに関連付け、各ネットワーク サイトをネットワーク領域に関連付けなければならない必要があります。 これらの用語の詳細については、「Skype for Business Server の高度な機能 [エンタープライズ VoIPネットワーク設定」を参照してください](../../plan-your-deployment/enterprise-voice-solution/network-settings-for-advanced-features.md)。

通話受付管理および E9-1-1 には、ネットワーク サイトの追加構成要件があります。

- 通話受付管理では、WAN の帯域幅が制限されているサイトごとに帯域幅ポリシー プロファイルを指定する必要があります。 通話受付管理を展開する場合は、ネットワーク サイトを構成する前に [、Skype for Business Server](create-bandwidth-policy-profiles.md) で帯域幅ポリシー プロファイルを作成する必要があります。

- E9-1-1 では、サイトごとに場所のポリシーを指定する必要があります。 E9-1-1 を展開する場合は、ネットワーク サイトを構成する前に [、Skype for Business Server](create-location-policies.md) で場所ポリシーを作成する必要があります。

## <a name="create-or-modify-a-network-region"></a>ネットワーク地域を作成または変更する

これらの機能の 1 つについてネットワーク領域を既に作成している場合は、新しいネットワーク領域を作成する必要があります。その他の高度エンタープライズ VoIP機能は、同じネットワーク領域を使用します。

ただし、機能固有の設定を適用するために、既存のネットワーク地域定義を変更することが必要になる場合があります。 たとえば、E9-1-1 のネットワーク領域 (関連付けられたセントラル サイトを必要としない) を作成し、通話受付管理を展開する場合は、ネットワーク領域定義を変更して中央サイトを指定する必要があります。

### <a name="to-create-a-network-region-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用してネットワーク領域を作成するには

1. Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。

2. New-CsNetworkRegion コマンドレットを実行してネットワーク地域を作成します。

   ```powershell
   New-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    次にその例を示します。

   ```powershell
   New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
   ```

    この例では、サイト ID CHICAGO を持つ中央サイトに関連付けられた "NorthAmerica" というネットワーク領域を作成しました。

3. トポロジでのネットワーク地域の作成を完了するには、ネットワーク地域ごとの設定値を使用してステップ 2 を繰り返します。

### <a name="to-create-a-network-region-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネルを使用してネットワーク領域を作成するには

1. Skype for Business Server コントロール パネルを開きます。

2. 左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。

3. [**地域**] をクリックします。

4. [**新規**] をクリックします。

5. [**新しい地域**] ページで、[**名前**] をクリックしてネットワーク地域の名前を入力します。

6. [**中央サイト**] をクリックし、リストにある中央サイトを 1 つクリックします。

7. オプションで、[**説明**] をクリックして、このネットワーク サイトを説明する追加情報を入力します。

8. [**確定**] をクリックします。

9. トポロジでのネットワーク地域の作成を完了するには、その他の地域の設定値を使用してステップ 4 ～ 8 を繰り返します。

### <a name="to-modify-a-network-region-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用してネットワーク地域を変更するには

1. Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。

2. Set-CsNetworkRegion コマンドレットを実行して、既存のネットワーク地域を変更します。

   ```powershell
   Set-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    次にその例を示します。

   ```powershell
   Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
   ```

    この例では、説明を変更して、"NorthAmerica" という既存のネットワーク領域 (このトピックの前の手順を使用して作成) を変更しました。 "NorthAmerica" 領域の説明が存在する場合、このコマンドは、この値で上書きします。説明が設定されていない場合は、このコマンドによって設定されます。

3. その他のネットワーク地域を変更するには、その他の地域の設定値を使用してステップ 2 を繰り返します。

### <a name="to-modify-a-network-region-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネルを使用してネットワーク地域を変更するには

1. Skype for Business Server コントロール パネルを開きます。

2. 左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。

3. [**地域**] ナビゲーション ボタンをクリックします。

4. 表で、変更するネットワーク地域をクリックします。

5. [**編集**] をクリックして、[**詳細の表示...**] をクリックします。

6. [地域 **の編集] ページ** で、このネットワーク地域の設定の値を必要に応じて変更します。

7. [**確定**] をクリックします。

8. ネットワーク地域の変更を完了するには、他の地域の設定値を使用してステップ 4 ～ 7 を繰り返します。

## <a name="create-or-modify-a-network-site"></a>ネットワーク サイトを作成または変更する

これらの機能の 1 つのネットワーク サイトを既に作成している場合は、新しいネットワーク サイトを作成する必要があります。その他の高度エンタープライズ VoIP機能は、同じネットワーク サイトを使用します。 ただし、機能固有の設定を適用するには、既存のネットワーク サイト定義を変更する必要があります。 たとえば、E9-1-1 のネットワーク サイトを作成した場合は、通話受付管理の展開中にネットワーク サイトを変更して帯域幅ポリシー プロファイルを適用する必要があります。

### <a name="to-create-a-network-site-by-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用してネットワーク サイトを作成するには

1. Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。

2. New-CsNetworkSite コマンドレットを実行して、ネットワーク サイトを作成します。

   ```powershell
   New-CsNetworkSite -NetworkSiteID <string>
   ```

    次にその例を示します。

   ```powershell
   New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
   ```

    この例では、"NorthAmerica" ネットワーク領域にある "Chicago" というネットワーク サイトを作成しました。

    > [!NOTE]
    > このコマンドを正常に実行するには、NorthAmerica ネットワーク地域があらかじめ存在する必要があります。

3. トポロジのネットワーク サイトを作成するには、他のサイトの設定に関してステップ 2 を繰り返します。

### <a name="to-create-a-network-site-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネルを使用してネットワーク サイトを作成するには

1. Skype for Business Server コントロール パネルを開きます。

2. 左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。

3. [**サイト**] ナビゲーション ボタンをクリックします。

4. [**新規**] をクリックします。

5. [**新しいサイト**] ページで、[**名前**] をクリックしてネットワーク サイトの名前を入力します。

6. [**地域**] をクリックして、リストで地域をクリックします。

7. オプションで、[**帯域幅ポリシー**] をクリックして、リストで帯域幅ポリシーをクリックします。

    > [!NOTE]
    > 帯域幅ポリシーが必要なのは、サイトで通話受付管理を展開する場合だけです。

8. オプションで、[**場所のポリシー**] をクリックして、リストで場所のポリシーをクリックします。

    > [!NOTE]
    > 場所のポリシーが必要なのは、サイトで E9-1-1 を展開する場合だけです。

9. オプションで、[**説明**] をクリックして、このネットワーク サイトを説明する追加情報を入力します。

10. [**確定**] をクリックします。

11. 他のサイトについての設定に関してステップ 4 ～ 10 を繰り返し、ご使用のトポロジのネットワーク サイトの作成を完了します。

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用してネットワーク サイトを変更するには

1. Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。

2. Set-CsNetworkSite コマンドレットを実行して、ネットワーク サイトを変更します。

   ```powershell
   Set-CsNetworkSite -Identity <string>
   ```

    次にその例を示します。

   ```powershell
   Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
   ```

    この例では、"Albuquerque" と呼ばれるサイトが "NorthAmerica" ネットワーク領域に移動されます。 ネットワーク サイトの構成を変更して、通話受付管理、E9-1-1、またはメディア バイパスを展開するには、Set-CsNetworkSite コマンドレットをそれぞれ BWPolicyProfileID または LocationPolicy パラメーターと組み合わせて実行し、ネットワーク サイトの設定を変更します。

    > [!NOTE]
    > メディア バイパス用に BypassID パラメーターが用意されていますが、自動生成されるバイパス ID を無効にしないことを強くお勧めします。 メディア バイパス用にネットワーク サイトを構成するために、追加パラメーターを指定する必要はありません。

3. 他のサイトについての設定に関してステップ 2 を繰り返し、ご使用のトポロジのネットワーク サイトの変更を完了します。

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネルを使用してネットワーク サイトを変更するには

1. Skype for Business Server コントロール パネルを開きます。

2. 左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。

3. [**サイト**] ナビゲーション ボタンをクリックします。

4. 表内で、変更するネットワーク サイトをクリックします。

5. [**編集**] をクリックして、[**詳細の表示...**] をクリックします。

6. [サイト **の編集] ページ** で、このネットワーク サイトの設定の値を必要に応じて変更します。

7. [**確定**] をクリックします。

8. 他のサイトについての設定に関してステップ 4 ～ 7 を繰り返し、ネットワーク サイトの変更を完了します。

## <a name="associate-a-subnet-with-a-network-site"></a>サブネットをネットワーク サイトに関連付ける
<a name="BKMK_AssociateSubnets"> </a>

新しいセッションの開始中にエンドポイントが位置するネットワーク サイトを決定するためにサブネット情報が使用されるので、ネットワーク内のすべてのサブネットは、特定のネットワーク サイトに関連付けられている必要があります。 セッション内の各パーティの場所が分かっている場合は、高度なエンタープライズ VoIP機能を使用して、通話のセットアップまたはルーティングを処理する方法を決定できます。

展開内の音声ビデオ エッジ サーバーの構成済みパブリック IP アドレスはすべて、ネットワーク構成設定に追加する必要があります。 これらの IP アドレスは、マスク値 32 のサブネットとして追加されます。 関連付けられたネットワーク サイトは、適切な構成済みネットワーク サイトに対応する必要があります。 たとえば、中央サイトシカゴの A/V Edge サービスに対応するパブリック IP アドレスは、NetworkSiteID Chicago です。

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用してサブネットをネットワーク サイトに関連付けるには

1. Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。

2. **New-CsNetworkSubnet** コマンドレットを実行して、サブネットをネットワーク サイトに関連付けます。

   ```powershell
   New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
   ```

    例:

   ```powershell
   New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
   ```

    この例では、サブネット 172.11.12.13 とネットワーク サイト "シカゴ" の間に関連付けを作成しました。

3. トポロジのすべてのサブネットに対して、ステップ 2 を繰り返します。

### <a name="to-associate-subnets-with-network-sites-by-importing-a-csv-file"></a>CSV ファイルをインポートしてサブネットをネットワーク サイトに関連付けるには

1. 追加する予定の、すべてのサブネットが含まれた CSV ファイルを作成します。たとえば、次の内容が含まれる、**subnet.csv** という名前のファイルを作成します。

     `IPAddress, mask, description, NetworkSiteID`

     `172.11.12.0, 24, "NA:Subnet in Portland", Portland`

     `172.11.13.0, 24, "NA:Subnet in Reno", Reno`

     `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`

     `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2. Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。

3. 次のコマンドレットを実行して **、subnet.csv** をインポートし、その内容を Lync Server 管理ストアに格納します。

   ```powershell
   import-csv subnet.csv | foreach {New-CsNetworkSubnet -Identity $_.IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}
   ```

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネルを使用してサブネットをネットワーク サイトに関連付けるには

1. Skype for Business Server コントロール パネルを開きます。

2. 左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。

3. [**サブネット**] ナビゲーション ボタンをクリックします。

4. [**新規**] をクリックします。

5. [**新しいサブネット**] ページで、[**サブネット ID**] をクリックし、サブネットで定義される IP アドレス範囲の最初のアドレスを入力します。このサブネットは、ネットワーク サイトに関連付けるネットワークです。

6. [**マスク**] をクリックし、サブネットに適用するビットマスクを入力します。

7. [**ネットワーク サイト ID**] をクリックし、このサブネットを追加する先のサイトのサイト ID を選択します。

    > [!NOTE]
    > ネットワーク サイトがまだ作成されていない場合、この一覧は空です。 手順の詳細については、「[Create or Modify a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-network-site)」を参照してください。 また、**Get-CsNetworkSite** コマンドレットを実行して、展開のサイト ID を取得することもできます。 詳細については、Skype for Business Server 管理シェルのドキュメントを参照してください。

8. 必要に応じて、[**説明**] をクリックし、このサブネットを説明する追加情報を入力します。

9. [**確定**] をクリックします。

その他のサブネットをネットワーク サイトに追加するには、これらのステップを繰り返します。
> [!NOTE]
> キー正常性インジケーター (KHI) アラートが発生し、ネットワークに存在するがサブネットに関連付けされていない IP アドレスの一覧を指定するか、IP アドレスを含むサブネットがネットワーク サイトに関連付けされません。 このアラートは、8 時間以内に 2 回以上発生しません。

関連するアラート情報と例は次のとおりです。

 **ソース**: CS 帯域幅ポリシー サービス (コア)

 **イベント番号**: 36034

 **レベル**: 2

 **説明**: 次の IP アドレスのサブネットが構成されていないか、サブネットがネットワーク サイト \<List of IP Addresses\> に関連付けされていません。

 **原因**: 対応する IP アドレスのサブネットがネットワーク構成設定にないか、サブネットがネットワーク サイトに関連付けられていません。

 **解決方法**: IP アドレス リストに対応するサブネットをネットワーク構成設定に追加し、すべてのサブネットをネットワーク サイトに関連付けます。

たとえば、通知に表示された IP アドレス リストが 10.121.248.226 および 10.121.249.20 であった場合、これらの IP アドレスがサブネットに関連付けられていないか、または関連付けられているサブネットがネットワーク サイトに属していないかのどちらかになります。10.121.248.0/24 および 10.121.249.0/24 がこれらのアドレスに対応するサブネットである場合、次の手順でこの問題を解決することができます。

1. IP アドレス 10.121.248.226 が 10.121.248.0/24 サブネットに関連付けられていること、および IP アドレス 10.121.249.20 が 10.121.249.0/24 サブネットに関連付けられていることを確認します。

2. 10.121.248.0/24 および 10.121.249.0/24 サブネットがそれぞれネットワーク サイトに関連付けられていることを確認します。

## <a name="see-also"></a>関連項目
<a name="BKMK_AssociateSubnets"> </a>


[New-CsNetworkRegion](/powershell/module/skype/new-csnetworkregion?view=skype-ps)

[Get-CsNetworkRegion](/powershell/module/skype/get-csnetworkregion?view=skype-ps)

[Set-CsNetworkRegion](/powershell/module/skype/set-csnetworkregion?view=skype-ps)

[Remove-CsNetworkRegion](/powershell/module/skype/remove-csnetworkregion?view=skype-ps)

[New-CsNetworkSubnet](/powershell/module/skype/new-csnetworksubnet?view=skype-ps)

[Get-CsNetworkSubnet](/powershell/module/skype/get-csnetworksubnet?view=skype-ps)

[Set-CsNetworkSubnet](/powershell/module/skype/set-csnetworksubnet?view=skype-ps)

[Remove-CsNetworkSubnet](/powershell/module/skype/remove-csnetworksubnet?view=skype-ps)