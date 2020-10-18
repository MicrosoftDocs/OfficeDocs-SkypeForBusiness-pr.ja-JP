---
title: 'Lync Server 2013: Enterprise Edition メンバーサーバーの復元'
description: 'Lync Server 2013: Enterprise Edition メンバーサーバーの復元。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring an Enterprise Edition member server
ms:assetid: d960b19c-2104-4719-b736-0d940f254d42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202191(v=OCS.15)
ms:contentKeyID: 51541523
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f9838f030205d92988e185798d982f835122c9f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576053"
---
# <a name="restoring-an-enterprise-edition-member-server-in-lync-server-2013"></a><span data-ttu-id="dc83f-103">Lync Server 2013 での Enterprise Edition メンバーサーバーの復元</span><span class="sxs-lookup"><span data-stu-id="dc83f-103">Restoring an Enterprise Edition member server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc83f-104">_**トピックの最終更新日:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="dc83f-104">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="dc83f-105">次のいずれかのサーバーの役割を実行しているサーバーで障害が発生した場合は、このトピックの手順に従ってサーバーを復元します。</span><span class="sxs-lookup"><span data-stu-id="dc83f-105">If a server running one of the following server roles fails, follow the procedure in this topic to restore the server.</span></span> <span data-ttu-id="dc83f-106">複数のサーバーで個別に障害が発生した場合は、各サーバーで手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="dc83f-106">If multiple servers fail independently, follow the procedure for each server.</span></span>

  - <span data-ttu-id="dc83f-107">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="dc83f-107">Front End Server</span></span>

  - <span data-ttu-id="dc83f-108">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="dc83f-108">Mediation Server</span></span>

  - <span data-ttu-id="dc83f-109">ディレクター</span><span class="sxs-lookup"><span data-stu-id="dc83f-109">Director</span></span>

  - <span data-ttu-id="dc83f-110">常設チャット サーバー</span><span class="sxs-lookup"><span data-stu-id="dc83f-110">Persistent Chat Server</span></span>

  - <span data-ttu-id="dc83f-111">エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="dc83f-111">Edge Server</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="dc83f-112">復元を開始する前に、システムのイメージコピーを取得することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dc83f-112">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="dc83f-113">復元中に問題が発生した場合に備えて、このイメージをロールバックポイントとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="dc83f-113">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="dc83f-114">オペレーティングシステムと SQL Server をインストールした後、画像コピーを取得し、証明書を復元または reenroll することができます。</span><span class="sxs-lookup"><span data-stu-id="dc83f-114">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-a-member-server"></a><span data-ttu-id="dc83f-115">メンバー サーバーを復元するには</span><span class="sxs-lookup"><span data-stu-id="dc83f-115">To restore a member server</span></span>

1.  <span data-ttu-id="dc83f-116">障害が発生したサーバーと同じ完全修飾ドメイン名 (FQDN) を持つクリーンサーバーまたは新しいサーバーを起動し、オペレーティングシステムをインストールしてから、証明書を復元または reenroll します。</span><span class="sxs-lookup"><span data-stu-id="dc83f-116">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed server, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dc83f-117">組織で定めるサーバーの展開手順に従って、この手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="dc83f-117">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="dc83f-118">RTCUniversalServerAdmins グループのメンバーであるユーザーアカウントから、復元するサーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="dc83f-118">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="dc83f-119">Lync Server インストールフォルダーまたはメディアを参照し、セットアップ amd64Setup.exe にある Lync Server 展開ウィザードを起動し \\ \\ \\ ます。</span><span class="sxs-lookup"><span data-stu-id="dc83f-119">Browse to the Lync Server installation folder or media, and start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span>

4.  <span data-ttu-id="dc83f-120">展開ウィザードに従って、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="dc83f-120">Follow the Deployment Wizard to do the following:</span></span>
    
    1.  <span data-ttu-id="dc83f-121">[**ステップ 1: ローカル構成ストアのインストール**] を実行して、ローカル構成ファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="dc83f-121">Run **Step 1: Install Local Configuration Store** to install the local configuration files.</span></span>
    
    2.  <span data-ttu-id="dc83f-122">[ **ステップ 2: lync Server コンポーネントのセットアップまたは削除** を実行して、lync server のサーバーの役割をインストールする」を実行します。</span><span class="sxs-lookup"><span data-stu-id="dc83f-122">Run **Step 2: Setup or Remove Lync Server Components** to install the Lync Server server role.</span></span>
    
    3.  <span data-ttu-id="dc83f-123">[**ステップ 3: 証明書の要求、インストール、または割り当て**] を実行して、証明書を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="dc83f-123">Run **Step 3: Request, Install or Assign Certificates** to assign the certificates.</span></span>
    
    4.  <span data-ttu-id="dc83f-124">[**ステップ 4: サービスの開始**] を実行して、サーバー上でサービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="dc83f-124">Run **Step 4: Start Services** to start services on the server.</span></span>
    
    <span data-ttu-id="dc83f-125">展開ウィザードの実行の詳細については、「展開」のドキュメントの「復元」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc83f-125">For details about running the Deployment Wizard, see the Deployment documentation for the server role that you are restoring.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

