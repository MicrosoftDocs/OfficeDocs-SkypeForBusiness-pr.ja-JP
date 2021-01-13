---
title: 新しい IP または PSTN ゲートウェイのルート トランクを定義する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: 4f437f9536b834b8b8dc69f59702bc77ce968ef2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835387"
---
# <a name="define-the-root-trunk-for-a-new-ip-or-pstn-gateway"></a><span data-ttu-id="bceab-103">新しい IP または PSTN ゲートウェイのルート トランクの定義</span><span class="sxs-lookup"><span data-stu-id="bceab-103">Define the Root Trunk for a New IP or PSTN Gateway</span></span>

<span data-ttu-id="bceab-104">IP または公衆交換電話網 (PSTN) 用のルート トランクを定義するには、次の項目を構成します。</span><span class="sxs-lookup"><span data-stu-id="bceab-104">You define the root trunk for the IP or public switched telephone network (PSTN) by configuring the following:</span></span>

- <span data-ttu-id="bceab-105">[**トランク名**]: トランクに関連付けられた完全修飾ドメイン名を定義します。</span><span class="sxs-lookup"><span data-stu-id="bceab-105">**Trunk name**: define the fully qualified domain name associated with the trunk</span></span>

- <span data-ttu-id="bceab-106">[**IP/PSTN ゲートウェイのリッスン ポート**]: このトランクがリッスンするポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="bceab-106">**Listening port for IP/PSTN gateway**: define the port that this trunk will listen on</span></span>

- <span data-ttu-id="bceab-107">[**SIP 転送プロトコル**]: トランク要件に基づき、リストから **TCP** または **TLS** のどちらかを選択します。</span><span class="sxs-lookup"><span data-stu-id="bceab-107">**SIP Transport Protocol**: select from the list either **TCP** or **TLS**, based on the trunk requirements</span></span>

- <span data-ttu-id="bceab-108">**関連付けられた仲介サーバー**: 展開で使用可能な仲介サーバーの一覧から選択する</span><span class="sxs-lookup"><span data-stu-id="bceab-108">**Associated Mediation Server**: select from the list of available Mediation Servers in your deployment</span></span>

- <span data-ttu-id="bceab-109">**関連付けられた仲介サーバーポート**: 選択した仲介サーバーがリッスンしているポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="bceab-109">**Associated Mediation Server port**: define the port that the selected Mediation Server is listening on</span></span>

## <a name="see-also"></a><span data-ttu-id="bceab-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="bceab-110">See also</span></span>

[<span data-ttu-id="bceab-111">Skype for Business Server 2015 でのメディア バイパスを使用したトランクの構成</span><span class="sxs-lookup"><span data-stu-id="bceab-111">Configure a trunk with media bypass in Skype for Business Server 2015</span></span>](../../deploy/deploy-enterprise-voice/configure-trunk-with-media-bypass.md)

[<span data-ttu-id="bceab-112">Skype for Business Server 2015 でのメディア バイパスなしのトランクの構成</span><span class="sxs-lookup"><span data-stu-id="bceab-112">Configure a trunk without media bypass in Skype for Business Server 2015</span></span>](../../deploy/deploy-enterprise-voice/configure-trunk-without-media-bypass.md)

[<span data-ttu-id="bceab-113">SIP トランキングのサポート</span><span class="sxs-lookup"><span data-stu-id="bceab-113">SIP Trunking Support</span></span>](https://technet.microsoft.com/library/e3042831-e8d8-4ea2-baa2-1a697401ffa0.aspx)
