---
title: Skype for Business Server でのトランクの構成
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: エンタープライズ VoIP 展開の一環として、仲介サーバーと 1 つ以上のピア間のトランクを構成して、組織内の エンタープライズ VoIP クライアントとデバイスに公衆交換電話網 (PSTN) 接続を提供できます。
ms.openlocfilehash: 57b8635d635c0fd0b8c41c95f92af768ff84dfd4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800117"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a><span data-ttu-id="2a2bb-103">Skype for Business Server でのトランクの構成</span><span class="sxs-lookup"><span data-stu-id="2a2bb-103">Configuring trunks in Skype for Business Server</span></span>

<span data-ttu-id="2a2bb-104">エンタープライズ VoIP 展開の一環として、仲介サーバーと次の 1 つ以上のピア間のトランクを構成して、組織内の エンタープライズ VoIP クライアントおよびデバイスに公衆交換電話網 (PSTN) 接続を提供できます。</span><span class="sxs-lookup"><span data-stu-id="2a2bb-104">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>

- <span data-ttu-id="2a2bb-105">インターネット テレフォニー サービス プロバイダー (ITSP) への SIP トランク接続</span><span class="sxs-lookup"><span data-stu-id="2a2bb-105">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
- <span data-ttu-id="2a2bb-106">PSTN ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="2a2bb-106">PSTN gateway</span></span>
- <span data-ttu-id="2a2bb-107">構内交換機 (PBX)</span><span class="sxs-lookup"><span data-stu-id="2a2bb-107">Private branch exchange (PBX)</span></span>

<span data-ttu-id="2a2bb-108">詳細については [、「Skype for Business Server での PSTN 接続の計画」を参照してください](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md)。</span><span class="sxs-lookup"><span data-stu-id="2a2bb-108">For details, see [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2a2bb-109">トランク構成を開始する前に、トポロジが既に作成済みであること、および仲介サーバーとそのピアが構成され、互いに関連付けられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2a2bb-109">Before you begin trunk configuration, verify that the topology has been created and that the Mediation Server and its peer have been configured and associated with one another.</span></span> <span data-ttu-id="2a2bb-110">詳細については [、「Skype for Business Server のトポロジ ビルダーでのゲートウェイの定義」を参照してください](../../deploy/deploy-enterprise-voice/define-a-gateway.md)。</span><span class="sxs-lookup"><span data-stu-id="2a2bb-110">For details, see [Define a gateway in Topology Builder in Skype for Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).</span></span>

> [!NOTE]
> <span data-ttu-id="2a2bb-111">トランク構成の一部として、Skype for Business Server メディア バイパス機能を有効にして、メディアで仲介サーバーをバイパスできます。</span><span class="sxs-lookup"><span data-stu-id="2a2bb-111">As a part of trunk configuration, you can enable the Skype for Business Server media bypass feature, which enables media to bypass the Mediation Server.</span></span> <span data-ttu-id="2a2bb-112">トランクは、メディア バイパスを有効にして構成できますが、有効にすることを強く推奨します。</span><span class="sxs-lookup"><span data-stu-id="2a2bb-112">Trunks can be configured either with or without media bypass enabled, but we strongly recommend that you enable it.</span></span> <span data-ttu-id="2a2bb-113">詳細については [、「Skype for Business でメディア バイパスを計画する」を参照してください](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="2a2bb-113">For details, see [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>
