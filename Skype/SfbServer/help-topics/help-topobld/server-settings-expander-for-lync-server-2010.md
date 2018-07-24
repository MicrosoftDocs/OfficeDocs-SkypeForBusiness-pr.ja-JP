---
title: Lync Server 2010 のサーバーの設定の拡張
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e2309ade-f9c7-4cd1-b135-45bf73b0441f
description: このコンピューターのプロパティを編集するにする操作を行います次。
ms.openlocfilehash: 242f2b25a77de7f81ce8c11828f2fc0fbe1c2d41
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20992450"
---
# <a name="server-settings-expander-for-lync-server-2010"></a>Lync Server 2010 のサーバーの設定の拡張
 
このコンピューターのプロパティを編集するにする操作を行います次。
  
- **完全修飾ドメイン名 (FQDN)** がこのコンピューターを編集します。 ドメイン ネーム システム (DNS)、およびサブジェクト代替名 (SAN)、またはこのコンピューターに関連付けられている証明書のサブジェクト名 (SN) で定義されているが、このエントリはコンピューター名に一致する必要があります。
    
- 次のいずれかを選択するとします。
    
    **構成されているすべての IP アドレスを使用**: このコンピューターのすべての構成済みの IP アドレスを使用するオプションを選択します。
    
    > [!IMPORTANT]
    > コンピューターに複数の IP アドレスが設定されている場合は、このコンピューターに関連付けられているサービスがすべての IP アドレスを使用してすべてのサービスのことに注意してくださいする必要があります。 リッスンしているサーバーまたはサービスが、特定の IP アドレスとポートの通信を期待している場合、サービスがリッスンする IP アドレスの最適な選択、ありません。 
  
    **選択した IP アドレスを使用するサービスの制限**: このコンピューターが他のコンピューターと、展開内のプールからの通信をリッスンする**プライマリ IP アドレス**の特定の IP アドレスを定義する場合にこのオプションを選択します。 コンピューターとサービスは通信をリッスンし、送信する通信を定義済みの PSTN ゲートウェイまたは IP-PBX は、特定の IP アドレスには、 **PSTN の IP アドレス**を定義します。
    

