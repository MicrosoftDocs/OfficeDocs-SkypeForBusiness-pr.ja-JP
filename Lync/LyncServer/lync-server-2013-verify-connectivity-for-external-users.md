---
title: 'Lync Server 2013: 外部ユーザーの接続の確認'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify connectivity for external users
ms:assetid: 5c02bd6e-1c96-448a-a21d-58c9961c6640
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398402(v=OCS.15)
ms:contentKeyID: 48184249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 577ba970e272e2306aae3a587d9ae014ba75ba17
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848239"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-connectivity-for-external-users-in-lync-server-2013"></a><span data-ttu-id="48d82-102">Lync Server 2013 での外部ユーザーの接続の確認</span><span class="sxs-lookup"><span data-stu-id="48d82-102">Verify connectivity for external users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48d82-103">_**最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="48d82-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="48d82-104">外部ユーザーへの接続を検証するには、ユーザーからサーバーおよびアクセスエッジサービスのポートへの接続を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="48d82-104">Validating connectivity for external users requires ensuring connectivity from users to the server and port for the Access Edge service.</span></span>

<span data-ttu-id="48d82-105">構成を確認し、外部ユーザーのアクセスに必要なシナリオに対して適切なメッセージの接続、送受信、受信を行うことができるようにするため<http://www.testocsconnectivity.com>の重要なリソース。リモート接続アナライザーサイト ()。</span><span class="sxs-lookup"><span data-stu-id="48d82-105">A valuable resource for confirming your configuration and the ability to connect, send and receive the correct messages for the scenarios that external user access requires is the Remote Connectivity Analyzer site (<http://www.testocsconnectivity.com>).</span></span> <span data-ttu-id="48d82-106">このサイトは、Microsoft サポートによって管理および管理されます。</span><span class="sxs-lookup"><span data-stu-id="48d82-106">The site is managed and maintained by Microsoft Support.</span></span> <span data-ttu-id="48d82-107">リモート接続アナライザーにアクセスするには、ブラウザーで Web サイトを開き、手順に従ってシナリオを選択します。</span><span class="sxs-lookup"><span data-stu-id="48d82-107">To reach the Remote Connectivity Analyzer, open the Web site in a browser and follow the instructions to select the scenario.</span></span>

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="48d82-108">外部ユーザーと外部アクセスの接続性をテストする</span><span class="sxs-lookup"><span data-stu-id="48d82-108">Test Connectivity of External Users and External access</span></span>

<span data-ttu-id="48d82-109">外部ユーザーアクセスのテストには、次のいずれか、またはすべてを含む、組織がサポートしている各種類の外部ユーザーを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="48d82-109">Tests for external user access should include each type of external user that your organization supports, including any or all of the following:</span></span>

  - <span data-ttu-id="48d82-110">少なくとも1つのフェデレーションドメインのユーザーを対象に、IM、プレゼンス、A/V、およびデスクトップ共有をテストします。</span><span class="sxs-lookup"><span data-stu-id="48d82-110">Users from at least one federated domain, and test IM, presence, A/V and desktop sharing.</span></span>

  - <span data-ttu-id="48d82-111">組織でサポートされている各パブリック IM サービスプロバイダーのユーザー (およびプロビジョニングが完了している場合)。</span><span class="sxs-lookup"><span data-stu-id="48d82-111">Users of each public IM service provider that your organization supports (and for which provisioning has been completed).</span></span>

  - <span data-ttu-id="48d82-112">匿名ユーザー。</span><span class="sxs-lookup"><span data-stu-id="48d82-112">Anonymous users.</span></span>

  - <span data-ttu-id="48d82-113">リモートで Lync にログインしていて、VPN を使用していない組織内のユーザー。</span><span class="sxs-lookup"><span data-stu-id="48d82-113">Users within your organization who are logged into Lync remotely, but not using VPN.</span></span>

<span data-ttu-id="48d82-114">これらのテストは、エッジサーバーが次の条件を持つかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="48d82-114">These tests determine whether your Edge Server is:</span></span>

  - <span data-ttu-id="48d82-115">ネットワーク外から telnet クライアントを使用して必要なポートをリッスンする。</span><span class="sxs-lookup"><span data-stu-id="48d82-115">Listening on the necessary ports by using a telnet client from outside your network.</span></span>
    
      - <span data-ttu-id="48d82-116">例: telnet sip.contoso.com 443</span><span class="sxs-lookup"><span data-stu-id="48d82-116">Example: telnet sip.contoso.com 443</span></span>
    
      - <span data-ttu-id="48d82-117">展開に応じて、エッジサーバーまたはエッジサーバープールで使用しているポートに対して、前のテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="48d82-117">Perform the preceding test on ports you are using on the Edge Server or Edge Server pool depending on your deployment.</span></span>

  - <span data-ttu-id="48d82-118">正確な外部 DNS 解決を実行する。</span><span class="sxs-lookup"><span data-stu-id="48d82-118">Performing accurate external DNS resolution.</span></span>
    
      - <span data-ttu-id="48d82-119">ネットワークの外部から、エッジまたはエッジプールの外部 FQDN のそれぞれについて ping を行います。</span><span class="sxs-lookup"><span data-stu-id="48d82-119">From outside your network ping each of the external FQDN’s of your Edge or Edge pool.</span></span> <span data-ttu-id="48d82-120">Ping が失敗した場合でも、IP アドレスが表示されます。これは、割り当てられているアドレスと比較できます。</span><span class="sxs-lookup"><span data-stu-id="48d82-120">Even if the ping fails you will see the IP addresses, which you can compare to the ones you have assigned.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

