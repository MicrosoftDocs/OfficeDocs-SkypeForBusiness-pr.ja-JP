---
title: EDU 向けの Microsoft Teams 低帯域幅ガイダンス
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: jesegher
description: EDU 向けの Microsoft Teams の記事は、低帯域幅に関連する会議やビデオの問題を解決するのに役立ちます。 親、教師、IT 管理者のいずれであっても、Teams のエクスペリエンスを向上できるオプションがあります。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 17520645f23500550c6bc991c9d25ad2f72b2b6e
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598426"
---
# <a name="help-for-low-bandwidth-situations-for-teams-for-edu"></a><span data-ttu-id="6e4de-104">EDU 向けの Teams の低帯域幅状況を解決するためのヘルプ</span><span class="sxs-lookup"><span data-stu-id="6e4de-104">Help for low-bandwidth situations for Teams for EDU</span></span>

<span data-ttu-id="6e4de-105">Microsoft Teams で作業する際にパフォーマンスに影響を与える可能性のあるネットワーク要素は多数あります。</span><span class="sxs-lookup"><span data-stu-id="6e4de-105">There are numerous network elements when it comes to working with Microsoft Teams that can affect performance.</span></span> <span data-ttu-id="6e4de-106">低帯域幅は、制御が難しいと感じる要素の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="6e4de-106">Low bandwidth is one of the situations that can feel entirely out of your control.</span></span> <span data-ttu-id="6e4de-107">次の状況について考えます。</span><span class="sxs-lookup"><span data-stu-id="6e4de-107">Consider the following situations:</span></span>

- <span data-ttu-id="6e4de-108">学校の低速インターネット接続。</span><span class="sxs-lookup"><span data-stu-id="6e4de-108">A low-speed internet connection for the school.</span></span>
- <span data-ttu-id="6e4de-109">1 人以上の学生の低速インターネット接続。</span><span class="sxs-lookup"><span data-stu-id="6e4de-109">A low-speed internet connection for one or more students.</span></span>
- <span data-ttu-id="6e4de-110">1 日のうち、領域内におけるネットワーク使用量が原因で低帯域幅になる時間帯。</span><span class="sxs-lookup"><span data-stu-id="6e4de-110">Times of the day when there's low bandwidth because of network usage in an area.</span></span>
- <span data-ttu-id="6e4de-111">学校または学生のどちらに対してでもないローカルの停止が原因で生じ、パフォーマンスに影響を与える低帯域幅期間。</span><span class="sxs-lookup"><span data-stu-id="6e4de-111">Low-bandwidth periods because of outages local to neither the school nor to students, but, which affect performance nonetheless.</span></span>
- <span data-ttu-id="6e4de-112">低帯域幅の問題であるかのように見える帯域幅以外の問題 (ハードウェアの問題など)。</span><span class="sxs-lookup"><span data-stu-id="6e4de-112">Non-bandwidth issues (for example, issues with hardware) that masquerade as low-bandwidth issues.</span></span>

