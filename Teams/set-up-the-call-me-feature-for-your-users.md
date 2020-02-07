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
description: ユーザーがオーディオ用にコンピューターを使用している可能性がある場合に、ユーザーが電話でオーディオ部分に参加できるように、Teams の [折り返し] 機能を設定する方法について説明します。
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: fe895fee4f3bc0872d277429289b5d04d6c9161d
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837997"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a><span data-ttu-id="6d561-103">ユーザーの [電話する] 機能をセットアップする</span><span class="sxs-lookup"><span data-stu-id="6d561-103">Set up the Call me feature for your users</span></span>

<span data-ttu-id="6d561-104">Microsoft Teams の [**折り返し**] 機能を使用すると、ユーザーは電話で会議のオーディオ部分に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="6d561-104">In Microsoft Teams, the **Call me** feature gives users a way to join the audio portion of a meeting by phone.</span></span> <span data-ttu-id="6d561-105">これは、オーディオ用のコンピューターを使うことができない場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="6d561-105">This is handy in scenarios when using a computer for audio might not be possible.</span></span> <span data-ttu-id="6d561-106">ユーザーは、会議のオーディオ部分を、携帯電話または陸上線と、会議の他の参加者&mdash;が自分の画面を共有したり、コンピューターでビデオ&mdash;を再生したりする場合に、会議のコンテンツ部分を取得します。</span><span class="sxs-lookup"><span data-stu-id="6d561-106">Users get the audio portion of the meeting through their cell phone or land line and the content portion of the meeting&mdash;such when another meeting participant shares their screen or plays a video&mdash;through their computer.</span></span>

## <a name="the-user-experience"></a><span data-ttu-id="6d561-107">ユーザーエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="6d561-107">The user experience</span></span>

### <a name="join-a-meeting-by-using-phone-for-audio"></a><span data-ttu-id="6d561-108">電話で音声を使って会議に参加する</span><span class="sxs-lookup"><span data-stu-id="6d561-108">Join a meeting by using phone for audio</span></span>

