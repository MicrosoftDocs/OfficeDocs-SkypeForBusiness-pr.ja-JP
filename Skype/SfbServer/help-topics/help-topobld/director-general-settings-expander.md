---
title: ディレクターの全般設定の展開
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.DirectorGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2026d0dd-6745-4e53-8b44-acdc378b47d1
description: 既存のディレクターの設定を編集するために、以下のセクションが表示されます。
ms.openlocfilehash: 261593cd7b1f8f79588462cb57eb8ecc517dd4a3
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218988"
---
# <a name="director-general-settings-expander"></a><span data-ttu-id="b2d9a-103">ディレクターの全般設定の展開</span><span class="sxs-lookup"><span data-stu-id="b2d9a-103">Director General Settings Expander</span></span>
 
<span data-ttu-id="b2d9a-104">既存のディレクターの設定を編集するために、以下のセクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b2d9a-104">To edit the settings for an existing Director, you are presented with the following sections:</span></span>
  
- <span data-ttu-id="b2d9a-105">全般設定</span><span class="sxs-lookup"><span data-stu-id="b2d9a-105">General settings</span></span>
    
- <span data-ttu-id="b2d9a-106">Web サービス</span><span class="sxs-lookup"><span data-stu-id="b2d9a-106">Web services</span></span>
    


## <a name="general-settings"></a><span data-ttu-id="b2d9a-107">全般設定</span><span class="sxs-lookup"><span data-stu-id="b2d9a-107">General settings</span></span>

<span data-ttu-id="b2d9a-p101">ディレクター プールの完全修飾ドメイン名 (FQDN)。値を変更するには、サーバーの FQDN を編集します。新しい値と一致しているドメイン ネーム システム (DNS) ホスト (A) レコードがある必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2d9a-p101">Fully qualified domain name (FQDN) of the Director pool. Edit the FQDN of the server to change the value. You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>
  
<span data-ttu-id="b2d9a-111">[**関連付け**] では、次の情報を編集または指定できます。</span><span class="sxs-lookup"><span data-stu-id="b2d9a-111">In **Associations** you can edit or specify the following:</span></span>
  
<span data-ttu-id="b2d9a-112">使用するディレクター プールのファイル共有。</span><span class="sxs-lookup"><span data-stu-id="b2d9a-112">File share for the Director pool to use.</span></span> <span data-ttu-id="b2d9a-113">トポロジビルダーで既に定義されている既存のファイル共有を選択するか、[ **新規** ] をクリックして新しいファイル共有定義を作成します。</span><span class="sxs-lookup"><span data-stu-id="b2d9a-113">Select an existing file share that has already been defined in Topology Builder, or click **New** to create a new file share definition.</span></span>
  
<span data-ttu-id="b2d9a-114">SQL Server ストアの監視。</span><span class="sxs-lookup"><span data-stu-id="b2d9a-114">Monitoring SQL Server store.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b2d9a-p103">新しく定義したトポロジの公開前に、指定するサーバーが存在し、ドメインに参加している必要があります。新しいファイル共有を作成する場合、そのファイル共有は指定するサーバー上に作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2d9a-p103">Before publishing the newly defined topology, the server that you specify must exist and be joined to the domain. If you created a new file share, the file share must be created on the server that you designate.</span></span> 
  
## <a name="web-services"></a><span data-ttu-id="b2d9a-117">Web サービス</span><span class="sxs-lookup"><span data-stu-id="b2d9a-117">Web services</span></span>

<span data-ttu-id="b2d9a-118">ディレクター プールの Web サービスの設定を編集したり追加の設定を指定したりするには、内部 Web サービスと外部 Web サービスの設定を変更または指定します。</span><span class="sxs-lookup"><span data-stu-id="b2d9a-118">To edit or specify additional settings for the Web services on the Director pool, you modify or specify settings in the Internal Web services and External Web services.</span></span>
  
<span data-ttu-id="b2d9a-119">[**内部 Web サービス**] では、次の情報を指定できます。</span><span class="sxs-lookup"><span data-stu-id="b2d9a-119">For **Internal web services** you can specify the following:</span></span>
  
