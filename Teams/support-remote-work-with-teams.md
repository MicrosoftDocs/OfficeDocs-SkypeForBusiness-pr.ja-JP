---
title: Microsoft Teams を使用してリモート ワーカーをサポートする
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: dansteve
localization_priority: Priority
search.appverid: MET150
description: このガイダンスは、Microsoft Teams を使用して組織のリモート ワーカーの生産性を向上させるために使用できます。特に、新型コロナウイルス感染症 (COVID-19) 発生への対策として従業員が在宅勤務 (WFH) となった場合に役立ちます。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 80af76906697ef2510fe75d8764e8908cdbbd976
ms.sourcegitcommit: ed0ecb3b1250a23d3b91a5a33256aee1c3119db1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/03/2020
ms.locfileid: "42374314"
---
# <a name="support-remote-workers-using-microsoft-teams"></a><span data-ttu-id="b6d0f-103">Microsoft Teams を使用してリモート ワーカーをサポートする</span><span class="sxs-lookup"><span data-stu-id="b6d0f-103">Support remote workers using Microsoft Teams</span></span>

<span data-ttu-id="b6d0f-104">この記事に記載されているベスト プラクティスを使用して、リモートまたは自宅で作業を行うユーザーをサポートしてください。</span><span class="sxs-lookup"><span data-stu-id="b6d0f-104">Use the best practices in this article to support your users who work remotely or from home.</span></span>

## <a name="technical"></a><span data-ttu-id="b6d0f-105">技術面に関する説明</span><span class="sxs-lookup"><span data-stu-id="b6d0f-105">Technical</span></span>

