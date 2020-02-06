---
title: 既存の会議および会議コンテンツの移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ユーザーアカウントを Skype for Business Server 2019 サーバーに移動すると、次の情報がそのユーザーアカウントに移動されます。
ms.openlocfilehash: 6394ebf798560ce5a13fe7ba931076364257decc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813475"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="f8b18-103">既存の会議および会議コンテンツの移行</span><span class="sxs-lookup"><span data-stu-id="f8b18-103">Migrate existing meetings and meeting content</span></span>

<span data-ttu-id="f8b18-104">ユーザーアカウントを Skype for Business Server 2019 サーバーに移動すると、次の情報がそのユーザーアカウントで移動されます。</span><span class="sxs-lookup"><span data-stu-id="f8b18-104">When a user account is moved to a Skype for Business Server 2019 server, the following information is moved with that user account:</span></span>
  
- <span data-ttu-id="f8b18-105">**ユーザーが既にスケジュールした会議**。</span><span class="sxs-lookup"><span data-stu-id="f8b18-105">**Meetings already scheduled by the user**.</span></span> <span data-ttu-id="f8b18-106">これには、会議ディレクトリと会議データの移動が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f8b18-106">This includes moving the conferencing directories and conferencing data.</span></span>
    
- <span data-ttu-id="f8b18-107">**ユーザーの暗証番号 (PIN)**。</span><span class="sxs-lookup"><span data-stu-id="f8b18-107">**User's personal identification number (PIN)**.</span></span> <span data-ttu-id="f8b18-108">ユーザーの現在の PIN は、有効期限が切れるか、ユーザーが新しい PIN を要求するまで、引き続き動作します。</span><span class="sxs-lookup"><span data-stu-id="f8b18-108">The user's current PIN continues to work until it expires or the user requests a new PIN.</span></span>
    
<span data-ttu-id="f8b18-109">次のユーザーアカウント情報は、新しいサーバーに移動されません。</span><span class="sxs-lookup"><span data-stu-id="f8b18-109">The following user account information does not move to the new server.</span></span>
  
- <span data-ttu-id="f8b18-110">**会議コンテンツ**。</span><span class="sxs-lookup"><span data-stu-id="f8b18-110">**Meeting content**.</span></span> <span data-ttu-id="f8b18-111">会議中に共有されたコンテンツ (PowerPoint、ホワイトボード、添付ファイル、投票データなど) を移動するには、 **move-CsUser**コマンドレットの一部として、 **-moveconの [data** ] パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="f8b18-111">In order to move the content shared during a meeting, such as PowerPoint, Whiteboard, attachments, or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span> 
    

