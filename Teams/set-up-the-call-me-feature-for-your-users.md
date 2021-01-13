---
title: ユーザーの [電話する] 機能をセットアップする
author: cichur
ms.author: v-cichur
ms.reviewer: macai, phedry
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: ユーザーが自分のコンピューターを音声に使用するときに電話で音声部分に参加できない可能性がある場合に、Teams の [自分に電話で知り合い] 機能を設定する方法について学習します。
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6b78edc01f68df19e850a85eb0ffa99163b9edae
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821097"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a><span data-ttu-id="6ac3d-103">ユーザーの [電話する] 機能をセットアップする</span><span class="sxs-lookup"><span data-stu-id="6ac3d-103">Set up the Call me feature for your users</span></span>

<span data-ttu-id="6ac3d-104">Microsoft Teams の通話機能 **を使用** すると、電話で会議の音声部分に参加できます。</span><span class="sxs-lookup"><span data-stu-id="6ac3d-104">In Microsoft Teams, the **Call me** feature gives users a way to join the audio portion of a meeting by phone.</span></span> <span data-ttu-id="6ac3d-105">これは、コンピューターを使用してオーディオを使用できない場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="6ac3d-105">This is handy in scenarios when using a computer for audio might not be possible.</span></span> <span data-ttu-id="6ac3d-106">ユーザーは、携帯電話または固定電話を通じて会議の音声部分を取得し、別の会議参加者が自分の画面を共有したり、自分のコンピューターを介してビデオを再生したりした場合など、会議のコンテンツ部分を &mdash; &mdash; 取得します。</span><span class="sxs-lookup"><span data-stu-id="6ac3d-106">Users get the audio portion of the meeting through their cell phone or land line and the content portion of the meeting&mdash;such as when another meeting participant shares their screen or plays a video&mdash;through their computer.</span></span>

> [!IMPORTANT]
> 
> <span data-ttu-id="6ac3d-107">(新型コロナウイルス感染症の発生で) 会議の数が多い間は、ユーザーは PSTN 会議番号を使用または<strong>[折り返し先]</strong>を使用してダイヤルインするのではなく、<strong>[Teams 会議に参加]</strong>ボタンをクリックして会議に参加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6ac3d-107">During periods of high meeting volume (which we've been experiencing in conjunction with the COVID-19 outbreak), we recommend that users join meetings by clicking the <strong>Join Teams Meeting</strong> button rather than dialing in by using the PSTN conference numbers or by using <strong>Call me at</strong>.</span></span> <span data-ttu-id="6ac3d-108">これにより、会議の数が多いことが PSTN ネットワークの混雑の原因となっているときに、音質を高められます。</span><span class="sxs-lookup"><span data-stu-id="6ac3d-108">This helps ensure quality audio during times when high meeting volume is causing congestion on the PSTN network.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="6ac3d-109">新型コロナウイルス感染症 (COVID-19) の発生が起こっている間、PSTN 会議番号を使用または **[折り返し先]** を使用してダイヤルインするのではなく、**[Teams 会議に参加]** ボタンをクリックして、ユーザーが会議に参加することをお勧めします</strong>。</span><span class="sxs-lookup"><span data-stu-id="6ac3d-109">During the duration of the COVID-19 outbreak, we recommend that users join meetings by clicking the **Join Teams Meeting** button rather than dialing in by using the PSTN conference numbers or by using **Call me at**</strong>.</span></span> <span data-ttu-id="6ac3d-110">これは主に、COVID-19 の影響を受ける国のテレフォニー インフラストラクチャが混雑するためです。</span><span class="sxs-lookup"><span data-stu-id="6ac3d-110">This is primarily because of congestion in the telephony infrastructures of countries impacted by COVID-19.</span></span> <span data-ttu-id="6ac3d-111">PSTN 通話を回避することによって、音質が向上します。</span><span class="sxs-lookup"><span data-stu-id="6ac3d-111">By avoiding PSTN calls, you'll likely experience better audio quality.</span></span> 

## <a name="the-user-experience"></a><span data-ttu-id="6ac3d-112">ユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="6ac3d-112">The user experience</span></span>

### <a name="join-a-meeting-by-using-phone-for-audio"></a><span data-ttu-id="6ac3d-113">音声に電話を使って会議に参加する</span><span class="sxs-lookup"><span data-stu-id="6ac3d-113">Join a meeting by using phone for audio</span></span>

<span data-ttu-id="6ac3d-114">[**参加]** をクリックして会議に参加し、[音声とビデオの設定の選択] 画面で [**電話の音声] をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="6ac3d-114">Click **Join** to join a meeting, and then click **Phone audio** on the  **Choose your audio and video settings** screen.</span></span> <span data-ttu-id="6ac3d-115">ここから、ユーザーは会議の電話を受け、会議に参加したり、会議に手動でダイヤルインできます。</span><span class="sxs-lookup"><span data-stu-id="6ac3d-115">From here, users can have the meeting call and join them or dial in manually to the meeting.</span></span>

