---
title: 既存の会議および会議コンテンツの移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ユーザー アカウントに移動した場合、Skype をビジネス サーバー 2019 サーバーに対して、次の情報がそのユーザー アカウントに移動します。
ms.openlocfilehash: bf10fa6b4ad4d555ce80dee5ec4e4a6584020ac7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874662"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="b6425-103">既存の会議および会議コンテンツの移行</span><span class="sxs-lookup"><span data-stu-id="b6425-103">Migrate existing meetings and meeting content</span></span>

<span data-ttu-id="b6425-104">ビジネス サーバー 2019 サーバーの Skype にユーザー アカウントを移動すると、次の情報がそのユーザー アカウントに移動します。</span><span class="sxs-lookup"><span data-stu-id="b6425-104">When a user account is moved to a Skype for Business Server 2019 server, the following information is moved with that user account:</span></span>
  
- <span data-ttu-id="b6425-105">**ユーザーが既にスケジュールされている会議**。</span><span class="sxs-lookup"><span data-stu-id="b6425-105">**Meetings already scheduled by the user**.</span></span> <span data-ttu-id="b6425-106">会議ディレクトリと会議のデータの移動が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b6425-106">This includes moving the conferencing directories and conferencing data.</span></span>
    
- <span data-ttu-id="b6425-107">**ユーザーの個人識別番号 (PIN)** です。</span><span class="sxs-lookup"><span data-stu-id="b6425-107">**User's personal identification number (PIN)**.</span></span> <span data-ttu-id="b6425-108">ユーザーの現在の PIN が期限切れになるか、ユーザーが新しい PIN を要求するまでの作業を続行します。</span><span class="sxs-lookup"><span data-stu-id="b6425-108">The user's current PIN continues to work until it expires or the user requests a new PIN.</span></span>
    
<span data-ttu-id="b6425-109">次のユーザー アカウント情報を新しいサーバーに移動しません。</span><span class="sxs-lookup"><span data-stu-id="b6425-109">The following user account information does not move to the new server.</span></span>
  
- <span data-ttu-id="b6425-110">**ミーティング コンテンツ**をします。</span><span class="sxs-lookup"><span data-stu-id="b6425-110">**Meeting content**.</span></span> <span data-ttu-id="b6425-111">PowerPoint など、会議中に共有されているコンテンツを移動するためにホワイト ボード、添付ファイル、またはポーリング ・ データは**移動 CsUser**コマンドレットの一部として**の MoveConferenceData**パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="b6425-111">In order to move the content shared during a meeting, such as PowerPoint, Whiteboard, attachments, or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span> 
    

