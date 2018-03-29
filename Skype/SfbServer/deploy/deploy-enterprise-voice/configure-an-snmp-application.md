---
title: Skype for Business Server 2015 での SNMP アプリケーションの構成
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
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: ビジネス サーバーのエンタープライズ VoIP Skype で ~ 9-1-1 で使用する SNMP アプリケーションを構成します。
ms.openlocfilehash: 5c10d00e05979c2a3e0efff015da61e5ff2c6ee9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="configure-an-snmp-application-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での SNMP アプリケーションの構成
 
ビジネス サーバーのエンタープライズ VoIP Skype で ~ 9-1-1 で使用する SNMP アプリケーションを構成します。 
  
Skype ビジネス サーバー用には、位置情報サービスをポートを MAC アドレスに一致して、スイッチの情報が簡易ネットワーク管理プロトコル (SNMP) アプリケーションに接続するために使用できる標準的な web サービス インターフェイスが含まれています。 
  
SNMP アプリケーションがインストールされている位置情報サービスは、場所データベース内の一致を検索するのには障害が発生した場合は、位置情報サービスは自動的にクライアントから提供された MAC アドレスを使用してアプリケーションを照会します。 位置情報サービスは、SNMP アプリケーションによって返されるポートとスイッチの情報を使用してもう一度場所データベースにクエリを実行します。
  
> [!NOTE]
> MAC アドレスは、Windows 8 を実行するコンピューターで使用可能ではありません。 
  
### <a name="to-configure-the-snmp-application-url"></a>SNMP アプリケーションの URL を構成するには

1.  Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
2. 次のコマンドレットを使用して SNMP アプリケーションの URL を構成します。 
    
   ```
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a>関連項目

#### 

[セット CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