<span data-ttu-id="6e4de-113">この記事では、低帯域幅の問題が発生した場合に、さまざまな Times アクティビティに応じて実行するベスト プラクティスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6e4de-113">This article will give you best practices to follow for various Teams activities when you're faced with a low-bandwidth issue.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6e4de-114">こちらの「[Microsoft Teams のメモリ使用方法](teams-memory-usage-perf.md)」の情報もご覧ください。低帯域幅の問題以外に、デバイスのリソースに問題が生じている場合もあります。</span><span class="sxs-lookup"><span data-stu-id="6e4de-114">There's information here on [How Microsoft Teams uses memory](teams-memory-usage-perf.md), because in addition to low bandwidth problems, you may be having resource issues on your device.</span></span> <span data-ttu-id="6e4de-115">Microsoft Teams のネットワーク ガイダンスについては、「[Microsoft Teams 用に組織のネットワークを準備する](prepare-network.md)」をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="6e4de-115">If you're looking for network guidance for Microsoft Teams, review [Prepare your organization's network for Microsoft Teams](prepare-network.md).</span></span>

## <a name="resolving-low-bandwidth-issues-for-admins"></a><span data-ttu-id="6e4de-116">IT 管理者として低帯域幅の問題を解決する</span><span class="sxs-lookup"><span data-stu-id="6e4de-116">Resolving low-bandwidth issues for Admins</span></span>

<span data-ttu-id="6e4de-117">IT 管理者として銘記しておくべき重要な点として、広範におよぶ低帯域幅の問題を迅速に解決できる解決策があっても、慎重に考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e4de-117">The important thing to remember, as an IT Admin, is that while you have solutions for low-bandwidth issues that are wide-spread that will resolve problems quickly, solutions should be considered carefully.</span></span> <span data-ttu-id="6e4de-118">これは、問題によっては教師または学生/親のレベルにおいてでさえもより狭い範囲に注目して解決できる場合があるためです。</span><span class="sxs-lookup"><span data-stu-id="6e4de-118">Some issues may be able to resolve with a more narrow focus taken at the educator or even the student/parent level.</span></span>

<span data-ttu-id="6e4de-119">つまり、大勢の学生たちに関して低帯域幅の問題が生じている場合には IT 管理者として対処するのが適切ですし、学生/教師レベルで対処しても有効でない場合にも適切であると言えます。</span><span class="sxs-lookup"><span data-stu-id="6e4de-119">In short, if the low-bandwidth issue occurs for a wide group of students, taking action as an IT Admin makes sense, and it also makes sense if the actions taken at the student/educator level haven't been helpful.</span></span>

> [!NOTE]
> <span data-ttu-id="6e4de-120">時間があるときに、「[QoE のレビュー ガイド](quality-of-experience-review-guide.md)」を読むと役立ちます (EDU 特有の情報ではありませんが、有用です)。</span><span class="sxs-lookup"><span data-stu-id="6e4de-120">If you've got the time to invest, the [Quality of Experience Review Guide](quality-of-experience-review-guide.md) is a worthwhile read (this is not EDU-specific, but it will still have valuable information).</span></span> <span data-ttu-id="6e4de-121">このガイドは、経験豊富な IT 管理者が教師と学生のエクスペリエンスの詳細を把握するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6e4de-121">This guide will allow experienced IT Admins to go in-depth on the experience for their educators and students.</span></span>

### <a name="meetings-and-video"></a><span data-ttu-id="6e4de-122">会議とビデオ</span><span class="sxs-lookup"><span data-stu-id="6e4de-122">Meetings and video</span></span>

<span data-ttu-id="6e4de-123">低帯域幅の問題に関してまず注意を向ける必要があるのは会議、特に会議のビデオです。</span><span class="sxs-lookup"><span data-stu-id="6e4de-123">A primary focus for low-bandwidth issues is meetings; specifically, video in meetings.</span></span> <span data-ttu-id="6e4de-124">教育機関向けの設定での最適な会議エクスペリエンスに関する問題が学生または教師によって報告された場合、IT 管理者は問題を扱うときに以下の操作を検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e4de-124">An IT Admin should consider the actions below when dealing with issues reported by students or educators in regard to having the best meeting experience in an educational setting.</span></span>

#### <a name="meeting-policies"></a><span data-ttu-id="6e4de-125">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="6e4de-125">Meeting policies</span></span>

<span data-ttu-id="6e4de-126">会議に関して、低帯域幅の状況で最も注意を向けるべき領域の 1 つはビデオに関連する事柄です。</span><span class="sxs-lookup"><span data-stu-id="6e4de-126">Regarding meetings, one of the most concerning areas for low-bandwidth situations has to do with videos.</span></span> <span data-ttu-id="6e4de-127">Teams が検出された帯域幅を自動的に拡大縮小できるだけでなく、IT 管理者は開催者またはユーザー レベルで、あるいはその両方のレベルでポリシー オプションを設定できます。</span><span class="sxs-lookup"><span data-stu-id="6e4de-127">In addition to Teams being able to scale to detected bandwidth automatically, you as an IT Admin have policy options you can set at the per-organizer and/or per-user level.</span></span> <span data-ttu-id="6e4de-128">このオプションによって、指定の時間に作業に使用する必要がある帯域幅で最適なエクスペリエンスをすべてのユーザーに提供できます。</span><span class="sxs-lookup"><span data-stu-id="6e4de-128">These options allow you to give everyone the best experience in light of the bandwidth they have to work with at a given time.</span></span>

<span data-ttu-id="6e4de-129">ポリシーで設定できる機能には、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="6e4de-129">Some of the things you can set via policy include:</span></span>

- <span data-ttu-id="6e4de-130">ビデオを完全に無効にして、だれも有効にできないようにします。</span><span class="sxs-lookup"><span data-stu-id="6e4de-130">Disabling video altogether, so no one could enable it.</span></span>
- <span data-ttu-id="6e4de-131">メディア ビット レート (この設定はユーザー単位で設定されます)。</span><span class="sxs-lookup"><span data-stu-id="6e4de-131">Media bit rate (this setting is set per-user).</span></span>

<span data-ttu-id="6e4de-132">オプションおよび会議とビデオに設定する必要があるポリシーの詳細については、「[会議ポリシーの設定 - オーディオとビデオ](meeting-policies-audio-and-video.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e4de-132">To learn more about your options, and to walk through the specifics of what policies you'd need to set for meetings and video, check out [Meeting policy settings in Teams: Audio and video](meeting-policies-audio-and-video.md).</span></span>

#### <a name="screen-sharing-policies"></a><span data-ttu-id="6e4de-133">画面共有ポリシー</span><span class="sxs-lookup"><span data-stu-id="6e4de-133">Screen sharing policies</span></span>

<span data-ttu-id="6e4de-134">別の例では、教師が取り上げている学習内容に関連するアプリケーションにのみ共有を限定する必要があるにもかかわらず、学生に自分の画面全体を共有している場合があります。</span><span class="sxs-lookup"><span data-stu-id="6e4de-134">In other cases, educators may be sharing their entire screen to students, when sharing should be limited to an application relevant to the lesson being taught.</span></span> <span data-ttu-id="6e4de-135">この設定は、教師が個別に選択するよりも適している場合には、ポリシーで設定できます。</span><span class="sxs-lookup"><span data-stu-id="6e4de-135">This setting can also be set via policy, if that's a more desirable way to do it than to have educators making that choice individually.</span></span>

<span data-ttu-id="6e4de-136">ポリシー設定を使用して画面共有を制限するうえで実行できる優れたアイデアについては、「[会議ポリシーの設定 - オーディオとビデオ](meeting-policies-audio-and-video.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e4de-136">For a good idea of what you can do about limiting screen sharing via policy settings, check out [Meeting policy settings in Teams: Audio and video](meeting-policies-audio-and-video.md).</span></span>

#### <a name="dial-in-number-for-meetings"></a><span data-ttu-id="6e4de-137">会議用のダイヤルイン番号</span><span class="sxs-lookup"><span data-stu-id="6e4de-137">Dial-in number for meetings</span></span>

<span data-ttu-id="6e4de-138">一部の学生にとっては、教室セッションにダイヤルインするほうが簡単な場合があります。</span><span class="sxs-lookup"><span data-stu-id="6e4de-138">It may be easier for some students to attempt to dial in to some classroom sessions.</span></span> <span data-ttu-id="6e4de-139">Teams 会議用のダイヤルイン番号を提供し、問題が生じている学生がビデオ会議に参加する代わりに電話をかけられるようにできます。</span><span class="sxs-lookup"><span data-stu-id="6e4de-139">You can provide a dial-in number for Teams meetings, so students with issues can phone in as an alternative to attending a video meeting.</span></span>

<span data-ttu-id="6e4de-140">この点の詳細については、「[Microsoft Teams で招待状に含まれている電話番号を設定する](set-the-phone-numbers-included-on-invites-in-teams.md)」を参照できます。</span><span class="sxs-lookup"><span data-stu-id="6e4de-140">For more information on this, you can read [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span>

## <a name="low-bandwidth-scenarios-as-an-educator"></a><span data-ttu-id="6e4de-141">教師としての低帯域幅のシナリオ</span><span class="sxs-lookup"><span data-stu-id="6e4de-141">Low-bandwidth scenarios as an educator</span></span>

<span data-ttu-id="6e4de-142">教師には、低帯域幅の問題を解決するための手順を実行する権限が与えられている必要があり、以下のような状況では IT 管理によるアクションが優れた選択となることがあります。</span><span class="sxs-lookup"><span data-stu-id="6e4de-142">Educators should feel empowered to take steps to resolve low-bandwidth issues, and may be a superior choice to IT Admin action in the following situations:</span></span>

- <span data-ttu-id="6e4de-143">問題が間欠的または一時的に発生する場合。</span><span class="sxs-lookup"><span data-stu-id="6e4de-143">If the problem is intermittent, or relatively transitory.</span></span>
- <span data-ttu-id="6e4de-144">問題が生じるのが一日の特定の時刻であると予期できる場合や、低帯域幅の期間が予測可能である場合。</span><span class="sxs-lookup"><span data-stu-id="6e4de-144">If there is a specific time of the day you can anticipate there being an issue, or the low bandwidth period has some predictability to it.</span></span>

<span data-ttu-id="6e4de-145">このような場合は、何らかの措置を講じることができます。</span><span class="sxs-lookup"><span data-stu-id="6e4de-145">In these situations, you can take some actions.</span></span>

<span data-ttu-id="6e4de-146">詳細については、「[帯域幅が少なくなったときに学業に Teams を使用する](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e4de-146">For more information, check out [Use Teams for schoolwork when bandwidth is low](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262).</span></span>

## <a name="low-bandwidth-scenarios-as-a-parent-or-student"></a><span data-ttu-id="6e4de-147">親または学生としての低帯域幅のシナリオ</span><span class="sxs-lookup"><span data-stu-id="6e4de-147">Low-bandwidth scenarios as a parent or student</span></span>

<span data-ttu-id="6e4de-148">帯域幅の問題が学生側にある可能性があり、教師と積極的に話し合う必要がある状況も存在します (たとえば、多数の学生が問題なくビデオ授業を視聴できるものの、少数の学生は困難であるという状況などです)。</span><span class="sxs-lookup"><span data-stu-id="6e4de-148">There are also situations, and you should proactively discuss them with your educators, where the bandwidth problem may be on the student's side (for example, a large number of students are able to watch the video lessons without issue, but a small number of students have difficulties).</span></span>

<span data-ttu-id="6e4de-149">多くの親にとってこうした問題のトラブルシューティングを行えると期待するのは実際的ではありません。</span><span class="sxs-lookup"><span data-stu-id="6e4de-149">It's not reasonable to expect many parents to be able to troubleshoot these issues.</span></span> <span data-ttu-id="6e4de-150">低帯域幅の問題は、学生や親の制御下にないという可能性もあります (自宅が高帯域幅にアクセスできない、大勢のユーザーが近くにいて帯域幅を消費しているため実行できる事柄が制限される、インターネットが不安定になっているなどの状況が生じ得ます)。</span><span class="sxs-lookup"><span data-stu-id="6e4de-150">Low-bandwidth issues may be out of a student or parent's control (their home may not have access to high bandwidth, they may have numerous people in their immediate area consuming bandwidth and affecting what they can do, there may be internet instability, and so on).</span></span>

<span data-ttu-id="6e4de-151">親と学生向けに「[帯域幅が少なくなったときに学業に Teams を使用する](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262)」の記事でガイダンスを提供しています。何らかの問題が生じている場合には、このガイダンスを確認し、推奨内容を試してください。</span><span class="sxs-lookup"><span data-stu-id="6e4de-151">We've put together guidance in our [Use Teams for schoolwork when bandwidth is low](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262) article for parents and students as well, you can review and try these recommendations if you're having any problems.</span></span>