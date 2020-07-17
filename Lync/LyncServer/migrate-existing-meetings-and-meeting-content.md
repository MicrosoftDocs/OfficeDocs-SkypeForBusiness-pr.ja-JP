---
title: 既存の会議および会議コンテンツの移行
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate existing meetings and meeting content
ms:assetid: 30516731-2ae1-4a6d-a7e1-d3f05778c954
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688011(v=OCS.15)
ms:contentKeyID: 49733599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d811a9e66f368752107020de48e5e09dd641115
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756968"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-existing-meetings-and-meeting-content"></a>既存の会議および会議コンテンツの移行

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-22_

ユーザーアカウントが Lync Server 2010 から Lync Server 2013 サーバーに移動されると、そのユーザーアカウントを使用して次の情報が移動されます。

  - **そのユーザーがスケジュールした会議**。電話会議ディレクトリおよび電話会議データも移動されます。

  - **ユーザーの暗証番号 (PIN)**。ユーザーの現在の PIN は、有効期限が切れるか、またはユーザーが新しい PIN を要求するまでの間、引き続き有効です。

次に示すユーザー アカウント情報は、新しいサーバーに移動されません。

  - **会議コンテンツ**。PowerPoint、ホワイトボード、添付ファイル、投票データなどの会議中に共有されるコンテンツを移動するには、**-MoveConferenceData** パラメーターを指定して **Move-CsUser** コマンドレットを実行する必要があります。

</div>

<span> </span>

</div>

</div>

</div>

