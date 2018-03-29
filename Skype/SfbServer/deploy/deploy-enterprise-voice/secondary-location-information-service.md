---
title: Skype for Business Server 2015 でのセカンダリ場所情報サービスの構成
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: ~ 9-1-1 では、Skype のビジネス サーバーのエンタープライズ VoIP のセカンダリ ・ サイトのソース (SLS) データベースを構成します。
ms.openlocfilehash: 03de4369b8473142e7a76e3698bb9fe7f129d546
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 でのセカンダリ場所情報サービスの構成
 
~ 9-1-1 では、Skype のビジネス サーバーのエンタープライズ VoIP のセカンダリ ・ サイトのソース (SLS) データベースを構成します。 
  
Skype ビジネス サーバーは、セカンダリ場所ソース (SLS) のデータベースに位置情報サービスを指すように使用できる web サービス インターフェイスを提供します。 SLS データベースに接続する web サービスのインタ フェースは、位置情報サービスの WSDL に従う必要があります。 場所データベースとセカンダリ場所データベースの両方を構成すると、位置情報サービスが、まず、場所データベースにクエリを実行し、一致が見つからなかった場合、場所に要求を送信、クライアントから SLS データベースします。 SLS の場所が存在する場合、位置情報サービスは、クライアントに場所を送信します。 
  
### <a name="to-configure-a-secondary-location-database"></a>セカンダリ場所データベースを構成するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
2. 次のコマンドレットを実行して、セカンダリ場所データベースの場所の URL を構成します。 
    
   ```
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a>関連項目

#### 

[セット CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

