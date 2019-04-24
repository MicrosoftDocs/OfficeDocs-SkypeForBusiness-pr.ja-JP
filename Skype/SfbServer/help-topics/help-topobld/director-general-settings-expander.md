---
title: ディレクターの全般設定の展開
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.DirectorGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2026d0dd-6745-4e53-8b44-acdc378b47d1
description: 既存の担当ディレクターの設定を編集するのには次のセクションが表示されます。
ms.openlocfilehash: 92ddafb0029f4860f4fd36ddb9a497d21deb97d2
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32226886"
---
# <a name="director-general-settings-expander"></a><span data-ttu-id="bb45f-103">ディレクターの全般設定の展開</span><span class="sxs-lookup"><span data-stu-id="bb45f-103">Director General Settings Expander</span></span>
 
<span data-ttu-id="bb45f-104">既存の担当ディレクターの設定を編集するのには次のセクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bb45f-104">To edit the settings for an existing Director, you are presented with the following sections:</span></span>
  
- <span data-ttu-id="bb45f-105">全般設定</span><span class="sxs-lookup"><span data-stu-id="bb45f-105">General settings</span></span>
    
- <span data-ttu-id="bb45f-106">Web サービス</span><span class="sxs-lookup"><span data-stu-id="bb45f-106">Web services</span></span>
    


## <a name="general-settings"></a><span data-ttu-id="bb45f-107">全般設定</span><span class="sxs-lookup"><span data-stu-id="bb45f-107">General settings</span></span>

<span data-ttu-id="bb45f-108">ディレクター プールの完全修飾ドメイン名 (FQDN) です。</span><span class="sxs-lookup"><span data-stu-id="bb45f-108">Fully qualified domain name (FQDN) of the Director pool.</span></span> <span data-ttu-id="bb45f-109">値を変更するには、サーバーの FQDN を編集します。</span><span class="sxs-lookup"><span data-stu-id="bb45f-109">Edit the FQDN of the server to change the value.</span></span> <span data-ttu-id="bb45f-110">新しい値と一致しているドメイン ネーム システム (DNS) ホスト (A) レコードがある必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb45f-110">You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>
  
<span data-ttu-id="bb45f-111">[**関連付け**] では、次の情報を編集または指定できます。</span><span class="sxs-lookup"><span data-stu-id="bb45f-111">In **Associations** you can edit or specify the following:</span></span>
  
<span data-ttu-id="bb45f-112">使用するディレクター プールのファイル共有。</span><span class="sxs-lookup"><span data-stu-id="bb45f-112">File share for the Director pool to use.</span></span> <span data-ttu-id="bb45f-113">トポロジ ビルダーでは、既に定義されている既存のファイル共有を選択するか、新しいファイル共有の定義を作成する**新規**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bb45f-113">Select an existing file share that has already been defined in Topology Builder, or click **New** to create a new file share definition.</span></span>
  
<span data-ttu-id="bb45f-114">SQL Server ストアを監視します。</span><span class="sxs-lookup"><span data-stu-id="bb45f-114">Monitoring SQL Server store.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="bb45f-115">新しく定義したトポロジの公開前に、指定するサーバーが存在し、ドメインに参加している必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb45f-115">Before publishing the newly defined topology, the server that you specify must exist and be joined to the domain.</span></span> <span data-ttu-id="bb45f-116">新しいファイル共有を作成した場合は、指定したサーバー上でファイル共有を作成しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="bb45f-116">If you created a new file share, the file share must be created on the server that you designate.</span></span> 
  
## <a name="web-services"></a><span data-ttu-id="bb45f-117">Web サービス</span><span class="sxs-lookup"><span data-stu-id="bb45f-117">Web services</span></span>

<span data-ttu-id="bb45f-118">編集またはディレクター プールの Web サービスの追加設定を指定、変更または、内部の Web サービスと外部の Web サービスの設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="bb45f-118">To edit or specify additional settings for the Web services on the Director pool, you modify or specify settings in the Internal Web services and External Web services.</span></span>
  
<span data-ttu-id="bb45f-119">**内部の web サービス**の次のように指定できます。</span><span class="sxs-lookup"><span data-stu-id="bb45f-119">For **Internal web services** you can specify the following:</span></span>
  
> [!CAUTION]
> <span data-ttu-id="bb45f-120">複数のフロント エンド プールまたはフロント エンド サーバーがある場合、外部 Web サービス FQDN 一意でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="bb45f-120">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="bb45f-121">などの**pool01.contoso.com**としては、外部の Web サービス サーバーをフロント エンド サーバーの FQDN を定義する場合は、別のフロント エンド プールまたはフロント エンド サーバーの**pool01.contoso.com**を使用できません。</span><span class="sxs-lookup"><span data-stu-id="bb45f-121">For example, if you define the external Web services FQDN of a Front End Server as **pool01.contoso.com**, you cannot use **pool01.contoso.com** for another Front End pool or Front End Server.</span></span> <span data-ttu-id="bb45f-122">ダイレクタを展開するも、外部 Web サービスのすべてのダイレクタに対して定義されている FQDN またはディレクター プールは、他の一意である必要がありますディレクターまたはディレクター プールも、すべてのフロント エンド プールまたはフロント エンド サーバーです。</span><span class="sxs-lookup"><span data-stu-id="bb45f-122">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="bb45f-123">自己定義の FQDN を内部 web サービスをオーバーライドする場合は、各 FQDN 一意でなければなりませんから、他のすべてのフロント エンド プール、ディレクターまたはディレクター プールです。</span><span class="sxs-lookup"><span data-stu-id="bb45f-123">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>
  
