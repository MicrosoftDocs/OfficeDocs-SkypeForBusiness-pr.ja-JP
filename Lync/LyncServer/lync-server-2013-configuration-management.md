---
title: 'Lync Server 2013: 構成管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration management
ms:assetid: 00ea1196-cb40-427f-99a4-5e8037cbf367
ms:mtpsurl: https://technet.microsoft.com/library/Dn720316(v=OCS.15)
ms:contentKeyID: 63969570
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de390f21c76a9636fc9ba2d6a7d3ee017681b6ba
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507834"
---
# <a name="configuration-management-in-lync-server-2013"></a><span data-ttu-id="31649-102">Lync Server 2013 での構成管理</span><span class="sxs-lookup"><span data-stu-id="31649-102">Configuration management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31649-103">_**トピックの最終更新日:** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="31649-103">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="31649-104">構成管理は、ハードウェアとソフトウェアの資産とシステム構成情報を記録および追跡するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="31649-104">Configuration management is the process of recording and tracking hardware and software assets and system configuration information.</span></span> <span data-ttu-id="31649-105">通常は、ソフトウェアライセンスの追跡、クライアントコンピューターとサーバーの標準的なハードウェアとソフトウェアのビルドの維持、新しいコンピューターの命名規則の定義に使用されます。</span><span class="sxs-lookup"><span data-stu-id="31649-105">It is generally used to track software licenses, maintain a standard hardware and software build for client computers and servers, and define naming standards for new computers.</span></span> <span data-ttu-id="31649-106">構成管理では、一般的に次のカテゴリについて説明します。</span><span class="sxs-lookup"><span data-stu-id="31649-106">Configuration management generally covers the following categories:</span></span>

  - <span data-ttu-id="31649-107">**ハードウェア**    このカテゴリは、IT 組織が所有する装置、機器の所在、および機器の使用者を追跡します。</span><span class="sxs-lookup"><span data-stu-id="31649-107">**Hardware**   This category tracks the pieces of equipment that the IT organization owns, where equipment is located, and who uses equipment.</span></span> <span data-ttu-id="31649-108">この情報によって、組織はアップグレードを計画および予算化し、標準のハードウェア構築を維持し、会計目的の IT 資産の価値に関するレポートを作成し、盗難防止に役立てることができます。</span><span class="sxs-lookup"><span data-stu-id="31649-108">This information enables an organization to plan and budget for upgrades, maintain standard hardware builds, report on the value of IT assets for accounting purposes, and help prevent theft.</span></span>

  - <span data-ttu-id="31649-109">**ソフトウェア**    このカテゴリは、各コンピューターにインストールされているソフトウェア、バージョン番号、およびライセンスが保持されている場所を追跡します。</span><span class="sxs-lookup"><span data-stu-id="31649-109">**Software**   This category tracks software that is installed on each computer, the version numbers, and where the licenses are held.</span></span> <span data-ttu-id="31649-110">この情報は、アップグレードを計画し、ソフトウェアがライセンスされていることを確認し、認証されていない (およびライセンスされていない) ソフトウェアが存在することを検出するのに役立つ</span><span class="sxs-lookup"><span data-stu-id="31649-110">This information helps plan upgrades, to ensure that software is licensed, and detect the presence of unauthorized (and unlicensed) software.</span></span>

  - <span data-ttu-id="31649-111">**標準ビルド**    このカテゴリは、クライアントコンピューターとサーバーの現在の標準ビルドを追跡し、クライアントコンピューターとサーバーがこの標準を満たしているかどうかを追跡します。</span><span class="sxs-lookup"><span data-stu-id="31649-111">**Standard Builds**   This category tracks the current standard build for the client computers and servers and whether the client computers and servers meet this standard.</span></span> <span data-ttu-id="31649-112">スタッフは、ソフトウェアの各機能について限られた数のバージョンのみを保持する必要があるため、標準ビルドを定義して適用すると、スタッフをサポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="31649-112">Defining and enforcing standard builds helps support staff because the staff is required to maintain only a limited number of versions of each piece of software.</span></span>

  - <span data-ttu-id="31649-113">**累積的な更新プログラムと修正プログラム**    このカテゴリでは、どのサービスパックがテストされ、使用が承認され、どのコンピューターが最新のものであるかを追跡します。</span><span class="sxs-lookup"><span data-stu-id="31649-113">**Cumulative Updates and Hotfixes**   This category tracks which service packs are tested and approved for use and which computers are up to date.</span></span> <span data-ttu-id="31649-114">この情報は、コンピューターが危険にさらされるリスクを軽減し、承認されていない更新プログラムをインストールしたユーザーを検出するために重要です。</span><span class="sxs-lookup"><span data-stu-id="31649-114">This information is important to reduce the risk of computers being compromised and to detect users who have installed unapproved updates.</span></span>

  - <span data-ttu-id="31649-115">**システム構成情報**    このカテゴリは、システムの機能、システム要素間の相互作用、円滑に実行されているシステムに依存するプロセスを追跡します。</span><span class="sxs-lookup"><span data-stu-id="31649-115">**System Configuration Information**   This category tracks the function of a system, the interaction between system elements, and the processes that depend on a system that is running smoothly.</span></span> <span data-ttu-id="31649-116">たとえば、サードパーティのプロキシサーバーを1台のサーバーに構成することができます。</span><span class="sxs-lookup"><span data-stu-id="31649-116">For example, third-party proxy server may be configured on a single server.</span></span> <span data-ttu-id="31649-117">障害が発生した場合は、このサーバーへのプロキシサーバーの依存関係を理解し、危機計画が必要になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="31649-117">The proxy server’s dependence on this server should be understood and contingency plans may be required if there is a failure.</span></span> <span data-ttu-id="31649-118">プロキシサーバーが別のフロントエンドサーバーとも通信するように構成できる場合は、依存関係とコンティンジェンシー計画が変わる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="31649-118">If the proxy server can be configured to also communicate with another front-end server, dependencies and contingency plans will probably change.</span></span>

