---
title: Skype のビジネス サーバーのセカンダリ場所情報サービスを構成します。
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: ~ 9-1-1 では、Skype のビジネス サーバーのエンタープライズ VoIP のセカンダリ ・ サイトのソース (SLS) データベースを構成します。
ms.openlocfilehash: 36bbe6183fa6f4eb086c8676e17c63f63fc994a4
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "21006528"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a>Skype のビジネス サーバーのセカンダリ場所情報サービスを構成します。
 
~ 9-1-1 では、Skype のビジネス サーバーのエンタープライズ VoIP のセカンダリ ・ サイトのソース (SLS) データベースを構成します。 
  
Skype ビジネス サーバーは、セカンダリ場所ソース (SLS) のデータベースに位置情報サービスを指すように使用できる web サービス インターフェイスを提供します。 SLS データベースに接続する web サービスのインタ フェースは、位置情報サービスの WSDL に従う必要があります。 場所データベースとセカンダリ場所データベースの両方を構成すると、位置情報サービスが、まず、場所データベースにクエリを実行し、一致が見つからなかった場合、場所に要求を送信、クライアントから SLS データベースします。 SLS の場所が存在する場合、位置情報サービスは、クライアントに場所を送信します。 
  
### <a name="to-configure-a-secondary-location-database"></a>セカンダリ場所データベースを構成するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
2. 次のコマンドレットを実行して、セカンダリ場所データベースの場所の URL を構成します。 
    
   ```
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a>関連項目

[セット CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

