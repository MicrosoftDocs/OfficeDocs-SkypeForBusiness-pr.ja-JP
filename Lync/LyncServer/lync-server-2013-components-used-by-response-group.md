---
title: 'Lync Server 2013: 応答グループで使用されるコンポーネント'
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
ms.openlocfilehash: 81275ca027971d661d3323fbfc175c51d4f4d7d4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757061"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-response-group-in-lync-server-2013"></a><span data-ttu-id="320b1-102">Lync Server 2013 の応答グループで使用されるコンポーネント</span><span class="sxs-lookup"><span data-stu-id="320b1-102">Components used by Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="320b1-103">_**最終更新日:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="320b1-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="320b1-104">応答グループアプリケーションは、エンタープライズボイスの展開時に自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="320b1-104">The Response Group application is automatically enabled when you deploy Enterprise Voice.</span></span> <span data-ttu-id="320b1-105">このセクションでは、応答グループアプリケーションをサポートするコンポーネントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="320b1-105">This section describes the components that support the Response Group application.</span></span>

<div>

## <a name="response-group-components"></a><span data-ttu-id="320b1-106">応答グループのコンポーネント</span><span class="sxs-lookup"><span data-stu-id="320b1-106">Response Group Components</span></span>

<span data-ttu-id="320b1-107">次の Microsoft Lync Server 2013 コンポーネントは、応答グループアプリケーションをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="320b1-107">The following Microsoft Lync Server 2013 components support the Response Group application:</span></span>

  - <span data-ttu-id="320b1-108">**アプリケーションサービス**   アプリケーションサービスは、応答グループなどのユニファイドコミュニケーションアプリケーションを展開、ホスティング、および管理するためのプラットフォームを提供します。</span><span class="sxs-lookup"><span data-stu-id="320b1-108">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications, such as Response Group.</span></span> <span data-ttu-id="320b1-109">アプリケーションサービスは、フロントエンドプールとすべての Standard Edition サーバーの各フロントエンドサーバーに自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="320b1-109">The Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="320b1-110">**応答グループ**   アプリケーション応答グループアプリケーションは、アプリケーションサービスによってホストされるユニファイドコミュニケーションアプリケーションの1つです。</span><span class="sxs-lookup"><span data-stu-id="320b1-110">**Response Group application**   The Response Group application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="320b1-111">応答グループを展開すると、自動的に含まれます。</span><span class="sxs-lookup"><span data-stu-id="320b1-111">It is included automatically when you deploy Response Group.</span></span> <span data-ttu-id="320b1-112">応答グループアプリケーションは、複数のエージェントに着信通話をルーティングしてキューに発信します。</span><span class="sxs-lookup"><span data-stu-id="320b1-112">The Response Group application routes and queues incoming calls to groups of agents.</span></span>

  - <span data-ttu-id="320b1-113">**言語パック**   : 音声合成と音声認識をサポートするには、言語パックが必要です。</span><span class="sxs-lookup"><span data-stu-id="320b1-113">**Language pack**   A language pack is required to support text-to-speech and speech recognition.</span></span> <span data-ttu-id="320b1-114">これらの音声テクノロジは、メッセージの構成 (開始メッセージおよびその他のプロンプト、対話型音声応答 (IVR) による質問と回答など) に使用します。</span><span class="sxs-lookup"><span data-stu-id="320b1-114">These speech technologies are used when you configure messages, such as the welcome message and other prompts, and interactive voice response (IVR) questions and answers.</span></span> <span data-ttu-id="320b1-115">既定では、Lync Server 2013 を展開すると、サポートされている26言語パックがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="320b1-115">By default, the 26 supported language packs are installed when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="320b1-116">**オーディオファイル**   のオーディオファイルは、メッセージおよび保留中の音楽に使用されます。</span><span class="sxs-lookup"><span data-stu-id="320b1-116">**Audio files**   Audio files are used for messages and on-hold music.</span></span>

  - <span data-ttu-id="320b1-117">**ファイル**   ストア応答グループは、ファイルストアを使ってオーディオファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="320b1-117">**File Store**   Response Group uses File store to store audio files.</span></span> <span data-ttu-id="320b1-118">複数の応答グループプールでは、同じファイルストアのインスタンスを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="320b1-118">Multiple Response Group pools can use the same instance of File store.</span></span>

  - <span data-ttu-id="320b1-119">**応答グループ構成ツール**   応答グループ構成ツールは、応答グループの作成と構成に使用される web ベースのツールです。</span><span class="sxs-lookup"><span data-stu-id="320b1-119">**Response Group Configuration Tool**   The Response Group Configuration Tool is a web-based tool that is used to create and configure response groups.</span></span> <span data-ttu-id="320b1-120">応答グループの構成ツールは、Web サービスをインストールするときに含まれています。</span><span class="sxs-lookup"><span data-stu-id="320b1-120">The Response Group Configuration Tool is included when you install Web Services.</span></span>

  - <span data-ttu-id="320b1-121">**Microsoft lync server 2013 コントロールパネル**   lync server コントロールパネルを使用して、応答グループのエージェントグループとキューをセットアップして構成することができます。</span><span class="sxs-lookup"><span data-stu-id="320b1-121">**Microsoft Lync Server 2013 Control Panel**   You can use Lync Server Control Panel to setup and configure agent groups and queues for response groups.</span></span>

  - <span data-ttu-id="320b1-122">**Lync server management shell**   lync server 管理シェルコマンドレットを使用して、すべての応答グループの設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="320b1-122">**Lync Server Management Shell**   All Response Group settings can be configured by using Lync Server Management Shell cmdlets.</span></span>

  - <span data-ttu-id="320b1-123">**Microsoft Lync 2013**   正式なエージェント (グループへの通話を許可するには、グループへのサインインが必要なエージェント) Lync 2013 を使って、グループへのサインインとサインアウトを行います。</span><span class="sxs-lookup"><span data-stu-id="320b1-123">**Microsoft Lync 2013**   Formal agents (agents who are required to sign in to the group before they can accept calls for the group) use Lync 2013 to sign in to and sign out from the group.</span></span> <span data-ttu-id="320b1-124">エージェントグループが正式なエージェント用に構成されている場合、エージェントは Lync 2013 のメニュー項目をクリックして Internet Explorer を開き、グループへのサインインとグループからのサインアウト用の web ページ本体を表示します。</span><span class="sxs-lookup"><span data-stu-id="320b1-124">If an agent group is configured for formal agents, the agents click a menu item in Lync 2013 to open Internet Explorer and display a webpage console for signing in and out of the group.</span></span>

  - <span data-ttu-id="320b1-125">**Web サービス**   web サービスは、応答グループ構成ツール、エージェントのサインインとサインアウトコンソール、Lync Server コントロールパネル、応答グループクライアント Web サービスに必要です。</span><span class="sxs-lookup"><span data-stu-id="320b1-125">**Web Services**   Web Services is required for Response Group Configuration Tool, the agents’ sign-in and sign-out console, Lync Server Control Panel, and Response Group client web service.</span></span>

  - <span data-ttu-id="320b1-126">**応答グループクライアント web サービス**   応答グループアプリケーションは、サードパーティのアプリケーションで、エージェント、エージェントグループメンバーシップ、エージェントのサインイン状態、グループの通話状態、匿名通話をサポートするグループの情報を取得するために使用できるクライアント web サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="320b1-126">**Response Group Client Web Service**   Response Group application provides a client web service, which can be used by third-party applications to retrieve information about agents, agent group membership, agent sign-in status, call status for groups, and the groups that support anonymous calls.</span></span> <span data-ttu-id="320b1-127">Lync 2013 および Lync 2010 アテンダント応答グループクライアント Web サービスを使用して、エージェントが匿名呼び出しを行うときに使用できる応答グループの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="320b1-127">Lync 2013 and Lync 2010 Attendant use Response Group Client Web service to retrieve the list of response groups that agents can use to make anonymous calls.</span></span> <span data-ttu-id="320b1-128">Web サービスをインストールするときに、クライアント web サービスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="320b1-128">The client web service is included when you install Web Services.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