<div>

## <a name="implementing-configuration-management"></a><span data-ttu-id="31649-119">構成管理を実装する</span><span class="sxs-lookup"><span data-stu-id="31649-119">Implementing configuration management</span></span>

<span data-ttu-id="31649-120">管理が必要なアイテムを特定したら、データとレポートデータを収集して構成管理を実装します。</span><span class="sxs-lookup"><span data-stu-id="31649-120">After you determine what items need managing, implement configuration management by collecting data and reporting data.</span></span> <span data-ttu-id="31649-121">小規模な組織にとって最も簡単なアプローチは、データを手動で収集 (クライアントコンピューター、オペレーティングシステム、インストールされているソフトウェアの数とモデル) して、それを Office Word または Office Excel ドキュメントに保存することです。</span><span class="sxs-lookup"><span data-stu-id="31649-121">The simplest approach for small organizations is to collect data manually (number and model of client computers, operating system, installed software) and save it in an Office Word or Office Excel document.</span></span> <span data-ttu-id="31649-122">より大規模で複雑で、絶えず変化するシステムでは、アセットの検出と詳細情報の収集を自動化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="31649-122">For larger, more complex, and constantly changing systems, the discovery of assets and collection of detailed information must be automated.</span></span> <span data-ttu-id="31649-123">組織に関連する情報を決定し、データベースに記録します。</span><span class="sxs-lookup"><span data-stu-id="31649-123">Decide what information is relevant to your organization and record it in a database.</span></span>

<span data-ttu-id="31649-124">構成管理データベースは、以下の領域でのサポート担当者および管理者にとって便利なツールです。</span><span class="sxs-lookup"><span data-stu-id="31649-124">The configuration management database is a useful tool for support staff and management in the following areas:</span></span>

  - <span data-ttu-id="31649-125">**セキュリティ監査**    このデータベースを使用すると、修正プログラムを適用する必要があるか、service pack のインストールまたは最新のウイルス対策更新プログラムがインストールされていない、Lync Server およびクライアントコンピューターシステムを実行しているサーバーを識別できます。</span><span class="sxs-lookup"><span data-stu-id="31649-125">**Security Audits**   The database enables you to identify servers that are running Lync Server and client computer systems that must have hotfixes applied or that have missed the installation of a service pack or the latest antivirus updates.</span></span>

  - <span data-ttu-id="31649-126">**ソフトウェアのインストール**    クライアントソフトウェアのバージョンを特定し、追跡することにより、管理者はバージョンの更新プログラムと新規インストールの計画や、ライセンスのドキュメントとコンプライアンスのサポートを受けることができます。</span><span class="sxs-lookup"><span data-stu-id="31649-126">**Software Installation**   Identifying client software versions and tracking them will aid administrators in planning version updates and new installs and also by helping with licensing documentation and compliance.</span></span>

  - <span data-ttu-id="31649-127">**構成情報**    既定の設定から変更されたすべての設定の最新のリストを維持すると、問題の迅速かつ効率的なトラブルシューティングを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="31649-127">**Configuration Information**   If you maintain an up-to-date list of all settings that were changed from their default, then you'll be able to troubleshoot issues quickly and more effectively.</span></span>

  - <span data-ttu-id="31649-128">アップグレードを計画する**Planning Upgrades**    容量のレビューで、Lync データベースサーバーで追加の記憶域が必要であることが判明した場合は、各サーバーに内部 RAID コントローラーがあるかどうかを確認することが重要です。</span><span class="sxs-lookup"><span data-stu-id="31649-128">**Planning Upgrades**   If a capacity review reveals that additional storage space is required on your Lync database servers, it’s important to know whether each server has an internal RAID controller.</span></span> <span data-ttu-id="31649-129">その場合は、同じモデルになりますか。</span><span class="sxs-lookup"><span data-stu-id="31649-129">If they do, then are they the same model?</span></span> <span data-ttu-id="31649-130">同じ数のディスクがインストールされているか。</span><span class="sxs-lookup"><span data-stu-id="31649-130">Do they have the same number of disks installed?</span></span> <span data-ttu-id="31649-131">構成管理データベースは、インストール可能なディスクの種類、番号、および各ケースのアップグレードパスを示します。</span><span class="sxs-lookup"><span data-stu-id="31649-131">The configuration management database will indicate the type of disk that can be installed, the number, and the upgrade path in each case.</span></span>

