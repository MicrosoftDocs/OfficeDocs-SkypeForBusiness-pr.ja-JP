---
title: セキュリティ構成ウィザードで IIS のポートを閉じた後にサーバーを再アクティブ化する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Re-activate server after Security Configuration Wizard closes ports in IIS
ms:assetid: cb8e17cf-f8c1-4099-b63b-c242d656c26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398851(v=OCS.15)
ms:contentKeyID: 48185644
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c939996c10c85141d3c3751ce84b0cf642007b9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823610"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="re-activate-server-after-security-configuration-wizard-closes-ports-in-iis"></a><span data-ttu-id="f4308-102">セキュリティ構成ウィザードで IIS のポートを閉じた後にサーバーを再アクティブ化する</span><span class="sxs-lookup"><span data-stu-id="f4308-102">Re-activate server after Security Configuration Wizard closes ports in IIS</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4308-103">_**最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="f4308-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="f4308-104">一部の Lync Server 2013 ロールでは、インターネットインフォメーションサービス (IIS) ポート4443で Web サービスが実行されます。</span><span class="sxs-lookup"><span data-stu-id="f4308-104">Some Lync Server 2013 roles run Web Services on Internet Information Services (IIS) port 4443.</span></span> <span data-ttu-id="f4308-105">Lync Server 展開ウィザード、ブートストラップを実行するか、または**CsComputer**コマンドレットを使用して、ファイアウォールで例外を作成し、ポートを開きます。</span><span class="sxs-lookup"><span data-stu-id="f4308-105">Running the Lync Server Deployment Wizard, Bootstrapper.exe, or using the **Enable-CsComputer** cmdlet creates an exception in the firewall and opens the port.</span></span> <span data-ttu-id="f4308-106">その後、Windows Server 2008 R2 セキュリティ構成ウィザード (またはその他の強化スクリプト) を実行すると、ポート4443はブロックされ、外部クライアントは Web サービスに接続できなくなります。</span><span class="sxs-lookup"><span data-stu-id="f4308-106">If you then run the Windows Server 2008 R2 Security Configuration Wizard (or other hardening scripts), port 4443 will be blocked, and external clients will not be able to contact Web Services.</span></span> <span data-ttu-id="f4308-107">ポートをもう一度開くには、ファイアウォールの例外を直接変更するか、サーバーを再アクティブ化することができます。</span><span class="sxs-lookup"><span data-stu-id="f4308-107">To reopen the port you can either modify the firewall exception directly or re-activate the server.</span></span>

<div>

## <a name="to-re-activate-the-server-by-using-the-deployment-wizard"></a><span data-ttu-id="f4308-108">展開ウィザードを使用してサーバーを再アクティブ化するには</span><span class="sxs-lookup"><span data-stu-id="f4308-108">To re-activate the server by using the Deployment Wizard</span></span>

1.  <span data-ttu-id="f4308-109">Lync Server の展開ウィザードのページで、[**手順 2: Lync サーバーコンポーネントをセットアップまたは削除**する] の横にある [**実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4308-109">On the Lync Server Deployment Wizard page, click **Run** next to **Step 2: Setup or Remove Lync Server Components**.</span></span>

2.  <span data-ttu-id="f4308-110">[ **Lync Server コンポーネントのセットアップ**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4308-110">On **Setup Lync Server components** page, click **Next**.</span></span>

3.  <span data-ttu-id="f4308-111">[**コマンドの実行**] ページで、タスクの状態が [完了] と表示されたら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4308-111">On the **Executing Commands** page, when the task status is shown as completed, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="f4308-112">また、client.exe を使用してサーバー <STRONG></STRONG>を再アクティブ化することもできます。</span><span class="sxs-lookup"><span data-stu-id="f4308-112">You can also use bootstrapper.exe or <STRONG>Enable-CsComputer</STRONG> to re-activate the server.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

