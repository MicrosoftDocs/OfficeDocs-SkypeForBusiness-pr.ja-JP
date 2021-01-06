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
ms.openlocfilehash: 1a1689d78f6ce4e35b2e632e4a46ff0ec23a0d15
ms.sourcegitcommit: 7575fb476a594d70084c603e508dd311ef1d7edb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/05/2021
ms.locfileid: "49757752"
---
# <a name="teams-experience-in-a-microsoft-365-multi-geo-enabled-tenancy"></a><span data-ttu-id="c32ad-103">Microsoft 365 Multi-Geo 対応テナントでの Teams のエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="c32ad-103">Teams experience in a Microsoft 365 Multi-Geo-enabled tenancy</span></span>

<span data-ttu-id="c32ad-104">Microsoft Teams は、Microsoft 365 のチームワークのハブであるグループ チャット ソフトウェアです。</span><span class="sxs-lookup"><span data-stu-id="c32ad-104">Microsoft Teams is group chat software, the hub for teamwork in Microsoft 365.</span></span> <span data-ttu-id="c32ad-105">Microsoft 365 Groups サービスを利用し、SharePoint や OneDrive と共にファイルのエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="c32ad-105">It is powered by the Microsoft 365 Groups service along with SharePoint and OneDrive for its files experience.</span></span> <span data-ttu-id="c32ad-106">テナントが北米、ヨーロッパ、オーストラリアなどの多くの地理的な場所に拡張されている複数地域の組織では、基になるファイル エクスペリエンスはマルチジオを認識しています。そのため、ファイルの共同作業に関する Teams のエクスペリエンスも複数地域対応です。</span><span class="sxs-lookup"><span data-stu-id="c32ad-106">In a Multi-Geo organization in which the tenant is extended to many geographic locations such as North America, Europe, and Australia, the underlying files experience is Multi-Geo aware, so the Teams experience with file collaboration is also Multi-Geo aware.</span></span> <span data-ttu-id="c32ad-107">これにより、Teams はネイティブ ファイル エクスペリエンスで複数の地理的な場所にホストされているファイルを表示できます。</span><span class="sxs-lookup"><span data-stu-id="c32ad-107">This allows Teams to surface files hosted across multiple geo locations in its native files experience.</span></span>

<span data-ttu-id="c32ad-108">たとえば、Contoso テナントでは、ヨーロッパを衛星地域として、北米を中心地域として使用している場合、ヨーロッパの衛星ユーザーには、左側のウィンドウの [ファイル] タブの下に OneDrive ファイルが表示されます。ただし、ファイルはヨーロッパのデータの場所でホストされ、米国はテナントの中心的な場所です。</span><span class="sxs-lookup"><span data-stu-id="c32ad-108">For example, in a Contoso tenancy with Europe as a satellite Geo and North America as the central Geo, a European satellite user will see his or her OneDrive files under the Files tab in left pane, although the files are hosted in the Europe data location and the United States is the tenant’s central location.</span></span> <span data-ttu-id="c32ad-109">また、ユーザーは [最近使ったビュー] ブレードの下で、最近使用したファイルにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c32ad-109">Also, the user can access the most recently used files under the Recent view blade.</span></span> <span data-ttu-id="c32ad-110">最近使用したファイルには、他の地域のユーザーから共有されたファイルが含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c32ad-110">Recent files may include files shared from users in other geo locations.</span></span> 

<span data-ttu-id="c32ad-111">特定のチームの SharePoint サイトも複数の地域を認識しています。</span><span class="sxs-lookup"><span data-stu-id="c32ad-111">A given Team’s SharePoint site is also Multi-Geo aware.</span></span> <span data-ttu-id="c32ad-112">つまり、ヨーロッパの衛星ユーザーがチームを作成している場合、対応する SharePoint サイトはヨーロッパの場所に作成され、そのチームに関連付けられているファイルは、その場所に保存されます。</span><span class="sxs-lookup"><span data-stu-id="c32ad-112">That is, if a European satellite user is creating a Team, the corresponding SharePoint site will be created in the Europe location and the files associated with that Team will be kept at rest in that location.</span></span> <span data-ttu-id="c32ad-113">新しいファイルのアップロードやファイルの編集など、その後のエクスペリエンスはヨーロッパの場所に保存され、それらのファイルに対するデータ常駐の約束が保たれるでしょう。</span><span class="sxs-lookup"><span data-stu-id="c32ad-113">Any subsequent experiences, such as uploading a new file or editing the file, will be stored in that European location, keeping the promise of data residency for those files.</span></span>

<span data-ttu-id="c32ad-114">Teams エクスペリエンス内のチャットや会議 IM ノート内の会話は、複数地域を認識しているのではなく、すべて組織内の中心的な場所にのみ保持されます。</span><span class="sxs-lookup"><span data-stu-id="c32ad-114">Note that conversations in chats and meeting IM notes within the Teams experience are not Multi-Geo aware and are all kept only inside the central location of the organization.</span></span>

<span data-ttu-id="c32ad-115">複数地域の詳細については [、Microsoft Multi-Geo の機能を参照してください](https://aka.ms/multi-geo)。</span><span class="sxs-lookup"><span data-stu-id="c32ad-115">For more information about Multi-Geo, see [Microsoft Multi-Geo capabilities](https://aka.ms/multi-geo).</span></span>
