---
title: Office Communications Server 2007 R2 環境の確認
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify Office Communications Server 2007 R2 environment
ms:assetid: e051bdd5-e7ef-4754-8705-900b2c57f37c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721906(v=OCS.15)
ms:contentKeyID: 49733840
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9369ad631b772e0a73677ab3214e24083426148a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847928"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-office-communications-server-2007-r2-environment"></a><span data-ttu-id="70380-102">Office Communications Server 2007 R2 環境の確認</span><span class="sxs-lookup"><span data-stu-id="70380-102">Verify Office Communications Server 2007 R2 environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70380-103">_**最終更新日:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="70380-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="70380-104">Office Communications Server 2007 R2 を使用して、共存状態で Lync Server 2013 を展開する前に、Office Communications Server 2007 R2 サービスが構成されて開始されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="70380-104">Prior to deploying Lync Server 2013 in a coexistence state with Office Communications Server 2007 R2, you need to verify the Office Communications Server 2007 R2 services are configured and started.</span></span>

<span data-ttu-id="70380-105">**Office Communications Server 2007 R2 管理ツールを使用してプールが開始されていることを確認する**</span><span class="sxs-lookup"><span data-stu-id="70380-105">**Verify the Pool is started using the Office Communications Server 2007 R2 Administrative Tool**</span></span>

1.  <span data-ttu-id="70380-106">Office Communications Server 2007 R2 管理ツールを開きます。</span><span class="sxs-lookup"><span data-stu-id="70380-106">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="70380-107">[**フォレスト**] ノードを展開し、 **Standard Edition サーバー**または [**エンタープライズプール**] ノードを展開して、プールまたはサーバー名を展開します。</span><span class="sxs-lookup"><span data-stu-id="70380-107">Expand the **Forest** node, expand the **Standard Edition Servers** or **Enterprise pools** node, and then expand the pool or server name.</span></span>

3.  <span data-ttu-id="70380-108">サービスが Standard Edition サーバーまたはエンタープライズプールで実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="70380-108">Ensure that the services are running on the Standard Edition server or Enterprise pool.</span></span>
    
    <span data-ttu-id="70380-109">![Office Communications Server 2007 R2 管理コンソール](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2 管理コンソール")</span><span class="sxs-lookup"><span data-stu-id="70380-109">![Office Communications Server 2007 R2 Admin Console](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2 Admin Console")</span></span>

<span data-ttu-id="70380-110">**Office Communications Server 2007 R2 用に構成されているユーザーを確認する**</span><span class="sxs-lookup"><span data-stu-id="70380-110">**Review Users configured for Office Communications Server 2007 R2**</span></span>

1.  <span data-ttu-id="70380-111">Office Communications Server 2007 R2 管理ツールを開きます。</span><span class="sxs-lookup"><span data-stu-id="70380-111">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="70380-112">[**フォレスト**] ノードを展開し、 **Standard Edition サーバー**または [**エンタープライズプール**] ノードを展開して、プールまたはサーバー名を展開します。</span><span class="sxs-lookup"><span data-stu-id="70380-112">Expand the **Forest** node, expand the **Standard Edition Servers** or **Enterprise pools** node, and then expand the pool or server name.</span></span>

3.  <span data-ttu-id="70380-113">[**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="70380-113">Click **Users**.</span></span>

4.  <span data-ttu-id="70380-114">Office Communications Server 2007 R2 ユーザーの一覧を確認します。</span><span class="sxs-lookup"><span data-stu-id="70380-114">Verify the list of Office Communications Server 2007 R2 users.</span></span>
    
    <span data-ttu-id="70380-115">![OCS 管理ツールでユーザーを一覧表示]する(images/JJ721906.f6bb7c4f-cbed-4389-8d0a-69a28577f17a(OCS.15).jpg "OCS 管理ツールでユーザーを一覧表示")する</span><span class="sxs-lookup"><span data-stu-id="70380-115">![List fo users in OCS Admin tool](images/JJ721906.f6bb7c4f-cbed-4389-8d0a-69a28577f17a(OCS.15).jpg "List fo users in OCS Admin tool")</span></span>

<span data-ttu-id="70380-116">**従来の XMPP フェデレーションパートナーの構成を確認する**</span><span class="sxs-lookup"><span data-stu-id="70380-116">**Verify legacy XMPP Federated Partner Configuration**</span></span>

1.  <span data-ttu-id="70380-117">従来の XMPP サーバーから、管理ツール\\の [サービス] アプレットに移動します。</span><span class="sxs-lookup"><span data-stu-id="70380-117">From the legacy XMPP server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="70380-118">Office Communications Server XMPP ゲートウェイサービスが開始されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="70380-118">Verify that the Office Communications Server XMPP Gateway service is started.</span></span>
    
    <span data-ttu-id="70380-119">![Office Communications Server XMPP ゲートウェイサービス](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP ゲートウェイサービス")</span><span class="sxs-lookup"><span data-stu-id="70380-119">![Office Communications Server XMPP Gateway Service](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP Gateway Service")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

