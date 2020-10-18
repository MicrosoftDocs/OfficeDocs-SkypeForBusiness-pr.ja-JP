---
title: セキュリティ構成ウィザードで IIS のポートを閉じた後にサーバーを再アクティブ化する
description: セキュリティ構成ウィザードで IIS のポートを閉じた後にサーバーを再アクティブ化します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Re-activate server after Security Configuration Wizard closes ports in IIS
ms:assetid: cb8e17cf-f8c1-4099-b63b-c242d656c26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398851(v=OCS.15)
ms:contentKeyID: 48185644
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d824845a7f89c28087a7b5d180a6ed017cb47ade
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579053"
---
# <a name="re-activate-server-after-security-configuration-wizard-closes-ports-in-iis"></a><span data-ttu-id="0fa1a-103">セキュリティ構成ウィザードで IIS のポートを閉じた後にサーバーを再アクティブ化する</span><span class="sxs-lookup"><span data-stu-id="0fa1a-103">Re-activate server after Security Configuration Wizard closes ports in IIS</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0fa1a-104">_**トピックの最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="0fa1a-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="0fa1a-105">一部の Lync Server 2013 の役割では、インターネットインフォメーションサービス (IIS) ポート4443で Web サービスを実行します。</span><span class="sxs-lookup"><span data-stu-id="0fa1a-105">Some Lync Server 2013 roles run Web Services on Internet Information Services (IIS) port 4443.</span></span> <span data-ttu-id="0fa1a-106">Lync Server 展開ウィザードの実行、Bootstrapper.exe、またはを使用し **て、ファイア** ウォールで例外を作成し、ポートを開きます。</span><span class="sxs-lookup"><span data-stu-id="0fa1a-106">Running the Lync Server Deployment Wizard, Bootstrapper.exe, or using the **Enable-CsComputer** cmdlet creates an exception in the firewall and opens the port.</span></span> <span data-ttu-id="0fa1a-107">その後、Windows Server 2008 R2 セキュリティ構成ウィザード (またはその他の強化スクリプト) を実行すると、ポート4443がブロックされ、外部クライアントは Web サービスに接続できなくなります。</span><span class="sxs-lookup"><span data-stu-id="0fa1a-107">If you then run the Windows Server 2008 R2 Security Configuration Wizard (or other hardening scripts), port 4443 will be blocked, and external clients will not be able to contact Web Services.</span></span> <span data-ttu-id="0fa1a-108">ポートを再度開くには、ファイアウォールの例外を直接変更するか、サーバーを再アクティブ化することができます。</span><span class="sxs-lookup"><span data-stu-id="0fa1a-108">To reopen the port you can either modify the firewall exception directly or re-activate the server.</span></span>

<div>

## <a name="to-re-activate-the-server-by-using-the-deployment-wizard"></a><span data-ttu-id="0fa1a-109">展開ウィザードを使用してサーバーを再アクティブ化するには</span><span class="sxs-lookup"><span data-stu-id="0fa1a-109">To re-activate the server by using the Deployment Wizard</span></span>

1.  <span data-ttu-id="0fa1a-110">[Lync Server 展開ウィザード] ページで、[**ステップ 2: Lync Server コンポーネントのセットアップまたは削除**] の横にある [**実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0fa1a-110">On the Lync Server Deployment Wizard page, click **Run** next to **Step 2: Setup or Remove Lync Server Components**.</span></span>

2.  <span data-ttu-id="0fa1a-111">[**Lync Server コンポーネントの設定**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0fa1a-111">On **Setup Lync Server components** page, click **Next**.</span></span>

3.  <span data-ttu-id="0fa1a-112">[**コマンドの実行**] ページで、タスク状態が完了と表示されたら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0fa1a-112">On the **Executing Commands** page, when the task status is shown as completed, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="0fa1a-113">bootstrapper.exe または <STRONG>Enable-CsComputer</STRONG> を使用して、サーバーを再アクティブ化することもできます。</span><span class="sxs-lookup"><span data-stu-id="0fa1a-113">You can also use bootstrapper.exe or <STRONG>Enable-CsComputer</STRONG> to re-activate the server.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

