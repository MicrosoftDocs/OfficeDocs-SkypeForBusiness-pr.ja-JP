---
title: 'Lync Server 2013: 環境テストに関する問題'
description: 'Lync Server 2013: 環境テストに関する問題。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Issues with the environment test
ms:assetid: ff1fe0d3-35b2-41ef-87e7-6a61e9e1d2ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205421(v=OCS.15)
ms:contentKeyID: 48185970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 551d7e914480e178e0558c1d17eefcf060c0688e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574973"
---
# <a name="issues-with-the-environment-test-in-lync-server-2013"></a><span data-ttu-id="ac955-103">Lync Server 2013 での環境テストに関する問題</span><span class="sxs-lookup"><span data-stu-id="ac955-103">Issues with the environment test in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac955-104">_**トピックの最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="ac955-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="ac955-105">ベストプラクティスアナライザーには、Lync Server 2013 環境がサポートされている構成であることを確認する方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="ac955-105">Best Practices Analyzer provides a way for you to verify that your Lync Server 2013 environment is a supported configuration.</span></span> <span data-ttu-id="ac955-106">Active Directory ドメインサービスのチェックの一部として、ベストプラクティスアナライザーは次の処理を行います。</span><span class="sxs-lookup"><span data-stu-id="ac955-106">As part of the Active Directory Domain Services check, Best Practices Analyzer does the following:</span></span>

  - <span data-ttu-id="ac955-107">Active Directory ドメインサービスのフォレストとスキーマの準備を検証します。</span><span class="sxs-lookup"><span data-stu-id="ac955-107">Verifies the Active Directory Domain Services forest and schema preparation.</span></span>

  - <span data-ttu-id="ac955-108">展開内の Active Directory ドメインサービスのサイトとドメインの数を示します。</span><span class="sxs-lookup"><span data-stu-id="ac955-108">Identifies the number of Active Directory Domain Services sites and domains in the deployment.</span></span>

  - <span data-ttu-id="ac955-109">フォレストとドメインのレベルを確認します。</span><span class="sxs-lookup"><span data-stu-id="ac955-109">Checks the forest and domain levels.</span></span>

  - <span data-ttu-id="ac955-110">ドメインコントローラーのバージョンを確認します。</span><span class="sxs-lookup"><span data-stu-id="ac955-110">Checks the domain controller version.</span></span>

  - <span data-ttu-id="ac955-111">ドメイン、構成、およびスキーマの名前付けコンテキストを識別します。</span><span class="sxs-lookup"><span data-stu-id="ac955-111">Identifies the domain, configuration, and schema naming context.</span></span>

  - <span data-ttu-id="ac955-112">有効なユーザーの数を識別します。</span><span class="sxs-lookup"><span data-stu-id="ac955-112">Identifies the number of enabled users.</span></span>

  - <span data-ttu-id="ac955-113">グローバル Active Directory ドメインサービス設定が保存されている場所をチェックします。</span><span class="sxs-lookup"><span data-stu-id="ac955-113">Checks where the global Active Directory Domain Services settings are stored.</span></span>

  - <span data-ttu-id="ac955-114">Lync Server のサービス接続ポイント (Scp) を確認します。</span><span class="sxs-lookup"><span data-stu-id="ac955-114">Checks for the service connection points (SCPs) for Lync Server.</span></span>

  - <span data-ttu-id="ac955-115">データベースバージョンを識別します。</span><span class="sxs-lookup"><span data-stu-id="ac955-115">Identifies the database version.</span></span>

<div>

## <a name="resolving-issues-with-the-environment"></a><span data-ttu-id="ac955-116">環境に関する問題の解決</span><span class="sxs-lookup"><span data-stu-id="ac955-116">Resolving Issues with the Environment</span></span>

<span data-ttu-id="ac955-117">環境テストで問題が検出された場合、これらの問題は、Active Directory の構成の問題、または特定のサーバーで実行されているソフトウェアのレベルによって発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ac955-117">If the environment test found problems with your environment, these problems are probably caused by issues with your Active Directory configuration or the level of software running on specific servers.</span></span> <span data-ttu-id="ac955-118">たとえば、ベストプラクティスアナライザーが Windows Server 2000 を実行している環境内のドメインコントローラーを識別する場合は、警告を発行し、それらのドメインコントローラーをサポートされているバージョンの Windows Server にアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac955-118">For example, if Best Practices Analyzer identifies any domain controllers in your environment that are running Windows Server 2000, it will issue a warning and you will need to upgrade those domain controllers to a supported version of Windows Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

