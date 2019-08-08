---
title: 既存の会議および会議コンテンツの移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ユーザーアカウントを Skype for Business Server 2019 サーバーに移動すると、次の情報がそのユーザーアカウントに移動されます。
ms.openlocfilehash: c8f87b46054a93af87c938d3da7a2a86be9cb0bf
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237999"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="7cbed-103">既存の会議および会議コンテンツの移行</span><span class="sxs-lookup"><span data-stu-id="7cbed-103">Migrate existing meetings and meeting content</span></span>

<span data-ttu-id="7cbed-104">ユーザーアカウントを Skype for Business Server 2019 サーバーに移動すると、次の情報がそのユーザーアカウントで移動されます。</span><span class="sxs-lookup"><span data-stu-id="7cbed-104">When a user account is moved to a Skype for Business Server 2019 server, the following information is moved with that user account:</span></span>
  
- <span data-ttu-id="7cbed-105">**ユーザーが既にスケジュールした会議**。</span><span class="sxs-lookup"><span data-stu-id="7cbed-105">**Meetings already scheduled by the user**.</span></span> <span data-ttu-id="7cbed-106">これには、会議ディレクトリと会議データの移動が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7cbed-106">This includes moving the conferencing directories and conferencing data.</span></span>
    
- <span data-ttu-id="7cbed-107">**ユーザーの暗証番号 (PIN)**。</span><span class="sxs-lookup"><span data-stu-id="7cbed-107">**User's personal identification number (PIN)**.</span></span> <span data-ttu-id="7cbed-108">ユーザーの現在の PIN は、有効期限が切れるか、ユーザーが新しい PIN を要求するまで、引き続き動作します。</span><span class="sxs-lookup"><span data-stu-id="7cbed-108">The user's current PIN continues to work until it expires or the user requests a new PIN.</span></span>
    
<span data-ttu-id="7cbed-109">次のユーザーアカウント情報は、新しいサーバーに移動されません。</span><span class="sxs-lookup"><span data-stu-id="7cbed-109">The following user account information does not move to the new server.</span></span>
  
- <span data-ttu-id="7cbed-110">**会議コンテンツ**。</span><span class="sxs-lookup"><span data-stu-id="7cbed-110">**Meeting content**.</span></span> <span data-ttu-id="7cbed-111">会議中に共有されたコンテンツ (PowerPoint、ホワイトボード、添付ファイル、投票データなど) を移動するには、 **move-CsUser**コマンドレットの一部として、 **-moveconの [data** ] パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="7cbed-111">In order to move the content shared during a meeting, such as PowerPoint, Whiteboard, attachments, or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span> 
    

