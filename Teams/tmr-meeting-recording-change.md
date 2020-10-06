---
title: 会議の記録に OneDrive と SharePoint を使用する
author: cichur
ms.author: v-cichur
ms.reviewer: hao.moy
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Microsoft Teams でストリームから OneDrive for business および SharePoint 会議のレコーディングストレージに切り替える方法について説明します。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b31972ed662b6752286fa2ff33b80150496cfb0f
ms.sourcegitcommit: 3b54a56ec1fe4366580621e19cdbb6a833a01161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2020
ms.locfileid: "48361337"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a><span data-ttu-id="e2b47-103">OneDrive for Business と、会議の記録に SharePoint または Stream を使用する</span><span class="sxs-lookup"><span data-stu-id="e2b47-103">Use OneDrive for Business and SharePoint or Stream for meeting recordings</span></span>

> [!Note]
> <span data-ttu-id="e2b47-104">Microsoft Stream の使用から 会議の記録用の OneDrive for Business および SharePoint への変更は段階的なアプローチになります。</span><span class="sxs-lookup"><span data-stu-id="e2b47-104">The change from using Microsoft Stream to OneDrive for Business and SharePoint for meeting recordings will be a phased approach.</span></span> <span data-ttu-id="e2b47-105">テナント管理者は、起動時にこの新しいワークフローオプションを今すぐ選ぶことができます。また、2020年10月に OneDrive for Business と SharePoint に自動アップロードされます。</span><span class="sxs-lookup"><span data-stu-id="e2b47-105">At launch, tenant admins can choose this new workflow option today and will start seeing recordings auto-upload to OneDrive for Business and SharePoint in October 2020.</span></span> <span data-ttu-id="e2b47-106">11月では、Stream の使用を続けたい場合と、2021の初期段階では、すべてのユーザーが OneDrive for Business と SharePoint を使って新しい会議のレコーディングを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2b47-106">In November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

<span data-ttu-id="e2b47-107">Microsoft Teams には、会議の記録を保存するための新しい方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="e2b47-107">Microsoft Teams has a new method for saving meeting recordings.</span></span> <span data-ttu-id="e2b47-108">ストリームからの出発として、このメソッドは microsoft 365 の Microsoft OneDrive と SharePoint を使用し、多くの利点を提供します。</span><span class="sxs-lookup"><span data-stu-id="e2b47-108">As a departure from Stream, the method uses Microsoft OneDrive and SharePoint in Microsoft 365 and offers many benefits.</span></span>

<span data-ttu-id="e2b47-109">OneDrive for Business と SharePoint を使ったレコーディングの保存には、次のような利点があります。</span><span class="sxs-lookup"><span data-stu-id="e2b47-109">The benefits of using OneDrive for Business and SharePoint for storing recordings include:</span></span>

