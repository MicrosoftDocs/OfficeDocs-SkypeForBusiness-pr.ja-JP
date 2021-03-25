---
title: Microsoft Teams のセキュリティ ガイド
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.date: 08/21/2020
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: pawa
description: 職場の共有コンピューターから Microsoft Teams を安全に使用するためのガイダンス。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 45497c824cfc20644a59e35f7812b17058f61c2c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117055"
---
# <a name="use-microsoft-teams-securely-on-shared-computers"></a><span data-ttu-id="d0e7f-103">共有コンピューターで Microsoft Teams を安全に使用する</span><span class="sxs-lookup"><span data-stu-id="d0e7f-103">Use Microsoft Teams securely on shared computers</span></span>

<span data-ttu-id="d0e7f-104">可能な場合は、クライアントデバイスに対して、デバイス管理機能、デバイスのヘルスチェックとポリシーの実施、デバイスレベルの暗号化、およびその他のセキュリティ機能を利用したゼロトラストアプローチを利用することを *お勧め* します。</span><span class="sxs-lookup"><span data-stu-id="d0e7f-104">When possible, it is *recommended* Enterprises make use of a Zero Trust approach to client devices making use of device management capabilities, device health checks and policy enforcement, device-level encryption, and other security features.</span></span>

:::image type="content" source="media/tp_ZeroTrustPrinciples.PNG" alt-text="ゼロトラストの写真は、青い円によって、明示的に確認し、最小限の特権しか与えず、違反を常に想定するというゼロトラストの中心原則を示しています。":::

<span data-ttu-id="d0e7f-106">管理者は、検証と最小限の特権を *主張* し、妥協案を想定することで、ユーザーとデータの両方に対するリスクを最小限に抑えるアクションにつながる標準を使用して、非常に安全な条件を作成できます。</span><span class="sxs-lookup"><span data-stu-id="d0e7f-106">Administrators can create very secure conditions by *insisting* on verification, least privilege, and by assuming compromise -- standards that lead to actions that minimize risk to both users and data.</span></span>