<span data-ttu-id="6d561-109">会議に参加するには、[**参加**] をクリックし、[**オーディオとビデオの設定を選択して**ください] 画面で [電話の**オーディオ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d561-109">Click **Join** to join a meeting, and then click **Phone audio** on the  **Choose your audio and video settings** screen.</span></span> <span data-ttu-id="6d561-110">ここでは、ユーザーが会議通話を使用して会議に参加したり、手動で会議にダイヤルインしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="6d561-110">From here, users can have the meeting call and join them or dial in manually to the meeting.</span></span>

![[電話] オーディオオプションのスクリーンショット](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

<span data-ttu-id="6d561-112">**チームに会議通話を許可する**</span><span class="sxs-lookup"><span data-stu-id="6d561-112">**Let the Teams meeting call**</span></span>

<span data-ttu-id="6d561-113">[**オーディオ用に電話を使う**] 画面で、ユーザーは電話番号を入力し、[**折り返し**先] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d561-113">On the **Use phone for audio** screen, the user enters their phone number, and then clicks **Call me**.</span></span> <span data-ttu-id="6d561-114">会議はユーザーを呼び出し、会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="6d561-114">The meeting calls the user and joins them to the meeting.</span></span>

![[オーディオ用電話を使う] 画面の [折り返し先] オプションのスクリーンショット](media/set-up-the-call-me-feature-for-your-users-call-me.png)

<span data-ttu-id="6d561-116">**手動でダイヤルする**</span><span class="sxs-lookup"><span data-stu-id="6d561-116">**Dial in manually**</span></span>

<span data-ttu-id="6d561-117">もう1つの方法は、会議に直接ダイヤルインすることです。</span><span class="sxs-lookup"><span data-stu-id="6d561-117">Another way to join is to dial in directly to the meeting.</span></span> <span data-ttu-id="6d561-118">[**オーディオ用に電話を使う**] 画面で、[**手動でダイヤル**する] をクリックして、会議にダイヤルインするために使用する電話番号の一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="6d561-118">On the **Use phone for audio** screen, click **Dial in manually** to get a list of phone numbers to use to dial in to the meeting.</span></span>

![[手動でダイヤルする] オプションのスクリーンショット](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a><span data-ttu-id="6d561-120">会議中に音声で問題が発生した場合に、通話を取り戻す</span><span class="sxs-lookup"><span data-stu-id="6d561-120">Get a call back when something goes wrong with audio during a meeting</span></span>

<span data-ttu-id="6d561-121">ユーザーが会議中に自分のコンピューターを使っているときに音声の問題が発生した場合、ユーザーは簡単に電話で音声通話に切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="6d561-121">If a user experiences audio issues when using their computer during a meeting, the user can easily switch to using their phone for audio.</span></span> <span data-ttu-id="6d561-122">チームは、音声またはデバイスの問題が発生したときに検出し、[**コールバック**] オプションを表示して、ユーザーが電話を使用するようにユーザーをリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="6d561-122">Teams detects when an audio or device issue occurs and redirects the user to use their phone by displaying a **Call me back** option.</span></span>

<span data-ttu-id="6d561-123">ここでは、Teams でマイクが検出されないときに表示されるメッセージと [折り返して**戻る**] オプションの例を示します。</span><span class="sxs-lookup"><span data-stu-id="6d561-123">Here's an example of the message and the **Call me back** option that's displayed when Teams doesn't detect a microphone.</span></span>

![[コールバック] オプションのスクリーンショット](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

<span data-ttu-id="6d561-125">ユーザーが [**コールバック**] をクリックすると、[**電話を使用する**] 画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6d561-125">The user clicks **Call me back**, which brings up the **Use phone for audio** screen.</span></span> <span data-ttu-id="6d561-126">このページでは、自分の電話番号を入力して、Teams 会議に参加し、会議に直接参加したり、手動で会議にダイヤルインしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="6d561-126">From here, they can enter their phone number and have the Teams meeting call and join them to the meeting or dial in manually to the meeting.</span></span>

## <a name="set-up-the-call-me-feature"></a><span data-ttu-id="6d561-127">[折り返し先] 機能を設定する</span><span class="sxs-lookup"><span data-stu-id="6d561-127">Set up the Call me feature</span></span>

<span data-ttu-id="6d561-128">組織内のユーザーに対して [折り返して呼び出す] 機能を有効にするには、次の設定を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d561-128">To enable the Call me feature for users in your organization, the following must be configured:</span></span>

- <span data-ttu-id="6d561-129">会議をスケジュールする組織内のユーザー (会議の開催者) では、電話会議が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="6d561-129">Audio Conferencing is enabled for users in your organization who schedule meetings (meeting organizers).</span></span> <span data-ttu-id="6d561-130">詳細については、「 [teams の電話会議をセットアップ](set-up-audio-conferencing-in-teams.md)する」および「 [teams でユーザーの電話会議の設定を管理](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d561-130">To learn more, see [Set up Audio Conferencing for Teams](set-up-audio-conferencing-in-teams.md) and [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

- <span data-ttu-id="6d561-131">ユーザーは会議からダイヤルアウトできます。</span><span class="sxs-lookup"><span data-stu-id="6d561-131">Users can dial out from meetings.</span></span> <span data-ttu-id="6d561-132">詳細については、「 [Teams でユーザーの電話会議の設定を管理](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d561-132">To learn more, see [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

<span data-ttu-id="6d561-133">ユーザーが会議からのダイヤルアウトを有効にしていない場合、 **[折り返し先] オプションは**利用できません。ユーザーは会議に参加するための電話を受けません。</span><span class="sxs-lookup"><span data-stu-id="6d561-133">If a user doesn't have dial out from meetings enabled, the **Call me** option isn't available and the user won't receive a call to join them to the meeting.</span></span> <span data-ttu-id="6d561-134">代わりに、電話で電話の会議に手動でダイヤルインするために使うことができる電話番号のリストが、[**オーディオの使用電話**] 画面に表示されます。</span><span class="sxs-lookup"><span data-stu-id="6d561-134">Instead, the user sees a list of phone numbers on the **Use phone for audio** screen that they can use to dial in manually to the meeting on their phone.</span></span>
