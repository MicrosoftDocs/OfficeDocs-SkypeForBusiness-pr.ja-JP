---
title: チームが、Office 365 の OneDrive と SharePoint のオンライン マルチが地域で有効なテナントの経験します。
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: snigdhav
description: Office 365 の OneDrive と SharePoint のオンライン マルチが地域で有効なテナントでチームを使用する方法について説明します。
localization_priority: Priority
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 343b15cd29f3ac40002bf7fe2851faea93f36288
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23860748"
---
<a name="teams-experience-in-an-office-365-onedrive-and-sharepoint-online-multi-geo-enabled-tenancy"></a><span data-ttu-id="c81fc-103">チームが、Office 365 の OneDrive と SharePoint のオンライン マルチが地域で有効なテナントの経験します。</span><span class="sxs-lookup"><span data-stu-id="c81fc-103">Teams experience in an Office 365 OneDrive and SharePoint Online Multi-Geo-enabled tenancy</span></span>
===========================================

<span data-ttu-id="c81fc-104">マイクロソフト チームは、グループ チャットのソフトウェア、Office 365 のチームワークのハブです。</span><span class="sxs-lookup"><span data-stu-id="c81fc-104">Microsoft Teams is group chat software, the hub for teamwork in Office 365.</span></span> <span data-ttu-id="c81fc-105">Office 365 のグループのサービスによって SharePoint Online と OneDrive とビジネスのファイル操作の電源です。</span><span class="sxs-lookup"><span data-stu-id="c81fc-105">It is powered by the Office 365 Groups service along with SharePoint Online and OneDrive for Business for its files experience.</span></span> <span data-ttu-id="c81fc-106">マルチ ・ Geo のオンライン ビジネス、SharePoint のテナント、テナントが北アメリカ、ヨーロッパ、オーストラリアなどの多くの地理的な場所に拡張するため、OneDrive ファイル経験を基になるがマルチ ・地域に対応しており、ファイルを使用して発生するチーム共同作業も複数の地域に注意してください。</span><span class="sxs-lookup"><span data-stu-id="c81fc-106">In a OneDrive for Business/SharePoint Online Multi-Geo tenancy, in which the tenant is extended to many geographic locations such as North America, Europe, and Australia, the underlying files experience is Multi-Geo aware, so the Teams experience with file collaboration is also Multi-Geo aware.</span></span> <span data-ttu-id="c81fc-107">これは、そのネイティブ ファイルの経験では複数の地域間でホストされている表面のファイルをチームの重要な最先端の機能です。</span><span class="sxs-lookup"><span data-stu-id="c81fc-107">This is a key leading-edge capability for Teams to surface files hosted across multiple Geos in its native files experience.</span></span>

<span data-ttu-id="c81fc-108">などでサテライト地域としてのヨーロッパと北米が中心的な地域として Contoso テナント、ヨーロッパ サテライト ユーザーがわかります左側ウィンドウで、[ファイル] タブの下にある OneDrive ファイルを自分が、ヨーロッパのデータの場所と、米国の状態でファイルがホストされています。es は、テナントの中央の場所です。</span><span class="sxs-lookup"><span data-stu-id="c81fc-108">For example, in a Contoso tenancy with Europe as a satellite Geo and North America as the central Geo, a European satellite user will see his or her OneDrive files under the Files tab in left pane, although the files are hosted in the Europe data location and the United States is the tenant’s central location.</span></span> <span data-ttu-id="c81fc-109">また、ユーザーは最新のビューのブレードの下にある最近使用したファイルにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c81fc-109">Also, the user can access the most recently used files under the Recent view blade.</span></span> <span data-ttu-id="c81fc-110">最近使用したファイルは他の地域のユーザーからのユーザーと共有されているファイルを含めることがあり、テナントが拡張されている他の地域の場所で習得することがあります。</span><span class="sxs-lookup"><span data-stu-id="c81fc-110">Recent files may include files shared with the user from users in other Geos and might be mastered in other Geo locations that the tenant is extended to.</span></span> 

<span data-ttu-id="c81fc-111">チームのグループ サイトも複数の地域に注意してください。</span><span class="sxs-lookup"><span data-stu-id="c81fc-111">A given Team’s group site is also Multi-Geo aware.</span></span> <span data-ttu-id="c81fc-112">サテライトのヨーロッパのユーザーは、チームを作成するが、ヨーロッパの場所に対応するサイトのグループを作成、ファイルに関連付けられているチームのグループは、その場所の残りの部分に保持されます。</span><span class="sxs-lookup"><span data-stu-id="c81fc-112">That is, if a European satellite user is creating a Team, the corresponding Groups site will be created in the Europe location and the files associated with that Team group will be kept at rest in that location.</span></span> <span data-ttu-id="c81fc-113">これらのファイルのデータの常駐サービスの約束を保持することをヨーロッパの場所に新しいファイルをアップロードして、ファイルの編集など、その後の経験が対象となります。</span><span class="sxs-lookup"><span data-stu-id="c81fc-113">Any subsequent experiences, such as uploading a new file or editing the file, will be targeted to that European location, keeping the promise of data residency for those files.</span></span> <span data-ttu-id="c81fc-114">これは、すべてが可能に、基になる財団の Office 365 のグループが複数地域の対応になります。</span><span class="sxs-lookup"><span data-stu-id="c81fc-114">This is all made possible by the underlying foundation Office 365 Groups becoming Multi-Geo aware.</span></span>

<span data-ttu-id="c81fc-115">複数地域のテナントが 1 つのグローバル テナントのため、実行中に参照投稿 @ サテライト ユーザーことがその場所に関係なく、世界中から同僚を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c81fc-115">Because a Multi-Geo tenancy is a single global tenant, during @ mentions satellite users will be able to see their colleagues from across the globe, no matter where they reside.</span></span> 

<span data-ttu-id="c81fc-116">チャットおよび会議のチームの経験内での IM のノートでの会話が複数地域を認識していないし、すべてのメモは、テナントの中央の場所の内部でのみ保持されます。</span><span class="sxs-lookup"><span data-stu-id="c81fc-116">Note that conversations in chats and meeting IM notes within the Teams experience are not Multi-Geo aware and are all kept only inside the central location of the tenant.</span></span> <span data-ttu-id="c81fc-117">通常、チャットは、常駐サービスのニーズをデータに適用されません。</span><span class="sxs-lookup"><span data-stu-id="c81fc-117">Typically, chat conversations aren’t applied to data residency needs.</span></span>

<span data-ttu-id="c81fc-118">Office 365 マルチ ・地域詳細については、[マイクロソフトの複数の地域の機能のページ](https://aka.ms/multi-geo)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c81fc-118">For more information about Office 365 Multi-Geo, refer to the [Microsoft Multi-Geo capabilities page](https://aka.ms/multi-geo).</span></span>