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
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: この付録には、Teams と Skype for Business のクラウド統合の一環としてエッジ証明書を更新するための詳細な手順が含まれています。
ms.openlocfilehash: 724ac63239c881283368fbd617ce0654d49fc0e6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120346"
---
# <a name="update-the-edge-certificate"></a><span data-ttu-id="fbea0-103">エッジ証明書の更新</span><span class="sxs-lookup"><span data-stu-id="fbea0-103">Update the edge certificate</span></span>

<span data-ttu-id="fbea0-104">エッジ証明書の更新は、SipDomain1 を使用したプレム環境が SipDomain2 を使用してクラウド環境に参加し、2 つの SIP ドメイン間で共有アドレス空間環境で適切なルーティングを行う重要なステップです。</span><span class="sxs-lookup"><span data-stu-id="fbea0-104">Updating the edge certificate is the key step to ensuring that an on-prem environment with SipDomain1 can join a cloud environment with SipDomain2 and ensure proper routing in a shared address space environment across the two SIP domains.</span></span> <span data-ttu-id="fbea0-105">この手順を実行できるコンテキストについては [、「Teams](cloud-consolidation.md) と Skype for Business のクラウド統合の手順 14」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fbea0-105">See step 14 in [Cloud consolidation for Teams and Skype for Business](cloud-consolidation.md) for context in which you might perform this step.</span></span> <span data-ttu-id="fbea0-106">この例では、SipDomain1 は AcquiredCompany です。 <span>com と SipDomain2 は OriginalCompany です。 <span>com.</span><span class="sxs-lookup"><span data-stu-id="fbea0-106">In our examples, SipDomain1 is AcquiredCompany.<span>com and SipDomain2 is OriginalCompany.<span>com.</span></span>

<span data-ttu-id="fbea0-107">オンプレミス環境内のすべてのエッジ サーバー上の証明書のサブジェクト代替名 (SAN) を更新して、純粋なオンライン テナントに存在するすべての SIP ドメイン (onmicrosoft <span> を除く) を含める必要があります。com ドメイン) の形式で "sip. \<domain> ".</span><span class="sxs-lookup"><span data-stu-id="fbea0-107">The subject alternate name (SAN) of the certificate on all edge servers in the on-premises environment must be updated to include all SIP domains that exist in the pure online tenant (excluding any onmicrosoft.<span>com domains), in the form “sip.\<domain>”.</span></span>  <span data-ttu-id="fbea0-108">この例では、これは sip です。OriginalCompany。 <span>com.</span><span class="sxs-lookup"><span data-stu-id="fbea0-108">In our example, this is sip.OriginalCompany.<span>com.</span></span> <span data-ttu-id="fbea0-109">この手順は、ユーザーをクラウドに移行する前に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fbea0-109">This step is critical to do before migrating any users to the cloud.</span></span>

<span data-ttu-id="fbea0-110">**手順:**</span><span class="sxs-lookup"><span data-stu-id="fbea0-110">**Steps:**</span></span>

1.  <span data-ttu-id="fbea0-111">"sip" という形式のクラウド環境のすべての SIP ドメイン (\*.onmicrosoft.com ドメインを除く) のすべての既存のエントリと SAN 内の追加エントリを持つエッジの新しい外部エッジ証明書を取得します。 <DomainName></span><span class="sxs-lookup"><span data-stu-id="fbea0-111">Obtain a new External Edge certificate for the edge that has all existing entries plus additional entries in the SAN for all SIP domains in the cloud environment (excluding \*.onmicrosoft.com domains) in the form “sip.<DomainName>”.</span></span>
2.  <span data-ttu-id="fbea0-112">証明書を各エッジ サーバーにローカルにインストールし、各エッジ サービスの Skype Edge サービスに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="fbea0-112">Install the certificate locally on each edge server and assign it to the Skype Edge service on each of the edge service.</span></span>  <span data-ttu-id="fbea0-113">詳細な手順については、「Deploy Edge Service in [Skype for Business Server 2015」](../../SfbServer/deploy/deploy-edge-server/deploy-edge-servers.md)の「外部エッジ インターフェイス証明書」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fbea0-113">For detailed steps, see the section “External Edge interface certificates” in [Deploy Edge Service in Skype for Business Server 2015](../../SfbServer/deploy/deploy-edge-server/deploy-edge-servers.md).</span></span>
3.  <span data-ttu-id="fbea0-114">各エッジ サーバーでエッジ サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="fbea0-114">Restart the Edge service on each of the edge servers.</span></span> <span data-ttu-id="fbea0-115">これは、次の PowerShell コマンドを使用して 1 つのボックスに対して実行できます。</span><span class="sxs-lookup"><span data-stu-id="fbea0-115">You can do this for a single box with the following PowerShell commands:</span></span>

    ```PowerShell
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a><span data-ttu-id="fbea0-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="fbea0-116">See also</span></span>

[<span data-ttu-id="fbea0-117">Teams と Skype for Business のクラウド統合</span><span class="sxs-lookup"><span data-stu-id="fbea0-117">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)