---
title: 'Lync Server 2013: 監視対象となる Lync Server コンピューターの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the Lync Server computers that will be monitored
ms:assetid: 9f1b2b91-d5af-42ad-a27d-b0815f762ad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205118(v=OCS.15)
ms:contentKeyID: 48184927
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 39819a546d59d47b60f0c6dfca76cc6939a1cdf2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532354"
---
# <a name="configuring-the-lync-server-computers-that-will-be-monitored-in-lync-server-2013"></a>Lync Server 2013 で監視される Lync Server コンピューターの構成

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-20_

Lync Server 2013 では、Microsoft Lync Server 2010 で使用される中央の探索プロセスは使用されないため、監視する各 Lync Server 2013 コンピューターは、その管理サーバーへのその存在を自己報告できる必要があります。 このことを可能にするには、監視する各コンピューターに Operations Manager エージェントファイルをインストールする必要があります。 エージェントファイルをインストールした後、システムセンタープロキシとして動作するようにコンピューターを構成する必要があります。 これらの手順は、これらのコンピューターに Lync Server をインストールして構成した後に実行する必要があることに注意してください。

</div>

<span> </span>

</div>

</div>

</div>

