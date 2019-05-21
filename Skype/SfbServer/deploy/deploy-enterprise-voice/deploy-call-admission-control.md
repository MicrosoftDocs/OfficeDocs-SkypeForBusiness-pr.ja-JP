---
title: Skype for Business Server で通話受付制御を展開する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: 通話受付制御 (CAC) は、使用可能な帯域幅に基づいてリアルタイムのセッションを確立して、混雑したネットワークのユーザーに対して低品質のオーディオ/ビデオ品質を防ぐことができるかどうかを決定するソリューションです。
ms.openlocfilehash: 7f7f8dee4e25061533564ce517f797281bef042e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280440"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="4a8a0-103">Skype for Business Server で通話受付制御を展開する</span><span class="sxs-lookup"><span data-stu-id="4a8a0-103">Deploy call admission control in Skype for Business Server</span></span>
 
<span data-ttu-id="4a8a0-104">通話受付制御 (CAC) は、使用可能な帯域幅に基づいてリアルタイムのセッションを確立して、混雑したネットワークのユーザーに対して低品質のオーディオ/ビデオ品質を防ぐことができるかどうかを決定するソリューションです。</span><span class="sxs-lookup"><span data-stu-id="4a8a0-104">Call admission control (CAC) is a solution that determines whether a real-time session can be established based on the available bandwidth to help prevent poor audio/video quality for users on congested networks.</span></span> <span data-ttu-id="4a8a0-105">詳細については、「 [Skype For Business Server での通話受付制御の計画](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a8a0-105">For more information, see [Plan for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span></span>
  
### <a name="to-deploy-call-admission-control"></a><span data-ttu-id="4a8a0-106">通話管理受付サービスを展開するには</span><span class="sxs-lookup"><span data-stu-id="4a8a0-106">To deploy Call Admission Control</span></span>

1.  <span data-ttu-id="4a8a0-107">「[例: Skype For Business Server での通話受付制御の要件の収集](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)」の説明に従って、エンタープライズネットワークトポロジに必要なすべての情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="4a8a0-107">Gather all of the required information for your enterprise network topology, as described in [Example: Gathering requirements for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span></span>
    
2. <span data-ttu-id="4a8a0-108">まだ行っていない場合は、ネットワーク地域とサイトを定義して、サブネットをネットワーク サイトに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a8a0-108">If you have not done so already, you must define network regions and sites, and associate subnets with network sites.</span></span> <span data-ttu-id="4a8a0-109">詳細については、「 [Skype For business でネットワークのリージョン、サイト、サブネットを展開](deploy-network.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a8a0-109">For details, see [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span>
    
3. <span data-ttu-id="4a8a0-110">「 [Skype For Business Server での帯域幅ポリシープロファイルの作成](create-bandwidth-policy-profiles.md)」で詳しく説明するように、帯域幅ポリシープロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="4a8a0-110">Create bandwidth policy profiles, as detailed in [Create bandwidth policy profiles in Skype for Business Server](create-bandwidth-policy-profiles.md)</span></span>
    
4. <span data-ttu-id="4a8a0-111">「 [Skype For Business Server でのネットワーク領域リンクの作成](create-network-region-links.md)」で詳しく説明するように、ネットワーク領域のリンクを作成します。</span><span class="sxs-lookup"><span data-stu-id="4a8a0-111">Create network region links, as detailed in [Create network region links in Skype for Business Server](create-network-region-links.md).</span></span>
    
5. <span data-ttu-id="4a8a0-112">「 [Skype For Business Server でネットワーク間の地域ルートを作成する](create-network-interregional-routes.md)」で詳しく説明するように、ネットワーク間のネットワーク間ルートを作成します。</span><span class="sxs-lookup"><span data-stu-id="4a8a0-112">Create network inter-region routes, as detailed in [Create network interregional routes in Skype for Business Server](create-network-interregional-routes.md).</span></span>
    
6. <span data-ttu-id="4a8a0-113">「 [Skype For Business Server でのネットワークのサイト間ポリシーの作成](create-network-intersite-policies.md)」で詳しく説明するように、ネットワークのサイト間ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="4a8a0-113">Create network intersite policies, as detailed in [Create network intersite policies in Skype for Business Server](create-network-intersite-policies.md).</span></span>
    
7. <span data-ttu-id="4a8a0-114">「 [Skype For Business Server で通話受付制御を有効にする](enable-call-admission-control.md)」で詳しく説明するように、通話受付制御を有効にします。</span><span class="sxs-lookup"><span data-stu-id="4a8a0-114">Enable call admission control, as detailed in [Enable call admission control in Skype for Business Server](enable-call-admission-control.md).</span></span>
    
8. <span data-ttu-id="4a8a0-115">いくつかの最終設定をチェックして、すべてが正しく設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4a8a0-115">Check a few final settings, to make sure everything is set up correctly.</span></span> <span data-ttu-id="4a8a0-116">詳細については、「[通話受付制御の展開: Skype For Business Server の最終チェックリスト](final-checklist.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a8a0-116">For details, see [Call admission control deployment: final checklist for Skype for Business Server](final-checklist.md).</span></span>
    

