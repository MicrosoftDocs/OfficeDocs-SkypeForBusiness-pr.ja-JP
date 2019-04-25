---
title: 発信回線 ID と発信者名の詳細
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 新しいローカル番号のポートの注文ウィザードを使用すると、アカウントに変更を加える権限を持つ人を追加する必要がある理由について説明します。
ms.openlocfilehash: 846abfd5b6973a02ad1a7388b45a79ec709695a0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229869"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a><span data-ttu-id="e4c6d-103">発信回線 ID と発信者名の詳細</span><span class="sxs-lookup"><span data-stu-id="e4c6d-103">More about Calling Line ID and Calling Party Name</span></span>

<span data-ttu-id="e4c6d-104">発信者番号、参照されている通常、実際にで構成されます情報のユーザーに接続する特定の 2 つの要素。</span><span class="sxs-lookup"><span data-stu-id="e4c6d-104">CallerID, as it is typically referred to, actually consists of two user-facing identifiable pieces of information:</span></span>
    - <span data-ttu-id="e4c6d-105">(CLID または通話とライン ID と通常呼ばれる) 電話番号</span><span class="sxs-lookup"><span data-stu-id="e4c6d-105">A phone number (typically referred to as CLID or calling line ID)</span></span> 
    - <span data-ttu-id="e4c6d-106">15 文字までの長さは、関係者名 (一般的には CNAM と呼ばれます) を呼び出しています。</span><span class="sxs-lookup"><span data-stu-id="e4c6d-106">Calling party name (typically referred to as CNAM) which can be up to 15 characters in length.</span></span> 

<span data-ttu-id="e4c6d-107">呼び出しが行われた、CLID (電話番号) にリンク先の配送業者 (終端キャリアとも呼ばれます) にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="e4c6d-107">When a call is made, the CLID (phone number) is routed to the destination's carrier (also known as the terminating carrier).</span></span> <span data-ttu-id="e4c6d-108">CNAM の呼び出しの情報は、この実装によって異なりますどの国が CNAM (ある場合) と、呼び出しにルーティングされません可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e4c6d-108">The CNAM info for the call may or may not be routed with the call as this depends on how the country has implemented CNAM (if at all).</span></span> <span data-ttu-id="e4c6d-109">呼び出しに CNAM の配信の信頼性は、国との中間層として、その呼び出しを処理する通信事業者または終端のキャリアによって異なります。</span><span class="sxs-lookup"><span data-stu-id="e4c6d-109">The reliability of CNAM delivery with the call varies depending on the country and carriers which handle the call either as an intermediary and/or a terminating carrier.</span></span> 

<span data-ttu-id="e4c6d-110">CLID & CNAM の転送は、キャリアを終了する必要があります CLID & CNAM の機能をサポートし、値の両方の最新レコードを提供するような終端の通信事業者の責任です。</span><span class="sxs-lookup"><span data-stu-id="e4c6d-110">CLID & CNAM transmission is the responsibility of the terminating carrier insofar as the terminating carrier must support CLID & CNAM functionality as well as provide up to date records for both values.</span></span> <span data-ttu-id="e4c6d-111">呼び出しを発信するときに Microsoft が CLID 値に確実に提供しますが、これらの値が保つことができませんそのままの状態、中間のキャリアまたは終端のキャリアを通過すると。</span><span class="sxs-lookup"><span data-stu-id="e4c6d-111">Microsoft reliably provides CLID values when originating calls, but those values may not be kept intact once they pass through an intermediary carrier or the terminating carrier.</span></span> <span data-ttu-id="e4c6d-112">残念ながら、CLID 値は、変更またはを省略すると、中間または末尾のキャリアでは切り捨てられ、イベント、マイクロソフトには、公衆電話網では、このような問題を修正するをほとんどの型がありません。</span><span class="sxs-lookup"><span data-stu-id="e4c6d-112">Unfortunately, in the event the CLID value is changed, omitted or truncated by the intermediary or terminating carrier, Microsoft has little to no recourse in correcting such problems in the public telephone network.</span></span>

<span data-ttu-id="e4c6d-113">CNAM で不整合への可能性が米国の場合のように権限を持つデータベースに CNAM の情報を更新する中間または末尾のキャリアに遅延が発生します。</span><span class="sxs-lookup"><span data-stu-id="e4c6d-113">Inconsistencies in CNAM can be caused by delays in intermediate or terminating carriers refreshing CNAM info in authoritative databases as in the case of the United States.</span></span> <span data-ttu-id="e4c6d-114">国に CNAM の権限を持つデータベースが存在しない、個々 のキャリア ・ プラクティスも問題があります CNAM の情報の整合性を呼び出しに到着したとします。</span><span class="sxs-lookup"><span data-stu-id="e4c6d-114">In countries where there is no authoritative database for CNAM, individual carrier practices can also cause problems with CNAM information arriving in tact with the call.</span></span> <span data-ttu-id="e4c6d-115">Microsoft 現在サポートしていません CNAM の発信元の情報、米国以外の国々 で。」</span><span class="sxs-lookup"><span data-stu-id="e4c6d-115">Microsoft currently does not support originating CNAM information in countries other than the United States."</span></span>

## <a name="related-topics"></a><span data-ttu-id="e4c6d-116">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e4c6d-116">Related topics</span></span>


