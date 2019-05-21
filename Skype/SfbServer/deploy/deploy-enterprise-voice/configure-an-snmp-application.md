---
title: Skype for Business Server で SNMP アプリケーションを構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: Skype for Business Server Enterprise Voice で E9-1-1 と連携するように SNMP アプリケーションを構成します。
ms.openlocfilehash: 575c982dae20ed085e49690edfbb141786390516
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303419"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server"></a>Skype for Business Server で SNMP アプリケーションを構成する
 
Skype for Business Server Enterprise Voice で E9-1-1 と連携するように SNMP アプリケーションを構成します。 
  
Skype for Business Server には標準の web サービスインターフェイスが含まれています。これを使用すると、場所情報サービスを、MAC アドレスとポートおよびスイッチ情報を照合する簡易ネットワーク管理プロトコル (SNMP) アプリケーションに接続することができます。 
  
SNMP アプリケーションがインストールされていて、位置情報サービスが位置情報データベースで一致を見つけることができなかった場合、位置情報サービスは、クライアントから提供された MAC アドレスを使ってアプリケーションを自動的に照会します。 次に、位置情報サービスは、SNMP アプリケーションによって返されるポートとスイッチの情報を使用して、位置情報データベースをもう一度照会します。
  
> [!NOTE]
> MAC アドレスは、Windows 8 を実行しているコンピューターでは使用できません。 
  
### <a name="to-configure-the-snmp-application-url"></a>SNMP アプリケーションの URL を構成するには

1.  Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
2. 次のコマンドレットを使用して SNMP アプリケーションの URL を構成します。 
    
   ```
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a>関連項目

[Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

