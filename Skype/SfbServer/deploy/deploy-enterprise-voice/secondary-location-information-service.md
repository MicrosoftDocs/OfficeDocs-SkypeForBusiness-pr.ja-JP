---
title: Skype for Business Server でセカンダリの場所情報サービスを構成する
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
description: Skype for Business Server サービスで E9-1-1 のセカンダリロケーション ソース (SLS) データベースをエンタープライズ VoIP。
ms.openlocfilehash: fd70957526d193951b56211c0d5a6623a26419e2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830647"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a>Skype for Business Server でセカンダリの場所情報サービスを構成する
 
Skype for Business Server サービスで E9-1-1 のセカンダリロケーション ソース (SLS) データベースをエンタープライズ VoIP。 
  
Skype for Business Server は、場所情報サービスがセカンダリロケーション ソース (SLS) データベースを指す Web サービス インターフェイスを提供します。 SLS データベースに接続する Web サービス インターフェイスは、場所情報サービス WSDL に準拠している必要があります。 場所データベースとセカンダリ場所データベースの両方が構成されている場合、場所情報サービスは最初に場所データベースを照会し、一致が見つからない場合は、場所の要求をクライアントから SLS データベースに送信します。 場所が SLS に存在する場合、場所情報サービスはその場所をクライアントに返送します。 
  
### <a name="to-configure-a-secondary-location-database"></a>セカンダリ場所データベースを構成するには

1. Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理シェル**] をクリックします。
    
2. 次のコマンドレットを実行して、セカンダリ場所データベースの場所の URL を構成します。 
    
   ```powershell
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a>関連項目

[Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

