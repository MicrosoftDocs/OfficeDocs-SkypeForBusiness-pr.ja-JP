---
title: Skype のビジネス サーバーの SNMP アプリケーションを構成します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: ビジネス サーバーのエンタープライズ VoIP Skype で ~ 9-1-1 で使用する SNMP アプリケーションを構成します。
ms.openlocfilehash: 7903163d6cf1cd78d7689557f4906966c2c67a2c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893085"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server"></a>Skype のビジネス サーバーの SNMP アプリケーションを構成します。
 
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

[セット CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

