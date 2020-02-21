---
title: エンタープライズ Voip のセキュリティおよび構成の前提条件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Security and configuration prerequisites for Enterprise Voice
ms:assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398221(v=OCS.15)
ms:contentKeyID: 48183495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d8aec487e2ef5c6f5a756305a6e44df0c31cbec0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200933"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="9c027-102">Lync Server 2013 でのエンタープライズ Voip のセキュリティおよび構成の前提条件</span><span class="sxs-lookup"><span data-stu-id="9c027-102">Security and configuration prerequisites for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c027-103">_**トピックの最終更新日:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="9c027-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="9c027-104">インフラストラクチャが次のセキュリティ、ユーザー構成、およびシナリオ固有のハードウェアの前提条件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9c027-104">Verify that your infrastructure meets the following security, user configuration, and scenario-specific hardware prerequisites.</span></span>

<div>

## <a name="administrative-rights-and-certificate-infrastructure"></a><span data-ttu-id="9c027-105">管理者権限と証明書インフラストラクチャ</span><span class="sxs-lookup"><span data-stu-id="9c027-105">Administrative Rights and Certificate Infrastructure</span></span>

<span data-ttu-id="9c027-106">エンタープライズ VoIP の展開プロセス時に使用する次の管理者ユーザー グループと証明書インフラストラクチャで環境が構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9c027-106">Be sure that your environment is configured with the following administrative user groups and certificate infrastructure for use during the Enterprise Voice deployment process.</span></span>

  - <span data-ttu-id="9c027-107">エンタープライズ VoIP を展開する管理者が RTCUniversalServerAdmins グループのメンバーであること。</span><span class="sxs-lookup"><span data-stu-id="9c027-107">Administrators deploying Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>

  - <span data-ttu-id="9c027-108">構成タスクを実行する管理者に十分な権限があること。</span><span class="sxs-lookup"><span data-stu-id="9c027-108">Administrators performing the configuration tasks must have adequate rights:</span></span>
    
      - <span data-ttu-id="9c027-109">\*\*CsVoiceAdministrator: \*\*この管理者の役割では、音声構成タスクの実行、音声アプリケーションの管理、エンド ユーザーへの音声ポリシーの割り当てができます。</span><span class="sxs-lookup"><span data-stu-id="9c027-109">**CsVoiceAdministrator:** This administrator role can perform voice configuration tasks, manage voice applications, and assign voice policies to end users.</span></span>
    
      - <span data-ttu-id="9c027-p101">\*\*CsUserAdministrator: \*\*この管理者の役割では、ユーザーのエンタープライズ VoIP を有効にするなど、ユーザーのプロパティを管理できます。 また、この管理者の役割では、ユーザー単位のポリシーの割り当て (アーカイブ ポリシー以外)、ユーザーの移動、共通領域電話やアナログ デバイスの管理を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="9c027-p101">**CsUserAdministrator:** This administrator role can manage user properties, such as enabling Enterprise Voice for a user. This administrator role can also assign per-user policies, with the exception of the archiving policy; move users; and manage common area phones and analog devices.</span></span>
    
      - <span data-ttu-id="9c027-112">\*\*CsAdministrator: \*\*この管理者の役割では、CsVoiceAdministrator と CsUserAdministrator のすべてのタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="9c027-112">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator and CsUserAdministrator.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="9c027-113">委任を使用すると、リソースへの不必要なアクセスを開かなくても、Lync Server の展開により多くの管理者が参加できます。</span><span class="sxs-lookup"><span data-stu-id="9c027-113">Delegation enables more administrators to participate in your Lync Server deployment without opening up unnecessary access to resources.</span></span>

    
    </div>

  - <span data-ttu-id="9c027-114">マイクロソフトまたはサードパーティの CA (証明機関) インフラストラクチャのいずれかを使用して、MKI (Managed key infrastructure) が展開され、構成されていること。</span><span class="sxs-lookup"><span data-stu-id="9c027-114">Managed key infrastructure (MKI) is deployed and configured, by using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="9c027-115">Lync Server での証明書の要件の詳細については、「計画」のドキュメントの「 <A href="lync-server-2013-certificate-infrastructure-requirements.md">Lync server 2013 の証明書インフラストラクチャ要件</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c027-115">For details about certificate requirements in Lync Server, see <A href="lync-server-2013-certificate-infrastructure-requirements.md">Certificate infrastructure requirements for Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="user-configuration"></a><span data-ttu-id="9c027-116">ユーザー構成</span><span class="sxs-lookup"><span data-stu-id="9c027-116">User Configuration</span></span>

