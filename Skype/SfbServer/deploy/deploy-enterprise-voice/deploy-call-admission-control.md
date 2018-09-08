---
title: ビジネス サーバーの Skype で通話受付制御を展開します。
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: 呼び出しの受付制御 (CAC) は、リアルタイム セッションを確立できるかどうかを決定するためのソリューションは、混雑したネットワーク上のユーザーのオーディオ/ビデオ品質の低下を防止するために利用可能な帯域幅に基づいています。
ms.openlocfilehash: 3cf2c63de5eb4e64eb33f690b003ea897a533893
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887500"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="e8ad3-103">ビジネス サーバーの Skype で通話受付制御を展開します。</span><span class="sxs-lookup"><span data-stu-id="e8ad3-103">Deploy call admission control in Skype for Business Server</span></span>
 
<span data-ttu-id="e8ad3-104">呼び出しの受付制御 (CAC) は、リアルタイム セッションを確立できるかどうかを決定するためのソリューションは、混雑したネットワーク上のユーザーのオーディオ/ビデオ品質の低下を防止するために利用可能な帯域幅に基づいています。</span><span class="sxs-lookup"><span data-stu-id="e8ad3-104">Call admission control (CAC) is a solution that determines whether a real-time session can be established based on the available bandwidth to help prevent poor audio/video quality for users on congested networks.</span></span> <span data-ttu-id="e8ad3-105">詳細については、[ビジネス サーバーの Skype で通話受付制御の計画](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8ad3-105">For more information, see [Plan for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span></span>
  
### <a name="to-deploy-call-admission-control"></a><span data-ttu-id="e8ad3-106">通話管理受付サービスを展開するには</span><span class="sxs-lookup"><span data-stu-id="e8ad3-106">To deploy Call Admission Control</span></span>

1.  <span data-ttu-id="e8ad3-107">説明したように、エンタープライズ ネットワーク トポロジに必要な情報のすべてを収集[の使用例: ビジネス サーバー Skype の呼受付制御の要件の収集](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e8ad3-107">Gather all of the required information for your enterprise network topology, as described in [Example: Gathering requirements for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span></span>
    
2. <span data-ttu-id="e8ad3-108">まだ行っていない場合は、ネットワーク地域とサイトを定義して、サブネットをネットワーク サイトに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8ad3-108">If you have not done so already, you must define network regions and sites, and associate subnets with network sites.</span></span> <span data-ttu-id="e8ad3-109">詳細については、[ネットワークの領域を展開、サイトとサブネットでビジネス用の Skype](deploy-network.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8ad3-109">For details, see [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span>
    
3. <span data-ttu-id="e8ad3-110">帯域幅[ビジネス サーバーの Skype で帯域幅ポリシー プロファイルを作成する](create-bandwidth-policy-profiles.md)を参考に、ポリシー プロファイルの作成します。</span><span class="sxs-lookup"><span data-stu-id="e8ad3-110">Create bandwidth policy profiles, as detailed in [Create bandwidth policy profiles in Skype for Business Server](create-bandwidth-policy-profiles.md)</span></span>
    
4. <span data-ttu-id="e8ad3-111">[Skype ビジネス サーバー用のネットワーク地域リンクの作成](create-network-region-links.md)の詳細と、ネットワーク地域リンクを作成します。</span><span class="sxs-lookup"><span data-stu-id="e8ad3-111">Create network region links, as detailed in [Create network region links in Skype for Business Server](create-network-region-links.md).</span></span>
    
5. <span data-ttu-id="e8ad3-112">[Skype ビジネス サーバー用のネットワーク interregional ルートの作成](create-network-interregional-routes.md)の参考に、ネットワーク間の地域ルートを作成します。</span><span class="sxs-lookup"><span data-stu-id="e8ad3-112">Create network inter-region routes, as detailed in [Create network interregional routes in Skype for Business Server](create-network-interregional-routes.md).</span></span>
    
6. <span data-ttu-id="e8ad3-113">[Skype ビジネス サーバー用のネットワーク サイト間ポリシーの作成](create-network-intersite-policies.md)の参考に、ネットワーク サイト間ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="e8ad3-113">Create network intersite policies, as detailed in [Create network intersite policies in Skype for Business Server](create-network-intersite-policies.md).</span></span>
    
7. <span data-ttu-id="e8ad3-114">[ビジネス サーバーの Skype で通話受付制御を有効にする](enable-call-admission-control.md)を参考に、呼び出しの受付制御を有効にします。</span><span class="sxs-lookup"><span data-stu-id="e8ad3-114">Enable call admission control, as detailed in [Enable call admission control in Skype for Business Server](enable-call-admission-control.md).</span></span>
    
8. <span data-ttu-id="e8ad3-115">いくつかの最終設定をチェックして、すべてが正しく設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e8ad3-115">Check a few final settings, to make sure everything is set up correctly.</span></span> <span data-ttu-id="e8ad3-116">詳細についてを参照してください[電話受付制御の展開: ビジネス サーバーの Skype の最終チェックリスト](final-checklist.md)。</span><span class="sxs-lookup"><span data-stu-id="e8ad3-116">For details, see [Call admission control deployment: final checklist for Skype for Business Server](final-checklist.md).</span></span>
    