> [!CAUTION]
> <span data-ttu-id="b2d9a-120">フロントエンドプールまたはフロントエンドサーバーが複数ある場合は、外部 Web サービスの FQDN が一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2d9a-120">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="b2d9a-121">たとえば、フロントエンドサーバーの外部 Web サービスの FQDN を **pool01.contoso.com**として定義した場合、別のフロントエンドプールまたはフロントエンドサーバーに **pool01.contoso.com** を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="b2d9a-121">For example, if you define the external Web services FQDN of a Front End Server as **pool01.contoso.com**, you cannot use **pool01.contoso.com** for another Front End pool or Front End Server.</span></span> <span data-ttu-id="b2d9a-122">ディレクターを展開している場合は、ディレクターまたはディレクタープールに対して定義されている外部 Web サービスの FQDN が、他のすべてのディレクターまたはディレクタープールと、フロントエンドプールまたはフロントエンドサーバーとも一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2d9a-122">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="b2d9a-123">内部 web サービスを自己定義の FQDN で上書きする場合、各 FQDN は他のフロントエンドプール、ディレクター、またはディレクタープールとは一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2d9a-123">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>
  
<span data-ttu-id="b2d9a-p105">[FQDN のオーバーライド] を選択する場合は、プールの内部 Web サービス ID として別の FQDN を指定できます。既定では、この設定はディレクター プールに定義されている現在のプール名です。</span><span class="sxs-lookup"><span data-stu-id="b2d9a-p105">If you select Override FQDN, you can specify a different FQDN for the Internal Web services identity on the pool. By default, the setting is the current pool name as defined for the Director pool.</span></span>
  
<span data-ttu-id="b2d9a-p106">展開で必要となる HTTP および HTTPS のリッスン ポートと公開ポートを指定できます。既定の設定である HTTP のポート 80 と HTTPS のポート 443 は、最も一般的な設定です。通常、組織内またはインフラストラクチャ設計上の特別な要件がない限り、変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b2d9a-p106">You can specify listening and published ports for HTTP and HTTPS that your deployment requires. The default setting of port 80 for HTTP and port 443 for HTTPS are the most common settings and typically do not need to be changed unless you have specific requirements within your organization and infrastructure design.</span></span>
  
<span data-ttu-id="b2d9a-128">[**外部 Web サービス**] では、次の情報を指定できます。</span><span class="sxs-lookup"><span data-stu-id="b2d9a-128">For **External web services**, you can specify the following:</span></span>
  
<span data-ttu-id="b2d9a-p107">外部 Web サービスの FQDN を定義できます。ここで指定する FQDN は、通常、リバース プロキシなどの外部接続要件に含まれる要件に従って定義されます。</span><span class="sxs-lookup"><span data-stu-id="b2d9a-p107">You can define the FQDN of the External Web services. The FQDN specified here will usually be defined by the requirements of your external connection requirements, such as the reverse proxy.</span></span>
  
<span data-ttu-id="b2d9a-p108">展開で必要となる HTTP および HTTPS のリッスン ポートと公開ポートを指定できます。既定の設定である HTTP 用のポート 8080 と HTTPS 用のポート 4443 は、最初に定義されます。リバース プロキシと外部ネットワークの要件に基づいて、リッスン ポートのこれらの設定を変更します。公開ポートは、既定で、HTTP の場合にはポート 80 に、HTTPS の場合にはポート 443 に設定されます。これらの値で、ディレクター プールまたはディレクター サーバーが着信要求をリッスンするポートを指定します。通常、プールでポート要件の競合がない限り、これらの値を変更する必要はありません。内部と外部の公開ポートで同じポート値が使用されることが予想されますが、これは競合ではありません。</span><span class="sxs-lookup"><span data-stu-id="b2d9a-p108">You can specify listening and published ports for HTTP and HTTPS that your deployment requires. The default settings of port 8080 for HTTP and port 4443 for HTTPS are defined initially. You change these settings for the listening ports based on what the requirements are for your reverse proxy and external network requirements. The published ports are set to default of port 80 for HTTP and port 443 for HTTPS. These values determine what ports the Director pool or Director server will listen for incoming requests. Typically, these do not need to be changed, unless there is conflict of port requirements on the pool. Internal and external published ports that use the same port values are expected. This is not a conflict.</span></span>
  

