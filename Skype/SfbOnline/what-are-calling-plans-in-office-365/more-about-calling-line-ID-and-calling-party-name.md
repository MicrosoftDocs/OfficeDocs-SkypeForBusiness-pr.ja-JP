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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 新しい電話番号のポート注文ウィザードを使用するときに、アカウントを変更できる認証済みユーザーを追加する必要がある理由について説明します。
ms.openlocfilehash: e77176b978cb33df2bc4efebae11fb218c3932a5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34293768"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a><span data-ttu-id="a9374-103">発信回線 ID と発信者名の詳細</span><span class="sxs-lookup"><span data-stu-id="a9374-103">More about Calling Line ID and Calling Party Name</span></span>

<span data-ttu-id="a9374-104">CallerID は、一般的に参照されているため、実際には2つのユーザーに対して識別できる情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a9374-104">CallerID, as it is typically referred to, actually consists of two user-facing identifiable pieces of information:</span></span>
    - <span data-ttu-id="a9374-105">電話番号 (通常は CLID または通話回線 ID とも呼ばれます)</span><span class="sxs-lookup"><span data-stu-id="a9374-105">A phone number (typically referred to as CLID or calling line ID)</span></span> 
    - <span data-ttu-id="a9374-106">発信者の名前 (通常は CNAM とも呼ばれます) で、最大15文字の長さを指定できます。</span><span class="sxs-lookup"><span data-stu-id="a9374-106">Calling party name (typically referred to as CNAM) which can be up to 15 characters in length.</span></span> 

<span data-ttu-id="a9374-107">通話が発信されると、CLID (電話番号) は送信先の電話会社 (終了キャリアとも呼ばれます) にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="a9374-107">When a call is made, the CLID (phone number) is routed to the destination's carrier (also known as the terminating carrier).</span></span> <span data-ttu-id="a9374-108">この方法では、通話の CNAM info が通話と共にルーティングされないことがあります。これは、国が CNAM を実装しているかどうかによって異なります (すべての場合)。</span><span class="sxs-lookup"><span data-stu-id="a9374-108">The CNAM info for the call may or may not be routed with the call as this depends on how the country has implemented CNAM (if at all).</span></span> <span data-ttu-id="a9374-109">CNAM での通話の信頼性は、通話を発信する国と航空会社によって異なります。中継または終了キャリアとして通話を処理します。</span><span class="sxs-lookup"><span data-stu-id="a9374-109">The reliability of CNAM delivery with the call varies depending on the country and carriers which handle the call either as an intermediary and/or a terminating carrier.</span></span> 

<span data-ttu-id="a9374-110">CLID & CNAM 伝送は、終了キャリアが CLID & CNAM 機能をサポートしており、両方の値の最新のレコードを提供している必要があるため、終了キャリアの責任となります。</span><span class="sxs-lookup"><span data-stu-id="a9374-110">CLID & CNAM transmission is the responsibility of the terminating carrier insofar as the terminating carrier must support CLID & CNAM functionality as well as provide up to date records for both values.</span></span> <span data-ttu-id="a9374-111">Microsoft は、発信時に CLID の値を提供していますが、中継業者または終了キャリアを通過すると、それらの値がそのまま保持されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="a9374-111">Microsoft reliably provides CLID values when originating calls, but those values may not be kept intact once they pass through an intermediary carrier or the terminating carrier.</span></span> <span data-ttu-id="a9374-112">残念ながら、CLID 値が変更された場合や、中継業者または終了キャリアによって省略または切り捨てられた場合、Microsoft は、このような問題を解決するために、公衆電話網の問題を修正することはほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="a9374-112">Unfortunately, in the event the CLID value is changed, omitted or truncated by the intermediary or terminating carrier, Microsoft has little to no recourse in correcting such problems in the public telephone network.</span></span>

<span data-ttu-id="a9374-113">CNAM の不整合は、米国の場合と同様に、信頼できるデータベースの CNAM 情報を更新するときに、中間または終了キャリアで遅延が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a9374-113">Inconsistencies in CNAM can be caused by delays in intermediate or terminating carriers refreshing CNAM info in authoritative databases as in the case of the United States.</span></span> <span data-ttu-id="a9374-114">CNAM の権限を持つデータベースが存在しない国では、個々の運送業者の慣行によって、tact で着信した CNAM 情報に関する問題が発生することもあります。</span><span class="sxs-lookup"><span data-stu-id="a9374-114">In countries where there is no authoritative database for CNAM, individual carrier practices can also cause problems with CNAM information arriving in tact with the call.</span></span> <span data-ttu-id="a9374-115">現時点では、Microsoft は米国以外の国での CNAM 情報の送信をサポートしていません。」</span><span class="sxs-lookup"><span data-stu-id="a9374-115">Microsoft currently does not support originating CNAM information in countries other than the United States."</span></span>

## <a name="related-topics"></a><span data-ttu-id="a9374-116">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a9374-116">Related topics</span></span>


