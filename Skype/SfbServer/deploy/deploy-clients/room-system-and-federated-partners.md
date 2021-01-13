---
title: Skype Room System と Skype for Business フェデレーション パートナー
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: このトピックでは、Skype for Business フェデレーション パートナー用に Skype Room System をセットアップする方法について説明します。
ms.openlocfilehash: ac0203479907f830f1bc6cec6831f8804906e669
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820807"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a><span data-ttu-id="838c8-103">Skype Room System と Skype for Business フェデレーション パートナー</span><span class="sxs-lookup"><span data-stu-id="838c8-103">Skype Room System and Skype for Business federated partners</span></span>
 
<span data-ttu-id="838c8-104">このトピックでは、Skype for Business フェデレーション パートナー用に Skype Room System をセットアップする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="838c8-104">Read this topic to learn how to set up Skype Room System for Skype for Business federated partners.</span></span>
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a><span data-ttu-id="838c8-105">Skype Room System と Skype for Business フェデレーション パートナー</span><span class="sxs-lookup"><span data-stu-id="838c8-105">Skype Room System and Skype for Business federated partners</span></span>

<span data-ttu-id="838c8-106">Skype Room System は、予定表の会議出席依頼の [Skype for Business 会議に参加する] リンクに依存します。</span><span class="sxs-lookup"><span data-stu-id="838c8-106">Skype Room System relies on the Join Skype for Business Meeting link in the calendar meeting request.</span></span> <span data-ttu-id="838c8-107">通常、参加リンクは会議出席依頼の本文に表示されます。</span><span class="sxs-lookup"><span data-stu-id="838c8-107">The join link is usually found in the body of a meeting request.</span></span> <span data-ttu-id="838c8-108">ただし、Skype Room System は、このリンクがメッセージの MAPI プロパティに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="838c8-108">However, Skype Room System depends on this link to be present in the MAPI properties of the message.</span></span> <span data-ttu-id="838c8-109">この会議出席依頼がリモート組織 (Skype for Business フェデレーション パートナー) に送信される場合、既定では、リモート組織の Skype Room System は予定表に会議参加リンクを表示します。</span><span class="sxs-lookup"><span data-stu-id="838c8-109">When this meeting request is sent to remote organizations (Skype for Business federated partners), by default the remote organization's Skype Room System will not show the meeting join link on the calendar.</span></span> <span data-ttu-id="838c8-110">実際、リモート組織の Outlook ユーザーは、予定表アイテムを右クリックするか、会議のアラーム内から Skype for Business 会議に参加できません。</span><span class="sxs-lookup"><span data-stu-id="838c8-110">In fact, any Outlook users in the remote organization will be unable to join the Skype for Business meeting with a right click of the calendar item or from within the meeting reminder.</span></span> <span data-ttu-id="838c8-111">会議の招待を開き、メッセージの本文で [Skype for Business 会議に参加] をクリックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="838c8-111">They must open meeting invite and click Join Skype for Business Meeting in the body of the message.</span></span> 
  
<span data-ttu-id="838c8-112">この制限の理由は、Outlook と Microsoft Exchange がインターネットを通してメッセージを送信する情報をパッケージ化するために特別な方法を使用しなだからです。</span><span class="sxs-lookup"><span data-stu-id="838c8-112">The reason for this limitation is that Outlook and Microsoft Exchange do not use a special method to package information for sending messages across the Internet.</span></span> <span data-ttu-id="838c8-113">トランスポート ニュートラル カプセル化形式 (TNEF) と呼ばれるこのメソッドは、Exchange 組織から外部に送信されるメッセージに対して既定で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="838c8-113">This method, referred to as Transport Neutral Encapsulation Format (TNEF), is disabled by default for messages sent externally from an Exchange organization.</span></span> <span data-ttu-id="838c8-114">会議参加リンクをリモートの Skype Room System に表示するには、次のコマンドを使用して送信組織が TNEF を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="838c8-114">For a meeting join link to appear on a remote Skype Room System, the sending organization must enable TNEF by using the following command:</span></span>
  
```powershell
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

<span data-ttu-id="838c8-115">リモート組織で TNEF が有効になると、インターネットを通して組織に送信されるメッセージは、TNEF 形式の添付ファイルとして送信されます。</span><span class="sxs-lookup"><span data-stu-id="838c8-115">After TNEF is enabled for the remote organization, any message sent over the Internet to the organization is sent as an attachment in TNEF format.</span></span> <span data-ttu-id="838c8-116">TNEF を有効にすると、Skype for Business の会議出席依頼が Skype for Business フェデレーション パートナーに送信された場合、Skype Room System は Skype for Business 会議に参加し、リモート ユーザーは Skype for Business 会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="838c8-116">With TNEF enabled, when a Skype for Business meeting request is sent to the Skype for Business federated partner, Skype Room System will be able to render the Join Skype for Business Meeting and remote users will be able to join Skype for Business meetings.</span></span> 
