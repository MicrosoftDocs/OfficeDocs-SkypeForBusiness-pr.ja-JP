---
title: Skype for Business Server の各 SIP trunks に関する情報を表示する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
description: '概要: Skype for Business Server の SIP trunks に関する情報を表示する方法について説明します。'
ms.openlocfilehash: f67fe998408b9c99311f1a86c35e08200de99431
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766930"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>Skype for Business Server の各 SIP trunks に関する情報を表示する
 
**概要:** Skype for Business Server の SIP trunks に関する情報を表示する方法について説明します。
  
SIP trunks は、Skype for Business Server のボイスオーバー IP 電話ネットワークと公衆交換電話網 (PSTN) を接続するために使用されます。 以前のバージョンの製品では、トランクを使用して仲介サーバーから PSTN ゲートウェイに発信通話がルーティングされ、各ゲートウェイは 1 つのトランクに制限されていました。 その結果、PSTN ゲートウェイと SIP トランクは実質的に同一でした。 管理者にとって、このことは、関連付けられている PSTN ゲートウェイに関する情報を表示するだけで個々の SIP トランクに関する情報を表示できることを意味していました。
  
ただし、Skype for Business Server では、複数の trunks を単一の PSTN ゲートウェイに割り当てることができるようになりました。これは、ゲートウェイと trunks が1つではなく、同じであることを意味します。 つまり、個々の SIP トランクに関する情報を表示するために、管理者は新しい[Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps)コマンドレットを使用する必要があります。
  
### <a name="to-view-information-for-all-your-sip-trunks"></a>すべての SIP トランクに関する情報の表示

- 次のコマンドは、組織で使用中のすべての SIP トランクに関する情報を返します。
    
  ```powershell
  Get-CsTrunk
  ```

### <a name="to-view-information-for-a-specific-sip-trunk"></a>特定の SIP トランクに関する情報の表示

- このコマンドは、PstnGateway:192.168.0.240 という Identity を持つ SIP トランクに関する情報のみを返します。
    
  ```powershell
  Get-CsTrunk -Identity "PstnGateway:192.168.0.240"
  ```

### <a name="view-information-for-all-the-sip-trunks-assigned-to-a-pool"></a>プールに割り当てられているすべての SIP トランクに関する情報を表示する

- この例では、プール atl-cs-001.litwareinc.com に割り当てられているすべての SIP トランクについて情報が返されます。
    
  ```powershell
  Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"
  ```
