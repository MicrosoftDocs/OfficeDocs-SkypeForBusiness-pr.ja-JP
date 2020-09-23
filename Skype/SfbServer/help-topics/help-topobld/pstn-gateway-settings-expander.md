---
title: PSTN ゲートウェイ設定の展開
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PstnGatewaySettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fd103df-150d-4ea8-b522-18dbc50f5061
description: PSTN (公衆交換電話網) ゲートウェイの設定を編集または変更するには、次のフィールドを変更します。
ms.openlocfilehash: 10669d4355acc8d2ea1a8546275116660c1ac7a7
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216588"
---
# <a name="pstn-gateway-settings-expander"></a><span data-ttu-id="1efec-103">PSTN ゲートウェイ設定の展開</span><span class="sxs-lookup"><span data-stu-id="1efec-103">PSTN Gateway Settings Expander</span></span>
 
<span data-ttu-id="1efec-104">PSTN (公衆交換電話網) ゲートウェイの設定を編集または変更するには、次のフィールドを変更します。</span><span class="sxs-lookup"><span data-stu-id="1efec-104">To edit or modify the settings for a public switched telephone network (PSTN) gateway, modify the following fields:</span></span>
  
<span data-ttu-id="1efec-105">ゲートウェイの FQDN または IP アドレスは必須のエントリであり、PSTN ゲートウェイの**完全修飾ドメイン名 (FQDN)** をドメイン ネーム システム (DNS) ホスト (A) レコード、静的 HOSTS ファイル エントリ、または PSTN ゲートウェイの IP アドレスのいずれとして定義するのかを定義します。</span><span class="sxs-lookup"><span data-stu-id="1efec-105">Gateway FQDN or IP Address is a required entry and defines wither the **Fully qualified domain name (FQDN)** of the PSTN gateway as defined by a Domain Name System (DNS) host (A) record, a static HOSTS file entry, or by the IP address of the PSTN gateway.</span></span>
  
<span data-ttu-id="1efec-p101">SIP トランスポート プロトコルは、伝送制御プロトコル (TCP) の場合とトランスポート層セキュリティ (TLS) の場合があります。TLS が既定です。ゲートウェイでサポートされるプロトコルについては、ゲートウェイ ベンダーのドキュメントを参照してください。既定は TLS で、ゲートウェイが TLS をサポートしている場合は、こちらがより安全性の高い選択肢と考えられます。</span><span class="sxs-lookup"><span data-stu-id="1efec-p101">The SIP Transport Protocol can either be Transmission Control Protocol (TCP) or Transport Layer Security (TLS). TLS is the default. Refer to the gateway vendor documentation for what you gateway supports. The default is TLS, and should be considered the more secure selection, if the gateway supports TLS.</span></span>
  
<span data-ttu-id="1efec-110">ゲートウェイで IPv4 および IPv6 を有効にするかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="1efec-110">Select whether to enable IPv4 and IPv6 for the gateway.</span></span>
  
<span data-ttu-id="1efec-p102">**代替メディア IP アドレス**は、展開されている PSTN ゲートウェイがメディア トラフィック用に、通常は SIP トラフィック専用の既定の構成済みの IP アドレスである、異なる IP アドレスを持っている仲介サーバー用の定義です。このパラメーターを定義すると、PSTN ゲートウェイで、異なるネットワーク インターフェイス、つまりメディアのパスがサポートされます。このアドレスを空白にすると、PSTN ゲートウェイではメディアの代替パスはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="1efec-p102">The **Alternate media IP address** is a definition for the Mediation Server for which the deployed PSTN gateway has a different IP address for media traffic than the default configured IP address, which is typically dedicated for SIP traffic. If you define this parameter, then the PSTN gateway supports a different supports a different network interface or path for media. If this address is left blank, then the PSTN gateway does not support the alternate path for media.</span></span>
  

