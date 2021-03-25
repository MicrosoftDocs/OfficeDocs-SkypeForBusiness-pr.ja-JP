---
title: サポートされていないブラウザーでの Microsoft Teams 会議
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
MS.collection:
- M365-collaboration
ms.reviewer: nakulm
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: サポートされていないブラウザーでの Teams でのオーディオとビデオのサポートについて学習します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 83617628fe04140c45b005e993d95eac34c6f8bd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121315"
---
# <a name="microsoft-teams-meetings-on-unsupported-browsers"></a><span data-ttu-id="113f1-103">サポートされていないブラウザーでの Microsoft Teams 会議</span><span class="sxs-lookup"><span data-stu-id="113f1-103">Microsoft Teams meetings on unsupported browsers</span></span>

<span data-ttu-id="113f1-104">Internet Explorer 11、Safari、Firefox などの一部のブラウザーは Microsoft Teams Web アプリをサポートしていますが、Teams の通話および会議機能の一部はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="113f1-104">Some browsers, such as Internet Explorer 11, Safari, and Firefox, support the Microsoft Teams web app but don't support some of the Teams calling and meeting features.</span></span> <span data-ttu-id="113f1-105">この制限を回避するために、Teams Web アプリを使用すると、ユーザーは PSTN 接続を介して音声を受信し、表示されたコンテンツ (画面共有) を表示速度を低下して表示できます。</span><span class="sxs-lookup"><span data-stu-id="113f1-105">To work around this limitation, the Teams web app lets users receive audio through a PSTN connection and lets them view presented content (screen share) at a reduced display rate.</span></span>

