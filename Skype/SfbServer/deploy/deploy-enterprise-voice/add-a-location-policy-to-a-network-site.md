---
title: Skype for Business Server のネットワークサイトに位置情報ポリシーを追加する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: E9-1 の場所のポリシーを Skype for Business Server Enterprise Voice のネットワークサイトに割り当てます。
ms.openlocfilehash: ef6395b2239256abce82612b4863a667ce3b27ab
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768280"
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server"></a>Skype for Business Server のネットワークサイトに位置情報ポリシーを追加する
 
E9-1 の場所のポリシーを Skype for Business Server Enterprise Voice のネットワークサイトに割り当てます。 
  
次の例は、 [Skype For Business Server の [場所ポリシーの作成](create-location-policies.md)] で定義されている**redmond**の場所ポリシーを既存のネットワークサイトに追加する方法と、 **redmond**の場所ポリシーを使用する新しいネットワークサイトを作成する方法を示しています。
  
ネットワークサイトの操作の詳細については、次のコマンドレットの Lync Server 管理シェルに関するドキュメントを参照してください。
  
- **新しい-CsNetworkSite**
    
- **Get-CsNetworkSite**
    
- **Set-CsNetworkSite**
    
- **CsNetworkSite の削除**
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a>場所のポリシーを既存のネットワーク サイトに割り当てるには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
2. 既存のネットワーク サイトを変更するには、以下のコマンドレットを実行します。
    
    **Redmond** とマークされている場所のポリシーを、**Redmond** という名前の既存のネットワーク サイトに割り当てます。
    
   ```powershell
   Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a>場所のポリシーを新しいネットワーク サイトに割り当てるには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
2. 新しいネットワーク サイトを作成するには、以下のコマンドレットを実行します。
    
    ネットワーク地域の新しいネットワーク サイトを作成して、**Redmond** とマークされた場所のポリシーを割り当てます。
    
   ```powershell
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


