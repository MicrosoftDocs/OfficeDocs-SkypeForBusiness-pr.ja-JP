---
title: Skype ビジネス サーバーでエンタープライズ VoIP のセキュリティおよび構成の前提条件
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
description: '概要: は、ビジネスのサーバーに、Skype でエンタープライズ VoIP のセキュリティおよび構成の前提条件について説明します。'
ms.openlocfilehash: 2738f1b39500673bd68b6c4f0c5cfdfb5b8b45d5
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "21017391"
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="a6622-103">Skype ビジネス サーバーでエンタープライズ VoIP のセキュリティおよび構成の前提条件</span><span class="sxs-lookup"><span data-stu-id="a6622-103">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="a6622-104">**の概要:** Business Server には、Skype でエンタープライズ VoIP のセキュリティおよび構成の前提条件について説明します。</span><span class="sxs-lookup"><span data-stu-id="a6622-104">**Summary:** Learn about the security and configuration prerequisites for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="a6622-105">エンタープライズ VoIP を展開するには、前に、インフラストラクチャが次のセキュリティ、ユーザー構成、およびシナリオ固有のハードウェアの前提条件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a6622-105">Before deploying Enterprise Voice, verify that your infrastructure meets the following security, user configuration, and scenario-specific hardware prerequisites.</span></span> 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a><span data-ttu-id="a6622-106">管理者権限と証明書インフラストラクチャ</span><span class="sxs-lookup"><span data-stu-id="a6622-106">Administrative rights and certificate infrastructure</span></span>

<span data-ttu-id="a6622-107">展開する前に、次を確認します。</span><span class="sxs-lookup"><span data-stu-id="a6622-107">Before deploying, check the following:</span></span>
  
- <span data-ttu-id="a6622-108">RTCUniversalServerAdmins グループのメンバーがエンタープライズ VoIP を展開する管理者にあります。</span><span class="sxs-lookup"><span data-stu-id="a6622-108">Administrators deploying Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>
    
- <span data-ttu-id="a6622-109">構成タスクを実行する管理者に十分な権限があること。</span><span class="sxs-lookup"><span data-stu-id="a6622-109">Administrators performing the configuration tasks must have adequate rights:</span></span>
    
  - <span data-ttu-id="a6622-110">**CsVoiceAdministrator:** この管理者の役割では、音声構成タスクの実行、音声アプリケーションの管理、エンド ユーザーへの音声ポリシーの割り当てができます。</span><span class="sxs-lookup"><span data-stu-id="a6622-110">**CsVoiceAdministrator:** This administrator role can perform voice configuration tasks, manage voice applications, and assign voice policies to end users.</span></span>
    
  - <span data-ttu-id="a6622-p101">**CsUserAdministrator:** この管理者の役割では、ユーザーのエンタープライズ VoIP を有効にするなど、ユーザーのプロパティを管理できます。 また、この管理者の役割では、ユーザー単位のポリシーの割り当て (アーカイブ ポリシー以外)、ユーザーの移動、共通領域電話やアナログ デバイスの管理を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="a6622-p101">**CsUserAdministrator:** This administrator role can manage user properties, such as enabling Enterprise Voice for a user. This administrator role can also assign per-user policies, with the exception of the archiving policy; move users; and manage common area phones and analog devices.</span></span>
    
  - <span data-ttu-id="a6622-113">**CsAdministrator:** この管理者の役割では、CsVoiceAdministrator と CsUserAdministrator のすべてのタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="a6622-113">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator and CsUserAdministrator.</span></span>
    
- <span data-ttu-id="a6622-114">マイクロソフトまたはサードパーティの CA (証明機関) インフラストラクチャのいずれかを使用して、MKI (Managed key infrastructure) が展開され、構成されていること。</span><span class="sxs-lookup"><span data-stu-id="a6622-114">Managed key infrastructure (MKI) is deployed and configured, by using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a6622-115">詳細については、Skype のビジネス サーバー用の証明書の要件は、[ビジネス サーバー 2015 の Skype の環境要件](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)や[ビジネス サーバー 2019 の Skype のサーバーの要件](../../../SfBServer2019/plan/system-requirements.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6622-115">For details about certificate requirements in Skype for Business Server, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  
## <a name="user-configuration"></a><span data-ttu-id="a6622-116">ユーザー構成</span><span class="sxs-lookup"><span data-stu-id="a6622-116">User configuration</span></span>

