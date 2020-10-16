---
title: Microsoft Teams のデータの場所
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: anach, kehardy
description: この記事では、Microsoft Teams におけるデータの地理的な場所について説明します。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c16065a864ac82cdf5f11c0d2c8254b648731cac
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121687"
---
# <a name="location-of-data-in-microsoft-teams"></a><span data-ttu-id="74d6d-103">Microsoft Teams のデータの場所</span><span class="sxs-lookup"><span data-stu-id="74d6d-103">Location of data in Microsoft Teams</span></span>

<span data-ttu-id="74d6d-104">Teams のデータはご利用の Microsoft 365 または Office 365 の組織に関連付けられている地理的領域内に存在します。</span><span class="sxs-lookup"><span data-stu-id="74d6d-104">Data in Teams resides in the geographic region associated with your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="74d6d-105">現在、Teams は、オーストラリア、カナダ、フランス、ドイツ、インド、日本、南アフリカ、韓国、スイス (リヒテンシュタインを含む)、アラブ首長国連邦、英国、南北アメリカ、APAC、および EMEA 地域をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="74d6d-105">Currently, Teams supports the Australia, Canada, France, Germany, India, Japan, South Africa, South Korea, Switzerland (which includes Liechtenstein), the United Arab Emirates, United Kingdom, Americas, APAC, and EMEA regions.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="74d6d-106">Teams は現在、新しいテナントに対して、オーストラリア、カナダ、フランス、ドイツ、インド、日本、アラブ首長国連邦、英国、韓国、南アフリカ、スイス (リヒテンシュタインを含む) にデータ所在地を提供しています。</span><span class="sxs-lookup"><span data-stu-id="74d6d-106">Teams currently offers data residency in Australia, Canada, France, Germany, India, Japan, the United Arab Emirates, United Kingdom, South Korea, South Africa, and Switzerland (which includes Liechtenstein) for new tenants only.</span></span>
> <span data-ttu-id="74d6d-107">新しいテナントは、Teams に 1 人のユーザーもサインインさせていない任意のテナントとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="74d6d-107">A new tenant is defined as any tenant that hasn’t had a single user from the tenant sign in to Teams.</span></span> <span data-ttu-id="74d6d-108">オーストラリア、インド、日本、韓国の既存のテナントは、引き続き APAC 地域に保存されている Teams のデータを保有します。</span><span class="sxs-lookup"><span data-stu-id="74d6d-108">Existing tenants from Australia, India, Japan, and South Korea will continue to have their Teams data stored in the APAC region.</span></span> <span data-ttu-id="74d6d-109">カナダの既存のテナントのデータは、引き続き南北アメリカに保存されます。</span><span class="sxs-lookup"><span data-stu-id="74d6d-109">Existing tenants in Canada will continue to have their data stored in the Americas.</span></span> <span data-ttu-id="74d6d-110">フランス、ドイツ、リヒテンシュタイン、アラブ首長国連邦、英国、南アフリカ、スイスの既存のテナントは、そのデータが EMEA 地域に保存されます。</span><span class="sxs-lookup"><span data-stu-id="74d6d-110">Existing tenants in France, Germany, Liechtenstein, the United Arab Emirates, the United Kingdom, South Africa, and Switzerland will have their data stored in the EMEA region.</span></span>

## <a name="where-your-teams-data-is-stored"></a><span data-ttu-id="74d6d-111">Teams データの保存場所</span><span class="sxs-lookup"><span data-stu-id="74d6d-111">Where your Teams data is stored</span></span>

