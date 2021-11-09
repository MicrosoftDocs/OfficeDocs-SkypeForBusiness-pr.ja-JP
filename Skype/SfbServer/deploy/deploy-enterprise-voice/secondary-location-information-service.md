---
title: サーバーでセカンダリ位置情報サービスを構成Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: E9-1-1 のセカンダリ 場所ソース (SLS) データベースを構成Skype for Business Server エンタープライズ VoIP。
ms.openlocfilehash: 7c41debb07ab8d1aece05b24f515f159f5be0dae
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60860804"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a>サーバーでセカンダリ位置情報サービスを構成Skype for Business Server
 
E9-1-1 のセカンダリ 場所ソース (SLS) データベースを構成Skype for Business Server エンタープライズ VoIP。 
  
Skype for Business Serverは、位置情報サービスをセカンダリ 位置情報ソース (SLS) データベースにポイントするために使用できる Web サービス インターフェイスを提供します。 SLS データベースに接続する Web サービス インターフェイスは、位置情報サービス WSDL に準拠している必要があります。 場所データベースとセカンダリ 場所データベースの両方が構成されている場合、場所情報サービスは最初に場所データベースにクエリを実行し、一致が見つからない場合は、場所要求をクライアントから SLS データベースに送信します。 場所が SLS に存在する場合、位置情報サービスはその場所をクライアントに返します。 
  
### <a name="to-configure-a-secondary-location-database"></a>セカンダリロケーション データベースを構成するには

1. 管理シェルをSkype for Business Serverする: [**スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[管理シェルSkype for Business Server **クリックします**。
    
2. 次のコマンドレットを実行して、セカンダリ場所データベースの場所の URL を構成します。 
    
   ```powershell
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a>関連項目

[Set-CsWebServiceConfiguration](/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)