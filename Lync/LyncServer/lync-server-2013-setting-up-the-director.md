---
title: 'Lync Server 2013: ディレクターの設定'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up the Director
ms:assetid: 408b76f7-6fdd-4e50-8a3e-e87db12c1394
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425915(v=OCS.15)
ms:contentKeyID: 48183951
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58d0b309e87dddb621d6c3a90b16b6c2e02845df
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764543"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-the-director-in-lync-server-2013"></a><span data-ttu-id="afc42-102">Lync Server 2013 でのディレクターの設定</span><span class="sxs-lookup"><span data-stu-id="afc42-102">Setting up the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="afc42-103">_**最終更新日:** 2014-05-05_</span><span class="sxs-lookup"><span data-stu-id="afc42-103">_**Topic Last Modified:** 2014-05-05_</span></span>

<span data-ttu-id="afc42-104">エッジサーバーを展開して外部ユーザーのアクセスを有効にしている場合は、1つの選択肢としてディレクターを展開することができます。</span><span class="sxs-lookup"><span data-stu-id="afc42-104">If you’re enabling access for external users by deploying Edge Servers, one option is to deploy a Director.</span></span> <span data-ttu-id="afc42-105">ディレクターは、Microsoft Lync Server 2013 を実行しているサーバーで、ユーザー要求を認証しますが、ユーザーアカウントはホームになりません。</span><span class="sxs-lookup"><span data-stu-id="afc42-105">A Director is a server running Microsoft Lync Server 2013 that authenticates user requests, but doesn’t home any user accounts.</span></span> <span data-ttu-id="afc42-106">現時点では、これは必須ではありませんが、認証要求の合理化に役立てるために、パフォーマンスを心配していて、さらに便利です。</span><span class="sxs-lookup"><span data-stu-id="afc42-106">Now, this isn’t a requirement, but it is very helpful if you’re worried about performance and want to help streamline authentication requests.</span></span> <span data-ttu-id="afc42-107">組織にとってこの方法が適していると判断された場合は、ディレクターまたはディレクタープールをセットアップする手順は、Enterprise Edition のフロントエンドプールまたは Standard Edition サーバーの設定に似ています。</span><span class="sxs-lookup"><span data-stu-id="afc42-107">If you decide this is a good idea for your organization, the steps to set up a Director or a Director pool are similar to setting up either an Enterprise Edition Front End pool or Standard Edition server.</span></span> <span data-ttu-id="afc42-108">トポロジビルダーでディレクターを定義した後で、このセクションの手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="afc42-108">After you’ve defined your Director(s) in Topology Builder, you’ll need to perform the steps in this section.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="afc42-109">このセクション中</span><span class="sxs-lookup"><span data-stu-id="afc42-109">In This Section</span></span>

  - [<span data-ttu-id="afc42-110">Lync Server 2013 でのローカル構成ストアのインストール</span><span class="sxs-lookup"><span data-stu-id="afc42-110">Install the Local Configuration store in Lync Server 2013</span></span>](lync-server-2013-install-the-local-configuration-store.md)

  - [<span data-ttu-id="afc42-111">ディレクターでの Lync Server 2013 のインストール</span><span class="sxs-lookup"><span data-stu-id="afc42-111">Install Lync Server 2013 on the Director</span></span>](lync-server-2013-install-lync-server-on-the-director.md)

  - [<span data-ttu-id="afc42-112">Lync Server 2013 でのディレクターの証明書の構成</span><span class="sxs-lookup"><span data-stu-id="afc42-112">Configure certificates for the Director in Lync Server 2013</span></span>](lync-server-2013-configure-certificates-for-the-director.md)

  - [<span data-ttu-id="afc42-113">Lync Server 2013 でのディレクターのサービスの開始</span><span class="sxs-lookup"><span data-stu-id="afc42-113">Start services on the Director in Lync Server 2013</span></span>](lync-server-2013-start-services-on-the-director.md)

  - [<span data-ttu-id="afc42-114">Lync Server 2013 でのディレクターのテスト</span><span class="sxs-lookup"><span data-stu-id="afc42-114">Test the Director in Lync Server 2013</span></span>](lync-server-2013-test-the-director.md)

  - [<span data-ttu-id="afc42-115">Lync Server 2013 でのディレクターを使った自動クライアント サインインの構成</span><span class="sxs-lookup"><span data-stu-id="afc42-115">Configure Automatic Client Sign-In to use the Director in Lync Server 2013</span></span>](lync-server-2013-configure-automatic-client-sign-in-to-use-the-director.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

