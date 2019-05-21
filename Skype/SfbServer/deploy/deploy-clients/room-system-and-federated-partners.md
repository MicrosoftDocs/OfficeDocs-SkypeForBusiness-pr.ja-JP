---
title: Skype Room System および Skype for Business のフェデレーション パートナー
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: このトピックでは、Skype for Business フェデレーション パートナー用に Skype Room System をセットアップする方法について説明します。
ms.openlocfilehash: f47659ce1fcf98e026eea3c4a1f38f74575235dc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34291717"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a><span data-ttu-id="12ecd-103">Skype Room System および Skype for Business のフェデレーション パートナー</span><span class="sxs-lookup"><span data-stu-id="12ecd-103">Skype Room System and Skype for Business federated partners</span></span>
 
<span data-ttu-id="12ecd-104">このトピックでは、Skype for Business フェデレーション パートナー用に Skype Room System をセットアップする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="12ecd-104">Read this topic to learn how to set up Skype Room System for Skype for Business federated partners.</span></span>
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a><span data-ttu-id="12ecd-105">Skype Room System および Skype for Business のフェデレーション パートナー</span><span class="sxs-lookup"><span data-stu-id="12ecd-105">Skype Room System and Skype for Business federated partners</span></span>

<span data-ttu-id="12ecd-106">Skype Room System は、予定表の会議出席依頼の [Skype for Business 会議への参加] リンクに依存しています。</span><span class="sxs-lookup"><span data-stu-id="12ecd-106">Skype Room System relies on the Join Skype for Business Meeting link in the calendar meeting request.</span></span> <span data-ttu-id="12ecd-107">通常、この参加リンクは会議出席依頼の本文に用意されています。</span><span class="sxs-lookup"><span data-stu-id="12ecd-107">The join link is usually found in the body of a meeting request.</span></span> <span data-ttu-id="12ecd-108">ただし、Skype Room システムは、このリンクに依存して、メッセージの MAPI プロパティに表示されます。</span><span class="sxs-lookup"><span data-stu-id="12ecd-108">However, Skype Room System depends on this link to be present in the MAPI properties of the message.</span></span> <span data-ttu-id="12ecd-109">この会議出席依頼がリモート組織 (Skype for Business フェデレーションパートナー) に送信されると、既定では、リモート組織の Skype Room System には予定表の [会議参加] リンクが表示されません。</span><span class="sxs-lookup"><span data-stu-id="12ecd-109">When this meeting request is sent to remote organizations (Skype for Business federated partners), by default the remote organization's Skype Room System will not show the meeting join link on the calendar.</span></span> <span data-ttu-id="12ecd-110">実際には、リモート組織のすべての Outlook ユーザーは、予定表アイテムを右クリックするか、会議のアラーム内から、Skype for Business 会議に参加することはできません。</span><span class="sxs-lookup"><span data-stu-id="12ecd-110">In fact, any Outlook users in the remote organization will be unable to join the Skype for Business meeting with a right click of the calendar item or from within the meeting reminder.</span></span> <span data-ttu-id="12ecd-111">会議出席依頼を開き、メッセージの本文で [Skype for Business 会議に参加する] をクリックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="12ecd-111">They must open meeting invite and click Join Skype for Business Meeting in the body of the message.</span></span> 
  
<span data-ttu-id="12ecd-112">この制約事項は、Outlook と Microsoft Exchange がインターネット経由でメッセージを送信するためのある特別な情報パッケージ化手法を使用していないことに起因しています。</span><span class="sxs-lookup"><span data-stu-id="12ecd-112">The reason for this limitation is that Outlook and Microsoft Exchange do not use a special method to package information for sending messages across the Internet.</span></span> <span data-ttu-id="12ecd-113">Transport Neutral Encapsulation Format (TNEF) と呼ばれるこの手法は、Exchange 組織外から送信されたメッセージに対して、既定で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="12ecd-113">This method, referred to as Transport Neutral Encapsulation Format (TNEF), is disabled by default for messages sent externally from an Exchange organization.</span></span> <span data-ttu-id="12ecd-114">会議参加リンクがリモートの Skype Room システムに表示されるようにするには、次のコマンドを使用して、送信側の組織が TNEF を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="12ecd-114">For a meeting join link to appear on a remote Skype Room System, the sending organization must enable TNEF by using the following command:</span></span>
  
```
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

<span data-ttu-id="12ecd-115">リモート組織に対して TNEF を有効にすると、その組織宛てにインターネット経由で送信されるあらゆるメッセージが、TNEF 形式の添付ファイルとして送信されます。</span><span class="sxs-lookup"><span data-stu-id="12ecd-115">After TNEF is enabled for the remote organization, any message sent over the Internet to the organization is sent as an attachment in TNEF format.</span></span> <span data-ttu-id="12ecd-116">TNEF を有効にすると、skype for business のフェデレーションパートナーに Skype for Business 会議出席依頼が送信されると、skype Room System は skype for business 会議に参加することができ、リモートユーザーは Skype for Business 会議に参加できるようになります。</span><span class="sxs-lookup"><span data-stu-id="12ecd-116">With TNEF enabled, when a Skype for Business meeting request is sent to the Skype for Business federated partner, Skype Room System will be able to render the Join Skype for Business Meeting and remote users will be able to join Skype for Business meetings.</span></span> 
