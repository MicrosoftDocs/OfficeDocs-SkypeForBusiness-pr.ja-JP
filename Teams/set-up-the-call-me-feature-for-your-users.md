---
title: ユーザーの [電話する] 機能をセットアップする
author: LanaChin
ms.author: v-lanac
ms.reviewer: macai, phedry
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: ユーザーがオーディオ用にコンピューターを使用しているときに、ユーザーが電話でオーディオ部分に参加できるように、Teams の [折り返し] 機能を設定する方法について説明します。
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d29a517b8df194fe19b9e16554f7c57964177c90
ms.sourcegitcommit: 70b80892a152f86a6d596f0f5b58cf391bc29098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138017"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a><span data-ttu-id="ffbce-103">ユーザーの [電話する] 機能をセットアップする</span><span class="sxs-lookup"><span data-stu-id="ffbce-103">Set up the Call me feature for your users</span></span>

<span data-ttu-id="ffbce-104">Microsoft Teams の [**折り返し**] 機能を使用すると、ユーザーは電話で会議のオーディオ部分に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="ffbce-104">In Microsoft Teams, the **Call me** feature gives users a way to join the audio portion of a meeting by phone.</span></span> <span data-ttu-id="ffbce-105">これは、オーディオ用のコンピューターを使うことができない場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="ffbce-105">This is handy in scenarios when using a computer for audio might not be possible.</span></span> <span data-ttu-id="ffbce-106">ユーザーは、会議のオーディオ部分を、携帯電話または土地ラインと、会議の &mdash; 他の参加者が自分の画面を共有したり、コンピューターでビデオを再生したりする場合など、会議のコンテンツ部分を取得し &mdash; ます。</span><span class="sxs-lookup"><span data-stu-id="ffbce-106">Users get the audio portion of the meeting through their cell phone or land line and the content portion of the meeting&mdash;such as when another meeting participant shares their screen or plays a video&mdash;through their computer.</span></span>

> [!IMPORTANT]
> 
> <span data-ttu-id="ffbce-107">会議の高いボリューム (COVID-19 の感染と連携しています) 中に、PSTN 電話番号を使用するか、または [<strong>折り返し</strong>先] を使用して、[ <strong>Teams 会議への参加</strong>] ボタンをクリックして会議に参加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ffbce-107">During periods of high meeting volume (which we've been experiencing in conjunction with the COVID-19 outbreak), we recommend that users join meetings by clicking the <strong>Join Teams Meeting</strong> button rather than dialing in by using the PSTN conference numbers or by using <strong>Call me at</strong>.</span></span> <span data-ttu-id="ffbce-108">これにより、会議の大規模が PSTN ネットワーク上の輻輳の原因となっている場合に、品質のオーディオを確保することができます。</span><span class="sxs-lookup"><span data-stu-id="ffbce-108">This helps ensure quality audio during times when high meeting volume is causing congestion on the PSTN network.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="ffbce-109">新型コロナウイルス感染症 (COVID-19) の発生が起こっている間、PSTN 会議番号を使用または **[折り返し先]** を使用してダイヤルインするのではなく、**[Teams 会議に参加]** ボタンをクリックして、ユーザーが会議に参加することをお勧めします</strong>。</span><span class="sxs-lookup"><span data-stu-id="ffbce-109">During the duration of the COVID-19 outbreak, we recommend that users join meetings by clicking the **Join Teams Meeting** button rather than dialing in by using the PSTN conference numbers or by using **Call me at**</strong>.</span></span> <span data-ttu-id="ffbce-110">これは主に、COVID-19 の影響を受ける国のテレフォニー インフラストラクチャが混雑するためです。</span><span class="sxs-lookup"><span data-stu-id="ffbce-110">This is primarily because of congestion in the telephony infrastructures of countries impacted by COVID-19.</span></span> <span data-ttu-id="ffbce-111">PSTN 通話を回避することによって、音質が向上します。</span><span class="sxs-lookup"><span data-stu-id="ffbce-111">By avoiding PSTN calls, you'll likely experience better audio quality.</span></span> 

## <a name="the-user-experience"></a><span data-ttu-id="ffbce-112">ユーザーエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="ffbce-112">The user experience</span></span>

### <a name="join-a-meeting-by-using-phone-for-audio"></a><span data-ttu-id="ffbce-113">電話で音声を使って会議に参加する</span><span class="sxs-lookup"><span data-stu-id="ffbce-113">Join a meeting by using phone for audio</span></span>

