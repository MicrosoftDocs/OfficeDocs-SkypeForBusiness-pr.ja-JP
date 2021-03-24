---
title: 新しいトランクを定義する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 以下の情報を指定することにより、新しいセッション開始プロトコル (SIP) トランクを定義します。
ms.openlocfilehash: 540076814d2916f74a5e11be42f99b57711da2b7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093275"
---
# <a name="define-a-new-trunk"></a><span data-ttu-id="30bb1-103">新しいトランクの定義</span><span class="sxs-lookup"><span data-stu-id="30bb1-103">Define a New Trunk</span></span>

<span data-ttu-id="30bb1-104">以下の情報を指定することにより、新しいセッション開始プロトコル (SIP) トランクを定義します。</span><span class="sxs-lookup"><span data-stu-id="30bb1-104">You define a new session initiation protocol (SIP) trunk by providing the following information:</span></span>

- <span data-ttu-id="30bb1-105">[**トランク名**]: トポロジ内でこのトランクを識別する一意の名前。</span><span class="sxs-lookup"><span data-stu-id="30bb1-105">**Trunk name**: unique name in your topology that will identify this trunk</span></span>

- <span data-ttu-id="30bb1-106">[**PSTN ゲートウェイの関連付け**]: 展開内の展開済みで構成済みの PSTN ゲートウェイをリストから選択します。</span><span class="sxs-lookup"><span data-stu-id="30bb1-106">**Associated PSTN Gateway**: select a deployed and configured PSTN gateway in your deployment from the list</span></span>

- <span data-ttu-id="30bb1-p101">[**IP/PSTN ゲートウェイのリッスン ポート**]: IP-PBX または PSTN ゲートウェイがリッスンするポート。展開内で構成されている他のすべてのトランク リッスン ポートと異なるものであることが必要です。</span><span class="sxs-lookup"><span data-stu-id="30bb1-p101">**Listening port for the IP/PSTN gateway**: port that the IP-PBX or PSTN gateway will listen on. Must be unique from all other trunk listening ports configured in your deployment</span></span>

- <span data-ttu-id="30bb1-109">[**SIP 転送プロトコル**]: リストから TCP または TLS を選択します。</span><span class="sxs-lookup"><span data-stu-id="30bb1-109">**SIP Transport Protocol**: select from the list either TCP or TLS</span></span>

- <span data-ttu-id="30bb1-110">**関連する仲介サーバー**: 展開で展開および構成されている仲介サーバーを一覧から選択します。</span><span class="sxs-lookup"><span data-stu-id="30bb1-110">**Associated Mediation Server**: select from the list a Mediation Server that is deployed and configured in your deployment</span></span>

- <span data-ttu-id="30bb1-111">**関連付けられた仲介サーバー** のポート: この SIP トランクで使用する仲介サーバーの TCP または TLS ポート値とポート値を設定します。</span><span class="sxs-lookup"><span data-stu-id="30bb1-111">**Associated Mediation Server port**: set the port value equal to the TCP or TLS port value of the Mediation Server that this SIP trunk will use</span></span>

## <a name="see-also"></a><span data-ttu-id="30bb1-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="30bb1-112">See also</span></span>

[<span data-ttu-id="30bb1-113">Skype for Business Server の M:N トランク</span><span class="sxs-lookup"><span data-stu-id="30bb1-113">M:N trunk in Skype for Business Server</span></span>](../../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[<span data-ttu-id="30bb1-114">SIP トランキングを実装する方法</span><span class="sxs-lookup"><span data-stu-id="30bb1-114">How do I implement SIP trunking?</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-how-do-i-implement-sip-trunking)