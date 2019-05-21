---
title: Lync Server 2010 用のサーバー設定エキスパンダー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e2309ade-f9c7-4cd1-b135-45bf73b0441f
description: このコンピューターのプロパティを編集するには、次の操作を行います。
ms.openlocfilehash: 28261b3637040acda70218f23101b4337b1f90c3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297611"
---
# <a name="server-settings-expander-for-lync-server-2010"></a>Lync Server 2010 用のサーバー設定エキスパンダー
 
このコンピューターのプロパティを編集するには、次の操作を行います。
  
- このコンピューターの**完全修飾ドメイン名 (FQDN)** を編集します。 このエントリは、ドメインネームシステム (DNS) で定義されているコンピューター名と、このコンピューターに関連付けられている証明書のサブジェクト代替名 (SAN) またはサブジェクト名 (SN) のいずれかに一致する必要があります。
    
- 次のいずれかを選択します。
    
    [**構成されているすべての ip アドレスを使用**]: コンピューターで構成されている ip アドレスをすべて使用する場合に選択します。
    
    > [!IMPORTANT]
    > コンピューターに複数の IP アドレスがある場合は、このコンピューターに関連付けられているサービスがすべてのサービスの IP アドレスを使用することに注意する必要があります。 リッスンしているサーバーまたはサービスが特定の IP アドレスとポートの通信を想定している場合、サービスはリッスンする IP アドレスを最適に選ぶことができません。 
  
    [指定**した ip アドレスにサービスを使用する]**: このオプションを選択すると、このコンピューターが、展開内の他のコンピューターやプールとの通信をリッスンする**プライマリ ip アドレス**の特定の ip アドレスを定義できます。 コンピューターとサービスが通信をリッスンし、定義された PSTN ゲートウェイまたは ip-pbx への通信を送信する特定の IP アドレスの**PSTN IP アドレス**を定義します。
    

