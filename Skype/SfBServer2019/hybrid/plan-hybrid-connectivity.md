---
title: ハイブリッド接続を計画します。
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: ビジネス オンラインまたはチームの業務サーバーの Skype と Skype との間のハイブリッドの接続を実装するための考慮事項を計画しています。
ms.openlocfilehash: d3726c2975056499ec61e12b4dd8d63f63beb3e9
ms.sourcegitcommit: a54864c3fcd1b8d240d0f7f2ccf68f8cba566e47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2018
ms.locfileid: "25849363"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-office-365"></a><span data-ttu-id="35861-103">Skype ビジネス サーバーと Office 365 のハイブリッド接続を計画します。</span><span class="sxs-lookup"><span data-stu-id="35861-103">Plan hybrid connectivity between Skype for Business Server and Office 365</span></span>

## <a name="overview"></a><span data-ttu-id="35861-104">概要</span><span class="sxs-lookup"><span data-stu-id="35861-104">Overview</span></span>

<span data-ttu-id="35861-105">業務サーバーおよびチームの Skype または Skype のオンライン ビジネスの間のハイブリッドの接続を計画する方法については、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="35861-105">Read this topic to learn how to plan hybrid connectivity between Skype for Business Server and Teams or Skype for Business Online.</span></span> <span data-ttu-id="35861-106">ハイブリッド接続の設定は、最初の手順で、オンプレミス環境をクラウドに移行です。</span><span class="sxs-lookup"><span data-stu-id="35861-106">Setting up hybrid connectivity is the first step in in moving your on-premises environment to the cloud.</span></span>

<span data-ttu-id="35861-107">いる場合、オンプレミス環境のチームを使用している、設置型のビジネス用の Skype をホームとしているユーザーにはビジネス ユーザーは、Skype で相互運用性も、フェデレーション組織のユーザーと通信する機能はありません。</span><span class="sxs-lookup"><span data-stu-id="35861-107">If you have an on-premises environment and are using Teams, users who are homed in Skype for Business on premises do not have the ability to interoperate with Skype for Business users, nor communicate with users in federated organizations.</span></span> <span data-ttu-id="35861-108">チームでは、この機能を取得するには、これらのユーザーする必要があります Skype から設置型のビジネスに移動、クラウドでは、Skype をビジネスのハイブリッド モード用に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35861-108">To gain this functionality in Teams, these users must be moved from Skype for Business on-premises to the cloud, which requires configuring Skype for Business hybrid mode.</span></span> <span data-ttu-id="35861-109">さらに、快適に、これらのユーザー必要がありますチームのみのモードで、すべての着信呼び出しを確保し、ユーザーのチームのクライアントで、ユーザーの土地からのチャットをします。</span><span class="sxs-lookup"><span data-stu-id="35861-109">In addition, for the best experience, these users should be in Teams Only mode, which ensures all incoming calls and chats from any user land in the user’s Teams client.</span></span>

<span data-ttu-id="35861-110">ハイブリッド接続を設定して、すべてのユーザーをクラウドに移行は、ビジネスを展開するため、設置型の Skype の使用を停止する前にも必要です。</span><span class="sxs-lookup"><span data-stu-id="35861-110">Setting up hybrid connectivity and moving all users to the cloud is also required before you decommission your on-premises Skype for Business deployment.</span></span>  <span data-ttu-id="35861-111">ハイブリッド接続の設定で、スケジュールとビジネスのニーズに基づくクラウドに移行するユーザーを移動するを選択できます。</span><span class="sxs-lookup"><span data-stu-id="35861-111">With hybrid connectivity set up, you can choose to move your users to the cloud based on your schedule and business need.</span></span> <span data-ttu-id="35861-112">直接ルーティングでは、クラウドに移行して、移行が完了した後に移動するときに、設置型音声インフラストラクチャを活用できます。</span><span class="sxs-lookup"><span data-stu-id="35861-112">With Direct Routing, you can leverage your on-premises voice infrastructure while you move to the cloud and after your migration is complete.</span></span>

<span data-ttu-id="35861-113">ここは、既存のオンプレミス Skype ビジネス サーバー環境、オンプレミスの Active Directory - で作成されたユーザーとの間のハイブリッドの接続を構成する必要があります、インフラストラクチャおよびシステムの要件を説明し、チームまたは Skype ビジネスをオンラインにします。</span><span class="sxs-lookup"><span data-stu-id="35861-113">This topic describes the infrastructure and system requirements you'll need to configure hybrid connectivity between your existing on-premises Skype for Business Server deployment--with users who were created in your on-premises Active Directory--and Teams or Skype for Business Online.</span></span> 