</div>

<div>

## <a name="tools-used-for-configuration-management"></a><span data-ttu-id="31649-132">構成管理に使用するツール</span><span class="sxs-lookup"><span data-stu-id="31649-132">Tools used for configuration management</span></span>

<span data-ttu-id="31649-133">アセットを検出、監査、およびレポートするためのツールは数多くあります。</span><span class="sxs-lookup"><span data-stu-id="31649-133">There are many tools to discover, audit, and report assets.</span></span> <span data-ttu-id="31649-134">このセクションでは、これらのツールの一部について説明します。</span><span class="sxs-lookup"><span data-stu-id="31649-134">Some of these tools are discussed in this section.</span></span>

  - <span data-ttu-id="31649-135">**自動化**されたスクリプト    オペレーティングシステム、service pack レベル、特定のコンピューターのセットにソフトウェアが存在するかどうかなどのアイテムをレポートするための簡単なスクリプトを記述できます。</span><span class="sxs-lookup"><span data-stu-id="31649-135">**Automated Scripts**   You can write simple scripts to report items such as the operating system, service pack level, and whether software exists on a specific set of computers.</span></span> <span data-ttu-id="31649-136">これらのスクリプトは、組織の正確な要件に書き込むことができます。</span><span class="sxs-lookup"><span data-stu-id="31649-136">You can write these scripts to an organization’s exact requirements.</span></span> <span data-ttu-id="31649-137">しかし、必要なスクリプト数とその複雑さにより、スクリプトを作成して管理するのにコストがかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="31649-137">However, the required number of scripts and their complexity can make scripts expensive to create and maintain.</span></span>

  - <span data-ttu-id="31649-138">**自動化ツール**    ビジネスおよび組織のニーズに応じて、自動化ツールの使用を検討することもできます。</span><span class="sxs-lookup"><span data-stu-id="31649-138">**Automated Tools**   Depending on the size of your business and your organizational needs, you may want to consider using automated tools.</span></span> <span data-ttu-id="31649-139">Microsoft エンドポイント構成マネージャーなどのツールには、標準レポートテンプレート (service pack レベルなど) が組み込まれており、カスタマイズされたレポートを作成することもできます (たとえば、カスタムアプリケーションの場合)。</span><span class="sxs-lookup"><span data-stu-id="31649-139">Tools such as Microsoft Endpoint Configuration Manager incorporate standard report templates (such as service pack level) and also enable you to create customized reports, for example, for a custom application.</span></span> <span data-ttu-id="31649-140">また、Microsoft エンドポイント構成マネージャーを使用して、ハードウェアおよびソフトウェアの構成に関するレポートを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="31649-140">The Microsoft Endpoint Configuration Manager can also be used to report on hardware and software configurations.</span></span>

</div>

<div>

## <a name="relationship-with-change-management"></a><span data-ttu-id="31649-141">変更管理との関係</span><span class="sxs-lookup"><span data-stu-id="31649-141">Relationship with change management</span></span>

<span data-ttu-id="31649-142">構成管理は、変更管理に密接に関連しています。</span><span class="sxs-lookup"><span data-stu-id="31649-142">Configuration management is closely related to change management.</span></span> <span data-ttu-id="31649-143">構成管理変更の必要性を特定し、変更が発生したことを特定して記録します。</span><span class="sxs-lookup"><span data-stu-id="31649-143">Configuration management identifies the need for change and identifies and records that a change has occurred.</span></span> <span data-ttu-id="31649-144">たとえば、構成管理データベースを使用して、修正プログラムを必要とするサーバーを識別できます。</span><span class="sxs-lookup"><span data-stu-id="31649-144">For example, the configuration management database can be used to identify servers that require a hotfix.</span></span> <span data-ttu-id="31649-145">変更管理では、修正プログラムを適用するプロセスを定義します。</span><span class="sxs-lookup"><span data-stu-id="31649-145">Change management then defines the process for applying the hotfix.</span></span>

<span data-ttu-id="31649-146">反対に、新しい累積的な更新プログラムがロールアウトされた場合、変更管理プロセスはこの情報を構成管理システムに提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="31649-146">Conversely, if a new cumulative update is rolled out, the change management process should supply this information to the configuration management system.</span></span> <span data-ttu-id="31649-147">多くの場合、構成管理ツールでは、ソフトウェアが展開された場所とタイミングを検出して追跡できるように、新しいソフトウェアを識別するように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="31649-147">The configuration management tools will probably need to be configured to identify the new software so that they can discover and track where and when the software is deployed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

