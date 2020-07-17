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
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121687"
---
# <a name="location-of-data-in-microsoft-teams"></a><span data-ttu-id="43950-103">Microsoft Teams のデータの場所</span><span class="sxs-lookup"><span data-stu-id="43950-103">Location of data in Microsoft Teams</span></span>

<span data-ttu-id="43950-104">Teams のデータは、Microsoft 365 または Office 365 組織に関連付けられた地理的地域内に存在します。</span><span class="sxs-lookup"><span data-stu-id="43950-104">Data in Teams resides in the geographic region associated with your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="43950-105">現在、Teams でサポートされているのは、オーストラリア、カナダ、フランス、ドイツ、インド、日本、南アフリカ、韓国、スイス (リヒテンシュタインを含む)、英国連邦、英国、南北アメリカ、APAC、および EMEA 地域です。</span><span class="sxs-lookup"><span data-stu-id="43950-105">Currently, Teams supports the Australia, Canada, France, Germany, India, Japan, South Africa, South Korea, Switzerland (which includes Liechtenstein), the United Arab Emirates, United Kingdom, Americas, APAC, and EMEA regions.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="43950-106">Teams では現在、オーストラリア、カナダ、フランス、ドイツ、インド、日本、英国、英国、韓国、南アフリカ、スイス (リヒテンシュタインを含む) で、新しいテナントのみにデータ常駐品が提供されています。</span><span class="sxs-lookup"><span data-stu-id="43950-106">Teams currently offers data residency in Australia, Canada, France, Germany, India, Japan, the United Arab Emirates, United Kingdom, South Korea, South Africa, and Switzerland (which includes Liechtenstein) for new tenants only.</span></span>
> <span data-ttu-id="43950-107">新しいテナントは、Teams に 1 人のユーザーもサインインさせていない任意のテナントとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="43950-107">A new tenant is defined as any tenant that hasn’t had a single user from the tenant sign in to Teams.</span></span> <span data-ttu-id="43950-108">オーストラリア、インド、日本、韓国の既存のテナントは、引き続き APAC 地域に保存されています。</span><span class="sxs-lookup"><span data-stu-id="43950-108">Existing tenants from Australia, India, Japan, and South Korea will continue to have their Teams data stored in the APAC region.</span></span> <span data-ttu-id="43950-109">カナダの既存のテナントのデータは、南北アメリカに保存され続けます。</span><span class="sxs-lookup"><span data-stu-id="43950-109">Existing tenants in Canada will continue to have their data stored in the Americas.</span></span> <span data-ttu-id="43950-110">フランス、ドイツ、リヒテンシュタイン、アラブ首長国連邦、英国、南アフリカ、スイスの既存のテナントには、EMEA 地域にデータが保存されています。</span><span class="sxs-lookup"><span data-stu-id="43950-110">Existing tenants in France, Germany, Liechtenstein, the United Arab Emirates, the United Kingdom, South Africa, and Switzerland will have their data stored in the EMEA region.</span></span>

## <a name="where-your-teams-data-is-stored"></a><span data-ttu-id="43950-111">チームデータが保存されている場所</span><span class="sxs-lookup"><span data-stu-id="43950-111">Where your Teams data is stored</span></span>

