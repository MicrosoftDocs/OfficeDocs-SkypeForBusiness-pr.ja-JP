---
title: 'Lync Server 2013: 主なセキュリティ機能'
description: 'Lync Server 2013: セキュリティの主要な機能。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Key security features in Lync Server 2013
ms:assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn342829(v=OCS.15)
ms:contentKeyID: 56107266
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 689cf2ac54eacd24bb4d31b451836edcf676521b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557613"
---
# <a name="key-security-features-in-lync-server-2013"></a><span data-ttu-id="446a4-103">Lync Server 2013 の主なセキュリティ機能</span><span class="sxs-lookup"><span data-stu-id="446a4-103">Key security features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="446a4-104">_**トピックの最終更新日:** 2013-07-18_</span><span class="sxs-lookup"><span data-stu-id="446a4-104">_**Topic Last Modified:** 2013-07-18_</span></span>

<span data-ttu-id="446a4-105">Lync Server 2013 には、サーバー間認証、役割ベースのアクセス制御、構成データの集中化されたストレージなど、いくつかのセキュリティ機能があります。</span><span class="sxs-lookup"><span data-stu-id="446a4-105">Lync Server 2013 includes several security features, including server-to-server authentication, role-based access control, and centralized storage of configuration data.</span></span>

<span data-ttu-id="446a4-106">この記事では、Lync Server 2013 のセキュリティの概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="446a4-106">This article provides a high level overview of Lync Server 2013 security.</span></span>

<div>

## <a name="key-security-features-in-lync-server-2013"></a><span data-ttu-id="446a4-107">Lync Server 2013 の主なセキュリティ機能</span><span class="sxs-lookup"><span data-stu-id="446a4-107">Key Security Features in Lync Server 2013</span></span>

<span data-ttu-id="446a4-108">セキュリティは非常に広範なトピックです。</span><span class="sxs-lookup"><span data-stu-id="446a4-108">Security is a very broad topic.</span></span> <span data-ttu-id="446a4-109">Lync Server 2013 のすべての機能に加えて、Lync エコシステムを構成するデータベース、サービス、ハードウェアのセキュリティが確保されます。</span><span class="sxs-lookup"><span data-stu-id="446a4-109">Security reaches across every feature of Lync Server 2013 as well as databases, services, and hardware that make up a Lync ecosystem.</span></span> <span data-ttu-id="446a4-110">この記事では、セキュリティを目的として設計された Lync Server 2013 の一部の機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="446a4-110">This article outlines some of the features in Lync Server 2013 in particular that are designed for security.</span></span>

<div>

## <a name="planning-and-design-tools"></a><span data-ttu-id="446a4-111">計画およびデザインツール</span><span class="sxs-lookup"><span data-stu-id="446a4-111">Planning and Design Tools</span></span>

<span data-ttu-id="446a4-112">Lync Server 2013 には、計画と設計を促進し、Lync Server コンポーネントを誤って構成する機会を減らすための2つのツールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="446a4-112">Lync Server 2013 provides two tools to facilitate planning and design and to reduce the chance of misconfiguring Lync Server components.</span></span>

  - <span data-ttu-id="446a4-113">トポロジ**計画ツール**は、多くのトポロジ設計プロセスを自動化します。</span><span class="sxs-lookup"><span data-stu-id="446a4-113">**Topology Planning Tool** automates much of the topology design process.</span></span> <span data-ttu-id="446a4-114">計画ツールの結果をトポロジビルダーにエクスポートできます。これは、Lync Server 2013 を実行している各サーバーをインストールするために必要なツールです。</span><span class="sxs-lookup"><span data-stu-id="446a4-114">You can export the results from the Planning Tool to Topology Builder, which is the tool that is required to install each server running Lync Server 2013.</span></span>

  - <span data-ttu-id="446a4-115">**トポロジビルダー** は、すべての構成情報を中央管理ストアに格納します。</span><span class="sxs-lookup"><span data-stu-id="446a4-115">**Topology Builder** stores all configuration information in the Central Management store.</span></span>

