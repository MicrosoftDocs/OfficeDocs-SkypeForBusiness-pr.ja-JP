---
title: 'Lync Server 2013: ベストプラクティスアナライザーの概要'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Best Practices Analyzer
ms:assetid: c5fcaa05-eb1c-4092-90ad-177b127e795b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591349(v=OCS.15)
ms:contentKeyID: 48185364
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a11cebfe1b8344bcad0385bbe17bb26277c498c1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153287"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="71e00-102">Lync Server 2013 のベストプラクティスアナライザーの概要</span><span class="sxs-lookup"><span data-stu-id="71e00-102">Overview of Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71e00-103">_**トピックの最終更新日:** 2012-09-19_</span><span class="sxs-lookup"><span data-stu-id="71e00-103">_**Topic Last Modified:** 2012-09-19_</span></span>

<span data-ttu-id="71e00-104">Lync Server 2013、ベストプラクティスアナライザーを使用して、Lync Server 2013 の展開に関する問題を特定し、解決することができます。</span><span class="sxs-lookup"><span data-stu-id="71e00-104">You can use Lync Server 2013, Best Practices Analyzer to identify and resolve problems with your Lync Server 2013 deployment.</span></span> <span data-ttu-id="71e00-105">Lync Server 2013、ベストプラクティスアナライザーは、Lync Server 2013 コンポーネントから構成情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="71e00-105">The Lync Server 2013, Best Practices Analyzer gathers configuration information from Lync Server 2013 components.</span></span>

<span data-ttu-id="71e00-106">適切なネットワークアクセスにより、ベストプラクティスアナライザーは、Active Directory ドメインサービス、Exchange Server ユニファイドメッセージング (UM)、および Lync Server 2013 を実行しているサーバーを調査できます。</span><span class="sxs-lookup"><span data-stu-id="71e00-106">With the proper network access, the Best Practices Analyzer can examine servers running Active Directory Domain Services, Exchange Server Unified Messaging (UM), and Lync Server 2013.</span></span> <span data-ttu-id="71e00-107">ベスト プラクティス アナライザーを使用して実行できるのは、以下の作業です。</span><span class="sxs-lookup"><span data-stu-id="71e00-107">You can use Best Practices Analyzer to do the following:</span></span>

  - <span data-ttu-id="71e00-108">事前にチェックを実行して、推奨されるベスト プラクティスに従って構成が設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="71e00-108">Proactively perform checks, verifying that the configuration is set according to recommended best practices.</span></span>

  - <span data-ttu-id="71e00-109">Lync Server 2013 に対する必要な更新プログラムを自動的に検出します。</span><span class="sxs-lookup"><span data-stu-id="71e00-109">Automatically detect required updates to Lync Server 2013.</span></span>

  - <span data-ttu-id="71e00-110">最適化されていない構成設定、サポートされていないオプション、適用されていない更新プログラム、推奨されないプラクティスなど、問題の一覧を生成します。</span><span class="sxs-lookup"><span data-stu-id="71e00-110">Generate a list of issues, such as suboptimal configuration settings, unsupported options, missing updates, or practices that we do not recommend.</span></span>

  - <span data-ttu-id="71e00-111">特定の問題のトラブルシューティングと修正を支援します。</span><span class="sxs-lookup"><span data-stu-id="71e00-111">Help you troubleshoot and fix specific problems.</span></span>

<span data-ttu-id="71e00-112">ベスト プラクティス アナライザーは、以下の特徴を備えています。</span><span class="sxs-lookup"><span data-stu-id="71e00-112">Best Practices Analyzer provides the following features:</span></span>

  - <span data-ttu-id="71e00-113">最小限のインストールの前提条件。</span><span class="sxs-lookup"><span data-stu-id="71e00-113">Minimal installation prerequisites.</span></span>

  - <span data-ttu-id="71e00-114">トラブルシューティングのヒントなど、レポートされた問題に関するオンライン ドキュメント。</span><span class="sxs-lookup"><span data-stu-id="71e00-114">Online documentation about reported issues, including troubleshooting tips.</span></span>

  - <span data-ttu-id="71e00-115">保存しておいて後で確認できる構成情報。</span><span class="sxs-lookup"><span data-stu-id="71e00-115">Configuration information that you can save for later review.</span></span>

  - <span data-ttu-id="71e00-116">最先端のシステム分析。</span><span class="sxs-lookup"><span data-stu-id="71e00-116">State-of-the-art system analysis.</span></span>

<span data-ttu-id="71e00-117">ベストプラクティスアナライザーは、一連の XML 構成ファイルを使用して、Lync Server 2013 環境から収集する情報を決定します。</span><span class="sxs-lookup"><span data-stu-id="71e00-117">Best Practices Analyzer uses a set of XML configuration files to determine the information to gather from your Lync Server 2013 environment.</span></span> <span data-ttu-id="71e00-118">Active Directory ドメイン サービスのチェックに加えて、Windows Management Instrumentation (WMI) での Windows Server オペレーティング システムのレジストリや設定などのソースをチェックします。</span><span class="sxs-lookup"><span data-stu-id="71e00-118">In addition to checking Active Directory Domain Services, it checks sources such as the Windows Server operating system registry and settings in Windows Management Instrumentation (WMI).</span></span>

<span data-ttu-id="71e00-119">ベストプラクティスアナライザーは、Lync Server 2013 の展開の設定と構成について、定義済みのルールのセットで収集したデータを比較します。</span><span class="sxs-lookup"><span data-stu-id="71e00-119">Best Practices Analyzer compares the data it gathers with a set of predefined rules for the settings and configurations of Lync Server 2013 deployments.</span></span>

<span data-ttu-id="71e00-120">収集したデータと事前定義されたルールを比較した後で、このツールは問題をレポートします。</span><span class="sxs-lookup"><span data-stu-id="71e00-120">After comparing the collected data with the predefined rules, the tool reports issues.</span></span> <span data-ttu-id="71e00-121">レポートに含まれるすべての問題について、ベストプラクティスアナライザーは、スキャンされた Lync Server 2013 環境および推奨される構成についての情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="71e00-121">For every issue that it reports, Best Practices Analyzer provides information about what was found in the scanned Lync Server 2013 environment and the recommended configuration.</span></span> <span data-ttu-id="71e00-122">また、特定の問題に関するさらに詳細な情報へのリンクも提供します。</span><span class="sxs-lookup"><span data-stu-id="71e00-122">Best Practices Analyzer also provides links to more detailed information about the specific issues.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="71e00-123">Lync Server 2013、ベストプラクティスアナライザーは、Lync Server 2013 コンポーネントからの構成情報のみを収集します。</span><span class="sxs-lookup"><span data-stu-id="71e00-123">The Lync Server 2013, Best Practices Analyzer gathers configuration information only from Lync Server 2013 components.</span></span> <span data-ttu-id="71e00-124">以前の環境のスキャンには、このツールの以前のバージョンを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="71e00-124">You can use the previous versions of the tool to scan previous environments.</span></span> <span data-ttu-id="71e00-125">詳細については、「 <A href="lync-server-2013-requirements-for-running-best-practices-analyzer.md">Lync Server 2013 でベストプラクティスアナライザーを実行するための要件</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71e00-125">For details, see <A href="lync-server-2013-requirements-for-running-best-practices-analyzer.md">Requirements for running Best Practices Analyzer in Lync Server 2013</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

