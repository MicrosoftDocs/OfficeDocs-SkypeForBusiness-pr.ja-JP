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
description: コンピューターを使用して音声を使用できない場合に、ユーザーが電話で音声部分に参加できるよう、Teams で通話機能を設定する方法について学習します。
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 04510a827e9343010c756b14590e9800354c71e9
ms.sourcegitcommit: f979c491af5210e6ceb1d1c00e000767f1a8311d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/07/2021
ms.locfileid: "51623135"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a><span data-ttu-id="4d8a0-103">ユーザーの [電話する] 機能をセットアップする</span><span class="sxs-lookup"><span data-stu-id="4d8a0-103">Set up the Call me feature for your users</span></span>

<span data-ttu-id="4d8a0-104">この **Microsoft Teams通話機能** を使用すると、ユーザーは電話で会議の音声部分に参加できます。</span><span class="sxs-lookup"><span data-stu-id="4d8a0-104">In Microsoft Teams, the **Call me** feature gives users a way to join the audio portion of a meeting by phone.</span></span> <span data-ttu-id="4d8a0-105">これは、オーディオにコンピューターを使用できない場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="4d8a0-105">This is handy in scenarios when using a computer for audio might not be possible.</span></span> <span data-ttu-id="4d8a0-106">ユーザーは、携帯電話や固定電話、会議のコンテンツ部分 (別の会議参加者が自分の画面を共有したり、コンピューターを通じてビデオを再生したりした場合など) を通じて会議の音声部分を &mdash; &mdash; 取得します。</span><span class="sxs-lookup"><span data-stu-id="4d8a0-106">Users get the audio portion of the meeting through their cell phone or land line and the content portion of the meeting&mdash;such as when another meeting participant shares their screen or plays a video&mdash;through their computer.</span></span>

> [!IMPORTANT]
> 
> <span data-ttu-id="4d8a0-107">(新型コロナウイルス感染症の発生で) 会議の数が多い間は、ユーザーは PSTN 会議番号を使用または<strong>[折り返し先]</strong>を使用してダイヤルインするのではなく、<strong>[Teams 会議に参加]</strong>ボタンをクリックして会議に参加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4d8a0-107">During periods of high meeting volume (which we've been experiencing in conjunction with the COVID-19 outbreak), we recommend that users join meetings by clicking the <strong>Join Teams Meeting</strong> button rather than dialing in by using the PSTN conference numbers or by using <strong>Call me at</strong>.</span></span> <span data-ttu-id="4d8a0-108">これにより、会議の数が多いことが PSTN ネットワークの混雑の原因となっているときに、音質を高められます。</span><span class="sxs-lookup"><span data-stu-id="4d8a0-108">This helps ensure quality audio during times when high meeting volume is causing congestion on the PSTN network.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="the-user-experience"></a><span data-ttu-id="4d8a0-109">ユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="4d8a0-109">The user experience</span></span>

### <a name="join-a-meeting-by-using-phone-for-audio"></a><span data-ttu-id="4d8a0-110">音声に電話を使って会議に参加する</span><span class="sxs-lookup"><span data-stu-id="4d8a0-110">Join a meeting by using phone for audio</span></span>

<span data-ttu-id="4d8a0-111">[**参加]** をクリックして会議に参加し、[ビデオ **電話** オプションの選択] 画面で音声を選択し、[今すぐ参加]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="4d8a0-111">Click **Join** to join a meeting, then **Phone audio** on the **Choose your video and audio options** screen, and click **Join now**.</span></span> <span data-ttu-id="4d8a0-112">ここから、ユーザーは会議の電話を受け、会議に参加したり、手動で会議にダイヤルインしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="4d8a0-112">From here, users can have the meeting call and join them or dial in manually to the meeting.</span></span>

