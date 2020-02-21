---
title: 'Lync Server 2013: 高パフォーマンスのモビリティサービスの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Mobility Service for high performance
ms:assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690042(v=OCS.15)
ms:contentKeyID: 48185332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f35d45c1b437c04e96885f098df6026650d61768
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213563"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-service-for-high-performance-in-lync-server-2013"></a>Lync Server 2013 での高パフォーマンスの Mobility Service の構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-17_

<div>


> [!IMPORTANT]  
> このトピックは Lync Server 2013 Mobility Service (Mcx) にのみ適用され、Lync Server 2013 の累積的な更新プログラム (2 月 11 2013 日) で提供されるように、統合コミュニケーション Web API (UCWA) には適用されません。



</div>

インターネットインフォメーションサービス (IIS) 7.5 に Mobility Service (Mcx) をインストールすると、Mobility Service インストーラーによってフロントエンドサーバーのパフォーマンス設定の一部が構成されます。 モビリティでは IIS 7.5 を使用することをお勧めします。 これらの設定は、同時ユーザー要求の最大数と、Mobility Service で利用できるスレッドの最大数に影響します。

次に、パフォーマンス設定を示します。

<div>

## <a name="settings-for-mcx-on-iis-75"></a>IIS 7.5 上の Mcx の設定

1.  **maxConcurrentThreadsPerCPU** は、ゼロ (0) に設定されます。

2.  **maxConcurrentRequestsPerCPU** は、ゼロ (0) に設定されます。

3.  ASP.NET プロセス モデルは、AutoConfig に設定されます (IIS 7.5 のみ)。

4.  HTTP.sys のキューの制限は 1,000 に設定されます (既定)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