<span data-ttu-id="9c027-117">フロントエンドの展開時に、各フロントエンドプールまたは Standard Edition サーバーに仲介サーバーを併置した場合、エンタープライズ Voip に必要なユーザー設定は、それらのサーバーの役割のファイルのインストール時に自動的に構成されました。</span><span class="sxs-lookup"><span data-stu-id="9c027-117">If you collocated the Mediation Server with each Front End pool or Standard Edition server during Front End deployment, user settings necessary for Enterprise Voice were configured automatically during installation of the files for those server roles.</span></span>

<span data-ttu-id="9c027-118">この時点でエンタープライズ VoIP のワークロードを新たに展開する場合、展開プロセスを開始する前に、エンタープライズ VoIP を有効にする各ユーザーの主要電話番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="9c027-118">If you are newly deploying the Enterprise Voice workload at this time, before you begin the deployment process, designate a primary phone number for each user who you plan to enable for Enterprise Voice.</span></span> <span data-ttu-id="9c027-119">管理者は、この番号が一意であることを確認する責任があります。</span><span class="sxs-lookup"><span data-stu-id="9c027-119">As the administrator, you are responsible for ensuring that this number is unique.</span></span> <span data-ttu-id="9c027-120">実装の前に、Lync Server コントロールパネルを使用して、すべてのプライマリ電話番号を正規化 (整形) し、各ユーザーの**回線 URI**プロパティにコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c027-120">Before implementation, all primary phone numbers must be normalized (correctly formatted) and copied to each user’s **Line URI** property using Lync Server Control Panel.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="9c027-121">エンタープライズ Voip の展開に必要な主要電話番号の例については、「計画」のドキュメントの「 <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Lync server 2013</A>でのダイヤルプランと正規化ルール」セクション<A href="lync-server-2013-dial-plans-and-normalization-rules.md">と「lync server 2013 の正規化ルール</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c027-121">For examples of primary phone numbers required for Enterprise Voice deployment, see the <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial plans and normalization rules in Lync Server 2013</A> section of <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial plans and normalization rules in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a><span data-ttu-id="9c027-122">次のステップ:  ファイルのインストールや PSTN 接続の構成</span><span class="sxs-lookup"><span data-stu-id="9c027-122">Next Steps: Install Files or Configure PSTN Connectivity</span></span>

<span data-ttu-id="9c027-123">エンタープライズ VoIP のソフトウェアおよび環境の前提条件を確認したら、以下の情報を参照して次のいずれかの操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="9c027-123">After verifying software and environmental prerequisites for Enterprise Voice, you can use the following content to either:</span></span>

  - <span data-ttu-id="9c027-124">「 [Lync server 2013 の仲介サーバーのファイル](lync-server-2013-install-the-files-for-mediation-server.md)をインストールする」の説明に従って、仲介サーバーをインストールします。これは、仲介サーバーがフロントエンドプールまたは Standard Edition サーバー展開プロセスの一部としてインストールされているためで、スタンドアロンの仲介サーバーまたはプールを展開する場合に限られます。</span><span class="sxs-lookup"><span data-stu-id="9c027-124">Install the Mediation Server, as described in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md), but only if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>

  - <span data-ttu-id="9c027-125">または、「[構成トランク In Lync Server 2013](lync-server-2013-configuring-trunks.md)」の説明に従って、エンタープライズ voip ユーザーの通話をルーティングするための設定の構成を開始します。</span><span class="sxs-lookup"><span data-stu-id="9c027-125">Or, begin configuring settings to route calls for Enterprise Voice users, as described in [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

