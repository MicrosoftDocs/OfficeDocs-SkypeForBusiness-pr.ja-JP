---
title: 集中ログサービスの構成設定の管理
description: 集中ログサービスの構成設定を管理する。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing the Centralized Logging Service configuration settings
ms:assetid: f455c3aa-0061-413d-bdfb-a3e78f82723d
ms:mtpsurl: https://technet.microsoft.com/library/JJ721938(v=OCS.15)
ms:contentKeyID: 49733875
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e25294e096b8368aa06a11e4ad851fe5d1a84c0f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572603"
---
# <a name="managing-the-centralized-logging-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="b3d83-103">Lync Server 2013 での集中ログサービスの構成設定の管理</span><span class="sxs-lookup"><span data-stu-id="b3d83-103">Managing the Centralized Logging Service configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3d83-104">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="b3d83-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="b3d83-105">集中ログサービスは、個々のコンピューターの集中ログサービスエージェント (CLSController) にコマンドを送信するために、集中ログサービスコントローラー (CLSController) によって作成および使用される設定とパラメーターによって制御および構成されます。</span><span class="sxs-lookup"><span data-stu-id="b3d83-105">The Centralized Logging Service is controlled and configured by settings and parameters that are created and used by the Centralized Logging Service Controller (CLSController) to send commands to the individual computer’s Centralized Logging Service Agent (CLSAgent).</span></span> <span data-ttu-id="b3d83-106">このエージェントは送信されたコマンドを処理し、シナリオ、プロバイダー、ログ サイズ、トレース期間、およびフラグの構成を使用して、提供された構成情報に従うトレース ログの収集を開始します。</span><span class="sxs-lookup"><span data-stu-id="b3d83-106">The agent processes the commands that are sent to it and (in the case of a Start command) uses the configuration of the scenarios, providers, log size, trace duration, and flags to begin collecting trace logs according to the configuration information provided.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="b3d83-107">集中ログサービス用に一覧表示されているすべての Windows PowerShell コマンドレットは、Lync Server 2013 社内展開で使用することを目的としたものではありません。</span><span class="sxs-lookup"><span data-stu-id="b3d83-107">Not all Windows PowerShell cmdlets listed for the Centralized Logging Service are intended for use with Lync Server 2013 on-premises deployments.</span></span> <span data-ttu-id="b3d83-108">次のコマンドレットは、稼働しているように見える場合がありますが、Lync Server 2013 の社内展開で機能するようには設計されていません。</span><span class="sxs-lookup"><span data-stu-id="b3d83-108">Although they may appear to work, the following cmdlets are not designed to function with Lync Server 2013 on-premises deployments:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="b3d83-109"><STRONG>CsClsRegion コマンドレット:</STRONG> <A href="https://technet.microsoft.com/library/JJ204879(v=OCS.15)">Get-CsClsRegion</A>、<A href="https://technet.microsoft.com/library/JJ204746(v=OCS.15)">Set-CsClsRegion</A>、<A href="https://technet.microsoft.com/library/JJ204658(v=OCS.15)">New-CsClsRegion</A>、および <A href="https://technet.microsoft.com/library/JJ204971(v=OCS.15)">Remove-CsClsRegion</A>。</span><span class="sxs-lookup"><span data-stu-id="b3d83-109"><STRONG>CsClsRegion cmdlets:</STRONG> <A href="https://technet.microsoft.com/library/JJ204879(v=OCS.15)">Get-CsClsRegion</A>, <A href="https://technet.microsoft.com/library/JJ204746(v=OCS.15)">Set-CsClsRegion</A>, <A href="https://technet.microsoft.com/library/JJ204658(v=OCS.15)">New-CsClsRegion</A>, and <A href="https://technet.microsoft.com/library/JJ204971(v=OCS.15)">Remove-CsClsRegion</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="b3d83-110"><STRONG>CsClsSearchTerm コマンドレット:</STRONG> <A href="https://technet.microsoft.com/library/JJ205061(v=OCS.15)">Get-CsClsSearchTerm</A> および <A href="https://technet.microsoft.com/library/JJ204911(v=OCS.15)">Set-CsClsSearchTerm</A>。</span><span class="sxs-lookup"><span data-stu-id="b3d83-110"><STRONG>CsClsSearchTerm cmdlets:</STRONG> <A href="https://technet.microsoft.com/library/JJ205061(v=OCS.15)">Get-CsClsSearchTerm</A> and <A href="https://technet.microsoft.com/library/JJ204911(v=OCS.15)">Set-CsClsSearchTerm</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="b3d83-111"><STRONG>CsClsSecurityGroup コマンドレット:</STRONG> <A href="https://technet.microsoft.com/library/JJ205285(v=OCS.15)">Get-CsClsSecurityGroup</A>、<A href="https://technet.microsoft.com/library/JJ204700(v=OCS.15)">Set-CsClsSecurityGroup</A>、<A href="https://technet.microsoft.com/library/JJ205359(v=OCS.15)">New-CsClsSecurityGroup</A>、および <A href="https://technet.microsoft.com/library/JJ204958(v=OCS.15)">Remove-CsClsSecurityGroup</A>。</span><span class="sxs-lookup"><span data-stu-id="b3d83-111"><STRONG>CsClsSecurityGroup cmdlets:</STRONG> <A href="https://technet.microsoft.com/library/JJ205285(v=OCS.15)">Get-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/library/JJ204700(v=OCS.15)">Set-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/library/JJ205359(v=OCS.15)">New-CsClsSecurityGroup</A>, and <A href="https://technet.microsoft.com/library/JJ204958(v=OCS.15)">Remove-CsClsSecurityGroup</A>.</span></span></P></LI></UL><span data-ttu-id="b3d83-112">これらのコマンドレットで定義されている設定は、悪影響を及ぼすことはありませんが、Microsoft 365 で使用するように設計されており、オンプレミスの展開で予期した結果をもたらすことはありません。</span><span class="sxs-lookup"><span data-stu-id="b3d83-112">The settings defined in these cmdlets will not hinder or cause any adverse behavior, but they are designed for use with Microsoft 365 and will not yield the expected results in on-premises deployments.</span></span> <span data-ttu-id="b3d83-113">これは、内部設置型展開ではこれらのコマンドレットが役に立たないという意味ではありませんが、その用途はより高度なトピックであるため、このドキュメントでは扱われません。</span><span class="sxs-lookup"><span data-stu-id="b3d83-113">This is not to say that there is no use for these cmdlets in on-premises deployments, but their use is a more advanced topic that is not covered in this documentation.</span></span>


