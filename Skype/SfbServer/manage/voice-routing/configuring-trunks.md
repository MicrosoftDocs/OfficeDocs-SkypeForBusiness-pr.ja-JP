---
title: Skype for Business Server で trunks を構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: エンタープライズ Voip の展開の一部として、仲介サーバーと1つ以上のピアの間でトランクを構成して、組織内のエンタープライズ Voip クライアントとデバイスの公衆交換電話網 (PSTN) 接続を提供できます。
ms.openlocfilehash: c350723720dccee069a28a4d9aa2c40517f6d1bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275004"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a><span data-ttu-id="d0cf8-103">Skype for Business Server で trunks を構成する</span><span class="sxs-lookup"><span data-stu-id="d0cf8-103">Configuring trunks in Skype for Business Server</span></span>

<span data-ttu-id="d0cf8-104">エンタープライズ Voip の展開の一部として、仲介サーバーと次のピアの1つ以上にトランクを構成して、組織内のエンタープライズボイスクライアントとデバイスの公衆交換電話網 (PSTN) 接続を提供できます。</span><span class="sxs-lookup"><span data-stu-id="d0cf8-104">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>

- <span data-ttu-id="d0cf8-105">インターネット テレフォニー サービス プロバイダー (ITSP) への SIP トランク接続</span><span class="sxs-lookup"><span data-stu-id="d0cf8-105">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
- <span data-ttu-id="d0cf8-106">PSTN ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="d0cf8-106">PSTN gateway</span></span>
- <span data-ttu-id="d0cf8-107">構内交換機 (PBX)</span><span class="sxs-lookup"><span data-stu-id="d0cf8-107">Private branch exchange (PBX)</span></span>

<span data-ttu-id="d0cf8-108">詳細については、「 [Skype For Business Server での PSTN 接続の計画](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0cf8-108">For details, see [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d0cf8-109">トランクの構成を開始する前に、トポロジが作成され、仲介サーバーとそのピアが構成されて互いに関連付けられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d0cf8-109">Before you begin trunk configuration, verify that the topology has been created and that the Mediation Server and its peer have been configured and associated with one another.</span></span> <span data-ttu-id="d0cf8-110">詳細については、「 [Skype For Business Server のトポロジビルダーでゲートウェイを定義する](../../deploy/deploy-enterprise-voice/define-a-gateway.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0cf8-110">For details, see [Define a gateway in Topology Builder in Skype for Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d0cf8-111">トランク構成の一部として、Skype for Business Server media バイパス機能を有効にすることで、メディアが仲介サーバーをバイパスすることを可能にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d0cf8-111">As a part of trunk configuration, you can enable the Skype for Business Server media bypass feature, which enables media to bypass the Mediation Server.</span></span> <span data-ttu-id="d0cf8-112">Trunks は、メディアのバイパスを有効にするかどうかを指定して構成できますが、有効にすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d0cf8-112">Trunks can be configured either with or without media bypass enabled, but we strongly recommend that you enable it.</span></span> <span data-ttu-id="d0cf8-113">詳細については、「 [Skype For business のメディアバイパスの計画](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0cf8-113">For details, see [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>