- <span data-ttu-id="e2b47-110">Teams 会議レコーディングのアイテム保持ポリシー (TMR) (S + C E5 autoretention ラベル)</span><span class="sxs-lookup"><span data-stu-id="e2b47-110">Retention policies for Teams meeting recording (TMR) (S+C E5 autoretention labels)</span></span>
- <span data-ttu-id="e2b47-111">OneDrive for Business と SharePoint の情報ガバナンスの利点</span><span class="sxs-lookup"><span data-stu-id="e2b47-111">Benefit from OneDrive for Business and SharePoint information governance</span></span>
- <span data-ttu-id="e2b47-112">簡単にアクセス許可と共有を設定する</span><span class="sxs-lookup"><span data-stu-id="e2b47-112">Easy to set permissions and sharing</span></span>
- <span data-ttu-id="e2b47-113">明確な共有のみを使用して、ゲスト (外部ユーザー) とのレコーディングを共有する</span><span class="sxs-lookup"><span data-stu-id="e2b47-113">Share recordings with guests (external users) with explicit share only</span></span>
- <span data-ttu-id="e2b47-114">アクセスフローを要求する</span><span class="sxs-lookup"><span data-stu-id="e2b47-114">Request access flow</span></span>
- <span data-ttu-id="e2b47-115">OneDrive for Business と SharePoint の共有リンクを提供する</span><span class="sxs-lookup"><span data-stu-id="e2b47-115">Provide OneDrive for Business and SharePoint shared links</span></span>
- <span data-ttu-id="e2b47-116">クォータの増加</span><span class="sxs-lookup"><span data-stu-id="e2b47-116">Increased quota</span></span>
- <span data-ttu-id="e2b47-117">会議のレコーディングは、より高速に使用できます</span><span class="sxs-lookup"><span data-stu-id="e2b47-117">Meeting  recordings are available faster</span></span>
- <span data-ttu-id="e2b47-118">**ローカル** テナントのサポートに移動する</span><span class="sxs-lookup"><span data-stu-id="e2b47-118">**Go local** tenant support</span></span>
- <span data-ttu-id="e2b47-119">複数地域のサポート–レコーディングは、そのユーザーに固有の地域に保存されます。</span><span class="sxs-lookup"><span data-stu-id="e2b47-119">Multi-geo support – recordings are stored in a region specific to that user</span></span>
- <span data-ttu-id="e2b47-120">独自のキー (BYOK) のサポートを利用する</span><span class="sxs-lookup"><span data-stu-id="e2b47-120">Bring your own key (BYOK) support</span></span>
- <span data-ttu-id="e2b47-121">議事録の品質とスピーカーの属性を改善しました</span><span class="sxs-lookup"><span data-stu-id="e2b47-121">Improved Transcript quality and speaker attribution</span></span>

<span data-ttu-id="e2b47-122">次の点について考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2b47-122">There are some limitations to consider:</span></span>

- <span data-ttu-id="e2b47-123">英語専用のクローズドキャプションとトランスクリプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e2b47-123">There will be English-only closed captions and transcripts.</span></span>
- <span data-ttu-id="e2b47-124">トランスクリプトまたはコンテンツを検索することはできません。</span><span class="sxs-lookup"><span data-stu-id="e2b47-124">You won't be able to search transcripts or their content.</span></span>
- <span data-ttu-id="e2b47-125">トランスクリプトを編集することはできませんが、字幕のオン/オフを切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="e2b47-125">You won’t be able to edit the transcripts, but you'll be able to toggle captions off/on.</span></span>
- <span data-ttu-id="e2b47-126">レコーディングを共有している相手を管理することはできますが、共有アクセス権を持つユーザーがレコーディングをダウンロードするのをブロックすることはできません。</span><span class="sxs-lookup"><span data-stu-id="e2b47-126">You can control with whom you share the recording, but you won't be able to block people with shared access from downloading the recording.</span></span>
- <span data-ttu-id="e2b47-127">レコーディングの保存が完了したときにメールを受け取ることはありませんが、レコーディングが完了したら会議のチャットに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e2b47-127">You'll not get an email when the recording finishes saving, but the recording will appear in the meeting chat once it’s finished.</span></span> <span data-ttu-id="e2b47-128">これは、以前のストリームで行ったよりもはるかに短時間で行われます</span><span class="sxs-lookup"><span data-stu-id="e2b47-128">This will happen much quicker than it did in Stream previously</span></span>

<span data-ttu-id="e2b47-129">詳細については、「会議の記録」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e2b47-129">Watch "Meeting Recording" for more information.</span></span>

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a><span data-ttu-id="e2b47-130">OneDrive for Business と SharePoint の会議のレコーディングオプションを設定する</span><span class="sxs-lookup"><span data-stu-id="e2b47-130">Set up the meeting recording option for OneDrive for Business and SharePoint</span></span>

