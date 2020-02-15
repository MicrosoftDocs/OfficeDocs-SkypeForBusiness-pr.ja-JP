---
title: 既存の会議と会議コンテンツを移行する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate existing meetings and meeting content
ms:assetid: 30516731-2ae1-4a6d-a7e1-d3f05778c954
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688011(v=OCS.15)
ms:contentKeyID: 49733599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31a6036421dd84f466df0f2353b6d5264e0680c2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029108"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="dd181-102">既存の会議と会議コンテンツを移行する</span><span class="sxs-lookup"><span data-stu-id="dd181-102">Migrate existing meetings and meeting content</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd181-103">_**トピックの最終更新日:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="dd181-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="dd181-104">ユーザーアカウントが Lync Server 2010 から Lync Server 2013 サーバーに移動されると、そのユーザーアカウントを使用して次の情報が移動されます。</span><span class="sxs-lookup"><span data-stu-id="dd181-104">When a user account is moved from Lync Server 2010 to a Lync Server 2013 server, the following information is moved with that user account:</span></span>

  - <span data-ttu-id="dd181-p101">**そのユーザーがスケジュールした会議**。電話会議ディレクトリおよび電話会議データも移動されます。</span><span class="sxs-lookup"><span data-stu-id="dd181-p101">**Meetings already scheduled by the user**. This includes moving the conferencing directories and conferencing data.</span></span>

  - <span data-ttu-id="dd181-p102">**ユーザーの暗証番号 (PIN)**。ユーザーの現在の PIN は、有効期限が切れるか、またはユーザーが新しい PIN を要求するまでの間、引き続き有効です。</span><span class="sxs-lookup"><span data-stu-id="dd181-p102">**User’s personal identification number (PIN)**. The user’s current PIN continues to work until it expires or the user requests a new PIN.</span></span>

<span data-ttu-id="dd181-109">次に示すユーザー アカウント情報は、新しいサーバーに移動されません。</span><span class="sxs-lookup"><span data-stu-id="dd181-109">The following user account information does not move to the new server.</span></span>

  - <span data-ttu-id="dd181-p103">**会議コンテンツ**。PowerPoint、ホワイトボード、添付ファイル、投票データなどの会議中に共有されるコンテンツを移動するには、**-MoveConferenceData** パラメーターを指定して **Move-CsUser** コマンドレットを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd181-p103">**Meeting content**. In order to move the content shared during a meeting, for example PowerPoint, Whiteboard, attachments or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

