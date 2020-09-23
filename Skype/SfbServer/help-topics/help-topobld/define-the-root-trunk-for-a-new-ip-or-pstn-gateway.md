---
title: 新しい IP または PSTN ゲートウェイのルート トランクを定義する
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
- ms.lync.tb.AddPstnGatewayTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 22203d9a-4612-45c7-9375-69ae9964ce1e
description: IP または公衆交換電話網 (PSTN) 用のルート トランクを定義するには、次の項目を構成します。
ms.openlocfilehash: 3789024ce5099645eca7c14576b586bc1c349683
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219078"
---
# <a name="define-the-root-trunk-for-a-new-ip-or-pstn-gateway"></a><span data-ttu-id="fed6c-103">新しい IP または PSTN ゲートウェイのルート トランクを定義する</span><span class="sxs-lookup"><span data-stu-id="fed6c-103">Define the Root Trunk for a New IP or PSTN Gateway</span></span>

<span data-ttu-id="fed6c-104">IP または公衆交換電話網 (PSTN) 用のルート トランクを定義するには、次の項目を構成します。</span><span class="sxs-lookup"><span data-stu-id="fed6c-104">You define the root trunk for the IP or public switched telephone network (PSTN) by configuring the following:</span></span>

- <span data-ttu-id="fed6c-105">[**トランク名**]: トランクに関連付けられた完全修飾ドメイン名を定義します。</span><span class="sxs-lookup"><span data-stu-id="fed6c-105">**Trunk name**: define the fully qualified domain name associated with the trunk</span></span>

- <span data-ttu-id="fed6c-106">[**IP/PSTN ゲートウェイのリッスン ポート**]: このトランクがリッスンするポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="fed6c-106">**Listening port for IP/PSTN gateway**: define the port that this trunk will listen on</span></span>

- <span data-ttu-id="fed6c-107">[**SIP 転送プロトコル**]: トランク要件に基づき、リストから **TCP** または **TLS** のどちらかを選択します。</span><span class="sxs-lookup"><span data-stu-id="fed6c-107">**SIP Transport Protocol**: select from the list either **TCP** or **TLS**, based on the trunk requirements</span></span>

- <span data-ttu-id="fed6c-108">[**関連付けられている仲介サーバー**]: 展開で利用可能な仲介サーバーの一覧から選択します。</span><span class="sxs-lookup"><span data-stu-id="fed6c-108">**Associated Mediation Server**: select from the list of available Mediation Servers in your deployment</span></span>

- <span data-ttu-id="fed6c-109">**関連付けられている仲介サーバーのポート**: 選択した仲介サーバーがリッスンしているポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="fed6c-109">**Associated Mediation Server port**: define the port that the selected Mediation Server is listening on</span></span>

## <a name="see-also"></a><span data-ttu-id="fed6c-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="fed6c-110">See also</span></span>

[<span data-ttu-id="fed6c-111">Skype for Business Server 2015 でメディアバイパスを使用してトランクを構成する</span><span class="sxs-lookup"><span data-stu-id="fed6c-111">Configure a trunk with media bypass in Skype for Business Server 2015</span></span>](../../deploy/deploy-enterprise-voice/configure-trunk-with-media-bypass.md)

[<span data-ttu-id="fed6c-112">Skype for Business Server 2015 でメディアバイパスを使用せずにトランクを構成する</span><span class="sxs-lookup"><span data-stu-id="fed6c-112">Configure a trunk without media bypass in Skype for Business Server 2015</span></span>](../../deploy/deploy-enterprise-voice/configure-trunk-without-media-bypass.md)

[<span data-ttu-id="fed6c-113">SIP トランキングのサポート</span><span class="sxs-lookup"><span data-stu-id="fed6c-113">SIP Trunking Support</span></span>](https://technet.microsoft.com/library/e3042831-e8d8-4ea2-baa2-1a697401ffa0.aspx)