> [!TIP]
> <span data-ttu-id="d0e7f-107">ゼロトラストの原則の詳細については、[こちらのビデオ](/security/ciso-workshop/ciso-workshop-module-3#part-2-zero-trust-definition-and-models-1537)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0e7f-107">For a deeper examination of Zero Trust principles, see [these videos](/security/ciso-workshop/ciso-workshop-module-3#part-2-zero-trust-definition-and-models-1537).</span></span>

## <a name="tips-for-using-microsoft-teams-securely-from-a-shared-computer"></a><span data-ttu-id="d0e7f-108">共有コンピューターから Microsoft Teams を安全に使用するためのヒント</span><span class="sxs-lookup"><span data-stu-id="d0e7f-108">Tips for using Microsoft Teams securely from a shared computer</span></span>

<span data-ttu-id="d0e7f-109">すべての状況で可能ではない、または実用的とは限りませんが、それでも、セキュリティ管理者が共有コンピューターまたは管理対象外のデバイスから Teams を使用するためのガイダンスに可能な限り従うことは重要です。</span><span class="sxs-lookup"><span data-stu-id="d0e7f-109">Recognizing that this may not be possible or practical in all scenarios, it is still important for security administrators to follow guidance for using Teams from a shared computer or unmanaged device as best they can.</span></span>

<span data-ttu-id="d0e7f-110">可能な限り迅速にガイドラインに準拠するように計画を策定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0e7f-110">Plans should be developed to adhere to guidelines as promptly as is possible.</span></span>

1. <span data-ttu-id="d0e7f-111">オペレーティングシステムプラットフォームのセキュリティ機能を利用します。</span><span class="sxs-lookup"><span data-stu-id="d0e7f-111">Make use of Operating System platform security capabilities.</span></span>
    1. <span data-ttu-id="d0e7f-112">オペレーティングシステムがオペレーティングシステムプロバイダーからの自動更新をインストールするように構成されていることを確認します（Microsoft システムの場合、これは [**Windows Update**](https://support.microsoft.com/help/12373/windows-update-faq) から実行できます）。</span><span class="sxs-lookup"><span data-stu-id="d0e7f-112">Ensure that the operating system is configured to install automatic updates from the Operating System provider (for Microsoft systems, this can be accomplished via [**Windows Update**](https://support.microsoft.com/help/12373/windows-update-faq)).</span></span> 
    1. <span data-ttu-id="d0e7f-113">[**BitLocker**](/windows/security/information-protection/bitlocker/bitlocker-overview) などのデバイスの暗号化機能が有効になっており、デバイスへのアクセスに使用するキーが保護されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d0e7f-113">Ensure that any device encryption capabilities such as [**bitlocker**](/windows/security/information-protection/bitlocker/bitlocker-overview) are enabled, and the key used to access the device is secured.</span></span>  <span data-ttu-id="d0e7f-114">最近のほとんどの [**Windows 10 デバイスはbitlockerをサポートしています**](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10)。</span><span class="sxs-lookup"><span data-stu-id="d0e7f-114">Note that most modern [**Windows 10 devices support bitlocker**](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10).</span></span> 
    1. <span data-ttu-id="d0e7f-115">デバイスで、[**Windows Defender**](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) が提供するようなウイルス対策機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="d0e7f-115">Use anti-virus capabilities such as those offered by [**Windows Defender**](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) on your devices.</span></span>
    1. <span data-ttu-id="d0e7f-116">システムのユーザーごとに[個別のユーザーアカウント](https://support.microsoft.com/help/4026923/windows-10-create-a-local-user-or-administrator-account)を使用することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d0e7f-116">Use of [separate user accounts](https://support.microsoft.com/help/4026923/windows-10-create-a-local-user-or-administrator-account) for each user of the system is highly recommended.</span></span>
    1. <span data-ttu-id="d0e7f-117">管理権限を必要としない機能（Web の閲覧、Teams の実行など）に対して管理者権限を付与または使用 *しない* でください。</span><span class="sxs-lookup"><span data-stu-id="d0e7f-117">*Do not* grant, or use, administrator privileges for non-administrative functions (such as browsing the web, running Teams, et cetera).</span></span>

<span data-ttu-id="d0e7f-118">上記のガイダンスが満たされていない場合は、追加のブラウザーセキュリティのベストプラクティスを利用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d0e7f-118">If the above guidance cannot be met, we recommend making use of additional browser security best practices:</span></span>

1. <span data-ttu-id="d0e7f-119">ブラウザのセキュリティ機能を活用します。</span><span class="sxs-lookup"><span data-stu-id="d0e7f-119">Leverage browser security capabilities.</span></span>
    1. <span data-ttu-id="d0e7f-120">プライベートブラウズセッションを使用して、ディスクに残るデータや履歴を最小限に抑えます。</span><span class="sxs-lookup"><span data-stu-id="d0e7f-120">Use private browsing sessions to minimize data and history that persists to disk.</span></span> <span data-ttu-id="d0e7f-121">たとえば、[Microsoft Edge での inPrivate ブラウズ](https://support.microsoft.com/help/4533513/microsoft-edge-browse-inprivate)、[Google Chrome でのシークレットブラウズ](https://support.google.com/chrome/answer/95464?co=GENIE.Platform%3DDesktop&hl=en)、または特定のブラウザでのプライベートブラウズ機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="d0e7f-121">For example, use [inPrivate browsing in Microsoft Edge](https://support.microsoft.com/help/4533513/microsoft-edge-browse-inprivate), [Incognito browsing in Google Chrome](https://support.google.com/chrome/answer/95464?co=GENIE.Platform%3DDesktop&hl=en), or the capabilities your specific browser for browsing privately.</span></span> 
    1. <span data-ttu-id="d0e7f-122">*既定で* プライベートブラウズを行うようにシステムの動作を変更しておくことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d0e7f-122">Changing the system behavior to engage private browsing *by default* is recommended.</span></span> 

2. <span data-ttu-id="d0e7f-123">ダウンロード可能な Teams クライアントではなく、[Teams Web アプリ](https://teams.microsoft.com)（*Web* クライアントとも呼ばれます）を閲覧して使用します。</span><span class="sxs-lookup"><span data-stu-id="d0e7f-123">Browse to and use the [Teams web app](https://teams.microsoft.com) (sometimes called the *web* client) not the downloadable Teams client.</span></span>

3. <span data-ttu-id="d0e7f-124">共有システムの使用が終了したら、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0e7f-124">When you are done using the shared system, you must:</span></span> 
    1. <span data-ttu-id="d0e7f-125">[Teams からサインアウトする](https://support.microsoft.com/office/sign-out-of-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487)。</span><span class="sxs-lookup"><span data-stu-id="d0e7f-125">[Sign out of Teams](https://support.microsoft.com/office/sign-out-of-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487).</span></span>
    1. <span data-ttu-id="d0e7f-126">ブラウザーのすべてのタブおよびウィンドウを閉じる。</span><span class="sxs-lookup"><span data-stu-id="d0e7f-126">Close all browser tabs and windows.</span></span>
    1. <span data-ttu-id="d0e7f-127">デバイスからサインアウトする。</span><span class="sxs-lookup"><span data-stu-id="d0e7f-127">Sign out of the device.</span></span>

<span data-ttu-id="d0e7f-128">上記の項目は、すべてのケースを網羅するベストプラクティスまたはセキュリティ管理の包括的なリストではなく、環境内で実行できる追加のアクションがある場合があります（たとえば、[Office 365 ATP プラン 1 または 2](/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide#office-365-atp-plan-1-and-plan-2) を使用している場合、セキュリティ管理者は Teams のセーフリンクとセーフアタッチメントの使用を選択できます）。</span><span class="sxs-lookup"><span data-stu-id="d0e7f-128">The items above are not a comprehensive list of best practices or security controls covering all cases, and there may be extra actions that can be taken in your environment, (for instance, security administrators may choose to use Safe Links and Safe Attachments for Teams if you have [Office 365 ATP Plan 1 or 2](/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide#office-365-atp-plan-1-and-plan-2)).</span></span> <span data-ttu-id="d0e7f-129">ただし、これらの手順は、共有デバイスから Teams を使用するためのガイダンスを構築するための開始点です。</span><span class="sxs-lookup"><span data-stu-id="d0e7f-129">However, these steps are a starting point for building guidance for using Teams from shared devices.</span></span>

## <a name="more-information"></a><span data-ttu-id="d0e7f-130">詳細</span><span class="sxs-lookup"><span data-stu-id="d0e7f-130">More Information</span></span>

[<span data-ttu-id="d0e7f-131">構成マネージャーの Bitlocker</span><span class="sxs-lookup"><span data-stu-id="d0e7f-131">Bitlocker in Configuration Manager</span></span>](/mem/configmgr/protect/deploy-use/bitlocker/deploy-management-agent)

[<span data-ttu-id="d0e7f-132">Intune の Windows 10 用 Bitlocker</span><span class="sxs-lookup"><span data-stu-id="d0e7f-132">Bitlocker for Windows 10 in Intune</span></span>](/mem/intune/protect/encrypt-devices)

[<span data-ttu-id="d0e7f-133">Intune のエンドポイントセキュリティ</span><span class="sxs-lookup"><span data-stu-id="d0e7f-133">Endpoint security in Intune</span></span>](/mem/intune/protect/endpoint-security)

<span data-ttu-id="d0e7f-134">Windows セキュリティで Microsoft Defender Antivirus を[有効](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app)にして[スキャンを実行する](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#run-a-scan-with-the-windows-security-app)</span><span class="sxs-lookup"><span data-stu-id="d0e7f-134">[Enable](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app) Microsoft Defender Antivirus in your Windows Security and [run scans](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#run-a-scan-with-the-windows-security-app)</span></span>

[<span data-ttu-id="d0e7f-135">Microsoft Defender セキュリティセンターの記事</span><span class="sxs-lookup"><span data-stu-id="d0e7f-135">Microsoft Defender security center article</span></span>](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus)

[<span data-ttu-id="d0e7f-136">Tems Web クライアント/ Teams Web アプリ</span><span class="sxs-lookup"><span data-stu-id="d0e7f-136">Teams web client/teams web app</span></span>](./get-clients.md#web-client)

[<span data-ttu-id="d0e7f-137">セキュリティと Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d0e7f-137">Security and Microsoft Teams</span></span>](./teams-security-guide.md)