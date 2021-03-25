---
title: AAD Connect を更新して複数のフォレストを含める
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: この付録には、Teams と Skype for Business のクラウド統合の一環として複数のフォレストを含める AAD Connect を更新するための詳細な手順が含まれています。
ms.openlocfilehash: 19b761f3b64caf7afad7d37a51ae391e23d6b5ef
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120376"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a><span data-ttu-id="a59df-103">AAD Connect を更新して複数のフォレストを含める</span><span class="sxs-lookup"><span data-stu-id="a59df-103">Update AAD Connect to include more than one forest</span></span>

<span data-ttu-id="a59df-104">Azure AD Connect は、複数 [のフォレストからの同期をサポートしています](/azure/active-directory/connect/active-directory-aadconnect-topologies)。</span><span class="sxs-lookup"><span data-stu-id="a59df-104">Azure AD Connect supports [syncing from multiple forests](/azure/active-directory/connect/active-directory-aadconnect-topologies).</span></span> <span data-ttu-id="a59df-105">ただし、Azure のインスタンスは 1 つのみサポートAD接続して AAD に同期します。</span><span class="sxs-lookup"><span data-stu-id="a59df-105">However, it supports only one instance of Azure AD Connect syncing to AAD.</span></span> <span data-ttu-id="a59df-106">したがって、Azure ADが 1 つのフォレストに既にインストールされている場合は、AAD Connect の既存のインスタンスを更新して、追加のフォレストから同期する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a59df-106">Therefore, in cases where Azure AD is already installed in one forest, the existing instance of AAD Connect must be updated to sync from the additional forest.</span></span>

 - <span data-ttu-id="a59df-107">すべての ID が両方のフォレストで 1 回だけ表される場合 (つまり、メールが有効な連絡先を作成していない場合)、AAD Connect ウィザードを再び実行し、[同期オプションのカスタマイズ]を選択してから、[ディレクトリの接続] ページで追加のフォレストと creds の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="a59df-107">If all identities are represented only once across both forests (that is, you haven’t made any mail-enabled contacts), then you can simply re-run the AAD Connect wizard, choose “Customize synchronization options,” and then on the **Connect Your Directories** page, enter the name of the additional forest and creds.</span></span><br><br>
 <span data-ttu-id="a59df-108">![[ディレクトリの接続] ページ](../media/cloud-consolidation-connect-your-directories.png)</span><span class="sxs-lookup"><span data-stu-id="a59df-108">![The Connect your directories page](../media/cloud-consolidation-connect-your-directories.png)</span></span>
 - <span data-ttu-id="a59df-109">ただし、ユーザーが複数のディレクトリに存在し、データをマージする場合 (たとえば、別のフォレスト内のユーザーに対応するフォレストに連絡先オブジェクトが存在する場合)、Azure AD Connect をアンインストールして再インストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a59df-109">However, if users can exist in more than one directory and you’ll be merging the data (for example, if contact objects exist in a forest corresponding to users in another forest), you will need to uninstall Azure AD Connect and re-install it.</span></span>  <span data-ttu-id="a59df-110">これは、フォレスト間参加ルールの条件が最初のインストール時にのみ構成できるためです。</span><span class="sxs-lookup"><span data-stu-id="a59df-110">This is because the cross-forest join rules condition can only be configured during the first install.</span></span> <span data-ttu-id="a59df-111">これは、次のページで行います。</span><span class="sxs-lookup"><span data-stu-id="a59df-111">This is done on the following page:</span></span><br><br>
 <span data-ttu-id="a59df-112">![[ユーザーを一意に識別する] ページ](../media/cloud-consolidation-uniquely-identifying-your-users.png)</span><span class="sxs-lookup"><span data-stu-id="a59df-112">![The Uniquely identifying your users page](../media/cloud-consolidation-uniquely-identifying-your-users.png)</span></span>


## <a name="see-also"></a><span data-ttu-id="a59df-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="a59df-113">See also</span></span>

[<span data-ttu-id="a59df-114">Teams と Skype for Business のクラウド統合</span><span class="sxs-lookup"><span data-stu-id="a59df-114">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)