---
title: 'Lync Server 2013: 大規模な会議のスケジュール処理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Large-meeting scheduling process
ms:assetid: de267458-885f-4176-a8d7-1a218e67640e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205334(v=OCS.15)
ms:contentKeyID: 48185639
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af97cdbd07603c420780a92fbbe0a03c8a4d0520
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="large-meeting-scheduling-process-in-lync-server-2013"></a>Lync Server 2013 での大規模な会議のスケジュールプロセス

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-22_

専用の大規模な会議プールでは、一度に1つの大きな会議のみがサポートされるため、大規模な会議の競合を防ぐために、大規模な会議のスケジュールプロセスを実装することをお勧めします。 このようなスケジュールプロセスの目的は、大規模な会議の設定を簡単にすることです。 このような機能は、Lync Server または Lync Server クライアントによって直接提供されるわけではありません。 こうしたプロセスを実装する 1 つの方法は、組織のサポート チームのチケット システム (使用できる場合) を使用することです。

大規模な会議の開催者の場合、大規模な会議のスケジュールを設定するには、次の手順を実行します。

1.  会議の開催者または代理人は、予定されている会議の時刻、時間、および規模に加えて、発表者のリストを決定します。予測される会議の規模が 250 人を超える場合、または 250 人以下の会議に対して最高のユーザー エクスペリエンスを保証する場合、開催者または代理人は、大規模会議に対して要求を提出します。

2.  スケジュール担当スタッフは、要求された日時が利用できるかどうかを確認します。大規模会議は専用プールで一度に 1 つだけサポートされるため、スケジュール担当スタッフは、大規模会議の予定表をチェックして、要求された日時に別の会議がスケジュールされているかどうかを判定する必要があります。要求された日時が利用できる場合、スタッフは会議の要求を承認します。

3.  要求が承認された場合、スケジュールスタッフは (専用プールの資格情報を使用)、Lync 2013 用のオンライン会議アドインを使用して、専用の大規模な会議プールで会議を設定します。 会議に参加するために使用する URL は、承認通知の一部として要求者に提供されます。

4.  会議の開催者または代理人は、Outlook を使用して、予定されている会議をスケジュールし、会議に参加するための URL を会議の招待状に追加します。次に、会議の開催者または代理人は、招待するユーザーを指定して、会議の招待状を送信します。
    
    次の図は、大規模な会議をスケジュールするための一般的な要求ワークフローと承認ワークフローを示しています。
    
    ![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d](images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")  

</div>

<span> </span>

</div>

</div>

</div>