<span data-ttu-id="74d6d-112">ご利用のテナントのデータがどの地域に格納されるかを確認するには、[[Microsoft 365 管理センター]](https://portal.office.com/adminportal/home) > **[設定]** > **[組織プロファイル]** に移動してください。</span><span class="sxs-lookup"><span data-stu-id="74d6d-112">To see which region houses data for your tenant, go to the [Microsoft 365 admin center](https://portal.office.com/adminportal/home) > **Settings** > **Organization profile**.</span></span> <span data-ttu-id="74d6d-113">下にスクロールして **[データの場所]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="74d6d-113">Scroll down to **Data location**.</span></span>

![管理センターの、Teams を含む、データの場所の表を示すスクリーンショット](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="location-of-teams-data-at-rest"></a><span data-ttu-id="74d6d-115">Teams 保存データの場所</span><span class="sxs-lookup"><span data-stu-id="74d6d-115">Location of Teams data at rest</span></span>

<span data-ttu-id="74d6d-116">Teams データは、コンテンツの種類に応じて異なる方法で保存されます。</span><span class="sxs-lookup"><span data-stu-id="74d6d-116">Your Teams data is stored differently depending on the content type.</span></span> 

![Teams のコンテンツの種類とそれらが保存されている場所を示す図](media/location-of-data-storage-at-rest.png)

<span data-ttu-id="74d6d-118">詳細なディスカッションについては、「[Microsoft Teams アーキテクチャに関する Ignite ブレイクアウト セッション](https://channel9.msdn.com/Events/Ignite/Microsoft-Ignite-Orlando-2017/BRK3071)」を確認してください。</span><span class="sxs-lookup"><span data-stu-id="74d6d-118">Check out the [Ignite breakout session on Microsoft Teams architecture](https://channel9.msdn.com/Events/Ignite/Microsoft-Ignite-Orlando-2017/BRK3071) for an in-depth discussion.</span></span>

### <a name="core-teams-customer-data"></a><span data-ttu-id="74d6d-119">Teams の主要な顧客データ</span><span class="sxs-lookup"><span data-stu-id="74d6d-119">Core Teams customer data</span></span>

<span data-ttu-id="74d6d-120">テナントが、オーストラリア、カナダ、欧州連合、フランス、ドイツ、インド、日本、南アフリカ、韓国、スイス (リヒテンシュタインを含む)、アラブ首長国連邦、英国、または米国でプロビジョニングされている場合、Microsoft はその場所にのみ次の顧客データを保存します:</span><span class="sxs-lookup"><span data-stu-id="74d6d-120">If your tenant is provisioned in Australia, Canada, the European Union, France, Germany, India, Japan, South Africa, South Korea, Switzerland (which includes Liechtenstein), the United Arab Emirates, the United Kingdom, or the United States, Microsoft stores the following customer data at rest only within that location:</span></span>

- <span data-ttu-id="74d6d-121">Teams のチャット、チームとチャネルの会話、画像、ボイスメール メッセージ、および連絡先</span><span class="sxs-lookup"><span data-stu-id="74d6d-121">Teams chats, team and channel conversations, images, voicemail messages, and contacts</span></span>
- <span data-ttu-id="74d6d-122">SharePoint Online サイトのコンテンツと、そのサイト内に格納されているファイル</span><span class="sxs-lookup"><span data-stu-id="74d6d-122">SharePoint Online site content and the files stored within that site</span></span>
- <span data-ttu-id="74d6d-123">OneDrive for Business にアップロードしたファイル</span><span class="sxs-lookup"><span data-stu-id="74d6d-123">Files uploaded to OneDrive for Business</span></span>

#### <a name="chat-channel-messages-team-structure"></a><span data-ttu-id="74d6d-124">チャット、チャネル メッセージ、チーム構造</span><span class="sxs-lookup"><span data-stu-id="74d6d-124">Chat, channel messages, team structure</span></span>

<span data-ttu-id="74d6d-125">Teams のすべてのチームは、Microsoft 365 グループとその SharePoint サイトおよび Exchange メールボックスによって支えられています。</span><span class="sxs-lookup"><span data-stu-id="74d6d-125">Every team in Teams is backed by a Microsoft 365 Group and its SharePoint site and Exchange mailbox.</span></span> <span data-ttu-id="74d6d-126">プライベート チャット （グループ チャットを含む）、チャネルでの会話の一部として送信されるメッセージ、およびチームとチャネルの構造は、Azureで実行されているチャット サービスに格納されます。</span><span class="sxs-lookup"><span data-stu-id="74d6d-126">Private chats (including group chats), messages sent as part of a conversation in a channel, and the structure of teams and channels are stored in a chat service running in Azure.</span></span> <span data-ttu-id="74d6d-127">データは、情報保護機能を有効にするために、ユーザーおよびグループのメールボックスの隠しフォルダーにも格納されます。</span><span class="sxs-lookup"><span data-stu-id="74d6d-127">The data is also stored in a hidden folder in the user and group mailboxes to enable Information Protection features.</span></span>

#### <a name="voicemail-and-contacts"></a><span data-ttu-id="74d6d-128">ボイスメールと連絡先</span><span class="sxs-lookup"><span data-stu-id="74d6d-128">Voicemail and contacts</span></span>

<span data-ttu-id="74d6d-129">ボイスメールは Exchange に格納されます。</span><span class="sxs-lookup"><span data-stu-id="74d6d-129">Voicemails are stored in Exchange.</span></span> <span data-ttu-id="74d6d-130">連絡先は Exchange ベースのクラウド データ ストアに格納されます。</span><span class="sxs-lookup"><span data-stu-id="74d6d-130">Contacts are stored in Exchange-based cloud data store.</span></span> <span data-ttu-id="74d6d-131">Exchange と Exchange ベースのクラウド ストアは、世界中の各データ センター地域ですでにデータ所在地を提供しています。</span><span class="sxs-lookup"><span data-stu-id="74d6d-131">Exchange and the Exchange-based cloud store already provide data residency in each of the worldwide datacenter geos.</span></span> <span data-ttu-id="74d6d-132">すべてのチームについて、ボイスメールと連絡先は、オーストラリア、カナダ、フランス、ドイツ、インド、日本、アラブ首長国連邦、英国、南アフリカ、韓国、スイス (リヒテンシュタインを含む)、米国の国内に保存されています。</span><span class="sxs-lookup"><span data-stu-id="74d6d-132">For all teams, voicemail and contacts are stored in-country for Australia, Canada, France, Germany, India, Japan, the United Arab Emirates, the United Kingdom, South Africa, South Korea, Switzerland (includes Liechtenstein), and the United States.</span></span> <span data-ttu-id="74d6d-133">他のすべての国では、ファイルはテナントのアフィニティに基づいて米国、ヨーロッパ、またはアジア太平洋地域に保存されます。</span><span class="sxs-lookup"><span data-stu-id="74d6d-133">For all other countries, files are stored in the US, Europe, or Asia-Pacific location based on tenant affinity.</span></span>

#### <a name="images-and-media"></a><span data-ttu-id="74d6d-134">画像とメディア</span><span class="sxs-lookup"><span data-stu-id="74d6d-134">Images and media</span></span>

<span data-ttu-id="74d6d-135">チャットで使用されるメディア （保存されていないが、元の Giphy サービス URL への参照リンクである Giphy GIF を除き、Giphy は Microsoft 以外のサービスです） は、チャット サービスと同じ場所に展開される Azure ベースのメディア サービスに格納されます。</span><span class="sxs-lookup"><span data-stu-id="74d6d-135">Media used in chats (except for Giphy GIFs which aren't stored but are a reference link to the original Giphy service URL, Giphy is a non-Microsoft service) is stored in an Azure-based media service that is deployed to the same locations as the chat service.</span></span>

#### <a name="files"></a><span data-ttu-id="74d6d-136">ファイル</span><span class="sxs-lookup"><span data-stu-id="74d6d-136">Files</span></span>

<span data-ttu-id="74d6d-137">チャネルで共有されているファイル （OneNote と Wiki を含む） は、チームの SharePoint サイトに保存されます。</span><span class="sxs-lookup"><span data-stu-id="74d6d-137">Files (including OneNote and Wiki) that somebody shares in a channel are stored in the team’s SharePoint site.</span></span> <span data-ttu-id="74d6d-138">プライベート チャット、または会議中または通話中のチャットで共有されたファイルは、ファイルを共有するユーザーのビジネス アカウントの OneDrive にアップロードおよび保存されます。</span><span class="sxs-lookup"><span data-stu-id="74d6d-138">Files shared in a private chat or a chat during a meeting or call are uploaded and stored in the OneDrive for the Business account of the user who shares the file.</span></span> <span data-ttu-id="74d6d-139">Exchange、SharePoint、および OneDrive は、世界中の各データセンター地域ですでにデータの所在地を提供しています。</span><span class="sxs-lookup"><span data-stu-id="74d6d-139">Exchange, SharePoint and OneDrive already provide data residency in each of the worldwide datacenter geos.</span></span> <span data-ttu-id="74d6d-140">そのため、既存のお客様については、Teams エクスペリエンスの一部であるすべてのファイル、OneNote ノートブック、Teams wiki コンテンツ、メールボックスは、テナントのアフィニティに基づいた場所に既に保存されています。</span><span class="sxs-lookup"><span data-stu-id="74d6d-140">So, for existing customers, all files, OneNote notebooks, Teams wiki content, and mailboxes that are part of the Teams experience are already stored in the location based on your tenant affinity.</span></span> <span data-ttu-id="74d6d-141">ファイルは、オーストラリア、カナダ、フランス、ドイツ、インド、日本、アラブ首長国連邦、英国、南アフリカ、韓国、スイス (リヒテンシュタインを含む) の国内に保存されています。</span><span class="sxs-lookup"><span data-stu-id="74d6d-141">Files are stored in-country for Australia, Canada, France, Germany, India, Japan, the United Arab Emirates, the United Kingdom, South Africa, South Korea, and Switzerland (which includes Liechtenstein).</span></span> <span data-ttu-id="74d6d-142">他のすべての国では、ファイルはテナントのアフィニティに基づいて米国、ヨーロッパ、またはアジア太平洋地域に保存されます。</span><span class="sxs-lookup"><span data-stu-id="74d6d-142">For all other countries, files are stored in the US, Europe, or Asia Pacific location based on tenant affinity.</span></span>

### <a name="datacenter-locations"></a><span data-ttu-id="74d6d-143">データセンターの場所</span><span class="sxs-lookup"><span data-stu-id="74d6d-143">Datacenter locations</span></span>

<span data-ttu-id="74d6d-144">このセクションで説明する Teams サービスは、保存データを次の場所に保存します:</span><span class="sxs-lookup"><span data-stu-id="74d6d-144">The Teams services described in this section store data at rest in the following locations:</span></span>

|<span data-ttu-id="74d6d-145">国または地域</span><span class="sxs-lookup"><span data-stu-id="74d6d-145">Country or region</span></span>  |<span data-ttu-id="74d6d-146">データセンターの場所</span><span class="sxs-lookup"><span data-stu-id="74d6d-146">Datacenter location</span></span> |
|---------|---------|
|<span data-ttu-id="74d6d-147">オーストラリア</span><span class="sxs-lookup"><span data-stu-id="74d6d-147">Australia</span></span>   |<span data-ttu-id="74d6d-148">ニューサウスウェールズ州とビクトリア州</span><span class="sxs-lookup"><span data-stu-id="74d6d-148">New South Wales and Victoria</span></span>         |
|<span data-ttu-id="74d6d-149">カナダ</span><span class="sxs-lookup"><span data-stu-id="74d6d-149">Canada</span></span>    |<span data-ttu-id="74d6d-150">ケベックシティとトロント</span><span class="sxs-lookup"><span data-stu-id="74d6d-150">Quebec City and Toronto</span></span>         |
|<span data-ttu-id="74d6d-151">フランス</span><span class="sxs-lookup"><span data-stu-id="74d6d-151">France</span></span>    |<span data-ttu-id="74d6d-152">マルセイユとパリ</span><span class="sxs-lookup"><span data-stu-id="74d6d-152">Marseille and Paris</span></span>         |
|<span data-ttu-id="74d6d-153">ドイツ</span><span class="sxs-lookup"><span data-stu-id="74d6d-153">Germany</span></span>    |<span data-ttu-id="74d6d-154">ベルリンとフランクフルト</span><span class="sxs-lookup"><span data-stu-id="74d6d-154">Berlin and Frankfurt</span></span>      |
|<span data-ttu-id="74d6d-155">インド</span><span class="sxs-lookup"><span data-stu-id="74d6d-155">India</span></span>   |<span data-ttu-id="74d6d-156">チェンナイとプネー</span><span class="sxs-lookup"><span data-stu-id="74d6d-156">Chennai and Pune</span></span>        |
|<span data-ttu-id="74d6d-157">日本</span><span class="sxs-lookup"><span data-stu-id="74d6d-157">Japan</span></span>    |<span data-ttu-id="74d6d-158">東京 （埼玉） と大阪</span><span class="sxs-lookup"><span data-stu-id="74d6d-158">Tokyo (Saitama) and Osaka</span></span>         |
|<span data-ttu-id="74d6d-159">リヒテンシュタイン</span><span class="sxs-lookup"><span data-stu-id="74d6d-159">Liechtenstein</span></span>   |<span data-ttu-id="74d6d-160">ジュネーブとチューリッヒ</span><span class="sxs-lookup"><span data-stu-id="74d6d-160">Geneva and Zurich</span></span>       |
|<span data-ttu-id="74d6d-161">南アフリカ</span><span class="sxs-lookup"><span data-stu-id="74d6d-161">South Africa</span></span>     |<span data-ttu-id="74d6d-162">ヨハネスブルグとケープタウン</span><span class="sxs-lookup"><span data-stu-id="74d6d-162">Johannesburg and Cape Town</span></span>         |
|<span data-ttu-id="74d6d-163">韓国</span><span class="sxs-lookup"><span data-stu-id="74d6d-163">South Korea</span></span>     |<span data-ttu-id="74d6d-164">ソウルと釜山</span><span class="sxs-lookup"><span data-stu-id="74d6d-164">Seoul and Busan</span></span>         |
|<span data-ttu-id="74d6d-165">スイス</span><span class="sxs-lookup"><span data-stu-id="74d6d-165">Switzerland</span></span>    |<span data-ttu-id="74d6d-166">ジュネーブとチューリッヒ</span><span class="sxs-lookup"><span data-stu-id="74d6d-166">Geneva and Zurich</span></span>       |
|<span data-ttu-id="74d6d-167">アラブ首長国連邦</span><span class="sxs-lookup"><span data-stu-id="74d6d-167">United Arab Emirates</span></span>     |<span data-ttu-id="74d6d-168">アブダビとドバイ</span><span class="sxs-lookup"><span data-stu-id="74d6d-168">Abu Dhabi and Dubai</span></span>         |
|<span data-ttu-id="74d6d-169">英国</span><span class="sxs-lookup"><span data-stu-id="74d6d-169">United Kingdom</span></span>     | <span data-ttu-id="74d6d-170">カーディフとロンドン</span><span class="sxs-lookup"><span data-stu-id="74d6d-170">Cardiff and London</span></span>        |
|<span data-ttu-id="74d6d-171">南北アメリカ – 北および南 （アメリカ）</span><span class="sxs-lookup"><span data-stu-id="74d6d-171">Americas – North, and South (AMER)</span></span> |<span data-ttu-id="74d6d-172">カリフォルニア州ベイとバージニア州ボイドトン</span><span class="sxs-lookup"><span data-stu-id="74d6d-172">Bay, CA and Boydton, VA</span></span>       |
|<span data-ttu-id="74d6d-173">アジア太平洋 （APAC）</span><span class="sxs-lookup"><span data-stu-id="74d6d-173">Asia Pacific (APAC)</span></span>  |<span data-ttu-id="74d6d-174">シンガポールと香港</span><span class="sxs-lookup"><span data-stu-id="74d6d-174">Singapore and Hong Kong</span></span>        |
|<span data-ttu-id="74d6d-175">ヨーロッパ、中東、およびアジア （EMEA）</span><span class="sxs-lookup"><span data-stu-id="74d6d-175">Europe, Middle East, and Asia (EMEA)</span></span>   |<span data-ttu-id="74d6d-176">ダブリンとアムステルダム</span><span class="sxs-lookup"><span data-stu-id="74d6d-176">Dublin and Amsterdam</span></span>        |

> [!NOTE]
> <span data-ttu-id="74d6d-177">リヒテンシュタインの場合、保存データはジュネーブとチューリッヒのスイスのデータ センターに格納されます。</span><span class="sxs-lookup"><span data-stu-id="74d6d-177">For Liechtenstein, data is stored at rest in the Switzerland data centers in Geneva and Zurich.</span></span>

### <a name="data-stored-with-a-third-party-storage-provider"></a><span data-ttu-id="74d6d-178">サードパーティのストレージ プロバイダーに保存されているデータ</span><span class="sxs-lookup"><span data-stu-id="74d6d-178">Data stored with a third-party storage provider</span></span>

<span data-ttu-id="74d6d-179">ユーザーがサードパーティのストレージ プロバイダーを使用してファイルを保存することを許可している組織は、それらのサービスのストレージの場所に依存しているため、それらのサービスの保存データの場所を個別に確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="74d6d-179">Organizations who allow users to store files with a third-party storage provider are dependent on the storage location of those services and should, therefore, review the location of data at rest for those services separately.</span></span>

- <span data-ttu-id="74d6d-180">**タブ**: タブを使用すると、ユーザーがアプリとサービスの情報をチャネルにピン留めすることができます。</span><span class="sxs-lookup"><span data-stu-id="74d6d-180">**Tabs**: Tabs allow users to pin information from apps and services to a channel.</span></span> <span data-ttu-id="74d6d-181">したがって、データが保存されているタブの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="74d6d-181">Thus, it varies by type of the tab where the data is stored.</span></span> <span data-ttu-id="74d6d-182">タブ自体はデータを保存しません。</span><span class="sxs-lookup"><span data-stu-id="74d6d-182">The tab itself doesn't store any data.</span></span> <span data-ttu-id="74d6d-183">たとえば、[SharePoint] タブには、SharePoint サイト コレクションがプロビジョニングされた場所に基づいてデータが格納されます。</span><span class="sxs-lookup"><span data-stu-id="74d6d-183">For example, a SharePoint tab will store data based on where the SharePoint site collection was provisioned.</span></span> <span data-ttu-id="74d6d-184">パートナーからの情報を含むタブは、パートナーが使用するシステムにデータを直接保存し、ビューのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="74d6d-184">A tab that includes information from a partner will store the data directly in the system used by the partner and only present a view of it.</span></span>
- <span data-ttu-id="74d6d-185">**その他のパートナー アプリ**: Microsoft は、Teams エクスペリエンス内で使用している可能性のあるパートナーからのアプリとサービスに対して、データの所在地のサポートを提供していません。</span><span class="sxs-lookup"><span data-stu-id="74d6d-185">**Other partner apps**: Microsoft doesn't provide any data residency support for apps and services from partners that you might be using within the Teams experience.</span></span> <span data-ttu-id="74d6d-186">データが保存されている場所については、これらのソリューションの情報を直接確認してください。</span><span class="sxs-lookup"><span data-stu-id="74d6d-186">Review information from those solutions directly to learn about where their data is being stored.</span></span>

## <a name="see-also"></a><span data-ttu-id="74d6d-187">関連項目</span><span class="sxs-lookup"><span data-stu-id="74d6d-187">See also</span></span>

- [<span data-ttu-id="74d6d-188">Microsoft Teams はアラブ首長国連邦データ所在地を立ち上げます</span><span class="sxs-lookup"><span data-stu-id="74d6d-188">Microsoft Teams launches United Arab Emirates Data Residency</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-United-Arab-Emirates-Data-Residency/ba-p/980330)

- [<span data-ttu-id="74d6d-189">Microsoft Teams は韓国データ所在地を立ち上げます</span><span class="sxs-lookup"><span data-stu-id="74d6d-189">Microsoft Teams launches South Korean Data Residency</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Korea-Data-Residency/ba-p/789171)

- [<span data-ttu-id="74d6d-190">Microsoft Teams は南アフリカデータ所在地を立ち上げます</span><span class="sxs-lookup"><span data-stu-id="74d6d-190">Microsoft Teams launches South African Data Residency</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Africa-Data-Residency/ba-p/776611)

- [<span data-ttu-id="74d6d-191">Microsoft Teams はフランスデータ所在地を立ち上げます</span><span class="sxs-lookup"><span data-stu-id="74d6d-191">Microsoft Teams Launches France Data Residency</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-France-Data-Residency/ba-p/364466)

- [<span data-ttu-id="74d6d-192">Microsoft Teams はインドデータ所在地を立ち上げ、その他の地域は近日公開です</span><span class="sxs-lookup"><span data-stu-id="74d6d-192">Microsoft Teams launches India Data Residency, other geos coming soon</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-India-Data-Residency-other-geos-coming/ba-p/154083)

- [<span data-ttu-id="74d6d-193">Microsoft Teams はオーストラリアおよび日本のデータ所在地を立ち上げます</span><span class="sxs-lookup"><span data-stu-id="74d6d-193">Microsoft Teams Launches Australia and Japan Data Residency</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Australia-and-Japan-Data-Residency/ba-p/237827)

- [<span data-ttu-id="74d6d-194">Microsoft Teams はカナダデータ所在地を立ち上げ、オーストラリアと日本は近日公開です</span><span class="sxs-lookup"><span data-stu-id="74d6d-194">Microsoft Teams Launches Canada Data Residency, Australia and Japan coming soon</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Canada-Data-Residency-Australia-and/ba-p/227178)
