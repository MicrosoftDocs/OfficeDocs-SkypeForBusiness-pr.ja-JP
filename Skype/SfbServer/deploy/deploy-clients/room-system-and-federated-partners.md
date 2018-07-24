---
title: Skype Room System および Skype for Business のフェデレーション パートナー
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: このトピックでは、Skype for Business フェデレーション パートナー用に Skype Room System をセットアップする方法について説明します。
ms.openlocfilehash: 8099b5af72d4ce8e5a8be25c7fabc8563387dd46
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20997952"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a><span data-ttu-id="5b9d2-103">Skype Room System および Skype for Business のフェデレーション パートナー</span><span class="sxs-lookup"><span data-stu-id="5b9d2-103">Skype Room System and Skype for Business federated partners</span></span>
 
<span data-ttu-id="5b9d2-104">このトピックでは、Skype for Business フェデレーション パートナー用に Skype Room System をセットアップする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5b9d2-104">Read this topic to learn how to set up Skype Room System for Skype for Business federated partners.</span></span>
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a><span data-ttu-id="5b9d2-105">Skype Room System および Skype for Business のフェデレーション パートナー</span><span class="sxs-lookup"><span data-stu-id="5b9d2-105">Skype Room System and Skype for Business federated partners</span></span>

<span data-ttu-id="5b9d2-106">Skype ルーム システムは、予定表の会議出席依頼に会議のリンクの参加の Skype に依存しています。</span><span class="sxs-lookup"><span data-stu-id="5b9d2-106">Skype Room System relies on the Join Skype for Business Meeting link in the calendar meeting request.</span></span> <span data-ttu-id="5b9d2-107">通常、この参加リンクは会議出席依頼の本文に用意されています。</span><span class="sxs-lookup"><span data-stu-id="5b9d2-107">The join link is usually found in the body of a meeting request.</span></span> <span data-ttu-id="5b9d2-108">ただし、Skype の部屋のシステムは、メッセージの MAPI プロパティには、このリンクによって異なります。</span><span class="sxs-lookup"><span data-stu-id="5b9d2-108">However, Skype Room System depends on this link to be present in the MAPI properties of the message.</span></span> <span data-ttu-id="5b9d2-109">この会議を要求するときに送信されますリモート組織 (連合のビジネス パートナーは、Skype) を既定では、リモート組織の Skype ルーム システムは会議の参加を予定表のリンクを表示しません。</span><span class="sxs-lookup"><span data-stu-id="5b9d2-109">When this meeting request is sent to remote organizations (Skype for Business federated partners), by default the remote organization's Skype Room System will not show the meeting join link on the calendar.</span></span> <span data-ttu-id="5b9d2-110">実際には、リモート組織内のすべての Outlook ユーザーことはできませんアイテムまたは予定表の右クリックでのビジネス会議のための Skype に参加する会議のアラームにします。</span><span class="sxs-lookup"><span data-stu-id="5b9d2-110">In fact, any Outlook users in the remote organization will be unable to join the Skype for Business meeting with a right click of the calendar item or from within the meeting reminder.</span></span> <span data-ttu-id="5b9d2-111">会議出席依頼を開き、Skype の参加をクリックして、メッセージの本文に会議のする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b9d2-111">They must open meeting invite and click Join Skype for Business Meeting in the body of the message.</span></span> 
  
<span data-ttu-id="5b9d2-112">この制約事項は、Outlook と Microsoft Exchange がインターネット経由でメッセージを送信するためのある特別な情報パッケージ化手法を使用していないことに起因しています。</span><span class="sxs-lookup"><span data-stu-id="5b9d2-112">The reason for this limitation is that Outlook and Microsoft Exchange do not use a special method to package information for sending messages across the Internet.</span></span> <span data-ttu-id="5b9d2-113">Transport Neutral Encapsulation Format (TNEF) と呼ばれるこの手法は、Exchange 組織外から送信されたメッセージに対して、既定で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="5b9d2-113">This method, referred to as Transport Neutral Encapsulation Format (TNEF), is disabled by default for messages sent externally from an Exchange organization.</span></span> <span data-ttu-id="5b9d2-114">ミーティングの参加のリンクに表示されるリモート Skype ルームのシステムでは、送信元の組織は、次のコマンドを使用して、TNEF を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b9d2-114">For a meeting join link to appear on a remote Skype Room System, the sending organization must enable TNEF by using the following command:</span></span>
  
```
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

<span data-ttu-id="5b9d2-115">リモート組織に対して TNEF を有効にすると、その組織宛てにインターネット経由で送信されるあらゆるメッセージが、TNEF 形式の添付ファイルとして送信されます。</span><span class="sxs-lookup"><span data-stu-id="5b9d2-115">After TNEF is enabled for the remote organization, any message sent over the Internet to the organization is sent as an attachment in TNEF format.</span></span> <span data-ttu-id="5b9d2-116">TNEF を有効にすると、Skype のビジネス会議出席依頼に送信されます、フェデレーション パートナーのビジネスの Skype Skype ルームのシステムはビジネスの会議に参加 Skype をレンダリングすることになり、リモート ユーザーは Skype をビジネス ・ ミーティングに参加することになります。</span><span class="sxs-lookup"><span data-stu-id="5b9d2-116">With TNEF enabled, when a Skype for Business meeting request is sent to the Skype for Business federated partner, Skype Room System will be able to render the Join Skype for Business Meeting and remote users will be able to join Skype for Business meetings.</span></span> 