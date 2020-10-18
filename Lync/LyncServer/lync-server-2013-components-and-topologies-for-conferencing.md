---
title: Lync Server 2013 の会議のコンポーネントとトポロジ
description: Lync Server 2013 の会議のコンポーネントとトポロジ。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for conferencing
ms:assetid: eb83052a-3360-4ba1-a6a0-6ee419942809
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399061(v=OCS.15)
ms:contentKeyID: 48185707
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 719fe81d0f634b1eab1e79c2e7e665e89b0a791a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576863"
---
# <a name="components-and-topologies-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="520f1-103">Lync Server 2013 の会議のコンポーネントとトポロジ</span><span class="sxs-lookup"><span data-stu-id="520f1-103">Components and topologies for conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="520f1-104">_**トピックの最終更新日:** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="520f1-104">_**Topic Last Modified:** 2013-02-04_</span></span>

<span data-ttu-id="520f1-105">トポロジビルダーで [会議] を選択すると、電話会議はフロントエンドサーバーまたは Standard Edition サーバーの一部として展開されます。</span><span class="sxs-lookup"><span data-stu-id="520f1-105">When you select conferencing in Topology Builder, conferencing is deployed as part of the Front End Server or Standard Edition server.</span></span> <span data-ttu-id="520f1-106">ダイヤルイン会議と PowerPoint 共有には、追加コンポーネントと構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="520f1-106">Dial-in conferencing and PowerPoint sharing requires additional components and configuration.</span></span> <span data-ttu-id="520f1-107">このセクションでは、Web 会議、音声ビデオ会議、およびダイヤルイン会議でサポートされるコンポーネントとトポロジについて説明します。</span><span class="sxs-lookup"><span data-stu-id="520f1-107">The following sections describe the supported components and topologies for web conferencing, A/V conferencing, and dial-in conferencing.</span></span>

<div>

## <a name="supported-components"></a><span data-ttu-id="520f1-108">サポートされるコンポーネント</span><span class="sxs-lookup"><span data-stu-id="520f1-108">Supported Components</span></span>

<span data-ttu-id="520f1-109">Web 会議と音声ビデオ会議のみが必要なコンポーネントは、組織のフロントエンドサーバーまたは Standard Edition サーバーです。</span><span class="sxs-lookup"><span data-stu-id="520f1-109">The only components web conferencing and A/V conferencing require are your organization’s Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="520f1-110">フロントエンドサーバーおよび Standard Edition サーバーのハードウェアおよびソフトウェア要件の一覧については、「lync server [2013 の場合はサポートされるハードウェア](lync-server-2013-supported-hardware.md) 」および「 [lync server 2013 でのサーバーソフトウェアとインフラストラクチャのサポート](lync-server-2013-server-software-and-infrastructure-support.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="520f1-110">For a list of hardware and software requirements for the Front End Servers and Standard Edition servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) and [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).</span></span>

