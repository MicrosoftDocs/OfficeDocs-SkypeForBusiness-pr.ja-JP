---
title: エッジ証明書の更新
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
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: この付録には、Teams および Skype for Business のクラウド統合の一環としてエッジ証明書を更新するための詳細な手順が含まれています。
ms.openlocfilehash: 52ab646387acb6901798f215f9677f16978e87fb
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "40963055"
---
# <a name="update-the-edge-certificate"></a><span data-ttu-id="d7958-103">エッジ証明書の更新</span><span class="sxs-lookup"><span data-stu-id="d7958-103">Update the edge certificate</span></span>

<span data-ttu-id="d7958-104">エッジ証明書の更新は、SipDomain1 を使用するオンプレミス環境が SipDomain2 を使用してクラウド環境に参加できるようにし、2つの SIP ドメイン間で共有アドレススペース環境で適切にルーティングできるようにするための重要な手順です。</span><span class="sxs-lookup"><span data-stu-id="d7958-104">Updating the edge certificate is the key step to ensuring that an on-prem environment with SipDomain1 can join a cloud environment with SipDomain2 and ensure proper routing in a shared address space environment across the two SIP domains.</span></span> <span data-ttu-id="d7958-105">この手順を実行する必要がある状況については、「 [Teams と Skype For business の](cloud-consolidation.md)手順14」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7958-105">See step 14 in [Cloud consolidation for Teams and Skype for Business](cloud-consolidation.md) for context in which you might perform this step.</span></span> <span data-ttu-id="d7958-106">この例では、SipDomain1 は AcquiredCompany です。<span>Com と SipDomain2 は originalcompany です。<span>com。</span><span class="sxs-lookup"><span data-stu-id="d7958-106">In our examples, SipDomain1 is AcquiredCompany.<span>com and SipDomain2 is OriginalCompany.<span>com.</span></span>

<span data-ttu-id="d7958-107">オンプレミス環境にあるすべてのエッジサーバー上の証明書のサブジェクト代替名 (SAN) を更新して、純粋なオンラインテナントに存在するすべての SIP ドメインを含める必要が<span>あります (任意の onmicrosoft を除く)。com ドメイン)、"sip" という形式です。\<ドメイン> "。</span><span class="sxs-lookup"><span data-stu-id="d7958-107">The subject alternate name (SAN) of the certificate on all edge servers in the on-premises environment must be updated to include all SIP domains that exist in the pure online tenant (excluding any onmicrosoft.<span>com domains), in the form “sip.\<domain>”.</span></span>  <span data-ttu-id="d7958-108">この例では、これは sip です。OriginalCompany。<span>com。</span><span class="sxs-lookup"><span data-stu-id="d7958-108">In our example, this is sip.OriginalCompany.<span>com.</span></span> <span data-ttu-id="d7958-109">この手順は、ユーザーをクラウドに移行する前に実行することが重要です。</span><span class="sxs-lookup"><span data-stu-id="d7958-109">This step is critical to do before migrating any users to the cloud.</span></span>

<span data-ttu-id="d7958-110">**行う**</span><span class="sxs-lookup"><span data-stu-id="d7958-110">**Steps:**</span></span>

1.  <span data-ttu-id="d7958-111">「SIP」という形式で、クラウド環境 (\* onmicrosoft.com ドメインを除く) のすべての SIP ドメインについて、既存のすべてのエントリと SAN の追加エントリに加えて、新しい外部エッジ証明書を取得します。<DomainName>"です。</span><span class="sxs-lookup"><span data-stu-id="d7958-111">Obtain a new External Edge certificate for the edge that has all existing entries plus additional entries in the SAN for all SIP domains in the cloud environment (excluding \*.onmicrosoft.com domains) in the form “sip.<DomainName>”.</span></span>
2.  <span data-ttu-id="d7958-112">各エッジサーバーにローカルに証明書をインストールし、各エッジサービスの Skype エッジサービスに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d7958-112">Install the certificate locally on each edge server and assign it to the Skype Edge service on each of the edge service.</span></span>  <span data-ttu-id="d7958-113">詳細な手順については、「 [Deploy Edge Service In Skype For Business Server 2015](https://technet.microsoft.com/library/dn951368.aspx)」の「外部エッジインターフェイスの証明書」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7958-113">For detailed steps, see the section “External Edge interface certificates” in [Deploy Edge Service in Skype for Business Server 2015](https://technet.microsoft.com/library/dn951368.aspx).</span></span>
3.  <span data-ttu-id="d7958-114">各エッジサーバーでエッジサービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="d7958-114">Restart the Edge service on each of the edge servers.</span></span> <span data-ttu-id="d7958-115">これは、次の PowerShell コマンドを使用して1つのボックスに対して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d7958-115">You can do this for a single box with the following PowerShell commands:</span></span>

    ```PowerShell
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a><span data-ttu-id="d7958-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="d7958-116">See also</span></span>

[<span data-ttu-id="d7958-117">Teams と Skype for Business のクラウド統合</span><span class="sxs-lookup"><span data-stu-id="d7958-117">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)
