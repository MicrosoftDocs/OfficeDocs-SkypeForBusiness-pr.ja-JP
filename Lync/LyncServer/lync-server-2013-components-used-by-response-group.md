---
title: 'Lync Server 2013: 応答グループによって使用されるコンポーネント'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Response Group
ms:assetid: 2b058785-47ca-43b7-b3de-6928a60dc685
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425768(v=OCS.15)
ms:contentKeyID: 48183693
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e6cf167917dc7d72484eb0fa833a688b0b4e4b8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136464"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-used-by-response-group-in-lync-server-2013"></a><span data-ttu-id="71852-102">Lync Server 2013 の応答グループによって使用されるコンポーネント</span><span class="sxs-lookup"><span data-stu-id="71852-102">Components used by Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71852-103">_**トピックの最終更新日:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="71852-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="71852-104">応答グループアプリケーションは、エンタープライズ Voip の展開時に自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="71852-104">The Response Group application is automatically enabled when you deploy Enterprise Voice.</span></span> <span data-ttu-id="71852-105">このセクションでは、応答グループアプリケーションをサポートするコンポーネントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="71852-105">This section describes the components that support the Response Group application.</span></span>

<div>

## <a name="response-group-components"></a><span data-ttu-id="71852-106">応答グループコンポーネント</span><span class="sxs-lookup"><span data-stu-id="71852-106">Response Group Components</span></span>

