---
title: 外部ユーザーのフェデレーションとリモート アクセスを確認する
description: 外部ユーザーのフェデレーションとリモートアクセスを確認します。
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
ms.openlocfilehash: 1ac36f2e1b6c5ddfd889810ba2a3ab4d82b7ae33
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555073"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="97318-103">外部ユーザーのフェデレーションとリモート アクセスを確認する</span><span class="sxs-lookup"><span data-stu-id="97318-103">Verify federation and remote access for external users</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97318-104">_**トピックの最終更新日:** 2012-09-18_</span><span class="sxs-lookup"><span data-stu-id="97318-104">_**Topic Last Modified:** 2012-09-18_</span></span>

<span data-ttu-id="97318-105">フェデレーションルートを Lync Server 2013 エッジサーバーに移行した後、機能テストを実行して、フェデレーションが期待どおりに動作することを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97318-105">After transitioning the federation route to the Lync Server 2013 Edge Server, you should perform some functional tests to verify that federation performs as expected.</span></span> <span data-ttu-id="97318-106">外部ユーザー アクセスのテストには、次のいずれかまたはすべてなど、組織がサポートしている各種類の外部ユーザーを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="97318-106">Tests for external user access should include each type of external user that your organization supports, including any or all of the following.</span></span>

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="97318-107">外部ユーザーの接続と外部アクセスをテストする</span><span class="sxs-lookup"><span data-stu-id="97318-107">Test Connectivity of External Users and External access</span></span>

  - <span data-ttu-id="97318-108">少なくとも1つのフェデレーションドメイン、Lync Server 2013 上の内部ユーザー、および Lync Server 2010 のユーザー。</span><span class="sxs-lookup"><span data-stu-id="97318-108">Users from at least one federated domain, an internal user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="97318-109">インスタント メッセージング (IM)、プレゼンス、音声ビデオ (A/V)、およびデスクトップ共有をテストします。</span><span class="sxs-lookup"><span data-stu-id="97318-109">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>

  - <span data-ttu-id="97318-110">組織がサポート (およびプロビジョニングが完了) している各パブリック IM サービスプロバイダーのユーザーが、Lync Server 2013 のユーザーおよび Lync Server 2010 のユーザーと通信します。</span><span class="sxs-lookup"><span data-stu-id="97318-110">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Lync Server 2013 and a user on Lync Server 2010.</span></span>

  - <span data-ttu-id="97318-111">匿名ユーザーが会議に参加できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="97318-111">Verify that anonymous users are able to join conferences.</span></span>

  - <span data-ttu-id="97318-112">Lync server 2013 上のユーザーと、lync Server のユーザーに対するリモートユーザーアクセスを使用して、Lync server 2010 でホストされているユーザー (lync Server 2010 の外部から VPN を使用しない)、および lync server 2010 上のユーザー。</span><span class="sxs-lookup"><span data-stu-id="97318-112">A user hosted on Lync Server 2010 using remote user access (logging into Lync Server 2010 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="97318-113">IM、プレゼンス、A/V、およびデスクトップ共有をテストします。</span><span class="sxs-lookup"><span data-stu-id="97318-113">Test IM, presence, A/V, and desktop sharing.</span></span>

  - <span data-ttu-id="97318-114">Lync server 2013 上のユーザーと、lync Server のユーザーに対するリモートユーザーアクセスを使用して、Lync server 2013 でホストされているユーザー (lync Server 2013 の外部から VPN を使用しない)、および lync server 2010 上のユーザー。</span><span class="sxs-lookup"><span data-stu-id="97318-114">A user hosted on Lync Server 2013 using remote user access (logging into Lync Server 2013 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="97318-115">IM、プレゼンス、A/V、およびデスクトップ共有をテストします。</span><span class="sxs-lookup"><span data-stu-id="97318-115">Test IM, presence, A/V, and desktop sharing.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

