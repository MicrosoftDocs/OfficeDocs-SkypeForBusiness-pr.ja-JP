---
title: Skype for Business Server 2015 での個別の SIP トランク情報の表示
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
description: '概要: ビジネス サーバー 2015 の Skype での SIP トランクに関する情報を表示する方法を説明します。'
ms.openlocfilehash: fb9990ec4315ffd26f51adaee2414810a053a97f
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568243"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での個別の SIP トランク情報の表示
 
**の概要:** ビジネス サーバー 2015 の Skype での SIP トランクに関する情報を表示する方法について説明します。
  
SIP トランクを使用して、Skype をビジネス サーバーの音声トラフィックの IP 電話ネットワークに、パブリック交換電話網 (PSTN) 経由で接続します。 以前のバージョンの製品では、トランクを使用して仲介サーバーから PSTN ゲートウェイに発信通話がルーティングされ、各ゲートウェイは 1 つのトランクに制限されていました。 その結果、PSTN ゲートウェイと SIP トランクは実質的に同一でした。 管理者にとって、このことは、関連付けられている PSTN ゲートウェイに関する情報を表示するだけで個々の SIP トランクに関する情報を表示できることを意味していました。
  
ビジネス サーバーの Skype でただし、複数のトランク今すぐに割り当て可能、1 つの PSTN ゲートウェイこれは、ゲートウェイとトランクに 1 つだけが不要になったことを意味します。 つまり、管理者が個々 の SIP トランクに関する情報を表示するために新しい[Get CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps)コマンドレットを使用する必要があります。
  
### <a name="to-view-information-for-all-your-sip-trunks"></a>すべての SIP トランクに関する情報の表示

- 次のコマンドは、組織で使用中のすべての SIP トランクに関する情報を返します。
    
  ```
  Get-CsTrunk
  ```

### <a name="to-view-information-for-a-specific-sip-trunk"></a>特定の SIP トランクに関する情報の表示

- このコマンドは、PstnGateway:192.168.0.240 という Identity を持つ SIP トランクに関する情報のみを返します。
    
  ```
  Get-CsTrunk -Identity "PstnGateway:192.168.0.240"
  ```

### <a name="view-information-for-all-the-sip-trunks-assigned-to-a-pool"></a>プールに割り当てられているすべての SIP トランクに関する情報を表示する

- この例では、プール atl-cs-001.litwareinc.com に割り当てられているすべての SIP トランクについて情報が返されます。
    
  ```
  Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"
  ```