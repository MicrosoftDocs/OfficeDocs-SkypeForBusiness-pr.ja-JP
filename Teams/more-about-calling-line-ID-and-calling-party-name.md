---
title: 発信回線 ID と発信者名の詳細
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: roykuntz, jenstr
ms.topic: article
ms.tgt.pltfrm: cloud
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business Online
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
ms.service: msteams
description: 通話回線 ID と通話者名について説明します。
ms.openlocfilehash: dd68327c8fb3f63bf17e0736f9d41b727efc1ff8
ms.sourcegitcommit: 83f14c4c79559ef28357ff076938e52b369fc0c7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2021
ms.locfileid: "52308316"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a><span data-ttu-id="a3037-103">発信回線 ID と発信者名の詳細</span><span class="sxs-lookup"><span data-stu-id="a3037-103">More about Calling Line ID and Calling Party Name</span></span>

<span data-ttu-id="a3037-104">CallerID は、次の 2 つのユーザー向け情報で構成されます。</span><span class="sxs-lookup"><span data-stu-id="a3037-104">CallerID consists of two user-facing pieces of information:</span></span>

- <span data-ttu-id="a3037-105">電話番号 (通常は CLID または通話回線 ID と呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="a3037-105">A phone number (typically referred to as CLID or calling line ID).</span></span>

- <span data-ttu-id="a3037-106">呼び出し元のパーティー名 (通常は CNAM と呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="a3037-106">Calling party name (typically referred to as CNAM).</span></span> 

<span data-ttu-id="a3037-107">呼び出しが行われた場合、CLID (電話番号) は宛先の運送業者 (終端通信事業者とも呼ばれる) にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="a3037-107">When a call is made, the CLID (phone number) is routed to the destination's carrier (also known as the terminating carrier).</span></span> <span data-ttu-id="a3037-108">この情報は国が CNAM を実装した方法に依存する (ある場合) ため、呼び出しの CNAM 情報は呼び出しでルーティングされる場合とルーティングされない場合があります。</span><span class="sxs-lookup"><span data-stu-id="a3037-108">The CNAM information for the call may or may not be routed with the call because as this information depends on how the country has implemented CNAM (if at all).</span></span> <span data-ttu-id="a3037-109">呼び出しによる CNAM 配信の信頼性は、通話を処理する国と通信事業者によって異なります。仲介者または終了運送業者のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="a3037-109">The reliability of CNAM delivery with the call varies depending on the country and carriers that handle the call--either as an intermediary or a terminating carrier.</span></span> 

<span data-ttu-id="a3037-110">CLID & CNAM 送信は、終端の通信事業者の責任です。</span><span class="sxs-lookup"><span data-stu-id="a3037-110">CLID & CNAM transmission is the responsibility of the terminating carrier.</span></span> <span data-ttu-id="a3037-111">終端の通信事業者は、CNAM & CLID をサポートし、両方の値に対して最新のレコードを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3037-111">The terminating carrier must support CLID & CNAM functionality as well as provide up-to-date records for both values.</span></span> <span data-ttu-id="a3037-112">Microsoft は呼び出しを発信するときに CLID 値を確実に提供しますが、仲介業者または終端の通信事業者を通過すると、それらの値はそのまま保持されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a3037-112">Microsoft reliably provides CLID values when originating calls, but those values may not be kept intact once they pass through an intermediary carrier or the terminating carrier.</span></span> <span data-ttu-id="a3037-113">CLID の値が仲介業者または終端の運送業者によって変更、省略、または切り捨てられた場合、Microsoft は公衆電話ネットワークでこのような問題を修正する方法はほとんど何もありません。</span><span class="sxs-lookup"><span data-stu-id="a3037-113">If the CLID value is changed, omitted, or truncated by the intermediary or terminating carrier, Microsoft has little to no recourse in correcting such problems in the public telephone network.</span></span>

<span data-ttu-id="a3037-114">CNAM の不整合は、米国の場合と同様に、中間または終了の通信事業者が権限のあるデータベースの CNAM 情報の更新を遅らせた場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a3037-114">Inconsistencies in CNAM can be caused when the intermediate or terminating carriers delay refreshing the CNAM information in authoritative databases--as in the case of the United States.</span></span> <span data-ttu-id="a3037-115">CNAM の権限のあるデータベースがない国では、個々の運送業者のプラクティスによって、CNAM 情報が呼び出しと同じ状態で到着する際に問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a3037-115">In countries where there are no authoritative databases for CNAM, individual carrier practices can also cause problems with CNAM information arriving intact with the call.</span></span> <span data-ttu-id="a3037-116">Microsoft は現在、米国以外の国で発信元の CNAM 情報をサポートしていない。</span><span class="sxs-lookup"><span data-stu-id="a3037-116">Microsoft currently does not support originating CNAM information in countries other than the United States.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a3037-117">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a3037-117">Related topics</span></span>


