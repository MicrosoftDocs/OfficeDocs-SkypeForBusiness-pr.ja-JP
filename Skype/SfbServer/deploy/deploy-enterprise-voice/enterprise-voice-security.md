---
title: Skype for Business Server での エンタープライズ VoIPのセキュリティと構成の前提条件
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
ms.assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
description: '概要: Skype for Business Server のセキュリティと構成エンタープライズ VoIPについて説明します。'
ms.openlocfilehash: 77efbf231f83c6d3c31254c9ab742de7e2b226e9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830847"
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="4634f-103">Skype for Business Server での エンタープライズ VoIPのセキュリティと構成の前提条件</span><span class="sxs-lookup"><span data-stu-id="4634f-103">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="4634f-104">**概要:** Skype for Business Server のセキュリティと構成の前提条件エンタープライズ VoIPについて説明します。</span><span class="sxs-lookup"><span data-stu-id="4634f-104">**Summary:** Learn about the security and configuration prerequisites for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="4634f-105">アプリケーションを展開するエンタープライズ VoIP、インフラストラクチャが次のセキュリティ、ユーザー構成、およびシナリオ固有のハードウェア前提条件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4634f-105">Before deploying Enterprise Voice, verify that your infrastructure meets the following security, user configuration, and scenario-specific hardware prerequisites.</span></span> 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a><span data-ttu-id="4634f-106">管理者権限と証明書インフラストラクチャ</span><span class="sxs-lookup"><span data-stu-id="4634f-106">Administrative rights and certificate infrastructure</span></span>

<span data-ttu-id="4634f-107">展開する前に、次の確認を行います。</span><span class="sxs-lookup"><span data-stu-id="4634f-107">Before deploying, check the following:</span></span>
  
- <span data-ttu-id="4634f-108">エンタープライズ VoIP を展開する管理者が RTCUniversalServerAdmins グループのメンバーであること。</span><span class="sxs-lookup"><span data-stu-id="4634f-108">Administrators deploying Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>
    
- <span data-ttu-id="4634f-109">構成タスクを実行する管理者に十分な権限があること。</span><span class="sxs-lookup"><span data-stu-id="4634f-109">Administrators performing the configuration tasks must have adequate rights:</span></span>
    
  - <span data-ttu-id="4634f-110">**CsVoiceAdministrator:** この管理者の役割では、音声構成タスクの実行、音声アプリケーションの管理、エンド ユーザーへの音声ポリシーの割り当てができます。</span><span class="sxs-lookup"><span data-stu-id="4634f-110">**CsVoiceAdministrator:** This administrator role can perform voice configuration tasks, manage voice applications, and assign voice policies to end users.</span></span>
    
  - <span data-ttu-id="4634f-p101">**CsUserAdministrator:** この管理者の役割では、ユーザーのエンタープライズ VoIP を有効にするなど、ユーザーのプロパティを管理できます。 また、この管理者の役割では、ユーザー単位のポリシーの割り当て (アーカイブ ポリシー以外)、ユーザーの移動、共通領域電話やアナログ デバイスの管理を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="4634f-p101">**CsUserAdministrator:** This administrator role can manage user properties, such as enabling Enterprise Voice for a user. This administrator role can also assign per-user policies, with the exception of the archiving policy; move users; and manage common area phones and analog devices.</span></span>
    
  - <span data-ttu-id="4634f-113">**CsAdministrator:** この管理者の役割では、CsVoiceAdministrator と CsUserAdministrator のすべてのタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="4634f-113">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator and CsUserAdministrator.</span></span>
    
- <span data-ttu-id="4634f-114">マイクロソフトまたはサードパーティの CA (証明機関) インフラストラクチャのいずれかを使用して、MKI (Managed key infrastructure) が展開され、構成されていること。</span><span class="sxs-lookup"><span data-stu-id="4634f-114">Managed key infrastructure (MKI) is deployed and configured, by using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4634f-115">Skype for Business Server の証明書要件の詳細については [、「Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4634f-115">For details about certificate requirements in Skype for Business Server, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  
## <a name="user-configuration"></a><span data-ttu-id="4634f-116">ユーザー構成</span><span class="sxs-lookup"><span data-stu-id="4634f-116">User configuration</span></span>