1.  <span data-ttu-id="b6d0f-106">[すべてのユーザーに対して Teams が有効になっている](assign-teams-licenses.md)ことを確認します</span><span class="sxs-lookup"><span data-stu-id="b6d0f-106">Make sure [Teams is turned on for everyone](assign-teams-licenses.md)</span></span>
    
      - <span data-ttu-id="b6d0f-107">[Teams E1 試用版](e1-trial-license.md)、[Teams Exploratory](teams-exploratory.md)、または[無料版の Teams](https://support.office.com/article/Welcome-to-Microsoft-Teams-free-6d79a648-6913-4696-9237-ed13de64ae3c) に関する説明を確認し、社員全員が Teams を利用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="b6d0f-107">Look at the [Teams E1 Trial](e1-trial-license.md), [Teams Exploratory](teams-exploratory.md), or [Teams free](https://support.office.com/article/Welcome-to-Microsoft-Teams-free-6d79a648-6913-4696-9237-ed13de64ae3c) to make Teams available to everybody in your company.</span></span>

      - <span data-ttu-id="b6d0f-108">リモートの従業員は、会議や電話会議に大きく依存しています。</span><span class="sxs-lookup"><span data-stu-id="b6d0f-108">Remote employees rely more heavily on meetings and audio conferencing.</span></span> <span data-ttu-id="b6d0f-109">これらのワークロードをまだ展開していない場合は、「[Teams でのミーティングと会議](deploy-meetings-microsoft-teams-landing-page.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6d0f-109">If you haven't yet rolled out these workloads, check out [Meetings and conferencing in Teams](deploy-meetings-microsoft-teams-landing-page.md).</span></span>

2.  <span data-ttu-id="b6d0f-110">Teams についてユーザーに通知します。</span><span class="sxs-lookup"><span data-stu-id="b6d0f-110">Tell your users about Teams.</span></span> <span data-ttu-id="b6d0f-111">[Teams カスタマー サクセス キット](https://download.microsoft.com/download/A/E/9/AE984CD4-CF4B-41E7-9ABD-6735E3F01897/MicrosoftTeamsCustomerSuccessKit.zip)をダウンロードして、プレゼンテーション、サンプル メール、ポスター、および使用開始ガイドを入手してください。</span><span class="sxs-lookup"><span data-stu-id="b6d0f-111">Download the [Teams Customer Success Kit](https://download.microsoft.com/download/A/E/9/AE984CD4-CF4B-41E7-9ABD-6735E3F01897/MicrosoftTeamsCustomerSuccessKit.zip) to get presentations, sample emails, posters, and getting-started guides.</span></span>


5.  <span data-ttu-id="b6d0f-112">従業員のインターネット アクセスと帯域幅が、Teams のために十分なものであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b6d0f-112">Make sure your employees have adequate internet access and bandwidth for Teams.</span></span> <span data-ttu-id="b6d0f-113">これを行う方法については、「[Teams 用に組織のネットワークを準備する](prepare-network.md)」のガイダンスをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b6d0f-113">Use the guidance in [Prepare your organization's network for Teams](prepare-network.md) to learn how to do this.</span></span>
    - <span data-ttu-id="b6d0f-114">帯域幅が十分でない場合、Teams 会議の音質に影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b6d0f-114">Limited bandwidth can affect audio quality in Teams meetings.</span></span> <span data-ttu-id="b6d0f-115">低帯域幅の条件下での会議エクスペリエンスを最良なものにするために、ビデオの使用を控え、通話と会議の音声に公衆交換電話網 (PSTN) を使用することをユーザーに推奨します。</span><span class="sxs-lookup"><span data-stu-id="b6d0f-115">To ensure the best meeting experience under low-bandwidth conditions, encourage users to limit video and use PSTN for calls and meeting audio.</span></span> 

    - <span data-ttu-id="b6d0f-116">通話や会議の品質に関する問題のトラブルシューティングや解決のサポートが必要な場合は、この記事の下部にある「[既知の問題: Skype for Business/Teams 会議 ID へのダイヤルイン](#known-issue-dialing-into-skype-for-business-or-teams-conference-ids)」のガイダンスに従ってください。</span><span class="sxs-lookup"><span data-stu-id="b6d0f-116">If you need help troubleshooting or fixing problems with call or meeting quality, follow the guidance in [Known issue: Dialing into Skype for Business/Teams conference IDs](#known-issue-dialing-into-skype-for-business-or-teams-conference-ids) at the bottom of this article.</span></span>

2.  <span data-ttu-id="b6d0f-117">[トレーニングへのリンクを送信](enduser-training.md)して、従業員が Teams を最大限に活用できるよう支援します。</span><span class="sxs-lookup"><span data-stu-id="b6d0f-117">[Send out links to training](enduser-training.md) to help your employees get the most out of Teams.</span></span>
    
3. <span data-ttu-id="b6d0f-118">リモートでの作業に関する Microsoft の新しいコンテンツを読み、ユーザーと共有します。</span><span class="sxs-lookup"><span data-stu-id="b6d0f-118">Read our new content about working remotely and share it with your users:</span></span>
        
      - <span data-ttu-id="b6d0f-119">Teams ブログ (2020 年 2 月 28 日): [Microsoft Teams を使用して在宅勤務するための 4 つのヒント](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/4-tips-for-working-from-home-with-microsoft-teams-by-lola/ba-p/1202083)</span><span class="sxs-lookup"><span data-stu-id="b6d0f-119">Teams blog (Feb 28, 2020): [4 tips for working from home with Microsoft Teams](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/4-tips-for-working-from-home-with-microsoft-teams-by-lola/ba-p/1202083)</span></span>

      - [<span data-ttu-id="b6d0f-120">Office 365 で共同作業する</span><span class="sxs-lookup"><span data-stu-id="b6d0f-120">Collaborate with Office 365</span></span>](https://support.office.com/article/Collaborate-with-Office-365-ac05a41e-0b49-4420-9ebc-190ee4e744f4)

      - [<span data-ttu-id="b6d0f-121">Teams と Office 365 を使用してリモートで作業する</span><span class="sxs-lookup"><span data-stu-id="b6d0f-121">Working remotely with Teams and Office 365</span></span>](https://support.microsoft.com/help/4549995/working-remotely-with-teams-and-office-365)

3.  <span data-ttu-id="b6d0f-122">モバイル アプリを[インストール](get-clients.md#mobile-clients)して使用することを全従業員に奨励します: [iOS](https://go.microsoft.com/fwlink/?LinkId=835758)   [Android](https://go.microsoft.com/fwlink/p/?linkid=2102168)</span><span class="sxs-lookup"><span data-stu-id="b6d0f-122">Encourage everyone to [install](get-clients.md#mobile-clients) and use the mobile app: [iOS](https://go.microsoft.com/fwlink/?LinkId=835758)   [Android](https://go.microsoft.com/fwlink/p/?linkid=2102168)</span></span>

    > [!NOTE]
    > <span data-ttu-id="b6d0f-123">中国にお住まいの場合は、「[中国で Android 用 Teams を取得する](get-teams-android-in-china.md)」にアクセスしてください</span><span class="sxs-lookup"><span data-stu-id="b6d0f-123">If you're in China, go here to [Get Teams for Android in China](get-teams-android-in-china.md)</span></span>

4.  <span data-ttu-id="b6d0f-124">ユーザーの問い合わせに対応するために [ヘルプ デスク](troubleshoot-installation.md)の人員を増やします。</span><span class="sxs-lookup"><span data-stu-id="b6d0f-124">Staff up your [helpdesk](troubleshoot-installation.md) to deal with user inquiries.</span></span>


## <a name="communications"></a><span data-ttu-id="b6d0f-125">コミュニケーション</span><span class="sxs-lookup"><span data-stu-id="b6d0f-125">Communications</span></span>

<span data-ttu-id="b6d0f-126">Teams を使用して、従業員と連絡を取り合います。</span><span class="sxs-lookup"><span data-stu-id="b6d0f-126">Use Teams to stay in touch with your employees:</span></span>
- <span data-ttu-id="b6d0f-127">[組織全体のチーム](create-an-org-wide-team.md)、および[社内コミュニケーター](https://docs.microsoft.com/microsoftteams/platform/samples/app-templates#company-communicator) アプリのテンプレート</span><span class="sxs-lookup"><span data-stu-id="b6d0f-127">[Org-wide teams](create-an-org-wide-team.md) and [Company Communicator](https://docs.microsoft.com/microsoftteams/platform/samples/app-templates#company-communicator) app template</span></span>
    
- <span data-ttu-id="b6d0f-128">組織の在宅勤務および健康と安全に関するポリシーに関する情報を送信します。</span><span class="sxs-lookup"><span data-stu-id="b6d0f-128">Send out information about your org’s work-from-home and health and safety policies.</span></span>
    
- <span data-ttu-id="b6d0f-129">全社的な会議および活動には、[ライブ イベント](teams-live-events/what-are-teams-live-events.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="b6d0f-129">Use [Live events](teams-live-events/what-are-teams-live-events.md) for company-wide meetings and outreach.</span></span> <span data-ttu-id="b6d0f-130">参加者が 250 人以上の会議は、ライブ イベントにします。</span><span class="sxs-lookup"><span data-stu-id="b6d0f-130">For any meeting of more than 250 participants, make it a live event.</span></span> 

## <a name="personal-considerations"></a><span data-ttu-id="b6d0f-131">社員が心がけるべきこと</span><span class="sxs-lookup"><span data-stu-id="b6d0f-131">Personal considerations</span></span>

<span data-ttu-id="b6d0f-132">在宅勤務を成功させるためのヒントを次に示します。</span><span class="sxs-lookup"><span data-stu-id="b6d0f-132">Here are some tips for successfully working from home:</span></span>

- <span data-ttu-id="b6d0f-133">明るく、適切なエルゴノミクスを備えた、他のスペースから区別された物理的な作業スペースを確保します。</span><span class="sxs-lookup"><span data-stu-id="b6d0f-133">Have a defined physical work space with good lighting and proper ergonomics.</span></span>

- <span data-ttu-id="b6d0f-134">勤務時間や在席予定時間を明確に決め、不在時は Teams の[プレゼンス状態](https://support.office.com/article/change-your-status-in-teams-ce36ed14-6bc9-4775-a33e-6629ba4ff78e)を使用してそのことを示します。</span><span class="sxs-lookup"><span data-stu-id="b6d0f-134">Set clear boundaries on your work hours and commitments, and use the Teams [presence status](https://support.office.com/article/change-your-status-in-teams-ce36ed14-6bc9-4775-a33e-6629ba4ff78e) to indicate when you're away.</span></span>

- <span data-ttu-id="b6d0f-135">在宅勤務でも意識的に「通勤」します。在宅勤務をすることで、在宅中イコール勤務時間にならないように気をつけてください。</span><span class="sxs-lookup"><span data-stu-id="b6d0f-135">“Commute” to and from your work-from-home office deliberately; don’t turn work-from-home into home-equals-work.</span></span>

- <span data-ttu-id="b6d0f-136">定期的に立ち上がり、休憩をとります。</span><span class="sxs-lookup"><span data-stu-id="b6d0f-136">Get up and take a break periodically.</span></span> <span data-ttu-id="b6d0f-137">散歩やストレッチをしたりお茶を飲んだりして休みます。</span><span class="sxs-lookup"><span data-stu-id="b6d0f-137">Go for a walk, stretch, make yourself a cup of tea.</span></span>

## <a name="known-issue-dialing-into-skype-for-business-or-teams-conference-ids"></a><span data-ttu-id="b6d0f-138">既知の問題: Skype for Business または Teams 会議 ID へのダイヤルイン</span><span class="sxs-lookup"><span data-stu-id="b6d0f-138">Known issue: Dialing into Skype for Business or Teams conference IDs</span></span>

<span data-ttu-id="b6d0f-139">以下は、2020 年 2 月 7 日のメッセージ センターの投稿 (MC203397) の概要です。</span><span class="sxs-lookup"><span data-stu-id="b6d0f-139">The following is a summary of a Feb 7, 2020 Message center post (MC203397):</span></span>

<span data-ttu-id="b6d0f-140">Microsoft では、中国地域の一部のユーザーが Skype for Business または Teams 会議 ID にダイヤルインする際に問題が発生していることを認識しています。</span><span class="sxs-lookup"><span data-stu-id="b6d0f-140">Microsoft is aware that some users in the China region are experiencing issues dialing into Skype for Business or Teams conference IDs.</span></span> <span data-ttu-id="b6d0f-141">ほとんどの場合、これらの問題は、Microsoft が管理するシステムの外部で発生しています。</span><span class="sxs-lookup"><span data-stu-id="b6d0f-141">In most cases, these problems are external to systems under our control.</span></span> <span data-ttu-id="b6d0f-142">多くの場合、問題はローカルのモバイル キャリアおよびテレフォニー キャリアにあります。</span><span class="sxs-lookup"><span data-stu-id="b6d0f-142">Often, the issue is with local mobile and telephony carriers.</span></span> 

<span data-ttu-id="b6d0f-143">電話会議の問題が発生した場合は、次のことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b6d0f-143">We recommend the following if you're having audio conferencing problems:</span></span>

- <span data-ttu-id="b6d0f-144">発信者または会議の開催者にユーザーの PSTN または携帯電話の電話番号に発信することを依頼する</span><span class="sxs-lookup"><span data-stu-id="b6d0f-144">Ask the caller or meeting organizer to call your PSTN or mobile number</span></span>
- <span data-ttu-id="b6d0f-145">VoIP を使用して、デスクトップまたはモバイル クライアントから電話や会議に参加する</span><span class="sxs-lookup"><span data-stu-id="b6d0f-145">Join the call or meeting from the desktop or mobile clients, using VoIP</span></span>

<span data-ttu-id="b6d0f-146">サポート チケットを記録する必要がある場合は、次の情報を入力してください。</span><span class="sxs-lookup"><span data-stu-id="b6d0f-146">If you need to log a support ticket, please include the following:</span></span>
    
- <span data-ttu-id="b6d0f-147">通話の正確な時間</span><span class="sxs-lookup"><span data-stu-id="b6d0f-147">Exact time of call</span></span>
- <span data-ttu-id="b6d0f-148">ダイヤルされた会議ブリッジ番号</span><span class="sxs-lookup"><span data-stu-id="b6d0f-148">Conference bridge number dialed</span></span>
- <span data-ttu-id="b6d0f-149">発信者の電話ネットワーク</span><span class="sxs-lookup"><span data-stu-id="b6d0f-149">Caller phone network</span></span>
- <span data-ttu-id="b6d0f-150">発信者の電話番号</span><span class="sxs-lookup"><span data-stu-id="b6d0f-150">Caller Phone Number</span></span>
