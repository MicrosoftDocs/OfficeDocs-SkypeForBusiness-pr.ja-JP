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
description: この付録には、Teams 接続を更新して、Teams と Skype for Business のクラウド統合の一部として複数のフォレストを含めるための詳細な手順が含まれています。
ms.openlocfilehash: a61a45c8a492afd761f8cc6b1020b591851645b8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049099"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a><span data-ttu-id="ef397-103">AAD Connect を更新して複数のフォレストを含める</span><span class="sxs-lookup"><span data-stu-id="ef397-103">Update AAD Connect to include more than one forest</span></span>

<span data-ttu-id="ef397-104">Azure AD Connect は、[複数のフォレストからの同期を](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-topologies)サポートしています。</span><span class="sxs-lookup"><span data-stu-id="ef397-104">Azure AD Connect supports [syncing from multiple forests](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-topologies).</span></span> <span data-ttu-id="ef397-105">ただし、AAD に対して Azure AD Connect 同期のインスタンスを1つだけサポートしています。</span><span class="sxs-lookup"><span data-stu-id="ef397-105">However, it supports only one instance of Azure AD Connect syncing to AAD.</span></span> <span data-ttu-id="ef397-106">そのため、Azure AD が1つのフォレストに既にインストールされている場合は、AAD Connect の既存のインスタンスを追加のフォレストから同期するように更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef397-106">Therefore, in cases where Azure AD is already installed in one forest, the existing instance of AAD Connect must be updated to sync from the additional forest.</span></span>

 - <span data-ttu-id="ef397-107">両方のフォレストですべての id が1回のみ表示されている場合 (つまり、メールが有効な連絡先がない場合)、AAD Connect ウィザードを再実行し、[同期オプションのカスタマイズ] を選択してから、[**ディレクトリの接続**] ページで追加のフォレストおよび資格情報の名前を入力するだけです。</span><span class="sxs-lookup"><span data-stu-id="ef397-107">If all identities are represented only once across both forests (that is, you haven’t made any mail-enabled contacts), then you can simply re-run the AAD Connect wizard, choose “Customize synchronization options,” and then on the **Connect Your Directories** page, enter the name of the additional forest and creds.</span></span><br><br>
 <span data-ttu-id="ef397-108">![[ディレクトリの接続] ページ](../media/cloud-consolidation-connect-your-directories.png)</span><span class="sxs-lookup"><span data-stu-id="ef397-108">![The Connect your directories page](../media/cloud-consolidation-connect-your-directories.png)</span></span>
 - <span data-ttu-id="ef397-109">ただし、ユーザーが複数のディレクトリに存在し、データを結合する場合 (たとえば、別のフォレストのユーザーに対応する連絡先オブジェクトがフォレスト内に存在する場合)、Azure AD Connect をアンインストールしてから再インストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef397-109">However, if users can exist in more than one directory and you’ll be merging the data (for example, if contact objects exist in a forest corresponding to users in another forest), you will need to uninstall Azure AD Connect and re-install it.</span></span>  <span data-ttu-id="ef397-110">これは、フォレスト間の参加ルールの条件は、最初のインストール時にのみ構成できるからです。</span><span class="sxs-lookup"><span data-stu-id="ef397-110">This is because the cross-forest join rules condition can only be configured during the first install.</span></span> <span data-ttu-id="ef397-111">これは、次のページで行われます。</span><span class="sxs-lookup"><span data-stu-id="ef397-111">This is done on the following page:</span></span><br><br>
 <span data-ttu-id="ef397-112">![ユーザーを一意に識別するページ](../media/cloud-consolidation-uniquely-identifying-your-users.png)</span><span class="sxs-lookup"><span data-stu-id="ef397-112">![The Uniquely identifying your users page](../media/cloud-consolidation-uniquely-identifying-your-users.png)</span></span>


## <a name="see-also"></a><span data-ttu-id="ef397-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="ef397-113">See also</span></span>

[<span data-ttu-id="ef397-114">Teams と Skype for Business のクラウド統合</span><span class="sxs-lookup"><span data-stu-id="ef397-114">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)