<span data-ttu-id="520f1-111">Lync Server 2013 は、Office Web Apps および Office Web Apps サーバーを使用して、PowerPoint プレゼンテーションの共有とレンダリングを処理します。</span><span class="sxs-lookup"><span data-stu-id="520f1-111">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="520f1-112">Office Web Apps サーバーのインストールと構成の詳細については、「 [Office Web Apps server および Lync Server 2013 との統合の構成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="520f1-112">For details about installing and configuring the Office Web Apps Server, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="520f1-113">Web 会議および音声ビデオ会議の要件に加えて、ダイヤルイン会議は次の Lync Server 2013 コンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="520f1-113">In addition to the requirements for web conferencing and A/V conferencing, dial-in conferencing uses the following Lync Server 2013 components:</span></span>

  - <span data-ttu-id="520f1-114">**アプリケーションサービス**    Application service は、統合コミュニケーション (UC) アプリケーションを展開、ホスト、および管理するためのプラットフォームを提供します。</span><span class="sxs-lookup"><span data-stu-id="520f1-114">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications (UC) applications.</span></span> <span data-ttu-id="520f1-115">ダイヤルイン会議では、アプリケーションサービスを必要とする2つの UC アプリケーション (会議アテンダントと会議アナウンス) を使用します。</span><span class="sxs-lookup"><span data-stu-id="520f1-115">Dial-in conferencing uses two UC applications that require Application service: Conferencing Attendant and Conferencing Announcement.</span></span> <span data-ttu-id="520f1-116">アプリケーション サービスは、会議ワークロードを展開してダイヤルイン会議オプションを選択した場合に、既定でフロント エンド プール内のすべてのフロント エンド サーバーおよびすべての Standard Edition サーバーにインストールされてアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="520f1-116">Application service is installed and activated by default on every Front End Server in a Front End pool and on every Standard Edition server when you deploy a Conferencing workload and select the dial-in conferencing option.</span></span>

  - <span data-ttu-id="520f1-117">**会議アテンダントアプリケーション**    電話会議アテンダントアプリケーションは、公衆交換電話網 (PSTN) 通話を受け付け、音声ガイダンスを再生して、通話を音声ビデオ会議に参加させる統合コミュニケーションアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="520f1-117">**Conferencing Attendant application**   Conferencing Attendant application is a unified communications application that accepts public switched telephone network (PSTN) calls, plays prompts, and joins the calls to an A/V conference.</span></span> <span data-ttu-id="520f1-118">会議ワークロードを展開し、[ダイヤルイン会議] オプションを選択すると、既定で会議アテンダントアプリケーションがインストールされ、アクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="520f1-118">Conferencing Attendant application is installed and activated by default when you deploy a Conferencing workload and select the dial-in conferencing option.</span></span>

  - <span data-ttu-id="520f1-119">**会議アナウンスアプリケーション**    会議アナウンスアプリケーションは、参加者が会議に参加または退室したとき、参加者がミュートまたはミュート解除、会議ロビーに入ったとき、または会議がロックまたはロック解除されたときなど、特定のアクションについての音声を再生する統合コミュニケーションアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="520f1-119">**Conferencing Announcement application**   Conferencing Announcement application is a unified communications application that plays tones and prompts to PSTN participants on certain actions, such as when participants join or leave a conference, participants are muted or unmuted, someone enters the conference lobby, or the conference is locked or unlocked.</span></span> <span data-ttu-id="520f1-120">会議アナウンスアプリケーションは、電話のキーパッドからのデュアルトーン多重周波数 (DTMF) コマンドもサポートします。</span><span class="sxs-lookup"><span data-stu-id="520f1-120">Conferencing Announcement application also supports dual-tone multifrequency (DTMF) commands from the phone keypad.</span></span> <span data-ttu-id="520f1-121">会議ワークロードを展開し、[ダイヤルイン会議] オプションを選択すると、既定で会議アナウンスアプリケーションが自動的にインストールされ、アクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="520f1-121">Conferencing Announcement application is automatically installed and activated by default when you deploy a Conferencing workload and select the dial-in conferencing option.</span></span>

  - <span data-ttu-id="520f1-122">**ダイヤルイン会議の設定ページ**    [ダイヤルイン会議の設定] ページには、使用可能な言語で会議のダイヤルイン番号、割り当てられている会議情報 (スケジュールする必要がない会議の場合)、および会議中の DTMF コントロールが表示され、個人識別番号 (PIN) と割り当てられた会議情報の管理をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="520f1-122">**Dial-in Conferencing Settings page**   The Dial-in Conferencing Settings page displays conference dial-in numbers with their available languages, assigned conference information (that is, for meetings that do not need to be scheduled), and in-conference DTMF controls, and supports management of personal identification number (PIN) and assigned conferencing information.</span></span> <span data-ttu-id="520f1-123">[ダイヤルイン会議の設定] ページは、Web サービスの一部として自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="520f1-123">The Dial-in Conferencing Settings page is automatically installed as part of Web Services.</span></span>

  - <span data-ttu-id="520f1-124">**Lync server 2013、仲介サーバーおよび PSTN ゲートウェイ**    ダイヤルイン会議では、Lync Server 2013 と PSTN ゲートウェイ間の信号 (およびメディア、一部の構成) を変換する仲介サーバー、および仲介サーバーと PSTN ゲートウェイ間の信号とメディアを変換する PSTN ゲートウェイを必要とします。</span><span class="sxs-lookup"><span data-stu-id="520f1-124">**Lync Server 2013, Mediation Server and PSTN gateway**   Dial-in conferencing requires a Mediation Server to translate signaling (and media, in some configurations) between Lync Server 2013 and the PSTN gateway, and a PSTN gateway to translate signaling and media between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="520f1-125">ダイヤルイン会議では、少なくとも 1 つの仲介サーバーと、少なくとも 1 つの次のものを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="520f1-125">For dial-in conferencing, you must deploy at least one Mediation Server and at least one of the following:</span></span>
    
      - <span data-ttu-id="520f1-126">PSTN ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="520f1-126">PSTN gateway</span></span>
    
      - <span data-ttu-id="520f1-127">IP-PBX</span><span class="sxs-lookup"><span data-stu-id="520f1-127">IP-PBX</span></span>
    
      - <span data-ttu-id="520f1-128">セッション ボーダー コントローラー (SBC) (SIP トランクを構成して接続するインターネット テレフォニー サービス プロバイダー (ITSP) のため)</span><span class="sxs-lookup"><span data-stu-id="520f1-128">Session Border Controller (SBC) (for an Internet telephony service provider to which you connect by configuring a SIP trunk)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="520f1-129">エンタープライズ Voip を展開している場合、仲介サーバーと PSTN ゲートウェイはエンタープライズ Voip 展開に含まれています。</span><span class="sxs-lookup"><span data-stu-id="520f1-129">If you are also deploying Enterprise Voice, Mediation Server and PSTN gateways are part of the Enterprise Voice deployment.</span></span> <span data-ttu-id="520f1-130">エンタープライズ VoIP を展開していない場合、ダイヤルイン会議用に、少なくとも 1 つの仲介サーバー、および少なくとも 1 つの PSTN ゲートウェイ、IP-PBX、または SBC を展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="520f1-130">If you are not deploying Enterprise Voice, you need to deploy at least one Mediation Server and at least one PSTN gateway, IP-PBX, or SBC for dial-in conferencing.</span></span>

    
    </div>

  - <span data-ttu-id="520f1-131">**ファイルストア**    ファイルストアは、録音された名前のオーディオファイルに対して使用されます。</span><span class="sxs-lookup"><span data-stu-id="520f1-131">**File store**   File store is used for recorded name audio files.</span></span> <span data-ttu-id="520f1-132">ファイル ストアは、すべての Enterprise Edition 展開または Standard Edition 展開の標準コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="520f1-132">File Store is a standard component in every Enterprise Edition or Standard Edition deployment.</span></span>

  - <span data-ttu-id="520f1-133">**ユーザーストア**    ユーザーストアは、ユーザーの Lync Server 2013 Pin を格納するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="520f1-133">**User store**   User store is used to store user Lync Server 2013 PINs.</span></span> <span data-ttu-id="520f1-134">PIN はハッシュされます。</span><span class="sxs-lookup"><span data-stu-id="520f1-134">PINs are hashed.</span></span> <span data-ttu-id="520f1-135">ユーザー ストアは、すべての Enterprise Edition 展開または Standard Edition 展開の標準コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="520f1-135">The User store is a standard component in every Enterprise Edition or Standard Edition deployment.</span></span>

  - <span data-ttu-id="520f1-136">**Lync Server コントロールパネル**    一部のダイヤルイン設定は、Lync Server コントロールパネルを使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="520f1-136">**Lync Server Control Panel**   Some dial-in settings can be configured by using Lync Server Control Panel.</span></span>

  - <span data-ttu-id="520f1-137">**Lync Server 管理シェル**    すべてのダイヤルイン設定は、Lync Server 管理シェルコマンドレットを使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="520f1-137">**Lync Server Management Shell**   All dial-in settings can be configured by using Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="520f1-138">Lync Server 管理シェルコマンドレットは、会議アテンダントアプリケーションおよび会議アナウンスアプリケーションの展開、構成、実行、監視、およびトラブルシューティングに使用できます。</span><span class="sxs-lookup"><span data-stu-id="520f1-138">Lync Server Management Shell cmdlets are available for deploying, configuring, running, monitoring, and troubleshooting Conferencing Attendant application and Conferencing Announcement application.</span></span> <span data-ttu-id="520f1-139">特定のコマンドレットの詳細については、「Lync Server Management Shell」のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="520f1-139">For details about specific cmdlets, see Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="520f1-140">サポートされるトポロジ</span><span class="sxs-lookup"><span data-stu-id="520f1-140">Supported Topologies</span></span>

<span data-ttu-id="520f1-141">Lync Server 2013 では、会議サービスを実行しているサーバーは、常にフロントエンドサーバーまたは Standard Edition サーバーと併置されています。</span><span class="sxs-lookup"><span data-stu-id="520f1-141">In Lync Server 2013, the server running conferencing services is always collocated with the Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="520f1-142">初期展開時に、トポロジビルダーでは、トポロジに電話会議を含めるオプションが提供されます。</span><span class="sxs-lookup"><span data-stu-id="520f1-142">During your initial deployment, Topology Builder gives you the option to include conferencing in your topology.</span></span> <span data-ttu-id="520f1-143">トポロジー ビルダーを使用して、既存の展開に会議を追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="520f1-143">You can also use Topology Builder to add conferencing to an existing deployment.</span></span> <span data-ttu-id="520f1-144">詳細については、「 [Lync Server 2013 でのトポロジの定義と構成](lync-server-2013-defining-and-configuring-the-topology.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="520f1-144">For details, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span>

<div>

## <a name="dial-in-conferencing-toplogies"></a><span data-ttu-id="520f1-145">ダイヤルイン会議のトポロジ</span><span class="sxs-lookup"><span data-stu-id="520f1-145">Dial in Conferencing Toplogies</span></span>

<span data-ttu-id="520f1-146">次のトポロジと構成にダイヤルイン会議を展開できます。</span><span class="sxs-lookup"><span data-stu-id="520f1-146">You can deploy dial-in conferencing in the following topologies and configurations:</span></span>

  - <span data-ttu-id="520f1-147">Lync Server 2013 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="520f1-147">Lync Server 2013 Standard Edition</span></span>

  - <span data-ttu-id="520f1-148">Lync Server 2013 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="520f1-148">Lync Server 2013 Enterprise Edition</span></span>

  - <span data-ttu-id="520f1-149">エンタープライズ Voip の有無にかかわらず</span><span class="sxs-lookup"><span data-stu-id="520f1-149">With or without Enterprise Voice</span></span>

<span data-ttu-id="520f1-150">アプリケーションサービス、会議アテンダントアプリケーション、および会議アナウンスアプリケーションは、中央サイトに展開できますが、ブランチサイトに展開することはできません。</span><span class="sxs-lookup"><span data-stu-id="520f1-150">You can deploy Application service, Conferencing Attendant application, and Conferencing Announcement application in a central site, but not in a branch site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="520f1-151">ダイヤルイン会議を展開する場合は、Lync Server 2013 会議を展開するすべてのプールに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="520f1-151">If you deploy dial-in conferencing, you must deploy it in every pool where you deploy Lync Server 2013 conferencing.</span></span> <span data-ttu-id="520f1-152">プールごとにアクセス番号を割り当てる必要はありませんが、プールごとにダイヤルイン会議機能を展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="520f1-152">You do not need to assign access numbers in every pool, but you must deploy the dial-in conferencing feature in every pool.</span></span> <span data-ttu-id="520f1-153">この要件では、ユーザーが1つのプールのアクセス番号を呼び出して Lync Server 2013 会議を別のプールに参加させるときに、記録された名前の機能がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="520f1-153">This requirement supports the recorded name feature when a user calls an access number from one pool to join a Lync Server 2013 conference in a different pool.</span></span>



</div>

</div>

<div>

## <a name="supported-topologies-for-lync-server-2013-and-office-web-apps"></a><span data-ttu-id="520f1-154">Lync Server 2013 および Office Web Apps でサポートされているトポロジ</span><span class="sxs-lookup"><span data-stu-id="520f1-154">Supported Topologies for Lync Server 2013 and Office Web Apps</span></span>

<span data-ttu-id="520f1-155">Lync Server 2013 には、Office Web Apps サーバーを構成するための次のような方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="520f1-155">Lync Server 2013 provides the following ways to configure Office Web Apps Server.</span></span> <span data-ttu-id="520f1-156">必要に応じて次のことができます。</span><span class="sxs-lookup"><span data-stu-id="520f1-156">Depending on your needs you can:</span></span>

  - <span data-ttu-id="520f1-157">**組織のファイアウォールの背後にある Lync Server 2013 と Office Web Apps サーバーの両方を、同じネットワークゾーンにインストールします。**</span><span class="sxs-lookup"><span data-stu-id="520f1-157">**Install both Lync Server 2013 and Office Web Apps Server on-premises behind your organization’s firewall, and in the same network zone.**</span></span> <span data-ttu-id="520f1-158">このトポロジでは、Office Web Apps サーバーへの外部アクセスはリバースプロキシサーバー経由で提供されます。</span><span class="sxs-lookup"><span data-stu-id="520f1-158">With this topology, external access to Office Web Apps Server will be provided through your reverse proxy server.</span></span> <span data-ttu-id="520f1-159">Lync Server 2013 と Office Web Apps サーバー (または Office Web Apps サーバーファーム) は、オンプレミスと組織のファイアウォールの背後にインストールされています。</span><span class="sxs-lookup"><span data-stu-id="520f1-159">Both Lync Server 2013 and Office Web Apps Server (or an Office Web Apps Server farm) are installed on-premises and behind your organization's firewall.</span></span> <span data-ttu-id="520f1-160">できれば、Lync Server と同じネットワークゾーンに Office Web Apps サーバーをインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="520f1-160">Ideally, you should install Office Web Apps Server in the same network zone as Lync Server.</span></span>
    
    <span data-ttu-id="520f1-161">外部の Lync クライアントは、リバースプロキシサーバーを使用して Lync Server 2013 および Office Web Apps サーバーに接続できます。これは、インターネットからの要求を受けて内部ネットワークに転送されるサーバーです。</span><span class="sxs-lookup"><span data-stu-id="520f1-161">External Lync clients can connect to Lync Server 2013 and to Office Web Apps Server by using a reverse proxy server, which is a server that takes requests from the Internet and forwards them to the internal network.</span></span> <span data-ttu-id="520f1-162">(内部クライアントは、Office Web Apps サーバーに直接接続できるため、リバースプロキシサーバーを使用する必要はありません)。このトポロジは、Lync Server 2013 のみで使用される専用の Office Web Apps サーバーファームを使用する場合に最適に機能します。</span><span class="sxs-lookup"><span data-stu-id="520f1-162">(Internal clients do not need to use the reverse proxy server because they can connect to Office Web Apps Server directly.) This topology works best if you want to use a dedicated Office Web Apps Server farm that is only used by Lync Server 2013.</span></span>

  - <span data-ttu-id="520f1-163">**外部に展開された Office Web Apps サーバーの使用**</span><span class="sxs-lookup"><span data-stu-id="520f1-163">**Using an externally deployed Office Web Apps Server**</span></span>
    
    <span data-ttu-id="520f1-164">このトポロジでは、Lync Server 2013 がオンプレミスで展開され、Lync Server ネットワークゾーンの外側に展開された Office Web Apps サーバーを使用します。</span><span class="sxs-lookup"><span data-stu-id="520f1-164">In this topology, Lync Server 2013 is deployed on-premises, and uses an Office Web Apps Server that is deployed outside of Lync Server network zone.</span></span> <span data-ttu-id="520f1-165">これは、Office Web Apps サーバーが企業内の複数のアプリケーション間で共有されており、Lync Server が Office Web Apps サーバーの外部インターフェイスを使用する必要があるネットワークに展開される場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="520f1-165">This may happen when Office Web Apps Server is shared across multiple applications in the corporation and is deployed in a network requiring Lync Server to use the external interface of Office Web Apps Server and vice versa.</span></span>
    
    <span data-ttu-id="520f1-166">リバースプロキシサーバーをインストールする必要はありません。その代わりに、Office Web Apps サーバーから Lync Server 2013 へのすべての要求が、エッジサーバーを経由してルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="520f1-166">You do not need to install a reverse proxy server; instead, all the requests from the Office Web Apps Server to Lync Server 2013 are routed through your Edge Server.</span></span> <span data-ttu-id="520f1-167">内部と外部の両方の Lync クライアントは、外部 URL を使用して Office Web Apps サーバーに接続します。</span><span class="sxs-lookup"><span data-stu-id="520f1-167">Both your internal and your external Lync clients connect to Office Web Apps Server using the external URL.</span></span>
    
    <span data-ttu-id="520f1-168">Office Web Apps サーバーが内部ファイアウォールの外側に展開されている場合は、[トポロジビルダー] の [ **Office Web Apps サーバーは外部ネットワークで展開されています (つまり、境界またはインターネット)** ] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="520f1-168">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** in Topology Builder.</span></span> <span data-ttu-id="520f1-169">詳細については [、「Office Web Apps Server および Lync Server 2013 との統合の構成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="520f1-169">For more details see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="520f1-170">選択するトポロジにかかわらず、ファイアウォールの正しいポートを開くことは重要です。</span><span class="sxs-lookup"><span data-stu-id="520f1-170">Regardless of the topology you select, it is critical that the correct firewall ports be opened.</span></span> <span data-ttu-id="520f1-171">Office Web Apps サーバー、ロードバランサー、または Lync Server のファイアウォールによって、DNS 名、IP アドレス、およびポートがブロックされないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="520f1-171">You must make sure that DNS names, IP addresses, and ports are not blocked by firewalls on the Office Web Apps Server, the load balancer, or Lync Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="520f1-172">Office Web Apps サーバーへの外部アクセスを提供するもう1つの方法は、境界ネットワークにサーバーを展開することです。</span><span class="sxs-lookup"><span data-stu-id="520f1-172">Another option for providing external access to Office Web Apps Server is to deploy the server in the perimeter network.</span></span> <span data-ttu-id="520f1-173">これを行う場合は、Office Web Apps サーバーのセットアップでは、サーバーコンピューターが Active Directory ドメインのメンバーである必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="520f1-173">If you elect to do this, keep in mind that Office Web Apps Server setup requires the server computer to be a member of your Active Directory domain.</span></span> <span data-ttu-id="520f1-174">ネットワークポリシーによって、境界ネットワーク内のコンピューターが Active Directory ドメインのメンバーになることが許可されていない場合は、境界ネットワークに Office Web Apps サーバーをインストールしないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="520f1-174">Unless your network policy allows computers in the perimeter network to be Active Directory domain members, it is recommended that you do not install Office Web Apps Server in the perimeter network.</span></span> <span data-ttu-id="520f1-175">その代わりに、Office Web Apps サーバーを内部ネットワークにインストールし、リバースプロキシサーバー経由で外部ユーザーアクセスを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="520f1-175">Instead, you should install Office Web Apps Server in the internal network and provide external user access through your reverse proxy server.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

