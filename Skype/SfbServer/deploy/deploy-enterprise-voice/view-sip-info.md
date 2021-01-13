---
title: Skype for Business Server の個々の SIP トランクに関する情報を表示する
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
ms.assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
description: '概要: Skype for Business Server で SIP トランクに関する情報を表示する方法について学習します。'
ms.openlocfilehash: 29a5a025589f4df7d99b8bf708bf8bd67d0f138f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830527"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>Skype for Business Server の個々の SIP トランクに関する情報を表示する
 
**概要:** Skype for Business Server で SIP トランクに関する情報を表示する方法について学習します。
  
SIP トランクは、Skype for Business Server Voice over IP 電話ネットワークを公衆交換電話網 (PSTN) に接続するために使用されます。 以前のバージョンの製品では、トランクを使用して仲介サーバーから PSTN ゲートウェイに発信通話がルーティングされ、各ゲートウェイは 1 つのトランクに制限されていました。 その結果、PSTN ゲートウェイと SIP トランクは実質的に同一でした。 管理者にとって、このことは、関連付けられている PSTN ゲートウェイに関する情報を表示するだけで個々の SIP トランクに関する情報を表示できることを意味していました。
  
ただし、Skype for Business Server では、複数のトランクを 1 つの PSTN ゲートウェイに割り当てることができます。これは、ゲートウェイとトランクが同一ではなくなったことを意味します。 つまり、管理者は新しい [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) コマンドレットを使用して、個々の SIP トランクに関する情報を表示する必要があります。
  
### <a name="to-view-information-for-all-your-sip-trunks"></a>すべての SIP トランクの情報を表示するには

- 次のコマンドは、組織で使用中のすべての SIP トランクに関する情報を返します。
    
  ```powershell
  Get-CsTrunk
  ```

### <a name="to-view-information-for-a-specific-sip-trunk"></a>特定の SIP トランクの情報を表示するには

- このコマンドは、PstnGateway:192.168.0.240 という Identity を持つ SIP トランクに関する情報のみを返します。
    
  ```powershell
  Get-CsTrunk -Identity "PstnGateway:192.168.0.240"
  ```

### <a name="view-information-for-all-the-sip-trunks-assigned-to-a-pool"></a>プールに割り当てられているすべての SIP トランクに関する情報を表示する

- この例では、プール atl-cs-001.litwareinc.com に割り当てられているすべての SIP トランクについて情報が返されます。
    
  ```powershell
  Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"
  ```
