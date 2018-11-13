---
title: マイクロソフトのチームを使用してディレクトリ検索のスコープ
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/09/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
localization_priority: Normal
search.appverid: MET150
description: ディレクトリのカスタマイズされたビューを提供するマイクロソフトのチームのスコープ指定されたディレクトリ検索を使用する方法について説明します。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3e9cddc12a5ef4de6dfb42a714b83e29b6fb4f5f
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2018
ms.locfileid: "26293808"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a><span data-ttu-id="7fac4-103">マイクロソフトのチームを使用してディレクトリ検索のスコープ</span><span class="sxs-lookup"><span data-stu-id="7fac4-103">Use Microsoft Teams scoped directory search</span></span>

<span data-ttu-id="7fac4-104">マイクロソフト チームのスコープ指定されたディレクトリ検索では、ユーザーが検索し、組織内の他のユーザーとの通信方法を制御する仮想の境界を作成することが可能します。</span><span class="sxs-lookup"><span data-stu-id="7fac4-104">Microsoft Teams scoped directory search allows organizations to create virtual boundaries that control how users can find and communicate with other users in their organization.</span></span> 

<span data-ttu-id="7fac4-105">マイクロソフトのチームでは、組織のユーザーに、ディレクトリのユーザー設定のビューを提供することができます。</span><span class="sxs-lookup"><span data-stu-id="7fac4-105">Microsoft Teams lets organizations provide custom views of the directory to their users.</span></span> <span data-ttu-id="7fac4-106">マイクロソフトのチームでは、これらのカスタム ビューをサポートするために[Exchange アドレス帳ポリシー](https://docs.microsoft.com/en-us/Exchange/email-addresses-and-address-books/address-book-policies/address-book-policies?view=exchserver-2019)を使用します。</span><span class="sxs-lookup"><span data-stu-id="7fac4-106">Microsoft Teams uses [Exchange address book policies](https://docs.microsoft.com/en-us/Exchange/email-addresses-and-address-books/address-book-policies/address-book-policies?view=exchserver-2019) to support these custom views.</span></span> <span data-ttu-id="7fac4-107">ポリシーを有効にすると、(たとえば、チャットを開始する、またはチームにメンバーを追加するのには) 他のユーザーの検索によって返される結果は構成されているポリシーに従ってスコープします。</span><span class="sxs-lookup"><span data-stu-id="7fac4-107">Once the policies are enabled, the results returned by searches for other users (for example, to initiate a chat or to add members to a team) will be scoped according to the configured policies.</span></span> <span data-ttu-id="7fac4-108">ユーザーは検索し、検出またはこれらのポリシー以外で新しいチームに参加することができません。</span><span class="sxs-lookup"><span data-stu-id="7fac4-108">Users will not be able to search or discover and join new teams outside of these policies.</span></span> 

## <a name="when-should-you-use-scoped-directory-searches"></a><span data-ttu-id="7fac4-109">スコープ指定されたディレクトリ検索を使用する場合</span><span class="sxs-lookup"><span data-stu-id="7fac4-109">When should you use scoped directory searches?</span></span>

<span data-ttu-id="7fac4-110">スコープ指定されたディレクトリ検索からメリットを得られるシナリオでは、アドレス帳ポリシーのシナリオに似ています。</span><span class="sxs-lookup"><span data-stu-id="7fac4-110">Scenarios that benefit from scoped directory searches are similar to address book policy scenarios.</span></span> <span data-ttu-id="7fac4-111">たとえば、スコープ指定されたディレクトリ検索を使用して、次のような状況でする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7fac4-111">For example, you may want to use scoped directory search in the following situations:</span></span>

- <span data-ttu-id="7fac4-112">組織には、別に保持する、テナント内の複数の企業がいます。</span><span class="sxs-lookup"><span data-stu-id="7fac4-112">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="7fac4-113">学校は、教職員と学生の間でチャットを制限する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fac4-113">Your school wants to limit chats between faculty and students.</span></span> 
 
<span data-ttu-id="7fac4-114">アドレス帳ポリシーの使用方法の詳細については、[ここで](https://docs.microsoft.com/en-us/Exchange/email-addresses-and-address-books/address-book-policies/abp-scenarios?view=exchserver-2019)。</span><span class="sxs-lookup"><span data-stu-id="7fac4-114">You can learn more about how address book policies can be used [here](https://docs.microsoft.com/en-us/Exchange/email-addresses-and-address-books/address-book-policies/abp-scenarios?view=exchserver-2019).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7fac4-115">アドレス帳のポリシーでは、のみ、仮想の分離のユーザー ディレクトリの観点からを提供します。</span><span class="sxs-lookup"><span data-stu-id="7fac4-115">Address book policies provide only a virtual separation of users from directory perspective.</span></span> <span data-ttu-id="7fac4-116">ユーザーは、完全な電子メール アドレスを提供することで他のユーザーとの通信を開始することができますも。</span><span class="sxs-lookup"><span data-stu-id="7fac4-116">Users can still initiate communications with others by providing complete email addresses.</span></span> 

## <a name="enable-scoped-directory-search"></a><span data-ttu-id="7fac4-117">スコープ指定されたディレクトリの検索を有効にします。</span><span class="sxs-lookup"><span data-stu-id="7fac4-117">Enable scoped directory search</span></span>

1.  <span data-ttu-id="7fac4-118">仮想サブグループに組織を構成するのにには、アドレス帳ポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="7fac4-118">Use address book policies to configure your organization into virtual subgroups.</span></span> <span data-ttu-id="7fac4-119">詳細については、[アドレス帳ポリシーの手順](https://docs.microsoft.com/en-us/Exchange/email-addresses-and-address-books/address-book-policies/abp-procedures?view=exchserver-2019)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7fac4-119">For more information, see [Procedures for address book policies](https://docs.microsoft.com/en-us/Exchange/email-addresses-and-address-books/address-book-policies/abp-procedures?view=exchserver-2019).</span></span>

2.  <span data-ttu-id="7fac4-120">Microsoft 365 の管理センターにサインインするのに、**管理センター**をを選択し、**チームと Skype**。</span><span class="sxs-lookup"><span data-stu-id="7fac4-120">Sign in to the Microsoft 365 admin center, select **Admin centers**, and then select **Teams & Skype**.</span></span>
 
3.  <span data-ttu-id="7fac4-121">マイクロソフトのチームと Skype ビジネス管理センターは、**組織全体の設定**を選択します > **チームの設定**です。</span><span class="sxs-lookup"><span data-stu-id="7fac4-121">In the Microsoft Teams & Skype for Business admin center, select **Org-wide settings** > **Teams settings**.</span></span>

4.  <span data-ttu-id="7fac4-122">**検索**、**チームが Exchange アドレス帳ポリシー (APB) を使用してディレクトリ検索のスコープ**をで **[** 表示/非表示をオンにします。</span><span class="sxs-lookup"><span data-stu-id="7fac4-122">Under **Search**, next to **Scope directory search in Teams using an Exchange address book policy (APB)**, turn the toggle **On**.</span></span> 

    ![ビジネス管理センターについては、チームと Skype のディレクトリ検索のスコープ](media/teams-scoped-directory-search-image1.png)

> [!NOTE]
> <span data-ttu-id="7fac4-124">ハイブリッド構成 (Exchange、オンプレミスのチーム) は、対象とした検索モードをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="7fac4-124">Hybrid configurations (Teams with Exchange on-premises) do not support scoped search mode.</span></span> 

