---
title: Skype 内のネットワーク サイトにビジネス サーバーの場所のポリシーを追加します。
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: ビジネス サーバーのエンタープライズ VoIP の Skype のネットワーク サイトへの ~ 9-1-1 の場所のポリシーを割り当てます。
ms.openlocfilehash: e8ff532d66531cbe92ca661d9eaa5780e5b9f56c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23885743"
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server"></a>Skype 内のネットワーク サイトにビジネス サーバーの場所のポリシーを追加します。
 
ビジネス サーバーのエンタープライズ VoIP の Skype のネットワーク サイトへの ~ 9-1-1 の場所のポリシーを割り当てます。 
  
次の例では、既存のネットワーク サイトに[Skype ビジネス サーバー用に作成する場所のポリシー](create-location-policies.md)で定義された**Redmond**の場所のポリシーを追加する方法、および**Redmond**の場所のポリシーを使用する新しいネットワーク サイトを作成する方法を示しています。
  
ネットワークのサイトの操作に関する詳細については、次のコマンドレットは Lync Server 管理シェルのマニュアルを参照してください。
  
- **新しい-CsNetworkSite**
    
- **Get CsNetworkSite**
    
- **セット CsNetworkSite**
    
- **削除 CsNetworkSite**
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a>場所のポリシーを既存のネットワーク サイトに割り当てるには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
2. 既存のネットワーク サイトを変更するには、以下のコマンドレットを実行します。
    
    **Redmond** とマークされている場所のポリシーを、**Redmond** という名前の既存のネットワーク サイトに割り当てます。
    
  ```
  Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
  ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a>場所のポリシーを新しいネットワーク サイトに割り当てるには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
2. 新しいネットワーク サイトを作成するには、以下のコマンドレットを実行します。
    
    ネットワーク地域の新しいネットワーク サイトを作成して、**Redmond** とマークされた場所のポリシーを割り当てます。
    
   ```
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


