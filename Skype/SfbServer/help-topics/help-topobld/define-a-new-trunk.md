---
title: 新しいトランクの定義
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
description: 新しいセッション開始プロトコル (SIP) トランクを定義するには、次の情報を提供します。
ms.openlocfilehash: 669f896e9a51a2f7f229a065a867f8ce8e48bcdc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33903783"
---
# <a name="define-a-new-trunk"></a><span data-ttu-id="abb5b-103">新しいトランクの定義</span><span class="sxs-lookup"><span data-stu-id="abb5b-103">Define a New Trunk</span></span>

<span data-ttu-id="abb5b-104">新しいセッション開始プロトコル (SIP) トランクを定義するには、次の情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="abb5b-104">You define a new session initiation protocol (SIP) trunk by providing the following information:</span></span>

- <span data-ttu-id="abb5b-105">**トランクの名前**: このトランクを識別するトポロジでは、一意の名前</span><span class="sxs-lookup"><span data-stu-id="abb5b-105">**Trunk name**: unique name in your topology that will identify this trunk</span></span>

- <span data-ttu-id="abb5b-106">**関連付けられている PSTN ゲートウェイ**: ボックスの一覧から、配置に配置され構成されている PSTN ゲートウェイを選択</span><span class="sxs-lookup"><span data-stu-id="abb5b-106">**Associated PSTN Gateway**: select a deployed and configured PSTN gateway in your deployment from the list</span></span>

- <span data-ttu-id="abb5b-107">**IP または PSTN ゲートウェイのリッスンするポート**: IP PBX または PSTN ゲートウェイがリッスンするポートです。</span><span class="sxs-lookup"><span data-stu-id="abb5b-107">**Listening port for the IP/PSTN gateway**: port that the IP-PBX or PSTN gateway will listen on.</span></span> <span data-ttu-id="abb5b-108">すべて他のトランク リスニング ・ ポートからの展開で構成されている一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="abb5b-108">Must be unique from all other trunk listening ports configured in your deployment</span></span>

- <span data-ttu-id="abb5b-109">**SIP トランスポート プロトコル**: TCP または TLS のいずれかを一覧から選択</span><span class="sxs-lookup"><span data-stu-id="abb5b-109">**SIP Transport Protocol**: select from the list either TCP or TLS</span></span>

- <span data-ttu-id="abb5b-110">**仲介サーバーの関連付けられている**: 仲介サーバーを展開し、展開の構成を一覧から選択</span><span class="sxs-lookup"><span data-stu-id="abb5b-110">**Associated Mediation Server**: select from the list a Mediation Server that is deployed and configured in your deployment</span></span>

- <span data-ttu-id="abb5b-111">**仲介サーバーの関連付けられているポート**: ポートの値をこの SIP トランクを使用する仲介サーバーの TCP または TLS ポートの値に設定</span><span class="sxs-lookup"><span data-stu-id="abb5b-111">**Associated Mediation Server port**: set the port value equal to the TCP or TLS port value of the Mediation Server that this SIP trunk will use</span></span>

## <a name="see-also"></a><span data-ttu-id="abb5b-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="abb5b-112">See also</span></span>

[<span data-ttu-id="abb5b-113">Skype for Business Server 2015 の M:N トランク</span><span class="sxs-lookup"><span data-stu-id="abb5b-113">M:N trunk in Skype for Business Server 2015</span></span>](../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[<span data-ttu-id="abb5b-114">SIP トランクを実装する方法は?</span><span class="sxs-lookup"><span data-stu-id="abb5b-114">How do I implement SIP trunking?</span></span>](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)