![[オーディオ] オプション電話スクリーン ショット](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

<span data-ttu-id="4d8a0-114">**会議のTeamsを行う**</span><span class="sxs-lookup"><span data-stu-id="4d8a0-114">**Let the Teams meeting call**</span></span>

<span data-ttu-id="4d8a0-115">[音声 **に電話を使う** ] 画面で、ユーザーが自分の電話番号を入力し、[通話] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="4d8a0-115">On the **Use phone for audio** screen, the user enters their phone number, and then clicks **Call me**.</span></span> <span data-ttu-id="4d8a0-116">会議はユーザーを呼び出し、会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="4d8a0-116">The meeting calls the user and joins them to the meeting.</span></span>

![[音声に電話を使う] 画面の [通話] オプションのスクリーン ショット](media/set-up-the-call-me-feature-for-your-users-call-me.png)

<span data-ttu-id="4d8a0-118">**手動でダイヤルインする**</span><span class="sxs-lookup"><span data-stu-id="4d8a0-118">**Dial in manually**</span></span>

<span data-ttu-id="4d8a0-119">参加するもう 1 つの方法は、会議に直接ダイヤルインする方法です。</span><span class="sxs-lookup"><span data-stu-id="4d8a0-119">Another way to join is to dial in directly to the meeting.</span></span> <span data-ttu-id="4d8a0-120">[音声 **に電話を使用** する]画面で、[手動でダイヤルイン] をクリックして、会議にダイヤルインするために使用する電話番号の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="4d8a0-120">On the **Use phone for audio** screen, click **Dial in manually** to get a list of phone numbers to use to dial in to the meeting.</span></span>

![[手動でダイヤルイン] オプションのスクリーン ショット](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a><span data-ttu-id="4d8a0-122">会議中に音声に問題が発生した場合に、通話を取り戻す</span><span class="sxs-lookup"><span data-stu-id="4d8a0-122">Get a call back when something goes wrong with audio during a meeting</span></span>

<span data-ttu-id="4d8a0-123">ユーザーが会議中にコンピューターを使用するときに音声の問題が発生した場合、ユーザーは電話を音声に簡単に使用する方法に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="4d8a0-123">If a user experiences audio issues when using their computer during a meeting, the user can easily switch to using their phone for audio.</span></span> <span data-ttu-id="4d8a0-124">Teamsまたはデバイスの問題が発生した場合を検出し、[戻る] オプションを表示することで、ユーザーが自分の電話を使用 **するリダイレクトを行** います。</span><span class="sxs-lookup"><span data-stu-id="4d8a0-124">Teams detects when an audio or device issue occurs and redirects the user to use their phone by displaying a **Call me back** option.</span></span>

<span data-ttu-id="4d8a0-125">次に示すのは、マイクが検出されない場合に表示されるメッセージと [Teams] オプションの例です。</span><span class="sxs-lookup"><span data-stu-id="4d8a0-125">Here's an example of the message and the **Call me back** option that's displayed when Teams doesn't detect a microphone.</span></span>

![[戻る] オプションのスクリーン ショット](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

<span data-ttu-id="4d8a0-127">ユーザーが [電話を **呼び戻す**] をクリックすると、[音声に電話を使う] **画面が表示** されます。</span><span class="sxs-lookup"><span data-stu-id="4d8a0-127">The user clicks **Call me back**, which brings up the **Use phone for audio** screen.</span></span> <span data-ttu-id="4d8a0-128">ここから、電話番号を入力し、Teams通話を受け、会議に参加するか、手動で会議にダイヤルインできます。</span><span class="sxs-lookup"><span data-stu-id="4d8a0-128">From here, they can enter their phone number and have the Teams meeting call and join them to the meeting or dial in manually to the meeting.</span></span>

## <a name="set-up-the-call-me-feature"></a><span data-ttu-id="4d8a0-129">[通話] 機能を設定する</span><span class="sxs-lookup"><span data-stu-id="4d8a0-129">Set up the Call me feature</span></span>

<span data-ttu-id="4d8a0-130">組織内のユーザーに対して [通話] 機能を有効にするには、次を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d8a0-130">To enable the Call me feature for users in your organization, the following must be configured:</span></span>

- <span data-ttu-id="4d8a0-131">電話会議は、会議をスケジュールする組織内のユーザー (会議開催者) に対して有効になります。</span><span class="sxs-lookup"><span data-stu-id="4d8a0-131">Audio Conferencing is enabled for users in your organization who schedule meetings (meeting organizers).</span></span> <span data-ttu-id="4d8a0-132">詳細については、「Teams[](set-up-audio-conferencing-in-teams.md)の電話会議を設定する」および「Teams でユーザーの電話会議[設定を管理する」を参照してください](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="4d8a0-132">To learn more, see [Set up Audio Conferencing for Teams](set-up-audio-conferencing-in-teams.md) and [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

- <span data-ttu-id="4d8a0-133">会議の開催者は、会議からダイヤルアウトできます。</span><span class="sxs-lookup"><span data-stu-id="4d8a0-133">Meeting organizer can dial-out from meetings.</span></span> <span data-ttu-id="4d8a0-134">詳細については、「ユーザーの電話[会議設定を](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)管理する」を参照Teams。</span><span class="sxs-lookup"><span data-stu-id="4d8a0-134">To learn more, see [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

<span data-ttu-id="4d8a0-135">会議の開催者が会議からのダイヤルアウトを有効にしない場合、[ビデオとオーディオのオプションの選択]画面の **電話** 音声オプションは誰も使用できません。他のユーザーは、会議に参加するための通話を受信できません。</span><span class="sxs-lookup"><span data-stu-id="4d8a0-135">If the meeting organizer doesn't have dial-out from meetings enabled, the **Phone audio** option on the **Choose your video and audio options** screen isn't available to anyone, and other users can't receive a call to join them to the meeting.</span></span> <span data-ttu-id="4d8a0-136">ダイヤルアウトが有効になっているユーザーの場合、会議に参加すると、[参加者の表示] アイコンから他のユーザーが自分の番号をダイヤル **して参加** できます。</span><span class="sxs-lookup"><span data-stu-id="4d8a0-136">For users with dial-out enabled, once they have joined the meeting, they can join others dialing their number from the **Show participants** icon.</span></span>
