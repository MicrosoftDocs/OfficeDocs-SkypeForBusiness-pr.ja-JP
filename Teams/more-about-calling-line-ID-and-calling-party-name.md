---
title: 発信回線 ID と発信者名の詳細
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: 新しいローカル番号のポート注文ウィザードを使用するときに、アカウントを変更できる承認されたユーザーを追加する必要がある理由について説明します。
ms.openlocfilehash: db64a5d1a7e7a5969f66d67d6b056ec6947d44bb
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255400"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a><span data-ttu-id="0da5a-103">発信回線 ID と発信者名の詳細</span><span class="sxs-lookup"><span data-stu-id="0da5a-103">More about Calling Line ID and Calling Party Name</span></span>

<span data-ttu-id="0da5a-104">CallerID は、通常はと呼ばれるので、実際には 2 つのユーザー向け識別可能な情報で構成されます。</span><span class="sxs-lookup"><span data-stu-id="0da5a-104">CallerID, as it is typically referred to, actually consists of two user-facing identifiable pieces of information:</span></span>
    - <span data-ttu-id="0da5a-105">電話番号 (通常は CLID または通話回線 ID と呼ばれます)</span><span class="sxs-lookup"><span data-stu-id="0da5a-105">A phone number (typically referred to as CLID or calling line ID)</span></span> 
    - <span data-ttu-id="0da5a-106">呼び出し元のパーティー名 (通常は CNAM と呼ばれます)。 長さは最大 15 文字です。</span><span class="sxs-lookup"><span data-stu-id="0da5a-106">Calling party name (typically referred to as CNAM) which can be up to 15 characters in length.</span></span> 

<span data-ttu-id="0da5a-107">呼び出しが行われた場合、CLID (電話番号) は宛先の運送業者 (終端通信事業者とも呼ばれる) にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="0da5a-107">When a call is made, the CLID (phone number) is routed to the destination's carrier (also known as the terminating carrier).</span></span> <span data-ttu-id="0da5a-108">呼び出しの CNAM 情報は、国が CNAM を実装した方法 (すべてである場合) によって異なるので、呼び出しでルーティングされる場合と一緒にルーティングされない場合があります。</span><span class="sxs-lookup"><span data-stu-id="0da5a-108">The CNAM info for the call may or may not be routed with the call as this depends on how the country has implemented CNAM (if at all).</span></span> <span data-ttu-id="0da5a-109">呼び出しによる CNAM 配信の信頼性は、通話を仲介者または終了運送業者として処理する国や通信事業者によって異なります。</span><span class="sxs-lookup"><span data-stu-id="0da5a-109">The reliability of CNAM delivery with the call varies depending on the country and carriers which handle the call either as an intermediary and/or a terminating carrier.</span></span> 

<span data-ttu-id="0da5a-110">CLID & CNAM 送信は、終端の通信事業者が CLID & CNAM 機能をサポートし、両方の値に対して最新のレコードを提供する必要がある場合に限り、終端の運送業者の責任です。</span><span class="sxs-lookup"><span data-stu-id="0da5a-110">CLID & CNAM transmission is the responsibility of the terminating carrier insofar as the terminating carrier must support CLID & CNAM functionality as well as provide up to date records for both values.</span></span> <span data-ttu-id="0da5a-111">Microsoft は呼び出しを発信するときに CLID 値を確実に提供しますが、仲介業者または終端の通信事業者を通過すると、それらの値はそのまま保持されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0da5a-111">Microsoft reliably provides CLID values when originating calls, but those values may not be kept intact once they pass through an intermediary carrier or the terminating carrier.</span></span> <span data-ttu-id="0da5a-112">残念ながら、CLID の値が仲介業者または終端の運送業者によって変更、省略、または切り捨てられた場合、Microsoft は公衆電話ネットワークでこのような問題を修正する方法はほとんど何もありません。</span><span class="sxs-lookup"><span data-stu-id="0da5a-112">Unfortunately, in the event the CLID value is changed, omitted or truncated by the intermediary or terminating carrier, Microsoft has little to no recourse in correcting such problems in the public telephone network.</span></span>

<span data-ttu-id="0da5a-113">CNAM の不整合は、米国の場合と同様に、権限のあるデータベースの CNAM 情報を更新する中間または終了の通信事業者の遅延が原因で発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0da5a-113">Inconsistencies in CNAM can be caused by delays in intermediate or terminating carriers refreshing CNAM info in authoritative databases as in the case of the United States.</span></span> <span data-ttu-id="0da5a-114">CNAM の権限のあるデータベースがない国では、個々の運送業者のプラクティスによって、CNAM 情報が呼び出しと同じ状態で到着する際に問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0da5a-114">In countries where there is no authoritative database for CNAM, individual carrier practices can also cause problems with CNAM information arriving intact with the call.</span></span> <span data-ttu-id="0da5a-115">Microsoft は現在、米国以外の国で発信元の CNAM 情報をサポートしていない」と述べています。</span><span class="sxs-lookup"><span data-stu-id="0da5a-115">Microsoft currently does not support originating CNAM information in countries other than the United States."</span></span>

## <a name="related-topics"></a><span data-ttu-id="0da5a-116">関連トピック</span><span class="sxs-lookup"><span data-stu-id="0da5a-116">Related topics</span></span>