1. <span data-ttu-id="e2b47-131">Skype For Business Online PowerShell 管理コンソールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="e2b47-131">Install the Skype For Business Online PowerShell admin console.</span></span>

    <span data-ttu-id="e2b47-132">a.</span><span class="sxs-lookup"><span data-stu-id="e2b47-132">a.</span></span> <span data-ttu-id="e2b47-133">[Skype For Business Online Powershell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="e2b47-133">Download [Skype for Business Online Powershell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide).</span></span>

    <span data-ttu-id="e2b47-134">b.</span><span class="sxs-lookup"><span data-stu-id="e2b47-134">b.</span></span> <span data-ttu-id="e2b47-135">指示に従ってインストールします。</span><span class="sxs-lookup"><span data-stu-id="e2b47-135">Follow the prompts to install it.</span></span>

    <span data-ttu-id="e2b47-136">c.</span><span class="sxs-lookup"><span data-stu-id="e2b47-136">c.</span></span> <span data-ttu-id="e2b47-137">コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="e2b47-137">Restart your machine.</span></span>

2. <span data-ttu-id="e2b47-138">管理者として PowerShell を起動する</span><span class="sxs-lookup"><span data-stu-id="e2b47-138">Launch PowerShell as an admin</span></span>

3. <span data-ttu-id="e2b47-139">SkypeOnline のコネクタをインポートして、Teams の管理者としてログインします。</span><span class="sxs-lookup"><span data-stu-id="e2b47-139">Import the SkypeOnline Connector and log in as a Teams admin.</span></span>

```PowerShell
  Import-Module SkypeOnlineConnector
  $sfbSession = New-CsOnlineSession
  Import-PSSession $sfbSession
```

4. <span data-ttu-id="e2b47-140">[Csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)を使用して、ストリームストレージから odsp に切り替える Teams 会議ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="e2b47-140">Use [set-csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) to set a Teams Meeting Policy to transition from the Stream storage to ODSP.</span></span>

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
```

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a><span data-ttu-id="e2b47-141">OneDrive for Business と SharePoint の使用を停止してストリームを継続する</span><span class="sxs-lookup"><span data-stu-id="e2b47-141">Opt out of OneDrive for Business and SharePoint to continue using Stream</span></span>

<span data-ttu-id="e2b47-142">ポリシーで **Stream**に設定されている場合でも、設定されていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e2b47-142">Even if a policy says it's set to **Stream**, it might not be set.</span></span> <span data-ttu-id="e2b47-143">通常、ポリシーが設定されていない場合、既定の設定は **Stream**です。</span><span class="sxs-lookup"><span data-stu-id="e2b47-143">Typically, if the policy isn't set, then the default setting is **Stream**.</span></span> <span data-ttu-id="e2b47-144">ただし、この新しい変更では、SharePoint または OneDrive を使用しないようにする場合は、ポリシーを [ **ストリーム** ] にリセットして既定の状態に戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2b47-144">However, with this new change, if you want to opt-out of using SharePoint or OneDrive, then you must reset the policy to **Stream** to ensure that it's the default.</span></span>

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="frequently-asked-questions"></a><span data-ttu-id="e2b47-145">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="e2b47-145">Frequently asked questions</span></span>

<span data-ttu-id="e2b47-146">**会議のレコーディングはどこに保存されますか?**</span><span class="sxs-lookup"><span data-stu-id="e2b47-146">**Where will the meeting recording be stored?**</span></span>

- <span data-ttu-id="e2b47-147">チャネル以外の会議の場合、レコーディングはという名前のフォルダーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="e2b47-147">For non-Channel meetings, the recording is stored in a folder named.</span></span> <span data-ttu-id="e2b47-148">レコーディング \* \* は、会議のレコーディングを開始したユーザーに属している OneDrive の最上位レベルにあります。</span><span class="sxs-lookup"><span data-stu-id="e2b47-148">Recordings\*\* that is at the top level of the OneDrive that belongs to the person who started the meeting recording.</span></span> <span data-ttu-id="e2b47-149">例:</span><span class="sxs-lookup"><span data-stu-id="e2b47-149">Example:</span></span>

  <span data-ttu-id="e2b47-150"><i>レコーダーの OneDrive For business</i> /**レコーディング**</span><span class="sxs-lookup"><span data-stu-id="e2b47-150"><i>recorder's OneDrive for Business</i>/**Recordings**</span></span>

- <span data-ttu-id="e2b47-151">チャネル会議の場合、レコーディングは [ **レコーディング**] という名前のフォルダーにある Teams サイトのドキュメントライブラリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="e2b47-151">For Channel meetings, the recording is stored in the Teams site documentation library in a folder named **Recordings**.</span></span> <span data-ttu-id="e2b47-152">例:</span><span class="sxs-lookup"><span data-stu-id="e2b47-152">Example:</span></span>

  <span data-ttu-id="e2b47-153"><i>Teams 名-チャネル名</i> /**ドキュメント** /**レコーディング**</span><span class="sxs-lookup"><span data-stu-id="e2b47-153"><i>Teams name - Channel name</i>/**Documents**/**Recordings**</span></span>

<span data-ttu-id="e2b47-154">**会議のレコーディングを表示する権限を持つユーザー**</span><span class="sxs-lookup"><span data-stu-id="e2b47-154">**Who has the permissions to view the meeting recording?**</span></span>

- <span data-ttu-id="e2b47-155">チャネル以外の会議の場合、外部ユーザーを除くすべての会議出席者は、自動的に個別の共有リンクを取得します。</span><span class="sxs-lookup"><span data-stu-id="e2b47-155">For non-Channel meetings, all meeting invitees, except for external users, will automatically get a personally shared link.</span></span> <span data-ttu-id="e2b47-156">外部ユーザーは、会議の開催者、または会議のレコーディングを開始したユーザーによって、共有リストに明示的に追加される必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2b47-156">External users will need to be explicitly added to the shared list by the meeting organizer or the person who started the meeting recording.</span></span>

- <span data-ttu-id="e2b47-157">チャネル会議の場合、アクセス許可はチャネルの所有者とメンバーの一覧から継承されます。</span><span class="sxs-lookup"><span data-stu-id="e2b47-157">For Channel meetings, permissions are inherited from the owners and members list in the channel.</span></span>

<span data-ttu-id="e2b47-158">**トランスクリプトを管理する方法を教えてください。**</span><span class="sxs-lookup"><span data-stu-id="e2b47-158">**How can I manage transcripts?**</span></span>

<span data-ttu-id="e2b47-159">このプレビューを有効にすると、OneDrive および SharePoint に移行されたチームの会議の記録にクローズドキャプションは表示されません。</span><span class="sxs-lookup"><span data-stu-id="e2b47-159">Customers opting in to this preview will not have closed captions available on their Teams Meeting Recordings that are migrated to OneDrive and SharePoint.</span></span><span data-ttu-id="e2b47-160">英語のキャプションから始まり、2020年10月の会議のレコーディングまで、キャプションを追加しています。</span><span class="sxs-lookup"><span data-stu-id="e2b47-160">  We're working to add captioning, beginning with closed captions in English, to meeting recordings in October 2020.</span></span>

<span data-ttu-id="e2b47-161">[Teams のクラウドレコーディング](cloud-recording.md)で説明されているように、トランスクリプトを許可することを選択しているお客様のために、クローズドキャプションが Teams の会議レコーディングで利用可能になる</span><span class="sxs-lookup"><span data-stu-id="e2b47-161">Closed captions will be available on Teams Meeting Recordings for customers who have opted in to allow transcripts as described in [Teams cloud recordings](cloud-recording.md)</span></span>

<span data-ttu-id="e2b47-162">キャプションを使用すると、すべてのアビリティーについて包括的なコンテンツを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="e2b47-162">Captions help create inclusive content for viewers of all abilities.</span></span> <span data-ttu-id="e2b47-163">所有者としては、キャプションを非表示にすることができます。ただし、Teams からキャプションを削除しない限り、そのトランスクリプトはまだ Teams で利用できます。</span><span class="sxs-lookup"><span data-stu-id="e2b47-163">As an owner, you can hide captions, although the transcript will still be available on Teams unless you delete the captions from Teams.</span></span> <span data-ttu-id="e2b47-164">[会議のレコーディングをオンまたはオフにする方法を確認する](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)</span><span class="sxs-lookup"><span data-stu-id="e2b47-164">See [how to turn on or off meeting recordings](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)</span></span>

<span data-ttu-id="e2b47-165">クローズドキャプションは、会議が記録された時点からの、60日間の Teams 会議レコーディングでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e2b47-165">Closed captions are supported for Teams meeting recordings for 60 days from when the meeting is recorded.</span></span>

<span data-ttu-id="e2b47-166">**記憶域のクォータにどのように影響が及ぶか**</span><span class="sxs-lookup"><span data-stu-id="e2b47-166">**How will my storage quota be impacted**</span></span>

<span data-ttu-id="e2b47-167">Teams 会議のレコーディングファイルは、OneDrive for Business と SharePoint に保存されており、これらのサービスのクォータに含まれています。</span><span class="sxs-lookup"><span data-stu-id="e2b47-167">Teams meeting recording files live in OneDrive for Business and SharePoint and are included in your quota for those services.</span></span> <span data-ttu-id="e2b47-168">[SharePoint のクォータ](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas)と [OneDrive for business のクォータ] () を参照してください https://docs.microsoft.com/onedrive/set-default-storage-space) 。</span><span class="sxs-lookup"><span data-stu-id="e2b47-168">See [SharePoint quota](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) and [OneDrive for Business quota] (https://docs.microsoft.com/onedrive/set-default-storage-space).</span></span>

<span data-ttu-id="e2b47-169">**Teams 会議のレコーディングを再生するにはどうすればよいですか?**</span><span class="sxs-lookup"><span data-stu-id="e2b47-169">**How can I play a Teams meeting recording?**</span></span>

<span data-ttu-id="e2b47-170">ビデオは、ファイルにアクセスした場所に応じて、OneDrive for Business または SharePoint のビデオプレーヤーで再生されます。</span><span class="sxs-lookup"><span data-stu-id="e2b47-170">Your video will play on the video player of OneDrive for Business or SharePoint depending on where you access the file.</span></span>

<span data-ttu-id="e2b47-171">**おけるをストリームに追加する予定の場合、既存のビデオはそのままで、どれだけの時間がかかりますか?**</span><span class="sxs-lookup"><span data-stu-id="e2b47-171">**If you plan on deprecating adding to Stream, will existing videos stay as is and for how long?**</span></span>

<span data-ttu-id="e2b47-172">近い将来、プラットフォームとしてのストリームは廃止されることはありません。</span><span class="sxs-lookup"><span data-stu-id="e2b47-172">Stream as a platform won't be deprecated in the near future.</span></span> <span data-ttu-id="e2b47-173">現在ストリーム内に存在するビデオは、移行を開始するまでそのまま残ります。</span><span class="sxs-lookup"><span data-stu-id="e2b47-173">The videos that currently live in Stream will stay there until we start migrating.</span></span> <span data-ttu-id="e2b47-174">これらのビデオは、移行時にも ODSP に移行されます。</span><span class="sxs-lookup"><span data-stu-id="e2b47-174">Upon migration, those videos will be migrated to ODSP as well.</span></span> <span data-ttu-id="e2b47-175">詳細について [は、ここ](https://docs.microsoft.com/stream/streamnew/classic-migration) を確認してください。</span><span class="sxs-lookup"><span data-stu-id="e2b47-175">Check [here](https://docs.microsoft.com/stream/streamnew/classic-migration) for more information.</span></span>
