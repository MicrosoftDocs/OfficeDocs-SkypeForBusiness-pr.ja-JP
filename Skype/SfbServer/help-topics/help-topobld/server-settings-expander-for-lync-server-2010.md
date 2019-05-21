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
# <a name="server-settings-expander-for-lync-server-2010"></a><span data-ttu-id="38784-103">Lync Server 2010 用のサーバー設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="38784-103">Server Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="38784-104">このコンピューターのプロパティを編集するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="38784-104">To edit the properties for this computer, you do the following:</span></span>
  
- <span data-ttu-id="38784-105">このコンピューターの**完全修飾ドメイン名 (FQDN)** を編集します。</span><span class="sxs-lookup"><span data-stu-id="38784-105">Edit the **Fully qualified domain name (FQDN)** for this computer.</span></span> <span data-ttu-id="38784-106">このエントリは、ドメインネームシステム (DNS) で定義されているコンピューター名と、このコンピューターに関連付けられている証明書のサブジェクト代替名 (SAN) またはサブジェクト名 (SN) のいずれかに一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="38784-106">This entry must match the computer name as it is defined in the domain name system (DNS), and in subject alternative names (SAN) or subject name (SN) of the certificate associated with this computer.</span></span>
    
- <span data-ttu-id="38784-107">次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="38784-107">You select one of the following:</span></span>
    
    <span data-ttu-id="38784-108">[**構成されているすべての ip アドレスを使用**]: コンピューターで構成されている ip アドレスをすべて使用する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="38784-108">**Use all configured IP addresses**: Select this to use all configured IP addresses on the computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="38784-109">コンピューターに複数の IP アドレスがある場合は、このコンピューターに関連付けられているサービスがすべてのサービスの IP アドレスを使用することに注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="38784-109">If the computer has multiple IP addresses, you must be aware that the services associated with this computer will use all IP addresses for all services.</span></span> <span data-ttu-id="38784-110">リッスンしているサーバーまたはサービスが特定の IP アドレスとポートの通信を想定している場合、サービスはリッスンする IP アドレスを最適に選ぶことができません。</span><span class="sxs-lookup"><span data-stu-id="38784-110">If a listening server or service is expecting communication of a specific IP address and port, the service may not make the best selection of which IP address to listen on.</span></span> 
  
    <span data-ttu-id="38784-111">[指定**した ip アドレスにサービスを使用する]**: このオプションを選択すると、このコンピューターが、展開内の他のコンピューターやプールとの通信をリッスンする**プライマリ ip アドレス**の特定の ip アドレスを定義できます。</span><span class="sxs-lookup"><span data-stu-id="38784-111">**Limit service usage to selected IP addresses**: Select this option if you want to define specific IP addresses for the **Primary IP address** that this computer will listen on for communication from other computers and pools in the deployment.</span></span> <span data-ttu-id="38784-112">コンピューターとサービスが通信をリッスンし、定義された PSTN ゲートウェイまたは ip-pbx への通信を送信する特定の IP アドレスの**PSTN IP アドレス**を定義します。</span><span class="sxs-lookup"><span data-stu-id="38784-112">Define **PSTN IP address** for the specific IP address that the computer and service will listen for communications and send communications to the defined PSTN gateway or IP-PBX.</span></span>
    

