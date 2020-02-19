---
title: 'Lync Server 2013: Windows PowerShell 3.0 のインストール'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Windows PowerShell 3.0
ms:assetid: d87bf21e-0a43-41cb-8fdc-626cedec8538
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205328(v=OCS.15)
ms:contentKeyID: 48185621
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce694fe34451d6465f1fff31119ecf40c13e82d7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42118630"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-windows-powershell-30-for-lync-server-2013"></a><span data-ttu-id="14266-102">Lync Server 2013 用の Windows PowerShell 3.0 のインストール</span><span class="sxs-lookup"><span data-stu-id="14266-102">Installing Windows PowerShell 3.0 for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14266-103">_**トピックの最終更新日:** 2014-06-27_</span><span class="sxs-lookup"><span data-stu-id="14266-103">_**Topic Last Modified:** 2014-06-27_</span></span>

<span data-ttu-id="14266-104">Lync Server 2013 を正常に展開するには、Lync Server トポロジの一部である各コンピューターで Windows PowerShell 3.0 が必要になります。</span><span class="sxs-lookup"><span data-stu-id="14266-104">To deploy Lync Server 2013 successfully, you’ll need Windows PowerShell 3.0 on each computer that’s part of your Lync Server topology.</span></span>

<span data-ttu-id="14266-105">Windows Server 2012 または Windows Server 2012 R2 を実行しているシステムでは、ここでは何もする必要はありません。また、次の展開ステージに進むことができます。これは、これらのオペレーティングシステムに PowerShell 3.0 が含まれているためです。</span><span class="sxs-lookup"><span data-stu-id="14266-105">Now, for systems running Windows Server 2012 or Windows Server 2012 R2, you don’t need to do anything here, and can go ahead to the next stage of deployment, because PowerShell 3.0 is included with those operating systems.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="14266-106">ただし、Windows Server 2008 R2 SP1 を実行しているシステムでは、Lync Server 2013 をインストールする前に、前提条件として PowerShell 3.0 をインストールする必要があります。そうしないと機能しないことがあります。</span><span class="sxs-lookup"><span data-stu-id="14266-106">But for systems running Windows Server 2008 R2 SP1, you’ll need to install PowerShell 3.0 as a prerequisite before you install Lync Server 2013, or things won’t work.</span></span> <span data-ttu-id="14266-107">PowerShell 3.0 をインストールするには、「 <A href="https://go.microsoft.com/fwlink/p/?linkid=329800">Windows Management Framework 3.0</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14266-107">To install PowerShell 3.0, see <A href="https://go.microsoft.com/fwlink/p/?linkid=329800">Windows Management Framework 3.0</A>.</span></span> <span data-ttu-id="14266-108">これは、PowerShell 3.0 ダウンロードページへの直接リンクであり、正常なインストールに関連する情報も含まれています。</span><span class="sxs-lookup"><span data-stu-id="14266-108">This is a direct link to the PowerShell 3.0 download page, along with information relating to installing it successfully.</span></span>



</div>

<span data-ttu-id="14266-109">インストールが完了した後、または Lync Server の展開を続行する前に確認しておく必要がある場合は、次のような場合には、PowerShell 3.0 がサーバーにあることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="14266-109">Once you’ve done the install, or if you just want to check and be sure before continuing with the Lync Server deployment, confirming that PowerShell 3.0 is on a server is pretty straightforward if you do this:</span></span>

1.  <span data-ttu-id="14266-110">確認するサーバーで、[**スタート**]、[すべての**プログラム**]、[**アクセサリ**]、[ **windows powershell**]、[ **windows powershell**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="14266-110">On the server you want to check, choose **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, and then click **Windows PowerShell**.</span></span>

2.  <span data-ttu-id="14266-111">Windows PowerShell コンソールで、コマンドプロンプトに次のコマンドを入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="14266-111">In the Windows PowerShell console, type the following command at the command prompt, and then press ENTER:</span></span>
    
        Get-Host | Select-Object Version

3.  <span data-ttu-id="14266-112">Windows PowerShell 3.0 がインストールされている場合は、次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="14266-112">If Windows PowerShell 3.0 is installed you’ll see output that looks like this:</span></span>
    
        Version
        -------
        3.0

</div>

<span> </span>

</div>

</div>

</div>

