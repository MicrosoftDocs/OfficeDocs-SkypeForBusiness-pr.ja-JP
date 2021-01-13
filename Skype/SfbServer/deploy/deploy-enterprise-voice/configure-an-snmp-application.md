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
description: Skype for Business Server サービスで E9-1-1 と動作する SNMP アプリケーションをエンタープライズ VoIP。
ms.openlocfilehash: eb1947f24968dccc6f45b6d8ea3a7df42282a58f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804157"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server"></a>Skype for Business Server で SNMP アプリケーションを構成する
 
Skype for Business Server サービスで E9-1-1 と動作する SNMP アプリケーションをエンタープライズ VoIP。 
  
Skype for Business Server には、場所情報サービスをポートおよびスイッチ情報と MAC アドレスと一致する簡易ネットワーク管理プロトコル (SNMP) アプリケーションに接続するために使用できる標準の Web サービス インターフェイスが含まれています。 
  
SNMP アプリケーションがインストールされ、場所情報サービスが場所データベースで一致するアプリケーションを検出できない場合、場所情報サービスは、クライアントが提供する MAC アドレスを使用してアプリケーションを自動的に照会します。 その後、場所情報サービスは、SNMP アプリケーションから返されたポートとスイッチ情報を使用して、場所データベースに再度クエリを実行します。
  
> [!NOTE]
> MAC アドレスは、MAC アドレスを実行しているコンピューター Windows 8。 
  
### <a name="to-configure-the-snmp-application-url"></a>SNMP アプリケーションの URL を構成するには

1.  Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理** シェル] をクリックします。
    
2. 次のコマンドレットを使用して SNMP アプリケーションの URL を構成します。 
    
   ```powershell
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a>関連項目

[Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