<span data-ttu-id="43950-112">テナントのデータが格納されている領域を確認するには、 [Microsoft 365 管理センター](https://portal.office.com/adminportal/home)の  >  **設定**  >  **組織プロファイル**に移動します。</span><span class="sxs-lookup"><span data-stu-id="43950-112">To see which region houses data for your tenant, go to the [Microsoft 365 admin center](https://portal.office.com/adminportal/home) > **Settings** > **Organization profile**.</span></span> <span data-ttu-id="43950-113">下にスクロールして **[データの場所]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="43950-113">Scroll down to **Data location**.</span></span>

![管理センターの Teams を含むデータの場所テーブルのスクリーンショット](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="location-of-teams-data-at-rest"></a><span data-ttu-id="43950-115">残りのチームデータの場所</span><span class="sxs-lookup"><span data-stu-id="43950-115">Location of Teams data at rest</span></span>

<span data-ttu-id="43950-116">チームデータの保存場所は、コンテンツの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="43950-116">Your Teams data is stored differently depending on the content type.</span></span> 

![Teams コンテンツタイプと保存場所に保存されている場所を示す図](media/location-of-data-storage-at-rest.png)

<span data-ttu-id="43950-118">詳細については、「 [Microsoft Teams アーキテクチャでの Ignite の分科セッション](https://channel9.msdn.com/Events/Ignite/Microsoft-Ignite-Orlando-2017/BRK3071)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43950-118">Check out the [Ignite breakout session on Microsoft Teams architecture](https://channel9.msdn.com/Events/Ignite/Microsoft-Ignite-Orlando-2017/BRK3071) for an in-depth discussion.</span></span>

### <a name="core-teams-customer-data"></a><span data-ttu-id="43950-119">主要な Teams の顧客データ</span><span class="sxs-lookup"><span data-stu-id="43950-119">Core Teams customer data</span></span>

<span data-ttu-id="43950-120">お客様のテナントが、オーストラリア、カナダ、欧州連合、フランス、ドイツ、インド、日本、南アフリカ、韓国、スイス (リヒテンシュタインを含む)、英国連邦、英国、または米国内にある場合は、次のお客様のデータが保持されている場所に保存されます。</span><span class="sxs-lookup"><span data-stu-id="43950-120">If your tenant is provisioned in Australia, Canada, the European Union, France, Germany, India, Japan, South Africa, South Korea, Switzerland (which includes Liechtenstein), the United Arab Emirates, the United Kingdom, or the United States, Microsoft stores the following customer data at rest only within that location:</span></span>

- <span data-ttu-id="43950-121">チームチャット、チームとチャネルでの会話、画像、ボイスメールメッセージ、連絡先</span><span class="sxs-lookup"><span data-stu-id="43950-121">Teams chats, team and channel conversations, images, voicemail messages, and contacts</span></span>
- <span data-ttu-id="43950-122">SharePoint Online サイトのコンテンツと、そのサイト内に保存されているファイル</span><span class="sxs-lookup"><span data-stu-id="43950-122">SharePoint Online site content and the files stored within that site</span></span>
- <span data-ttu-id="43950-123">OneDrive for Business にアップロードされたファイル</span><span class="sxs-lookup"><span data-stu-id="43950-123">Files uploaded to OneDrive for Business</span></span>

#### <a name="chat-channel-messages-team-structure"></a><span data-ttu-id="43950-124">チャット、チャネルメッセージ、チーム構造</span><span class="sxs-lookup"><span data-stu-id="43950-124">Chat, channel messages, team structure</span></span>

<span data-ttu-id="43950-125">Teams のすべてのチームは、Microsoft 365 グループとその SharePoint サイトと Exchange メールボックスによってサポートされます。</span><span class="sxs-lookup"><span data-stu-id="43950-125">Every team in Teams is backed by a Microsoft 365 Group and its SharePoint site and Exchange mailbox.</span></span> <span data-ttu-id="43950-126">プライベートチャット (グループチャットを含む)、チャネルでの会話の一部として送信されるメッセージ、チームとチャネルの構造は、Azure で実行されているチャットサービスに格納されます。</span><span class="sxs-lookup"><span data-stu-id="43950-126">Private chats (including group chats), messages sent as part of a conversation in a channel, and the structure of teams and channels are stored in a chat service running in Azure.</span></span> <span data-ttu-id="43950-127">また、データは、情報保護機能を有効にするために、ユーザーとグループのメールボックスの隠しフォルダーにも保存されています。</span><span class="sxs-lookup"><span data-stu-id="43950-127">The data is also stored in a hidden folder in the user and group mailboxes to enable Information Protection features.</span></span>

#### <a name="voicemail-and-contacts"></a><span data-ttu-id="43950-128">ボイスメールと連絡先</span><span class="sxs-lookup"><span data-stu-id="43950-128">Voicemail and contacts</span></span>

<span data-ttu-id="43950-129">ボイスメールは Exchange に格納されます。</span><span class="sxs-lookup"><span data-stu-id="43950-129">Voicemails are stored in Exchange.</span></span> <span data-ttu-id="43950-130">連絡先は Exchange ベースのクラウドデータストアに保存されます。</span><span class="sxs-lookup"><span data-stu-id="43950-130">Contacts are stored in Exchange-based cloud data store.</span></span> <span data-ttu-id="43950-131">Exchange と Exchange ベースのクラウドストアでは、世界各地の datacenter geos のそれぞれにデータ常駐サービスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="43950-131">Exchange and the Exchange-based cloud store already provide data residency in each of the worldwide datacenter geos.</span></span> <span data-ttu-id="43950-132">すべてのチームの場合、ボイスメールと連絡先は、オーストラリア、カナダ、フランス、ドイツ、インド、日本、英国、英国、南アフリカ、韓国、スイス (リヒテンシュタインを含む)、および米国に保存されています。</span><span class="sxs-lookup"><span data-stu-id="43950-132">For all teams, voicemail and contacts are stored in-country for Australia, Canada, France, Germany, India, Japan, the United Arab Emirates, the United Kingdom, South Africa, South Korea, Switzerland (includes Liechtenstein), and the United States.</span></span> <span data-ttu-id="43950-133">その他の国の場合、ファイルは、テナントのアフィニティに基づいて米国、ヨーロッパ、またはアジア太平洋地域に保存されます。</span><span class="sxs-lookup"><span data-stu-id="43950-133">For all other countries, files are stored in the US, Europe, or Asia-Pacific location based on tenant affinity.</span></span>

#### <a name="images-and-media"></a><span data-ttu-id="43950-134">画像とメディア</span><span class="sxs-lookup"><span data-stu-id="43950-134">Images and media</span></span>

<span data-ttu-id="43950-135">チャットで使用されるメディア (保存されていないが、元の Giphy サービス URL への参照リンクであるのに対して) は、チャットサービスと同じ場所に展開された Azure ベースメディアサービスに格納されます。</span><span class="sxs-lookup"><span data-stu-id="43950-135">Media used in chats (except for Giphy GIFs which aren't stored but are a reference link to the original Giphy service URL, Giphy is a non-Microsoft service) is stored in an Azure-based media service that is deployed to the same locations as the chat service.</span></span>

#### <a name="files"></a><span data-ttu-id="43950-136">ファイル</span><span class="sxs-lookup"><span data-stu-id="43950-136">Files</span></span>

<span data-ttu-id="43950-137">チャネルで他の人が共有しているファイル (OneNote や Wiki を含む) は、チームの SharePoint サイトに保存されます。</span><span class="sxs-lookup"><span data-stu-id="43950-137">Files (including OneNote and Wiki) that somebody shares in a channel are stored in the team’s SharePoint site.</span></span> <span data-ttu-id="43950-138">会議または通話中にプライベートチャットまたはチャットで共有されたファイルは、ファイルを共有しているユーザーのビジネスアカウント用の OneDrive にアップロードおよび保存されます。</span><span class="sxs-lookup"><span data-stu-id="43950-138">Files shared in a private chat or a chat during a meeting or call are uploaded and stored in the OneDrive for the Business account of the user who shares the file.</span></span> <span data-ttu-id="43950-139">Exchange、SharePoint、OneDrive では、世界各地の各 datacenter geos でデータ常駐サービスを既に提供しています。</span><span class="sxs-lookup"><span data-stu-id="43950-139">Exchange, SharePoint and OneDrive already provide data residency in each of the worldwide datacenter geos.</span></span> <span data-ttu-id="43950-140">したがって、既存のユーザーについては、すべてのファイル、OneNote ノートブック、チーム wiki コンテンツ、チームエクスペリエンスの一部であるメールボックスは、テナントのアフィニティに基づいて既に場所に保存されています。</span><span class="sxs-lookup"><span data-stu-id="43950-140">So, for existing customers, all files, OneNote notebooks, Teams wiki content, and mailboxes that are part of the Teams experience are already stored in the location based on your tenant affinity.</span></span> <span data-ttu-id="43950-141">ファイルは、オーストラリア、カナダ、フランス、ドイツ、インド、日本、英国、英国、南アフリカ、韓国、スイス (リヒテンシュタインを含む) の国内に保存されています。</span><span class="sxs-lookup"><span data-stu-id="43950-141">Files are stored in-country for Australia, Canada, France, Germany, India, Japan, the United Arab Emirates, the United Kingdom, South Africa, South Korea, and Switzerland (which includes Liechtenstein).</span></span> <span data-ttu-id="43950-142">その他の国の場合、ファイルは、テナントのアフィニティに基づいて米国、ヨーロッパ、またはアジア太平洋地域の場所に保存されます。</span><span class="sxs-lookup"><span data-stu-id="43950-142">For all other countries, files are stored in the US, Europe, or Asia Pacific location based on tenant affinity.</span></span>

### <a name="datacenter-locations"></a><span data-ttu-id="43950-143">データセンターの場所</span><span class="sxs-lookup"><span data-stu-id="43950-143">Datacenter locations</span></span>

<span data-ttu-id="43950-144">このセクションで説明する Teams サービスは、残りのデータを次の場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="43950-144">The Teams services described in this section store data at rest in the following locations:</span></span>

|<span data-ttu-id="43950-145">国または地域</span><span class="sxs-lookup"><span data-stu-id="43950-145">Country or region</span></span>  |<span data-ttu-id="43950-146">データセンターの場所</span><span class="sxs-lookup"><span data-stu-id="43950-146">Datacenter location</span></span> |
|---------|---------|
|<span data-ttu-id="43950-147">オーストラリア</span><span class="sxs-lookup"><span data-stu-id="43950-147">Australia</span></span>   |<span data-ttu-id="43950-148">新しいサウスウェールズと Victoria</span><span class="sxs-lookup"><span data-stu-id="43950-148">New South Wales and Victoria</span></span>         |
|<span data-ttu-id="43950-149">カナダ</span><span class="sxs-lookup"><span data-stu-id="43950-149">Canada</span></span>    |<span data-ttu-id="43950-150">ケベック市とトロント</span><span class="sxs-lookup"><span data-stu-id="43950-150">Quebec City and Toronto</span></span>         |
|<span data-ttu-id="43950-151">フランス</span><span class="sxs-lookup"><span data-stu-id="43950-151">France</span></span>    |<span data-ttu-id="43950-152">Marseille とパリ</span><span class="sxs-lookup"><span data-stu-id="43950-152">Marseille and Paris</span></span>         |
|<span data-ttu-id="43950-153">ドイツ</span><span class="sxs-lookup"><span data-stu-id="43950-153">Germany</span></span>    |<span data-ttu-id="43950-154">ベルリンと Frankfurt</span><span class="sxs-lookup"><span data-stu-id="43950-154">Berlin and Frankfurt</span></span>      |
|<span data-ttu-id="43950-155">インド</span><span class="sxs-lookup"><span data-stu-id="43950-155">India</span></span>   |<span data-ttu-id="43950-156">チェンナイ (と Pune</span><span class="sxs-lookup"><span data-stu-id="43950-156">Chennai and Pune</span></span>        |
|<span data-ttu-id="43950-157">日本</span><span class="sxs-lookup"><span data-stu-id="43950-157">Japan</span></span>    |<span data-ttu-id="43950-158">東京 (Saitama) および大阪 ()</span><span class="sxs-lookup"><span data-stu-id="43950-158">Tokyo (Saitama) and Osaka</span></span>         |
|<span data-ttu-id="43950-159">リヒテンシュタイン</span><span class="sxs-lookup"><span data-stu-id="43950-159">Liechtenstein</span></span>   |<span data-ttu-id="43950-160">ジュネーブと Zurich</span><span class="sxs-lookup"><span data-stu-id="43950-160">Geneva and Zurich</span></span>       |
|<span data-ttu-id="43950-161">南アフリカ</span><span class="sxs-lookup"><span data-stu-id="43950-161">South Africa</span></span>     |<span data-ttu-id="43950-162">ヨハネルブルグとカーボベルデ</span><span class="sxs-lookup"><span data-stu-id="43950-162">Johannesburg and Cape Town</span></span>         |
|<span data-ttu-id="43950-163">韓国</span><span class="sxs-lookup"><span data-stu-id="43950-163">South Korea</span></span>     |<span data-ttu-id="43950-164">ソウルと Busan</span><span class="sxs-lookup"><span data-stu-id="43950-164">Seoul and Busan</span></span>         |
|<span data-ttu-id="43950-165">スイス</span><span class="sxs-lookup"><span data-stu-id="43950-165">Switzerland</span></span>    |<span data-ttu-id="43950-166">ジュネーブと Zurich</span><span class="sxs-lookup"><span data-stu-id="43950-166">Geneva and Zurich</span></span>       |
|<span data-ttu-id="43950-167">アラブ首長国連邦</span><span class="sxs-lookup"><span data-stu-id="43950-167">United Arab Emirates</span></span>     |<span data-ttu-id="43950-168">アブダビと Dubai</span><span class="sxs-lookup"><span data-stu-id="43950-168">Abu Dhabi and Dubai</span></span>         |
|<span data-ttu-id="43950-169">英国</span><span class="sxs-lookup"><span data-stu-id="43950-169">United Kingdom</span></span>     | <span data-ttu-id="43950-170">Cardiff と London</span><span class="sxs-lookup"><span data-stu-id="43950-170">Cardiff and London</span></span>        |
|<span data-ttu-id="43950-171">南北アメリカ–北、南 (AMER)</span><span class="sxs-lookup"><span data-stu-id="43950-171">Americas – North, and South (AMER)</span></span> |<span data-ttu-id="43950-172">Bay、CA、Boydton、VA</span><span class="sxs-lookup"><span data-stu-id="43950-172">Bay, CA and Boydton, VA</span></span>       |
|<span data-ttu-id="43950-173">アジア太平洋 (APAC)</span><span class="sxs-lookup"><span data-stu-id="43950-173">Asia Pacific (APAC)</span></span>  |<span data-ttu-id="43950-174">シンガポール・香港</span><span class="sxs-lookup"><span data-stu-id="43950-174">Singapore and Hong Kong</span></span>        |
|<span data-ttu-id="43950-175">ヨーロッパ、中東、アジア (EMEA)</span><span class="sxs-lookup"><span data-stu-id="43950-175">Europe, Middle East, and Asia (EMEA)</span></span>   |<span data-ttu-id="43950-176">ダブリンとアムステルダム</span><span class="sxs-lookup"><span data-stu-id="43950-176">Dublin and Amsterdam</span></span>        |

> [!NOTE]
> <span data-ttu-id="43950-177">リヒテンシュタインの場合、データはジュネーブと Zurich のスイスのデータセンターの残りの部分に保存されます。</span><span class="sxs-lookup"><span data-stu-id="43950-177">For Liechtenstein, data is stored at rest in the Switzerland data centers in Geneva and Zurich.</span></span>

### <a name="data-stored-with-a-third-party-storage-provider"></a><span data-ttu-id="43950-178">サードパーティストレージプロバイダーと共に保存されているデータ</span><span class="sxs-lookup"><span data-stu-id="43950-178">Data stored with a third-party storage provider</span></span>

<span data-ttu-id="43950-179">ユーザーがサードパーティストレージプロバイダーを使用してファイルを保存することを許可している組織は、それらのサービスの保存場所に依存しているため、残りのサービスのデータの場所を個別に確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="43950-179">Organizations who allow users to store files with a third-party storage provider are dependent on the storage location of those services and should, therefore, review the location of data at rest for those services separately.</span></span>

- <span data-ttu-id="43950-180">**タブ**: タブでは、ユーザーがアプリやサービスからチャネルに情報をピン留めすることができます。</span><span class="sxs-lookup"><span data-stu-id="43950-180">**Tabs**: Tabs allow users to pin information from apps and services to a channel.</span></span> <span data-ttu-id="43950-181">そのため、データが保存されているタブの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="43950-181">Thus, it varies by type of the tab where the data is stored.</span></span> <span data-ttu-id="43950-182">タブ自体にデータが保存されることはありません。</span><span class="sxs-lookup"><span data-stu-id="43950-182">The tab itself doesn't store any data.</span></span> <span data-ttu-id="43950-183">たとえば、SharePoint のタブには、SharePoint サイトコレクションがプロビジョニングされた場所に基づいてデータが保存されます。</span><span class="sxs-lookup"><span data-stu-id="43950-183">For example, a SharePoint tab will store data based on where the SharePoint site collection was provisioned.</span></span> <span data-ttu-id="43950-184">パートナーからの情報を含むタブは、パートナーによって使用されているシステムにデータを直接保存し、ビューを表示します。</span><span class="sxs-lookup"><span data-stu-id="43950-184">A tab that includes information from a partner will store the data directly in the system used by the partner and only present a view of it.</span></span>
- <span data-ttu-id="43950-185">**その他のパートナーアプリ**: Microsoft は、Teams のエクスペリエンス内で使用されているパートナーからのアプリやサービスに対して、データ常駐サポートを提供していません。</span><span class="sxs-lookup"><span data-stu-id="43950-185">**Other partner apps**: Microsoft doesn't provide any data residency support for apps and services from partners that you might be using within the Teams experience.</span></span> <span data-ttu-id="43950-186">これらのソリューションの情報を直接確認して、データの保存場所について確認します。</span><span class="sxs-lookup"><span data-stu-id="43950-186">Review information from those solutions directly to learn about where their data is being stored.</span></span>

## <a name="see-also"></a><span data-ttu-id="43950-187">関連項目</span><span class="sxs-lookup"><span data-stu-id="43950-187">See also</span></span>

- [<span data-ttu-id="43950-188">Microsoft Teams でアラブ首長国のデータ常駐サービスを開始</span><span class="sxs-lookup"><span data-stu-id="43950-188">Microsoft Teams launches United Arab Emirates Data Residency</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-United-Arab-Emirates-Data-Residency/ba-p/980330)

- [<span data-ttu-id="43950-189">Microsoft Teams で韓国のデータ常駐サービスが起動する</span><span class="sxs-lookup"><span data-stu-id="43950-189">Microsoft Teams launches South Korean Data Residency</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Korea-Data-Residency/ba-p/789171)

- [<span data-ttu-id="43950-190">Microsoft Teams が南アフリカのデータ常駐サービスを発表</span><span class="sxs-lookup"><span data-stu-id="43950-190">Microsoft Teams launches South African Data Residency</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Africa-Data-Residency/ba-p/776611)

- [<span data-ttu-id="43950-191">Microsoft Teams がフランスのデータ常駐サービスを起動する</span><span class="sxs-lookup"><span data-stu-id="43950-191">Microsoft Teams Launches France Data Residency</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-France-Data-Residency/ba-p/364466)

- [<span data-ttu-id="43950-192">Microsoft Teams がインドのデータ配信を開始します。その他の geos は近日中に公開されます。</span><span class="sxs-lookup"><span data-stu-id="43950-192">Microsoft Teams launches India Data Residency, other geos coming soon</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-India-Data-Residency-other-geos-coming/ba-p/154083)

- [<span data-ttu-id="43950-193">Microsoft Teams がオーストラリアおよび日本のデータ常駐サービスを発表</span><span class="sxs-lookup"><span data-stu-id="43950-193">Microsoft Teams Launches Australia and Japan Data Residency</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Australia-and-Japan-Data-Residency/ba-p/237827)

- [<span data-ttu-id="43950-194">Microsoft Teams では、近日中にカナダのデータ常駐、オーストラリア、日本が発売されます</span><span class="sxs-lookup"><span data-stu-id="43950-194">Microsoft Teams Launches Canada Data Residency, Australia and Japan coming soon</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Canada-Data-Residency-Australia-and/ba-p/227178)
