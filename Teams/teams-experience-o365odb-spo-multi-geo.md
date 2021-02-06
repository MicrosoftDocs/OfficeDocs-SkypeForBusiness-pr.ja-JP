---
title: Microsoft 365 Multi-Geo 対応環境での Teams のエクスペリエンス
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
description: この記事では、Microsoft 365 Multi-Geo 対応環境での Teams の使用について説明します。
ms.openlocfilehash: 43abe221c6159e6dfed1705f5cbc4839c1ce57db
ms.sourcegitcommit: 93d84e172cb4b19acde4b8bae9b77efe96c44c00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122247"
---
# <a name="teams-experience-in-a-microsoft-365-multi-geo-enabled-tenancy"></a><span data-ttu-id="0cc76-103">Microsoft 365 Multi-Geo 対応テナントでの Teams のエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="0cc76-103">Teams experience in a Microsoft 365 Multi-Geo-enabled tenancy</span></span>

<span data-ttu-id="0cc76-104">Microsoft Teams は、Microsoft 365 および Office 365 のチームワークのハブです。</span><span class="sxs-lookup"><span data-stu-id="0cc76-104">Microsoft Teams is group chat software, the hub for teamwork in Microsoft 365 and Office 365.</span></span> <span data-ttu-id="0cc76-105">Microsoft 365 Groups サービスを利用し、SharePoint Online や OneDrive for Business でファイルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0cc76-105">It's powered by the Microsoft 365 Groups service along with SharePoint Online and OneDrive for Business for its files experience.</span></span> <span data-ttu-id="0cc76-106">テナントが北米、ヨーロッパ、オーストラリアなどの多くの地理的な場所に拡張される OneDrive for Business/SharePoint Online Multi-Geo テナントでは、基になるファイル エクスペリエンスはマルチジオ対応なので、Teams でのファイルの共同作業のエクスペリエンスもマルチジオ対応です。</span><span class="sxs-lookup"><span data-stu-id="0cc76-106">In a OneDrive for Business/SharePoint Online Multi-Geo tenancy, in which the tenant is extended to many geographic locations such as North America, Europe, and Australia, the underlying files experience is Multi-Geo-aware, so the Teams experience with file collaboration is also Multi-Geo-aware.</span></span> <span data-ttu-id="0cc76-107">この機能は、Teams がネイティブ ファイル エクスペリエンスで複数の地域でホストされているファイルを表示するための主要な最先端機能です。</span><span class="sxs-lookup"><span data-stu-id="0cc76-107">This functionality is a key leading-edge capability for Teams to surface files that are hosted across multiple Geos in its native files experience.</span></span> <span data-ttu-id="0cc76-108">これには、OneNote ファイルと Wiki ファイルも含まれます。</span><span class="sxs-lookup"><span data-stu-id="0cc76-108">This also includes OneNote and Wiki files.</span></span>

<span data-ttu-id="0cc76-109">たとえば、Contoso テナントでは、ヨーロッパを衛星地域として、北米を中心地域として使用している場合、ヨーロッパの衛星ユーザーは、左側のウィンドウの [ファイル] タブの下に OneDrive ファイルが表示されます。ただし、ファイルはヨーロッパのデータの場所でホストされ、米国はテナントの中心的な場所です。</span><span class="sxs-lookup"><span data-stu-id="0cc76-109">For example, in a Contoso tenancy with Europe as a satellite Geo and North America as the central Geo, a European satellite user will see their OneDrive files under the **Files** tab in left pane, although the files are hosted in the Europe data location and the United States is the tenant’s central location.</span></span> <span data-ttu-id="0cc76-110">また、ユーザーは [最近使ったビュー] ブレードの下で、最近使用した **ファイルに** アクセスできます。</span><span class="sxs-lookup"><span data-stu-id="0cc76-110">Also, the user can access the most recently used files under the **Recent** view blade.</span></span> <span data-ttu-id="0cc76-111">最近使用したファイルには、他の地域のユーザーから共有されたファイルが含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="0cc76-111">Recent files may include files shared from users in other geo locations.</span></span> 

<span data-ttu-id="0cc76-112">特定のチームの SharePoint サイトも、複数の地域を認識しています。</span><span class="sxs-lookup"><span data-stu-id="0cc76-112">A given Team’s SharePoint site is also Multi-Geo-aware.</span></span> <span data-ttu-id="0cc76-113">つまり、ヨーロッパの衛星ユーザーがチームを作成している場合、対応する SharePoint サイトがヨーロッパの場所に作成されます。</span><span class="sxs-lookup"><span data-stu-id="0cc76-113">That is, if a European satellite user is creating a Team, the corresponding SharePoint site will be created in the Europe location.</span></span> <span data-ttu-id="0cc76-114">そのチームに関連付けられているファイルは、その場所に保存されます。</span><span class="sxs-lookup"><span data-stu-id="0cc76-114">The files that are associated with that Team will be kept at rest in that location.</span></span> <span data-ttu-id="0cc76-115">新しいファイルのアップロードやファイルの編集など、その後のエクスペリエンスはヨーロッパの場所に保存され、それらのファイルに対するデータ常駐の約束が保たれるでしょう。</span><span class="sxs-lookup"><span data-stu-id="0cc76-115">Any subsequent experiences, such as uploading a new file or editing the file, will be stored in that European location, keeping the promise of data residency for those files.</span></span>

<span data-ttu-id="0cc76-116">複数地域テナントは 1 つのグローバル テナントなので、@ メンションの間、衛星ユーザーは、場所に関係なく、世界中の同僚を見る可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0cc76-116">Because a Multi-Geo tenancy is a single global tenant, during @ mentions satellite users will be able to see their colleagues from across the globe, no matter where they are.</span></span>

<span data-ttu-id="0cc76-117">Teams エクスペリエンス内のチャット、チャネル メッセージ、会議 IM ノート/チャット内の会話は、マルチジオ対応ではなんらテナントの中心的な場所にのみ保存されます。</span><span class="sxs-lookup"><span data-stu-id="0cc76-117">Conversations in chats, channels messages, and meeting IM notes/chats within the Teams experience aren't Multi-Geo-aware and are all kept only inside the central location of the tenant.</span></span> <span data-ttu-id="0cc76-118">通常、チャットの会話はデータ常駐のニーズには適用されません。</span><span class="sxs-lookup"><span data-stu-id="0cc76-118">Typically, chat conversations aren’t applied to data residency needs.</span></span> <span data-ttu-id="0cc76-119">詳細については [、「Microsoft Teams のデータの場所」を参照してください](location-of-data-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="0cc76-119">For more information, see [Location of data in Microsoft Teams](location-of-data-in-teams.md).</span></span>

<span data-ttu-id="0cc76-120">Multi-Geo の詳細については [、Microsoft Multi-Geo](https://aka.ms/multi-geo)の機能ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0cc76-120">For more info about Multi-Geo, refer to the [Microsoft Multi-Geo capabilities page](https://aka.ms/multi-geo).</span></span>
