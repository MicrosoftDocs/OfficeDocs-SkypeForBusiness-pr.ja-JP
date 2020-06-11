---
title: Microsoft 365 または Office 365 OneDrive および SharePoint Online の複数の地域に対応したテナントでの Teams の操作
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
audience: admin
description: この記事では、Microsoft 365 または Office 365 OneDrive と SharePoint Online の複数の Geo 対応のテナントで Teams を使用する方法について説明します。
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
ms.openlocfilehash: de73dc3edff66bfe8b427e570bfc661e1dec46b4
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2020
ms.locfileid: "44689683"
---
<a name="teams-experience-in-a-microsoft-365-or-office-365-onedrive-and-sharepoint-online-multi-geo-enabled-tenancy"></a><span data-ttu-id="d3ba2-103">Microsoft 365 または Office 365 OneDrive および SharePoint Online の複数の地域に対応したテナントでの Teams の操作</span><span class="sxs-lookup"><span data-stu-id="d3ba2-103">Teams experience in a Microsoft 365 or Office 365 OneDrive and SharePoint Online Multi-Geo-enabled tenancy</span></span>
===========================================

<span data-ttu-id="d3ba2-104">Microsoft Teams は、グループチャットソフトウェアであり、Microsoft 365 および Office 365 でのチームワークのハブです。</span><span class="sxs-lookup"><span data-stu-id="d3ba2-104">Microsoft Teams is group chat software, the hub for teamwork in Microsoft 365 and Office 365.</span></span> <span data-ttu-id="d3ba2-105">この機能は、Microsoft 365 Groups サービスと SharePoint Online および OneDrive for Business のファイルエクスペリエンスによって実現されています。</span><span class="sxs-lookup"><span data-stu-id="d3ba2-105">It is powered by the Microsoft 365 Groups service along with SharePoint Online and OneDrive for Business for its files experience.</span></span> <span data-ttu-id="d3ba2-106">OneDrive for Business または SharePoint Online の複数地域のテナント (北米、ヨーロッパ、オーストラリアなどの多くの地理的な場所にテナントが拡張されているため、基盤となるファイルのエクスペリエンスは複数の地域に対応しているため、ファイルの共同作業でも複数の地域に対応しています。</span><span class="sxs-lookup"><span data-stu-id="d3ba2-106">In a OneDrive for Business/SharePoint Online Multi-Geo tenancy, in which the tenant is extended to many geographic locations such as North America, Europe, and Australia, the underlying files experience is Multi-Geo aware, so the Teams experience with file collaboration is also Multi-Geo aware.</span></span> <span data-ttu-id="d3ba2-107">これは、ネイティブファイルエクスペリエンスで複数の Geos でホストされているファイルを処理するための主要な最先端機能です。</span><span class="sxs-lookup"><span data-stu-id="d3ba2-107">This is a key leading-edge capability for Teams to surface files hosted across multiple Geos in its native files experience.</span></span>

<span data-ttu-id="d3ba2-108">たとえば、ヨーロッパを使用する Contoso のテナントが、中央の Geo としてサテライトの Geo および北米として表示されている場合、ファイルはヨーロッパのデータの場所でホストされていますが、米国はテナントの中央の場所であるということです。</span><span class="sxs-lookup"><span data-stu-id="d3ba2-108">For example, in a Contoso tenancy with Europe as a satellite Geo and North America as the central Geo, a European satellite user will see his or her OneDrive files under the Files tab in left pane, although the files are hosted in the Europe data location and the United States is the tenant’s central location.</span></span> <span data-ttu-id="d3ba2-109">また、最新のビューブレードで、最近使用したファイルにアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d3ba2-109">Also, the user can access the most recently used files under the Recent view blade.</span></span> <span data-ttu-id="d3ba2-110">最近使用したファイルには、他の Geos のユーザーから共有されているファイルが含まれている可能性があります。また、テナントが拡張されている他の Geo の場所でもそのようになっている場合</span><span class="sxs-lookup"><span data-stu-id="d3ba2-110">Recent files may include files shared with the user from users in other Geos and might be mastered in other Geo locations that the tenant is extended to.</span></span> 

<span data-ttu-id="d3ba2-111">特定のチームのグループサイトも、複数の地域に対応しています。</span><span class="sxs-lookup"><span data-stu-id="d3ba2-111">A given Team’s group site is also Multi-Geo aware.</span></span> <span data-ttu-id="d3ba2-112">つまり、ヨーロッパのサテライトユーザーがチームを作成している場合、対応するグループサイトはヨーロッパの場所に作成され、そのチームグループに関連付けられたファイルは、その場所の残りの部分に保存されます。</span><span class="sxs-lookup"><span data-stu-id="d3ba2-112">That is, if a European satellite user is creating a Team, the corresponding Groups site will be created in the Europe location and the files associated with that Team group will be kept at rest in that location.</span></span> <span data-ttu-id="d3ba2-113">新しいファイルをアップロードしたり、ファイルを編集したりするなど、以降のすべてのエクスペリエンスは、そのヨーロッパの場所を対象としているため、これらのファイルに対してデータを確実に保持できます。</span><span class="sxs-lookup"><span data-stu-id="d3ba2-113">Any subsequent experiences, such as uploading a new file or editing the file, will be targeted to that European location, keeping the promise of data residency for those files.</span></span> <span data-ttu-id="d3ba2-114">これは、基本的な foundation Microsoft 365 グループによって、複数の地域に対応するようになりました。</span><span class="sxs-lookup"><span data-stu-id="d3ba2-114">This is all made possible by the underlying foundation Microsoft 365 Groups becoming Multi-Geo aware.</span></span>

<span data-ttu-id="d3ba2-115">複数の Geo のテナントは1つのグローバルテナントであるため、@ メンションを実行しているユーザーは、どこにいても、世界中の同僚を見ることができます。</span><span class="sxs-lookup"><span data-stu-id="d3ba2-115">Because a Multi-Geo tenancy is a single global tenant, during @ mentions satellite users will be able to see their colleagues from across the globe, no matter where they reside.</span></span> 

<span data-ttu-id="d3ba2-116">チームエクスペリエンス内でのチャットおよび会議 IM のメモの会話は、複数の地域に認識されず、すべてがテナントの中央の場所でのみ保持されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d3ba2-116">Note that conversations in chats and meeting IM notes within the Teams experience are not Multi-Geo aware and are all kept only inside the central location of the tenant.</span></span> <span data-ttu-id="d3ba2-117">通常、チャットの会話はデータ常駐のニーズには適用されません。</span><span class="sxs-lookup"><span data-stu-id="d3ba2-117">Typically, chat conversations aren’t applied to data residency needs.</span></span>

<span data-ttu-id="d3ba2-118">複数地域の詳細については、「 [Microsoft の多機能機能」ページ](https://aka.ms/multi-geo)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3ba2-118">For more information about Multi-Geo, refer to the [Microsoft Multi-Geo capabilities page](https://aka.ms/multi-geo).</span></span>