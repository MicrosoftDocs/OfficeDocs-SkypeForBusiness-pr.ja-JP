---
title: 外部ユーザーのフェデレーションとリモート アクセスを確認する
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify federation and remote access for external users
ms:assetid: a383fefb-c428-4462-93fd-15ba540fa867
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688163(v=OCS.15)
ms:contentKeyID: 49733768
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c5821cd8710b8493a29684d1b7ee695f5bf5c747
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508384"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="a9ada-102">外部ユーザーのフェデレーションとリモート アクセスを確認する</span><span class="sxs-lookup"><span data-stu-id="a9ada-102">Verify federation and remote access for external users</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9ada-103">_**トピックの最終更新日:** 2012-09-18_</span><span class="sxs-lookup"><span data-stu-id="a9ada-103">_**Topic Last Modified:** 2012-09-18_</span></span>

<span data-ttu-id="a9ada-104">フェデレーションルートを Lync Server 2013 エッジサーバーに移行した後、機能テストを実行して、フェデレーションが期待どおりに動作することを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9ada-104">After transitioning the federation route to the Lync Server 2013 Edge Server, you should perform some functional tests to verify that federation performs as expected.</span></span> <span data-ttu-id="a9ada-105">外部ユーザー アクセスのテストには、次のいずれかまたはすべてなど、組織がサポートしている各種類の外部ユーザーを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9ada-105">Tests for external user access should include each type of external user that your organization supports, including any or all of the following.</span></span>

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="a9ada-106">外部ユーザーの接続と外部アクセスをテストする</span><span class="sxs-lookup"><span data-stu-id="a9ada-106">Test Connectivity of External Users and External access</span></span>

  - <span data-ttu-id="a9ada-107">少なくとも1つのフェデレーションドメイン、Lync Server 2013 上の内部ユーザー、および Lync Server 2010 のユーザー。</span><span class="sxs-lookup"><span data-stu-id="a9ada-107">Users from at least one federated domain, an internal user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="a9ada-108">インスタント メッセージング (IM)、プレゼンス、音声ビデオ (A/V)、およびデスクトップ共有をテストします。</span><span class="sxs-lookup"><span data-stu-id="a9ada-108">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>

  - <span data-ttu-id="a9ada-109">組織がサポート (およびプロビジョニングが完了) している各パブリック IM サービスプロバイダーのユーザーが、Lync Server 2013 のユーザーおよび Lync Server 2010 のユーザーと通信します。</span><span class="sxs-lookup"><span data-stu-id="a9ada-109">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Lync Server 2013 and a user on Lync Server 2010.</span></span>

  - <span data-ttu-id="a9ada-110">匿名ユーザーが会議に参加できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a9ada-110">Verify that anonymous users are able to join conferences.</span></span>

  - <span data-ttu-id="a9ada-111">Lync server 2013 上のユーザーと、lync Server のユーザーに対するリモートユーザーアクセスを使用して、Lync server 2010 でホストされているユーザー (lync Server 2010 の外部から VPN を使用しない)、および lync server 2010 上のユーザー。</span><span class="sxs-lookup"><span data-stu-id="a9ada-111">A user hosted on Lync Server 2010 using remote user access (logging into Lync Server 2010 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="a9ada-112">IM、プレゼンス、A/V、およびデスクトップ共有をテストします。</span><span class="sxs-lookup"><span data-stu-id="a9ada-112">Test IM, presence, A/V, and desktop sharing.</span></span>

  - <span data-ttu-id="a9ada-113">Lync server 2013 上のユーザーと、lync Server のユーザーに対するリモートユーザーアクセスを使用して、Lync server 2013 でホストされているユーザー (lync Server 2013 の外部から VPN を使用しない)、および lync server 2010 上のユーザー。</span><span class="sxs-lookup"><span data-stu-id="a9ada-113">A user hosted on Lync Server 2013 using remote user access (logging into Lync Server 2013 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="a9ada-114">IM、プレゼンス、A/V、およびデスクトップ共有をテストします。</span><span class="sxs-lookup"><span data-stu-id="a9ada-114">Test IM, presence, A/V, and desktop sharing.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

