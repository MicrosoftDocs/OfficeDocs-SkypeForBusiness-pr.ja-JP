---
title: Lync Server 2010 用のサーバー設定エキスパンダー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.MachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e2309ade-f9c7-4cd1-b135-45bf73b0441f
description: このコンピューターのプロパティを編集するには、次の操作を行います。
ms.openlocfilehash: 0f8a1a31c593c792ff4872d0e104c6aadabcd819
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819299"
---
# <a name="server-settings-expander-for-lync-server-2010"></a><span data-ttu-id="2e375-103">Lync Server 2010 用のサーバー設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="2e375-103">Server Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="2e375-104">このコンピューターのプロパティを編集するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="2e375-104">To edit the properties for this computer, you do the following:</span></span>
  
- <span data-ttu-id="2e375-105">このコンピューターの**完全修飾ドメイン名 (FQDN)** を編集します。</span><span class="sxs-lookup"><span data-stu-id="2e375-105">Edit the **Fully qualified domain name (FQDN)** for this computer.</span></span> <span data-ttu-id="2e375-106">このエントリは、ドメインネームシステム (DNS) で定義されているコンピューター名と、このコンピューターに関連付けられている証明書のサブジェクト代替名 (SAN) またはサブジェクト名 (SN) のいずれかに一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e375-106">This entry must match the computer name as it is defined in the domain name system (DNS), and in subject alternative names (SAN) or subject name (SN) of the certificate associated with this computer.</span></span>
    
- <span data-ttu-id="2e375-107">次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="2e375-107">You select one of the following:</span></span>
    
    <span data-ttu-id="2e375-108">[**構成されているすべての ip アドレスを使用**]: コンピューターで構成されている ip アドレスをすべて使用する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="2e375-108">**Use all configured IP addresses**: Select this to use all configured IP addresses on the computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="2e375-109">コンピューターに複数の IP アドレスがある場合は、このコンピューターに関連付けられているサービスがすべてのサービスの IP アドレスを使用することに注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e375-109">If the computer has multiple IP addresses, you must be aware that the services associated with this computer will use all IP addresses for all services.</span></span> <span data-ttu-id="2e375-110">リッスンしているサーバーまたはサービスが特定の IP アドレスとポートの通信を想定している場合、サービスはリッスンする IP アドレスを最適に選ぶことができません。</span><span class="sxs-lookup"><span data-stu-id="2e375-110">If a listening server or service is expecting communication of a specific IP address and port, the service may not make the best selection of which IP address to listen on.</span></span> 
  
    <span data-ttu-id="2e375-111">[指定**した ip アドレスにサービスを使用する]**: このオプションを選択すると、このコンピューターが、展開内の他のコンピューターやプールとの通信をリッスンする**プライマリ ip アドレス**の特定の ip アドレスを定義できます。</span><span class="sxs-lookup"><span data-stu-id="2e375-111">**Limit service usage to selected IP addresses**: Select this option if you want to define specific IP addresses for the **Primary IP address** that this computer will listen on for communication from other computers and pools in the deployment.</span></span> <span data-ttu-id="2e375-112">コンピューターとサービスが通信をリッスンし、定義された PSTN ゲートウェイまたは ip-pbx への通信を送信する特定の IP アドレスの**PSTN IP アドレス**を定義します。</span><span class="sxs-lookup"><span data-stu-id="2e375-112">Define **PSTN IP address** for the specific IP address that the computer and service will listen for communications and send communications to the defined PSTN gateway or IP-PBX.</span></span>
    

