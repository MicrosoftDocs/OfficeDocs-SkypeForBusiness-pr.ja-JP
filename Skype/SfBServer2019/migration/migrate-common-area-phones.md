---
title: 共通領域電話の移行
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 共通領域電話は、ロビー、調理場、または工場の作業場のような、共有ワークスペースまたは共用エリアによく設置されている IP 電話です。 共通領域電話は、統合コミュニケーション (UC) 機能を提供するためにSkype for Business Server接続する必要があります。 展開を 2019 年 2019 年Skype for Business Serverした後、従来の共通領域に関連付けられている連絡先オブジェクトも移行する必要電話。 管理Skype for Business Serverを使用して、最初に従来の共通領域電話に関連付けられているすべての連絡先オブジェクトを取得し、それらのオブジェクトを 2019 プールに移動Skype for Business Serverします。
ms.openlocfilehash: 808e874216fac97b01face6efa7aae00e269b74ee0f009b106f872a33a6d6261
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54340433"
---
# <a name="migrate-common-area-phones"></a>共通領域電話の移行

共通領域電話は、ロビー、調理場、または工場の作業場のような、共有ワークスペースまたは共用エリアによく設置されている IP 電話です。 共通領域電話は、統合コミュニケーション (UC) 機能を提供するためにSkype for Business Server接続する必要があります。 展開を 2019 年 2019 年Skype for Business Serverした後、従来の共通領域に関連付けられている連絡先オブジェクトも移行する必要電話。 管理Skype for Business Serverを使用して、まず従来の共通領域電話に関連付けられているすべての連絡先オブジェクトを取得し、それらのオブジェクトを Skype for Business Server 2019 プールに移動します。
  
### <a name="migrate-common-area-phones"></a>共通領域電話の移行

1. 2019 Skype for Business Server 2019 フロントエンド サーバーから、[管理シェル] Skype for Business Server開きます。
    
2. コマンド ラインで、次のように入力します。
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. すべての連絡先オブジェクト Skype for Business Serverが 2019 年 2019 年のプールに移動されたSkype for Business Serverを確認するには、次Skype for Business Server入力します。
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    すべての連絡先オブジェクトが 2019 プールに関連付Skype for Business Server確認します。
    

