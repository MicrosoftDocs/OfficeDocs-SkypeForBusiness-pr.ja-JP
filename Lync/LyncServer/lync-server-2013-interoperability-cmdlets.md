---
title: 'Lync Server 2013: 相互運用コマンドレット'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Interoperability cmdlets
ms:assetid: 18444a0b-7b66-4540-a262-775ea10b3b7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204714(v=OCS.15)
ms:contentKeyID: 48183527
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9360a9366c5358c30dbf2cb007af990125dcb15
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832957"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="interoperability-cmdlets-in-lync-server-2013"></a><span data-ttu-id="02e41-102">Lync Server 2013 の相互運用性コマンドレット</span><span class="sxs-lookup"><span data-stu-id="02e41-102">Interoperability cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02e41-103">_**最終更新日:** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="02e41-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="02e41-104">相互運用コマンドレットを使用して、Microsoft Lync Server 2013 と Microsoft Exchange Server 2013 などの他のサーバー製品間のサーバー間認証と承認を構成します。</span><span class="sxs-lookup"><span data-stu-id="02e41-104">The interoperability cmdlets are used to configure server-to-server authentication and authorization between Microsoft Lync Server 2013 and other server products such as Microsoft Exchange Server 2013.</span></span> <span data-ttu-id="02e41-105">サーバー間の認証と承認によって、これらのサーバーがシームレスに exchange を使用してデータを共有することができます。</span><span class="sxs-lookup"><span data-stu-id="02e41-105">Server-to-server authentication and authorization enables these servers to seamless exchange and share data.</span></span>

<div>

## <a name="interoperability-cmdlets"></a><span data-ttu-id="02e41-106">相互運用性のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="02e41-106">Interoperability Cmdlets</span></span>

<span data-ttu-id="02e41-107">Microsoft Lync Server 2013 とその他のサーバー製品の間の相互運用性の構成と管理に直接関連するコマンドレットの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="02e41-107">The following is a list of cmdlets that relate directly to configuring and managing interoperability between Microsoft Lync Server 2013 and other server products:</span></span>

<span data-ttu-id="02e41-108">**相互運用性のコマンドレット**</span><span class="sxs-lookup"><span data-stu-id="02e41-108">**Interoperability Cmdlets**</span></span>

  - <span data-ttu-id="02e41-109">[Get-CsOAuthConfiguration](https://technet.microsoft.com/en-us/library/JJ205155(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="02e41-109">[Get-CsOAuthConfiguration](https://technet.microsoft.com/en-us/library/JJ205155(v=OCS.15))</span></span>

  - <span data-ttu-id="02e41-110">[Set-CsOAuthConfiguration](https://technet.microsoft.com/en-us/library/JJ204841(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="02e41-110">[Set-CsOAuthConfiguration](https://technet.microsoft.com/en-us/library/JJ204841(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="02e41-111">[Get-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ205238(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="02e41-111">[Get-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ205238(v=OCS.15))</span></span>

  - <span data-ttu-id="02e41-112">[New-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ205206(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="02e41-112">[New-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ205206(v=OCS.15))</span></span>

  - <span data-ttu-id="02e41-113">[CsOAuthServer を削除します](https://technet.microsoft.com/en-us/library/JJ205408(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="02e41-113">[Remove-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ205408(v=OCS.15))</span></span>

  - <span data-ttu-id="02e41-114">[Set-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ204896(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="02e41-114">[Set-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ204896(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="02e41-115">[Get-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ205128(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="02e41-115">[Get-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ205128(v=OCS.15))</span></span>

  - <span data-ttu-id="02e41-116">[New-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204628(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="02e41-116">[New-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204628(v=OCS.15))</span></span>

  - <span data-ttu-id="02e41-117">[Remove-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204820(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="02e41-117">[Remove-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204820(v=OCS.15))</span></span>

  - <span data-ttu-id="02e41-118">[Set-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204755(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="02e41-118">[Set-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204755(v=OCS.15))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

