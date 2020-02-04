---
title: エンタープライズ VoIP のセキュリティおよび構成の前提条件
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
ms.openlocfilehash: 6530e00a942e2e839eaf4bc2d069212b746e2504
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732577"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="6fa36-102">Lync Server 2013 でのエンタープライズ Voip のセキュリティと構成の前提条件</span><span class="sxs-lookup"><span data-stu-id="6fa36-102">Security and configuration prerequisites for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6fa36-103">_**最終更新日:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="6fa36-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="6fa36-104">インフラストラクチャが以下のセキュリティ、ユーザー構成、およびシナリオ固有のハードウェアの前提条件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6fa36-104">Verify that your infrastructure meets the following security, user configuration, and scenario-specific hardware prerequisites.</span></span>

<div>

## <a name="administrative-rights-and-certificate-infrastructure"></a><span data-ttu-id="6fa36-105">管理者権限と証明書インフラストラクチャ</span><span class="sxs-lookup"><span data-stu-id="6fa36-105">Administrative Rights and Certificate Infrastructure</span></span>

<span data-ttu-id="6fa36-106">環境が、エンタープライズ Voip 展開プロセスで使用するために、次の管理者ユーザーグループと証明書インフラストラクチャを使って構成されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6fa36-106">Be sure that your environment is configured with the following administrative user groups and certificate infrastructure for use during the Enterprise Voice deployment process.</span></span>

  - <span data-ttu-id="6fa36-107">エンタープライズボイスを展開する管理者は、RTCUniversalServerAdmins グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fa36-107">Administrators deploying Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>

  - <span data-ttu-id="6fa36-108">構成タスクを実行する管理者に十分な権限があること。</span><span class="sxs-lookup"><span data-stu-id="6fa36-108">Administrators performing the configuration tasks must have adequate rights:</span></span>
    
      - <span data-ttu-id="6fa36-109">**CsVoiceAdministrator:** この管理者の役割では、音声構成タスクの実行、音声アプリケーションの管理、エンド ユーザーへの音声ポリシーの割り当てができます。</span><span class="sxs-lookup"><span data-stu-id="6fa36-109">**CsVoiceAdministrator:** This administrator role can perform voice configuration tasks, manage voice applications, and assign voice policies to end users.</span></span>
    
      - <span data-ttu-id="6fa36-p101">**CsUserAdministrator:** この管理者の役割では、ユーザーのエンタープライズ VoIP を有効にするなど、ユーザーのプロパティを管理できます。 また、この管理者の役割では、ユーザー単位のポリシーの割り当て (アーカイブ ポリシー以外)、ユーザーの移動、共通領域電話やアナログ デバイスの管理を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="6fa36-p101">**CsUserAdministrator:** This administrator role can manage user properties, such as enabling Enterprise Voice for a user. This administrator role can also assign per-user policies, with the exception of the archiving policy; move users; and manage common area phones and analog devices.</span></span>
    
      - <span data-ttu-id="6fa36-112">**CsAdministrator:** この管理者の役割では、CsVoiceAdministrator と CsUserAdministrator のすべてのタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="6fa36-112">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator and CsUserAdministrator.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="6fa36-113">委任により、リソースへの不要なアクセスを開かずに、Lync Server の展開により多くの管理者が参加できるようになります。</span><span class="sxs-lookup"><span data-stu-id="6fa36-113">Delegation enables more administrators to participate in your Lync Server deployment without opening up unnecessary access to resources.</span></span>

    
    </div>

  - <span data-ttu-id="6fa36-114">マイクロソフトまたはサードパーティの CA (証明機関) インフラストラクチャのいずれかを使用して、MKI (Managed key infrastructure) が展開され、構成されていること。</span><span class="sxs-lookup"><span data-stu-id="6fa36-114">Managed key infrastructure (MKI) is deployed and configured, by using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="6fa36-115">Lync Server の証明書の要件の詳細については、「計画ドキュメントの「 <A href="lync-server-2013-certificate-infrastructure-requirements.md">Lync server 2013 の証明書インフラストラクチャの要件</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fa36-115">For details about certificate requirements in Lync Server, see <A href="lync-server-2013-certificate-infrastructure-requirements.md">Certificate infrastructure requirements for Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="user-configuration"></a><span data-ttu-id="6fa36-116">ユーザー構成</span><span class="sxs-lookup"><span data-stu-id="6fa36-116">User Configuration</span></span>