> [!Note]
> <span data-ttu-id="113f1-106">Microsoft 365 のアプリとサービスは、2021 年 8 月 17 日から Internet Explorer 11 をサポートしない予定です (Microsoft Teams では、2020 年 11 月 30 日から Internet Explorer 11 以前はサポートされていません)。</span><span class="sxs-lookup"><span data-stu-id="113f1-106">Microsoft 365 apps and services will not support Internet Explorer 11 starting August 17, 2021 (Microsoft Teams will not support Internet Explorer 11 earlier, starting  November 30, 2020).</span></span> <span data-ttu-id="113f1-107">[詳細情報を参照してください](https://aka.ms/AA97tsw)。</span><span class="sxs-lookup"><span data-stu-id="113f1-107">[Learn more](https://aka.ms/AA97tsw).</span></span> <span data-ttu-id="113f1-108">Internet Explorer 11 は、サポート対象のブラウザーとして残ることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="113f1-108">Please note that Internet Explorer 11 will remain a supported browser.</span></span> <span data-ttu-id="113f1-109">Internet Explorer 11 は Windows オペレーティング システムのコンポーネントであり[](/lifecycle/faq/internet-explorer-microsoft-edge)、インストールされている製品のライフサイクル ポリシーに従います。</span><span class="sxs-lookup"><span data-stu-id="113f1-109">Internet Explorer 11 is a component of the Windows operating system and [follows the Lifecycle Policy](/lifecycle/faq/internet-explorer-microsoft-edge) for the product on which it is  installed.</span></span>

<span data-ttu-id="113f1-110">Teams がサポートされていないブラウザーを検出すると、問題とセッションの制限を説明するメッセージが自動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="113f1-110">When Teams detects an unsupported browser, it automatically displays a message explaining the issue and the session limitations.</span></span> <span data-ttu-id="113f1-111">このメッセージには、Teams がユーザーに通話を呼び出せするように呼び出し元の番号を残すようユーザーに指示したり、会議出席依頼に含まれる電話会議番号に電話するようにユーザーに指示したりなど、会議の音声にアクセスする手順が示されます。</span><span class="sxs-lookup"><span data-stu-id="113f1-111">The message provides further instructions for accessing the meeting audio, such as advising the user to leave a call back number so that Teams can call the user, or instructing the user to call the conference number included in the meeting invitation.</span></span> <span data-ttu-id="113f1-112">このメッセージでは、Teams デスクトップ クライアントをダウンロードして [使用し、Teams](https://teams.microsoft.com/downloads) の完全なエクスペリエンスを得る方法もユーザーに推奨されます。</span><span class="sxs-lookup"><span data-stu-id="113f1-112">The message also encourages the user to download and use the [Teams desktop client](https://teams.microsoft.com/downloads) for the full Teams experience.</span></span>

<span data-ttu-id="113f1-113">PSTN が利用できない場合、ユーザーには会議にアクセスする手順が表示され、会議に参加できません。</span><span class="sxs-lookup"><span data-stu-id="113f1-113">If PSTN is unavailable, the user won't see the instructions for accessing the meeting and won't be able to join the meeting.</span></span>

## <a name="browser-limitations"></a><span data-ttu-id="113f1-114">ブラウザーの制限事項</span><span class="sxs-lookup"><span data-stu-id="113f1-114">Browser limitations</span></span>

<span data-ttu-id="113f1-115">サポートされていないブラウザーで Teams Web アプリを使用するユーザーには、次の制限があります。</span><span class="sxs-lookup"><span data-stu-id="113f1-115">People who use the Teams web app on unsupported browsers will experience the following limitations:</span></span>

- <span data-ttu-id="113f1-116">音声は PSTN 接続でのみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="113f1-116">Audio is available through a PSTN connection only.</span></span> <span data-ttu-id="113f1-117">ユーザーは自分のマイクを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="113f1-117">Users can't use their microphone.</span></span>
- <span data-ttu-id="113f1-118">ユーザーはカメラを共有したり、他の参加者のビデオを表示したりできないが、画像ベースの画面共有を通じて表示されたコンテンツを表示できる。</span><span class="sxs-lookup"><span data-stu-id="113f1-118">Users can't share their camera or see other participants' videos but can view presented content through image-based screen sharing.</span></span>
- <span data-ttu-id="113f1-119">ユーザーは自分の画面を共有できないが、別の会議参加者が共有している画面を表示できる。</span><span class="sxs-lookup"><span data-stu-id="113f1-119">Users can't share their screen, although they can see a screen that another meeting participant shares.</span></span>
- <span data-ttu-id="113f1-120">ユーザーは、画面共有セッション中に制御を受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="113f1-120">Users can't take control during a screen sharing session.</span></span>
- <span data-ttu-id="113f1-121">ユーザーは着信通話通知を受信しない。</span><span class="sxs-lookup"><span data-stu-id="113f1-121">Users won't receive incoming call notifications.</span></span>
- <span data-ttu-id="113f1-122">通話が中断された場合、会議は自動的に再接続されません。</span><span class="sxs-lookup"><span data-stu-id="113f1-122">If the call is interrupted, the meeting won't automatically reconnect.</span></span>
- <span data-ttu-id="113f1-123">ユーザーが会議を開始できない。</span><span class="sxs-lookup"><span data-stu-id="113f1-123">Users can't start meetings.</span></span>

<span data-ttu-id="113f1-124">Teams でのブラウザー サポートの詳細については、「Teams の制限と [仕様」を参照してください](./limits-specifications-teams.md#browsers)。</span><span class="sxs-lookup"><span data-stu-id="113f1-124">For more information about browser support in Teams, see [Limits and specifications for Teams](./limits-specifications-teams.md#browsers).</span></span>

## <a name="related-topics"></a><span data-ttu-id="113f1-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="113f1-125">Related topics</span></span>

- [<span data-ttu-id="113f1-126">サポートされていないブラウザーで Teams 会議に参加する</span><span class="sxs-lookup"><span data-stu-id="113f1-126">Join a Teams meeting on an unsupported browser</span></span>](https://support.office.com/article/daafdd3c-ac7a-4855-871b-9113bad15907)