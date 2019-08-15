---
title: Microsoft Teams の制限事項と仕様
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karuanag
description: Microsoft Teams に適用される制限、仕様、およびその他の要件について説明します。
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: ecd31a243da999704b7d466b3dc93dd66fb7ac25
ms.sourcegitcommit: 9053c0d5ddb6be3ce3da85dffcde3f45dbc0ab7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "36407882"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a><span data-ttu-id="e0ff1-103">Microsoft Teams の制限事項と仕様</span><span class="sxs-lookup"><span data-stu-id="e0ff1-103">Limits and specifications for Microsoft Teams</span></span>

<span data-ttu-id="e0ff1-104">この記事では、Teams に適用される制限、仕様、およびその他の要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="e0ff1-104">This article describes some of the limits, specifications, and other requirements that apply to Teams.</span></span>

## <a name="teams-and-channels"></a><span data-ttu-id="e0ff1-105">Teams とチャネル</span><span class="sxs-lookup"><span data-stu-id="e0ff1-105">Teams and channels</span></span> 

|<span data-ttu-id="e0ff1-106">機能</span><span class="sxs-lookup"><span data-stu-id="e0ff1-106">Feature</span></span>    | <span data-ttu-id="e0ff1-107">上限</span><span class="sxs-lookup"><span data-stu-id="e0ff1-107">Maximum limit</span></span> |
|-----------|---------------|
|<span data-ttu-id="e0ff1-108">ユーザーが作成できるチームの数</span><span class="sxs-lookup"><span data-stu-id="e0ff1-108">Number of teams a user can create</span></span> | <span data-ttu-id="e0ff1-109">オブジェクト制限 250、&sup1</span><span class="sxs-lookup"><span data-stu-id="e0ff1-109">Subject to a 250 object limit&sup1;</span></span>         |
|<span data-ttu-id="e0ff1-110">チームのメンバーの数</span><span class="sxs-lookup"><span data-stu-id="e0ff1-110">Number of members in a team</span></span> | <span data-ttu-id="e0ff1-111">5,000</span><span class="sxs-lookup"><span data-stu-id="e0ff1-111">5,000</span></span>       |
|<span data-ttu-id="e0ff1-112">テナントで許可されている組織全体のチームの数</span><span class="sxs-lookup"><span data-stu-id="e0ff1-112">Number of org-wide teams allowed in a tenant</span></span> | <span data-ttu-id="e0ff1-113">5</span><span class="sxs-lookup"><span data-stu-id="e0ff1-113">5</span></span>     |
|<span data-ttu-id="e0ff1-114">[組織全体のチーム](create-an-org-wide-team.md)のメンバーの数</span><span class="sxs-lookup"><span data-stu-id="e0ff1-114">Number of members in an [org-wide team](create-an-org-wide-team.md)</span></span> | <span data-ttu-id="e0ff1-115">5,000</span><span class="sxs-lookup"><span data-stu-id="e0ff1-115">5,000</span></span>       |
|<span data-ttu-id="e0ff1-116">グローバル管理者を作成できるチームの数</span><span class="sxs-lookup"><span data-stu-id="e0ff1-116">Number of teams a global admin can create</span></span>        |  <span data-ttu-id="e0ff1-117">500,000</span><span class="sxs-lookup"><span data-stu-id="e0ff1-117">500,000</span></span>   |
|<span data-ttu-id="e0ff1-118">Office 365 テナントが持てるチームの数</span><span class="sxs-lookup"><span data-stu-id="e0ff1-118">Number of teams an Office 365 tenant can have</span></span>    | <span data-ttu-id="e0ff1-119">50万&sup2;</span><span class="sxs-lookup"><span data-stu-id="e0ff1-119">500,000&sup2;</span></span>     |
|<span data-ttu-id="e0ff1-120">チームごとのチャネル数</span><span class="sxs-lookup"><span data-stu-id="e0ff1-120">Number of channels per team</span></span>    | <span data-ttu-id="e0ff1-121">200 (削除されたチャンネルを含む) &sup3;</span><span class="sxs-lookup"><span data-stu-id="e0ff1-121">200 (includes deleted channels)&sup3;</span></span>         |

