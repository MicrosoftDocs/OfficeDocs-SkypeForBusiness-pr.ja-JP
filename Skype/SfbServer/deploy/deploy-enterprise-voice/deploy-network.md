---
title: Skype for Business でネットワークのリージョン、サイト、サブネットを展開する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
description: Skype for Business Server のネットワーク領域、ネットワークサイト、ネットワークサブネットの関連付けを作成または変更します。 これらはすべて、高度なエンタープライズ Voip 機能 (メディアバイパス、通話受付制御、位置ベースのルーティング) に使用されます。
ms.openlocfilehash: 3ce0f4dcf011f57e25c4741c34135bc4ba62085a
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221484"
---
# <a name="deploy-network-regions-sites-and-subnets-in-skype-for-business"></a>Skype for Business でネットワークのリージョン、サイト、サブネットを展開する

Skype for Business Server のネットワーク領域、ネットワークサイト、ネットワークサブネットの関連付けを作成または変更します。 これらはすべて、高度なエンタープライズ Voip 機能 (メディアバイパス、通話受付制御、位置ベースのルーティング) に使用されます。

高度なエンタープライズ Voip 機能には、[通話受付制御](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)、[メディアのバイパス](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)、[位置情報に基づくルーティング](../../plan-your-deployment/enterprise-voice-solution/location-based-routing.md)、E9-1 [-](../../plan-your-deployment/enterprise-voice-solution/emergency-services.md)1 があります。 これらの各機能を使用するには、ネットワーク地域、ネットワーク サイト、サブネットを作成する必要があります。 たとえば、これらの各機能では、トポロジ内にある各サブネットを特定のネットワーク サイトに関連付け、各ネットワーク サイトをネットワーク地域に関連付ける必要があります。 これらの用語の詳細については、「 [Skype For Business Server の高度なエンタープライズ voip 機能のネットワーク設定](../../plan-your-deployment/enterprise-voice-solution/network-settings-for-advanced-features.md)」を参照してください。

通話受付管理および E9-1-1 には、ネットワーク サイトの追加構成要件があります。

- 通話受付管理では、WAN の帯域幅が制限されているサイトごとに帯域幅ポリシー プロファイルを指定する必要があります。 通話受付制御の展開を計画している場合は、ネットワークサイトを構成する前に、 [Skype For Business Server で帯域幅ポリシープロファイルを作成](create-bandwidth-policy-profiles.md)する必要があります。

- E9-1-1 では、サイトごとに 場所のポリシーを指定する必要があります。 E9 の展開を計画している場合は、ネットワークサイトを構成する前に、 [Skype For Business Server で位置情報ポリシーを作成](create-location-policies.md)する必要があります。

## <a name="create-or-modify-a-network-region"></a>ネットワーク地域の作成または変更

これらの機能のいずれかに対して既にネットワークの領域を作成している場合は、新しいネットワークの領域を作成する必要はありません。その他の高度なエンタープライズ Voip 機能でも、同じネットワーク領域が使用されます。

ただし、機能固有の設定を適用するために、ネットワーク地域に関する既存の定義に変更を加える必要が生じることがあります。たとえば、E9-1-1 用のネットワーク地域を作成し (この場合は関連付けられた中央サイトは必要ありません)、次に通話受付管理を展開する場合は、中央サイトを指定するためにネットワーク地域の定義を変更する必要があります。

### <a name="to-create-a-network-region-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用してネットワークの領域を作成するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。

2. New-CsNetworkRegion コマンドレットを実行してネットワーク地域を作成します。

   ```
   New-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    次に例を示します。

   ```
   New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
   ```

    この例では、サイト ID がシカゴのセントラルサイトに関連付けられた "NorthAmerica" というネットワーク領域を作成しました。

3. トポロジでのネットワーク地域の作成を完了するには、ネットワーク地域ごとの設定値を使用してステップ 2 を繰り返します。

### <a name="to-create-a-network-region-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロールパネルを使用してネットワークの領域を作成するには

1. Skype for Business Server コントロールパネルを開きます。

2. 左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。

3. [**地域**] をクリックします。

4. [**新規**] をクリックします。

5. [**新しい地域**] ページで、[**名前**] をクリックしてネットワーク地域の名前を入力します。

6. [**中央サイト**] をクリックし、リストにある中央サイトを 1 つクリックします。

7. オプションで、[**説明**] をクリックして、このネットワーク サイトを説明する追加情報を入力します。

8. [**確定**] をクリックします。

9. トポロジでのネットワーク地域の作成を完了するには、その他の地域の設定値を使用してステップ 4 ～ 8 を繰り返します。

### <a name="to-modify-a-network-region-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用してネットワークの地域を変更するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。

2. Set-CsNetworkRegion コマンドレットを実行して、既存のネットワーク地域を変更します。

   ```
   Set-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    次に例を示します。

   ```
   Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
   ```

    この例では、説明を変更することで、"NorthAmerica" という既存のネットワーク領域 (前述の手順を使用して作成) を変更しました。 "NorthAmerica" 領域の説明が存在する場合、このコマンドによってこの値が上書きされます。説明が設定されていない場合は、このコマンドによって設定されます。

