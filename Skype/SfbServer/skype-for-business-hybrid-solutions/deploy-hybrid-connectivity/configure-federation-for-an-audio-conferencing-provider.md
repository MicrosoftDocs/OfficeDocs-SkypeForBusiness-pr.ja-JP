---
title: ハイブリッド展開で、オーディオ会議プロバイダーのフェデレーションを構成します。
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/8/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: 08dedcce-0d3f-45da-8282-cf2634a41665
description: '概要: ビジネス オンラインの Skype のオーディオ会議プロバイダーのフェデレーションを構成する方法を説明します。'
ms.openlocfilehash: 8ac7e8d365b2a46ac37091510c6909ea996d8ada
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a>ハイブリッド展開で、オーディオ会議プロバイダーのフェデレーションを構成します。
 
**の概要:**ビジネス オンラインの Skype のオーディオ会議プロバイダーのフェデレーションを構成する方法について説明します。
  
(オンプレミスをオンラインと共に使う) ハイブリッド展開で電話会議プロバイダー (ACP) を使う場合、オンプレミス展開と許可されるパートナー サーバーとしての ACP パートナーとの間にフェデレーションを構成する必要があります。 フェデレーションは、ACP パートナー ドメインとエッジ サーバー (アクセス プロキシとも呼ばれます) をオンプレミス展開のフェデレーション ドメイン リストに追加すると設定できます。 その後、APC パートナーは、オンプレミスのエッジ サーバー プールの FQDN を、許可されるフェデレーション ドメイン リストに追加する必要があります。 詳細については、ACP プロバイダーに問い合わせてください。 その後、APC パートナーは、オンプレミスのエッジ サーバー プールの FQDN を、許可されるフェデレーション ドメイン リストに追加する必要があります。
  
- **許可されるフェデレーション ドメインとしての ACP ドメインおよびエッジ サーバーの追加**
    
    許可パートナー サーバー (ドメインのフェデレーションを許可する) として、ACP ドメインを追加するのには[外部ドメインの許可の構成のサポート](http://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx)で、手順を実行します。 エッジ サーバーでは、ACP パートナーのエッジ サーバーの FQDN を追加します。 ACP からもアクセス プロキシとして参照される可能性があるエッジ サーバーの FQDN を取得するには ACP パートナーへの問い合わせが必要になる場合があります。
    
- **ACP パートナーへのエッジ サーバー プールの FQDN の指定**
    
    ACP パートナーは、フェデレーションを構成してオンプレミスのドメインを許可されるパートナー サーバーとして追加する必要があります。そのためには、エッジ サーバー プールの FQDN を許可されるフェデレーション ドメインとして追加します。
    