<span data-ttu-id="bb45f-124">[FQDN の上書き] を選択すると、プールの内部 Web サービス ID として別の FQDN を指定できます。</span><span class="sxs-lookup"><span data-stu-id="bb45f-124">If you select Override FQDN, you can specify a different FQDN for the Internal Web services identity on the pool.</span></span> <span data-ttu-id="bb45f-125">ディレクター プールに対して定義されている、既定では、設定、現在プール名です。</span><span class="sxs-lookup"><span data-stu-id="bb45f-125">By default, the setting is the current pool name as defined for the Director pool.</span></span>
  
<span data-ttu-id="bb45f-126">HTTP と HTTPS の展開を必要とするは、ポートをリッスンし、公開されているを指定できます。</span><span class="sxs-lookup"><span data-stu-id="bb45f-126">You can specify listening and published ports for HTTP and HTTPS that your deployment requires.</span></span> <span data-ttu-id="bb45f-127">ポート 80 の既定の設定を HTTP とポート 443 の HTTPS の最も一般的な設定は、通常、インフラストラクチャの設計、組織内の特定の要件がある場合を除き、変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="bb45f-127">The default setting of port 80 for HTTP and port 443 for HTTPS are the most common settings and typically do not need to be changed unless you have specific requirements within your organization and infrastructure design.</span></span>
  
<span data-ttu-id="bb45f-128">**外部 web サービス**は、次のように指定できます。</span><span class="sxs-lookup"><span data-stu-id="bb45f-128">For **External web services**, you can specify the following:</span></span>
  
<span data-ttu-id="bb45f-129">外部 Web サービスの FQDN を定義することができます。</span><span class="sxs-lookup"><span data-stu-id="bb45f-129">You can define the FQDN of the External Web services.</span></span> <span data-ttu-id="bb45f-130">ここで指定する FQDN は、通常、リバース プロキシなどの外部接続要件に含まれる要件に従って定義されます。</span><span class="sxs-lookup"><span data-stu-id="bb45f-130">The FQDN specified here will usually be defined by the requirements of your external connection requirements, such as the reverse proxy.</span></span>
  
<span data-ttu-id="bb45f-131">HTTP と HTTPS の展開を必要とするは、ポートをリッスンし、公開されているを指定できます。</span><span class="sxs-lookup"><span data-stu-id="bb45f-131">You can specify listening and published ports for HTTP and HTTPS that your deployment requires.</span></span> <span data-ttu-id="bb45f-132">既定の設定である HTTP のポート 8080 と HTTPS のポート 4443 が初期定義されています。</span><span class="sxs-lookup"><span data-stu-id="bb45f-132">The default settings of port 8080 for HTTP and port 4443 for HTTPS are defined initially.</span></span> <span data-ttu-id="bb45f-133">リッスン ポートのこれらの設定は、リバース プロキシと外部ネットワークの要件に応じて変更します。</span><span class="sxs-lookup"><span data-stu-id="bb45f-133">You change these settings for the listening ports based on what the requirements are for your reverse proxy and external network requirements.</span></span> <span data-ttu-id="bb45f-134">公開ポートは、既定で HTTP のポート 80 と HTTPS のポート 443 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="bb45f-134">The published ports are set to default of port 80 for HTTP and port 443 for HTTPS.</span></span> <span data-ttu-id="bb45f-135">ディレクター プールまたはディレクター サーバーは、着信要求をリッスンするポートについては、これらの値によって決まります。</span><span class="sxs-lookup"><span data-stu-id="bb45f-135">These values determine what ports the Director pool or Director server will listen for incoming requests.</span></span> <span data-ttu-id="bb45f-136">通常、これら必要はありません変更するには、プール上のポートの要件の競合がない限り、します。</span><span class="sxs-lookup"><span data-stu-id="bb45f-136">Typically, these do not need to be changed, unless there is conflict of port requirements on the pool.</span></span> <span data-ttu-id="bb45f-137">ポートと同じ値を使用して、内部および外部の公開されているポートが必要です。</span><span class="sxs-lookup"><span data-stu-id="bb45f-137">Internal and external published ports that use the same port values are expected.</span></span> <span data-ttu-id="bb45f-138">これは競合ではありません。</span><span class="sxs-lookup"><span data-stu-id="bb45f-138">This is not a conflict.</span></span>
  

