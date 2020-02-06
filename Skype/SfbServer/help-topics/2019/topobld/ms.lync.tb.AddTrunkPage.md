---
title: 新しいトランクの定義
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
ROBOTS: NOINDEX, NOFOLLOW
description: 新しいセッション開始プロトコル (SIP) トランクを定義するには、次の情報を指定します。
ms.openlocfilehash: 17f6b72f1234813e717cfc72be60bb5f0352134a
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794316"
---
# <a name="define-a-new-trunk"></a><span data-ttu-id="dd9f5-103">新しいトランクの定義</span><span class="sxs-lookup"><span data-stu-id="dd9f5-103">Define a New Trunk</span></span>

<span data-ttu-id="dd9f5-104">新しいセッション開始プロトコル (SIP) トランクを定義するには、次の情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="dd9f5-104">You define a new session initiation protocol (SIP) trunk by providing the following information:</span></span>

- <span data-ttu-id="dd9f5-105">**トランク名**: このトランクを識別するトポロジの一意の名前</span><span class="sxs-lookup"><span data-stu-id="dd9f5-105">**Trunk name**: unique name in your topology that will identify this trunk</span></span>

- <span data-ttu-id="dd9f5-106">**関連付けられている Pstn ゲートウェイ**: 展開済みの pstn ゲートウェイを一覧から選びます。</span><span class="sxs-lookup"><span data-stu-id="dd9f5-106">**Associated PSTN Gateway**: select a deployed and configured PSTN gateway in your deployment from the list</span></span>

- <span data-ttu-id="dd9f5-107">**Ip/pstn ゲートウェイのリスニングポート**: ip PBX または pstn ゲートウェイがリッスンするポート。</span><span class="sxs-lookup"><span data-stu-id="dd9f5-107">**Listening port for the IP/PSTN gateway**: port that the IP-PBX or PSTN gateway will listen on.</span></span> <span data-ttu-id="dd9f5-108">展開で構成されている他のすべてのトランクリッスンポートから一意である必要があります</span><span class="sxs-lookup"><span data-stu-id="dd9f5-108">Must be unique from all other trunk listening ports configured in your deployment</span></span>

- <span data-ttu-id="dd9f5-109">**SIP トランスポートプロトコル**: TCP または TLS の一覧から選択します。</span><span class="sxs-lookup"><span data-stu-id="dd9f5-109">**SIP Transport Protocol**: select from the list either TCP or TLS</span></span>

- <span data-ttu-id="dd9f5-110">**関連付けられている仲介サーバー**: 展開で展開され構成されている仲介サーバーを一覧から選びます。</span><span class="sxs-lookup"><span data-stu-id="dd9f5-110">**Associated Mediation Server**: select from the list a Mediation Server that is deployed and configured in your deployment</span></span>

- <span data-ttu-id="dd9f5-111">**関連付けられている仲介サーバーポート**: この SIP トランクで使用する仲介サーバーの TCP または TLS ポートの値としてポート値を設定します</span><span class="sxs-lookup"><span data-stu-id="dd9f5-111">**Associated Mediation Server port**: set the port value equal to the TCP or TLS port value of the Mediation Server that this SIP trunk will use</span></span>

## <a name="see-also"></a><span data-ttu-id="dd9f5-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="dd9f5-112">See also</span></span>

[<span data-ttu-id="dd9f5-113">Skype for Business Server の M:N トランク</span><span class="sxs-lookup"><span data-stu-id="dd9f5-113">M:N trunk in Skype for Business Server</span></span>](../../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[<span data-ttu-id="dd9f5-114">SIP トランキングの実装方法を教えてください。</span><span class="sxs-lookup"><span data-stu-id="dd9f5-114">How do I implement SIP trunking?</span></span>](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)