3. その他のネットワーク地域を変更するには、その他の地域の設定値を使用してステップ 2 を繰り返します。

### <a name="to-modify-a-network-region-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロールパネルを使用してネットワークの地域を変更するには

1. Skype for Business Server コントロールパネルを開きます。

2. 左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。

3. [**地域**] ナビゲーション ボタンをクリックします。

4. 表で、変更するネットワーク地域をクリックします。

5. [**編集**] をクリックして、[**詳細の表示...**] をクリックします。

6. [**領域の編集**] ページで、必要に応じて、このネットワーク領域の設定の値を変更します。

7. [**コミット**] をクリックします。

8. ネットワーク地域の変更を完了するには、他の地域の設定値を使用してステップ 4 ～ 7 を繰り返します。

## <a name="create-or-modify-a-network-site"></a>ネットワーク サイトの作成または変更

これらの機能のいずれかに対して既にネットワークサイトを作成している場合は、新しいネットワークサイトを作成する必要はありません。その他の高度なエンタープライズ Voip 機能でも、同じネットワークサイトが使用されます。 ただし、機能固有の設定を適用するには、既存のネットワークサイト定義を変更する必要がある場合があります。 たとえば、E9 のネットワークサイトを作成した場合、通話受付制御の展開中にネットワークサイトを変更して、帯域幅ポリシープロファイルを適用する必要があります。

### <a name="to-create-a-network-site-by-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用してネットワークサイトを作成するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。

2. New-CsNetworkSite コマンドレットを実行して、ネットワーク サイトを作成します。

   ```
   New-CsNetworkSite -NetworkSiteID <string>
   ```

    次に例を示します。

   ```
   New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
   ```

    この例では、"NorthAmerica" ネットワーク領域内に "シカゴ" というネットワークサイトを作成しました。

    > [!NOTE]
    > このコマンドを正常に実行するには、NorthAmerica ネットワーク地域があらかじめ存在する必要があります。

3. トポロジのネットワーク サイトを作成するには、他のサイトの設定値を使用してステップ 2 を繰り返します。

### <a name="to-create-a-network-site-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロールパネルを使用してネットワークサイトを作成するには

1. Skype for Business Server コントロールパネルを開きます。

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

11. 使用しているトポロジのネットワーク サイトの作成を完了するには、他のサイトの設定値を使用してステップ 4 ～ 10 を繰り返します。

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用してネットワークサイトを変更するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。

2. Set-CsNetworkSite コマンドレットを実行して、ネットワーク サイトを変更します。

   ```
   Set-CsNetworkSite -Identity <string>
   ```

    例:

   ```
   Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
   ```

    この例では、"アルバカーキ" という名前のサイトが "NorthAmerica" ネットワークの領域に移動されます。 ネットワーク サイトの構成を変更して、通話受付管理、E9-1-1、またはメディア バイパスを展開するには、Set-CsNetworkSite コマンドレットをそれぞれ BWPolicyProfileID または LocationPolicy パラメーターと組み合わせて実行し、ネットワーク サイトの設定を変更します。

    > [!NOTE]
    > メディア バイパス用に BypassID パラメーターが用意されていますが、自動生成されるバイパス ID を上書きしないことを強くお勧めします。 メディア バイパス用にネットワーク サイトを構成するために、追加パラメーターを指定する必要はありません。

3. 使用しているトポロジのネットワーク サイトの変更を完了するには、他のサイトの設定値を使用してステップ 2 を繰り返します。

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロールパネルを使用してネットワークサイトを変更するには

1. Skype for Business Server コントロールパネルを開きます。

2. 左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。

3. [**サイト**] ナビゲーション ボタンをクリックします。

4. 表内で、変更するネットワーク サイトをクリックします。

5. [**編集**] をクリックして、[**詳細の表示...**] をクリックします。

6. [**サイトの編集**] ページで、必要に応じて、このネットワークサイトの設定の値を変更します。

7. [**確定**] をクリックします。

8. ネットワーク サイトの変更を完了するには、他のサイトの設定値を使用してステップ 4 ～ 7 を繰り返します。

## <a name="associate-a-subnet-with-a-network-site"></a>ネットワーク サイトとサブネットの関連付け
<a name="BKMK_AssociateSubnets"> </a>

ネットワーク内のすべてのサブネットは、新しいセッションが開始されている間、エンドポイントが配置されているネットワークサイトを特定するために使用されるため、サブネット情報が特定のネットワークサイトと関連付けられている必要があります。 セッションの各パーティの場所がわかっている場合は、高度なエンタープライズ音声機能を使用して、通話の設定またはルーティングを処理する方法を決定するためにその情報を適用することができます。

展開内の音声ビデオ エッジ サーバーの構成済みパブリック IP アドレスはすべて、ネットワーク構成設定に追加する必要があります。 これらの IP アドレスは、マスク値 32 のサブネットとして追加されます。 関連付けられたネットワーク サイトは、適切な構成済みネットワーク サイトに対応する必要があります。 たとえば、セントラルサイトシカゴの A/V エッジサービスに対応するパブリック IP アドレスは、NetworkSiteID シカゴになります。

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用してサブネットをネットワークサイトに関連付けるには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。

