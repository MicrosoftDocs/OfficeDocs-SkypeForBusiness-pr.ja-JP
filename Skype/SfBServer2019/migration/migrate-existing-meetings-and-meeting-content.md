---
title: 既存の会議および会議コンテンツの移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ユーザーアカウントを Skype for Business Server 2019 サーバーに移動すると、次の情報がそのユーザーアカウントに移動されます。
ms.openlocfilehash: 4b5c7981374f3e2bf6dc2d87a0b21d972ddb14ae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288601"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="946d3-103">既存の会議および会議コンテンツの移行</span><span class="sxs-lookup"><span data-stu-id="946d3-103">Migrate existing meetings and meeting content</span></span>

<span data-ttu-id="946d3-104">ユーザーアカウントを Skype for Business Server 2019 サーバーに移動すると、次の情報がそのユーザーアカウントで移動されます。</span><span class="sxs-lookup"><span data-stu-id="946d3-104">When a user account is moved to a Skype for Business Server 2019 server, the following information is moved with that user account:</span></span>
  
- <span data-ttu-id="946d3-105">**ユーザーが既にスケジュールした会議**。</span><span class="sxs-lookup"><span data-stu-id="946d3-105">**Meetings already scheduled by the user**.</span></span> <span data-ttu-id="946d3-106">これには、会議ディレクトリと会議データの移動が含まれます。</span><span class="sxs-lookup"><span data-stu-id="946d3-106">This includes moving the conferencing directories and conferencing data.</span></span>
    
- <span data-ttu-id="946d3-107">**ユーザーの暗証番号 (PIN)**。</span><span class="sxs-lookup"><span data-stu-id="946d3-107">**User's personal identification number (PIN)**.</span></span> <span data-ttu-id="946d3-108">ユーザーの現在の PIN は、有効期限が切れるか、ユーザーが新しい PIN を要求するまで、引き続き動作します。</span><span class="sxs-lookup"><span data-stu-id="946d3-108">The user's current PIN continues to work until it expires or the user requests a new PIN.</span></span>
    
<span data-ttu-id="946d3-109">次のユーザーアカウント情報は、新しいサーバーに移動されません。</span><span class="sxs-lookup"><span data-stu-id="946d3-109">The following user account information does not move to the new server.</span></span>
  
- <span data-ttu-id="946d3-110">**会議コンテンツ**。</span><span class="sxs-lookup"><span data-stu-id="946d3-110">**Meeting content**.</span></span> <span data-ttu-id="946d3-111">会議中に共有されたコンテンツ (PowerPoint、ホワイトボード、添付ファイル、投票データなど) を移動するには、 **move-CsUser**コマンドレットの一部として、 **-moveconの [data** ] パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="946d3-111">In order to move the content shared during a meeting, such as PowerPoint, Whiteboard, attachments, or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span> 
    

