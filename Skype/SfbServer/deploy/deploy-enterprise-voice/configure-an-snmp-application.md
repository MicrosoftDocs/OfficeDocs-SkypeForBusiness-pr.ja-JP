---
title: サーバーで SNMP アプリケーションを構成Skype for Business Server
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
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: E9-1-1 で動作する SNMP アプリケーションを構成Skype for Business Server エンタープライズ VoIP。
ms.openlocfilehash: cf1dcb324360f5bb85066f97300ebe97b6cf084edb7d784be0e33ae9c93d19ca
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54283889"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server"></a>サーバーで SNMP アプリケーションを構成Skype for Business Server
 
E9-1-1 で動作する SNMP アプリケーションを構成Skype for Business Server エンタープライズ VoIP。 
  
Skype for Business Serverには、場所情報サービスをポートおよびスイッチ情報と MAC アドレスと一致する簡易ネットワーク管理プロトコル (SNMP) アプリケーションに接続するために使用できる標準的な Web サービス インターフェイスが含まれています。 
  
SNMP アプリケーションがインストールされ、位置情報サービスが場所データベース内で一致する検索に失敗した場合、位置情報サービスはクライアントが提供する MAC アドレスを使用してアプリケーションに自動的にクエリを実行します。 その後、Location Information Service はポートを使用して、SNMP アプリケーションから返される情報を切り替えて、場所データベースに対して再度クエリを実行します。
  
> [!NOTE]
> MAC アドレスは、デバイスを実行しているコンピューターではWindows 8。 
  
### <a name="to-configure-the-snmp-application-url"></a>SNMP アプリケーションの URL を構成するには

1.  管理シェルをSkype for Business Serverする: [**スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[管理シェルSkype for Business Server **クリックします**。
    
2. 次のコマンドレットを使用して SNMP アプリケーションの URL を構成します。 
    
   ```powershell
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a>関連項目

[Set-CsWebServiceConfiguration](/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)