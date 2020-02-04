---
title: 'フェーズ 10: レガシサイトの廃止'
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: 'Phase 10: Decommission legacy site'
ms:assetid: d591a310-3b5c-4092-b19e-0349616e40df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205300(v=OCS.15)
ms:contentKeyID: 48185540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8110d41e5f6436bfdbecc64fe07d514b5d0538ac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757711"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="phase-10-decommission-legacy-site"></a><span data-ttu-id="b13e8-102">フェーズ 10: レガシサイトの廃止</span><span class="sxs-lookup"><span data-stu-id="b13e8-102">Phase 10: Decommission legacy site</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b13e8-103">_**最終更新日:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="b13e8-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="b13e8-104">次のトピックでは、Office Communications Server 2007 R2 のレガシ展開でのプールの廃止、サーバーとプールの無効化と削除に関するガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="b13e8-104">The following topics provide guidance in decommissioning pools, and deactivating and removing servers and pools from a legacy deployment of Office Communications Server 2007 R2.</span></span> <span data-ttu-id="b13e8-105">このセクションに記載されているすべての手順を行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b13e8-105">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="b13e8-106">以下の各トピックの情報を読み、使用する使用停止手順を確認してください。</span><span class="sxs-lookup"><span data-stu-id="b13e8-106">Read the information in each of these topics to determine which decommissioning procedure to use.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="b13e8-107">ダイヤルイン会議用の会議ディレクトリを Lync Server 2013 にインポートした場合は、プールの廃止を開始する前に、会議ディレクトリの所有権を Lync Server 2013 に移行することが重要です。</span><span class="sxs-lookup"><span data-stu-id="b13e8-107">If you imported conference directories for dial-in conferencing to Lync Server 2013, it is important to transition conference directory ownership to Lync Server 2013 before you begin to decommission your pools.</span></span> <span data-ttu-id="b13e8-108">最初に会議ディレクトリの所有権を移行することなくプールを廃止すると、移行したすべての会議のダイヤルイン機能が機能しなくなります。</span><span class="sxs-lookup"><span data-stu-id="b13e8-108">If you decommission a pool without first transitioning conference directory ownership, the dial-in feature for all migrated meetings will no longer work.</span></span> <span data-ttu-id="b13e8-109">従来のプールの各会議ディレクトリについて、所有権を1回移行する手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b13e8-109">You must perform the step to transition ownership once for each conference directory in your legacy pool.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b13e8-110">Microsoft ユニファイドコミュニケーションマネージ API (UCMA) アプリケーションの移行とアップグレードに関する情報については、「従来の環境を廃止する前に」を参照してください。<A href="http://go.microsoft.com/fwlink/p/?linkid=269555">http://go.microsoft.com/fwlink/p/?LinkId=269555</A></span><span class="sxs-lookup"><span data-stu-id="b13e8-110">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, prior to decommissioning your legacy environment, see <A href="http://go.microsoft.com/fwlink/p/?linkid=269555">http://go.microsoft.com/fwlink/p/?LinkId=269555</A></span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b13e8-111">このセクション中</span><span class="sxs-lookup"><span data-stu-id="b13e8-111">In This Section</span></span>

  - [<span data-ttu-id="b13e8-112">会議ディレクトリを移動する</span><span class="sxs-lookup"><span data-stu-id="b13e8-112">Move conference directories</span></span>](move-conference-directories.md)

  - [<span data-ttu-id="b13e8-113">DNS SRV レコードの更新</span><span class="sxs-lookup"><span data-stu-id="b13e8-113">Update DNS SRV records</span></span>](update-dns-srv-records_1.md)

  - [<span data-ttu-id="b13e8-114">サーバーとプールの無効化</span><span class="sxs-lookup"><span data-stu-id="b13e8-114">Decommissioning servers and pools</span></span>](decommissioning-servers-and-pools.md)

  - [<span data-ttu-id="b13e8-115">BackCompatSite を削除する</span><span class="sxs-lookup"><span data-stu-id="b13e8-115">Remove BackCompatSite</span></span>](remove-backcompatsite.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

