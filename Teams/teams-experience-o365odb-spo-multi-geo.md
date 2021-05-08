---
title: Teams Geo 対応環境Microsoft 365環境でのエクスペリエンスの向上
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- SPO_Content
ms.custom: seo-marvel-apr2020
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
description: この記事では、複数の geo 対応環境でTeamsをMicrosoft 365について学習します。
ms.openlocfilehash: a1b86cf83a0eabde81331e5311561aa1600d3c7e
ms.sourcegitcommit: ca2230a981a1e3c03437d1ecb8727d66ad6967f9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760540"
---
# <a name="teams-experience-in-a-microsoft-365-multi-geo-enabled-tenancy"></a><span data-ttu-id="c52fb-103">Teams Geo 対応テナントMicrosoft 365でのエクスペリエンスの向上</span><span class="sxs-lookup"><span data-stu-id="c52fb-103">Teams experience in a Microsoft 365 Multi-Geo-enabled tenancy</span></span>

<span data-ttu-id="c52fb-104">Microsoft Teamsは、グループ チャット ソフトウェアであり、チームワークのハブであり、Microsoft 365およびOffice 365。</span><span class="sxs-lookup"><span data-stu-id="c52fb-104">Microsoft Teams is group chat software, the hub for teamwork in Microsoft 365 and Office 365.</span></span> <span data-ttu-id="c52fb-105">Microsoft 365 Groups サービスを利用し、SharePoint Online とOneDrive for Businessファイルエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="c52fb-105">It's powered by the Microsoft 365 Groups service along with SharePoint Online and OneDrive for Business for its files experience.</span></span> <span data-ttu-id="c52fb-106">テナントが北米、ヨーロッパ、オーストラリアなどの多くの地理的な場所に拡張される OneDrive for Business/SharePoint Online Multi-Geo テナントでは、基になるファイル エクスペリエンスはマルチ geo 対応なので、Teams でのファイルコラボレーションのエクスペリエンスもマルチ geo 対応です。</span><span class="sxs-lookup"><span data-stu-id="c52fb-106">In a OneDrive for Business/SharePoint Online Multi-Geo tenancy, in which the tenant is extended to many geographic locations such as North America, Europe, and Australia, the underlying files experience is Multi-Geo-aware, so the Teams experience with file collaboration is also Multi-Geo-aware.</span></span> <span data-ttu-id="c52fb-107">この機能は、ネイティブ ファイル エクスペリエンスでTeams Geo でホストされているファイルを表示するための主要な最先端の機能です。</span><span class="sxs-lookup"><span data-stu-id="c52fb-107">This functionality is a key leading-edge capability for Teams to surface files that are hosted across multiple Geos in its native files experience.</span></span> <span data-ttu-id="c52fb-108">これには、他のOneNote Wiki ファイルも含まれます。</span><span class="sxs-lookup"><span data-stu-id="c52fb-108">This also includes OneNote and Wiki files.</span></span>

<span data-ttu-id="c52fb-109">たとえば、ヨーロッパを衛星 geo として、北米を中央 Geo として使用する Contoso テナントでは、ヨーロッパの衛星ユーザーは左側のウィンドウの [ファイル] タブに OneDrive ファイルを表示しますが、ファイルはヨーロッパのデータの場所でホストされ、米国はテナントの中央の場所です。</span><span class="sxs-lookup"><span data-stu-id="c52fb-109">For example, in a Contoso tenancy with Europe as a satellite Geo and North America as the central Geo, a European satellite user will see their OneDrive files under the **Files** tab in left pane, although the files are hosted in the Europe data location and the United States is the tenant’s central location.</span></span> <span data-ttu-id="c52fb-110">また、ユーザーは [最近使用したビュー] ブレードで、最近使用した **ファイルに** アクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c52fb-110">Also, the user can access the most recently used files under the **Recent** view blade.</span></span> <span data-ttu-id="c52fb-111">最近使用したファイルには、他の地理的な場所のユーザーから共有されたファイルが含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c52fb-111">Recent files may include files shared from users in other geo locations.</span></span> 

<span data-ttu-id="c52fb-112">特定のチームのSharePointサイトもマルチ geo 対応です。</span><span class="sxs-lookup"><span data-stu-id="c52fb-112">A given Team’s SharePoint site is also Multi-Geo-aware.</span></span> <span data-ttu-id="c52fb-113">つまり、ヨーロッパの衛星ユーザーがチームを作成している場合、対応するSharePointサイトがヨーロッパの場所に作成されます。</span><span class="sxs-lookup"><span data-stu-id="c52fb-113">That is, if a European satellite user is creating a Team, the corresponding SharePoint site will be created in the Europe location.</span></span> <span data-ttu-id="c52fb-114">そのチームに関連付けられているファイルは、その場所に保存されます。</span><span class="sxs-lookup"><span data-stu-id="c52fb-114">The files that are associated with that Team will be kept at rest in that location.</span></span> <span data-ttu-id="c52fb-115">新しいファイルのアップロードやファイルの編集などの後続のエクスペリエンスは、ヨーロッパの場所に保存され、それらのファイルのデータ常駐が約束されます。</span><span class="sxs-lookup"><span data-stu-id="c52fb-115">Any subsequent experiences, such as uploading a new file or editing the file, will be stored in that European location, keeping the promise of data residency for those files.</span></span>

<span data-ttu-id="c52fb-116">Multi-Geo テナントは 1 つのグローバル テナントなので、@ メンション中は、衛星ユーザーは、場所に関係なく、世界中から同僚を表示できます。</span><span class="sxs-lookup"><span data-stu-id="c52fb-116">Because a Multi-Geo tenancy is a single global tenant, during @ mentions satellite users will be able to see their colleagues from across the globe, no matter where they are.</span></span>

<span data-ttu-id="c52fb-117">Teams エクスペリエンス内のチャット、チャネル メッセージ、会議 IM ノート/チャットの会話は、マルチ geo 対応ではなんらテナントの中央の場所内にのみ保持されます。</span><span class="sxs-lookup"><span data-stu-id="c52fb-117">Conversations in chats, channels messages, and meeting IM notes/chats within the Teams experience aren't Multi-Geo-aware and are all kept only inside the central location of the tenant.</span></span> <span data-ttu-id="c52fb-118">通常、チャット会話はデータ常駐のニーズには適用されません。</span><span class="sxs-lookup"><span data-stu-id="c52fb-118">Typically, chat conversations aren’t applied to data residency needs.</span></span> <span data-ttu-id="c52fb-119">詳細については、「データの場所[」を参照Microsoft Teams。](location-of-data-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="c52fb-119">For more information, see [Location of data in Microsoft Teams](location-of-data-in-teams.md).</span></span>

<span data-ttu-id="c52fb-120">複数地域でのサポートは、Teamsロードマップ[Microsoft 365されています](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=70783)。</span><span class="sxs-lookup"><span data-stu-id="c52fb-120">Multi-Geo support for Teams is on the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=70783).</span></span>

<span data-ttu-id="c52fb-121">Multi-Geo の詳細については [、Microsoft Multi-Geo の機能に関するページを参照してください](https://aka.ms/multi-geo)。</span><span class="sxs-lookup"><span data-stu-id="c52fb-121">For more info about Multi-Geo, refer to the [Microsoft Multi-Geo capabilities page](https://aka.ms/multi-geo).</span></span>
