---
title: 'Lync Server 2013: サーバーでのサービスの開始'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Start services on servers
ms:assetid: fa26eaed-0529-4f32-9f3f-f32c4bd4b1c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413059(v=OCS.15)
ms:contentKeyID: 48185912
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4cab7d2e53b981cc971284cfad37f89ca4749590
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208303"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="start-services-on-servers-for-lync-server-2013"></a><span data-ttu-id="8e41a-102">Lync Server 2013 のサーバーでのサービスの開始</span><span class="sxs-lookup"><span data-stu-id="8e41a-102">Start services on servers for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e41a-103">_**トピックの最終更新日:** 2014-09-03_</span><span class="sxs-lookup"><span data-stu-id="8e41a-103">_**Topic Last Modified:** 2014-09-03_</span></span>

<span data-ttu-id="8e41a-104">この手順を正常に完了するには、RTCUniversalServerAdmins グループのメンバーとしてログオンしているか、適切なアクセス許可が委任されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e41a-104">To successfully complete this procedure you should be logged in as a user who is a member of the RTCUniversalServerAdmins group or have the correct permissions delegated.</span></span> <span data-ttu-id="8e41a-105">アクセス許可の委任の詳細については、「 [Lync Server 2013 の委任のセットアップのアクセス許可](lync-server-2013-delegate-setup-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e41a-105">For details about delegating permissions, see the topic [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

<span data-ttu-id="8e41a-106">サーバーにローカル構成ストアをインストールし、Lync Server 2013 コンポーネントをインストールして、フロントエンドサーバーまたはフロントエンドサーバーで証明書を構成すると、サーバー上で Lync Server 2013 サービスを開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e41a-106">After you install the Local Configuration store on your servers, install the Lync Server 2013 components, and configure certificates on a Front End Server or Front End Server, you must start the Lync Server 2013 services on the server.</span></span> <span data-ttu-id="8e41a-107">次の手順を使用して、展開内の各フロントエンドサーバーでサービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="8e41a-107">Use the following procedure to start services on each Front End Server in your deployment.</span></span>

<div>

## <a name="to-start-services-on-a-standard-edition-or-front-end-server"></a><span data-ttu-id="8e41a-108">Standard Edition またはフロントエンドサーバーでサービスを開始するには</span><span class="sxs-lookup"><span data-stu-id="8e41a-108">To start services on a Standard Edition or Front End Server</span></span>

1.  <span data-ttu-id="8e41a-109">Lync Server 展開ウィザードの [ **Lync server 2013** ] ページで、[**ステップ 4: サービスの開始**] の横にある [**実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e41a-109">In the Lync Server Deployment Wizard, on the **Lync Server 2013** page, click **Run** next to **Step 4: Start Services**.</span></span>

2.  <span data-ttu-id="8e41a-110">[**サービスの開始**] ページで、[**次**へ] をクリックして、サーバー上の Lync Server サービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="8e41a-110">On the **Start Services** page, click **Next** to start the Lync Server services on the server.</span></span>

3.  <span data-ttu-id="8e41a-111">すべてのサービスが正常に開始されたら、**[コマンドの実行]** ページで **[終了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e41a-111">On the **Executing Commands** page, after all services have started successfully, click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="8e41a-112">サーバーのサービスを開始するコマンドは、サービスが事実上開始されたことをレポートするベストエフォート型の方法です。</span><span class="sxs-lookup"><span data-stu-id="8e41a-112">The command to start the services on the server is a best effort method to report that the services have in fact started.</span></span> <span data-ttu-id="8e41a-113">サービスの実際の状態を反映していない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="8e41a-113">It might not reflect the actual state of the service.</span></span> <span data-ttu-id="8e41a-114">[<STRONG>サービスの開始</STRONG>] の直後に、ステップ [<STRONG>サービスの状態 (オプション)</STRONG>] で Microsoft 管理コンソール (MMC) を開き、サービスが正常に開始されたことを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8e41a-114">We recommend that you use the step <STRONG>Service Status (Optional)</STRONG> immediately following <STRONG>Start Services</STRONG> to open the Microsoft Management Console (MMC) and confirm that the services have started successfully.</span></span> <span data-ttu-id="8e41a-115">いずれかの Lync Server サービスが開始されていない場合は、MMC でそのサービスを右クリックし、[<STRONG>開始</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e41a-115">If any Lync Server service has not started, you can right-click that service in the MMC, and then click <STRONG>Start</STRONG>.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

