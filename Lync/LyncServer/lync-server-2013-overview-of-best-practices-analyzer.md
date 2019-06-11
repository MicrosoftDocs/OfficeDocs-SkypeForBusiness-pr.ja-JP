---
title: 'Lync Server 2013: ベストプラクティスアナライザーの概要'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of Best Practices Analyzer
ms:assetid: c5fcaa05-eb1c-4092-90ad-177b127e795b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591349(v=OCS.15)
ms:contentKeyID: 48185364
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a304f33071b8be13c61c3f930f196113ac3af6de
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825689"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="97448-102">Lync Server 2013 のベストプラクティスアナライザーの概要</span><span class="sxs-lookup"><span data-stu-id="97448-102">Overview of Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97448-103">_**最終更新日:** 2012-09-19_</span><span class="sxs-lookup"><span data-stu-id="97448-103">_**Topic Last Modified:** 2012-09-19_</span></span>

<span data-ttu-id="97448-104">Lync Server 2013 のベストプラクティスアナライザーを使用して、Lync Server 2013 の展開に関する問題を特定して解決することができます。</span><span class="sxs-lookup"><span data-stu-id="97448-104">You can use Lync Server 2013, Best Practices Analyzer to identify and resolve problems with your Lync Server 2013 deployment.</span></span> <span data-ttu-id="97448-105">Lync Server 2013 のベストプラクティスアナライザーは、Lync Server 2013 コンポーネントから構成情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="97448-105">The Lync Server 2013, Best Practices Analyzer gathers configuration information from Lync Server 2013 components.</span></span>

<span data-ttu-id="97448-106">ベストプラクティスアナライザーは、適切なネットワークアクセスで、Active Directory ドメインサービス、Exchange Server ユニファイドメッセージング (UM)、および Lync Server 2013 を実行しているサーバーを調査できます。</span><span class="sxs-lookup"><span data-stu-id="97448-106">With the proper network access, the Best Practices Analyzer can examine servers running Active Directory Domain Services, Exchange Server Unified Messaging (UM), and Lync Server 2013.</span></span> <span data-ttu-id="97448-107">ベストプラクティスアナライザーを使用して、次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="97448-107">You can use Best Practices Analyzer to do the following:</span></span>

  - <span data-ttu-id="97448-108">事前にチェックを行い、推奨されるベストプラクティスに従って構成が設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="97448-108">Proactively perform checks, verifying that the configuration is set according to recommended best practices.</span></span>

  - <span data-ttu-id="97448-109">Lync Server 2013 に必要な更新プログラムを自動的に検出します。</span><span class="sxs-lookup"><span data-stu-id="97448-109">Automatically detect required updates to Lync Server 2013.</span></span>

  - <span data-ttu-id="97448-110">最適の構成設定、サポートされていないオプション、不足している更新、または推奨されないプラクティスなどの問題の一覧を生成します。</span><span class="sxs-lookup"><span data-stu-id="97448-110">Generate a list of issues, such as suboptimal configuration settings, unsupported options, missing updates, or practices that we do not recommend.</span></span>

  - <span data-ttu-id="97448-111">特定の問題のトラブルシューティングと解決に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="97448-111">Help you troubleshoot and fix specific problems.</span></span>

<span data-ttu-id="97448-112">ベストプラクティスアナライザーには、次の機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="97448-112">Best Practices Analyzer provides the following features:</span></span>

  - <span data-ttu-id="97448-113">インストールの最小要件。</span><span class="sxs-lookup"><span data-stu-id="97448-113">Minimal installation prerequisites.</span></span>

  - <span data-ttu-id="97448-114">トラブルシューティングのヒントを含む、報告された問題に関するオンラインドキュメント。</span><span class="sxs-lookup"><span data-stu-id="97448-114">Online documentation about reported issues, including troubleshooting tips.</span></span>

  - <span data-ttu-id="97448-115">後で確認するために保存できる構成情報。</span><span class="sxs-lookup"><span data-stu-id="97448-115">Configuration information that you can save for later review.</span></span>

  - <span data-ttu-id="97448-116">最新のシステムの分析。</span><span class="sxs-lookup"><span data-stu-id="97448-116">State-of-the-art system analysis.</span></span>

<span data-ttu-id="97448-117">ベストプラクティスアナライザーは、一連の XML 構成ファイルを使用して、Lync Server 2013 環境から収集する情報を決定します。</span><span class="sxs-lookup"><span data-stu-id="97448-117">Best Practices Analyzer uses a set of XML configuration files to determine the information to gather from your Lync Server 2013 environment.</span></span> <span data-ttu-id="97448-118">Active Directory ドメインサービスの確認に加えて、windows Server オペレーティングシステムのレジストリと、Windows Management Instrumentation (WMI) の設定などのソースを確認します。</span><span class="sxs-lookup"><span data-stu-id="97448-118">In addition to checking Active Directory Domain Services, it checks sources such as the Windows Server operating system registry and settings in Windows Management Instrumentation (WMI).</span></span>

<span data-ttu-id="97448-119">ベストプラクティスアナライザーは、収集したデータを、Lync Server 2013 展開の設定と構成に関する事前定義されたルールのセットと比較します。</span><span class="sxs-lookup"><span data-stu-id="97448-119">Best Practices Analyzer compares the data it gathers with a set of predefined rules for the settings and configurations of Lync Server 2013 deployments.</span></span>

<span data-ttu-id="97448-120">収集したデータと事前定義されたルールを比較した後、ツールによって問題が報告されます。</span><span class="sxs-lookup"><span data-stu-id="97448-120">After comparing the collected data with the predefined rules, the tool reports issues.</span></span> <span data-ttu-id="97448-121">レポートされるすべての問題について、ベストプラクティスアナライザーは、スキャンされた Lync Server 2013 環境と推奨される構成についての情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="97448-121">For every issue that it reports, Best Practices Analyzer provides information about what was found in the scanned Lync Server 2013 environment and the recommended configuration.</span></span> <span data-ttu-id="97448-122">ベストプラクティスアナライザーには、特定の問題に関する詳細情報へのリンクも含まれています。</span><span class="sxs-lookup"><span data-stu-id="97448-122">Best Practices Analyzer also provides links to more detailed information about the specific issues.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="97448-123">Lync Server 2013 のベストプラクティスアナライザーは、Lync Server 2013 コンポーネントからのみ構成情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="97448-123">The Lync Server 2013, Best Practices Analyzer gathers configuration information only from Lync Server 2013 components.</span></span> <span data-ttu-id="97448-124">以前のバージョンのツールを使用して、以前の環境をスキャンすることができます。</span><span class="sxs-lookup"><span data-stu-id="97448-124">You can use the previous versions of the tool to scan previous environments.</span></span> <span data-ttu-id="97448-125">詳細については、「 <A href="lync-server-2013-requirements-for-running-best-practices-analyzer.md">Lync Server 2013 でベストプラクティスアナライザーを実行するための要件</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97448-125">For details, see <A href="lync-server-2013-requirements-for-running-best-practices-analyzer.md">Requirements for running Best Practices Analyzer in Lync Server 2013</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

