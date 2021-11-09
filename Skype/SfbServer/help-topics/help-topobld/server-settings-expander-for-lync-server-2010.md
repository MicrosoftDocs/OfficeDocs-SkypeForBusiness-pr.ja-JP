---
title: Lync Server 2010 用のサーバー設定エキスパンダー
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MachineSettingsExpander2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e2309ade-f9c7-4cd1-b135-45bf73b0441f
description: このコンピューターのプロパティを編集するには、次の操作を行います。
ms.openlocfilehash: 7eb3eb68114133c412653b9f02c493e2d85ba992
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60836479"
---
# <a name="server-settings-expander-for-lync-server-2010"></a>Lync Server 2010 用のサーバー設定エキスパンダー
 
このコンピューターのプロパティを編集するには、次の操作を行います。
  
- このコンピューターの **完全修飾ドメイン名 (FQDN)** を編集します。このエントリは、ドメイン ネーム システム (DNS) および、このコンピューターに関連付けられている証明書のサブジェクト名 (SN) またはサブジェクトの別名 (SAN) で定義されているコンピューター名と一致している必要があります。
    
- 以下のどちらかを選択します。
    
    [**すべての構成済み IP アドレスを使用する**]: コンピューター上のすべての構成済み IP アドレスを使用するには、このオプションを選択します。
    
    > [!IMPORTANT]
    > このコンピューターに複数の IP アドレスがある場合は、このコンピューターに関連付けられているサービスで、すべてのサービスにすべての IP アドレスが使用されることに留意してください。リスニング サーバーまたはリスニング サービスで特定の IP アドレスとポートの通信を想定している場合、そのサービスでリッスンする IP アドレスの最適な選択が行われない可能性があります。 
  
    [**選択された IP アドレスのみにサービスの使用を制限する**]: このコンピューターが展開の他のコンピューターとプールからの通信用にリッスンする **プライマリ IP アドレス** として特定の IP アドレスを定義するには、このオプションを選択します。このコンピューターとサービスが通信のためにリッスンし、定義されている PSTN ゲートウェイまたは IP-PBX に通信を送る、特定の IP アドレスに対して **PSTN の IP アドレス** を定義してください。
    

