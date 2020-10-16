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
ms.openlocfilehash: 624dcb4f99bc8ae2b83a1b8f62917ac0a5701888
ms.sourcegitcommit: 8a345ca9a8ddc6a84f9e270ab55f1b28f6ba49c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48486772"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a><span data-ttu-id="6e07f-103">OneDrive for Business と、会議の記録に SharePoint または Stream を使用する</span><span class="sxs-lookup"><span data-stu-id="6e07f-103">Use OneDrive for Business and SharePoint or Stream for meeting recordings</span></span>

> [!Note]
> <span data-ttu-id="6e07f-104">会議の記録用に Microsoft Stream を使用して OneDrive for Business と Microsoft SharePoint を使用するように変更した場合は、段階的なアプローチとなります。</span><span class="sxs-lookup"><span data-stu-id="6e07f-104">The change from using Microsoft Stream to OneDrive for Business and Microsoft SharePoint for meeting recordings will be a phased approach.</span></span>


|<span data-ttu-id="6e07f-105">日付</span><span class="sxs-lookup"><span data-stu-id="6e07f-105">Date</span></span>|<span data-ttu-id="6e07f-106">イベント</span><span class="sxs-lookup"><span data-stu-id="6e07f-106">Event</span></span>|
|---|-----------------|
|<span data-ttu-id="6e07f-107">初めての Q4 CY20</span><span class="sxs-lookup"><span data-stu-id="6e07f-107">Early Q4 CY20</span></span>|<span data-ttu-id="6e07f-108">**OneDrive for Business および SharePoint での Teams 会議の記録は、オプトインまたはオプトアウトで利用できます。**</span><span class="sxs-lookup"><span data-stu-id="6e07f-108">**Teams meeting recording on OneDrive for Business and SharePoint available for opt in or opt out.**</span></span><br> <span data-ttu-id="6e07f-109">テナント管理者は、OneDrive for Business と SharePoint のオプトインまたは脱退を行うことができます。 PowerShell で Teams ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="6e07f-109">Tenant admins can opt in  or opt out of OneDrive for Business and SharePoint setting the Teams policy in PowerShell</span></span>|
|<span data-ttu-id="6e07f-110">第 CY20 四半期中旬</span><span class="sxs-lookup"><span data-stu-id="6e07f-110">Mid Q4 CY20</span></span>|<span data-ttu-id="6e07f-111">**OneDrive for Business および SharePoint でのチーム会議の記録は、脱退しないテナントの既定として設定されます**</span><span class="sxs-lookup"><span data-stu-id="6e07f-111">**Teams meeting recording on OneDrive for Business and SharePoint set as default for tenants who don't opt out**</span></span><br> <span data-ttu-id="6e07f-112">これは、ほとんどのお客様に推奨されるパスです。</span><span class="sxs-lookup"><span data-stu-id="6e07f-112">This is the  recommended path for most customers</span></span>|
|<span data-ttu-id="6e07f-113">Q1 CY21</span><span class="sxs-lookup"><span data-stu-id="6e07f-113">Q1 CY21</span></span>|<span data-ttu-id="6e07f-114">**Teams 会議の記録を従来のストリームに保存することはできなくなりました**</span><span class="sxs-lookup"><span data-stu-id="6e07f-114">**Saving Teams meeting recording to Classic Stream no longer allowed**</span></span><br><span data-ttu-id="6e07f-115">すべてのテナントが、Teams 会議の記録を OneDrive for Business と SharePoint に保存します</span><span class="sxs-lookup"><span data-stu-id="6e07f-115">All tenants will save Teams meeting recording to OneDrive for Business and SharePoint</span></span>|


