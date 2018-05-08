---
title: Skype for Business Server 2015 での通話受付管理の展開
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: 呼び出しの受付制御 (CAC) は、リアルタイム セッションを確立できるかどうかを決定するためのソリューションは、混雑したネットワーク上のユーザーのオーディオ/ビデオ品質の低下を防止するために利用可能な帯域幅に基づいています。 詳細についてを参照してください計画 Skype の呼受付制御のビジネス サーバー 2015 のです。
ms.openlocfilehash: 471bc7abe8a79f2ef4b4cc322450dbc7c639129f
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="deploy-call-admission-control-in-skype-for-business-server-2015"></a><span data-ttu-id="f9d0f-104">Skype for Business Server 2015 での通話受付管理の展開</span><span class="sxs-lookup"><span data-stu-id="f9d0f-104">Deploy call admission control in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f9d0f-105">呼び出しの受付制御 (CAC) は、リアルタイム セッションを確立できるかどうかを決定するためのソリューションは、混雑したネットワーク上のユーザーのオーディオ/ビデオ品質の低下を防止するために利用可能な帯域幅に基づいています。</span><span class="sxs-lookup"><span data-stu-id="f9d0f-105">Call admission control (CAC) is a solution that determines whether a real-time session can be established based on the available bandwidth to help prevent poor audio/video quality for users on congested networks.</span></span> <span data-ttu-id="f9d0f-106">詳細については、[ビジネス サーバー 2015 の Skype の呼受付制御の計画](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9d0f-106">For more information, see [Plan for call admission control in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span></span>
  
### <a name="to-deploy-call-admission-control"></a><span data-ttu-id="f9d0f-107">通話管理受付サービスを展開するには</span><span class="sxs-lookup"><span data-stu-id="f9d0f-107">To deploy Call Admission Control</span></span>

1.  <span data-ttu-id="f9d0f-108">説明したように、エンタープライズ ネットワーク トポロジに必要な情報のすべてを収集[の使用例: ビジネス サーバー 2015 の Skype の呼受付制御の要件を収集する](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="f9d0f-108">Gather all of the required information for your enterprise network topology, as described in [Example: Gathering requirements for call admission control in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span></span>
    
2. <span data-ttu-id="f9d0f-109">まだ行っていない場合は、ネットワーク地域とサイトを定義して、サブネットをネットワーク サイトに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9d0f-109">If you have not done so already, you must define network regions and sites, and associate subnets with network sites.</span></span> <span data-ttu-id="f9d0f-110">詳細については、[ネットワークの領域を展開、サイト、およびビジネス 2015年の Skype のサブネットを](deploy-network.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9d0f-110">For details, see [Deploy network regions, sites and subnets in Skype for Business 2015](deploy-network.md).</span></span>
    
3. <span data-ttu-id="f9d0f-111">帯域幅[ビジネス サーバー 2015 の Skype で帯域幅ポリシー プロファイルを作成する](create-bandwidth-policy-profiles.md)を参考に、ポリシー プロファイルの作成します。</span><span class="sxs-lookup"><span data-stu-id="f9d0f-111">Create bandwidth policy profiles, as detailed in [Create bandwidth policy profiles in Skype for Business Server 2015](create-bandwidth-policy-profiles.md)</span></span>
    
4. <span data-ttu-id="f9d0f-112">[ビジネス サーバー 2015 の Skype のネットワーク地域リンクの作成](create-network-region-links.md)の詳細と、ネットワーク地域リンクを作成します。</span><span class="sxs-lookup"><span data-stu-id="f9d0f-112">Create network region links, as detailed in [Create network region links in Skype for Business Server 2015](create-network-region-links.md).</span></span>
    
5. <span data-ttu-id="f9d0f-113">[ビジネス サーバー 2015 の Skype のネットワーク interregional ルートの作成](create-network-interregional-routes.md)の参考に、ネットワーク間の地域ルートを作成します。</span><span class="sxs-lookup"><span data-stu-id="f9d0f-113">Create network inter-region routes, as detailed in [Create network interregional routes in Skype for Business Server 2015](create-network-interregional-routes.md).</span></span>
    
6. <span data-ttu-id="f9d0f-114">[ビジネス サーバー 2015 の Skype のネットワーク サイト間ポリシーの作成](create-network-intersite-policies.md)の参考に、ネットワーク サイト間ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="f9d0f-114">Create network intersite policies, as detailed in [Create network intersite policies in Skype for Business Server 2015](create-network-intersite-policies.md).</span></span>
    
7. <span data-ttu-id="f9d0f-115">[ビジネス サーバー 2015 の Skype で通話受付制御を有効にする](enable-call-admission-control.md)を参考に、呼び出しの受付制御を有効にします。</span><span class="sxs-lookup"><span data-stu-id="f9d0f-115">Enable call admission control, as detailed in [Enable call admission control in Skype for Business Server 2015](enable-call-admission-control.md).</span></span>
    
8. <span data-ttu-id="f9d0f-116">いくつかの最終設定をチェックして、すべてが正しく設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f9d0f-116">Check a few final settings, to make sure everything is set up correctly.</span></span> <span data-ttu-id="f9d0f-117">詳細についてを参照してください[電話受付制御の展開: ビジネス サーバー 2015 の Skype の最終チェックリスト](final-checklist.md)。</span><span class="sxs-lookup"><span data-stu-id="f9d0f-117">For details, see [Call admission control deployment: final checklist for Skype for Business Server 2015](final-checklist.md).</span></span>
    

