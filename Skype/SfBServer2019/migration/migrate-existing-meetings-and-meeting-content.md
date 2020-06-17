---
title: 既存の会議および会議コンテンツの移行
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ユーザーアカウントを Skype for Business Server 2019 サーバーに移動すると、そのユーザーアカウントを使用して次の情報が移動されます。
ms.openlocfilehash: 6513f581f55028ec28d4cf05f1f1b3df37c49e65
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752689"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="14b36-103">既存の会議および会議コンテンツの移行</span><span class="sxs-lookup"><span data-stu-id="14b36-103">Migrate existing meetings and meeting content</span></span>

<span data-ttu-id="14b36-104">ユーザーアカウントが Skype for Business Server 2019 サーバーに移動されると、そのユーザーアカウントを使用して次の情報が移動されます。</span><span class="sxs-lookup"><span data-stu-id="14b36-104">When a user account is moved to a Skype for Business Server 2019 server, the following information is moved with that user account:</span></span>
  
- <span data-ttu-id="14b36-105">**そのユーザーがスケジュールした会議**。</span><span class="sxs-lookup"><span data-stu-id="14b36-105">**Meetings already scheduled by the user**.</span></span> <span data-ttu-id="14b36-106">電話会議ディレクトリおよび電話会議データも移動されます。</span><span class="sxs-lookup"><span data-stu-id="14b36-106">This includes moving the conferencing directories and conferencing data.</span></span>
    
- <span data-ttu-id="14b36-107">**ユーザーの暗証番号 (PIN)**。</span><span class="sxs-lookup"><span data-stu-id="14b36-107">**User's personal identification number (PIN)**.</span></span> <span data-ttu-id="14b36-108">ユーザーの現在の PIN は、期限が切れるか、ユーザーが新しい PIN を要求するまで引き続き機能します。</span><span class="sxs-lookup"><span data-stu-id="14b36-108">The user's current PIN continues to work until it expires or the user requests a new PIN.</span></span>
    
<span data-ttu-id="14b36-109">次に示すユーザー アカウント情報は、新しいサーバーに移動されません。</span><span class="sxs-lookup"><span data-stu-id="14b36-109">The following user account information does not move to the new server.</span></span>
  
- <span data-ttu-id="14b36-110">**会議コンテンツ**。</span><span class="sxs-lookup"><span data-stu-id="14b36-110">**Meeting content**.</span></span> <span data-ttu-id="14b36-111">PowerPoint、ホワイトボード、添付ファイル、投票データなど、会議中に共有されるコンテンツを移動するには、 **-moveconferencedata**パラメーターを、 **csuser**コマンドレットの一部として使用します。</span><span class="sxs-lookup"><span data-stu-id="14b36-111">In order to move the content shared during a meeting, such as PowerPoint, Whiteboard, attachments, or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span> 
    

