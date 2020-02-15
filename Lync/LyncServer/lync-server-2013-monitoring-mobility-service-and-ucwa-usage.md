---
title: 'Lync Server 2013: Mobility Service および UCWA の使用状況の監視'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring Mobility Service and UCWA usage
ms:assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690025(v=OCS.15)
ms:contentKeyID: 48184683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e8fbdd2e411f3613519278f807caed334955810
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048010"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-mobility-service-and-ucwa-usage-in-lync-server-2013"></a>Lync Server 2013 でのモビリティサービスおよび UCWA の使用状況の監視

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-14_

継続的に、Lync Server Mobility Service (Mcx) および統合コミュニケーション Web API (UCWA) で使用されている CPU とメモリを監視する必要があります。 使用状況を監視するには、次のものを使用できます。

**ユニファイドコミュニケーション Web API (UCWA) の場合:**

  - インターネットインフォメーションサービス (IIS) マネージャーの**LyncUcwa**ワーカープロセス。 [**ワーカー プロセス**] ウィンドウで、[**CPU %**] および [**プライベート バイト (KB)**] (メモリ) の列を確認します。

  - [**CPU**] および [**プロセッサ**] パフォーマンス カウンター

ほとんどの展開では、UCWA の CPU 使用率は平均で15% を下回っている必要があります。 メモリ使用量は、「 [Lync server 2013 のサーバーのメモリ容量制限の監視](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)」で説明されている制限の範囲内に収まる必要があります。

CPU およびメモリの使用状況カウンターに加えて、次のパフォーマンスカウンターを使用して、サーバーが要求で過負荷になっていないかどうかを判断するのに役立てることができます。

  - **LS: web-調整と認証\\web-処理中の要求の総数**。これは、サーバー上で保留中の WEB 要求の数を示します。 このカウンターが1万に達すると、次の要求は失敗し、エラーメッセージ "503-サービスを使用できません。" が表示されます。

  - **ASP.NET\\Requests はキューに入れら**れます (常に0である必要があります)。

<div>


> [!NOTE]  
> これらの値と一致するか、それを超える場合は、Web サービスをホストしているコンピューターの CPU、コアの数、およびメモリの正確なサイジングに関する容量計画を再検討して再計算する必要があります。



</div>

**Mobility Service (Mcx) の場合:**

  - インターネットインフォメーションサービス (IIS) マネージャーの**Csintmcxapppool**および**csextmcxapppool**ワーカープロセス。 [**ワーカー プロセス**] ウィンドウで、[**CPU %**] および [**プライベート バイト (KB)**] (メモリ) の列を確認します。

  - [**CPU**] および [**プロセッサ**] パフォーマンス カウンター

ほとんどの展開では、モビリティサービスの CPU 使用率は平均で15% を下回っている必要があります。 メモリ使用量は、「 [Lync server 2013 のサーバーのメモリ容量制限の監視](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)」で説明されている制限の範囲内に収まる必要があります。

CPU とメモリの使用状況カウンターに加えて、以下の ASP.NET パフォーマンス カウンターを使用すると、サーバーが要求で過負荷になっていないかどうかを確認するのに役立つ場合があります。

  - **ASP.NET v v2.0.50727\\は Current を要求**します。これは、サーバー上で保留中の web 要求の数を示します。 このカウンターが5000に達すると、以降の要求は失敗し、"503-サービスは使用できません" というエラーメッセージが表示されます。

  - **ASP.NET\\Requests はキューに入れら**れます (常に0である必要があります)。

<div>


> [!NOTE]  
> これらの値と一致するか、それを超えた場合は、Web サービスをホストしているコンピューターの CPU、コア数、およびメモリの正確なサイジングを行うために、容量計画を再検討して再計算する必要があります。



</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのサーバーのメモリ容量制限の監視](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

