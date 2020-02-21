---
title: 'Lync Server 2013: 大規模な会議のスケジュール処理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Large-meeting scheduling process
ms:assetid: de267458-885f-4176-a8d7-1a218e67640e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205334(v=OCS.15)
ms:contentKeyID: 48185639
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a11e24f6131ace7323a407d739e2174b24b57a7e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186750"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="large-meeting-scheduling-process-in-lync-server-2013"></a>Lync Server 2013 での大規模な会議のスケジューリングプロセス

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-22_

専用の大規模な会議プールでは、一度に1つの大規模な会議のみがサポートされるので、大規模な会議の競合を防ぐために、大規模な会議のスケジュールプロセスを実装することをお勧めします。 このようなスケジュールプロセスの目的は、大規模な会議の設定を容易にすることです。 このような機能は、Lync Server または Lync Server クライアントによって直接提供されるわけではありません。 このようなプロセスを実装する方法の1つとして、組織のサポートチームのチケットシステムを使用する方法があります (利用可能な場合)。

大規模な会議の開催者の場合、大規模な会議のスケジュールを設定するには、次の手順を実行します。

1.  会議の開催者または代理人は、発表者のリストに加えて、今後の会議の時間、期間、およびサイズを決定します。 予定されている会議のサイズが250ユーザーを超えている場合、またはユーザーが250ユーザーより少ない会議に最高のユーザー環境を確保する場合は、開催者または代理人が大規模会議の要求を送信します。

2.  スケジュールスタッフは、要求された日付と時刻が利用可能かどうかを確認します。 一度に専用プールに対して1つの大規模な会議のみをサポートしているため、スケジュール担当者は、要求された日時に別の会議がスケジュールされているかどうかを確認するために、大規模な会議予定表をチェックする必要があります。 要求された時間が利用可能な場合、スタッフは会議出席依頼を承認します。

3.  要求が承認された場合、(専用プールの資格情報を使用する) スケジュール担当者は Lync 2013 用オンラインミーティングアドインを使用して、専用の大規模な会議プールで会議を設定します。 会議への参加に使用される URL は、承認通知の一部として依頼者に提供されます。

4.  会議の開催者または代理人は、Outlook を使用して今後の会議をスケジュールし、会議出席依頼に参加するための URL を追加します。 会議の開催者または代理人は、招待されるユーザーを指定し、会議出席依頼を送信します。
    
    次の図は、大規模な会議をスケジュールするための一般的な要求および承認のワークフローを示しています。
    
    ![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d](images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")  

</div>

<span> </span>

</div>

</div>

</div>