<span data-ttu-id="e0ff1-122">&sup1; Azure Active Directory の任意のディレクトリ オブジェクトは、この制限にカウントされます。</span><span class="sxs-lookup"><span data-stu-id="e0ff1-122">&sup1;Any directory object in Azure Active Directory counts towards this limit.</span></span> <span data-ttu-id="e0ff1-123">グローバル管理者は、[アプリケーションのアクセス許可](https://docs.microsoft.com/graph/permissions-reference)を使用して Microsoft Graph を呼び出すアプリと同様に、この制限から除外されます。</span><span class="sxs-lookup"><span data-stu-id="e0ff1-123">Global admins are exempt from this limit, as are apps calling Microsoft Graph using [application permissions](https://docs.microsoft.com/graph/permissions-reference).</span></span>

<span data-ttu-id="e0ff1-124">&sup2;この制限には、アーカイブされたチームが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e0ff1-124">&sup2;This limit includes archived teams.</span></span>

<span data-ttu-id="e0ff1-125">&sup3; 削除されたチャンネルは、30日以内に復元できます。</span><span class="sxs-lookup"><span data-stu-id="e0ff1-125">&sup3;Deleted channels can be restored within 30 days.</span></span> <span data-ttu-id="e0ff1-126">30日以内に、削除されたチャネルは、チームの上限に対して200チャネルに対してカウントされ続けます。</span><span class="sxs-lookup"><span data-stu-id="e0ff1-126">During these 30 days, a deleted channel continues to be counted towards the 200 channel per team limit.</span></span> <span data-ttu-id="e0ff1-127">30日が経過すると、削除されたチャネルとそのコンテンツは完全に削除され、チャネルはチームの制限に従って200チャネルにカウントされなくなります。</span><span class="sxs-lookup"><span data-stu-id="e0ff1-127">After 30 days, a deleted channel and its content are permanently deleted and the channel no longer counts towards the 200 channels per team limit.</span></span>

## <a name="channel-names"></a><span data-ttu-id="e0ff1-128">チャネル名</span><span class="sxs-lookup"><span data-stu-id="e0ff1-128">Channel names</span></span>

<span data-ttu-id="e0ff1-129">チャネル名には、次の文字または単語を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="e0ff1-129">Channel names can't contain the following characters or words.</span></span>

|||
|---------|---------|
|<span data-ttu-id="e0ff1-130">アルファベット</span><span class="sxs-lookup"><span data-stu-id="e0ff1-130">Characters</span></span>     | <span data-ttu-id="e0ff1-131">~ #% & \* {} +/\:  < > ?</span><span class="sxs-lookup"><span data-stu-id="e0ff1-131">~ # % & \* { } + / \ : < > ?</span></span> <span data-ttu-id="e0ff1-132">&#124; ' "..</span><span class="sxs-lookup"><span data-stu-id="e0ff1-132">&#124; ' " ..</span></span>        |
|<span data-ttu-id="e0ff1-133">これらの範囲に含まれる文字</span><span class="sxs-lookup"><span data-stu-id="e0ff1-133">Characters in these ranges</span></span>    | <span data-ttu-id="e0ff1-134">0 ~ 1F</span><span class="sxs-lookup"><span data-stu-id="e0ff1-134">0 to 1F</span></span><br><span data-ttu-id="e0ff1-135">80から9F</span><span class="sxs-lookup"><span data-stu-id="e0ff1-135">80 to 9F</span></span>        |
|<span data-ttu-id="e0ff1-136">いう</span><span class="sxs-lookup"><span data-stu-id="e0ff1-136">Words</span></span>     | <span data-ttu-id="e0ff1-137">フォーム、CON、CONIN $、CONIN $、PRN、AUX、NUL、COM1 から COM9、LPT1 から LPT9、desktop.ini、&#95;vti&#95;</span><span class="sxs-lookup"><span data-stu-id="e0ff1-137">forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1 to COM9, LPT1 to LPT9, desktop.ini,  &#95;vti&#95;</span></span>|

<span data-ttu-id="e0ff1-138">チャネル名には、アンダースコア (_) またはピリオド (.) で始めることも、ピリオド (.) で終わらせることもできません。</span><span class="sxs-lookup"><span data-stu-id="e0ff1-138">Channel names also can't start with an underscore (_) or period (.), or end with a period (.).</span></span>

## <a name="meetings-and-calls"></a><span data-ttu-id="e0ff1-139">会議と通話</span><span class="sxs-lookup"><span data-stu-id="e0ff1-139">Meetings and calls</span></span>

|<span data-ttu-id="e0ff1-140">機能</span><span class="sxs-lookup"><span data-stu-id="e0ff1-140">Feature</span></span>     | <span data-ttu-id="e0ff1-141">上限</span><span class="sxs-lookup"><span data-stu-id="e0ff1-141">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="e0ff1-142">会議に参加できるユーザー数</span><span class="sxs-lookup"><span data-stu-id="e0ff1-142">Number of people in a meeting</span></span>  | <span data-ttu-id="e0ff1-143">250</span><span class="sxs-lookup"><span data-stu-id="e0ff1-143">250</span></span>    |

## <a name="teams-live-events"></a><span data-ttu-id="e0ff1-144">Teams ライブイベント</span><span class="sxs-lookup"><span data-stu-id="e0ff1-144">Teams live events</span></span>

|<span data-ttu-id="e0ff1-145">機能</span><span class="sxs-lookup"><span data-stu-id="e0ff1-145">Feature</span></span>     | <span data-ttu-id="e0ff1-146">上限</span><span class="sxs-lookup"><span data-stu-id="e0ff1-146">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="e0ff1-147">対象ユーザーのサイズ</span><span class="sxs-lookup"><span data-stu-id="e0ff1-147">Audience size</span></span> | <span data-ttu-id="e0ff1-148">出席者 10,000 名</span><span class="sxs-lookup"><span data-stu-id="e0ff1-148">10,000 attendees</span></span> |
|<span data-ttu-id="e0ff1-149">イベントの期間</span><span class="sxs-lookup"><span data-stu-id="e0ff1-149">Duration of event</span></span> | <span data-ttu-id="e0ff1-150">4 時間</span><span class="sxs-lookup"><span data-stu-id="e0ff1-150">4 hours</span></span> |
|<span data-ttu-id="e0ff1-151">列</span><span class="sxs-lookup"><span data-stu-id="e0ff1-151">Column1</span></span>  |<span data-ttu-id="e0ff1-152">Column2</span><span class="sxs-lookup"><span data-stu-id="e0ff1-152">Column2</span></span>  |
|---------|---------|
|<span data-ttu-id="e0ff1-153">Row1</span><span class="sxs-lookup"><span data-stu-id="e0ff1-153">Row1</span></span>     |         |
|<span data-ttu-id="e0ff1-154">Row2</span><span class="sxs-lookup"><span data-stu-id="e0ff1-154">Row2</span></span>     |         |

<span data-ttu-id="e0ff1-155">|Office 365 テナントでの同時ライブイベント |15 |</span><span class="sxs-lookup"><span data-stu-id="e0ff1-155">|Concurrent live events in an Office 365 tenant | 15 |</span></span>

<span data-ttu-id="e0ff1-156">ライブイベントと、Teams ライブイベントと Skype 会議ブロードキャストの比較の詳細については、「 [teams live イベント」および「Skype 会議ブロードキャスト](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0ff1-156">For more information about live events and a comparison of Teams live events to Skype Meeting Broadcast, go to [Teams live events and Skype Meeting Broadcast](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast).</span></span>

## <a name="storage"></a><span data-ttu-id="e0ff1-157">ストレージ</span><span class="sxs-lookup"><span data-stu-id="e0ff1-157">Storage</span></span>

<span data-ttu-id="e0ff1-p104">Microsoft Teams の各チームには SharePoint Online にチーム サイトがあり、チーム内の各チャネルには既定のチーム サイト ドキュメント ライブラリが作成されます。会話内で共有したファイルはドキュメント ライブラリに自動的に格納されます。SharePoint で設定した権限やファイル セキュリティ オプションは Teams 内で自動的に反映されます。</span><span class="sxs-lookup"><span data-stu-id="e0ff1-p104">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library. Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

<span data-ttu-id="e0ff1-160">テナントで有効な SharePoint Online をお持ちでない場合は、 Microsoft Teams ユーザーがチーム内のファイルを共有することはできません。</span><span class="sxs-lookup"><span data-stu-id="e0ff1-160">If you don't have SharePoint Online enabled in your tenant, Microsoft Teams users cannot always share files in teams.</span></span> <span data-ttu-id="e0ff1-161">プライベート チャット内のユーザーもファイルを共有できません。これは OneDrive for Business (SharePoint のライセンスに関連付けられています) がその機能に必要だからです。</span><span class="sxs-lookup"><span data-stu-id="e0ff1-161">Users in private chat also cannot share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.</span></span>

<span data-ttu-id="e0ff1-162">SharePoint Online ドキュメント ライブラリと OneDrive for Business にファイルを格納することで、テナントレベルで構成されるすべてのコンプライアンス ルールが順守されます。</span><span class="sxs-lookup"><span data-stu-id="e0ff1-162">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> <span data-ttu-id="e0ff1-163">(詳しくは、[Microsoft Teams との SharePoint Online と OneDrive for Business の連携](sharepoint-onedrive-interact.md)をご確認ください。)</span><span class="sxs-lookup"><span data-stu-id="e0ff1-163">(For more, see [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).)</span></span>

<span data-ttu-id="e0ff1-164">Team は、SharePoint Online のバックエンドのファイル共有で実行しているために、SharePoint の制限は、Team 内のファイルのセクションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="e0ff1-164">Because Teams runs on a SharePoint Online backend for file sharing, SharePoint limitations apply to the Files section within a Team.</span></span> <span data-ttu-id="e0ff1-165">ここでは、SharePoint Online の適用可能な記憶域の制限を示します。</span><span class="sxs-lookup"><span data-stu-id="e0ff1-165">Here are the applicable storage limits for SharePoint Online.</span></span>

|<span data-ttu-id="e0ff1-166">機能</span><span class="sxs-lookup"><span data-stu-id="e0ff1-166">Feature</span></span>                 |<span data-ttu-id="e0ff1-167">Office 365 Business Essentials</span><span class="sxs-lookup"><span data-stu-id="e0ff1-167">Office 365 Business Essentials</span></span>  |<span data-ttu-id="e0ff1-168">Office 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="e0ff1-168">Office 365 Business Premium</span></span>   |<span data-ttu-id="e0ff1-169">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="e0ff1-169">Office 365 Enterprise E1</span></span>  |<span data-ttu-id="e0ff1-170">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="e0ff1-170">Office 365 Enterprise E3</span></span>  |<span data-ttu-id="e0ff1-171">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="e0ff1-171">Office 365 Enterprise E5</span></span>  |<span data-ttu-id="e0ff1-172">Office 365 Enterprise F1</span><span class="sxs-lookup"><span data-stu-id="e0ff1-172">Office 365 Enterprise F1</span></span>  |
|------------------------|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="e0ff1-173">ストレージ</span><span class="sxs-lookup"><span data-stu-id="e0ff1-173">Storage</span></span>                 |<span data-ttu-id="e0ff1-174">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="e0ff1-174">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="e0ff1-175">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="e0ff1-175">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="e0ff1-176">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="e0ff1-176">1 TB per organization plus 10 GB per license purchased</span></span>   |<span data-ttu-id="e0ff1-177">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="e0ff1-177">1 TB per organization plus 10 GB per license purchased</span></span> |<span data-ttu-id="e0ff1-178">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="e0ff1-178">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="e0ff1-179">1 組織につき 1 TB</span><span class="sxs-lookup"><span data-stu-id="e0ff1-179">1 TB per organization</span></span>           |
|<span data-ttu-id="e0ff1-180">Teams ファイル用のストレージ</span><span class="sxs-lookup"><span data-stu-id="e0ff1-180">Storage for Teams Files</span></span> |<span data-ttu-id="e0ff1-181">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="e0ff1-181">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="e0ff1-182">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="e0ff1-182">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="e0ff1-183">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="e0ff1-183">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="e0ff1-184">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="e0ff1-184">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="e0ff1-185">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="e0ff1-185">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="e0ff1-186">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="e0ff1-186">Up to 25 TB per site collection or group</span></span> |
|<span data-ttu-id="e0ff1-187">ファイルアップロードの上限 (ファイル単位)</span><span class="sxs-lookup"><span data-stu-id="e0ff1-187">File upload limit  (per file)</span></span>    |<span data-ttu-id="e0ff1-188">15 GB</span><span class="sxs-lookup"><span data-stu-id="e0ff1-188">15 GB</span></span>    |<span data-ttu-id="e0ff1-189">15 GB</span><span class="sxs-lookup"><span data-stu-id="e0ff1-189">15 GB</span></span>    |<span data-ttu-id="e0ff1-190">15 GB</span><span class="sxs-lookup"><span data-stu-id="e0ff1-190">15 GB</span></span>    |<span data-ttu-id="e0ff1-191">15 GB</span><span class="sxs-lookup"><span data-stu-id="e0ff1-191">15 GB</span></span>    |<span data-ttu-id="e0ff1-192">15 GB</span><span class="sxs-lookup"><span data-stu-id="e0ff1-192">15 GB</span></span>    |<span data-ttu-id="e0ff1-193">15 GB</span><span class="sxs-lookup"><span data-stu-id="e0ff1-193">15 GB</span></span>    |

<span data-ttu-id="e0ff1-194">チャネルは、チーム用に作成された SharePoint Online サイトコレクション内のフォルダーによってサポートされるため、チャネル内のファイルタブは、所属するチームの記憶域制限を共有します。</span><span class="sxs-lookup"><span data-stu-id="e0ff1-194">Channels are backed by folders within the SharePoint Online site collection created for the team, so file tabs within Channels share the storage limits of the team they belong to.</span></span>

<span data-ttu-id="e0ff1-195">詳細については、「[SharePoint Online の制限事項](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0ff1-195">For more information, see [SharePoint Online limits](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span></span>

## <a name="messaging"></a><span data-ttu-id="e0ff1-196">メッセージング </span><span class="sxs-lookup"><span data-stu-id="e0ff1-196">Messaging</span></span>

<span data-ttu-id="e0ff1-197">Microsoft Teams のチャット リストの一部である会話に参加したユーザーが、管理者がチャットの会話を検索するための Exchange Online (クラウドベース) メールボックスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0ff1-197">Users who participate in conversations that are part of the Chat list in Microsoft Teams must have an Exchange Online (cloud-based) mailbox for an admin to search chat conversations.</span></span> <span data-ttu-id="e0ff1-198">これは、チャット リストの一部である会話が、チャット参加者のクラウドベースのメールボックスに保存されるためです。</span><span class="sxs-lookup"><span data-stu-id="e0ff1-198">That's because conversations that are part of the Chat list are stored in the cloud-based mailboxes of the chat participants.</span></span> <span data-ttu-id="e0ff1-199">チャット参加者が Exchange Online メールボックスを持っていない場合、管理者はチャットの会話を検索または保留することはできません。</span><span class="sxs-lookup"><span data-stu-id="e0ff1-199">If a chat participant doesn't have an Exchange Online mailbox, the admin won't be able to search or place a hold on chat conversations.</span></span> <span data-ttu-id="e0ff1-200">たとえば、Exchange ハイブリッド展開では、オンプレミスのメールボックスを持つユーザーは、Microsoft Teams のチャットリストの一部である会話に参加できる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e0ff1-200">For example, in an Exchange hybrid deployment, users with on-premises mailboxes might be able to participate in conversations that are part of the Chat list in Microsoft Teams.</span></span> <span data-ttu-id="e0ff1-201">ただし、この例では、ユーザーがクラウド ベースのメールボックスを持っていないために、これらの会話のコンテンツを検索できないし、保留することもできません。</span><span class="sxs-lookup"><span data-stu-id="e0ff1-201">However, in this case, content from these conversations isn't searchable and can't be placed on hold because the users don't have cloud-based mailboxes.</span></span> <span data-ttu-id="e0ff1-202">(詳しくは、[Exchange と Microsoft Teams の連携](exchange-teams-interact.md)をご確認ください。)</span><span class="sxs-lookup"><span data-stu-id="e0ff1-202">(For more, see [How Exchange and Microsoft Teams interact](exchange-teams-interact.md).)</span></span>

<span data-ttu-id="e0ff1-203">Microsoft Teams チャット機能は、Microsoft Exchange のバックエンドで動作するため、Microsoft Teams 内のチャット機能にExchange メッセージングの制限を適用することができます。</span><span class="sxs-lookup"><span data-stu-id="e0ff1-203">Microsoft Teams chat function works on a Microsoft Exchange backend, so you can apply the Exchange messaging limits to the chat function within Microsoft Teams.</span></span> <span data-ttu-id="e0ff1-204">ユーザーが Teams のチャネルにメールを送信する場合、チャネルのメール アドレスを使用します。</span><span class="sxs-lookup"><span data-stu-id="e0ff1-204">If users want to send an email to a channel in Teams, they use the channel email address.</span></span> <span data-ttu-id="e0ff1-205">一度メールがチャネルの一部になると、誰でもそれに返信して会話を開始できます。</span><span class="sxs-lookup"><span data-stu-id="e0ff1-205">Once an email is part of a channel, anyone can reply to it to start a conversation.</span></span> <span data-ttu-id="e0ff1-206">チャネルにメールを送信するための適用可能な制限の一部を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e0ff1-206">Here are some of the applicable limits for sending email to a channel.</span></span> 

|<span data-ttu-id="e0ff1-207">機能</span><span class="sxs-lookup"><span data-stu-id="e0ff1-207">Feature</span></span>  | <span data-ttu-id="e0ff1-208">上限</span><span class="sxs-lookup"><span data-stu-id="e0ff1-208">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="e0ff1-209">プライベート チャットに参加できるユーザー数</span><span class="sxs-lookup"><span data-stu-id="e0ff1-209">Number of people in a private chat</span></span>  | <span data-ttu-id="e0ff1-210">100</span><span class="sxs-lookup"><span data-stu-id="e0ff1-210">100</span></span>    |
|<span data-ttu-id="e0ff1-211">メッセージサイズ&dagger;</span><span class="sxs-lookup"><span data-stu-id="e0ff1-211">Message size &dagger;</span></span>  |<span data-ttu-id="e0ff1-212">25 KB</span><span class="sxs-lookup"><span data-stu-id="e0ff1-212">25 KB</span></span>   |
|<span data-ttu-id="e0ff1-213">添付ファイルの数&Dagger;</span><span class="sxs-lookup"><span data-stu-id="e0ff1-213">Number of file attachments &Dagger;</span></span>  |<span data-ttu-id="e0ff1-214">常用</span><span class="sxs-lookup"><span data-stu-id="e0ff1-214">10</span></span>     |
|<span data-ttu-id="e0ff1-215">インライン画像の数&Dagger;</span><span class="sxs-lookup"><span data-stu-id="e0ff1-215">Number of inline images &Dagger;</span></span> |<span data-ttu-id="e0ff1-216">50</span><span class="sxs-lookup"><span data-stu-id="e0ff1-216">50</span></span>   |

<span data-ttu-id="e0ff1-217">&dagger; メッセージがこの制限を超えると、プレビュー メッセージが生成され、ユーザーは提供されたリンクから元のメールを表示/ダウンロードするように求められます。</span><span class="sxs-lookup"><span data-stu-id="e0ff1-217">&dagger; If the message exceeds this limit, a preview message is generated and the user is asked to view/download the original email from the link provided.</span></span>

<span data-ttu-id="e0ff1-218">&Dagger;添付ファイルまたは画像の数がこの制限を超えると、メッセージは処理されず、NDR メールが送信者に送信され、エラーが通知されます。</span><span class="sxs-lookup"><span data-stu-id="e0ff1-218">&Dagger; If the number of attachments or images exceeds this limit, the message will not be processed and an NDR email will be sent back to the sender notifying them of the error.</span></span>

> [!NOTE]
> <span data-ttu-id="e0ff1-219">メッセージサイズ、添付ファイル、インライン画像の制限は、すべての Office 365 ライセンスで同じです。</span><span class="sxs-lookup"><span data-stu-id="e0ff1-219">The message size, file attachments, and inline images limits are the same across all Office 365 licenses.</span></span>

<span data-ttu-id="e0ff1-220">詳細については、[「 Exchange Online の制限 」](https://technet.microsoft.com/library/exchange-online-limits.aspx)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e0ff1-220">For more information, see [Exchange Online limits](https://technet.microsoft.com/library/exchange-online-limits.aspx).</span></span>

## <a name="browsers"></a><span data-ttu-id="e0ff1-221">ブラウザー</span><span class="sxs-lookup"><span data-stu-id="e0ff1-221">Browsers</span></span>

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a><span data-ttu-id="e0ff1-222">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="e0ff1-222">Operating systems</span></span>

<span data-ttu-id="e0ff1-223">各オペレーティング システムの要件については、「[Microsoft Teams のクライアントを取得する](get-clients.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e0ff1-223">For information about operating system requirements, see [Get clients for Microsoft Teams](get-clients.md).</span></span>
