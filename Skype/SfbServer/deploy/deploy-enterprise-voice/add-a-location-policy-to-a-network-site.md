---
title: Skype for Business Server のネットワーク サイトに場所ポリシーを追加する
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
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: Skype for Business Server のネットワーク サイトに E9-1-1 の場所ポリシーを割り当エンタープライズ VoIP。
ms.openlocfilehash: 887c2fcab63acd5d143ba80f6be6976e8fe2b39f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804277"
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server"></a>Skype for Business Server のネットワーク サイトに場所ポリシーを追加する
 
Skype for Business Server のネットワーク サイトに E9-1-1 の場所ポリシーを割り当エンタープライズ VoIP。 
  
次の例は [、「Create location policies in Skype for Business Server」](create-location-policies.md)で定義されている Redmond の場所ポリシーを既存のネットワーク サイトに追加する方法と **、Redmond** の場所ポリシーを使用する新しいネットワーク サイトを作成する方法を示しています。 
  
ネットワーク サイトの操作の詳細については、次のコマンドレットの Lync Server 管理シェルのドキュメントを参照してください。
  
- **New-CsNetworkSite**
    
- **Get-CsNetworkSite**
    
- **Set-CsNetworkSite**
    
- **Remove-CsNetworkSite**
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a>場所のポリシーを既存のネットワーク サイトに割り当てるには

1. Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理** シェル] をクリックします。
    
2. 既存のネットワーク サイトを変更するには、以下のコマンドレットを実行します。
    
    **Redmond というタグ付** きの場所ポリシーを Redmond という名前の既存のネットワーク サイトに **割り当てる**。
    
   ```powershell
   Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a>場所のポリシーを新しいネットワーク サイトに割り当てるには

1. Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理** シェル] をクリックします。
    
2. 新しいネットワーク サイトを作成するには、以下のコマンドレットを実行します。
    
    ネットワーク地域の新しいネットワーク サイトを作成して、**Redmond** とマークされた場所のポリシーを割り当てます。
    
   ```powershell
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


