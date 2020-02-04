---
title: 'Lync Server 2013: Enterprise Edition のメンバーサーバーを復元する'
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
ms.openlocfilehash: e870b68d1252ea5a203b3c334299fb65b6a56512
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733217"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-an-enterprise-edition-member-server-in-lync-server-2013"></a><span data-ttu-id="ea6d5-102">Lync Server 2013 で Enterprise Edition メンバーサーバーを復元する</span><span class="sxs-lookup"><span data-stu-id="ea6d5-102">Restoring an Enterprise Edition member server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea6d5-103">_**最終更新日:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="ea6d5-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="ea6d5-104">次のいずれかのサーバーの役割を実行しているサーバーで障害が発生した場合は、このトピックの手順に従ってサーバーを復元します。</span><span class="sxs-lookup"><span data-stu-id="ea6d5-104">If a server running one of the following server roles fails, follow the procedure in this topic to restore the server.</span></span> <span data-ttu-id="ea6d5-105">複数のサーバーが個別に失敗した場合は、各サーバーの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="ea6d5-105">If multiple servers fail independently, follow the procedure for each server.</span></span>

  - <span data-ttu-id="ea6d5-106">フロントエンド サーバー</span><span class="sxs-lookup"><span data-stu-id="ea6d5-106">Front End Server</span></span>

  - <span data-ttu-id="ea6d5-107">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="ea6d5-107">Mediation Server</span></span>

  - <span data-ttu-id="ea6d5-108">ディレクター</span><span class="sxs-lookup"><span data-stu-id="ea6d5-108">Director</span></span>

  - <span data-ttu-id="ea6d5-109">常設チャット サーバー</span><span class="sxs-lookup"><span data-stu-id="ea6d5-109">Persistent Chat Server</span></span>

  - <span data-ttu-id="ea6d5-110">エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="ea6d5-110">Edge Server</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="ea6d5-111">復元を開始する前に、システムのイメージコピーを取得することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ea6d5-111">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="ea6d5-112">復元中に問題が発生した場合に備えて、この画像をロールバックポイントとして使うことができます。</span><span class="sxs-lookup"><span data-stu-id="ea6d5-112">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="ea6d5-113">オペレーティングシステムと SQL Server をインストールした後に画像のコピーを取得し、証明書を復元または reenroll することができます。</span><span class="sxs-lookup"><span data-stu-id="ea6d5-113">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-a-member-server"></a><span data-ttu-id="ea6d5-114">メンバーサーバーを復元するには</span><span class="sxs-lookup"><span data-stu-id="ea6d5-114">To restore a member server</span></span>

1.  <span data-ttu-id="ea6d5-115">障害が発生したサーバーと同じ完全修飾ドメイン名 (FQDN) を持つクリーンまたは新しいサーバーを起動し、オペレーティングシステムをインストールして、証明書を復元または reenroll します。</span><span class="sxs-lookup"><span data-stu-id="ea6d5-115">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed server, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ea6d5-116">組織のサーバー展開手順に従って、この手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ea6d5-116">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="ea6d5-117">RTCUniversalServerAdmins グループのメンバーであるユーザーアカウントから、復元しているサーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="ea6d5-117">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="ea6d5-118">Lync Server のインストールフォルダーまたはメディアを参照し、セットアップ\\\\Amd64\\Setup.exe で [lync server 展開ウィザード] を起動します。</span><span class="sxs-lookup"><span data-stu-id="ea6d5-118">Browse to the Lync Server installation folder or media, and start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span>

4.  <span data-ttu-id="ea6d5-119">展開ウィザードの指示に従って、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ea6d5-119">Follow the Deployment Wizard to do the following:</span></span>
    
    1.  <span data-ttu-id="ea6d5-120">**手順 1: ローカル構成ストアをインストール**して、ローカル構成ファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="ea6d5-120">Run **Step 1: Install Local Configuration Store** to install the local configuration files.</span></span>
    
    2.  <span data-ttu-id="ea6d5-121">**手順 2: lync server のコンポーネントをセットアップまたは削除**して lync server server の役割をインストールする</span><span class="sxs-lookup"><span data-stu-id="ea6d5-121">Run **Step 2: Setup or Remove Lync Server Components** to install the Lync Server server role.</span></span>
    
    3.  <span data-ttu-id="ea6d5-122">手順 3: 証明書を割り当てるために**証明書を要求、インストール、または割り当て**ます。</span><span class="sxs-lookup"><span data-stu-id="ea6d5-122">Run **Step 3: Request, Install or Assign Certificates** to assign the certificates.</span></span>
    
    4.  <span data-ttu-id="ea6d5-123">**手順 4: サービスを開始**して、サーバー上のサービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="ea6d5-123">Run **Step 4: Start Services** to start services on the server.</span></span>
    
    <span data-ttu-id="ea6d5-124">展開ウィザードの実行の詳細については、復元するサーバーの役割の展開ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea6d5-124">For details about running the Deployment Wizard, see the Deployment documentation for the server role that you are restoring.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

