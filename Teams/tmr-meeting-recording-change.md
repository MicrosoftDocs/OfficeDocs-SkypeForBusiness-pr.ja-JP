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
ms.openlocfilehash: 83a7a0628d76a96318081ec51a039d458ea1570f
ms.sourcegitcommit: c48a5aca37220ac6a797ac88b09cf80090b1b7df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "48444233"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a><span data-ttu-id="65c51-103">OneDrive for Business と、会議の記録に SharePoint または Stream を使用する</span><span class="sxs-lookup"><span data-stu-id="65c51-103">Use OneDrive for Business and SharePoint or Stream for meeting recordings</span></span>

> [!Note]
> <span data-ttu-id="65c51-104">会議の記録用に Microsoft Stream を使用して OneDrive for Business と Microsoft SharePoint を使用するように変更した場合は、段階的なアプローチとなります。</span><span class="sxs-lookup"><span data-stu-id="65c51-104">The change from using Microsoft Stream to OneDrive for Business and Microsoft SharePoint for meeting recordings will be a phased approach.</span></span>

|||
|---|-----------------|
|<span data-ttu-id="65c51-105">日付</span><span class="sxs-lookup"><span data-stu-id="65c51-105">Date</span></span>|<span data-ttu-id="65c51-106">イベント</span><span class="sxs-lookup"><span data-stu-id="65c51-106">Event</span></span>|
|<span data-ttu-id="65c51-107">初めての Q4 CY20</span><span class="sxs-lookup"><span data-stu-id="65c51-107">Early Q4 CY20</span></span>|<span data-ttu-id="65c51-108">**OneDrive for Business および SharePoint での Teams 会議の記録は、オプトインまたはオプトアウトで利用できます。**</span><span class="sxs-lookup"><span data-stu-id="65c51-108">**Teams meeting recording on OneDrive for Business and SharePoint available for opt in or opt out.**</span></span><br> <span data-ttu-id="65c51-109">テナント管理者は、OneDrive for Business と SharePoint のオプトインまたは脱退を行うことができます。 PowerShell で Teams ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="65c51-109">Tenant admins can opt in  or opt out of OneDrive for Business and SharePoint setting the Teams policy in PowerShell</span></span>|
|<span data-ttu-id="65c51-110">第 CY20 四半期中旬</span><span class="sxs-lookup"><span data-stu-id="65c51-110">Mid Q4 CY20</span></span>|<span data-ttu-id="65c51-111">**OneDrive for Business および SharePoint でのチーム会議の記録は、脱退しないテナントの既定として設定されます**</span><span class="sxs-lookup"><span data-stu-id="65c51-111">**Teams meeting recording on OneDrive for Business and SharePoint set as default for tenants who don't opt out**</span></span><br> <span data-ttu-id="65c51-112">これは、ほとんどのお客様に推奨されるパスです。</span><span class="sxs-lookup"><span data-stu-id="65c51-112">This is the  recommended path for most customers</span></span>|
<span data-ttu-id="65c51-113">Q1 CY21</span><span class="sxs-lookup"><span data-stu-id="65c51-113">Q1 CY21</span></span>|<span data-ttu-id="65c51-114">**Teams 会議の記録を従来のストリームに保存することはできなくなりました**</span><span class="sxs-lookup"><span data-stu-id="65c51-114">**Saving Teams meeting recording to Classic Stream no longer allowed**</span></span><br><span data-ttu-id="65c51-115">すべてのテナントが、Teams 会議の記録を OneDrive for Business と SharePoint に保存します</span><span class="sxs-lookup"><span data-stu-id="65c51-115">All tenants will save Teams meeting recording to OneDrive for Business and SharePoint</span></span>|
|||

