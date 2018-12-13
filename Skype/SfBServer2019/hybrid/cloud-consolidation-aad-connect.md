---
title: AAD は、複数のフォレストを含むように接続を更新します。
ms.author: crowe
author: crowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: この付録には、AAD のチームおよびビジネス用の Skype のためのクラウドの統合の一部として複数のフォレストを含むように接続を更新する詳細な手順が含まれています。
ms.openlocfilehash: d7229d54c159f7e07a233636f1576830e667dce5
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247691"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a><span data-ttu-id="d45fa-103">AAD は、複数のフォレストを含むように接続を更新します。</span><span class="sxs-lookup"><span data-stu-id="d45fa-103">Update AAD Connect to include more than one forest</span></span>

<span data-ttu-id="d45fa-104">Azure AD 接続は、[複数のフォレストからの同期](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-topologies)をサポートします。</span><span class="sxs-lookup"><span data-stu-id="d45fa-104">Azure AD Connect supports [syncing from multiple forests](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-topologies).</span></span> <span data-ttu-id="d45fa-105">ただし、AAD と同期される Azure の AD 接続のインスタンスを 1 つだけをサポートします。</span><span class="sxs-lookup"><span data-stu-id="d45fa-105">However, it supports only one instance of Azure AD Connect syncing to AAD.</span></span> <span data-ttu-id="d45fa-106">Azure AD が 1 つのフォレストに既にインストールされている場合、AAD の接続の既存のインスタンスを更新する必要がありますので、他のフォレストからの同期をします。</span><span class="sxs-lookup"><span data-stu-id="d45fa-106">Therefore, in cases where Azure AD is already installed in one forest, the existing instance of AAD Connect must be updated to sync from the additional forest.</span></span>

 - <span data-ttu-id="d45fa-107">すべての id が 2 つのフォレスト全体で 1 回だけで表されている場合 (つまり、メールが有効な連絡先を行っていない、) 単に AAD の接続ウィザードを再実行、「同期オプションのカスタマイズ」を選択して**に、ディレクトリを接続し、** ページで、資格情報、その他のフォレストの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="d45fa-107">If all identities are represented only once across both forests (that is, you haven’t made any mail-enabled contacts), then you can simply re-run the AAD Connect wizard, choose “Customize synchronization options,” and then on the **Connect Your Directories** page, enter the name of the additional forest and creds.</span></span><br><br>
 <span data-ttu-id="d45fa-108">![接続]、[ディレクトリ] ページ](../media/cloud-consolidation-connect-your-directories.png)</span><span class="sxs-lookup"><span data-stu-id="d45fa-108">![The Connect your directories page](../media/cloud-consolidation-connect-your-directories.png)</span></span>
 - <span data-ttu-id="d45fa-109">ただしでユーザーが存在することができますより 1 つのディレクトリとすることをマージすることデータ (たとえば、連絡先オブジェクトは、別のフォレスト内のユーザーに対応するフォレスト内に存在) 場合、Azure AD 接続をアンインストールして再インストールをする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d45fa-109">However, if users can exist in more than one directory and you’ll be merging the data (for example, if contact objects exist in a forest corresponding to users in another forest), you will need to uninstall Azure AD Connect and re-install it.</span></span>  <span data-ttu-id="d45fa-110">最初のインストール中に、フォレスト間の結合規則の条件を構成するためです。</span><span class="sxs-lookup"><span data-stu-id="d45fa-110">This is because the cross-forest join rules condition can only be configured during the first install.</span></span> <span data-ttu-id="d45fa-111">これは次のページで行います。</span><span class="sxs-lookup"><span data-stu-id="d45fa-111">This is done on the following page:</span></span><br><br>
 <span data-ttu-id="d45fa-112">![一意に識別する、ユーザーのページ](../media/cloud-consolidation-uniquely-identifying-your-users.png)</span><span class="sxs-lookup"><span data-stu-id="d45fa-112">![The Uniquely identifying your users page](../media/cloud-consolidation-uniquely-identifying-your-users.png)</span></span>


## <a name="see-also"></a><span data-ttu-id="d45fa-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="d45fa-113">See also</span></span>

[<span data-ttu-id="d45fa-114">チームと Skype のビジネス向けのクラウド統合</span><span class="sxs-lookup"><span data-stu-id="d45fa-114">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)