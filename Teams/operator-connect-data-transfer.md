---
title: オペレーター サービスを利用した運送業者と Microsoft の間でのConnect
author: MicrosoftHeidi
ms.author: heidip
ms.reviewer: alaina, creager
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 通信事業者と Microsoft との間でのデータまたは情報の転送に関する特定のプライバシー情報(特にオペレーターとオペレーターとの関係) Connect。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 78f602fcacf6ee2f9a29393aa9a4d6b860251e2d
ms.sourcegitcommit: 39d26edd43b6066d5a6dee2a5ad1354a1e560a0d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694565"
---
# <a name="data-transfers-between-carriers-and-microsoft-for-operator-connect"></a><span data-ttu-id="0348d-103">オペレーター サービスを利用した運送業者と Microsoft の間でのConnect</span><span class="sxs-lookup"><span data-stu-id="0348d-103">Data transfers between carriers and Microsoft for Operator Connect</span></span>

## <a name="provisioned-and-assigned-numbers"></a><span data-ttu-id="0348d-104">プロビジョニング済みおよび割り当て済み番号</span><span class="sxs-lookup"><span data-stu-id="0348d-104">Provisioned and Assigned Numbers</span></span>

<span data-ttu-id="0348d-105">オペレーター Connect プログラムが適切に機能することを保証するために、Microsoft は、Teams 管理センター内で割り当てられている携帯電話会社の電話番号と、その電話番号の SIP URI (Session Initiation Protocol Uniform Resource Identifiers) を API を通じて、各参加している通信事業者に通知します。</span><span class="sxs-lookup"><span data-stu-id="0348d-105">To ensure the proper functioning of the Operator Connect program, Microsoft will inform each participating carrier, through an API, which of the carrier’s phone numbers have been assigned within the Teams admin center, as well as the SIP URI (Session Initiation Protocol Uniform Resource Identifiers) of that phone number.</span></span>

## <a name="call-detail-records-and-quality-data"></a><span data-ttu-id="0348d-106">通話の詳細レコードと品質データ</span><span class="sxs-lookup"><span data-stu-id="0348d-106">Call Detail Records and Quality Data</span></span>

<span data-ttu-id="0348d-107">Microsoft は、API を通じて各参加通信事業者に通話の詳細レコードと品質データを提供します。</span><span class="sxs-lookup"><span data-stu-id="0348d-107">Microsoft will provide call detail records and quality data to each participating carrier through an API.</span></span> <span data-ttu-id="0348d-108">これは、Microsoft と通信事業者がトラブルシューティングを実行し、サービスの適切な機能を確保するために必要です。</span><span class="sxs-lookup"><span data-stu-id="0348d-108">This is necessary for Microsoft and the carrier to perform troubleshooting and ensure the proper functioning of the service.</span></span>

## <a name="call-duration-data"></a><span data-ttu-id="0348d-109">通話時間データ</span><span class="sxs-lookup"><span data-stu-id="0348d-109">Call Duration Data</span></span>

<span data-ttu-id="0348d-110">各通信事業者は、API を通じて、お客様がサービスを使用して行った通話のMicrosoft Teams。</span><span class="sxs-lookup"><span data-stu-id="0348d-110">Each carrier will provide to Microsoft, through an API, the duration of calls placed by their customers using Microsoft Teams.</span></span> <span data-ttu-id="0348d-111">Microsoft は、これらのレコードを使用して、お客様に使用状況情報を提供し、Microsoft のレコードが運送業者のレコードと一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0348d-111">Microsoft will use these records to provide customers with usage information and to ensure our records are consistent with that of the carrier.</span></span> <span data-ttu-id="0348d-112">Microsoft は、適用される法令および Microsoft のプライバシーに関する声明に従って、これらのレコードを保存および処理します。</span><span class="sxs-lookup"><span data-stu-id="0348d-112">Microsoft will store and process these records in compliance with applicable laws and regulations, as well as the Microsoft Privacy Statement.</span></span>

<span data-ttu-id="0348d-113">詳細については、「キャリア コーチを購入、構成、有効化する[」を参照Microsoft Teams](career-coach.md)</span><span class="sxs-lookup"><span data-stu-id="0348d-113">For more information: [Purchase, configure, and enable Career Coach for Microsoft Teams](career-coach.md)</span></span>