<span data-ttu-id="4634f-117">フロントエンドの展開中に仲介サーバーを各フロントエンド プールまたは Standard Edition サーバーと一緒に配置した場合、これらのサーバーの役割のファイルのインストール中に、エンタープライズ VoIP に必要なユーザー設定が自動的に構成されました。</span><span class="sxs-lookup"><span data-stu-id="4634f-117">If you collocated the Mediation Server with each Front End pool or Standard Edition server during Front End deployment, user settings necessary for Enterprise Voice were configured automatically during installation of the files for those server roles.</span></span>
  
<span data-ttu-id="4634f-118">この時点でエンタープライズ VoIP のワークロードを新たに展開する場合、展開プロセスを開始する前に、エンタープライズ VoIP を有効にする各ユーザーの主要電話番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="4634f-118">If you are newly deploying the Enterprise Voice workload at this time, before you begin the deployment process, designate a primary phone number for each user who you plan to enable for Enterprise Voice.</span></span> <span data-ttu-id="4634f-119">管理者は、この番号が一意であることを確認する責任があります。</span><span class="sxs-lookup"><span data-stu-id="4634f-119">As the administrator, you are responsible for ensuring that this number is unique.</span></span> <span data-ttu-id="4634f-120">実装する前に、すべての主要電話番号を正規化 (正しい形式) にし、Skype for Business Server コントロール パネルを使用して各ユーザーの **回線 URI** プロパティにコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4634f-120">Before implementation, all primary phone numbers must be normalized (correctly formatted) and copied to each user's **Line URI** property using Skype for Business Server Control Panel.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4634f-121">展開に必要な主要電話番号の例については、「エンタープライズ VoIP正規化ルール」を [参照してください](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules)。</span><span class="sxs-lookup"><span data-stu-id="4634f-121">For examples of primary phone numbers required for Enterprise Voice deployment, see [Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules).</span></span> 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a><span data-ttu-id="4634f-122">次の手順: ファイルをインストールするか、PSTN 接続を構成する</span><span class="sxs-lookup"><span data-stu-id="4634f-122">Next Steps: Install files or configure PSTN connectivity</span></span>

<span data-ttu-id="4634f-123">ソフトウェアと環境の前提条件を確認したエンタープライズ VoIP、次のいずれかを実行できます。</span><span class="sxs-lookup"><span data-stu-id="4634f-123">After verifying software and environmental prerequisites for Enterprise Voice you can either:</span></span>
  
- <span data-ttu-id="4634f-124">[「Skype for Business Server](deploy-a-mediation-server.md)のトポロジ ビルダーでの仲介サーバーの展開」の説明に従って、仲介サーバーをインストールします。ただし、仲介サーバーは、フロントエンド プールまたは Standard Edition サーバーの展開プロセスの一部としてインストールされる場合に、スタンドアロンの仲介サーバーまたはプールを展開する場合にのみインストールします。</span><span class="sxs-lookup"><span data-stu-id="4634f-124">Install the Mediation Server, as described in [Deploy a Mediation Server in Topology Builder in Skype for Business Server](deploy-a-mediation-server.md), but only if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>
    
- <span data-ttu-id="4634f-125">または、「Skype for Business Server でトランクを構成する」の説明に従って、エンタープライズ VoIP ユーザーの通話をルーティングするように設定 [の構成を開始します](configure-trunks.md)。</span><span class="sxs-lookup"><span data-stu-id="4634f-125">Or, begin configuring settings to route calls for Enterprise Voice users, as described in [Configure trunks in Skype for Business Server](configure-trunks.md).</span></span>
    