<span data-ttu-id="a6622-117">フロント エンドの展開時に各フロント エンド プールに仲介サーバーまたは Standard Edition サーバーを併設されている場合、それらのサーバーの役割用のファイルのインストール中にユーザー設定のエンタープライズ VoIP に必要なが自動的に構成されました。</span><span class="sxs-lookup"><span data-stu-id="a6622-117">If you collocated the Mediation Server with each Front End pool or Standard Edition server during Front End deployment, user settings necessary for Enterprise Voice were configured automatically during installation of the files for those server roles.</span></span>
  
<span data-ttu-id="a6622-118">展開プロセスを開始する前に、この時点でエンタープライズ VoIP のワークロードを新しく導入する場合は、エンタープライズ VoIP を有効にする各ユーザーのプライマリ電話番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="a6622-118">If you are newly deploying the Enterprise Voice workload at this time, before you begin the deployment process, designate a primary phone number for each user who you plan to enable for Enterprise Voice.</span></span> <span data-ttu-id="a6622-119">管理者は、この番号が一意であることを確認する責任があります。</span><span class="sxs-lookup"><span data-stu-id="a6622-119">As the administrator, you are responsible for ensuring that this number is unique.</span></span> <span data-ttu-id="a6622-120">実装では、前にすべてのプライマリ ・は電話番号を正規化する必要があります (正しく書式設定された) とビジネス サーバーのコントロール パネルの Skype を使用して各ユーザーの**回線 URI**のプロパティにコピーします。</span><span class="sxs-lookup"><span data-stu-id="a6622-120">Before implementation, all primary phone numbers must be normalized (correctly formatted) and copied to each user's **Line URI** property using Skype for Business Server Control Panel.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a6622-121">エンタープライズ VoIP の展開に必要な主要電話番号の例については、「[Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6622-121">For examples of primary phone numbers required for Enterprise Voice deployment, see [Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules).</span></span> 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a><span data-ttu-id="a6622-122">次のステップ: ファイルのインストールや PSTN 接続の構成</span><span class="sxs-lookup"><span data-stu-id="a6622-122">Next Steps: Install files or configure PSTN connectivity</span></span>

<span data-ttu-id="a6622-123">ソフトウェアとエンタープライズ VoIP に必要な環境を確認した後ことができますか。</span><span class="sxs-lookup"><span data-stu-id="a6622-123">After verifying software and environmental prerequisites for Enterprise Voice you can either:</span></span>
  
- <span data-ttu-id="a6622-124">[Skype ビジネス サーバーのトポロジ ビルダーでの仲介サーバーの展開](deploy-a-mediation-server.md)] で説明されているようですが、仲介サーバーがフロント エンドの一部としてインストールされているために、スタンドアロンの仲介サーバーまたはプールを展開する場合、仲介サーバーをインストールします。プールまたは Standard Edition サーバーの展開プロセスは 1 か所です。</span><span class="sxs-lookup"><span data-stu-id="a6622-124">Install the Mediation Server, as described in [Deploy a Mediation Server in Topology Builder in Skype for Business Server](deploy-a-mediation-server.md), but only if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>
    
- <span data-ttu-id="a6622-125">または、 [Skype ビジネス サーバー用に構成するトランク](configure-trunks.md)で説明するようにエンタープライズ VoIP ユーザーは、ルートの呼び出しに設定の構成を開始します。</span><span class="sxs-lookup"><span data-stu-id="a6622-125">Or, begin configuring settings to route calls for Enterprise Voice users, as described in [Configure trunks in Skype for Business Server](configure-trunks.md).</span></span>
    

