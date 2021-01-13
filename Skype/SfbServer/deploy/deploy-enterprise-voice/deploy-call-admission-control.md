---
title: Skype for Business Server での通話受付管理の展開
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: 通話受付管理 (CAC) は、混雑したネットワーク上のユーザーの音声/ビデオ品質の低下を防ぐために、使用可能な帯域幅に基づいてリアルタイム セッションを確立できるかどうかを決定するソリューションです。
ms.openlocfilehash: af08afe02b1dc138aa38ded654d567aed6a09247
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836887"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="f4ae0-103">Skype for Business Server での通話受付管理の展開</span><span class="sxs-lookup"><span data-stu-id="f4ae0-103">Deploy call admission control in Skype for Business Server</span></span>
 
<span data-ttu-id="f4ae0-104">通話受付管理 (CAC) は、混雑したネットワーク上のユーザーの音声/ビデオ品質の低下を防ぐために、使用可能な帯域幅に基づいてリアルタイム セッションを確立できるかどうかを決定するソリューションです。</span><span class="sxs-lookup"><span data-stu-id="f4ae0-104">Call admission control (CAC) is a solution that determines whether a real-time session can be established based on the available bandwidth to help prevent poor audio/video quality for users on congested networks.</span></span> <span data-ttu-id="f4ae0-105">詳細については [、「Plan for call admission control in Skype for Business Server 」を参照してください](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)。</span><span class="sxs-lookup"><span data-stu-id="f4ae0-105">For more information, see [Plan for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span></span>
  
### <a name="to-deploy-call-admission-control"></a><span data-ttu-id="f4ae0-106">通話受付管理を展開するには</span><span class="sxs-lookup"><span data-stu-id="f4ae0-106">To deploy Call Admission Control</span></span>

1.  <span data-ttu-id="f4ae0-107">「例: Skype for Business Server での通話受付管理の要件の収集」で説明するように、エンタープライズ ネットワーク トポロジに必要なすべての [情報を収集します](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f4ae0-107">Gather all of the required information for your enterprise network topology, as described in [Example: Gathering requirements for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span></span>
    
2. <span data-ttu-id="f4ae0-108">まだ定義していない場合は、ネットワーク地域とサイトを定義し、サブネットをネットワーク サイトに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4ae0-108">If you have not done so already, you must define network regions and sites, and associate subnets with network sites.</span></span> <span data-ttu-id="f4ae0-109">詳細については [、「Skype for Business でのネットワーク地域、サイト、サブネットの展開」を参照してください](deploy-network.md)。</span><span class="sxs-lookup"><span data-stu-id="f4ae0-109">For details, see [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span>
    
3. <span data-ttu-id="f4ae0-110">「Skype for Business Server での帯域幅ポリシー プロファイルの作成」の説明に示されている帯域幅ポリシー プロファイル [の作成](create-bandwidth-policy-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="f4ae0-110">Create bandwidth policy profiles, as detailed in [Create bandwidth policy profiles in Skype for Business Server](create-bandwidth-policy-profiles.md)</span></span>
    
4. <span data-ttu-id="f4ae0-111">「Skype for Business Server でのネットワーク地域リンクの作成 [」で説明されているネットワーク地域リンクを作成します](create-network-region-links.md)。</span><span class="sxs-lookup"><span data-stu-id="f4ae0-111">Create network region links, as detailed in [Create network region links in Skype for Business Server](create-network-region-links.md).</span></span>
    
5. <span data-ttu-id="f4ae0-112">「Skype for Business Server でのネットワーク地域間ルートの作成」で説明されているネットワーク地域間ルート [を作成します](create-network-interregional-routes.md)。</span><span class="sxs-lookup"><span data-stu-id="f4ae0-112">Create network inter-region routes, as detailed in [Create network interregional routes in Skype for Business Server](create-network-interregional-routes.md).</span></span>
    
6. <span data-ttu-id="f4ae0-113">「Skype for Business Server でネットワーク サイト間ポリシーを作成する」の説明に従って、 [ネットワーク サイト間ポリシーを作成します](create-network-intersite-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="f4ae0-113">Create network intersite policies, as detailed in [Create network intersite policies in Skype for Business Server](create-network-intersite-policies.md).</span></span>
    
7. <span data-ttu-id="f4ae0-114">「Skype for Business Server で通話受付管理を有効にする」の説明に示されている方法で、 [通話受付管理を有効にします](enable-call-admission-control.md)。</span><span class="sxs-lookup"><span data-stu-id="f4ae0-114">Enable call admission control, as detailed in [Enable call admission control in Skype for Business Server](enable-call-admission-control.md).</span></span>
    
8. <span data-ttu-id="f4ae0-115">最終的な設定を確認して、すべてが正しく設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f4ae0-115">Check a few final settings, to make sure everything is set up correctly.</span></span> <span data-ttu-id="f4ae0-116">詳細については、「 [通話受付管理の展開: Skype for Business Server の最終チェックリスト」を参照してください](final-checklist.md)。</span><span class="sxs-lookup"><span data-stu-id="f4ae0-116">For details, see [Call admission control deployment: final checklist for Skype for Business Server](final-checklist.md).</span></span>
    

