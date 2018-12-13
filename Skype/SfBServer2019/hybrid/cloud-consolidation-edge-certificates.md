---
title: エッジの証明書を更新します。
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
description: この付録には、チームおよびビジネス用の Skype のためのクラウドの統合の一部として、エッジの証明書を更新する詳細な手順が含まれています。
ms.openlocfilehash: bd7707add0962a827373f1d07de9f8f8f9d3ec7c
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247682"
---
# <a name="update-the-edge-certificate"></a><span data-ttu-id="f1919-103">エッジの証明書を更新します。</span><span class="sxs-lookup"><span data-stu-id="f1919-103">Update the edge certificate</span></span>

<span data-ttu-id="f1919-104">SipDomain1 prem の環境が SipDomain2 でのクラウド環境への参加し、2 つの SIP ドメイン間で共有アドレス スペースの環境で適切なルーティングを確保できることを確認するのには重要なステップは、エッジの証明書を更新します。</span><span class="sxs-lookup"><span data-stu-id="f1919-104">Updating the edge certificate is the key step to ensuring that an on-prem environment with SipDomain1 can join a cloud environment with SipDomain2 and ensure proper routing in a shared address space environment across the two SIP domains.</span></span> <span data-ttu-id="f1919-105">この手順を実行する可能性がありますコンテキストの[チームおよびビジネス用の Skype のためのクラウドの統合](cloud-consolidation.md)の手順 14 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1919-105">See step 14 in [Cloud consolidation for Teams and Skype for Business](cloud-consolidation.md) for context in which you might perform this step.</span></span> <span data-ttu-id="f1919-106">例では、SipDomain1 は AcquiredCompany です。<span>OriginalCompany は、com と SipDomain2。<span>com です。</span><span class="sxs-lookup"><span data-stu-id="f1919-106">In our examples, SipDomain1 is AcquiredCompany.<span>com and SipDomain2 is OriginalCompany.<span>com.</span></span>

<span data-ttu-id="f1919-107">純粋なオンライン テナント内に存在するすべての SIP ドメインを含むように、オンプレミス環境でのすべてのエッジ サーバーの証明書のサブジェクト代替名 (SAN) を更新する必要があります (任意の onmicrosoft を除外します<span>。com ドメインの場合)、フォームの"sip。\<ドメイン >"です。</span><span class="sxs-lookup"><span data-stu-id="f1919-107">The subject alternate name (SAN) of the certificate on all edge servers in the on-premises environment must be updated to include all SIP domains that exist in the pure online tenant (excluding any onmicrosoft.<span>com domains), in the form “sip.\<domain>”.</span></span>  <span data-ttu-id="f1919-108">この例では、これは、sip です。OriginalCompany。<span>com です。</span><span class="sxs-lookup"><span data-stu-id="f1919-108">In our example, this is sip.OriginalCompany.<span>com.</span></span> <span data-ttu-id="f1919-109">この手順は、すべてのユーザーをクラウドに移行する前に重要です。</span><span class="sxs-lookup"><span data-stu-id="f1919-109">This step is critical to do before migrating any users to the cloud.</span></span>

<span data-ttu-id="f1919-110">**手順に従います。**</span><span class="sxs-lookup"><span data-stu-id="f1919-110">**Steps:**</span></span>

1.  <span data-ttu-id="f1919-111">クラウド環境内のすべての SIP ドメインの SAN のすべての既存のエントリとその他のエントリには、エッジの新しい外部境界の証明書を取得 (を除く \*. onmicrosoft.com ドメイン) フォームの"sip。<DomainName>」です。</span><span class="sxs-lookup"><span data-stu-id="f1919-111">Obtain a new External Edge certificate for the edge that has all existing entries plus additional entries in the SAN for all SIP domains in the cloud environment (excluding \*.onmicrosoft.com domains) in the form “sip.<DomainName>”.</span></span>
2.  <span data-ttu-id="f1919-112">各エッジ サーバーで証明書をローカルにインストールし、各エッジ サービスの Skype のエッジ サービスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f1919-112">Install the certificate locally on each edge server and assign it to the Skype Edge service on each of the edge service.</span></span>  <span data-ttu-id="f1919-113">詳細な手順は、[ビジネス サーバー 2015 の Skype でのエッジ サービスの展開](https://technet.microsoft.com/en-us/library/dn951368.aspx)で「外部エッジ インターフェイスの証明書」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1919-113">For detailed steps, see the section “External Edge interface certificates” in [Deploy Edge Service in Skype for Business Server 2015](https://technet.microsoft.com/en-us/library/dn951368.aspx).</span></span>
3.  <span data-ttu-id="f1919-114">各エッジ トランスポート サーバーのエッジ サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="f1919-114">Restart the Edge service on each of the edge servers.</span></span> <span data-ttu-id="f1919-115">次の PowerShell コマンドを使用して 1 つのボックスで、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f1919-115">You can do this for a single box with the following PowerShell commands:</span></span>

    ```
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a><span data-ttu-id="f1919-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1919-116">See also</span></span>

[<span data-ttu-id="f1919-117">チームと Skype のビジネス向けのクラウド統合</span><span class="sxs-lookup"><span data-stu-id="f1919-117">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)