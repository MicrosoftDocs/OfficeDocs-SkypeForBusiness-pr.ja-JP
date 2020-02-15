---
title: 'フェーズ 10: 従来のサイトを使用停止にする'
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
ms.openlocfilehash: 6e46c2977289ae8fec1db26e4eb33dfd6736f838
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034377"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="phase-10-decommission-legacy-site"></a><span data-ttu-id="85aa7-102">フェーズ 10: 従来のサイトを使用停止にする</span><span class="sxs-lookup"><span data-stu-id="85aa7-102">Phase 10: Decommission legacy site</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85aa7-103">_**トピックの最終更新日:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="85aa7-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="85aa7-104">次のトピックでは、使用停止プールのガイダンス、および Office Communications Server 2007 R2 の従来の展開におけるサーバーとプールの非アクティブ化と削除について説明します。</span><span class="sxs-lookup"><span data-stu-id="85aa7-104">The following topics provide guidance in decommissioning pools, and deactivating and removing servers and pools from a legacy deployment of Office Communications Server 2007 R2.</span></span> <span data-ttu-id="85aa7-105">このセクションに記載されているすべての手順が必要なわけではありません。</span><span class="sxs-lookup"><span data-stu-id="85aa7-105">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="85aa7-106">個々のトピックの情報を読んで、どの使用停止の手順を使用するかを判断してください。</span><span class="sxs-lookup"><span data-stu-id="85aa7-106">Read the information in each of these topics to determine which decommissioning procedure to use.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="85aa7-107">ダイヤルイン会議の会議ディレクトリを Lync Server 2013 にインポートした場合は、プールの使用停止を開始する前に、会議ディレクトリの所有権を Lync Server 2013 に移行することが重要です。</span><span class="sxs-lookup"><span data-stu-id="85aa7-107">If you imported conference directories for dial-in conferencing to Lync Server 2013, it is important to transition conference directory ownership to Lync Server 2013 before you begin to decommission your pools.</span></span> <span data-ttu-id="85aa7-108">会議ディレクトリの所有権を最初に切り替えずにプールを使用停止すると、移行したすべての会議のダイヤルイン機能が動作しなくなります。</span><span class="sxs-lookup"><span data-stu-id="85aa7-108">If you decommission a pool without first transitioning conference directory ownership, the dial-in feature for all migrated meetings will no longer work.</span></span> <span data-ttu-id="85aa7-109">使用していたプールのそれぞれの会議ディレクトリについて、所有権を切り替えるための手順を 1 回ずつ実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="85aa7-109">You must perform the step to transition ownership once for each conference directory in your legacy pool.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="85aa7-110">従来の環境を使用停止にする前に、Microsoft ユニファイドコミュニケーションマネージ API (UCMA) アプリケーションの移行およびアップグレードの詳細については、「」を参照してください。<A href="http://go.microsoft.com/fwlink/p/?linkid=269555">http://go.microsoft.com/fwlink/p/?LinkId=269555</A></span><span class="sxs-lookup"><span data-stu-id="85aa7-110">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, prior to decommissioning your legacy environment, see <A href="http://go.microsoft.com/fwlink/p/?linkid=269555">http://go.microsoft.com/fwlink/p/?LinkId=269555</A></span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="85aa7-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="85aa7-111">In This Section</span></span>

  - [<span data-ttu-id="85aa7-112">会議ディレクトリを移動する</span><span class="sxs-lookup"><span data-stu-id="85aa7-112">Move conference directories</span></span>](move-conference-directories.md)

  - [<span data-ttu-id="85aa7-113">DNS SRV レコードを更新する</span><span class="sxs-lookup"><span data-stu-id="85aa7-113">Update DNS SRV records</span></span>](update-dns-srv-records_1.md)

  - [<span data-ttu-id="85aa7-114">サーバーとプールの使用停止</span><span class="sxs-lookup"><span data-stu-id="85aa7-114">Decommissioning servers and pools</span></span>](decommissioning-servers-and-pools.md)

  - [<span data-ttu-id="85aa7-115">BackCompatSite の削除</span><span class="sxs-lookup"><span data-stu-id="85aa7-115">Remove BackCompatSite</span></span>](remove-backcompatsite.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

