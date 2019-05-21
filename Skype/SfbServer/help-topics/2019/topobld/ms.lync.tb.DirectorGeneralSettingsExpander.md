---
title: ディレクターの全般設定の展開
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.DirectorGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2026d0dd-6745-4e53-8b44-acdc378b47d1
ROBOTS: NOINDEX, NOFOLLOW
description: 既存のディレクターの設定を編集するには、次のセクションが表示されます。
ms.openlocfilehash: 92d0026f2bc769f32ca635435cd71866efb75d3e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280540"
---
# <a name="director-general-settings-expander"></a><span data-ttu-id="c0a4b-103">ディレクターの全般設定の展開</span><span class="sxs-lookup"><span data-stu-id="c0a4b-103">Director General Settings Expander</span></span>
 
<span data-ttu-id="c0a4b-104">既存のディレクターの設定を編集するには、次のセクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c0a4b-104">To edit the settings for an existing Director, you are presented with the following sections:</span></span>
  
- <span data-ttu-id="c0a4b-105">全般設定</span><span class="sxs-lookup"><span data-stu-id="c0a4b-105">General settings</span></span>
    
- <span data-ttu-id="c0a4b-106">Web サービス</span><span class="sxs-lookup"><span data-stu-id="c0a4b-106">Web services</span></span>
    

## <a name="general-settings"></a><span data-ttu-id="c0a4b-107">全般設定</span><span class="sxs-lookup"><span data-stu-id="c0a4b-107">General settings</span></span>

<span data-ttu-id="c0a4b-108">ディレクタープールの完全修飾ドメイン名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="c0a4b-108">Fully qualified domain name (FQDN) of the Director pool.</span></span> <span data-ttu-id="c0a4b-109">値を変更するには、サーバーの FQDN を編集します。</span><span class="sxs-lookup"><span data-stu-id="c0a4b-109">Edit the FQDN of the server to change the value.</span></span> <span data-ttu-id="c0a4b-110">新しい値と一致しているドメイン ネーム システム (DNS) ホスト (A) レコードがある必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0a4b-110">You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>
  
<span data-ttu-id="c0a4b-111">[**関連付け**] では、次の情報を編集または指定できます。</span><span class="sxs-lookup"><span data-stu-id="c0a4b-111">In **Associations** you can edit or specify the following:</span></span>
  
<span data-ttu-id="c0a4b-112">使用するディレクタープールのファイル共有。</span><span class="sxs-lookup"><span data-stu-id="c0a4b-112">File share for the Director pool to use.</span></span> <span data-ttu-id="c0a4b-113">Topology Builder で既に定義されている既存のファイル共有を選択するか、[**新規**] をクリックして新しいファイル共有定義を作成します。</span><span class="sxs-lookup"><span data-stu-id="c0a4b-113">Select an existing file share that has already been defined in Topology Builder, or click **New** to create a new file share definition.</span></span>
  
<span data-ttu-id="c0a4b-114">SQL Server ストアを監視しています。</span><span class="sxs-lookup"><span data-stu-id="c0a4b-114">Monitoring SQL Server store.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c0a4b-115">新しく定義したトポロジの公開前に、指定するサーバーが存在し、ドメインに参加している必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0a4b-115">Before publishing the newly defined topology, the server that you specify must exist and be joined to the domain.</span></span> <span data-ttu-id="c0a4b-116">新しいファイル共有を作成した場合は、指定したサーバー上にファイル共有を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0a4b-116">If you created a new file share, the file share must be created on the server that you designate.</span></span> 
  
## <a name="web-services"></a><span data-ttu-id="c0a4b-117">Web サービス</span><span class="sxs-lookup"><span data-stu-id="c0a4b-117">Web services</span></span>

<span data-ttu-id="c0a4b-118">ディレクタープールの Web サービスの追加設定を編集または指定するには、内部 Web サービスと外部 Web サービスの設定を変更または指定します。</span><span class="sxs-lookup"><span data-stu-id="c0a4b-118">To edit or specify additional settings for the Web services on the Director pool, you modify or specify settings in the Internal Web services and External Web services.</span></span>
  
<span data-ttu-id="c0a4b-119">**内部の web サービス**では、次のように指定できます。</span><span class="sxs-lookup"><span data-stu-id="c0a4b-119">For **Internal web services** you can specify the following:</span></span>
  