<span data-ttu-id="71852-107">次の Microsoft Lync Server 2013 コンポーネントは、応答グループアプリケーションをサポートします。</span><span class="sxs-lookup"><span data-stu-id="71852-107">The following Microsoft Lync Server 2013 components support the Response Group application:</span></span>

  - <span data-ttu-id="71852-108">**Application service**   アプリケーションサービスは、応答グループなどの統合コミュニケーションアプリケーションを展開、ホスト、および管理するためのプラットフォームを提供します。</span><span class="sxs-lookup"><span data-stu-id="71852-108">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications, such as Response Group.</span></span> <span data-ttu-id="71852-109">アプリケーションサービスは、フロントエンドプール内のすべてのフロントエンドサーバーとすべての Standard Edition サーバーに自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="71852-109">The Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="71852-110">**応答グループアプリケーション**   応答グループアプリケーションは、アプリケーションサービスによってホストされている統合コミュニケーションアプリケーションの1つです。</span><span class="sxs-lookup"><span data-stu-id="71852-110">**Response Group application**   The Response Group application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="71852-111">応答グループを展開するときに自動的に含まれます。</span><span class="sxs-lookup"><span data-stu-id="71852-111">It is included automatically when you deploy Response Group.</span></span> <span data-ttu-id="71852-112">応答グループアプリケーションは、エージェントのグループへの着信呼び出しをルーティングし、キューに入れます。</span><span class="sxs-lookup"><span data-stu-id="71852-112">The Response Group application routes and queues incoming calls to groups of agents.</span></span>

  - <span data-ttu-id="71852-113">**言語パック**   音声合成と音声認識をサポートするには、言語パックが必要です。</span><span class="sxs-lookup"><span data-stu-id="71852-113">**Language pack**   A language pack is required to support text-to-speech and speech recognition.</span></span> <span data-ttu-id="71852-114">これらの音声技術は、メッセージ (ウェルカムメッセージやその他の音声ガイダンス、音声応答 (IVR) の質問と回答など) を構成するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="71852-114">These speech technologies are used when you configure messages, such as the welcome message and other prompts, and interactive voice response (IVR) questions and answers.</span></span> <span data-ttu-id="71852-115">既定では、Lync Server 2013 を展開すると、サポートされている26言語パックがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="71852-115">By default, the 26 supported language packs are installed when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="71852-116">**オーディオファイル**   オーディオファイルは、メッセージおよび保留音に使用されます。</span><span class="sxs-lookup"><span data-stu-id="71852-116">**Audio files**   Audio files are used for messages and on-hold music.</span></span>

  - <span data-ttu-id="71852-117">**ファイル**   ストア応答グループは、ファイルストアを使用してオーディオファイルを格納します。</span><span class="sxs-lookup"><span data-stu-id="71852-117">**File Store**   Response Group uses File store to store audio files.</span></span> <span data-ttu-id="71852-118">複数の応答グループプールで、同じインスタンスのファイルストアを使用できます。</span><span class="sxs-lookup"><span data-stu-id="71852-118">Multiple Response Group pools can use the same instance of File store.</span></span>

  - <span data-ttu-id="71852-119">**応答グループ構成ツール**   応答グループ構成ツールは、応答グループの作成と構成に使用される web ベースのツールです。</span><span class="sxs-lookup"><span data-stu-id="71852-119">**Response Group Configuration Tool**   The Response Group Configuration Tool is a web-based tool that is used to create and configure response groups.</span></span> <span data-ttu-id="71852-120">Web サービスをインストールするときに、応答グループ構成ツールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="71852-120">The Response Group Configuration Tool is included when you install Web Services.</span></span>

  - <span data-ttu-id="71852-121">**Microsoft lync server 2013 コントロールパネル**   Lync server コントロールパネルを使用して、応答グループのエージェントグループおよびキューをセットアップして構成することができます。</span><span class="sxs-lookup"><span data-stu-id="71852-121">**Microsoft Lync Server 2013 Control Panel**   You can use Lync Server Control Panel to setup and configure agent groups and queues for response groups.</span></span>

  - <span data-ttu-id="71852-122">**Lync server 管理シェル**   lync server 管理シェルコマンドレットを使用して、すべての応答グループ設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="71852-122">**Lync Server Management Shell**   All Response Group settings can be configured by using Lync Server Management Shell cmdlets.</span></span>

  - <span data-ttu-id="71852-123">**Microsoft Lync 2013**   正式エージェント (グループへの通話を受け付ける前にグループにサインインする必要があるエージェント) は、lync 2013 を使用して、グループにサインインし、グループからサインアウトします。</span><span class="sxs-lookup"><span data-stu-id="71852-123">**Microsoft Lync 2013**   Formal agents (agents who are required to sign in to the group before they can accept calls for the group) use Lync 2013 to sign in to and sign out from the group.</span></span> <span data-ttu-id="71852-124">エージェントグループが正式なエージェントに対して構成されている場合、エージェントは Lync 2013 のメニュー項目をクリックして、Internet Explorer を開き、グループにサインインおよびサインアウトするための web ページコンソールを表示します。</span><span class="sxs-lookup"><span data-stu-id="71852-124">If an agent group is configured for formal agents, the agents click a menu item in Lync 2013 to open Internet Explorer and display a webpage console for signing in and out of the group.</span></span>

  - <span data-ttu-id="71852-125">**Web サービス**   web サービスは、応答グループ構成ツール、エージェントのサインインとサインアウトコンソール、Lync Server コントロールパネル、応答グループクライアント Web サービスに必要です。</span><span class="sxs-lookup"><span data-stu-id="71852-125">**Web Services**   Web Services is required for Response Group Configuration Tool, the agents’ sign-in and sign-out console, Lync Server Control Panel, and Response Group client web service.</span></span>

  - <span data-ttu-id="71852-126">**応答グループクライアント web サービス**   応答グループアプリケーションは、クライアント web サービスを提供します。これは、サードパーティのアプリケーションがエージェント、エージェントグループのメンバーシップ、エージェントのサインイン状態、グループの呼び出しの状態、匿名呼び出しをサポートするグループの情報を取得するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="71852-126">**Response Group Client Web Service**   Response Group application provides a client web service, which can be used by third-party applications to retrieve information about agents, agent group membership, agent sign-in status, call status for groups, and the groups that support anonymous calls.</span></span> <span data-ttu-id="71852-127">Lync 2013 および Lync 2010 アテンダントは応答グループクライアント Web サービスを使用して、エージェントが匿名呼び出しを行うために使用できる応答グループの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="71852-127">Lync 2013 and Lync 2010 Attendant use Response Group Client Web service to retrieve the list of response groups that agents can use to make anonymous calls.</span></span> <span data-ttu-id="71852-128">Web サービスをインストールすると、クライアント web サービスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="71852-128">The client web service is included when you install Web Services.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