<span data-ttu-id="446a4-116">これらのツールの詳細については、「 [Planning For Lync Server 2013](lync-server-2013-planning.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="446a4-116">For details about these tools, see [Planning for Lync Server 2013](lync-server-2013-planning.md).</span></span>

</div>

<div>

## <a name="central-management-store"></a><span data-ttu-id="446a4-117">中央管理ストア</span><span class="sxs-lookup"><span data-stu-id="446a4-117">Central Management Store</span></span>

<span data-ttu-id="446a4-118">Lync Server 2013 では、サーバーとサービスに関する構成データは中央管理ストアに含まれています。</span><span class="sxs-lookup"><span data-stu-id="446a4-118">In Lync Server 2013, configuration data about servers and services is part of the Central Management store.</span></span> <span data-ttu-id="446a4-119">中央管理ストアは、Lync Server 展開の定義、セットアップ、管理、管理、説明、および運用に必要なデータの堅牢で schematized ストレージを提供します。</span><span class="sxs-lookup"><span data-stu-id="446a4-119">The Central Management store provides a robust, schematized storage of the data needed to define, set up, maintain, administer, describe, and operate a Lync Server deployment.</span></span> <span data-ttu-id="446a4-120">また、CMS はこのデータを検証して構成の一貫性も保証します。</span><span class="sxs-lookup"><span data-stu-id="446a4-120">It also validates the data to ensure configuration consistency.</span></span> <span data-ttu-id="446a4-121">この構成データに加えられたすべての変更は中央管理ストアで行われるため、"同期ができません" の問題が発生しなくなります。</span><span class="sxs-lookup"><span data-stu-id="446a4-121">All changes to this configuration data happen at the Central Management store, eliminating “out-of-sync” issues.</span></span>

<span data-ttu-id="446a4-122">このデータの読み取り専用のコピーは、エッジ サーバーを含めたトポロジ内のすべてのサーバーにレプリケートされます。</span><span class="sxs-lookup"><span data-stu-id="446a4-122">Read-only copies of the data are replicated to all servers in the topology, including Edge Servers and Survivable Branch Appliances.</span></span> <span data-ttu-id="446a4-123">レプリケーションは、既定でネットワークサービスのコンテキスト下で実行されるサービスによって管理されます。これにより、コンピューター上の単純なユーザーの権限とアクセス許可が減少します。</span><span class="sxs-lookup"><span data-stu-id="446a4-123">Replication is managed by a service that is, by default, run under the context of the Network service, reducing the rights and permissions to that of a simple user on the computer.</span></span>

</div>

<div>

## <a name="server-to-server-authentication"></a><span data-ttu-id="446a4-124">サーバー間認証</span><span class="sxs-lookup"><span data-stu-id="446a4-124">Server-to-Server Authentication</span></span>

<span data-ttu-id="446a4-125">Lync Server 2013 では、Open Authorization (OAuth) プロトコルを使用して、サーバー間で認証を構成できます。</span><span class="sxs-lookup"><span data-stu-id="446a4-125">In Lync Server 2013, authentication can be configured between servers by using the Open Authorization (OAuth) protocol.</span></span> <span data-ttu-id="446a4-126">たとえば、Exchange Server 2013 を実行しているサーバーでの認証を行うように Lync Server 2013 を構成できます。</span><span class="sxs-lookup"><span data-stu-id="446a4-126">For example, you can configure Lync Server 2013 to authenticate with a server that is running Exchange Server 2013.</span></span> <span data-ttu-id="446a4-127">Lync server と Exchange サーバーは、OAuth プロトコルを使用して相互に信頼することができます。</span><span class="sxs-lookup"><span data-stu-id="446a4-127">Using the OAuth protocol, the Lync server and the Exchange server can trust each other.</span></span> <span data-ttu-id="446a4-128">これにより、シームレスな方法で製品を統合することができます。</span><span class="sxs-lookup"><span data-stu-id="446a4-128">This provides the ability to integrate the products in a seamless manner.</span></span> <span data-ttu-id="446a4-129">詳細については、「 [Lync server 2013 でのサーバー間認証 (OAuth) およびパートナーアプリケーションの管理](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="446a4-129">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)</span></span>

</div>

<div>

## <a name="windows-powershell-based-management-and-web-based-management-interface"></a><span data-ttu-id="446a4-130">Windows PowerShell ベースの管理および Web ベースの管理インターフェイス</span><span class="sxs-lookup"><span data-stu-id="446a4-130">Windows PowerShell-based management and Web-based Management Interface</span></span>

<span data-ttu-id="446a4-131">Lync Server 2013 は、Windows PowerShell コマンドラインインターフェイス上に構築された強力な管理インターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="446a4-131">Lync Server 2013 provides a powerful management interface, built on the Windows PowerShell command-line interface.</span></span> <span data-ttu-id="446a4-132">これにはセキュリティを管理するためのコマンドレットが含まれており、ユーザーが簡単にまたは知らないうちにスクリプトを実行できないように、Windows PowerShell のセキュリティ機能が既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="446a4-132">It includes cmdlets for managing security, and Windows PowerShell security features are enabled by default so that users cannot easily or unknowingly run scripts.</span></span> <span data-ttu-id="446a4-133">つまり、セキュリティを最大限に高め、攻撃の手段を減少させるように、ソフトウェアの既定値が自動的に設定されています。</span><span class="sxs-lookup"><span data-stu-id="446a4-133">This means that the software defaults are set to automatically help maximize security and reduce the avenues of attack.</span></span> <span data-ttu-id="446a4-134">Lync Server 2013 での Windows PowerShell 管理サポートの詳細については、「 [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="446a4-134">For details about Windows PowerShell management support in Lync Server 2013, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span></span>

</div>

<div>

## <a name="role-based-access-control-rbac"></a><span data-ttu-id="446a4-135">役割ベースのアクセス制御 (RBAC)</span><span class="sxs-lookup"><span data-stu-id="446a4-135">Role-Based Access Control (RBAC)</span></span>

<span data-ttu-id="446a4-136">Microsoft Lync Server 2013 は、役割ベースのアクセス制御 (RBAC) を提供して、セキュリティの高い標準を維持しながら管理タスクを委任できるようにします。</span><span class="sxs-lookup"><span data-stu-id="446a4-136">Microsoft Lync Server 2013 provides role-based access control (RBAC) to enable you to delegate administrative tasks while maintaining high standards for security.</span></span> <span data-ttu-id="446a4-137">業務上必要な管理権限のみをユーザーに与える "最小限の特権" の原則に従って RBAC を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="446a4-137">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative rights that their jobs require.</span></span> <span data-ttu-id="446a4-138">Lync Server 2013 には、新しい役割を作成したり、既存の役割を変更したりする機能が導入されています。</span><span class="sxs-lookup"><span data-stu-id="446a4-138">Lync Server 2013 introduces the ability to create a new role and also the ability to modify an existing role.</span></span> <span data-ttu-id="446a4-139">詳細については、「 [Lync Server 2013 での役割ベースのアクセス制御の計画](lync-server-2013-planning-for-role-based-access-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="446a4-139">For details, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

</div>

</div>

<div>

## <a name="network-address-translation-nat"></a><span data-ttu-id="446a4-140">ネットワークアドレス変換 (NAT)</span><span class="sxs-lookup"><span data-stu-id="446a4-140">Network Address Translation (NAT)</span></span>

<span data-ttu-id="446a4-141">Lync Server 2013 は、エッジサーバーの内部インターフェイスでのネットワークアドレス変換 (NAT) の使用をサポートしていませんが、アクセスエッジサービス、Web 会議エッジサービス、および音声ビデオエッジサービスの外部インターフェイスを、単一および拡張統合エッジサーバートポロジの両方でネットワークアドレス変換 (NAT) を実行するルーターまたはファイアウォールの背後に配置することをサポート</span><span class="sxs-lookup"><span data-stu-id="446a4-141">Lync Server 2013 does not support the use of network address translation (NAT) on the internal interface of the Edge Server, but it does support placing the external interface of the Access Edge service, Web Conferencing Edge service, and A/V Edge service behind a router or firewall that performs network address translation (NAT) for both single and scaled consolidated Edge Server topologies.</span></span> <span data-ttu-id="446a4-142">ロードバランサー機器の背後にある複数のエッジサーバーは、NAT を使用できません。</span><span class="sxs-lookup"><span data-stu-id="446a4-142">Multiple Edge Servers behind a hardware load balancer cannot use NAT.</span></span> <span data-ttu-id="446a4-143">複数のエッジサーバーが外部インターフェイスで NAT を使用している場合は、ドメインネームシステム (DNS) 負荷分散が必要です。</span><span class="sxs-lookup"><span data-stu-id="446a4-143">If multiple Edge Servers use NAT on their external interfaces, Domain Name System (DNS) load balancing is required.</span></span> <span data-ttu-id="446a4-144">さらに、DNS 負荷分散を使用すると、エッジサーバープール内のエッジサーバーごとのパブリック IP アドレスの数を減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="446a4-144">In turn, using DNS load balancing allows you to reduce the number of public IP addresses per Edge Server in an Edge Server pool.</span></span> <span data-ttu-id="446a4-145">詳細については、「[Lync Server 2013 での外部ユーザーアクセスの計画](lync-server-2013-planning-for-external-user-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="446a4-145">For details, see[Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="446a4-146">Microsoft Office Communications Server 2007 の展開があり、企業とフェデレーションエンタープライズとの間で音声ビデオを使用する必要がある企業とフェデレーションを行う場合、ポート要件は展開された旧バージョンのエッジサーバー用のものになります。</span><span class="sxs-lookup"><span data-stu-id="446a4-146">If you federate with enterprises that have a Microsoft Office Communications Server 2007 deployment and you need to use audio/video between your enterprise and the federated enterprise, the port requirements will be those for the older version of the Edge Servers that are deployed.</span></span> <span data-ttu-id="446a4-147">たとえば、フェデレーションパートナーがエッジサーバーを Lync Server 2013 にアップグレードするまで、これらの古いバージョンに必要なポート範囲を両方のエンタープライズに対して開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="446a4-147">For example, the port ranges required for those older versions must be opened for both enterprises until the federated partner upgrades its Edge Servers to Lync Server 2013.</span></span> <span data-ttu-id="446a4-148">その時点で、ポート要件を確認し、新しい構成に応じて減少できます。</span><span class="sxs-lookup"><span data-stu-id="446a4-148">At that time, the port requirements can be reviewed and reduced according to the new configuration.</span></span>



</div>

</div>

<div>

## <a name="simplified-certificates-for-edge-servers"></a><span data-ttu-id="446a4-149">エッジサーバーの簡略化された証明書</span><span class="sxs-lookup"><span data-stu-id="446a4-149">Simplified Certificates for Edge Servers</span></span>

<span data-ttu-id="446a4-150">展開ウィザードはサブジェクト名 (SN) およびサブジェクト代替名 (SAN) を自動的に読む込むことができるため、不要で、安全でない可能性があるエントリを含める危険性が減少します。</span><span class="sxs-lookup"><span data-stu-id="446a4-150">The Deployment Wizard can automatically populate subject names (SNs) and subject alternative names (SANs), reducing the possibility of including unnecessary and potentially unsecure entries.</span></span>

</div>

<div>

## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a><span data-ttu-id="446a4-151">信頼できるコンピューティングのセキュリティ開発ライフサイクル (SDL)</span><span class="sxs-lookup"><span data-stu-id="446a4-151">Trustworthy Computing Security Development Lifecycle (SDL)</span></span>

<span data-ttu-id="446a4-152">Lync Server 2013 は、「」に記載されている「Microsoft の信頼できるコンピューティングのセキュリティ開発ライフサイクル (SDL)」に準拠して設計および開発されてい <https://go.microsoft.com/fwlink/?linkid=68761> ます。</span><span class="sxs-lookup"><span data-stu-id="446a4-152">Lync Server 2013 is designed and developed in compliance with the Microsoft Trustworthy Computing Security Development Lifecycle (SDL), which is described at <https://go.microsoft.com/fwlink/?linkid=68761>.</span></span>

  - <span data-ttu-id="446a4-153">設計による**信頼**    より安全な統合コミュニケーションシステムを作成するための最初の手順は、脅威モデルを設計し、設計された各機能をテストすることです。</span><span class="sxs-lookup"><span data-stu-id="446a4-153">**Trustworthy by Design**   The first step in creating a more secure unified communications system was to design threat models and test each feature as it was designed.</span></span> <span data-ttu-id="446a4-154">さらに、Microsoft は、予期しない製品の動作から生じるセキュリティの脆弱性を検出するために、設計された動作の外部でのテストを行います。</span><span class="sxs-lookup"><span data-stu-id="446a4-154">In addition, Microsoft performs testing outside of the designed behavior in order to find security vulnerabilities resulting from unexpected product behavior.</span></span> <span data-ttu-id="446a4-155">複数のセキュリティ関連の改善点がコーディング プロセスとコーディング手法に組み込まれました。</span><span class="sxs-lookup"><span data-stu-id="446a4-155">Multiple security-related improvements were built into the coding process and practices.</span></span> <span data-ttu-id="446a4-156">コードが最終的な製品にチェックインされる前に、ビルド時ツールにより、バッファー オーバーランおよびその他のセキュリティ脅威の可能性を検出します。</span><span class="sxs-lookup"><span data-stu-id="446a4-156">Build-time tools detect buffer overruns and other potential security threats before the code is checked in to the final product.</span></span> <span data-ttu-id="446a4-157">もちろん、すべての未知のセキュリティ脅威を防ぐように設計することは不可能です。</span><span class="sxs-lookup"><span data-stu-id="446a4-157">Of course, it is impossible to design against all unknown security threats.</span></span> <span data-ttu-id="446a4-158">完全なセキュリティを保証できるシステムはありません。</span><span class="sxs-lookup"><span data-stu-id="446a4-158">No system can guarantee complete security.</span></span> <span data-ttu-id="446a4-159">ただし、製品の開発は開始時にセキュリティ保護された設計原則を採用しているため、Lync Server 2013 には、そのアーキテクチャの基本的な部分として業界標準のセキュリティテクノロジが組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="446a4-159">However, because product development embraced secure design principles from the start, Lync Server 2013 incorporates industry standard security technologies as a fundamental part of its architecture.</span></span>

  - <span data-ttu-id="446a4-160">既定で信頼**できる**    既定では、Lync Server 2013 のネットワーク通信は暗号化されています。</span><span class="sxs-lookup"><span data-stu-id="446a4-160">**Trustworthy by Default**   By default, network communications in Lync Server 2013 are encrypted.</span></span> <span data-ttu-id="446a4-161">すべてのサーバーが証明書と Kerberos 認証、TLS、Secure Real-Time Transport Protocol (SRTP)、およびその他の業界標準の暗号化手法 (128 ビット Advanced Encryption Standard (AES) 暗号化を含む) を使用しているため、事実上すべての Lync Server データがネットワーク上で保護されています。</span><span class="sxs-lookup"><span data-stu-id="446a4-161">Because all servers use certificates and Kerberos authentication, TLS, Secure Real-Time Transport Protocol (SRTP), and other industry-standard encryption techniques, including 128-bit Advanced Encryption Standard (AES) encryption, virtually all Lync Server data is protected on the network.</span></span> <span data-ttu-id="446a4-162">また、役割ベースのアクセス制御を使用すると、Lync Server 2013 を実行しているサーバーを展開して、各サーバーの役割がサービスのみを実行し、そのサービスに関連するアクセス許可のみをサーバーの役割に適したように展開することができます。</span><span class="sxs-lookup"><span data-stu-id="446a4-162">In addition, role-based access control makes it possible to deploy servers running Lync Server 2013 so that each server role runs only the services, and has only the permissions related to those services, that are appropriate for the server role.</span></span>

  - <span data-ttu-id="446a4-163">展開による**信頼**    すべての Lync Server 2013 ドキュメントには、展開に最適なセキュリティレベルを決定および構成し、既定以外のオプションをアクティブ化する際のセキュリティリスクを評価するためのベストプラクティスと推奨事項が含まれています。</span><span class="sxs-lookup"><span data-stu-id="446a4-163">**Trustworthy by Deployment**   All Lync Server 2013 documentation includes best practices and recommendations to help you determine and configure the optimal security levels for your deployment and assess the security risks of activating non-default options.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

