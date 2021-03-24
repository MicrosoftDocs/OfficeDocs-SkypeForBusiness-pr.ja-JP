---
title: Skype for Business Server で SNMP アプリケーションを構成する
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
description: Skype for Business Server の E9-1-1 で動作する SNMP アプリケーションを構成エンタープライズ VoIP。
ms.openlocfilehash: f8b4c7503524dacdc20e85fc68f0a79286e38c2e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103633"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server"></a>Skype for Business Server で SNMP アプリケーションを構成する
 
Skype for Business Server の E9-1-1 で動作する SNMP アプリケーションを構成エンタープライズ VoIP。 
  
Skype for Business Server には標準的な Web サービス インターフェイスが含まれています。このインターフェイスを使用して、場所情報サービスをポートおよびスイッチ情報と MAC アドレスと一致する簡易ネットワーク管理プロトコル (SNMP) アプリケーションに接続できます。 
  
SNMP アプリケーションがインストールされ、位置情報サービスが場所データベース内で一致する検索に失敗した場合、位置情報サービスはクライアントが提供する MAC アドレスを使用してアプリケーションに自動的にクエリを実行します。 その後、Location Information Service はポートを使用して、SNMP アプリケーションから返される情報を切り替えて、場所データベースに対して再度クエリを実行します。
  
> [!NOTE]
> MAC アドレスは、MAC アドレスを実行しているコンピューターではWindows 8。 
  
### <a name="to-configure-the-snmp-application-url"></a>SNMP アプリケーションの URL を構成するには

1.  Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。
    
2. 次のコマンドレットを使用して SNMP アプリケーションの URL を構成します。 
    
   ```powershell
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a>関連項目

[Set-CsWebServiceConfiguration](/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)