<span data-ttu-id="6fa36-117">フロントエンドの展開時に、各フロントエンドプールまたは Standard Edition サーバーに仲介サーバーを併置した場合、エンタープライズボイスに必要なユーザー設定は、それらのサーバーロールのファイルのインストール中に自動的に構成されました。</span><span class="sxs-lookup"><span data-stu-id="6fa36-117">If you collocated the Mediation Server with each Front End pool or Standard Edition server during Front End deployment, user settings necessary for Enterprise Voice were configured automatically during installation of the files for those server roles.</span></span>

<span data-ttu-id="6fa36-118">現時点でエンタープライズ音声のワークロードを新しく展開している場合は、展開プロセスを開始する前に、エンタープライズ Voip を有効にする予定の各ユーザーのプライマリ電話番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="6fa36-118">If you are newly deploying the Enterprise Voice workload at this time, before you begin the deployment process, designate a primary phone number for each user who you plan to enable for Enterprise Voice.</span></span> <span data-ttu-id="6fa36-119">管理者は、この番号が一意であることを確認する責任があります。</span><span class="sxs-lookup"><span data-stu-id="6fa36-119">As the administrator, you are responsible for ensuring that this number is unique.</span></span> <span data-ttu-id="6fa36-120">実装前に、すべての主要な電話番号を正規化し (適切に書式設定)、Lync Server コントロールパネルを使用して、各ユーザーの**行 URI**プロパティにコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fa36-120">Before implementation, all primary phone numbers must be normalized (correctly formatted) and copied to each user’s **Line URI** property using Lync Server Control Panel.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="6fa36-121">エンタープライズ Voip の展開に必要な主要な電話番号の例については、計画ドキュメントの「lync server <A href="lync-server-2013-dial-plans-and-normalization-rules.md">2013 のダイヤルプランと正規化ルール</A>」セクションの「<A href="lync-server-2013-dial-plans-and-normalization-rules.md">ダイヤルプランと2013正規化</A>ルール」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fa36-121">For examples of primary phone numbers required for Enterprise Voice deployment, see the <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial plans and normalization rules in Lync Server 2013</A> section of <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial plans and normalization rules in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a><span data-ttu-id="6fa36-122">次の手順: ファイルをインストールする、または PSTN 接続を構成する</span><span class="sxs-lookup"><span data-stu-id="6fa36-122">Next Steps: Install Files or Configure PSTN Connectivity</span></span>

<span data-ttu-id="6fa36-123">エンタープライズ Voip のソフトウェアと環境の前提条件を確認した後、次のようなコンテンツを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="6fa36-123">After verifying software and environmental prerequisites for Enterprise Voice, you can use the following content to either:</span></span>

  - <span data-ttu-id="6fa36-124">「 [Lync server 2013 に「仲介サーバー用のファイルをインストール](lync-server-2013-install-the-files-for-mediation-server.md)する」の説明に従って、仲介サーバーをインストールします。ただし、仲介された場合は、仲介サーバーがフロントエンドプールまたは Standard Edition サーバー展開プロセスの一環としてインストールされているためです。</span><span class="sxs-lookup"><span data-stu-id="6fa36-124">Install the Mediation Server, as described in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md), but only if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>

  - <span data-ttu-id="6fa36-125">または、「 [Lync Server 2013 での trunks の構成](lync-server-2013-configuring-trunks.md)」で説明されているように、エンタープライズ voip ユーザーの呼び出しをルーティングするための設定の構成を開始します。</span><span class="sxs-lookup"><span data-stu-id="6fa36-125">Or, begin configuring settings to route calls for Enterprise Voice users, as described in [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

