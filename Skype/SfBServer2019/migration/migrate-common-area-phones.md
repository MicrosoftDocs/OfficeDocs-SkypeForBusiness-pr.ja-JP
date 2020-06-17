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
description: 共通領域電話は、ロビー、調理場、または工場の作業場のような、共有ワークスペースまたは共用エリアによく設置されている IP 電話です。 Skype for Business Server 統合コミュニケーション (UC) 機能を提供するために、共通領域電話をコンピューターに接続する必要はありません。 展開を Skype for Business Server 2019 に移行した後、従来の共通領域電話に関連付けられている連絡先オブジェクトも移行する必要があります。 Skype for Business Server 管理シェルを使用して、まず、従来の共通領域電話に関連付けられているすべての連絡先オブジェクトを取得し、そのオブジェクトを Skype for Business Server 2019 プールに移動します。
ms.openlocfilehash: b9cf5a32614ac41ac3c82773af4f37907c16e6f2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752709"
---
# <a name="migrate-common-area-phones"></a>共通領域電話の移行

共通領域電話は、ロビー、調理場、または工場の作業場のような、共有ワークスペースまたは共用エリアによく設置されている IP 電話です。 Skype for Business Server 統合コミュニケーション (UC) 機能を提供するために、共通領域電話をコンピューターに接続する必要はありません。 展開を Skype for Business Server 2019 に移行した後、従来の共通領域電話に関連付けられている連絡先オブジェクトも移行する必要があります。 Skype for business Server 管理シェルを使用して、まず、従来の共通領域電話に関連付けられているすべての連絡先オブジェクトを取得し、そのオブジェクトを Skype for Business Server 2019 プールに移動します。
  
### <a name="migrate-common-area-phones"></a>共通領域電話の移行

1. Skype for business Server 2019 フロントエンドサーバーから、Skype for Business Server 管理シェルを開きます。
    
2. コマンド ラインで、次のように入力します。
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. すべての連絡先オブジェクトが Skype for Business Server 2019 プールに移動されたことを確認するには、Skype for Business Server 管理シェルから次のように入力します。
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    すべての連絡先オブジェクトが Skype for Business Server 2019 プールに関連付けられていることを確認します。
    

