---
title: 'Lync Server 2013: Lync Online からオンプレミスの Lync へのユーザーの移行を開始する前の最初の手順'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: First steps before you start migrating users from Lync Online to Lync on-premises
ms:assetid: 98245b04-ded4-4186-8da3-ba1c554b5c39
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689118(v=OCS.15)
ms:contentKeyID: 62258123
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e278fcb1e63c1db1334e625765d65d5d556e934
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833142"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="first-steps-before-you-start-migrating-users-from-lync-online-to-lync-on-premises-in-lync-server-2013"></a><span data-ttu-id="917cc-102">Lync Online から内部設置型 lync へのユーザーの移行を開始する前の最初の手順2013</span><span class="sxs-lookup"><span data-stu-id="917cc-102">First steps before you start migrating users from Lync Online to Lync on-premises in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="917cc-103">_**最終更新日:** 2014-05-08_</span><span class="sxs-lookup"><span data-stu-id="917cc-103">_**Topic Last Modified:** 2014-05-08_</span></span>

<span data-ttu-id="917cc-104">Lync Online ユーザーをオンプレミス環境に移行する前に、次のすべての条件が満たされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="917cc-104">Before you start moving Lync Online users to your on-premises environment, check that all of the following are true:</span></span>

  - <span data-ttu-id="917cc-105">Lync Server のオンプレミス環境を完全に展開して検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="917cc-105">Your Lync Server on-premises environment must be fully deployed and validated.</span></span> <span data-ttu-id="917cc-106">詳細については、「 [Lync Server 2013 の展開](lync-server-2013-deploying-lync-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="917cc-106">For more information, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md).</span></span>

  - <span data-ttu-id="917cc-107">Lync Online テナントがリモート PowerShell アクセス用に構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="917cc-107">Your Lync Online tenant must be configured for remote PowerShell Access.</span></span>
    
    <span data-ttu-id="917cc-108">これを行うには、まず、Windows PowerShell 用の Lync Online モジュールをインストールします。 [http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911)これは次の場所で入手できます。</span><span class="sxs-lookup"><span data-stu-id="917cc-108">To do this, first install the Lync Online module for Windows PowerShell, which you can get here: [http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911).</span></span>
    
    <span data-ttu-id="917cc-109">モジュールをインストールした後、Lync Server 管理シェルで次のコマンドレットを入力して、リモートセッションを確立できます。</span><span class="sxs-lookup"><span data-stu-id="917cc-109">After you install the module, you can establish a remote session by typing the following cmdlets in the Lync Server Management Shell:</span></span>
    
       ```
        Import-Module LyncOnlineConnector
       ```  
    
       ```
        $cred = Get-Credential
       ``` 
    
       ```
        $CSSession = New-CsOnlineSession -Credential $cred
       ```
    
       ```
        Import-PSSession $CSSession -AllowClobber
       ```
    
    <span data-ttu-id="917cc-110">Lync Online とのリモート PowerShell セッションを確立する方法の詳細については、「 [Windows PowerShell を使用した Lync online への接続](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="917cc-110">For more information about how to establish a remote PowerShell session with Lync Online, see [Connecting to Lync Online by using Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  
    <span data-ttu-id="917cc-111">Lync Online PowerShell モジュールの使用方法の詳細については、「 [Windows PowerShell を使用して Lync online を管理する](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="917cc-111">For more information about using the Lync Online PowerShell module, see [Using Windows PowerShell to manage Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

  - <span data-ttu-id="917cc-112">Lync Online は共有 SIP アドレススペース用に構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="917cc-112">Your Lync Online must be configured for Shared SIP Address Space.</span></span> <span data-ttu-id="917cc-113">これを行うには、まず、Lync Online とのリモート Powershell セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="917cc-113">To do this, first start a remote Powershell session with Lync Online.</span></span> <span data-ttu-id="917cc-114">続いて、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="917cc-114">Then run the following cmdlet:</span></span>
    
        Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True

<span data-ttu-id="917cc-115">これらの手順を完了したら、lync [Online ユーザーをオンプレミスの Lync Server 2013 で移行](lync-server-2013-migrating-lync-online-users-to-lync-on-premises.md)できます。</span><span class="sxs-lookup"><span data-stu-id="917cc-115">After you’ve finished these steps, you can move on to [Migrating Lync Online users to Lync on-premises in Lync Server 2013](lync-server-2013-migrating-lync-online-users-to-lync-on-premises.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

