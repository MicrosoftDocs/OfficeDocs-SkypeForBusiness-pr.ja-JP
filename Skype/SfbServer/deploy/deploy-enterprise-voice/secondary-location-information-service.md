---
title: Skype for Business Server でセカンダリ場所情報サービスを構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: Skype for Business Server Enterprise Voice で、E9 のセカンダリ場所ソース (SLS) データベースを構成します。
ms.openlocfilehash: 47dd4015cde79536323cee3edc04ed546459a3f0
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240166"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a>Skype for Business Server でセカンダリ場所情報サービスを構成する
 
Skype for Business Server Enterprise Voice で、E9 のセカンダリ場所ソース (SLS) データベースを構成します。 
  
Skype for Business Server には、位置情報サービスをセカンダリの場所のソース (SLS) データベースにポイントするために使用できる web サービスインターフェイスが用意されています。 SLS データベースに接続する web サービスインターフェイスは、位置情報サービスの WSDL に準拠している必要があります。 ロケーションデータベースとセカンダリロケーションデータベースの両方が構成されている場合、位置情報サービスは最初に位置情報データベースを照会し、一致が見つからない場合は、クライアントから SLS データベースに位置情報要求を送信します。 場所が SLS に存在する場合、位置情報サービスはその場所をクライアントに送り返します。 
  
### <a name="to-configure-a-secondary-location-database"></a>セカンダリ場所データベースを構成するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
2. 次のコマンドレットを実行して、セカンダリ場所データベースの場所の URL を構成します。 
    
   ```
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a>関連項目

[Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

