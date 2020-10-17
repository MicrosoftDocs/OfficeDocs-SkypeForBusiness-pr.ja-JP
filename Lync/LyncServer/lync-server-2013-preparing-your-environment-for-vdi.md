---
title: 'Lync Server 2013: VDI のための環境の準備'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing your environment for VDI
ms:assetid: a3ec2e13-1a73-4b1c-a54a-8db7d4cd50f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205154(v=OCS.15)
ms:contentKeyID: 48185052
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bf8480a0905184d7259a9f0c3aa79725453f59d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506804"
---
# <a name="preparing-your-lync-server-2013-environment-for-vdi"></a><span data-ttu-id="28fc6-102">VDI の Lync Server 2013 環境の準備</span><span class="sxs-lookup"><span data-stu-id="28fc6-102">Preparing your Lync Server 2013 environment for VDI</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28fc6-103">_**トピックの最終更新日:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="28fc6-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="28fc6-104">Lync VDI プラグインの環境を準備するには、管理者は次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="28fc6-104">To prepare the environment for the Lync VDI plug-in, the administrator must perform the following steps.</span></span>

1.  <span data-ttu-id="28fc6-105">Lync Server 2013 では、すべての VDI ユーザーに対して対して enablemediaredirection が TRUE に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="28fc6-105">In Lync Server 2013, ensure that EnableMediaRedirection is set to TRUE for all VDI users.</span></span> <span data-ttu-id="28fc6-106">詳細については、「 [新しい-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) コマンドレット」および「 [Set-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) コマンドレット」のヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="28fc6-106">For details, see the Help topics for the [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) cmdlet and the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) cmdlet.</span></span>

2.  <span data-ttu-id="28fc6-107">データセンターコンピューターで、Lync 2013 クライアントをすべての仮想マシンにインストールします。</span><span class="sxs-lookup"><span data-stu-id="28fc6-107">On the data center computer, install the Lync 2013 client on all virtual machines.</span></span>

3.  <span data-ttu-id="28fc6-108">ローカルコンピューターで、Lync VDI プラグインをインストールします。</span><span class="sxs-lookup"><span data-stu-id="28fc6-108">On the local computers, install the Lync VDI plug-in.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

