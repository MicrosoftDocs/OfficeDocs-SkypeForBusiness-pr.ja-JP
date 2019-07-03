---
title: ユーザー用に通話機能を設定する
author: LanaChin
ms.author: v-lanac
ms.reviewer: macai
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: ユーザーがオーディオ用にコンピューターを使用している可能性がある場合に、ユーザーが電話でオーディオ部分に参加できるように、Teams の [折り返し] 機能を設定する方法について説明します。
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3f1ffee416b1d5674e831fda4c5bb15a89c510f4
ms.sourcegitcommit: 1ddd29e3839e50387efb4ec7b9d2154991bb2642
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2019
ms.locfileid: "35432140"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a><span data-ttu-id="f223f-103">ユーザー用に通話機能を設定する</span><span class="sxs-lookup"><span data-stu-id="f223f-103">Set up the Call me feature for your users</span></span>

<span data-ttu-id="f223f-104">Microsoft Teams の [**折り返し**] 機能を使用すると、ユーザーは電話で会議のオーディオ部分に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="f223f-104">In Microsoft Teams, the **Call me** feature gives users a way to join the audio portion of a meeting by phone.</span></span> <span data-ttu-id="f223f-105">これは、オーディオ用のコンピューターを使うことができない場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="f223f-105">This is handy in scenarios when using a computer for audio might not be possible.</span></span> <span data-ttu-id="f223f-106">ユーザーは、会議のオーディオ部分を、携帯電話または陸上線と、会議の他の参加者&mdash;が自分の画面を共有したり、コンピューターでビデオ&mdash;を再生したりする場合に、会議のコンテンツ部分を取得します。</span><span class="sxs-lookup"><span data-stu-id="f223f-106">Users get the audio portion of the meeting through their cell phone or land line and the content portion of the meeting&mdash;such when another meeting participant shares their screen or plays a video&mdash;through their computer.</span></span>

## <a name="the-user-experience"></a><span data-ttu-id="f223f-107">ユーザーエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="f223f-107">The user experience</span></span>

<span data-ttu-id="f223f-108">会議に参加するには、[**参加**] をクリックし、[**オーディオとビデオの設定を選択して**ください] 画面で [電話の**オーディオ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f223f-108">Click **Join** to join a meeting, and then click **Phone audio** on the  **Choose your audio and video settings** screen.</span></span> <span data-ttu-id="f223f-109">ここでは、ユーザーが会議通話を使用して会議に参加したり、手動で会議にダイヤルインしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="f223f-109">From here, users can have the meeting call and join them or dial in manually to the meeting.</span></span>

![[電話] オーディオオプションのスクリーンショット](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

<span data-ttu-id="f223f-111">**チームに会議通話を許可する**</span><span class="sxs-lookup"><span data-stu-id="f223f-111">**Let the Teams meeting call**</span></span>

<span data-ttu-id="f223f-112">[**オーディオ用に電話を使う**] 画面で、ユーザーは電話番号を入力し、[**折り返し**先] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f223f-112">On the **Use phone for audio** screen, the user enters their phone number, and then clicks **Call me**.</span></span> <span data-ttu-id="f223f-113">会議はユーザーを呼び出し、会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="f223f-113">The meeting calls the user and joins them to the meeting.</span></span>

![[オーディオ用電話を使う] 画面の [折り返し先] オプションのスクリーンショット](media/set-up-the-call-me-feature-for-your-users-call-me.png)

<span data-ttu-id="f223f-115">**手動でダイヤルする**</span><span class="sxs-lookup"><span data-stu-id="f223f-115">**Dial in manually**</span></span>

<span data-ttu-id="f223f-116">もう1つの方法は、会議に直接ダイヤルインすることです。</span><span class="sxs-lookup"><span data-stu-id="f223f-116">Another way to join is to dial in directly to the meeting.</span></span> <span data-ttu-id="f223f-117">[**オーディオ用に電話を使う**] 画面で、[**手動でダイヤル**する] をクリックして、会議にダイヤルインするために使用する電話番号の一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="f223f-117">On the **Use phone for audio** screen, click **Dial in manually** to get a list of phone numbers to use to dial in to the meeting.</span></span>

![[手動でダイヤルする] オプションのスクリーンショット](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

## <a name="set-up-the-call-me-feature"></a><span data-ttu-id="f223f-119">[折り返し先] 機能を設定する</span><span class="sxs-lookup"><span data-stu-id="f223f-119">Set up the Call me feature</span></span>

<span data-ttu-id="f223f-120">組織内のユーザーに対して [折り返して呼び出す] 機能を有効にするには、次の設定を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="f223f-120">To enable the Call me feature for users in your organization, the following must be configured:</span></span>

- <span data-ttu-id="f223f-121">会議をスケジュールする組織内のユーザー (会議の開催者) では、電話会議が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="f223f-121">Audio Conferencing is enabled for users in your organization who schedule meetings (meeting organizers).</span></span> <span data-ttu-id="f223f-122">詳細については、「 [teams の電話会議をセットアップ](set-up-audio-conferencing-in-teams.md)する」および「 [teams でユーザーの電話会議の設定を管理](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f223f-122">To learn more, see [Set up Audio Conferencing for Teams](set-up-audio-conferencing-in-teams.md) and [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

- <span data-ttu-id="f223f-123">ユーザーは会議からダイヤルアウトできます。</span><span class="sxs-lookup"><span data-stu-id="f223f-123">Users can dial out from meetings.</span></span> <span data-ttu-id="f223f-124">詳細については、「 [Teams でユーザーの電話会議の設定を管理](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f223f-124">To learn more, see [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

<span data-ttu-id="f223f-125">ユーザーが会議からのダイヤルアウトを有効にして\*\*\*\* いない場合、[折り返し先] オプションは利用できません。ユーザーは会議に参加するための電話を受けません。</span><span class="sxs-lookup"><span data-stu-id="f223f-125">If a user doesn't have dial out from meetings enabled, the **Call me** option isn't available and the user won't receive a call to join them to the meeting.</span></span> <span data-ttu-id="f223f-126">代わりに、電話で電話の会議に手動でダイヤルインするために使うことができる電話番号のリストが、[**オーディオの使用電話**] 画面に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f223f-126">Instead, the user sees a list of phone numbers on the **Use phone for audio** screen that they can use to dial in manually to the meeting on their phone.</span></span>