<span data-ttu-id="35861-114">インフラストラクチャについて説明し、システム要件の間、既存のハイブリッド接続を構成する必要があります設置 Skype ビジネス サーバー配置では、チームまたは Skype のオンライン ビジネスの。</span><span class="sxs-lookup"><span data-stu-id="35861-114">This topic describes the infrastructure and system requirements you'll need to configure hybrid connectivity between your existing on-premises Skype for Business Server deployment and Teams or Skype for Business Online.</span></span>

<span data-ttu-id="35861-115">このトピックを読んでいるし、ハイブリッドの接続を構成する準備ができている後、は、 [Skype ビジネス サーバーと Office 365 の間のハイブリッド接続の構成](configure-hybrid-connectivity.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35861-115">After you have read this topic and are ready to configure hybrid connectivity, see [Configure hybrid connectivity between Skype for Business Server and Office 365](configure-hybrid-connectivity.md).</span></span> <span data-ttu-id="35861-116">構成に関するトピックでは、オンライン ビジネスの設置型展開チームと Skype との間のハイブリッドの接続をセットアップするためのステップ バイ ステップのガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="35861-116">The configuration topics provide step-by-step guidance for setting up hybrid connectivity between your on-premises deployment and Teams or Skype for Business Online.</span></span>


## <a name="about-split-domain-functionality"></a><span data-ttu-id="35861-117">分割ドメインの機能について</span><span class="sxs-lookup"><span data-stu-id="35861-117">About Split domain functionality</span></span>
<span data-ttu-id="35861-118"><a name="BKMK_Overview"> </a></span><span class="sxs-lookup"><span data-stu-id="35861-118"></span></span>

 <span data-ttu-id="35861-119">ハイブリッド接続がビジネスのサーバーおよびチームの Skype または Skype のオンライン ビジネスの設置型展開の間で設定されて、いくつかのユーザー ホーム設置型を持つことができ、一部のユーザーがオンライン ホームします。</span><span class="sxs-lookup"><span data-stu-id="35861-119">With hybrid connectivity set up between an on-premises deployment of Skype for Business Server and Teams or Skype for Business Online, you can have some users homed on-premises and some users homed online.</span></span>

<span data-ttu-id="35861-120">この種類の構成は、共有 SIP アドレス スペースの機能に依存しているし、分割ドメイン」--つまり、contoso.com などのドメインのユーザーは、複数の設置型およびチームの業務サーバーやビジネス用の Skype の Skype を使用して分割されるとも呼ばオンライン、次の図に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="35861-120">This type of configuration relies on shared SIP address space functionality, and is sometimes referred to as "split domain"--meaning users of a domain, such as contoso.com, are split between using Skype for Business Server on premises and Teams or Skype for Business Online, as shown in the following diagram:</span></span> 

![SfB ハイブリッド接続 - 分割ドメイン](../../sfbserver2019/media/plan-hybrid-connectivity-2019-1.png)

<span data-ttu-id="35861-122">共有 SIP アドレス スペースが構成されている場合。</span><span class="sxs-lookup"><span data-stu-id="35861-122">When shared SIP address space is configured:</span></span>

- <span data-ttu-id="35861-123">Azure Active Directory 接続は、Office 365 で、設置ディレクトリを同期する使用されます。</span><span class="sxs-lookup"><span data-stu-id="35861-123">Azure Active Directory Connect is used to synchronize your on-premises directory with Office 365.</span></span>

- <span data-ttu-id="35861-124">施設内に置かれているユーザーは、ビジネスのサーバーの設置型の Skype と対話します。</span><span class="sxs-lookup"><span data-stu-id="35861-124">Users who are homed on premises interact with on-premises Skype for Business servers.</span></span> 

- <span data-ttu-id="35861-125">オンラインが置かれているユーザーは、オンライン ビジネスやチームのサービスの Skype と対話可能性があります。</span><span class="sxs-lookup"><span data-stu-id="35861-125">Users who are homed online may interact with Skype for Business Online or Teams services.</span></span>

- <span data-ttu-id="35861-126">両方の環境からのユーザーは、互いに通信できます。</span><span class="sxs-lookup"><span data-stu-id="35861-126">Users from both environments can communicate with each other.</span></span> 

- <span data-ttu-id="35861-127">オンプレミスの Active Directory は、権限を持つ。</span><span class="sxs-lookup"><span data-stu-id="35861-127">The on-premises Active Directory is authoritative.</span></span> <span data-ttu-id="35861-128">すべてのユーザーは、最初に、オンプレミスの Active Directory 内に作成し、Azure AD に同期する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35861-128">All users should be created in the on-premises Active Directory first, and then synchronized to Azure AD.</span></span> <span data-ttu-id="35861-129">オンラインのホーム ユーザーの場合でも、オンプレミスの環境でユーザーを最初に作成、ユーザーは、オンプレミスのユーザーが検出できることを確認するのにはオンラインにユーザーを移動してください。</span><span class="sxs-lookup"><span data-stu-id="35861-129">Even if you intend for the user to be homed online, you must first create the user in the on-premises environment, and then move the user to online to ensure the user is discoverable by on-premises users.</span></span> 

<span data-ttu-id="35861-130">オンライン ユーザーを移動することができます、前にユーザーは、Skype オンライン ビジネス (プラン 2) のライセンスの割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="35861-130">Before a user can be moved online, the user must be assigned a Skype for Business Online (Plan 2) license.</span></span> <span data-ttu-id="35861-131">ユーザーがチームを使用する場合、ユーザーがチームのライセンスを割り当てられてもする必要があります (とビジネス ライセンスの Skype は常に有効)。</span><span class="sxs-lookup"><span data-stu-id="35861-131">If the user will be using Teams, the user must also be assigned a Teams license (and the Skype for Business license must remain enabled).</span></span> <span data-ttu-id="35861-132">オーディオ会議や電話システムなどの他のオンライン機能を利用する場合は、ユーザーは、Office 365 の適切なライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="35861-132">If your users want to take advantage of additional online features, such as Audio Conferencing or Phone System, you need to assign them the appropriate license in Office 365.</span></span>


## <a name="infrastructure-requirements"></a><span data-ttu-id="35861-133">インフラストラクチャの要件</span><span class="sxs-lookup"><span data-stu-id="35861-133">Infrastructure requirements</span></span>
<span data-ttu-id="35861-134"><a name="BKMK_Infrastructure"> </a></span><span class="sxs-lookup"><span data-stu-id="35861-134"></span></span>

<span data-ttu-id="35861-135">オンプレミス環境と Office 365 の通信サービスとの間のハイブリッドの接続を実装するには、次のインフラストラクチャ要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="35861-135">To implement hybrid connectivity between your on-premises environment and Office 365 communication services, you need to meet the following infrastructure requirements:</span></span>

- <span data-ttu-id="35861-136">1 つ設置 Skype のビジネス サーバーまたはサポートされているトポロジに展開されている Lync Server の展開です。</span><span class="sxs-lookup"><span data-stu-id="35861-136">A single on-premises deployment of Skype for Business Server or Lync Server that is deployed in a supported topology.</span></span> <span data-ttu-id="35861-137">このトピックでは、[トポロジの要件](plan-hybrid-connectivity.md#BKMK_Topology)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35861-137">See [Topology requirements](plan-hybrid-connectivity.md#BKMK_Topology) in this topic.</span></span>

- <span data-ttu-id="35861-138">有効にし、ビジネス オンラインの Skype での Microsoft Office 365 テナントです。</span><span class="sxs-lookup"><span data-stu-id="35861-138">A Microsoft Office 365 tenant with Skype for Business Online enabled.</span></span>

    > [!NOTE]
    > <span data-ttu-id="35861-139">オンプレミス展開があるハイブリッド構成には、1 つのテナントしか使用できません。</span><span class="sxs-lookup"><span data-stu-id="35861-139">You can use only a single tenant for a hybrid configuration with your on-premises deployment.</span></span>

- <span data-ttu-id="35861-140">オンプレミスのディレクトリを Office 365と同期させる Azure Active Directory Connect。</span><span class="sxs-lookup"><span data-stu-id="35861-140">Azure Active Directory Connect to synchronize your on-premises directory with Office 365.</span></span> <span data-ttu-id="35861-141">詳細についてを参照してください[Azure AD 接続: アカウントとアクセス許可](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions)。</span><span class="sxs-lookup"><span data-stu-id="35861-141">For more information, see [Azure AD Connect: Accounts and permissions](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions).</span></span>

- <span data-ttu-id="35861-142">Business Server 管理ツールの Skype です。</span><span class="sxs-lookup"><span data-stu-id="35861-142">Skype for Business Server administrative tools.</span></span>  <span data-ttu-id="35861-143">これらは、オンプレミスからクラウドに移行するユーザーを移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35861-143">These are required to move users from on-premises to the cloud.</span></span> <span data-ttu-id="35861-144">設置型展開とインターネットの両方にアクセス権を持つサーバーにこれらのツールをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="35861-144">These tools must be installed on a server with access to both on-premises deployment and the internet.</span></span> 

- <span data-ttu-id="35861-145">オンライン管理ツールです。</span><span class="sxs-lookup"><span data-stu-id="35861-145">Online administrative tools.</span></span>  <span data-ttu-id="35861-146">ビジネス オンラインのチームと Skype を管理するために、チームと Skype のビジネス管理センターまたは Windows PowerShell を使用できます。</span><span class="sxs-lookup"><span data-stu-id="35861-146">You can use either the Teams and Skype for Business Admin Center or Windows PowerShell to manage Teams and Skype for Business Online.</span></span> <span data-ttu-id="35861-147">PowerShell を使用して、オンライン ビジネスのチームまたは Skype のいずれかを管理するために、ダウンロードして、Skype をビジネス オンラインのコネクタをインストールします。</span><span class="sxs-lookup"><span data-stu-id="35861-147">To use PowerShell to manage either Teams or Skype for Business Online, download and install the Skype for Business Online Connector.</span></span> 

- <span data-ttu-id="35861-148">共有 SIP アドレス スペースを有効にする必要があり、ホスティング プロバイダーと Office 365 を使用するのには、設置型の展開を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35861-148">Shared SIP address space must be enabled, and your on-premise deployment must be configured to use Office 365 as a hosting provider.</span></span> <span data-ttu-id="35861-149">ハイブリッド接続を構成する手順の詳細については、[ハイブリッド接続の構成](configure-hybrid-connectivity.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35861-149">For more information about the steps required to configure hybrid connectivity, see [Configure hybrid connectivity](configure-hybrid-connectivity.md).</span></span>

<span data-ttu-id="35861-150">ハイブリッド接続を構成した後は、オンライン ビジネスのチームまたは Skype にユーザーを移動できます。</span><span class="sxs-lookup"><span data-stu-id="35861-150">After you configure hybrid connectivity, you can move users to Teams or Skype for Business Online.</span></span> <span data-ttu-id="35861-151">詳細については、[設置をチームからユーザーを移動](move-users-from-on-premises-to-teams.md)し、 [Skype ビジネスをオンラインにするには、社内設置型からユーザーを移動する](move-users-from-on-premises-to-skype-for-business-online.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35861-151">For more information, see [Move users from on-premises to Teams](move-users-from-on-premises-to-teams.md) and [Move users from on premises to Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md).</span></span>


## <a name="topology-requirements"></a><span data-ttu-id="35861-152">トポロジ要件</span><span class="sxs-lookup"><span data-stu-id="35861-152">Topology requirements</span></span>
<span data-ttu-id="35861-153"><a name="BKMK_Topology"> </a></span><span class="sxs-lookup"><span data-stu-id="35861-153"></span></span>

<span data-ttu-id="35861-154">チームまたは Skype のオンライン ビジネスのハイブリッド展開を構成するには、次のサポートされているトポロジのいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="35861-154">To configure your deployment for hybrid with Teams or Skype for Business Online, you need to have one of the following supported topologies:</span></span>

- <span data-ttu-id="35861-155">ビジネス サーバー 2019 の Skype を実行しているすべてのサーバーとサーバー 2019 のビジネス展開するための Skype です。</span><span class="sxs-lookup"><span data-stu-id="35861-155">A Skype for Business Server 2019 deployment with all servers running Skype for Business Server 2019.</span></span> 

- <span data-ttu-id="35861-156">ビジネス サーバー 2015 の Skype を実行しているすべてのサーバーとサーバー 2015 のビジネス展開するための Skype です。</span><span class="sxs-lookup"><span data-stu-id="35861-156">A Skype for Business Server 2015 deployment with all servers running Skype for Business Server 2015.</span></span>

- <span data-ttu-id="35861-157">Lync Server 2013 を実行しているすべてのサーバーに Lync Server 2013 展開します。</span><span class="sxs-lookup"><span data-stu-id="35861-157">A Lync Server 2013 deployment with all servers running Lync Server 2013.</span></span>

    <span data-ttu-id="35861-158">ハイブリッド音声接続をフェデレーションするエッジに指定されているエッジ サーバーがビジネス 2015; の Skype をする必要があります。エッジには、ビジネス サーバーのバックエンドは、Skype も必要です。</span><span class="sxs-lookup"><span data-stu-id="35861-158">For hybrid voice connectivity, the Edge Server that is designated as Federation Edge must be Skype for Business 2015; the Edge also requires a Skype for Business Server backend.</span></span> <span data-ttu-id="35861-159">ユーザーのいないプールを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="35861-159">You might have a pool with no users on it.</span></span>

- <span data-ttu-id="35861-160">混合 Lync Server 2015、Skype の次のサーバーの役割を持つサーバー 2019 のビジネス展開。</span><span class="sxs-lookup"><span data-stu-id="35861-160">A mixed Lync Server 2015 and Skype for Business Server 2019 deployment with the following server roles:</span></span> 

  - <span data-ttu-id="35861-161">少なくとも 1 台のエンタープライズ プールまたは Standard Edition サーバー </span><span class="sxs-lookup"><span data-stu-id="35861-161">At least one Enterprise Pool or Standard Edition server</span></span> 

  - <span data-ttu-id="35861-162">SIP フェデレーションに関連づけられたディレクター プール (もしあれば)</span><span class="sxs-lookup"><span data-stu-id="35861-162">The Director Pool associated with SIP federation, if it exists</span></span> 

  - <span data-ttu-id="35861-163">SIP フェデレーションに関連づけられたエッジ プール (もしあれば)</span><span class="sxs-lookup"><span data-stu-id="35861-163">The Edge Pool associated with SIP federation</span></span> 

- <span data-ttu-id="35861-164">混合 Lync Server 2013、Skype ビジネス サーバー 2019 の Skype を実行するには、少なくとも 1 つのサイトで次のサーバーの役割を持つサーバー 2019 のビジネス展開に。</span><span class="sxs-lookup"><span data-stu-id="35861-164">A mixed Lync Server 2013 and Skype for Business Server 2019 deployment with the following server roles in at least one site running Skype for Business Server 2019:</span></span> 

  - <span data-ttu-id="35861-165">少なくとも 1 台のエンタープライズ プールまたは Standard Edition サーバー </span><span class="sxs-lookup"><span data-stu-id="35861-165">At least one Enterprise Pool or Standard Edition server</span></span> 
  - <span data-ttu-id="35861-166">SIP フェデレーションに関連づけられたディレクター プール (もしあれば)</span><span class="sxs-lookup"><span data-stu-id="35861-166">The Director Pool associated with SIP federation, if it exists</span></span> 
  - <span data-ttu-id="35861-167">SIP フェデレーションに関連づけられたエッジ プール (もしあれば)</span><span class="sxs-lookup"><span data-stu-id="35861-167">The Edge Pool associated with SIP federation</span></span> 

- <span data-ttu-id="35861-168">混合 Lync Server 2013、Skype ビジネス サーバー 2015 の Skype を実行するには、少なくとも 1 つのサイトで次のサーバーの役割を持つサーバー 2015 のビジネス展開に。</span><span class="sxs-lookup"><span data-stu-id="35861-168">A mixed Lync Server 2013 and Skype for Business Server 2015 deployment with the following server roles in at least one site running Skype for Business Server 2015:</span></span>

  - <span data-ttu-id="35861-169">少なくとも 1 台のエンタープライズ プールまたは Standard Edition サーバー </span><span class="sxs-lookup"><span data-stu-id="35861-169">At least one Enterprise Pool or Standard Edition server</span></span>

  - <span data-ttu-id="35861-170">SIP フェデレーションに関連づけられたディレクター プール (もしあれば)</span><span class="sxs-lookup"><span data-stu-id="35861-170">The Director Pool associated with SIP federation, if it exists</span></span>

  - <span data-ttu-id="35861-171">SIP フェデレーションに関連づけられたエッジ プール (もしあれば)</span><span class="sxs-lookup"><span data-stu-id="35861-171">The Edge Pool associated with SIP federation</span></span>

- <span data-ttu-id="35861-172">混合 Lync Server 2010、Skype ビジネス サーバー 2015 の Skype を実行するには、少なくとも 1 つのサイトで次のサーバーの役割を持つサーバー 2015 のビジネス展開に。</span><span class="sxs-lookup"><span data-stu-id="35861-172">A mixed Lync Server 2010 and Skype for Business Server 2015 deployment with the following server roles in at least one site running Skype for Business Server 2015:</span></span>

  - <span data-ttu-id="35861-173">少なくとも 1 台のエンタープライズ プールまたは Standard Edition サーバー </span><span class="sxs-lookup"><span data-stu-id="35861-173">At least one Enterprise Pool or Standard Edition server</span></span>

  - <span data-ttu-id="35861-174">SIP フェデレーションに関連づけられたディレクター プール (もしあれば)</span><span class="sxs-lookup"><span data-stu-id="35861-174">The Director Pool associated with SIP federation, if it exists</span></span>

  - <span data-ttu-id="35861-175">サイトの SIP フェデレーションに関連づけられたエッジ プール</span><span class="sxs-lookup"><span data-stu-id="35861-175">The Edge Pool associated with SIP federation for the Site</span></span>

- <span data-ttu-id="35861-176">Lync Server 2013 を実行している少なくとも 1 つのサイトで次のサーバーの役割を組み合わせた Lync Server 2010 および Lync Server 2013 展開します。</span><span class="sxs-lookup"><span data-stu-id="35861-176">A mixed Lync Server 2010 and Lync Server 2013 deployment with the following server roles in at least one site running Lync Server 2013:</span></span>

  - <span data-ttu-id="35861-177">サイトの少なくとも 1 台のエンタープライズ プールまたは Standard Edition サーバー</span><span class="sxs-lookup"><span data-stu-id="35861-177">At least one Enterprise Pool or Standard Edition server in the site</span></span>

  - <span data-ttu-id="35861-178">SIP フェデレーションに関連づけられたディレクター プール (もしサイトにあれば)</span><span class="sxs-lookup"><span data-stu-id="35861-178">The Director Pool associated with SIP federation, if it exists in the site</span></span>

  - <span data-ttu-id="35861-179">サイトの SIP フェデレーションに関連づけられたエッジ プール</span><span class="sxs-lookup"><span data-stu-id="35861-179">The Edge Pool associated with SIP federation for the site</span></span>

- <span data-ttu-id="35861-180">Lync Server 2010 を最新の累積的な更新プログラムを実行しているすべてのサーバーに Lync Server 2010 展開します。</span><span class="sxs-lookup"><span data-stu-id="35861-180">A Lync Server 2010 deployment with all servers running Lync Server 2010 with the latest cumulative updates.</span></span>

  - <span data-ttu-id="35861-181">エッジ サーバーのフェデレーションおよびエッジ サーバーのフェデレーションからの次ホップ サーバーする必要があります実行している Lync Server 2010 を最新の累積的な更新プログラム。</span><span class="sxs-lookup"><span data-stu-id="35861-181">The federation Edge Server and next hop server from the federation Edge Server must be running Lync Server 2010 with the latest cumulative updates.</span></span>

  - <span data-ttu-id="35861-182">ビジネス サーバー 2015 または Lync Server 2013 の管理ツールの Skype が少なくとも 1 つのサーバーまたは管理ワークステーション上にインストールしなければなりません。</span><span class="sxs-lookup"><span data-stu-id="35861-182">The Skype for Business Server 2015 or Lync Server 2013 Administrative Tools must be installed on at least one server or management workstation.</span></span>


 ## <a name="multi-forest-support"></a><span data-ttu-id="35861-183">マルチ フォレストのサポート</span><span class="sxs-lookup"><span data-stu-id="35861-183">Multi-forest support</span></span>
<span data-ttu-id="35861-184"><a name="BKMK_MultiForest"> </a></span><span class="sxs-lookup"><span data-stu-id="35861-184"></span></span>

<span data-ttu-id="35861-185">ユーザーは、次の要件が満たされれば、別のフォレストで Skype for Business の機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="35861-185">Users can access Skype for Business functionality in another forest if the following requirements are met:</span></span>

- <span data-ttu-id="35861-186">ユーザーが、Skype for Business をホストするフォレストに適切に同期されている。ハイブリッド構成において、これはユーザーが無効化されたユーザー オブジェクトとして同期される必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="35861-186">Users are properly synchronized into the forest that hosts Skype for Business: In hybrid configurations, this means that users must be synchronized as disabled user objects.</span></span>

- <span data-ttu-id="35861-187">Skype for Business をホストするフォレストは、ユーザーを含むフォレストを信頼する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35861-187">The forest hosting Skype for Business must trust the forest containing the users.</span></span>

<span data-ttu-id="35861-188">ハイブリッドの複数のフォレスト シナリオの詳細については、[ハイブリッド ビジネスの Skype の複数のフォレスト環境の構成](configure-a-multi-forest-environment-for-hybrid.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35861-188">For details on multi-forest hybrid scenarios, see [Configure a multi-forest environment for hybrid Skype for Business](configure-a-multi-forest-environment-for-hybrid.md).</span></span>


## <a name="federation-requirements"></a><span data-ttu-id="35861-189">フェデレーションの要件</span><span class="sxs-lookup"><span data-stu-id="35861-189">Federation requirements</span></span>
<span data-ttu-id="35861-190"><a name="BKMK_Federation"> </a></span><span class="sxs-lookup"><span data-stu-id="35861-190"></span></span>

<span data-ttu-id="35861-191">ハイブリッドを構成するとき、オンプレミスとオンライン環境を互いにフェデレーションできるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="35861-191">When configuring hybrid, you must ensure that your on-premises and online environments can federate with each other.</span></span>  <span data-ttu-id="35861-192">オンライン環境では、開いているフェデレーションが、デフォルトでは多くの場合、オンプレミス環境には、既定でフェデレーションを閉じられました。</span><span class="sxs-lookup"><span data-stu-id="35861-192">The online environment has open federation by default; the on-premises environment often has closed federation by default.</span></span>  

<span data-ttu-id="35861-193">ハイブリッド展開を正しく構成するには、次の必要条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="35861-193">The following requirements must be met to successfully configure a hybrid deployment:</span></span>

- <span data-ttu-id="35861-p115">オンプレミス展開と Office 365 テナントでドメイン マッチングの構成を同一にする必要があります。オンプレミス展開でパートナーの検出が有効になっている場合、オンライン テナントではオープン フェデレーションを有効にする必要があります。パートナーの検出が無効になっている場合、オンライン テナントではクローズド フェデレーションを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35861-p115">Domain matching must be configured the same for your on-premises deployment and your Office 365 tenant. If partner discovery is enabled on the on-premises deployment, then open federation must be configured for your online tenant. If partner discovery is not enabled, then closed federation must be configured for your online tenant.</span></span>

- <span data-ttu-id="35861-197">オンプレミス展開における禁止ドメインの一覧はオンライン テナントの禁止ドメインの一覧と正確に一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35861-197">The Blocked domains list in the on-premises deployment must exactly match the Blocked domains list for your online tenant.</span></span>

- <span data-ttu-id="35861-198">オンプレミス展開における許可ドメインの一覧はオンライン テナントの許可ドメインの一覧と正確に一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35861-198">The Allowed domains list in the on-premises deployment must exactly match the Allowed domains list for your online tenant.</span></span>

- <span data-ttu-id="35861-199">オンラインのテナントのため、外部との連絡に対しては、フェデレーションを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="35861-199">Federation must be enabled for the external communications for the online tenant.</span></span>


## <a name="network-considerations"></a><span data-ttu-id="35861-200">ネットワークに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="35861-200">Network considerations</span></span>

<span data-ttu-id="35861-201">に関する考慮事項を次に説明します。</span><span class="sxs-lookup"><span data-stu-id="35861-201">The following sections describe considerations for:</span></span> 

- <span data-ttu-id="35861-202">DNS の設定</span><span class="sxs-lookup"><span data-stu-id="35861-202">DNS settings</span></span> 
- <span data-ttu-id="35861-203">ファイアウォールの考慮事項</span><span class="sxs-lookup"><span data-stu-id="35861-203">Firewall considerations</span></span> 


### <a name="dns-settings"></a><span data-ttu-id="35861-204">DNS の設定</span><span class="sxs-lookup"><span data-stu-id="35861-204">DNS settings</span></span>
<span data-ttu-id="35861-205"><a name="BKMK_DNS"> </a></span><span class="sxs-lookup"><span data-stu-id="35861-205"></span></span>

<span data-ttu-id="35861-206">ハイブリッド展開用の DNS レコードを作成するには、外部の DNS レコードをビジネスのすべての Skype はオンプレミス インフラストラクチャを指し示します。</span><span class="sxs-lookup"><span data-stu-id="35861-206">When creating DNS records for hybrid deployments, all Skype for Business external DNS records should point to the on-premises infrastructure.</span></span> <span data-ttu-id="35861-207">必要な DNS レコードの詳細については、 [Skype ビジネス サーバー用の DNS の要件](../../sfbserver/plan-your-deployment/network-requirements/dns.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35861-207">For details on required DNS records, please refer to [DNS requirements for Skype for Business Server](../../sfbserver/plan-your-deployment/network-requirements/dns.md).</span></span>

<span data-ttu-id="35861-208">また、設置型展開で、次の表に記載されている DNS 解決が正しく動作することを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35861-208">Additionally, you need to ensure that the DNS resolution described in the following table works in your on-premises deployment.</span></span> <span data-ttu-id="35861-209">(既に設置のフェデレーションを構成した場合、最も可能性の高いがあるこれら。)</span><span class="sxs-lookup"><span data-stu-id="35861-209">(If you already configured federation for on-premises, then you most likely already have these.)</span></span>

|<span data-ttu-id="35861-210">DNS レコード</span><span class="sxs-lookup"><span data-stu-id="35861-210">DNS record</span></span>  <br/> |<span data-ttu-id="35861-211">解決方法</span><span class="sxs-lookup"><span data-stu-id="35861-211">Resolvable by</span></span>  <br/> |<span data-ttu-id="35861-212">DNS 要件</span><span class="sxs-lookup"><span data-stu-id="35861-212">DNS requirement</span></span>  <br/> |
|:-----|:-----|:-----|
|<span data-ttu-id="35861-213">_Sipfederationtls._tcp の DNS SRV レコードです。\<sipdomain.com\>サポートされているすべての SIP ドメインがアクセス エッジの外部 IP(s) に解決するため</span><span class="sxs-lookup"><span data-stu-id="35861-213">DNS SRV record for _sipfederationtls._tcp.\<sipdomain.com\> for all supported SIP domains resolving to Access Edge external IP(s)</span></span>  <br/> |<span data-ttu-id="35861-214">エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="35861-214">Edge server(s)</span></span>  <br/> |<span data-ttu-id="35861-p118">ハイブリッド展開でフェデレーション通信を有効にする。オンプレミスとオンラインで分割される SIP ドメイン用のフェデレーション トラフィックのルートをエッジ サーバーで認識している必要があります。</span><span class="sxs-lookup"><span data-stu-id="35861-p118">Enable federated communication in a hybrid configuration. The Edge Server needs to know where to route federated traffic for the SIP domain that is split between on premises and online.</span></span>  <br/> <span data-ttu-id="35861-217">ユーザー名のドメインと SRV レコードの間で一致する厳密な DNS 名を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35861-217">Must use strict DNS name matching between the domain in the user name and the SRV record.</span></span>  <br/> |
|<span data-ttu-id="35861-218">エッジ Web 会議サービス FQDN の DNS A レコード、たとえば、webcon.contoso.com は Web 会議のエッジ外部 IP に解決される</span><span class="sxs-lookup"><span data-stu-id="35861-218">DNS A record(s) for Edge Web Conferencing Service FQDN, e.g. webcon.contoso.com resolving to Web Conferencing Edge external IP(s)</span></span>  <br/> |<span data-ttu-id="35861-219">ユーザーのコンピューターが社内ネットワークに接続されています。</span><span class="sxs-lookup"><span data-stu-id="35861-219">Internal corporate network connected users' computers</span></span>  <br/> |<span data-ttu-id="35861-p119">オンライン ユーザーを有効にして、オンプレミスのホストされた会議でのコンテンツを提供または表示する。コンテンツには、PowerPoint ファイル、ホワイトボード、投票、および共有メモがあります。</span><span class="sxs-lookup"><span data-stu-id="35861-p119">Enable online users to present or view content in on-premises hosted meetings. Content includes PowerPoint files, whiteboards, polls, and shared notes.</span></span>  <br/> |

<span data-ttu-id="35861-222">所属する組織での DNS の構成方法によっては、内部 DNS 解決をこれらのレコードに適用するために、対応する SIP ドメインに対して組織内でホストする DNS ゾーンにこれらのレコードを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35861-222">Depending on how DNS is configured in your organization, you may need to add these records to the internal hosted DNS zone for the corresponding SIP domain(s) to provide internal DNS resolution to these records.</span></span> 

### <a name="firewall-considerations"></a><span data-ttu-id="35861-223">ファイアウォールの考慮事項</span><span class="sxs-lookup"><span data-stu-id="35861-223">Firewall considerations</span></span>
<span data-ttu-id="35861-224"><a name="BKMK_Firewall"> </a></span><span class="sxs-lookup"><span data-stu-id="35861-224"></span></span>

<span data-ttu-id="35861-p120">ネットワーク上のコンピューターは、標準のインターネット DNS 参照を実行できる必要があります。これらのコンピューターが標準のインターネット サイトに接続できれば、ネットワークはこの要件を満たしています。</span><span class="sxs-lookup"><span data-stu-id="35861-p120">Computers on your network must be able to perform standard Internet DNS lookups. If these computers can reach standard Internet sites, your network meets this requirement.</span></span>

<span data-ttu-id="35861-227">Microsoft Online Services のデータ ・ センターの場所、によって、ワイルドカード ドメイン名に基づいて接続を許可するのには、ネットワークのファイアウォール デバイスを構成する必要がありますも (からのすべてのトラフィックは、 \*. outlook.com)。</span><span class="sxs-lookup"><span data-stu-id="35861-227">Depending on the location of your Microsoft Online Services data center, you must also configure your network firewall devices to accept connections based on wildcard domain names (for example, all traffic from \*.outlook.com).</span></span> <span data-ttu-id="35861-228">組織のファイアウォールはワイルドカードの名前の構成をサポートしていない場合は、許可したい IP アドレスの範囲、指定されたポートを手動で確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35861-228">If your organization's firewalls do not support wildcard name configurations, you will have to manually determine the IP address ranges that you would like to allow and the specified ports.</span></span>

<span data-ttu-id="35861-229">ポートおよびプロトコルの要件に関する詳細情報を含む詳細については、 [Office 365 の Url と IP アドレスの範囲](https://go.microsoft.com/fwlink/p/?LinkId=252942)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35861-229">For more information, including details about ports and protocol requirements, see [Office 365 URLs and IP address ranges](https://go.microsoft.com/fwlink/p/?LinkId=252942).</span></span>
