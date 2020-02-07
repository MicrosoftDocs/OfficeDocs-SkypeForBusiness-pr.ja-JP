---
title: Microsoft Teams の範囲指定ディレクトリ検索を使用する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/21/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Microsoft Teams のスコープ指定ディレクトリ検索を使用して、ディレクトリのカスタマイズされたビューを提供する方法について説明します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: ca20e7293f20d68ea98f61a98090f7892ba294e8
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836947"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a><span data-ttu-id="f061d-103">Microsoft Teams の範囲指定ディレクトリ検索を使用する</span><span class="sxs-lookup"><span data-stu-id="f061d-103">Use Microsoft Teams scoped directory search</span></span>

<span data-ttu-id="f061d-104">Microsoft Teams 範囲指定ディレクトリ検索を使用すると、組織は、ユーザーが組織内の他のユーザーを検索して通信する方法を制御する仮想境界を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="f061d-104">Microsoft Teams scoped directory search allows organizations to create virtual boundaries that control how users can find and communicate with other users in their organization.</span></span> 

<span data-ttu-id="f061d-105">Microsoft Teams を使用すると、組織はディレクトリのカスタムビューをユーザーに提供できます。</span><span class="sxs-lookup"><span data-stu-id="f061d-105">Microsoft Teams lets organizations provide custom views of the directory to their users.</span></span> <span data-ttu-id="f061d-106">Microsoft Teams では、これらのカスタムビューをサポートするために、[情報バリアポリシー](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)を使用しています。</span><span class="sxs-lookup"><span data-stu-id="f061d-106">Microsoft Teams uses [Information Barrier policies](https://docs.microsoft.com/microsoft-365/compliance/information-barriers) to support these custom views.</span></span> <span data-ttu-id="f061d-107">ポリシーを有効にすると、他のユーザーの検索結果 (チャットの開始やチームへのメンバーの追加など) は、構成されたポリシーに従って範囲設定されます。</span><span class="sxs-lookup"><span data-stu-id="f061d-107">Once the policies are enabled, the results returned by searches for other users (for example, to initiate a chat or to add members to a team) will be scoped according to the configured policies.</span></span> <span data-ttu-id="f061d-108">スコープ指定された検索が有効になっている場合、ユーザーはチームを検索または検出できません。</span><span class="sxs-lookup"><span data-stu-id="f061d-108">Users will not be able to search or discover teams when scoped search is in effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="f061d-109">Exchange ハイブリッド環境では、この機能は Exchange Online のメールボックスでのみ機能し、オンプレミスのメールボックスには使用できません。</span><span class="sxs-lookup"><span data-stu-id="f061d-109">In Exchange hybrid environments, this feature only works with Exchange Online mailboxes, and not with on-premises mailboxes.</span></span>

## <a name="when-should-you-use-scoped-directory-searches"></a><span data-ttu-id="f061d-110">スコープディレクトリ検索を使用する場合</span><span class="sxs-lookup"><span data-stu-id="f061d-110">When should you use scoped directory searches?</span></span>

<span data-ttu-id="f061d-111">スコープを指定したディレクトリ検索を利用するシナリオは、アドレス帳ポリシーのシナリオと似ています。</span><span class="sxs-lookup"><span data-stu-id="f061d-111">Scenarios that benefit from scoped directory searches are similar to address book policy scenarios.</span></span> <span data-ttu-id="f061d-112">たとえば、次のような場合には、スコープ指定されたディレクトリ検索を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="f061d-112">For example, you may want to use scoped directory search in the following situations:</span></span>

- <span data-ttu-id="f061d-113">所属する組織において、テナント内に複数の会社があり、それらを切り離された状態で維持する場合。</span><span class="sxs-lookup"><span data-stu-id="f061d-113">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="f061d-114">所属する学校において、教職員と学生との間のチャットを制限する必要がある場合。</span><span class="sxs-lookup"><span data-stu-id="f061d-114">Your school wants to limit chats between faculty and students.</span></span> 
 
<span data-ttu-id="f061d-115">アドレス帳ポリシーの使用方法については、「 [Exchange Online で情報バリアポリシー](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f061d-115">To learn how to use address book policies, read [Information Barrier policies in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/information-barriers).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f061d-116">アドレス帳ポリシーは、ディレクトリの観点からのユーザーの仮想的な分離のみを提供します。</span><span class="sxs-lookup"><span data-stu-id="f061d-116">Address book policies provide only a virtual separation of users from directory perspective.</span></span> <span data-ttu-id="f061d-117">ユーザーは、完全なメールアドレスを提供して、他のユーザーとの通信を開始することができます。</span><span class="sxs-lookup"><span data-stu-id="f061d-117">Users can still initiate communications with others by providing complete email addresses.</span></span> <span data-ttu-id="f061d-118">また、新規または更新されたアドレス帳ポリシーを適用する前に、既にキャッシュされていたすべてのユーザーデータは、最大30日間はユーザーに対して利用可能になることに注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f061d-118">It is also important to note that any user data that had already been cached, prior to the enforcement of new or updated address book policies, will remain available to users for up to 30 days.</span></span>

## <a name="turn-on-scoped-directory-search"></a><span data-ttu-id="f061d-119">スコープディレクトリ検索を有効にする</span><span class="sxs-lookup"><span data-stu-id="f061d-119">Turn on scoped directory search</span></span>

1. <span data-ttu-id="f061d-120">情報バリアポリシーを使用して、組織を仮想サブグループに構成します。</span><span class="sxs-lookup"><span data-stu-id="f061d-120">Use Information Barrier policies to configure your organization into virtual subgroups.</span></span> <span data-ttu-id="f061d-121">詳細については、「[情報バリアポリシーを定義](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-policies)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f061d-121">For more information, see [Define Information Barrier policies](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-policies).</span></span>

2. <span data-ttu-id="f061d-122">Microsoft Teams 管理センターで、[**組織全体の設定** > **チームの設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f061d-122">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams settings**.</span></span>

3. <span data-ttu-id="f061d-123">[**検索**] の [ **Exchange アドレス帳ポリシー (apb) を使用して Teams で検索**する] の横にある [オン **] に切り替えます。**</span><span class="sxs-lookup"><span data-stu-id="f061d-123">Under **Search**, next to **Scope directory search in Teams using an Exchange address book policy (APB)**, turn the toggle **On**.</span></span>

    ![Microsoft Teams 管理センターでのスコープディレクトリ検索](media/teams-scoped-directory-search-image1.png)


> [!IMPORTANT]
> <span data-ttu-id="f061d-125">この変更は、複製に最大24時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="f061d-125">This change can take up to 24 hours to replicate.</span></span>