2. **New-CsNetworkSubnet** コマンドレットを実行して、サブネットをネットワーク サイトに関連付けます。

   ```
   New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
   ```

    次に例を示します。

   ```
   New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
   ```

    この例では、サブネット172.11.12.13 とネットワークサイト "シカゴ" の間の関連付けを作成しました。

3. トポロジのすべてのサブネットに対して、ステップ 2 を繰り返します。

### <a name="to-associate-subnets-with-network-sites-by-importing-a-csv-file"></a>CSV ファイルをインポートしてサブネットをネットワーク サイトに関連付けるには

1. 追加する予定の、すべてのサブネットが含まれた CSV ファイルを作成します。たとえば、次の内容が含まれる、**subnet.csv** という名前のファイルを作成します。

     `IPAddress, mask, description, NetworkSiteID`

     `172.11.12.0, 24, "NA:Subnet in Portland", Portland`

     `172.11.13.0, 24, "NA:Subnet in Reno", Reno`

     `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`

     `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。

3. 次のコマンドレットを実行して、**サブネット .csv**をインポートし、その内容を Lync Server 管理ストアに保存します。

   ```
   import-csv subnet.csv | foreach {New-CsNetworkSubnet -Identity $_.IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}
   ```

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロールパネルを使用してサブネットをネットワークサイトに関連付けるには

1. Skype for Business Server コントロールパネルを開きます。

2. 左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。

3. [**サブネット**] ナビゲーション ボタンをクリックします。

4. [**新規**] をクリックします。

5. [**新しいサブネット**] ページで、[**サブネット ID**] をクリックし、ネットワーク サイトに関連付けるサブネットで定義される IP アドレス範囲の最初のアドレスを入力します。

6. [**マスク**] をクリックし、サブネットに適用するビットマスクを入力します。

7. [**ネットワーク サイト ID**] をクリックし、このサブネットの追加先となるサイトのサイト ID を選択します。

    > [!NOTE]
    > ネットワーク サイトがまだ作成されていない場合、この一覧は空です。 手順の詳細については、「[Create or Modify a Network Site](https://technet.microsoft.com/library/14e24856-9996-4da4-9f31-300940bdf5aa.aspx)」を参照してください。 また、**Get-CsNetworkSite** コマンドレットを実行して、展開のサイト ID を取得することもできます。 詳細については、「Skype for Business Server 管理シェルのドキュメント」を参照してください。

8. オプションで、[**説明**] をクリックし、このサブネットを説明する追加情報を入力します。

9. [**確定**] をクリックします。

これらのステップを繰り返して、その他のサブネットをネットワーク サイトに追加します。
> [!NOTE]
> ネットワークに存在するが、サブネットに関連付けられていない、または IP アドレスを含むサブネットがネットワークサイトに関連付けられていない IP アドレスのリストを指定して、キー正常性インジケータ (KHI) アラートが発生します。 このアラートは8時間以内に複数回発生することはありません。

関連する通知情報と例を以下に示します。

 **ソース**: CS 帯域幅ポリシー サービス (コア)

 **イベント番号**: 36034

 **レベル**: 2

 **説明**: 次の ip アドレスのサブネット: \<ip アドレス\>の一覧が構成されていないか、サブネットがネットワークサイトに関連付けられていません。

 **原因**: 対応する IP アドレスのサブネットがネットワーク構成設定にないか、サブネットがネットワーク サイトに関連付けられていません。

 **解決方法**: IP アドレス リストに対応するサブネットをネットワーク構成設定に追加し、すべてのサブネットをネットワーク サイトに関連付けます。

たとえば、通知に表示された IP アドレス リストが 10.121.248.226 および 10.121.249.20 であった場合、これらの IP アドレスがサブネットに関連付けられていないか、または関連付けられているサブネットがネットワーク サイトに属していないかのどちらかになります。10.121.248.0/24 および 10.121.249.0/24 がこれらのアドレスに対応するサブネットである場合、次の手順でこの問題を解決することができます。

1. IP アドレス 10.121.248.226 が 10.121.248.0/24 サブネットに関連付けられていること、および IP アドレス 10.121.249.20 が 10.121.249.0/24 サブネットに関連付けられていることを確認します。

2. 10.121.248.0/24 および 10.121.249.0/24 サブネットがそれぞれネットワーク サイトに関連付けられていることを確認します。

## <a name="see-also"></a>関連項目
<a name="BKMK_AssociateSubnets"> </a>


[新しい CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregion?view=skype-ps)

[Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregion?view=skype-ps)

[Set-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregion?view=skype-ps)

[CsNetworkRegion の削除](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregion?view=skype-ps)

[新しい-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-csnetworksubnet?view=skype-ps)

[Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/get-csnetworksubnet?view=skype-ps)

[Set-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/set-csnetworksubnet?view=skype-ps)

[CsNetworkSubnet の削除](https://docs.microsoft.com/powershell/module/skype/remove-csnetworksubnet?view=skype-ps)

