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
ms.openlocfilehash: 24f34ea2e65906c648081a019d6acf8a3f8a5cd5
ms.sourcegitcommit: e710bb8dbbd084912cbf509896515a674ab5e19f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2020
ms.locfileid: "43034077"
---
# <a name="help-for-low-bandwidth-situations-for-teams-for-edu"></a><span data-ttu-id="f628d-104">EDU 向けの Teams の低帯域幅状況を解決するためのヘルプ</span><span class="sxs-lookup"><span data-stu-id="f628d-104">Help for low bandwidth situations for Teams for EDU</span></span>

<span data-ttu-id="f628d-105">Microsoft Teams で作業する際にパフォーマンスに影響を与える可能性のあるネットワーク要素は多数あります。低帯域幅は、制御が難しいと感じる要素の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="f628d-105">There are a lot of network elements when it comes to working with Microsoft Teams that can affect performance, and low bandwidth is one of the situations that can feel entirely out of your control.</span></span> <span data-ttu-id="f628d-106">次の状況について検討しましょう。</span><span class="sxs-lookup"><span data-stu-id="f628d-106">Consider the following:</span></span>

- <span data-ttu-id="f628d-107">学校の低速インターネット接続。</span><span class="sxs-lookup"><span data-stu-id="f628d-107">A low-speed internet connection for the school.</span></span>
- <span data-ttu-id="f628d-108">1 人以上の学生の低速インターネット接続。</span><span class="sxs-lookup"><span data-stu-id="f628d-108">A low-speed internet connection for one or more students.</span></span>
- <span data-ttu-id="f628d-109">特定場所におけるネットワーク使用量が原因で低帯域幅になる一日の回数。</span><span class="sxs-lookup"><span data-stu-id="f628d-109">Times of the day when there is low bandwidth due to network usage in an area.</span></span>
- <span data-ttu-id="f628d-110">学校または学生のどちらに対してでもないローカルの停止が原因で生じ、パフォーマンスに影響を与える低帯域幅期間。</span><span class="sxs-lookup"><span data-stu-id="f628d-110">Low bandwidth periods due to outages local to neither the school nor to students, but which impact performance nonetheless.</span></span>
- <span data-ttu-id="f628d-111">低帯域幅の問題であるかのように見える帯域幅以外の問題 (ハードウェアの問題など)。</span><span class="sxs-lookup"><span data-stu-id="f628d-111">Non-bandwidth issues (for example, issues with hardware) that masquerade as low bandwidth issues.</span></span>

