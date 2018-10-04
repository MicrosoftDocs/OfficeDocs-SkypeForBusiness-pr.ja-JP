---
title: 修正プログラムを適用またはビジネスのサーバーの Skype でのフロント エンド サーバーを更新します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
description: '概要: は、Skype でのフロント エンド サーバーにビジネスのサーバーのアップグレードやパッチを適用する方法を説明します。'
ms.openlocfilehash: cf209159391ef084d77b5adc639698ed766427ff
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "25371718"
---
# <a name="patch-or-update-front-end-servers-in-skype-for-business-server"></a>修正プログラムを適用またはビジネスのサーバーの Skype でのフロント エンド サーバーを更新します。
 
**の概要:** Skype でのフロント エンド サーバーにビジネスのサーバーのアップグレードやパッチを適用する方法について説明します。
  
フロント エンド プール内のサーバーにパッチを適用するときは、同時に、1 つのサーバーを行います。 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a>プール内のフロントエンド サーバーにアップグレードを適用する

1. 次のコマンドレットを入力します。
    
   ```
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     このコマンドレットで不足しているレプリカが示された場合は、次のコマンドレットでプールを復元してから、パッチを適用してください。
    
   ```
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. パッチを適用する最初のサーバーで、次のコマンドレットを実行します。
    
   ```
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    このコマンドレットでは、すべてのサービスを他のプール内のフロント エンド サーバーに移動し、このサーバーは、オフラインです。
    
3. このサーバーにアップグレードまたはパッチを適用します。
    
4. アップグレードしたサーバーで、次のコマンドレットを実行します。
    
   ```
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    サーバーがサービスに復帰します。
    
5. アップグレードが必要なサーバーごとに、手順 2 ～ 4 を繰り返します。
    