> [!CAUTION]
> <span data-ttu-id="c0a4b-120">複数のフロントエンドプールまたはフロントエンドサーバーがある場合は、外部 Web サービスの FQDN が一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0a4b-120">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="c0a4b-121">たとえば、フロントエンドサーバーの外部 Web サービス FQDN を**pool01.contoso.com**として定義する場合、別のフロントエンドプールまたはフロントエンドサーバーに対して**pool01.contoso.com**を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="c0a4b-121">For example, if you define the external Web services FQDN of a Front End Server as **pool01.contoso.com**, you cannot use **pool01.contoso.com** for another Front End pool or Front End Server.</span></span> <span data-ttu-id="c0a4b-122">ディレクターも展開する場合、任意のディレクターまたはディレクタープール用に定義された外部 Web サービスの FQDN は、他のすべてのディレクターまたはディレクタープールと、フロントエンドプールまたはフロントエンドサーバーから一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0a4b-122">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="c0a4b-123">自動定義の FQDN を使用して内部 web サービスを上書きする場合、各 FQDN は、他のフロントエンドプール、ディレクター、またはディレクタープールから一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0a4b-123">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>
  
<span data-ttu-id="c0a4b-124">[FQDN の上書き] を選択すると、プールの内部 Web サービス ID として別の FQDN を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c0a4b-124">If you select Override FQDN, you can specify a different FQDN for the Internal Web services identity on the pool.</span></span> <span data-ttu-id="c0a4b-125">既定では、設定は、ディレクタープールに対して定義されている現在のプール名です。</span><span class="sxs-lookup"><span data-stu-id="c0a4b-125">By default, the setting is the current pool name as defined for the Director pool.</span></span>
  
<span data-ttu-id="c0a4b-126">展開に必要な HTTP と HTTPS のリッスンポートと公開ポートを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c0a4b-126">You can specify listening and published ports for HTTP and HTTPS that your deployment requires.</span></span> <span data-ttu-id="c0a4b-127">HTTP のポート80と HTTPS 用のポート443の既定の設定は最も一般的な設定であり、組織とインフラストラクチャの設計時に特定の要件がある場合を除き、変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c0a4b-127">The default setting of port 80 for HTTP and port 443 for HTTPS are the most common settings and typically do not need to be changed unless you have specific requirements within your organization and infrastructure design.</span></span>
  
<span data-ttu-id="c0a4b-128">**外部の web サービス**の場合は、次のように指定できます。</span><span class="sxs-lookup"><span data-stu-id="c0a4b-128">For **External web services**, you can specify the following:</span></span>
  
<span data-ttu-id="c0a4b-129">外部 Web サービスの FQDN を定義できます。</span><span class="sxs-lookup"><span data-stu-id="c0a4b-129">You can define the FQDN of the External Web services.</span></span> <span data-ttu-id="c0a4b-130">ここで指定する FQDN は、通常、リバース プロキシなどの外部接続要件に含まれる要件に従って定義されます。</span><span class="sxs-lookup"><span data-stu-id="c0a4b-130">The FQDN specified here will usually be defined by the requirements of your external connection requirements, such as the reverse proxy.</span></span>
  
<span data-ttu-id="c0a4b-131">展開に必要な HTTP と HTTPS のリッスンポートと公開ポートを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c0a4b-131">You can specify listening and published ports for HTTP and HTTPS that your deployment requires.</span></span> <span data-ttu-id="c0a4b-132">既定の設定である HTTP のポート 8080 と HTTPS のポート 4443 が初期定義されています。</span><span class="sxs-lookup"><span data-stu-id="c0a4b-132">The default settings of port 8080 for HTTP and port 4443 for HTTPS are defined initially.</span></span> <span data-ttu-id="c0a4b-133">リッスン ポートのこれらの設定は、リバース プロキシと外部ネットワークの要件に応じて変更します。</span><span class="sxs-lookup"><span data-stu-id="c0a4b-133">You change these settings for the listening ports based on what the requirements are for your reverse proxy and external network requirements.</span></span> <span data-ttu-id="c0a4b-134">公開ポートは、既定で HTTP のポート 80 と HTTPS のポート 443 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="c0a4b-134">The published ports are set to default of port 80 for HTTP and port 443 for HTTPS.</span></span> <span data-ttu-id="c0a4b-135">これらの値によって、ディレクタープールまたはディレクターサーバーが着信要求をリッスンするポートが決まります。</span><span class="sxs-lookup"><span data-stu-id="c0a4b-135">These values determine what ports the Director pool or Director server will listen for incoming requests.</span></span> <span data-ttu-id="c0a4b-136">通常、プールのポート要件が競合しない限り、これらの変更は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="c0a4b-136">Typically, these do not need to be changed, unless there is conflict of port requirements on the pool.</span></span> <span data-ttu-id="c0a4b-137">同じポート値を使用する内部および外部公開ポートが想定されています。</span><span class="sxs-lookup"><span data-stu-id="c0a4b-137">Internal and external published ports that use the same port values are expected.</span></span> <span data-ttu-id="c0a4b-138">これは競合ではありません。</span><span class="sxs-lookup"><span data-stu-id="c0a4b-138">This is not a conflict.</span></span>
  

