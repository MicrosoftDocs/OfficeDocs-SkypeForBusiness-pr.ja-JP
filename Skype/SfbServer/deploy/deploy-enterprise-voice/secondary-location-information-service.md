---
title: Skype for Business Server でセカンダリ位置情報サービスを構成する
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
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: Skype for Business Server エンタープライズ VoIP で E9-1-1 のセカンダリ 場所ソース (SLS) データベースを構成エンタープライズ VoIP。
ms.openlocfilehash: 7a81d8573ca0425d4d445dc00f257f014a39d8c6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103383"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a>Skype for Business Server でセカンダリ位置情報サービスを構成する
 
Skype for Business Server エンタープライズ VoIP で E9-1-1 のセカンダリ 場所ソース (SLS) データベースを構成エンタープライズ VoIP。 
  
Skype for Business Server には、位置情報サービスをセカンダリ ロケーション ソース (SLS) データベースにポイントするために使用できる Web サービス インターフェイスが提供されています。 SLS データベースに接続する Web サービス インターフェイスは、位置情報サービス WSDL に準拠している必要があります。 場所データベースとセカンダリ 場所データベースの両方が構成されている場合、場所情報サービスは最初に場所データベースにクエリを実行し、一致が見つからない場合は、場所要求をクライアントから SLS データベースに送信します。 場所が SLS に存在する場合、位置情報サービスはその場所をクライアントに返します。 
  
### <a name="to-configure-a-secondary-location-database"></a>セカンダリロケーション データベースを構成するには

1. Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。
    
2. 次のコマンドレットを実行して、セカンダリ場所データベースの場所の URL を構成します。 
    
   ```powershell
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a>関連項目

[Set-CsWebServiceConfiguration](/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)