<span data-ttu-id="65c51-116">Microsoft Teams には、会議の記録を保存するための新しい方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="65c51-116">Microsoft Teams has a new method for saving meeting recordings.</span></span> <span data-ttu-id="65c51-117">従来の Microsoft Stream から [新しいストリーム](https://docs.microsoft.com/stream/streamnew/new-stream)への移行の最初のフェーズとして、このメソッドは microsoft 365 の microsoft OneDrive と SharePoint 上にレコーディングを保存し、多くの利点を提供します。</span><span class="sxs-lookup"><span data-stu-id="65c51-117">As the first phase of a transition from classic Microsoft Stream to the [new Stream](https://docs.microsoft.com/stream/streamnew/new-stream), this method stores recordings on Microsoft OneDrive and SharePoint in Microsoft 365 and offers many benefits.</span></span>

<span data-ttu-id="65c51-118">OneDrive for Business と SharePoint を使ったレコーディングの保存には、次のような利点があります。</span><span class="sxs-lookup"><span data-stu-id="65c51-118">The benefits of using OneDrive for Business and SharePoint for storing recordings include:</span></span>

- <span data-ttu-id="65c51-119">Teams 会議レコーディングのアイテム保持ポリシー (TMR) (S + C E5 autoretention ラベル)</span><span class="sxs-lookup"><span data-stu-id="65c51-119">Retention policies for Teams meeting recording (TMR) (S+C E5 autoretention labels)</span></span>
- <span data-ttu-id="65c51-120">OneDrive for Business と SharePoint の情報ガバナンスの利点</span><span class="sxs-lookup"><span data-stu-id="65c51-120">Benefit from OneDrive for Business and SharePoint information governance</span></span>
- <span data-ttu-id="65c51-121">簡単にアクセス許可と共有を設定する</span><span class="sxs-lookup"><span data-stu-id="65c51-121">Easy to set permissions and sharing</span></span>
- <span data-ttu-id="65c51-122">明確な共有のみを使用して、ゲスト (外部ユーザー) とのレコーディングを共有する</span><span class="sxs-lookup"><span data-stu-id="65c51-122">Share recordings with guests (external users) with explicit share only</span></span>
- <span data-ttu-id="65c51-123">アクセスフローを要求する</span><span class="sxs-lookup"><span data-stu-id="65c51-123">Request access flow</span></span>
- <span data-ttu-id="65c51-124">OneDrive for Business と SharePoint の共有リンクを提供する</span><span class="sxs-lookup"><span data-stu-id="65c51-124">Provide OneDrive for Business and SharePoint shared links</span></span>
- <span data-ttu-id="65c51-125">クォータの増加</span><span class="sxs-lookup"><span data-stu-id="65c51-125">Increased quota</span></span>
- <span data-ttu-id="65c51-126">会議のレコーディングは、より高速に使用できます</span><span class="sxs-lookup"><span data-stu-id="65c51-126">Meeting  recordings are available faster</span></span>
- <span data-ttu-id="65c51-127">**ローカル** テナントのサポートに移動する</span><span class="sxs-lookup"><span data-stu-id="65c51-127">**Go local** tenant support</span></span>
- <span data-ttu-id="65c51-128">複数地域のサポート–レコーディングは、そのユーザーに固有の地域に保存されます。</span><span class="sxs-lookup"><span data-stu-id="65c51-128">Multi-geo support – recordings are stored in a region specific to that user</span></span>
- <span data-ttu-id="65c51-129">独自のキー (BYOK) のサポートを利用する</span><span class="sxs-lookup"><span data-stu-id="65c51-129">Bring your own key (BYOK) support</span></span>
- <span data-ttu-id="65c51-130">議事録の品質とスピーカーの属性を改善しました</span><span class="sxs-lookup"><span data-stu-id="65c51-130">Improved Transcript quality and speaker attribution</span></span>

<span data-ttu-id="65c51-131">次の点について考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65c51-131">There are some limitations to consider:</span></span>

- <span data-ttu-id="65c51-132">英語専用のクローズドキャプションとトランスクリプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="65c51-132">There will be English-only closed captions and transcripts.</span></span>
- <span data-ttu-id="65c51-133">トランスクリプトまたはコンテンツを検索することはできません。</span><span class="sxs-lookup"><span data-stu-id="65c51-133">You won't be able to search transcripts or their content.</span></span>
- <span data-ttu-id="65c51-134">トランスクリプトを編集することはできませんが、字幕のオン/オフを切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="65c51-134">You won’t be able to edit the transcripts, but you'll be able to toggle captions off/on.</span></span>
- <span data-ttu-id="65c51-135">レコーディングを共有している相手を管理することはできますが、共有アクセス権を持つユーザーがレコーディングをダウンロードするのをブロックすることはできません。</span><span class="sxs-lookup"><span data-stu-id="65c51-135">You can control with whom you share the recording, but you won't be able to block people with shared access from downloading the recording.</span></span>
- <span data-ttu-id="65c51-136">レコーディングの保存が完了したときにメールを受け取ることはありませんが、レコーディングが完了したら会議のチャットに表示されます。</span><span class="sxs-lookup"><span data-stu-id="65c51-136">You'll not get an email when the recording finishes saving, but the recording will appear in the meeting chat once it’s finished.</span></span> <span data-ttu-id="65c51-137">これは、以前のストリームで行ったよりもはるかに短時間で行われます</span><span class="sxs-lookup"><span data-stu-id="65c51-137">This will happen much quicker than it did in Stream previously</span></span>

<span data-ttu-id="65c51-138">詳細については、「会議の記録」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="65c51-138">Watch "Meeting Recording" for more information.</span></span>

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a><span data-ttu-id="65c51-139">OneDrive for Business と SharePoint の会議のレコーディングオプションを設定する</span><span class="sxs-lookup"><span data-stu-id="65c51-139">Set up the meeting recording option for OneDrive for Business and SharePoint</span></span>

1. <span data-ttu-id="65c51-140">Skype For Business Online PowerShell 管理コンソールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="65c51-140">Install the Skype For Business Online PowerShell admin console.</span></span>

    <span data-ttu-id="65c51-141">a.</span><span class="sxs-lookup"><span data-stu-id="65c51-141">a.</span></span> <span data-ttu-id="65c51-142">[Skype For Business Online PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="65c51-142">Download [Skype for Business Online PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide).</span></span>

    <span data-ttu-id="65c51-143">b.</span><span class="sxs-lookup"><span data-stu-id="65c51-143">b.</span></span> <span data-ttu-id="65c51-144">指示に従ってインストールします。</span><span class="sxs-lookup"><span data-stu-id="65c51-144">Follow the prompts to install it.</span></span>

    <span data-ttu-id="65c51-145">c.</span><span class="sxs-lookup"><span data-stu-id="65c51-145">c.</span></span> <span data-ttu-id="65c51-146">コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="65c51-146">Restart your machine.</span></span>

2. <span data-ttu-id="65c51-147">管理者として PowerShell を起動する</span><span class="sxs-lookup"><span data-stu-id="65c51-147">Launch PowerShell as an admin</span></span>

3. <span data-ttu-id="65c51-148">SkypeOnline のコネクタをインポートして、Teams の管理者としてログインします。</span><span class="sxs-lookup"><span data-stu-id="65c51-148">Import the SkypeOnline Connector and log in as a Teams admin.</span></span>

```PowerShell
  Import-Module SkypeOnlineConnector
  $sfbSession = New-CsOnlineSession
  Import-PSSession $sfbSession
```

4. <span data-ttu-id="65c51-149">[Csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)を使用して、ストリームストレージから odsp に切り替える Teams 会議ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="65c51-149">Use [set-csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) to set a Teams Meeting Policy to transition from the Stream storage to ODSP.</span></span>

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
```

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a><span data-ttu-id="65c51-150">OneDrive for Business と SharePoint の使用を停止してストリームを継続する</span><span class="sxs-lookup"><span data-stu-id="65c51-150">Opt out of OneDrive for Business and SharePoint to continue using Stream</span></span>

<span data-ttu-id="65c51-151">ポリシーで **Stream**に設定されている場合でも、設定されていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="65c51-151">Even if a policy says it's set to **Stream**, it might not be set.</span></span> <span data-ttu-id="65c51-152">通常、ポリシーが設定されていない場合、既定の設定は **Stream**です。</span><span class="sxs-lookup"><span data-stu-id="65c51-152">Typically, if the policy isn't set, then the default setting is **Stream**.</span></span> <span data-ttu-id="65c51-153">ただし、この新しい変更では、SharePoint または OneDrive を使用しないようにする場合は、ポリシーを [ **ストリーム** ] にリセットして既定の状態に戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="65c51-153">However, with this new change, if you want to opt-out of using SharePoint or OneDrive, then you must reset the policy to **Stream** to ensure that it's the default.</span></span>

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="frequently-asked-questions"></a><span data-ttu-id="65c51-154">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="65c51-154">Frequently asked questions</span></span>

<span data-ttu-id="65c51-155">**会議のレコーディングはどこに保存されますか?**</span><span class="sxs-lookup"><span data-stu-id="65c51-155">**Where will the meeting recording be stored?**</span></span>

- <span data-ttu-id="65c51-156">チャネル以外の会議の場合、レコーディングは、会議のレコーディングを開始したユーザーに属している OneDrive の最上位レベルの **レコーディング** という名前のフォルダーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="65c51-156">For non-Channel meetings, the recording is stored in a folder named **Recordings** that is at the top level of the OneDrive that belongs to the person who started the meeting recording.</span></span> <span data-ttu-id="65c51-157">例:</span><span class="sxs-lookup"><span data-stu-id="65c51-157">Example:</span></span>

  <span data-ttu-id="65c51-158"><i>レコーダーの OneDrive For business</i> /**レコーディング**</span><span class="sxs-lookup"><span data-stu-id="65c51-158"><i>recorder's OneDrive for Business</i>/**Recordings**</span></span>

- <span data-ttu-id="65c51-159">チャネル会議の場合、レコーディングは [ **レコーディング**] という名前のフォルダーにある Teams サイトのドキュメントライブラリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="65c51-159">For Channel meetings, the recording is stored in the Teams site documentation library in a folder named **Recordings**.</span></span> <span data-ttu-id="65c51-160">例:</span><span class="sxs-lookup"><span data-stu-id="65c51-160">Example:</span></span>

  <span data-ttu-id="65c51-161"><i>Teams 名-チャネル名</i> /**ドキュメント** /**レコーディング**</span><span class="sxs-lookup"><span data-stu-id="65c51-161"><i>Teams name - Channel name</i>/**Documents**/**Recordings**</span></span>

<span data-ttu-id="65c51-162">**元従業員のレコーディングを処理する方法を教えてください。**</span><span class="sxs-lookup"><span data-stu-id="65c51-162">**How do I handle recordings from former employees?**</span></span>

<span data-ttu-id="65c51-163">ビデオは、OneDrive や SharePoint の他のファイルと同様に、従業員が退職した後の所有と保持は、通常の [onedrive と sharepoint のプロセス]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process)に従います。</span><span class="sxs-lookup"><span data-stu-id="65c51-163">Since videos are just like any other file in OneDrive and SharePoint, handling ownership and retention after an employee leaves will follow the normal [OneDrive and SharePoint process]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process).</span></span>

<span data-ttu-id="65c51-164">**会議のレコーディングを表示する権限を持つユーザー**</span><span class="sxs-lookup"><span data-stu-id="65c51-164">**Who has the permissions to view the meeting recording?**</span></span>

- <span data-ttu-id="65c51-165">チャネル以外の会議の場合、外部ユーザーを除くすべての会議出席者は、自動的に個別の共有リンクを取得します。</span><span class="sxs-lookup"><span data-stu-id="65c51-165">For non-Channel meetings, all meeting invitees, except for external users, will automatically get a personally shared link.</span></span> <span data-ttu-id="65c51-166">外部ユーザーは、会議の開催者、または会議のレコーディングを開始したユーザーによって、共有リストに明示的に追加される必要があります。</span><span class="sxs-lookup"><span data-stu-id="65c51-166">External users will need to be explicitly added to the shared list by the meeting organizer or the person who started the meeting recording.</span></span>

- <span data-ttu-id="65c51-167">チャネル会議の場合、アクセス許可はチャネルの所有者とメンバーの一覧から継承されます。</span><span class="sxs-lookup"><span data-stu-id="65c51-167">For Channel meetings, permissions are inherited from the owners and members list in the channel.</span></span>

<span data-ttu-id="65c51-168">**トランスクリプトを管理する方法を教えてください。**</span><span class="sxs-lookup"><span data-stu-id="65c51-168">**How can I manage transcripts?**</span></span>

<span data-ttu-id="65c51-169">このプレビューを有効にすると、OneDrive および SharePoint に移行されたチームの会議の記録にクローズドキャプションは表示されません。</span><span class="sxs-lookup"><span data-stu-id="65c51-169">Customers opting in to this preview will not have closed captions available on their Teams Meeting Recordings that are migrated to OneDrive and SharePoint.</span></span><span data-ttu-id="65c51-170">英語のキャプションから始まり、2020年10月の会議のレコーディングまで、キャプションを追加しています。</span><span class="sxs-lookup"><span data-stu-id="65c51-170">  We're working to add captioning, beginning with closed captions in English, to meeting recordings in October 2020.</span></span>

<span data-ttu-id="65c51-171">[Teams のクラウドレコーディング](cloud-recording.md)で説明されているように、トランスクリプトを許可することを選択しているお客様のために、クローズドキャプションが Teams の会議レコーディングで利用可能になる</span><span class="sxs-lookup"><span data-stu-id="65c51-171">Closed captions will be available on Teams Meeting Recordings for customers who have opted in to allow transcripts as described in [Teams cloud recordings](cloud-recording.md)</span></span>

<span data-ttu-id="65c51-172">キャプションを使用すると、すべてのアビリティーについて包括的なコンテンツを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="65c51-172">Captions help create inclusive content for viewers of all abilities.</span></span> <span data-ttu-id="65c51-173">所有者としては、キャプションを非表示にすることができます。ただし、Teams からキャプションを削除しない限り、そのトランスクリプトはまだ Teams で利用できます。</span><span class="sxs-lookup"><span data-stu-id="65c51-173">As an owner, you can hide captions, although the transcript will still be available on Teams unless you delete the captions from Teams.</span></span> <span data-ttu-id="65c51-174">[会議のレコーディングをオンまたはオフにする方法を確認する](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)</span><span class="sxs-lookup"><span data-stu-id="65c51-174">See [how to turn on or off meeting recordings](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)</span></span>

<span data-ttu-id="65c51-175">クローズドキャプションは、会議が記録された時点からの、60日間の Teams 会議レコーディングでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="65c51-175">Closed captions are supported for Teams meeting recordings for 60 days from when the meeting is recorded.</span></span>

<span data-ttu-id="65c51-176">**記憶域のクォータにどのように影響が及ぶか**</span><span class="sxs-lookup"><span data-stu-id="65c51-176">**How will my storage quota be impacted**</span></span>

<span data-ttu-id="65c51-177">Teams 会議のレコーディングファイルは、OneDrive for Business と SharePoint に保存されており、これらのサービスのクォータに含まれています。</span><span class="sxs-lookup"><span data-stu-id="65c51-177">Teams meeting recording files live in OneDrive for Business and SharePoint and are included in your quota for those services.</span></span> <span data-ttu-id="65c51-178">[SharePoint のクォータ](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas)と [OneDrive for business のクォータ] () を参照してください https://docs.microsoft.com/onedrive/set-default-storage-space) 。</span><span class="sxs-lookup"><span data-stu-id="65c51-178">See [SharePoint quota](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) and [OneDrive for Business quota] (https://docs.microsoft.com/onedrive/set-default-storage-space).</span></span>

<span data-ttu-id="65c51-179">**Teams 会議のレコーディングを再生するにはどうすればよいですか?**</span><span class="sxs-lookup"><span data-stu-id="65c51-179">**How can I play a Teams meeting recording?**</span></span>

<span data-ttu-id="65c51-180">ビデオは、ファイルにアクセスした場所に応じて、OneDrive for Business または SharePoint のビデオプレーヤーで再生されます。</span><span class="sxs-lookup"><span data-stu-id="65c51-180">Your video will play on the video player of OneDrive for Business or SharePoint depending on where you access the file.</span></span>

<span data-ttu-id="65c51-181">**おけるをストリームに追加する予定の場合、既存のビデオはそのままで、どれだけの時間がかかりますか?**</span><span class="sxs-lookup"><span data-stu-id="65c51-181">**If you plan on deprecating adding to Stream, will existing videos stay as is and for how long?**</span></span>

<span data-ttu-id="65c51-182">近い将来、プラットフォームとしてのストリームは廃止されることはありません。</span><span class="sxs-lookup"><span data-stu-id="65c51-182">Stream as a platform won't be deprecated in the near future.</span></span> <span data-ttu-id="65c51-183">現在ストリーム内に存在するビデオは、移行を開始するまでそのまま残ります。</span><span class="sxs-lookup"><span data-stu-id="65c51-183">The videos that currently live in Stream will stay there until we start migrating.</span></span> <span data-ttu-id="65c51-184">これらのビデオは、移行時にも ODSP に移行されます。</span><span class="sxs-lookup"><span data-stu-id="65c51-184">Upon migration, those videos will be migrated to ODSP as well.</span></span> <span data-ttu-id="65c51-185">詳細について [は、ここ](https://docs.microsoft.com/stream/streamnew/classic-migration) を確認してください。</span><span class="sxs-lookup"><span data-stu-id="65c51-185">Check [here](https://docs.microsoft.com/stream/streamnew/classic-migration) for more information.</span></span>
