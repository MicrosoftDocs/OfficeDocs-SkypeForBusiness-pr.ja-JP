---
title: 'Lync Server 2013: 高パフォーマンスのモビリティサービスを構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Mobility Service for high performance
ms:assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690042(v=OCS.15)
ms:contentKeyID: 48185332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54a1c9b901e9a861b40a5cfa8c2642e3e3e41ffe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840201"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-service-for-high-performance-in-lync-server-2013"></a>Lync Server 2013 での高パフォーマンスのモビリティサービスの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-17_

<div>


> [!IMPORTANT]  
> このトピックは、lync server 2013 モビリティサービス (Mcx) にのみ適用され、Lync Server 2013 2013 の累積更新プログラムで提供されるように、統合コミュニケーション Web API (UCWA) には適用されません。



</div>

インターネットインフォメーションサービス (IIS) 7.5 にモバイルサービス (Mcx) をインストールすると、Mobility Service installer によって、フロントエンドサーバーの一部のパフォーマンス設定が構成されます。 モビリティでは IIS 7.5 を使用することをお勧めします。 これらの設定は、同時ユーザー要求の最大数と、Mobility Service で利用できるスレッドの最大数に影響します。

以下にパフォーマンス設定を示します。

<div>

## <a name="settings-for-mcx-on-iis-75"></a>IIS 7.5 での Mcx の設定

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