<span data-ttu-id="6e07f-116">Microsoft Teams には、会議の記録を保存するための新しい方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="6e07f-116">Microsoft Teams has a new method for saving meeting recordings.</span></span> <span data-ttu-id="6e07f-117">従来の Microsoft Stream から [新しいストリーム](https://docs.microsoft.com/stream/streamnew/new-stream)への移行の最初のフェーズとして、このメソッドは microsoft 365 の microsoft OneDrive と SharePoint 上にレコーディングを保存し、多くの利点を提供します。</span><span class="sxs-lookup"><span data-stu-id="6e07f-117">As the first phase of a transition from classic Microsoft Stream to the [new Stream](https://docs.microsoft.com/stream/streamnew/new-stream), this method stores recordings on Microsoft OneDrive and SharePoint in Microsoft 365 and offers many benefits.</span></span>

<span data-ttu-id="6e07f-118">OneDrive for Business と SharePoint を使ったレコーディングの保存には、次のような利点があります。</span><span class="sxs-lookup"><span data-stu-id="6e07f-118">The benefits of using OneDrive for Business and SharePoint for storing recordings include:</span></span>

- <span data-ttu-id="6e07f-119">Teams 会議レコーディングのアイテム保持ポリシー (TMR) (S + C E5 autoretention ラベル)</span><span class="sxs-lookup"><span data-stu-id="6e07f-119">Retention policies for Teams meeting recording (TMR) (S+C E5 autoretention labels)</span></span>
- <span data-ttu-id="6e07f-120">OneDrive for Business と SharePoint の情報ガバナンスの利点</span><span class="sxs-lookup"><span data-stu-id="6e07f-120">Benefit from OneDrive for Business and SharePoint information governance</span></span>
- <span data-ttu-id="6e07f-121">簡単にアクセス許可と共有を設定する</span><span class="sxs-lookup"><span data-stu-id="6e07f-121">Easy to set permissions and sharing</span></span>
- <span data-ttu-id="6e07f-122">明確な共有のみを使用して、ゲスト (外部ユーザー) とのレコーディングを共有する</span><span class="sxs-lookup"><span data-stu-id="6e07f-122">Share recordings with guests (external users) with explicit share only</span></span>
- <span data-ttu-id="6e07f-123">アクセスフローを要求する</span><span class="sxs-lookup"><span data-stu-id="6e07f-123">Request access flow</span></span>
- <span data-ttu-id="6e07f-124">OneDrive for Business と SharePoint の共有リンクを提供する</span><span class="sxs-lookup"><span data-stu-id="6e07f-124">Provide OneDrive for Business and SharePoint shared links</span></span>
- <span data-ttu-id="6e07f-125">クォータの増加</span><span class="sxs-lookup"><span data-stu-id="6e07f-125">Increased quota</span></span>
- <span data-ttu-id="6e07f-126">会議のレコーディングは、より高速に使用できます</span><span class="sxs-lookup"><span data-stu-id="6e07f-126">Meeting  recordings are available faster</span></span>
- <span data-ttu-id="6e07f-127">**ローカル** テナントのサポートに移動する</span><span class="sxs-lookup"><span data-stu-id="6e07f-127">**Go local** tenant support</span></span>
- <span data-ttu-id="6e07f-128">複数地域のサポート–レコーディングは、そのユーザーに固有の地域に保存されます。</span><span class="sxs-lookup"><span data-stu-id="6e07f-128">Multi-geo support – recordings are stored in a region specific to that user</span></span>
- <span data-ttu-id="6e07f-129">独自のキー (BYOK) のサポートを利用する</span><span class="sxs-lookup"><span data-stu-id="6e07f-129">Bring your own key (BYOK) support</span></span>
- <span data-ttu-id="6e07f-130">議事録の品質とスピーカーの属性を改善しました</span><span class="sxs-lookup"><span data-stu-id="6e07f-130">Improved Transcript quality and speaker attribution</span></span>

<span data-ttu-id="6e07f-131">次の点について考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e07f-131">There are some limitations to consider:</span></span>

- <span data-ttu-id="6e07f-132">英語専用のクローズドキャプションとトランスクリプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6e07f-132">There will be English-only closed captions and transcripts.</span></span>
- <span data-ttu-id="6e07f-133">トランスクリプトまたはコンテンツを検索することはできません。</span><span class="sxs-lookup"><span data-stu-id="6e07f-133">You won't be able to search transcripts or their content.</span></span>
- <span data-ttu-id="6e07f-134">トランスクリプトを編集することはできませんが、字幕のオン/オフを切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="6e07f-134">You won’t be able to edit the transcripts, but you'll be able to toggle captions off/on.</span></span>
- <span data-ttu-id="6e07f-135">レコーディングを共有している相手を管理することはできますが、共有アクセス権を持つユーザーがレコーディングをダウンロードするのをブロックすることはできません。</span><span class="sxs-lookup"><span data-stu-id="6e07f-135">You can control with whom you share the recording, but you won't be able to block people with shared access from downloading the recording.</span></span>
- <span data-ttu-id="6e07f-136">レコーディングの保存が完了したときにメールを受け取ることはありませんが、レコーディングが完了したら会議のチャットに表示されます。</span><span class="sxs-lookup"><span data-stu-id="6e07f-136">You'll not get an email when the recording finishes saving, but the recording will appear in the meeting chat once it’s finished.</span></span> <span data-ttu-id="6e07f-137">これは、以前のストリームで行ったよりもはるかに短時間で行われます</span><span class="sxs-lookup"><span data-stu-id="6e07f-137">This will happen much quicker than it did in Stream previously</span></span>

<span data-ttu-id="6e07f-138">詳細については、「会議の記録」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6e07f-138">Watch "Meeting Recording" for more information.</span></span>

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a><span data-ttu-id="6e07f-139">OneDrive for Business と SharePoint の会議のレコーディングオプションを設定する</span><span class="sxs-lookup"><span data-stu-id="6e07f-139">Set up the meeting recording option for OneDrive for Business and SharePoint</span></span>

1. <span data-ttu-id="6e07f-140">Skype For Business Online PowerShell 管理コンソールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="6e07f-140">Install the Skype For Business Online PowerShell admin console.</span></span>

    <span data-ttu-id="6e07f-141">a.</span><span class="sxs-lookup"><span data-stu-id="6e07f-141">a.</span></span> <span data-ttu-id="6e07f-142">[Skype For Business Online PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="6e07f-142">Download [Skype for Business Online PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide).</span></span>

    <span data-ttu-id="6e07f-143">b.</span><span class="sxs-lookup"><span data-stu-id="6e07f-143">b.</span></span> <span data-ttu-id="6e07f-144">指示に従ってインストールします。</span><span class="sxs-lookup"><span data-stu-id="6e07f-144">Follow the prompts to install it.</span></span>

    <span data-ttu-id="6e07f-145">c.</span><span class="sxs-lookup"><span data-stu-id="6e07f-145">c.</span></span> <span data-ttu-id="6e07f-146">コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="6e07f-146">Restart your machine.</span></span>

2. <span data-ttu-id="6e07f-147">管理者として PowerShell を起動する</span><span class="sxs-lookup"><span data-stu-id="6e07f-147">Launch PowerShell as an admin</span></span>

3. <span data-ttu-id="6e07f-148">SkypeOnline のコネクタをインポートして、Teams の管理者としてログインします。</span><span class="sxs-lookup"><span data-stu-id="6e07f-148">Import the SkypeOnline Connector and log in as a Teams admin.</span></span>

```PowerShell
  Import-Module SkypeOnlineConnector
  $sfbSession = New-CsOnlineSession
  Import-PSSession $sfbSession
```

4. <span data-ttu-id="6e07f-149">[Csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)を使用して、ストリームストレージから odsp に切り替える Teams 会議ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="6e07f-149">Use [set-csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) to set a Teams Meeting Policy to transition from the Stream storage to ODSP.</span></span>

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
```

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a><span data-ttu-id="6e07f-150">OneDrive for Business と SharePoint の使用を停止してストリームを継続する</span><span class="sxs-lookup"><span data-stu-id="6e07f-150">Opt out of OneDrive for Business and SharePoint to continue using Stream</span></span>

<span data-ttu-id="6e07f-151">ポリシーで **Stream**に設定されている場合でも、設定されていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6e07f-151">Even if a policy says it's set to **Stream**, it might not be set.</span></span> <span data-ttu-id="6e07f-152">通常、ポリシーが設定されていない場合、既定の設定は **Stream**です。</span><span class="sxs-lookup"><span data-stu-id="6e07f-152">Typically, if the policy isn't set, then the default setting is **Stream**.</span></span> <span data-ttu-id="6e07f-153">ただし、この新しい変更では、SharePoint または OneDrive を使用しないようにする場合は、ポリシーを [ **ストリーム** ] にリセットして既定の状態に戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e07f-153">However, with this new change, if you want to opt-out of using SharePoint or OneDrive, then you must reset the policy to **Stream** to ensure that it's the default.</span></span>

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="permissions-or-role-based-access"></a><span data-ttu-id="6e07f-154">権限またはロールベースのアクセス</span><span class="sxs-lookup"><span data-stu-id="6e07f-154">Permissions or role-based access</span></span>


|<span data-ttu-id="6e07f-155">会議の種類</span><span class="sxs-lookup"><span data-stu-id="6e07f-155">Meeting type</span></span>                               | <span data-ttu-id="6e07f-156">レコードをクリックしたユーザー</span><span class="sxs-lookup"><span data-stu-id="6e07f-156">Who clicked on Record?</span></span>| <span data-ttu-id="6e07f-157">記録はどこにありますか?</span><span class="sxs-lookup"><span data-stu-id="6e07f-157">Where does the recording land?</span></span>                               |<span data-ttu-id="6e07f-158">アクセス権を持つユーザー</span><span class="sxs-lookup"><span data-stu-id="6e07f-158">Who has access?</span></span> <span data-ttu-id="6e07f-159">R/W、R、または共有</span><span class="sxs-lookup"><span data-stu-id="6e07f-159">R/W, R or sharing</span></span>                                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|<span data-ttu-id="6e07f-160">社内関係者との1:1 通話</span><span class="sxs-lookup"><span data-stu-id="6e07f-160">1:1 call with internal parties</span></span>             |<span data-ttu-id="6e07f-161">[発信者]</span><span class="sxs-lookup"><span data-stu-id="6e07f-161">Caller</span></span>                 |<span data-ttu-id="6e07f-162">発信者の OneDrive for business アカウント</span><span class="sxs-lookup"><span data-stu-id="6e07f-162">Caller’s OneDrive for Business account</span></span>                        |<span data-ttu-id="6e07f-163">-発信者は所有者であり、完全な権利の呼び出し先 (同じテナント内の場合) に読み取り専用のアクセス許可があります (異なるテナントの場合)、共有アクセスは許可されません。</span><span class="sxs-lookup"><span data-stu-id="6e07f-163">- Caller is owner, has full rights  - Callee (if in the same tenant) has read only access, no sharing access -  Callee (if in different tenant) has no access.</span></span> <span data-ttu-id="6e07f-164">呼び出し元は呼び出し元に共有する必要があります</span><span class="sxs-lookup"><span data-stu-id="6e07f-164">Caller must share it to the Callee</span></span>|
|<span data-ttu-id="6e07f-165">社内関係者との1:1 通話</span><span class="sxs-lookup"><span data-stu-id="6e07f-165">1:1 call with internal parties</span></span>             |<span data-ttu-id="6e07f-166">[呼び出し先]</span><span class="sxs-lookup"><span data-stu-id="6e07f-166">Callee</span></span>                 |<span data-ttu-id="6e07f-167">呼び出し先の OneDrive for business アカウント</span><span class="sxs-lookup"><span data-stu-id="6e07f-167">Callee’s OneDrive for Business account</span></span>                        |<span data-ttu-id="6e07f-168">-呼び出し元は所有者であり、完全な権限が与えられています (同じテナント内で読み取り専用アクセス権を持っている場合は、共有アクセス権がありません)。</span><span class="sxs-lookup"><span data-stu-id="6e07f-168">- Callee is owner, has full rights - Caller (if in the same tenant has read only access, no sharing access - Caller (if in different tenant) has no access.</span></span> <span data-ttu-id="6e07f-169">呼び出し先は呼び出し先に共有する必要があります</span><span class="sxs-lookup"><span data-stu-id="6e07f-169">Callee must share it to the Callee</span></span>|
|<span data-ttu-id="6e07f-170">外部通話での1:1 通話</span><span class="sxs-lookup"><span data-stu-id="6e07f-170">1:1 call with an external call</span></span>             |<span data-ttu-id="6e07f-171">[発信者]</span><span class="sxs-lookup"><span data-stu-id="6e07f-171">Caller</span></span>                 |<span data-ttu-id="6e07f-172">発信者の OneDrive for business アカウント</span><span class="sxs-lookup"><span data-stu-id="6e07f-172">Caller’s OneDrive for Business account</span></span>                        |<span data-ttu-id="6e07f-173">-発信者は所有者であり、完全な権限が与えられています。</span><span class="sxs-lookup"><span data-stu-id="6e07f-173">- Caller is owner, has full rights - Callee has no access.</span></span> <span data-ttu-id="6e07f-174">呼び出し元は呼び出し元に共有する必要があります</span><span class="sxs-lookup"><span data-stu-id="6e07f-174">Caller must share it to the Callee</span></span>|
|<span data-ttu-id="6e07f-175">外部通話での1:1 通話</span><span class="sxs-lookup"><span data-stu-id="6e07f-175">1:1 call with an external call</span></span>             |<span data-ttu-id="6e07f-176">[呼び出し先]</span><span class="sxs-lookup"><span data-stu-id="6e07f-176">Callee</span></span>                 |<span data-ttu-id="6e07f-177">発信者の OneDrive for business アカウント</span><span class="sxs-lookup"><span data-stu-id="6e07f-177">Caller’s OneDrive for Business account</span></span>                        |<span data-ttu-id="6e07f-178">-呼び出し元は所有者であり、完全な権限を持ちます。</span><span class="sxs-lookup"><span data-stu-id="6e07f-178">- Callee is owner, has full rights - Caller has no access.</span></span> <span data-ttu-id="6e07f-179">呼び出し元は呼び出し元に共有する必要があります</span><span class="sxs-lookup"><span data-stu-id="6e07f-179">Callee must share it to the Caller</span></span>|
|<span data-ttu-id="6e07f-180">グループ通話</span><span class="sxs-lookup"><span data-stu-id="6e07f-180">Group call</span></span>                                 |<span data-ttu-id="6e07f-181">通話の任意のメンバー</span><span class="sxs-lookup"><span data-stu-id="6e07f-181">Any member of the call</span></span> |<span data-ttu-id="6e07f-182">レコードの OneDrive for Business アカウントをクリックしたメンバー</span><span class="sxs-lookup"><span data-stu-id="6e07f-182">Member who clicked on Record’s OneDrive for Business account</span></span>  |<span data-ttu-id="6e07f-183">-レコードをクリックしたメンバーには完全な権限があります。また、同じテナントの他のメンバーには読み取り権限があります。他のメンバーには権限がありません。</span><span class="sxs-lookup"><span data-stu-id="6e07f-183">- Member who clicked on Record has full rights - Other members from the same tenant have Read rights - Other members for different have no rights to it.</span></span>|
|<span data-ttu-id="6e07f-184">アドホック/スケジュールされた会議</span><span class="sxs-lookup"><span data-stu-id="6e07f-184">Adhoc/Scheduled meeting</span></span>                    |<span data-ttu-id="6e07f-185">[開催者]</span><span class="sxs-lookup"><span data-stu-id="6e07f-185">Organizer</span></span>              |<span data-ttu-id="6e07f-186">開催者の OneDrive for business アカウント</span><span class="sxs-lookup"><span data-stu-id="6e07f-186">Organizer’s OneDrive for Business account</span></span>                     |<span data-ttu-id="6e07f-187">-開催者はレコーディングへのフル権限を持っています。他の参加者全員が読み取りアクセス権を持っています。</span><span class="sxs-lookup"><span data-stu-id="6e07f-187">- Organizer has full rights to the recording - All other members of the meeting have read access</span></span>|
|<span data-ttu-id="6e07f-188">アドホック/スケジュールされた会議</span><span class="sxs-lookup"><span data-stu-id="6e07f-188">Adhoc/Scheduled meeting</span></span>                    |<span data-ttu-id="6e07f-189">その他の会議メンバー</span><span class="sxs-lookup"><span data-stu-id="6e07f-189">Other meeting member</span></span>   |<span data-ttu-id="6e07f-190">レコードをクリックしたメンバー</span><span class="sxs-lookup"><span data-stu-id="6e07f-190">Member who clicked on Record</span></span>                                  |<span data-ttu-id="6e07f-191">-レコードをクリックしたメンバーは、レコーディングの編集権限を持ち、共有することができます。他のメンバー全員が読み取りアクセス権を持っています</span><span class="sxs-lookup"><span data-stu-id="6e07f-191">- Member who clicked on Record has full rights to the recording - Organizer has edit rights and can share - All other members have read access</span></span>|
|<span data-ttu-id="6e07f-192">外部ユーザーとのアドホック/スケジュールされた会議</span><span class="sxs-lookup"><span data-stu-id="6e07f-192">Adhoc/Scheduled meeting with external users</span></span>|<span data-ttu-id="6e07f-193">[開催者]</span><span class="sxs-lookup"><span data-stu-id="6e07f-193">Organizer</span></span>              |<span data-ttu-id="6e07f-194">開催者の OneDrive for business アカウント</span><span class="sxs-lookup"><span data-stu-id="6e07f-194">Organizer’s OneDrive for Business account</span></span>                     |<span data-ttu-id="6e07f-195">-開催者は読み取りアクセス権を持っているので、その他のすべてのメンバーがレコーディングに対する完全な権限を持っています。その他のすべての外部メンバーは、アクセス権を持っておらず、開催者が共有する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e07f-195">- Organizer has full rights to the recording - All other members of the meeting from the same tenant as the organizer have read access - All other external members have no access and the Organizer must share it to them</span></span>|
|<span data-ttu-id="6e07f-196">外部ユーザーとのアドホック/スケジュールされた会議</span><span class="sxs-lookup"><span data-stu-id="6e07f-196">Adhoc/Scheduled meeting with external users</span></span>|<span data-ttu-id="6e07f-197">その他の会議メンバー</span><span class="sxs-lookup"><span data-stu-id="6e07f-197">Other meeting member</span></span>   |<span data-ttu-id="6e07f-198">レコードをクリックしたメンバー</span><span class="sxs-lookup"><span data-stu-id="6e07f-198">Member who clicked on Record</span></span>                                  |<span data-ttu-id="6e07f-199">-レコードをクリックしたメンバーには、レコーディングの権限があります。また、編集者は読み取りアクセス権を持っているため、他のすべての外部メンバーにはアクセス権がなく、その他のすべてのメンバーは共有できます。</span><span class="sxs-lookup"><span data-stu-id="6e07f-199">- Member who clicked on Record has full rights to the recording - Organizer has edit rights and can share - All other members of the meeting from the same tenant as the organizer have read access - All other external members have no access and the Organizer must share it to them</span></span>|
|<span data-ttu-id="6e07f-200">チャネル会議</span><span class="sxs-lookup"><span data-stu-id="6e07f-200">Channel meeting</span></span>                            |<span data-ttu-id="6e07f-201">チャネルメンバー</span><span class="sxs-lookup"><span data-stu-id="6e07f-201">Channel Member</span></span>         |<span data-ttu-id="6e07f-202">そのチャネル用の Teams の SharePoint の場所</span><span class="sxs-lookup"><span data-stu-id="6e07f-202">Teams' SharePoint location for that channel</span></span>                   |<span data-ttu-id="6e07f-203">-レコードをクリックしたメンバーには、レコーディングの編集権限があります。他のメンバーのアクセス許可は、チャネルの SharePoint アクセス許可に基づいています。</span><span class="sxs-lookup"><span data-stu-id="6e07f-203">- Member who clicked on Record has edit rights to the recording  - Every other member’s permissions are based off of the Channel SharePoint permissions</span></span>|


## <a name="frequently-asked-questions"></a><span data-ttu-id="6e07f-204">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="6e07f-204">Frequently asked questions</span></span>

<span data-ttu-id="6e07f-205">**会議のレコーディングはどこに保存されますか?**</span><span class="sxs-lookup"><span data-stu-id="6e07f-205">**Where will the meeting recording be stored?**</span></span>

- <span data-ttu-id="6e07f-206">チャネル以外の会議の場合、レコーディングは、会議のレコーディングを開始したユーザーに属している OneDrive の最上位レベルの **レコーディング** という名前のフォルダーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="6e07f-206">For non-Channel meetings, the recording is stored in a folder named **Recordings** that is at the top level of the OneDrive that belongs to the person who started the meeting recording.</span></span> <span data-ttu-id="6e07f-207">例:</span><span class="sxs-lookup"><span data-stu-id="6e07f-207">Example:</span></span>

  <span data-ttu-id="6e07f-208"><i>レコーダーの OneDrive For business</i> /**レコーディング**</span><span class="sxs-lookup"><span data-stu-id="6e07f-208"><i>recorder's OneDrive for Business</i>/**Recordings**</span></span>

- <span data-ttu-id="6e07f-209">チャネル会議の場合、レコーディングは [ **レコーディング**] という名前のフォルダーにある Teams サイトのドキュメントライブラリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="6e07f-209">For Channel meetings, the recording is stored in the Teams site documentation library in a folder named **Recordings**.</span></span> <span data-ttu-id="6e07f-210">例:</span><span class="sxs-lookup"><span data-stu-id="6e07f-210">Example:</span></span>

  <span data-ttu-id="6e07f-211"><i>Teams 名-チャネル名</i> /**ドキュメント** /**レコーディング**</span><span class="sxs-lookup"><span data-stu-id="6e07f-211"><i>Teams name - Channel name</i>/**Documents**/**Recordings**</span></span>

<span data-ttu-id="6e07f-212">**元従業員のレコーディングを処理する方法を教えてください。**</span><span class="sxs-lookup"><span data-stu-id="6e07f-212">**How do I handle recordings from former employees?**</span></span>

<span data-ttu-id="6e07f-213">ビデオは、OneDrive や SharePoint の他のファイルと同様に、従業員が退職した後の所有と保持は、通常の [onedrive と sharepoint のプロセス]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process)に従います。</span><span class="sxs-lookup"><span data-stu-id="6e07f-213">Since videos are just like any other file in OneDrive and SharePoint, handling ownership and retention after an employee leaves will follow the normal [OneDrive and SharePoint process]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process).</span></span>

<span data-ttu-id="6e07f-214">**会議のレコーディングを表示する権限を持つユーザー**</span><span class="sxs-lookup"><span data-stu-id="6e07f-214">**Who has the permissions to view the meeting recording?**</span></span>

- <span data-ttu-id="6e07f-215">チャネル以外の会議の場合、外部ユーザーを除くすべての会議出席者は、自動的に個別の共有リンクを取得します。</span><span class="sxs-lookup"><span data-stu-id="6e07f-215">For non-Channel meetings, all meeting invitees, except for external users, will automatically get a personally shared link.</span></span> <span data-ttu-id="6e07f-216">外部ユーザーは、会議の開催者、または会議のレコーディングを開始したユーザーによって、共有リストに明示的に追加される必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e07f-216">External users will need to be explicitly added to the shared list by the meeting organizer or the person who started the meeting recording.</span></span>

- <span data-ttu-id="6e07f-217">チャネル会議の場合、アクセス許可はチャネルの所有者とメンバーの一覧から継承されます。</span><span class="sxs-lookup"><span data-stu-id="6e07f-217">For Channel meetings, permissions are inherited from the owners and members list in the channel.</span></span>

<span data-ttu-id="6e07f-218">**トランスクリプトを管理する方法を教えてください。**</span><span class="sxs-lookup"><span data-stu-id="6e07f-218">**How can I manage transcripts?**</span></span>

<span data-ttu-id="6e07f-219">このプレビューを有効にすると、OneDrive および SharePoint に移行されたチームの会議の記録にクローズドキャプションは表示されません。</span><span class="sxs-lookup"><span data-stu-id="6e07f-219">Customers opting in to this preview will not have closed captions available on their Teams Meeting Recordings that are migrated to OneDrive and SharePoint.</span></span><span data-ttu-id="6e07f-220">英語のキャプションから始まり、2020年10月の会議のレコーディングまで、キャプションを追加しています。</span><span class="sxs-lookup"><span data-stu-id="6e07f-220">  We're working to add captioning, beginning with closed captions in English, to meeting recordings in October 2020.</span></span>

<span data-ttu-id="6e07f-221">[Teams のクラウドレコーディング](cloud-recording.md)で説明されているように、トランスクリプトを許可することを選択しているお客様のために、クローズドキャプションが Teams の会議レコーディングで利用可能になる</span><span class="sxs-lookup"><span data-stu-id="6e07f-221">Closed captions will be available on Teams Meeting Recordings for customers who have opted in to allow transcripts as described in [Teams cloud recordings](cloud-recording.md)</span></span>

<span data-ttu-id="6e07f-222">キャプションを使用すると、すべてのアビリティーについて包括的なコンテンツを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="6e07f-222">Captions help create inclusive content for viewers of all abilities.</span></span> <span data-ttu-id="6e07f-223">所有者としては、キャプションを非表示にすることができます。ただし、Teams からキャプションを削除しない限り、そのトランスクリプトはまだ Teams で利用できます。</span><span class="sxs-lookup"><span data-stu-id="6e07f-223">As an owner, you can hide captions, although the transcript will still be available on Teams unless you delete the captions from Teams.</span></span> <span data-ttu-id="6e07f-224">[会議のレコーディングをオンまたはオフにする方法を確認する](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)</span><span class="sxs-lookup"><span data-stu-id="6e07f-224">See [how to turn on or off meeting recordings](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)</span></span>

<span data-ttu-id="6e07f-225">クローズドキャプションは、会議が記録された時点からの、60日間の Teams 会議レコーディングでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6e07f-225">Closed captions are supported for Teams meeting recordings for 60 days from when the meeting is recorded.</span></span>

<span data-ttu-id="6e07f-226">**記憶域のクォータにどのように影響が及ぶか**</span><span class="sxs-lookup"><span data-stu-id="6e07f-226">**How will my storage quota be impacted**</span></span>

<span data-ttu-id="6e07f-227">Teams 会議のレコーディングファイルは、OneDrive for Business と SharePoint に保存されており、これらのサービスのクォータに含まれています。</span><span class="sxs-lookup"><span data-stu-id="6e07f-227">Teams meeting recording files live in OneDrive for Business and SharePoint and are included in your quota for those services.</span></span> <span data-ttu-id="6e07f-228">[SharePoint のクォータ](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas)と [OneDrive for business のクォータ] () を参照してください https://docs.microsoft.com/onedrive/set-default-storage-space) 。</span><span class="sxs-lookup"><span data-stu-id="6e07f-228">See [SharePoint quota](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) and [OneDrive for Business quota] (https://docs.microsoft.com/onedrive/set-default-storage-space).</span></span>

<span data-ttu-id="6e07f-229">**Teams 会議のレコーディングを再生するにはどうすればよいですか?**</span><span class="sxs-lookup"><span data-stu-id="6e07f-229">**How can I play a Teams meeting recording?**</span></span>

<span data-ttu-id="6e07f-230">ビデオは、ファイルにアクセスした場所に応じて、OneDrive for Business または SharePoint のビデオプレーヤーで再生されます。</span><span class="sxs-lookup"><span data-stu-id="6e07f-230">Your video will play on the video player of OneDrive for Business or SharePoint depending on where you access the file.</span></span>

<span data-ttu-id="6e07f-231">**おけるをストリームに追加する予定の場合、既存のビデオはそのままで、どれだけの時間がかかりますか?**</span><span class="sxs-lookup"><span data-stu-id="6e07f-231">**If you plan on deprecating adding to Stream, will existing videos stay as is and for how long?**</span></span>

<span data-ttu-id="6e07f-232">近い将来、プラットフォームとしてのストリームは廃止されることはありません。</span><span class="sxs-lookup"><span data-stu-id="6e07f-232">Stream as a platform won't be deprecated in the near future.</span></span> <span data-ttu-id="6e07f-233">現在ストリーム内に存在するビデオは、移行を開始するまでそのまま残ります。</span><span class="sxs-lookup"><span data-stu-id="6e07f-233">The videos that currently live in Stream will stay there until we start migrating.</span></span> <span data-ttu-id="6e07f-234">これらのビデオは、移行時にも ODSP に移行されます。</span><span class="sxs-lookup"><span data-stu-id="6e07f-234">Upon migration, those videos will be migrated to ODSP as well.</span></span> <span data-ttu-id="6e07f-235">詳細について [は、ここ](https://docs.microsoft.com/stream/streamnew/classic-migration) を確認してください。</span><span class="sxs-lookup"><span data-stu-id="6e07f-235">Check [here](https://docs.microsoft.com/stream/streamnew/classic-migration) for more information.</span></span>
