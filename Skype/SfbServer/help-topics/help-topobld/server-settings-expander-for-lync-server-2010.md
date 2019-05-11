---
title: Lync Server 2010 用のサーバー設定エキスパンダー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 0db8f318f7c4381707869fe06ee7c492c78d63ac
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929540"
---
# <a name="server-settings-expander-for-lync-server-2010"></a><span data-ttu-id="b2d30-103">Lync Server 2010 用のサーバー設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="b2d30-103">Server Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="b2d30-104">このコンピューターのプロパティを編集するにする操作を行います次。</span><span class="sxs-lookup"><span data-stu-id="b2d30-104">To edit the properties for this computer, you do the following:</span></span>
  
- <span data-ttu-id="b2d30-105">**完全修飾ドメイン名 (FQDN)** がこのコンピューターを編集します。</span><span class="sxs-lookup"><span data-stu-id="b2d30-105">Edit the **Fully qualified domain name (FQDN)** for this computer.</span></span> <span data-ttu-id="b2d30-106">ドメイン ネーム システム (DNS)、およびサブジェクト代替名 (SAN)、またはこのコンピューターに関連付けられている証明書のサブジェクト名 (SN) で定義されているが、このエントリはコンピューター名に一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2d30-106">This entry must match the computer name as it is defined in the domain name system (DNS), and in subject alternative names (SAN) or subject name (SN) of the certificate associated with this computer.</span></span>
    
- <span data-ttu-id="b2d30-107">次のいずれかを選択するとします。</span><span class="sxs-lookup"><span data-stu-id="b2d30-107">You select one of the following:</span></span>
    
    <span data-ttu-id="b2d30-108">**構成されているすべての IP アドレスを使用**: このコンピューターのすべての構成済みの IP アドレスを使用するオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="b2d30-108">**Use all configured IP addresses**: Select this to use all configured IP addresses on the computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="b2d30-109">コンピューターに複数の IP アドレスが設定されている場合は、このコンピューターに関連付けられているサービスがすべての IP アドレスを使用してすべてのサービスのことに注意してくださいする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2d30-109">If the computer has multiple IP addresses, you must be aware that the services associated with this computer will use all IP addresses for all services.</span></span> <span data-ttu-id="b2d30-110">リッスンしているサーバーまたはサービスが、特定の IP アドレスとポートの通信を期待している場合、サービスがリッスンする IP アドレスの最適な選択、ありません。</span><span class="sxs-lookup"><span data-stu-id="b2d30-110">If a listening server or service is expecting communication of a specific IP address and port, the service may not make the best selection of which IP address to listen on.</span></span> 
  
    <span data-ttu-id="b2d30-111">**選択した IP アドレスを使用するサービスの制限**: このコンピューターが他のコンピューターと、展開内のプールからの通信をリッスンする**プライマリ IP アドレス**の特定の IP アドレスを定義する場合にこのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="b2d30-111">**Limit service usage to selected IP addresses**: Select this option if you want to define specific IP addresses for the **Primary IP address** that this computer will listen on for communication from other computers and pools in the deployment.</span></span> <span data-ttu-id="b2d30-112">コンピューターとサービスは通信をリッスンし、送信する通信を定義済みの PSTN ゲートウェイまたは IP-PBX は、特定の IP アドレスには、 **PSTN の IP アドレス**を定義します。</span><span class="sxs-lookup"><span data-stu-id="b2d30-112">Define **PSTN IP address** for the specific IP address that the computer and service will listen for communications and send communications to the defined PSTN gateway or IP-PBX.</span></span>
    