![電話の音声オプションのスクリーン ショット](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

<span data-ttu-id="6ac3d-117">**Teams 会議の通話を行う**</span><span class="sxs-lookup"><span data-stu-id="6ac3d-117">**Let the Teams meeting call**</span></span>

<span data-ttu-id="6ac3d-118">[音声 **に電話を使** う] 画面で、ユーザーが自分の電話番号を入力し、[電話を受け取る] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="6ac3d-118">On the **Use phone for audio** screen, the user enters their phone number, and then clicks **Call me**.</span></span> <span data-ttu-id="6ac3d-119">会議によってユーザーが呼び出され、会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="6ac3d-119">The meeting calls the user and joins them to the meeting.</span></span>

![[電話をオーディオ画面に使う] の [電話で呼び出す] オプションのスクリーン ショット](media/set-up-the-call-me-feature-for-your-users-call-me.png)

<span data-ttu-id="6ac3d-121">**手動でダイヤルインする**</span><span class="sxs-lookup"><span data-stu-id="6ac3d-121">**Dial in manually**</span></span>

<span data-ttu-id="6ac3d-122">参加するもう 1 つの方法は、会議に直接ダイヤルインする方法です。</span><span class="sxs-lookup"><span data-stu-id="6ac3d-122">Another way to join is to dial in directly to the meeting.</span></span> <span data-ttu-id="6ac3d-123">[音声 **に電話を使う**]画面で、[手動でダイヤルイン] をクリックして、会議にダイヤルインするために使用する電話番号の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="6ac3d-123">On the **Use phone for audio** screen, click **Dial in manually** to get a list of phone numbers to use to dial in to the meeting.</span></span>

![[手動でダイヤルイン] オプションのスクリーン ショット](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a><span data-ttu-id="6ac3d-125">会議中に音声に問題が発生した場合に通話を取り戻す</span><span class="sxs-lookup"><span data-stu-id="6ac3d-125">Get a call back when something goes wrong with audio during a meeting</span></span>

<span data-ttu-id="6ac3d-126">ユーザーが会議中にコンピューターを使用するときに音声の問題が発生した場合、ユーザーは簡単に自分の電話を音声に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="6ac3d-126">If a user experiences audio issues when using their computer during a meeting, the user can easily switch to using their phone for audio.</span></span> <span data-ttu-id="6ac3d-127">Teams は、音声またはデバイスの問題が発生した場合を検出し、[戻る] オプションを表示してユーザーに電話を使用 **をリダイレクト** します。</span><span class="sxs-lookup"><span data-stu-id="6ac3d-127">Teams detects when an audio or device issue occurs and redirects the user to use their phone by displaying a **Call me back** option.</span></span>

<span data-ttu-id="6ac3d-128">Teams がマイクを検出しない場合に表示されるメッセージと [電話で戻る] オプションの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6ac3d-128">Here's an example of the message and the **Call me back** option that's displayed when Teams doesn't detect a microphone.</span></span>

![[戻る] オプションのスクリーン ショット](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

<span data-ttu-id="6ac3d-130">ユーザーが [電話で **戻る**] をクリックすると、[電話を音声で使う] **画面が表示** されます。</span><span class="sxs-lookup"><span data-stu-id="6ac3d-130">The user clicks **Call me back**, which brings up the **Use phone for audio** screen.</span></span> <span data-ttu-id="6ac3d-131">ここから、電話番号を入力し、Teams 会議通話を受け、会議に参加するか、会議に手動でダイヤルインします。</span><span class="sxs-lookup"><span data-stu-id="6ac3d-131">From here, they can enter their phone number and have the Teams meeting call and join them to the meeting or dial in manually to the meeting.</span></span>

## <a name="set-up-the-call-me-feature"></a><span data-ttu-id="6ac3d-132">通話機能を設定する</span><span class="sxs-lookup"><span data-stu-id="6ac3d-132">Set up the Call me feature</span></span>

<span data-ttu-id="6ac3d-133">組織内のユーザーに対して [呼び出し] 機能を有効にするには、次を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ac3d-133">To enable the Call me feature for users in your organization, the following must be configured:</span></span>

- <span data-ttu-id="6ac3d-134">電話会議は、会議をスケジュールする組織内のユーザー (会議の開催者) に対して有効になります。</span><span class="sxs-lookup"><span data-stu-id="6ac3d-134">Audio Conferencing is enabled for users in your organization who schedule meetings (meeting organizers).</span></span> <span data-ttu-id="6ac3d-135">詳細については、「Teams の電話会議のセットアップ」および [「Teams](set-up-audio-conferencing-in-teams.md) でユーザーの電話会議設定 [を管理する」を参照してください](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="6ac3d-135">To learn more, see [Set up Audio Conferencing for Teams](set-up-audio-conferencing-in-teams.md) and [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

- <span data-ttu-id="6ac3d-136">ユーザーは会議からダイヤルアウトできます。</span><span class="sxs-lookup"><span data-stu-id="6ac3d-136">Users can dial out from meetings.</span></span> <span data-ttu-id="6ac3d-137">詳細については、「Teams でユーザー [の電話会議設定を管理する」を参照してください](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="6ac3d-137">To learn more, see [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

<span data-ttu-id="6ac3d-138">ユーザーが会議からダイヤルアウトを有効にしない場合、[呼び出し] オプションは使用できないので、ユーザーは会議に参加する呼び出しを受信しません。</span><span class="sxs-lookup"><span data-stu-id="6ac3d-138">If a user doesn't have dial out from meetings enabled, the **Call me** option isn't available and the user won't receive a call to join them to the meeting.</span></span> <span data-ttu-id="6ac3d-139">代わりに、[電話を音声に使う] 画面に電話番号の一覧が表示されます。この一覧を使って、電話で会議に手動でダイヤルインできます。</span><span class="sxs-lookup"><span data-stu-id="6ac3d-139">Instead, the user sees a list of phone numbers on the **Use phone for audio** screen that they can use to dial in manually to the meeting on their phone.</span></span>
