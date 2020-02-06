---
title: 新しいトランクの定義
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
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
description: 新しいセッション開始プロトコル (SIP) トランクを定義するには、次の情報を指定します。
ms.openlocfilehash: 9b3d42500c57723b13d9c74668b3c4ad7159301b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820219"
---
# <a name="define-a-new-trunk"></a><span data-ttu-id="a42f0-103">新しいトランクの定義</span><span class="sxs-lookup"><span data-stu-id="a42f0-103">Define a New Trunk</span></span>

<span data-ttu-id="a42f0-104">新しいセッション開始プロトコル (SIP) トランクを定義するには、次の情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="a42f0-104">You define a new session initiation protocol (SIP) trunk by providing the following information:</span></span>

- <span data-ttu-id="a42f0-105">**トランク名**: このトランクを識別するトポロジの一意の名前</span><span class="sxs-lookup"><span data-stu-id="a42f0-105">**Trunk name**: unique name in your topology that will identify this trunk</span></span>

- <span data-ttu-id="a42f0-106">**関連付けられている Pstn ゲートウェイ**: 展開済みの pstn ゲートウェイを一覧から選びます。</span><span class="sxs-lookup"><span data-stu-id="a42f0-106">**Associated PSTN Gateway**: select a deployed and configured PSTN gateway in your deployment from the list</span></span>

- <span data-ttu-id="a42f0-107">**Ip/pstn ゲートウェイのリスニングポート**: ip PBX または pstn ゲートウェイがリッスンするポート。</span><span class="sxs-lookup"><span data-stu-id="a42f0-107">**Listening port for the IP/PSTN gateway**: port that the IP-PBX or PSTN gateway will listen on.</span></span> <span data-ttu-id="a42f0-108">展開で構成されている他のすべてのトランクリッスンポートから一意である必要があります</span><span class="sxs-lookup"><span data-stu-id="a42f0-108">Must be unique from all other trunk listening ports configured in your deployment</span></span>

- <span data-ttu-id="a42f0-109">**SIP トランスポートプロトコル**: TCP または TLS の一覧から選択します。</span><span class="sxs-lookup"><span data-stu-id="a42f0-109">**SIP Transport Protocol**: select from the list either TCP or TLS</span></span>

- <span data-ttu-id="a42f0-110">**関連付けられている仲介サーバー**: 展開で展開され構成されている仲介サーバーを一覧から選びます。</span><span class="sxs-lookup"><span data-stu-id="a42f0-110">**Associated Mediation Server**: select from the list a Mediation Server that is deployed and configured in your deployment</span></span>

- <span data-ttu-id="a42f0-111">**関連付けられている仲介サーバーポート**: この SIP トランクで使用する仲介サーバーの TCP または TLS ポートの値としてポート値を設定します</span><span class="sxs-lookup"><span data-stu-id="a42f0-111">**Associated Mediation Server port**: set the port value equal to the TCP or TLS port value of the Mediation Server that this SIP trunk will use</span></span>

## <a name="see-also"></a><span data-ttu-id="a42f0-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="a42f0-112">See also</span></span>

[<span data-ttu-id="a42f0-113">Skype for Business Server 2015 の M:N トランク</span><span class="sxs-lookup"><span data-stu-id="a42f0-113">M:N trunk in Skype for Business Server 2015</span></span>](../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[<span data-ttu-id="a42f0-114">SIP トランキングの実装方法を教えてください。</span><span class="sxs-lookup"><span data-stu-id="a42f0-114">How do I implement SIP trunking?</span></span>](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)
