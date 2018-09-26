---
title: 既存のミーティングとミーティングのコンテンツを移行します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ユーザー アカウントに移動した場合、Skype をビジネス サーバー 2019 サーバーに対して、次の情報がそのユーザー アカウントに移動します。
ms.openlocfilehash: 03ccad0498af777c7d93765af7df2baf5da51f83
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "25030372"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="6af5d-103">既存のミーティングとミーティングのコンテンツを移行します。</span><span class="sxs-lookup"><span data-stu-id="6af5d-103">Migrate existing meetings and meeting content</span></span>

<span data-ttu-id="6af5d-104">ビジネス サーバー 2019 サーバーの Skype にユーザー アカウントを移動すると、次の情報がそのユーザー アカウントに移動します。</span><span class="sxs-lookup"><span data-stu-id="6af5d-104">When a user account is moved to a Skype for Business Server 2019 server, the following information is moved with that user account:</span></span>
  
- <span data-ttu-id="6af5d-105">**ユーザーが既にスケジュールされている会議**。</span><span class="sxs-lookup"><span data-stu-id="6af5d-105">**Meetings already scheduled by the user**.</span></span> <span data-ttu-id="6af5d-106">会議ディレクトリと会議のデータの移動が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6af5d-106">This includes moving the conferencing directories and conferencing data.</span></span>
    
- <span data-ttu-id="6af5d-107">**ユーザーの個人識別番号 (PIN)** です。</span><span class="sxs-lookup"><span data-stu-id="6af5d-107">**User's personal identification number (PIN)**.</span></span> <span data-ttu-id="6af5d-108">ユーザーの現在の PIN が期限切れになるか、ユーザーが新しい PIN を要求するまでの作業を続行します。</span><span class="sxs-lookup"><span data-stu-id="6af5d-108">The user's current PIN continues to work until it expires or the user requests a new PIN.</span></span>
    
<span data-ttu-id="6af5d-109">次のユーザー アカウント情報を新しいサーバーに移動しません。</span><span class="sxs-lookup"><span data-stu-id="6af5d-109">The following user account information does not move to the new server.</span></span>
  
- <span data-ttu-id="6af5d-110">**ミーティング コンテンツ**をします。</span><span class="sxs-lookup"><span data-stu-id="6af5d-110">**Meeting content**.</span></span> <span data-ttu-id="6af5d-111">PowerPoint など、会議中に共有されているコンテンツを移動するためにホワイト ボード、添付ファイル、またはポーリング ・ データは**移動 CsUser**コマンドレットの一部として**の MoveConferenceData**パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="6af5d-111">In order to move the content shared during a meeting, such as PowerPoint, Whiteboard, attachments, or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span> 
    

