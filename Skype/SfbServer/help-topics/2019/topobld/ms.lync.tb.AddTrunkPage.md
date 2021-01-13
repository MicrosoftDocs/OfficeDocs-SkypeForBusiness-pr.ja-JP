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
ms.openlocfilehash: db98c6d6f6aacf31b4e0b228dbe499f40ea01bdf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800897"
---
# <a name="define-a-new-trunk"></a><span data-ttu-id="dfc8d-103">新しいトランクの定義</span><span class="sxs-lookup"><span data-stu-id="dfc8d-103">Define a New Trunk</span></span>

<span data-ttu-id="dfc8d-104">以下の情報を指定することにより、新しいセッション開始プロトコル (SIP) トランクを定義します。</span><span class="sxs-lookup"><span data-stu-id="dfc8d-104">You define a new session initiation protocol (SIP) trunk by providing the following information:</span></span>

- <span data-ttu-id="dfc8d-105">[**トランク名**]: トポロジ内でこのトランクを識別する一意の名前。</span><span class="sxs-lookup"><span data-stu-id="dfc8d-105">**Trunk name**: unique name in your topology that will identify this trunk</span></span>

- <span data-ttu-id="dfc8d-106">[**PSTN ゲートウェイの関連付け**]: 展開内の展開済みで構成済みの PSTN ゲートウェイをリストから選択します。</span><span class="sxs-lookup"><span data-stu-id="dfc8d-106">**Associated PSTN Gateway**: select a deployed and configured PSTN gateway in your deployment from the list</span></span>

- <span data-ttu-id="dfc8d-p101">[**IP/PSTN ゲートウェイのリッスン ポート**]: IP-PBX または PSTN ゲートウェイがリッスンするポート。展開内で構成されている他のすべてのトランク リッスン ポートと異なるものであることが必要です。</span><span class="sxs-lookup"><span data-stu-id="dfc8d-p101">**Listening port for the IP/PSTN gateway**: port that the IP-PBX or PSTN gateway will listen on. Must be unique from all other trunk listening ports configured in your deployment</span></span>

- <span data-ttu-id="dfc8d-109">[**SIP 転送プロトコル**]: リストから TCP または TLS を選択します。</span><span class="sxs-lookup"><span data-stu-id="dfc8d-109">**SIP Transport Protocol**: select from the list either TCP or TLS</span></span>

- <span data-ttu-id="dfc8d-110">**関連付けられた仲介サーバー**: 展開で展開および構成されている仲介サーバーを一覧から選択します。</span><span class="sxs-lookup"><span data-stu-id="dfc8d-110">**Associated Mediation Server**: select from the list a Mediation Server that is deployed and configured in your deployment</span></span>

- <span data-ttu-id="dfc8d-111">**関連付けられた仲介サーバーポート**: この SIP トランクが使用する仲介サーバーの TCP ポートまたは TLS ポート値と同じポート値を設定します。</span><span class="sxs-lookup"><span data-stu-id="dfc8d-111">**Associated Mediation Server port**: set the port value equal to the TCP or TLS port value of the Mediation Server that this SIP trunk will use</span></span>

## <a name="see-also"></a><span data-ttu-id="dfc8d-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="dfc8d-112">See also</span></span>

[<span data-ttu-id="dfc8d-113">Skype for Business Server の M:N トランク</span><span class="sxs-lookup"><span data-stu-id="dfc8d-113">M:N trunk in Skype for Business Server</span></span>](../../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[<span data-ttu-id="dfc8d-114">SIP トランキングを実装する方法</span><span class="sxs-lookup"><span data-stu-id="dfc8d-114">How do I implement SIP trunking?</span></span>](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)
