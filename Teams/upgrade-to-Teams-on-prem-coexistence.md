---
title: Microsoft Teams と Skype for Business を共存させる
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/20
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Skype for Business から Teams にアップグレードする-共存
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2c5993611a383ee9b7040dfa4b74dae1b392253f
ms.sourcegitcommit: b37632ffa22e3a6045b476c95d46889e9193a15b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "47955964"
---
# <a name="coexistence-with-teams-and-skype-for-business"></a><span data-ttu-id="da686-103">Teams と Skype for Business の共存</span><span class="sxs-lookup"><span data-stu-id="da686-103">Coexistence with Teams and Skype for Business</span></span>

<span data-ttu-id="da686-104">この記事では、どのモードやどのアップグレード方法を使用しているかに関係なく、同じ組織内で Teams と Skype for Business クライアントの両方を実行しているときに発生する可能性のある動作について説明します。</span><span class="sxs-lookup"><span data-stu-id="da686-104">This article summarizes behavior that may be experienced when running both Teams and Skype for Business clients in the same organization, regardless of what mode and what upgrade method is used:</span></span>

- [<span data-ttu-id="da686-105">会議</span><span class="sxs-lookup"><span data-stu-id="da686-105">Meetings</span></span>](#meetings)
- [<span data-ttu-id="da686-106">相互運用性</span><span class="sxs-lookup"><span data-stu-id="da686-106">Interoperability</span></span>](#interoperability)
- [<span data-ttu-id="da686-107">Teams の会話 - 相互運用とネイティブ スレッドの違い</span><span class="sxs-lookup"><span data-stu-id="da686-107">Teams conversations-Interop versus native threads</span></span>](#teams-conversations---interop-versus-native-threads)
- [<span data-ttu-id="da686-108">プレゼンス</span><span class="sxs-lookup"><span data-stu-id="da686-108">Presence</span></span>](#presence)
- [<span data-ttu-id="da686-109">フェデレーション</span><span class="sxs-lookup"><span data-stu-id="da686-109">Federation</span></span>](#federation)
- [<span data-ttu-id="da686-110">連絡先</span><span class="sxs-lookup"><span data-stu-id="da686-110">Contacts</span></span>](#contacts)



## <a name="meetings"></a><span data-ttu-id="da686-111">会議</span><span class="sxs-lookup"><span data-stu-id="da686-111">Meetings</span></span>

<span data-ttu-id="da686-112">モードに関係なく、ユーザーは、Skype for Business であれ Teams であれ、招待されたすべての種類の会議にいつでも参加できます。</span><span class="sxs-lookup"><span data-stu-id="da686-112">Regardless of their mode, users can always join any type of meeting they are invited to, whether it is Skype for Business or Teams.</span></span>  <span data-ttu-id="da686-113">ただし、ユーザーは、会議の種類に合った対応するクライアントを使用してその会議に参加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da686-113">However, users must join the meeting with a corresponding client that matches the meeting type:</span></span>

- <span data-ttu-id="da686-114">会議が Teams 会議の場合、参加者全員 (TeamsOnly、アイランド、Skype for Business のいずれのユーザーであっても) が、Teams クライアントを使用して会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="da686-114">If the meeting is a Teams meeting, all participants (whether they are TeamsOnly, Islands, or Skype for Business users) use the Teams client to join the meeting.</span></span> <span data-ttu-id="da686-115">Teams がインストールされていない場合、そのユーザーが会議に参加しようとすると、Web に移動されます。</span><span class="sxs-lookup"><span data-stu-id="da686-115">If Teams is not installed, the user will be directed to the web, upon attempting to join a meeting.</span></span>

- <span data-ttu-id="da686-116">会議が Skype for Business 会議の場合、参加者全員 (TeamsOnly、アイランド、Skype for Business のいずれのユーザーであっても) が、Skype for Business クライアントを使用して会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="da686-116">If the meeting is a Skype for Business meeting, all participants (whether they are TeamsOnly, Islands, or Skype for Business users) use the Skype for Business client to join the meeting.</span></span> <span data-ttu-id="da686-117">Skype for Business クライアントがインストールされていない場合、そのユーザーは、Skype 会議アプリ経由で参加できるように Web に移動されます。</span><span class="sxs-lookup"><span data-stu-id="da686-117">If the Skype for Business client is not installed, the user will be directed to the web to join via the Skype Meeting App.</span></span>

<span data-ttu-id="da686-118">会議を開催する場合、スケジュールされる会議の種類は、次の表に示すように開催者のモードに基づいて決定されます。</span><span class="sxs-lookup"><span data-stu-id="da686-118">When organizing meetings, the meeting type that gets scheduled is based on the mode of the organizer, as shown in the following table:</span></span>

| <span data-ttu-id="da686-119">開催者のモード</span><span class="sxs-lookup"><span data-stu-id="da686-119">Mode of organizer</span></span>    |      <span data-ttu-id="da686-120">動作</span><span class="sxs-lookup"><span data-stu-id="da686-120">Behavior</span></span> |
| :------------------ | :---------------- |
| <span data-ttu-id="da686-121">TeamsOnly、SfbWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="da686-121">TeamsOnly, SfbWithTeamsCollabAndMeetings</span></span> |    <span data-ttu-id="da686-122">すべての会議が Teams でスケジュールされます。</span><span class="sxs-lookup"><span data-stu-id="da686-122">All meetings scheduled in Teams.</span></span> <span data-ttu-id="da686-123">Skype for Business アドインは Outlook では使用できません。</span><span class="sxs-lookup"><span data-stu-id="da686-123">Skype for Business add-in is not available in Outlook.</span></span> | 
| <span data-ttu-id="da686-124">SfbWithTeamsCollab、SfbOnly</span><span class="sxs-lookup"><span data-stu-id="da686-124">SfbWithTeamsCollab, SfbOnly</span></span>   | <span data-ttu-id="da686-125">すべての会議が Skype for Business でスケジュールされます。</span><span class="sxs-lookup"><span data-stu-id="da686-125">All meetings scheduled in Skype for Business.</span></span> <span data-ttu-id="da686-126">Teams アドインは Outlook では使用できません。</span><span class="sxs-lookup"><span data-stu-id="da686-126">Teams add-in is not available in Outlook.</span></span> | 
| <span data-ttu-id="da686-127">アイランド</span><span class="sxs-lookup"><span data-stu-id="da686-127">Islands</span></span> | <span data-ttu-id="da686-128">既定では、会議は Skype for Business または Teams のいずれかでスケジュールできます。</span><span class="sxs-lookup"><span data-stu-id="da686-128">By default, meetings can be scheduled in either Skype for Business or Teams.</span></span> <span data-ttu-id="da686-129">両方のアドインを Outlook で使用できます。</span><span class="sxs-lookup"><span data-stu-id="da686-129">Both add-ins are available in Outlook.</span></span> <span data-ttu-id="da686-130">ただし、必要に応じて、TeamsMeetingPolicy のインスタンスを PreferredMeetingProviderForIslandsMode = Teams で割り当てることによって、島々のユーザーに常に Teams の会議をスケジュールするように要求することができます。</span><span class="sxs-lookup"><span data-stu-id="da686-130">However, you can optionally require that users in Islands always schedule meetings in Teams by assigning them an instance of TeamsMeetingPolicy with the PreferredMeetingProviderForIslandsMode=Teams.</span></span>| 


## <a name="interoperability"></a><span data-ttu-id="da686-131">相互運用性</span><span class="sxs-lookup"><span data-stu-id="da686-131">Interoperability</span></span>

<span data-ttu-id="da686-132">Teams では、特定のシナリオで Skype for Business との相互運用性をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="da686-132">Teams supports interoperability (“interop”) with Skype for Business in certain scenarios.</span></span> <span data-ttu-id="da686-133">相互運用通信とは、Skype for Business ユーザーと Teams ユーザーとの間のチャットや通話を意味しています。</span><span class="sxs-lookup"><span data-stu-id="da686-133">Interop communication refers to a chat or call between a Skype for Business user and a Teams user.</span></span>  <span data-ttu-id="da686-134">相互運用通信は、2 人のユーザー間でのみ可能です。マルチパーティ チャットや通信、別のユーザーを追加することはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="da686-134">Interop communication is only possible between two users; multi-party chat/calling or adding additional users is not supported.</span></span>

<span data-ttu-id="da686-135">2 人のユーザー間での相互運用チャットや通信は、次の各条件が満たされている場合に作成されます。</span><span class="sxs-lookup"><span data-stu-id="da686-135">An interop chat or call between two users is created when each of the following are true:</span></span>

- <span data-ttu-id="da686-136">一方のユーザーは Teams を使用し、他方のユーザーは Skype for Business を使用している。</span><span class="sxs-lookup"><span data-stu-id="da686-136">One user is using Teams and the other is using Skype for Business.</span></span>

- <span data-ttu-id="da686-137">どちらも同じ組織内のユーザーである場合は、最初の通信の受信者のモードがアイランドではない (アイランド モードの場合、通信は同一のクライアントに配信される)。</span><span class="sxs-lookup"><span data-stu-id="da686-137">The mode of the recipient of the initial communication is NOT Islands (otherwise the communication would land in the same client) if both users are in the same organization.</span></span> <span data-ttu-id="da686-138">フェデレーション シナリオの場合、送信側のユーザーは Teams を使用しており、受信者は TeamsOnly モードではない。</span><span class="sxs-lookup"><span data-stu-id="da686-138">In federated scenarios, the sending user is using Teams, and the recipient is not in TeamsOnly mode.</span></span> 

- <span data-ttu-id="da686-139">Teams ユーザーは、オンプレミスに所属している Skype for Business アカウントも所有してはいない。</span><span class="sxs-lookup"><span data-stu-id="da686-139">The Teams user does NOT also have a Skype for Business account homed on-premises.</span></span> 

<span data-ttu-id="da686-140">相互運用通信では、チャットはプレーンテキストのみです。</span><span class="sxs-lookup"><span data-stu-id="da686-140">Within the interop communication, chat is plain-text only.</span></span> <span data-ttu-id="da686-141">また、*相互運用チャット自体*では、ファイル共有や画面共有は行えません。</span><span class="sxs-lookup"><span data-stu-id="da686-141">In addition, file sharing and screen sharing are not possible *in the interop chat itself*.</span></span> <span data-ttu-id="da686-142">ただし、次のようにして相互運用チャット内からオンデマンド会議を作成することにより、相互運用会話中のユーザーは簡単にファイル共有や画面共有を実現できます。</span><span class="sxs-lookup"><span data-stu-id="da686-142">However, users in an interop conversation can easily achieve file and/or screen sharing by creating an on-demand meeting, from within the interop chat, as described below:</span></span>

- <span data-ttu-id="da686-143">Teams ユーザーが画面を共有しようとすると、オンデマンドの Teams 会議が自動的に作成され、Skype for Business ユーザーのクライアントにその会議への招待リンクが送信されます。</span><span class="sxs-lookup"><span data-stu-id="da686-143">If the Teams user attempts to share their screen, an on-demand Teams meeting is automatically created and an invite link to that meeting is sent to the Skype for Business user’s client.</span></span> <span data-ttu-id="da686-144">リンクをクリックすると、Skype for Business ユーザーの Teams が開き、会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="da686-144">Upon clicking the link, the Skype for Business user will open Teams and join the meeting.</span></span> <span data-ttu-id="da686-145">これで、両方のユーザーが Teams 会議に参加する形になり、必要に応じて共有を行なえます。</span><span class="sxs-lookup"><span data-stu-id="da686-145">Both users are now in a Teams meeting and can share as needed.</span></span>

- <span data-ttu-id="da686-146">Skype for Business ユーザーが 2018 以降のクライアントを使用していて、任意のコンテンツを共有しようとすると、オンデマンドの Skype for Business 会議が自動的に作成され、Teams ユーザーのクライアントにその会議への招待リンクが送信されます。</span><span class="sxs-lookup"><span data-stu-id="da686-146">If the Skype for Business user is using a client from 2018 or later and attempts to share any content, an on-demand Skype for Business meeting is automatically created and an invite link to that meeting is sent to the Teams user’s client.</span></span> <span data-ttu-id="da686-147">リンクをクリックすると、Teams ユーザーがその Skype for Business 会議に参加するための試行が実行されます。</span><span class="sxs-lookup"><span data-stu-id="da686-147">Upon clicking the link, the Teams user will attempt to join the Skype for Business meeting.</span></span> <span data-ttu-id="da686-148">その Teams ユーザーが Skype for Business クライアントをインストール済みの場合は、そのクライアントが開き、ユーザーはログインするように求められます (ログインしていない場合)。</span><span class="sxs-lookup"><span data-stu-id="da686-148">If the Teams user has the Skype for Business client installed, it will open and the user is prompted to sign in (if not already signed in).</span></span>  <span data-ttu-id="da686-149">その Teams ユーザーが Skype for Business クライアントをインストールしていない場合は、Web バージョンを使用するように求められます。</span><span class="sxs-lookup"><span data-stu-id="da686-149">If the Teams user does not have the Skype for Business client installed, the user will be prompted to use the web version.</span></span> <span data-ttu-id="da686-150">両方のユーザーがログインすると、どちらも Skype for Business 会議に参加している形になり、必要に応じて共有を行なえます。</span><span class="sxs-lookup"><span data-stu-id="da686-150">Once both users are signed in, they are in a Skype for Business meeting and can share as needed.</span></span>

## <a name="teams-conversations---interop-versus-native-threads"></a><span data-ttu-id="da686-151">Teams の会話 - 相互運用とネイティブ スレッドの違い</span><span class="sxs-lookup"><span data-stu-id="da686-151">Teams conversations - Interop versus native threads</span></span>

<span data-ttu-id="da686-152">相互運用通信はネイティブな Teams の会話の一部の機能をサポートしていないため、Teams クライアントは、"Teams から Teams" の通信と "Teams から Skype for Business" の通信の会話スレッドを別個に維持します。</span><span class="sxs-lookup"><span data-stu-id="da686-152">Because interop communications do not support all the features of native Teams conversation, the Teams client maintains separate conversation threads for Teams-to-Teams and Teams-to-Skype for Business communication.</span></span> <span data-ttu-id="da686-153">これらの会話は、ユーザー インターフェイスに異なる方法で表示されます。相互運用スレッドは、通常のネイティブな Teams スレッドと次の点で区別できます。</span><span class="sxs-lookup"><span data-stu-id="da686-153">These conversations are rendered differently in the user interface: Interop threads can be differentiated from a regular native Teams thread by:</span></span>

- <span data-ttu-id="da686-154">リッチ テキスト、ファイル/画面共有、ユーザー追加禁止のコントロールが表示されない。</span><span class="sxs-lookup"><span data-stu-id="da686-154">Lack of controls for rich text, file/screen sharing, inability to add users.</span></span>
- <span data-ttu-id="da686-155">ターゲット ユーザーのアイコンが変更され、Skype for Business を意味する S が表示される。</span><span class="sxs-lookup"><span data-stu-id="da686-155">A modification to the target user’s icon, showing an “S” for Skype for Business.</span></span>

<span data-ttu-id="da686-156">これらの違いを次のスクリーンショットに示します。</span><span class="sxs-lookup"><span data-stu-id="da686-156">These differences are shown in the following screenshots:</span></span>

<span data-ttu-id="da686-157">ユーザー G3 Test とのネイティブな "Teams から Teams" の会話</span><span class="sxs-lookup"><span data-stu-id="da686-157">A native Teams-to-Teams conversation with User G3 Test</span></span>

![ネイティブな "Teams から Teams" の会話を示す図](media/teams-upgrade-native-thread.png)

<span data-ttu-id="da686-159">同じユーザー G3 Test との相互運用会話</span><span class="sxs-lookup"><span data-stu-id="da686-159">An interop conversation with the same User G3 Test</span></span>

![相互運用の "Teams から Teams" の会話を示す図](media/teams-upgrade-interop-thread.png)

<span data-ttu-id="da686-161">会話スレッドが一旦作成されると、その種類は変更されません。</span><span class="sxs-lookup"><span data-stu-id="da686-161">Once a conversation thread is created, its type never changes.</span></span> <span data-ttu-id="da686-162">作成された Teams の相互運用スレッドは、常にターゲット ユーザーの Skype for Business クライアントにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="da686-162">Once created, an interop thread in Teams will always route to the target user’s Skype for Business client.</span></span> <span data-ttu-id="da686-163">ネイティブ スレッドは、常にターゲット ユーザーの Teams クライアントにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="da686-163">A native thread will always route to the target user’s Teams client.</span></span>  <span data-ttu-id="da686-164">受信者ユーザーのモードが変わると、そのユーザーに対する既存の Teams スレッドは機能しなくなり、次のスクリーンショットに示すように、メモと、ネイティブな会話を新たに始めるためのリンクがそのチャット上に表示されます。</span><span class="sxs-lookup"><span data-stu-id="da686-164">If a recipient user’s mode changes, existing Teams threads to that user will no longer function and a note will be displayed on that chat with a link to start a new native conversation as shown in the following screenshot.</span></span>


![アップグレードした Skype for Business ユーザーとのチャットを示す図](media/teams-upgrade-chat-with-upgraded-sfb-user.png)

## <a name="presence"></a><span data-ttu-id="da686-166">プレゼンス</span><span class="sxs-lookup"><span data-stu-id="da686-166">Presence</span></span>

<span data-ttu-id="da686-167">特定のユーザーのプレゼンスは、クライアントを介したサービスでのユーザーのアクティビティに基づきます。</span><span class="sxs-lookup"><span data-stu-id="da686-167">Presence for a given user is based on the user’s activity in the service via the client.</span></span> <span data-ttu-id="da686-168">プレゼンスは、他のユーザーが表示できるように公開されます。</span><span class="sxs-lookup"><span data-stu-id="da686-168">The presence is then published for other users to see.</span></span>  <span data-ttu-id="da686-169">Skype for Business と Teams は、別個のクライアントを持つ別個のサービスなので、各サービスはユーザーに関する独自のプレゼンス状態を持ちます。</span><span class="sxs-lookup"><span data-stu-id="da686-169">Skype for Business and Teams are separate services with separate clients, so each service has its own presence state for a user.</span></span>   <span data-ttu-id="da686-170">Teams と Skype for Business Online のプレゼンス サービスの間では、同期も行われます。</span><span class="sxs-lookup"><span data-stu-id="da686-170">There is also synchronization between the presence services in Teams and in Skype for Business Online.</span></span>  <span data-ttu-id="da686-171">これにより、必要に応じて一方のサービスが他方のサービスからユーザーのプレゼンスを公開することが可能になります。</span><span class="sxs-lookup"><span data-stu-id="da686-171">This allows one service to potentially publish the presence of the user from the other service if needed.</span></span> 

<span data-ttu-id="da686-172">プレゼンスの公開動作は、ユーザーのモードに基づいて決定されます。</span><span class="sxs-lookup"><span data-stu-id="da686-172">Presence publishing behavior is based on the user’s mode.</span></span> <span data-ttu-id="da686-173">次の 3 つの基本的なケースがあります。</span><span class="sxs-lookup"><span data-stu-id="da686-173">There are three basic cases:</span></span>

- <span data-ttu-id="da686-174">ユーザーが TeamsOnly モードの場合、他のすべてのユーザーには、使用するクライアントに関係なく、そのユーザーの Teams プレゼンスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="da686-174">If a user is in TeamsOnly mode, all other users see Teams presence for that user, regardless of which client they use.</span></span>

- <span data-ttu-id="da686-175">ユーザーが Skype for Business のいずれかのモードの場合、他のすべてのユーザーには、使用するクライアントに関係なく、そのユーザーの Skype for Business プレゼンスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="da686-175">If a user is in any of the Skype for Business modes, all other users see Skype for Business presence for that user, regardless of which client they use.</span></span>

- <span data-ttu-id="da686-176">ユーザーがアイランド モードの場合、Skype for Business と Teams で公開されるプレゼンスは独立しているため、同一組織内のユーザーに表示されるプレゼンスは、相手側ユーザーのクライアントによって決まります。</span><span class="sxs-lookup"><span data-stu-id="da686-176">If a user is in Islands mode, presence published in Skype for Business and Teams are independent, so the presence shown to users within the same organization will depend on the client of the other user.</span></span> <span data-ttu-id="da686-177">フェデレーション組織のユーザーには、Skype for Business のアクティビティに基づいてそのユーザーのプレゼンスが表示されます。これは、アイランド モードのユーザーに対するフェデレーション トラフィックが Skype for Business に配信されるためです。</span><span class="sxs-lookup"><span data-stu-id="da686-177">Users in federated organizations will see presence of that user based on their Skype for Business activity, since federated traffic to an Islands mode user lands in Skype for Business.</span></span>

<span data-ttu-id="da686-178">たとえば、ユーザー A がアイランド モードであるとします。</span><span class="sxs-lookup"><span data-stu-id="da686-178">For example, Assume User A is in Islands mode.</span></span> <span data-ttu-id="da686-179">ユーザー A が Teams ではアクティブで Skype for Business にはサインインしていない場合、他のユーザーには、Teams クライアントからはユーザー A はアクティブであるように見えますが、Skype for Business クライアントではユーザー A はオフラインであるように見えます。</span><span class="sxs-lookup"><span data-stu-id="da686-179">If User A is active in Teams but is not signed in to Skype for Business, other users would see User A as active from their Teams client, but in their Skype for Business client they would see User A as offline.</span></span> <span data-ttu-id="da686-180">これは仕様です。クライアントを実行していない場合、ユーザー A にはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="da686-180">This is by design, since User A cannot be reached if they are not running the client.</span></span> 


## <a name="federation"></a><span data-ttu-id="da686-181">フェデレーション</span><span class="sxs-lookup"><span data-stu-id="da686-181">Federation</span></span>

<span data-ttu-id="da686-182">Skype for Business を使用している他のユーザーへの Teams からのフェデレーションには、Teams ユーザーが Skype for Business のオンラインに所属している必要があります。</span><span class="sxs-lookup"><span data-stu-id="da686-182">Federation from Teams to another user using Skype for Business requires the Teams user to be homed online in Skype for Business.</span></span> <span data-ttu-id="da686-183">TeamsUpgradePolicy は、着信するフェデレーションされたチャットと通話のルーティングを制御します。</span><span class="sxs-lookup"><span data-stu-id="da686-183">TeamsUpgradePolicy governs routing for incoming federated chats and calls.</span></span> <span data-ttu-id="da686-184">フェデレーションされたルーティングの動作は、同じテナントの場合のシナリオと同じものです (アイランド モードの場合を除く)。</span><span class="sxs-lookup"><span data-stu-id="da686-184">Federated routing behavior is the same as for same-tenant scenarios, except in Islands mode.</span></span> <span data-ttu-id="da686-185">受信者がアイランド モードの場合の動作は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="da686-185">When recipients are in Islands mode:</span></span>

- <span data-ttu-id="da686-186">Teams から開始されたチャットと通話は、受信者がフェデレーションされたテナントにいる場合、Skype for Business に配信されます。</span><span class="sxs-lookup"><span data-stu-id="da686-186">Chats and calls initiated from Teams land in Skype for Business if the recipient is in a federated tenant.</span></span>
- <span data-ttu-id="da686-187">Teams から開始されたチャットと通話は、受信者が同じテナントにいる場合、Teams に配信されます。</span><span class="sxs-lookup"><span data-stu-id="da686-187">Chats and calls initiated from Teams land in Teams if the recipient is in the same tenant.</span></span>
- <span data-ttu-id="da686-188">Skype for Business から開始されたチャットと通話は常に、Skype for Business に配信されます。</span><span class="sxs-lookup"><span data-stu-id="da686-188">Chats and calls initiated from Skype for Business always land in Skype for Business.</span></span>

<span data-ttu-id="da686-189">フェデレーションされたチャットは、ネイティブスレッドまたは相互運用スレッドのいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="da686-189">A federated chat can either be a native thread or an interop thread.</span></span> <span data-ttu-id="da686-190">「 [チームの会話---相互運用機能とネイティブスレッド](#teams-conversations---interop-versus-native-threads)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="da686-190">See [Teams Conversations ---interop-versus-native-threads](#teams-conversations---interop-versus-native-threads).</span></span>

- <span data-ttu-id="da686-191">受信者と送信者が両方ともチームのアップグレードモードである場合、会話はネイティブのチャットエクスペリエンスになり、すべての豊富なメッセージング機能と通話機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="da686-191">If the receiver and sender are both in TeamsOnly upgrade mode, the conversation will be a native chat experience which includes all the rich messaging and calling capabilities.</span></span> <span data-ttu-id="da686-192">詳細については、「 [Teams の外部 (フェデレーション) ユーザー向けのネイティブチャットの操作」](native-chat-for-external-users.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da686-192">To learn more, read [Native chat experience for external (federated) users in Teams](native-chat-for-external-users.md).</span></span> 

- <span data-ttu-id="da686-193">いずれかの会話参加者がチームのアップグレードモードになっていない場合、会話はテキストのみのメッセージでの相互運用機能の操作環境のままです。</span><span class="sxs-lookup"><span data-stu-id="da686-193">If either of the conversation participants is NOT in TeamsOnly upgrade mode, the conversation remains an interop experience with text-only messages.</span></span> <span data-ttu-id="da686-194">ユーザー インターフェイスには、そのユーザーが外部ユーザーであることを示すメモがあることを除けば、同一テナントの相互運用スレッドと同様の方法でフェデレーション チャットが表示されます。</span><span class="sxs-lookup"><span data-stu-id="da686-194">The user interface exposes federated chats in a similar manner to same-tenant interop threads, except there is a note indicating the user is external.</span></span>

<span data-ttu-id="da686-195">詳細については、「 [Microsoft teams で外部アクセスを管理](manage-external-access.md) する」および「 [teams の外部 (フェデレーション) ユーザー向けのネイティブチャットの操作](native-chat-for-external-users.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da686-195">For more details, see [Manage external access in Microsoft Teams](manage-external-access.md) and [Native chat experience for external (federated) users in Teams](native-chat-for-external-users.md).</span></span>

## <a name="contacts"></a><span data-ttu-id="da686-196">連絡先</span><span class="sxs-lookup"><span data-stu-id="da686-196">Contacts</span></span>

<span data-ttu-id="da686-197">Teams と Skype for Business は、連絡先の別個のリストを保持します。</span><span class="sxs-lookup"><span data-stu-id="da686-197">Teams and Skype for Business have separate lists of contacts.</span></span> <span data-ttu-id="da686-198">これは、一方のシステムでなされた連絡先の追加、削除、変更が、他方のシステムには同期されないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="da686-198">This means that contact additions, removal, and modifications made in one system are not synchronized to the other system.</span></span> <span data-ttu-id="da686-199">ただし、次の 2 つの特定のイベントのどちらかが発生すると、Skype for Business の連絡先が Teams に自動的にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="da686-199">However, contacts from Skype for Business are automatically copied over to Teams when either of two specific events occur:</span></span> 

- <span data-ttu-id="da686-200">Skype for Business Online ユーザーが初めて Teams にログオンすると、Skype for Business の連絡先が Teams にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="da686-200">For any Skype for Business Online user, the first time they log onto Teams, contacts from Skype for Business will be copied over to Teams.</span></span>  <span data-ttu-id="da686-201">この動作は、Skype for Business Server のオンプレミス アカウントを持つユーザーには利用できません。</span><span class="sxs-lookup"><span data-stu-id="da686-201">This behavior is not available for users with an on-premises account in Skype for Business Server.</span></span>  

- <span data-ttu-id="da686-202">ユーザーが TeamsOnly にアップグレードされ (TeamsUpgradePolicy を割り当てるか Move-CsUser -MoveToTeams で) た後に、次にユーザーが Teams にログインすると、Skype for Business の既存の連絡先が Teams の既存の連絡先とマージされます。</span><span class="sxs-lookup"><span data-stu-id="da686-202">After a user is upgraded to TeamsOnly (either via assigning TeamsUpgradePolicy or via Move-CsUser -MoveToTeams), the next time a user logs into Teams, existing contacts in Skype for Business will be merged with existing contacts already in Teams.</span></span> <span data-ttu-id="da686-203">この動作は、ユーザーの Skype for Business アカウントがオンプレミスかオンラインである場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="da686-203">This behavior happens whether the user’s Skype for Business Account is homed on-premises or online.</span></span> 

<span data-ttu-id="da686-204">どちらの場合も、Skype for Business から Teams への連絡先の転送は非同期なので、連絡先が Teams に表示されるまでに数分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="da686-204">In both cases, the transfer of contacts from Skype for Business to Teams is asynchronous so it may be a few minutes before contacts appear in Teams.</span></span> <span data-ttu-id="da686-205">上述の 2 つのイベントがコピーをトリガーします。</span><span class="sxs-lookup"><span data-stu-id="da686-205">The two events above are what trigger the copy.</span></span>  

## <a name="related-links"></a><span data-ttu-id="da686-206">関連リンク</span><span class="sxs-lookup"><span data-stu-id="da686-206">Related links</span></span>

[<span data-ttu-id="da686-207">Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス</span><span class="sxs-lookup"><span data-stu-id="da686-207">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="da686-208">Skype for Business Server と Microsoft 365 または Office 365 間のハイブリッド接続を構成する</span><span class="sxs-lookup"><span data-stu-id="da686-208">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="da686-209">オンプレミスとクラウドの間でユーザーを移動する</span><span class="sxs-lookup"><span data-stu-id="da686-209">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="da686-210">共存およびアップグレードを設定する</span><span class="sxs-lookup"><span data-stu-id="da686-210">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="da686-211">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="da686-211">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="da686-212">会議移行サービス (MMS) を使用する</span><span class="sxs-lookup"><span data-stu-id="da686-212">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

