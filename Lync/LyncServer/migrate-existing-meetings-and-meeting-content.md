---
title: 既存の会議および会議コンテンツの移行
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
ms.openlocfilehash: 0aa0b83e2e206421300d16faf220b3fa0bb81503
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762925"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="ca25d-102">既存の会議および会議コンテンツの移行</span><span class="sxs-lookup"><span data-stu-id="ca25d-102">Migrate existing meetings and meeting content</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca25d-103">_**最終更新日:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="ca25d-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="ca25d-104">ユーザーアカウントを Lync Server 2010 から Lync Server 2013 サーバーに移動すると、次の情報がそのユーザーアカウントに移動されます。</span><span class="sxs-lookup"><span data-stu-id="ca25d-104">When a user account is moved from Lync Server 2010 to a Lync Server 2013 server, the following information is moved with that user account:</span></span>

  - <span data-ttu-id="ca25d-105">**ユーザーが既にスケジュールした会議**。</span><span class="sxs-lookup"><span data-stu-id="ca25d-105">**Meetings already scheduled by the user**.</span></span> <span data-ttu-id="ca25d-106">これには、会議ディレクトリと会議データの移動が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ca25d-106">This includes moving the conferencing directories and conferencing data.</span></span>

  - <span data-ttu-id="ca25d-107">**ユーザーの暗証番号 (PIN)**。</span><span class="sxs-lookup"><span data-stu-id="ca25d-107">**User’s personal identification number (PIN)**.</span></span> <span data-ttu-id="ca25d-108">ユーザーの現在の PIN は、有効期限が切れるか、ユーザーが新しい PIN を要求するまで、引き続き動作します。</span><span class="sxs-lookup"><span data-stu-id="ca25d-108">The user’s current PIN continues to work until it expires or the user requests a new PIN.</span></span>

<span data-ttu-id="ca25d-109">次のユーザーアカウント情報は、新しいサーバーに移動されません。</span><span class="sxs-lookup"><span data-stu-id="ca25d-109">The following user account information does not move to the new server.</span></span>

  - <span data-ttu-id="ca25d-110">**会議コンテンツ**。</span><span class="sxs-lookup"><span data-stu-id="ca25d-110">**Meeting content**.</span></span> <span data-ttu-id="ca25d-111">会議中に共有されたコンテンツ (PowerPoint、ホワイトボード、添付ファイル、投票データなど) を移動するには、 **move-CsUser**コマンドレットの一部として、 **-moveconの [data** ] パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="ca25d-111">In order to move the content shared during a meeting, for example PowerPoint, Whiteboard, attachments or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