<span data-ttu-id="ffbce-114">会議に参加するには、[**参加**] をクリックし、[**オーディオとビデオの設定を選択して**ください] 画面で [電話の**オーディオ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ffbce-114">Click **Join** to join a meeting, and then click **Phone audio** on the  **Choose your audio and video settings** screen.</span></span> <span data-ttu-id="ffbce-115">ここでは、ユーザーが会議通話を使用して会議に参加したり、手動で会議にダイヤルインしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="ffbce-115">From here, users can have the meeting call and join them or dial in manually to the meeting.</span></span>

![[電話] オーディオオプションのスクリーンショット](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

<span data-ttu-id="ffbce-117">**チームに会議通話を許可する**</span><span class="sxs-lookup"><span data-stu-id="ffbce-117">**Let the Teams meeting call**</span></span>

<span data-ttu-id="ffbce-118">[**オーディオ用に電話を使う**] 画面で、ユーザーは電話番号を入力し、[**折り返し**先] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ffbce-118">On the **Use phone for audio** screen, the user enters their phone number, and then clicks **Call me**.</span></span> <span data-ttu-id="ffbce-119">会議はユーザーを呼び出し、会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="ffbce-119">The meeting calls the user and joins them to the meeting.</span></span>

![[オーディオ用電話を使う] 画面の [折り返し先] オプションのスクリーンショット](media/set-up-the-call-me-feature-for-your-users-call-me.png)

<span data-ttu-id="ffbce-121">**手動でダイヤルする**</span><span class="sxs-lookup"><span data-stu-id="ffbce-121">**Dial in manually**</span></span>

<span data-ttu-id="ffbce-122">もう1つの方法は、会議に直接ダイヤルインすることです。</span><span class="sxs-lookup"><span data-stu-id="ffbce-122">Another way to join is to dial in directly to the meeting.</span></span> <span data-ttu-id="ffbce-123">[**オーディオ用に電話を使う**] 画面で、[**手動でダイヤル**する] をクリックして、会議にダイヤルインするために使用する電話番号の一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="ffbce-123">On the **Use phone for audio** screen, click **Dial in manually** to get a list of phone numbers to use to dial in to the meeting.</span></span>

![[手動でダイヤルする] オプションのスクリーンショット](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a><span data-ttu-id="ffbce-125">会議中に音声で問題が発生した場合に、通話を取り戻す</span><span class="sxs-lookup"><span data-stu-id="ffbce-125">Get a call back when something goes wrong with audio during a meeting</span></span>

<span data-ttu-id="ffbce-126">ユーザーが会議中に自分のコンピューターを使っているときに音声の問題が発生した場合、ユーザーは簡単に電話で音声通話に切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="ffbce-126">If a user experiences audio issues when using their computer during a meeting, the user can easily switch to using their phone for audio.</span></span> <span data-ttu-id="ffbce-127">チームは、音声またはデバイスの問題が発生したときに検出し、[**コールバック**] オプションを表示して、ユーザーが電話を使用するようにユーザーをリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="ffbce-127">Teams detects when an audio or device issue occurs and redirects the user to use their phone by displaying a **Call me back** option.</span></span>

<span data-ttu-id="ffbce-128">ここでは、Teams でマイクが検出されないときに表示されるメッセージと [折り返して**戻る**] オプションの例を示します。</span><span class="sxs-lookup"><span data-stu-id="ffbce-128">Here's an example of the message and the **Call me back** option that's displayed when Teams doesn't detect a microphone.</span></span>

![[コールバック] オプションのスクリーンショット](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

<span data-ttu-id="ffbce-130">ユーザーが [**コールバック**] をクリックすると、[**電話を使用する**] 画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ffbce-130">The user clicks **Call me back**, which brings up the **Use phone for audio** screen.</span></span> <span data-ttu-id="ffbce-131">このページでは、自分の電話番号を入力して、Teams 会議に参加し、会議に直接参加したり、手動で会議にダイヤルインしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="ffbce-131">From here, they can enter their phone number and have the Teams meeting call and join them to the meeting or dial in manually to the meeting.</span></span>

## <a name="set-up-the-call-me-feature"></a><span data-ttu-id="ffbce-132">[折り返し先] 機能を設定する</span><span class="sxs-lookup"><span data-stu-id="ffbce-132">Set up the Call me feature</span></span>

<span data-ttu-id="ffbce-133">組織内のユーザーに対して [折り返して呼び出す] 機能を有効にするには、次の設定を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="ffbce-133">To enable the Call me feature for users in your organization, the following must be configured:</span></span>

- <span data-ttu-id="ffbce-134">会議をスケジュールする組織内のユーザー (会議の開催者) では、電話会議が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="ffbce-134">Audio Conferencing is enabled for users in your organization who schedule meetings (meeting organizers).</span></span> <span data-ttu-id="ffbce-135">詳細については、「 [teams の電話会議をセットアップ](set-up-audio-conferencing-in-teams.md)する」および「 [teams でユーザーの電話会議の設定を管理](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ffbce-135">To learn more, see [Set up Audio Conferencing for Teams](set-up-audio-conferencing-in-teams.md) and [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

- <span data-ttu-id="ffbce-136">ユーザーは会議からダイヤルアウトできます。</span><span class="sxs-lookup"><span data-stu-id="ffbce-136">Users can dial out from meetings.</span></span> <span data-ttu-id="ffbce-137">詳細については、「 [Teams でユーザーの電話会議の設定を管理](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ffbce-137">To learn more, see [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

<span data-ttu-id="ffbce-138">ユーザーが会議からのダイヤルアウトを有効にしていない場合、 **[折り返し先] オプションは**利用できません。ユーザーは会議に参加するための電話を受けません。</span><span class="sxs-lookup"><span data-stu-id="ffbce-138">If a user doesn't have dial out from meetings enabled, the **Call me** option isn't available and the user won't receive a call to join them to the meeting.</span></span> <span data-ttu-id="ffbce-139">代わりに、電話で電話の会議に手動でダイヤルインするために使うことができる電話番号のリストが、[**オーディオの使用電話**] 画面に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ffbce-139">Instead, the user sees a list of phone numbers on the **Use phone for audio** screen that they can use to dial in manually to the meeting on their phone.</span></span>
