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
- CSH
ms.custom:
- ms.lync.tb.MachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e2309ade-f9c7-4cd1-b135-45bf73b0441f
description: このコンピューターのプロパティを編集するには、次の操作を行います。
ms.openlocfilehash: c0eb39a516cbcce18940abe7936747fc18db9761
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215698"
---
# <a name="server-settings-expander-for-lync-server-2010"></a><span data-ttu-id="28db1-103">Lync Server 2010 用のサーバー設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="28db1-103">Server Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="28db1-104">このコンピューターのプロパティを編集するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="28db1-104">To edit the properties for this computer, you do the following:</span></span>
  
- <span data-ttu-id="28db1-p101">このコンピューターの**完全修飾ドメイン名 (FQDN)** を編集します。このエントリは、ドメイン ネーム システム (DNS) および、このコンピューターに関連付けられている証明書のサブジェクト名 (SN) またはサブジェクトの別名 (SAN) で定義されているコンピューター名と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="28db1-p101">Edit the **Fully qualified domain name (FQDN)** for this computer. This entry must match the computer name as it is defined in the domain name system (DNS), and in subject alternative names (SAN) or subject name (SN) of the certificate associated with this computer.</span></span>
    
- <span data-ttu-id="28db1-107">以下のどちらかを選択します。</span><span class="sxs-lookup"><span data-stu-id="28db1-107">You select one of the following:</span></span>
    
    <span data-ttu-id="28db1-108">[**すべての構成済み IP アドレスを使用する**]: コンピューター上のすべての構成済み IP アドレスを使用するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="28db1-108">**Use all configured IP addresses**: Select this to use all configured IP addresses on the computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="28db1-p102">このコンピューターに複数の IP アドレスがある場合は、このコンピューターに関連付けられているサービスで、すべてのサービスにすべての IP アドレスが使用されることに留意してください。リスニング サーバーまたはリスニング サービスで特定の IP アドレスとポートの通信を想定している場合、そのサービスでリッスンする IP アドレスの最適な選択が行われない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="28db1-p102">If the computer has multiple IP addresses, you must be aware that the services associated with this computer will use all IP addresses for all services. If a listening server or service is expecting communication of a specific IP address and port, the service may not make the best selection of which IP address to listen on.</span></span> 
  
    <span data-ttu-id="28db1-p103">[**選択された IP アドレスのみにサービスの使用を制限する**]: このコンピューターが展開の他のコンピューターとプールからの通信用にリッスンする**プライマリ IP アドレス**として特定の IP アドレスを定義するには、このオプションを選択します。このコンピューターとサービスが通信のためにリッスンし、定義されている PSTN ゲートウェイまたは IP-PBX に通信を送る、特定の IP アドレスに対して **PSTN の IP アドレス**を定義してください。</span><span class="sxs-lookup"><span data-stu-id="28db1-p103">**Limit service usage to selected IP addresses**: Select this option if you want to define specific IP addresses for the **Primary IP address** that this computer will listen on for communication from other computers and pools in the deployment. Define **PSTN IP address** for the specific IP address that the computer and service will listen for communications and send communications to the defined PSTN gateway or IP-PBX.</span></span>
    