</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b3d83-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b3d83-114">In This Section</span></span>

<span data-ttu-id="b3d83-115">このセクションのトピックでは、集中ログサービスの構成オプション、パラメーター、および設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="b3d83-115">The topics in this section define the configuration options, parameters, and settings for the Centralized Logging Service.</span></span> <span data-ttu-id="b3d83-116">集中ログサービスの構成方法、構成設定の取得方法、シナリオの作成方法、集中ログサービスのためのセキュリティグループの管理、検索などについては、以下のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3d83-116">Information about how to configure the Centralized Logging Service, how to retrieve the configuration settings, creation of scenarios, management of security groups for Centralized Logging Service, searching, and more is contained in the following topics.</span></span>

  - [<span data-ttu-id="b3d83-117">Lync Server 2013 でのコンピューター、サイト、およびグローバルな集中ログサービスの構成の管理</span><span class="sxs-lookup"><span data-stu-id="b3d83-117">Managing computer, site and global Centralized Logging Service configuration in Lync Server 2013</span></span>](lync-server-2013-managing-computer-site-and-global-centralized-logging-service-configuration.md)

  - [<span data-ttu-id="b3d83-118">Lync Server 2013 での集中ログサービスのプロバイダーの構成</span><span class="sxs-lookup"><span data-stu-id="b3d83-118">Configuring providers for Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-configuring-providers-for-centralized-logging-service.md)

  - [<span data-ttu-id="b3d83-119">Lync Server 2013 での集中ログサービスのシナリオの構成</span><span class="sxs-lookup"><span data-stu-id="b3d83-119">Configuring scenarios for the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-configuring-scenarios-for-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b3d83-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="b3d83-120">See Also</span></span>


[<span data-ttu-id="b3d83-121">Lync Server 2013 の集中ログサービスの概要</span><span class="sxs-lookup"><span data-stu-id="b3d83-121">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  
[<span data-ttu-id="b3d83-122">Lync Server 2013 での集中ログのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="b3d83-122">Centralized Logging cmdlets in Lync Server 2013</span></span>](lync-server-2013-centralized-logging-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

