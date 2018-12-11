---
title: ビジネス サーバーの Skype でトランクを構成します。
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: エンタープライズ VoIP 展開の一部として、エンタープライズ VoIP クライアントと、組織内のデバイスの公衆交換電話網 (PSTN) 接続を提供するには、仲介サーバーと 1 つまたは複数のピア間のトランクを構成できます。
ms.openlocfilehash: 34391e09bb87144252634b572bf0eac6a10fe1d9
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222864"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a><span data-ttu-id="1ee5e-103">ビジネス サーバーの Skype でトランクを構成します。</span><span class="sxs-lookup"><span data-stu-id="1ee5e-103">Configuring trunks in Skype for Business Server</span></span>

<span data-ttu-id="1ee5e-104">エンタープライズ VoIP 展開の一部として、仲介サーバーと 1 つ以上のエンタープライズ VoIP クライアントと、組織内のデバイスの公衆交換電話網 (PSTN) 接続を提供する次のピア間のトランクを構成できます。</span><span class="sxs-lookup"><span data-stu-id="1ee5e-104">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>

- <span data-ttu-id="1ee5e-105">インターネット テレフォニー サービス プロバイダー (ITSP) への SIP トランク接続</span><span class="sxs-lookup"><span data-stu-id="1ee5e-105">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
- <span data-ttu-id="1ee5e-106">PSTN ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="1ee5e-106">PSTN gateway</span></span>
- <span data-ttu-id="1ee5e-107">構内交換機 (PBX)</span><span class="sxs-lookup"><span data-stu-id="1ee5e-107">Private branch exchange (PBX)</span></span>

<span data-ttu-id="1ee5e-108">詳細については、 [Skype のビジネス サーバーの PSTN への接続の計画](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ee5e-108">For details, see [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1ee5e-109">トランク構成を開始する前に、トポロジが作成されたことと、仲介サーバーとそのピアを構成および相互に関連付けられているを確認します。</span><span class="sxs-lookup"><span data-stu-id="1ee5e-109">Before you begin trunk configuration, verify that the topology has been created and that the Mediation Server and its peer have been configured and associated with one another.</span></span> <span data-ttu-id="1ee5e-110">詳細については、 [Skype のビジネス サーバーで、トポロジ ビルダーでゲートウェイを定義する](../../deploy/deploy-enterprise-voice/define-a-gateway.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ee5e-110">For details, see [Define a gateway in Topology Builder in Skype for Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1ee5e-111">、トランクの構成の一部として、Skype ビジネス サーバー メディア バイパス機能は、仲介サーバーをバイパスするメディアを有効にするを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="1ee5e-111">As a part of trunk configuration, you can enable the Skype for Business Server media bypass feature, which enables media to bypass the Mediation Server.</span></span> <span data-ttu-id="1ee5e-112">またはメディアのバイパスを有効にせず、トランクを構成することができますが、それを有効にすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1ee5e-112">Trunks can be configured either with or without media bypass enabled, but we strongly recommend that you enable it.</span></span> <span data-ttu-id="1ee5e-113">詳細については、[ビジネスの Skype で使用しないメディアの計画](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ee5e-113">For details, see [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>