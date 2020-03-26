---
title: Microsoft Teams でサポートされていないブラウザーに関する会議
author: lanachin
ms.author: v-lanac
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
description: チームがサポートされていないブラウザーで音声とビデオをサポートする方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1dfd2ba704aa2428555dd126c506e1673a120b72
ms.sourcegitcommit: 46b15a11755a89526be2a0b20befad61c628cdb4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2020
ms.locfileid: "42955716"
---
# <a name="microsoft-teams-meetings-on-unsupported-browsers"></a><span data-ttu-id="91730-103">Microsoft Teams でサポートされていないブラウザーに関する会議</span><span class="sxs-lookup"><span data-stu-id="91730-103">Microsoft Teams meetings on unsupported browsers</span></span>

<span data-ttu-id="91730-104">Internet Explorer 11、Safari、Firefox などの一部のブラウザーでは、Microsoft Teams web app がサポートされていますが、チームの通話機能と会議機能の一部はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="91730-104">Some browsers, such as Internet Explorer 11, Safari, and Firefox, support the Microsoft Teams web app but don't support some of the Teams calling and meeting features.</span></span> <span data-ttu-id="91730-105">この制限を回避するために、Teams web app では、ユーザーが PSTN 接続を使用して音声を受信できるようにし、表示されたコンテンツ (スクリーン共有) を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="91730-105">To work around this limitation, the Teams web app lets users receive audio through a PSTN connection and lets them view presented content (screen share) at a reduced display rate.</span></span>

<span data-ttu-id="91730-106">チームでサポートされていないブラウザーが検出されると、その問題とセッションの制限を説明するメッセージが自動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="91730-106">When Teams detects an unsupported browser, it automatically displays a message explaining the issue and the session limitations.</span></span> <span data-ttu-id="91730-107">このメッセージには、会議の音声にアクセスするための詳しい手順が記載されています。たとえば、チームがユーザーに電話をかけたり、会議の出席依頼に記載されている電話会議の電話番号に電話をかけたりするようにユーザーに指示することができます。</span><span class="sxs-lookup"><span data-stu-id="91730-107">The message provides further instructions for accessing the meeting audio, such as advising the user to leave a call back number so that Teams can call the user, or instructing the user to call the conference number included in the meeting invitation.</span></span> <span data-ttu-id="91730-108">また、このメッセージにより、teams の[デスクトップクライアント](https://teams.microsoft.com/downloads)をダウンロードして、チームのすべてのエクスペリエンスに使用することが奨励されます。</span><span class="sxs-lookup"><span data-stu-id="91730-108">The message also encourages the user to download and use the [Teams desktop client](https://teams.microsoft.com/downloads) for the full Teams experience.</span></span>

<span data-ttu-id="91730-109">PSTN を使用できない場合は、会議にアクセスするための手順が表示されず、会議に参加できません。</span><span class="sxs-lookup"><span data-stu-id="91730-109">If PSTN is unavailable, the user won't see the instructions for accessing the meeting and won't be able to join the meeting.</span></span>

## <a name="browser-limitations"></a><span data-ttu-id="91730-110">ブラウザーの制限</span><span class="sxs-lookup"><span data-stu-id="91730-110">Browser limitations</span></span>

<span data-ttu-id="91730-111">サポートされていないブラウザーで Teams web app を使用しているユーザーには、次の制限があります。</span><span class="sxs-lookup"><span data-stu-id="91730-111">People who use the Teams web app on unsupported browsers will experience the following limitations:</span></span>

- <span data-ttu-id="91730-112">オーディオは PSTN 接続のみで利用できます。</span><span class="sxs-lookup"><span data-stu-id="91730-112">Audio is available through a PSTN connection only.</span></span> <span data-ttu-id="91730-113">ユーザーはマイクを使用できません。</span><span class="sxs-lookup"><span data-stu-id="91730-113">Users can't use their microphone.</span></span>
- <span data-ttu-id="91730-114">ユーザーはカメラを共有したり、他の参加者のビデオを表示したりすることはできませんが、イメージベースの画面共有を通じて表示されるコンテンツを表示できます。</span><span class="sxs-lookup"><span data-stu-id="91730-114">Users can't share their camera or see other participants' videos but can view presented content through image-based screen sharing.</span></span>
- <span data-ttu-id="91730-115">ユーザーは画面を共有することはできませんが、別の会議出席者が共有している画面を表示できます。</span><span class="sxs-lookup"><span data-stu-id="91730-115">Users can't share their screen, although they can see a screen that another meeting participant shares.</span></span>
- <span data-ttu-id="91730-116">画面共有セッション中は、ユーザーが制御を行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="91730-116">Users can't take control during a screen sharing session.</span></span>
- <span data-ttu-id="91730-117">着信通話の通知を受信できません。</span><span class="sxs-lookup"><span data-stu-id="91730-117">Users won't receive incoming call notifications.</span></span>
- <span data-ttu-id="91730-118">通話が中断された場合、会議は自動的に再接続されません。</span><span class="sxs-lookup"><span data-stu-id="91730-118">If the call is interrupted, the meeting won't automatically reconnect.</span></span>
- <span data-ttu-id="91730-119">ユーザーは会議を開始できません。</span><span class="sxs-lookup"><span data-stu-id="91730-119">Users can't start meetings.</span></span>

<span data-ttu-id="91730-120">Teams でのブラウザーのサポートについて詳しくは、「 [teams の制限と仕様](/microsoftteams/limits-specifications-teams#browsers)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="91730-120">For more information about browser support in Teams, see [Limits and specifications for Teams](/microsoftteams/limits-specifications-teams#browsers).</span></span>

## <a name="related-topics"></a><span data-ttu-id="91730-121">Related topics</span><span class="sxs-lookup"><span data-stu-id="91730-121">Related topics</span></span>

- [<span data-ttu-id="91730-122">サポートされていないブラウザーで Teams 会議に参加する</span><span class="sxs-lookup"><span data-stu-id="91730-122">Join a Teams meeting on an unsupported browser</span></span>](https://support.office.com/article/daafdd3c-ac7a-4855-871b-9113bad15907)