<span data-ttu-id="f628d-112">この記事では、低帯域幅の問題が発生した場合に、さまざまな Times アクティビティに応じて実行するベスト プラクティスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f628d-112">This article will give you best practices to follow for a variety of Teams activities when you're faced with a low-bandwidth issue.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f628d-113">こちらの「[Microsoft Teams のメモリ使用方法](teams-memory-usage-perf.md)」の情報もご覧ください。低帯域幅の問題以外に、デバイスのリソースに問題が生じている場合もあります。</span><span class="sxs-lookup"><span data-stu-id="f628d-113">There's information here on [How Microsoft Teams uses memory](teams-memory-usage-perf.md), because in addition to low bandwidth problems, you may be having resource issues on your device.</span></span> <span data-ttu-id="f628d-114">Microsoft Teams のネットワーク ガイダンスについては、「[Microsoft Teams 用に組織のネットワークを準備する](prepare-network.md)」をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="f628d-114">If you're looking for network guidance for Microsoft Teams, review [Prepare your organization's network for Microsoft Teams](prepare-network.md).</span></span>

## <a name="resolving-low-bandwidth-issues-for-itadmins"></a><span data-ttu-id="f628d-115">IT 管理者として低帯域幅の問題を解決する</span><span class="sxs-lookup"><span data-stu-id="f628d-115">Resolving low bandwidth issues for ITAdmins</span></span>

<span data-ttu-id="f628d-116">IT 管理者として銘記しておくべき重要な点として、広範におよぶ低帯域幅の問題を迅速に解決できる解決策があっても、問題によっては教師または学生/親のレベルにおいてでさえもより狭い範囲に注目して解決できる場合があるので、慎重に考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f628d-116">The important thing to remember, as an ITAdmin, is that while you have solutions for low bandwidth issues that are wide-spread that will resolve problems quickly, this should be considered carefully, as some issues may be able to resolved with a more narrow focus taken at the educator or even the student/parent level.</span></span>

<span data-ttu-id="f628d-117">つまり、大勢の学生たちに関して低帯域幅の問題が生じている場合には IT 管理者として対処するのが適切ですし、学生/教師レベルで対処しても有効でない場合にも適切であると言えます。</span><span class="sxs-lookup"><span data-stu-id="f628d-117">In short, if the low bandwidth issue occurs for a wide group of students, taking action as an ITAdmin makes sense, and it also makes sense if the actions taken at the student/educator level haven't been helpful.</span></span>

> [!NOTE]
> <span data-ttu-id="f628d-118">時間があるときに、「[QoE のレビュー ガイド](quality-of-experience-review-guide.md)」を読むと役立ちます (EDU 特有の情報ではありませんが、有用です)。</span><span class="sxs-lookup"><span data-stu-id="f628d-118">If you've got the time to invest, the [Quality of Experience Review Guide](quality-of-experience-review-guide.md) is a worthwhile read (this is not EDU-specific, but it will still have valuable information).</span></span> <span data-ttu-id="f628d-119">参照すると、経験豊富な IT 管理者は、教師と学生のエクスペリエンスの詳細を把握できます。</span><span class="sxs-lookup"><span data-stu-id="f628d-119">This will allow experienced ITAdmins to go in-depth on the experience for their educators and students.</span></span>

### <a name="meetings-and-video"></a><span data-ttu-id="f628d-120">会議とビデオ</span><span class="sxs-lookup"><span data-stu-id="f628d-120">Meetings and video</span></span>

<span data-ttu-id="f628d-121">低帯域幅の問題に関してまず注意を向ける必要があるのは、会議、特に会議のビデオです。</span><span class="sxs-lookup"><span data-stu-id="f628d-121">A primary focus for low bandwidth issues are meetings, and specifically video in meetings.</span></span> <span data-ttu-id="f628d-122">教育機関向けの設定で最適な会議エクスペリエンスにする点で、学生または教師によって報告される問題を扱うときに IT 管理者が考慮すべきアクションの一部を以下に取り上げます。</span><span class="sxs-lookup"><span data-stu-id="f628d-122">We have some of the actions below that an ITAdmin should consider when dealing with issues reported by students or educators in regard to having the best meeting experience in an educational setting.</span></span>

#### <a name="meeting-policies"></a><span data-ttu-id="f628d-123">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="f628d-123">Meeting policies</span></span>

<span data-ttu-id="f628d-124">会議に関して低帯域幅の状況で最も注意を向けるべき領域の 1 つはビデオに関連する事柄です。</span><span class="sxs-lookup"><span data-stu-id="f628d-124">In regards to meetings, one of the most concerning areas for low bandwidth situations has to do with videos.</span></span> <span data-ttu-id="f628d-125">幸いなことに Teams は検出された帯域幅を自動的に拡大縮小できるので、IT 管理者は開催者またはユーザーのレベルで、あるいはその両方のレベルでポリシー オプションを設定し、ユーザーが指定の時間に作業に使用する必要がある帯域幅で最適なエクスペリエンスを得られるようにすることが可能です。</span><span class="sxs-lookup"><span data-stu-id="f628d-125">Fortunately, in addition to Teams being able to scale to detected bandwidth automatically, you as an ITAdmin have policy options you can set at the per-organizer and/or per-user level to give everyone the best experience in light of the bandwidth they have to work with at a given time.</span></span>

<span data-ttu-id="f628d-126">ポリシーで設定できる機能には、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="f628d-126">Some of the things you can set via policy include:</span></span>

- <span data-ttu-id="f628d-127">ビデオを完全に無効にして、だれも有効にできないようにします。</span><span class="sxs-lookup"><span data-stu-id="f628d-127">Disabling video altogether, so no one could enable it.</span></span>
- <span data-ttu-id="f628d-128">メディア ビット レート (ユーザー単位で設定されます)。</span><span class="sxs-lookup"><span data-stu-id="f628d-128">Media bit rate (this is set per-user).</span></span>

<span data-ttu-id="f628d-129">オプションの詳細、および会議とビデオに設定する必要があるポリシーの詳細については、「[会議ポリシーの設定 - オーディオとビデオ](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#meeting-policy-settings---audio--video)」でご確認ください。</span><span class="sxs-lookup"><span data-stu-id="f628d-129">To learn more about your options, and to walk through the specifics of what policies you'd need to set for meetings and video, check out [Meeting policy settings in Teams: Audio and video](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#meeting-policy-settings---audio--video) for detailed walk-through information.</span></span>

#### <a name="screen-sharing-policies"></a><span data-ttu-id="f628d-130">画面共有ポリシー</span><span class="sxs-lookup"><span data-stu-id="f628d-130">Screen sharing policies</span></span>

<span data-ttu-id="f628d-131">別の例では、教師が取り上げている学習内容に関連するアプリケーションにのみ共有を限定する必要があるにもかかわらず、学生に自分の画面全体を共有している場合があります。</span><span class="sxs-lookup"><span data-stu-id="f628d-131">In other cases, educators may be sharing their entire screen to students, when sharing should be limited to an application relevant to the lesson being taught.</span></span> <span data-ttu-id="f628d-132">この点は、教師が個別に選択するよりも適している場合には、ポリシーで設定できます。</span><span class="sxs-lookup"><span data-stu-id="f628d-132">This can also be set via policy, if that's a more desirable way to do it than to have educators making that choice individually.</span></span>

<span data-ttu-id="f628d-133">ポリシー設定を使用して画面共有を制限するうえで実行できる優れたアイデアについては、「[会議ポリシーの設定 - 画面共有](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#meeting-policy-settings---audio--video)」をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="f628d-133">For a good idea of what you can do about limiting screen sharing via policy settings, check out [Meeting policy settings in Teams: Screen sharing](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#meeting-policy-settings---audio--video).</span></span>

#### <a name="dial-in-number-for-meetings"></a><span data-ttu-id="f628d-134">会議用のダイヤルイン番号</span><span class="sxs-lookup"><span data-stu-id="f628d-134">Dial-in number for meetings</span></span>

<span data-ttu-id="f628d-135">一部の学生にとっては、教室セッションにダイヤルインするほうが簡単な場合があります。</span><span class="sxs-lookup"><span data-stu-id="f628d-135">It may be easier for some students to attempt to dial in to some classroom sessions.</span></span> <span data-ttu-id="f628d-136">Teams 会議用のダイヤルイン番号を提供し、問題が生じている学生がビデオ会議に参加する代わりに電話をかけられるようにできます。</span><span class="sxs-lookup"><span data-stu-id="f628d-136">You can provide a dial-in number for Teams meetings, so students with issues can phone in as an alternative to attending a video meeting.</span></span>

<span data-ttu-id="f628d-137">この点の詳細については、「[Microsoft Teams で招待状に含まれている電話番号を設定する](set-the-phone-numbers-included-on-invites-in-teams.md)」を参照できます。</span><span class="sxs-lookup"><span data-stu-id="f628d-137">For more information on this, you can read [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span>

## <a name="low-bandwidth-scenarios-as-an-educator"></a><span data-ttu-id="f628d-138">教師としての低帯域幅のシナリオ</span><span class="sxs-lookup"><span data-stu-id="f628d-138">Low bandwidth scenarios as an educator</span></span>

<span data-ttu-id="f628d-139">教師には、低帯域幅の問題を解決するための手順を実行する権限が与えられている必要があり、以下のような状況では IT 管理によるアクションが優れた選択となることがあります。</span><span class="sxs-lookup"><span data-stu-id="f628d-139">Educators should feel empowered to take steps to resolve low bandwidth issues, and may be a superior choice to ITAdmin action in the following situations:</span></span>

- <span data-ttu-id="f628d-140">問題が間欠的または一時的に発生する場合。</span><span class="sxs-lookup"><span data-stu-id="f628d-140">If the problem is intermittent, or relatively transitory.</span></span>
- <span data-ttu-id="f628d-141">問題が生じるのが一日の特定の時刻であると予期できる場合や、低帯域幅の期間が予測可能である場合。</span><span class="sxs-lookup"><span data-stu-id="f628d-141">If there is a specific time of the day you can anticipate there being an issue, or the low bandwidth period has some predictability to it.</span></span>

<span data-ttu-id="f628d-142">このような場合は、何らかの措置を講じることができます。</span><span class="sxs-lookup"><span data-stu-id="f628d-142">In these situations, you can take some actions.</span></span>

<span data-ttu-id="f628d-143">詳細については、「[帯域幅が少なくなったときに学業に Teams を使用する](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f628d-143">For more information, check out [Use Teams for schoolwork when bandwidth is low](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262).</span></span>

## <a name="low-bandwidth-scenarios-as-a-parent-or-student"></a><span data-ttu-id="f628d-144">親または学生としての低帯域幅のシナリオ</span><span class="sxs-lookup"><span data-stu-id="f628d-144">Low bandwidth scenarios as a parent or student</span></span>

<span data-ttu-id="f628d-145">帯域幅の問題が学生側にある可能性があり、教師と積極的に話し合う必要がある状況も存在します (たとえば、多数の学生が問題なくビデオ授業を視聴できるものの、少数の学生は困難であるという状況などです)。</span><span class="sxs-lookup"><span data-stu-id="f628d-145">There are also situations, and you should proactively discuss them with your educators, where the bandwidth problem may be on the student's side (for example, a large number of students are able to watch the video lessons without issue, but a small number of students have difficulties).</span></span>

<span data-ttu-id="f628d-146">多くの親にとってこうした問題のトラブルシューティングを行えると期待するのは実際的ではなく、低帯域幅の問題は、学生や親の制御下にないという可能性もあります (自宅が高帯域幅にアクセスできない、大勢のユーザーが近くにいて帯域幅を消費しているため実行できる事柄が制限される、インターネットが不安定になっているなどの状況が生じ得ます)。</span><span class="sxs-lookup"><span data-stu-id="f628d-146">It's not reasonable to expect many parents to be able to troubleshoot these issues, and low bandwidth issues may be out of a student or parent's control (their home may not have access to high bandwidth, they may have a lot of people in their immediate area consuming bandwidth and affecting what they can do, there may be internet instability, and so on).</span></span>

<span data-ttu-id="f628d-147">親と学生向けに「[帯域幅が少なくなったときに学業に Teams を使用する](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262)」の記事でガイダンスを提供しています。何らかの問題が生じている場合には、このガイダンスを確認し、推奨内容を試してください。</span><span class="sxs-lookup"><span data-stu-id="f628d-147">We've put together guidance in our [Use Teams for schoolwork when bandwidth is low](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262) article for parents and students as well, you can review and try these recommendations if you're having any problems.</span></span>