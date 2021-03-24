---
title: Skype for Business Server 2015 の管理者レポートを確認する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 22d480ea-cd64-4d09-99fe-96e997570844
description: 管理者レポートは、展開と運用に関する詳細情報です。 レポートは、デザイン サイトでマークされた選択内容に基づいて生成されます。 設計者は、ネットワーク ダイアグラムを編集し、サーバー、プール、およびロード バランサーの完全な IP アドレスと完全修飾ドメイン名 (FQDN) を定義することで、管理者レポートに値を追加できます。
ms.openlocfilehash: dbef33351e7032e769e1d5ee68c5f0d582317eb6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104323"
---
# <a name="review-the-administrator-reports-in-skype-for-business-server-2015"></a><span data-ttu-id="18e69-105">Skype for Business Server 2015 の管理者レポートを確認する</span><span class="sxs-lookup"><span data-stu-id="18e69-105">Review the Administrator Reports in Skype for Business Server 2015</span></span>

<span data-ttu-id="18e69-106">管理者レポートは、展開と運用に関する詳細情報です。</span><span class="sxs-lookup"><span data-stu-id="18e69-106">The Administrator Reports are detailed information for deployment and operations.</span></span> <span data-ttu-id="18e69-107">レポートは、デザイン サイトでマークされている選択内容に基 **づいて生成されます**。</span><span class="sxs-lookup"><span data-stu-id="18e69-107">The reports are generated based on the selections marked in **Design Sites**.</span></span> <span data-ttu-id="18e69-108">設計者は、ネットワーク ダイアグラムを編集し、サーバー、プール、およびロード バランサーの完全な IP アドレスと完全修飾ドメイン名 (FQDN) を定義することで、管理者レポートに値を追加できます。</span><span class="sxs-lookup"><span data-stu-id="18e69-108">The designer can further add value to the Administrator Reports by editing the network diagrams and defining the complete IP addresses and fully qualified domain names (FQDNs) for servers, pools, and load balancers.</span></span>

<span data-ttu-id="18e69-109">管理者レポート機能を使用すると、次の機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="18e69-109">The Administrator reports feature allows you to:</span></span>

- [<span data-ttu-id="18e69-110">概要レポートを確認する</span><span class="sxs-lookup"><span data-stu-id="18e69-110">Review the Summary Report</span></span>](review-the-administrator-reports.md#Summary_report)

- [<span data-ttu-id="18e69-111">証明書レポートを確認する</span><span class="sxs-lookup"><span data-stu-id="18e69-111">Review the Certificates Report</span></span>](review-the-administrator-reports.md#Certificates_Report)

- [<span data-ttu-id="18e69-112">ファイアウォール レポートの確認</span><span class="sxs-lookup"><span data-stu-id="18e69-112">Review the Firewall Report</span></span>](review-the-administrator-reports.md#Firewall_report)

- [<span data-ttu-id="18e69-113">DNS レポートを確認する</span><span class="sxs-lookup"><span data-stu-id="18e69-113">Review the DNS Report</span></span>](review-the-administrator-reports.md#DNS_Report)

## <a name="review-the-summary-report"></a><span data-ttu-id="18e69-114">概要レポートを確認する</span><span class="sxs-lookup"><span data-stu-id="18e69-114">Review the Summary Report</span></span>
<span data-ttu-id="18e69-115"><a name="Summary_report"> </a></span><span class="sxs-lookup"><span data-stu-id="18e69-115"><a name="Summary_report"> </a></span></span>

<span data-ttu-id="18e69-116">Skype for Business Administrator Report は、デザインを詳細に文書化する 4 つの貴重なレポートの最初のレポートです。</span><span class="sxs-lookup"><span data-stu-id="18e69-116">The Skype for Business Administrator Report is the first of four valuable reports that document your design in detail.</span></span> <span data-ttu-id="18e69-117">このレポートの情報と、関連付けられている他の 3 つのレポートは、情報テクノロジ チームに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="18e69-117">The information in this report, and the other three associated reports, is useful for your Information Technology Teams:</span></span>

![概要管理レポート](../../media/General_Summary_Report_Admin_Report.png)

<span data-ttu-id="18e69-119">概要レポートは、エッジ ネットワークに関連付けられた一般的な構成情報を示します。</span><span class="sxs-lookup"><span data-stu-id="18e69-119">The Summary Report lists general configuration information associated with your Edge network.</span></span> <span data-ttu-id="18e69-120">場所、完全修飾ドメイン名 (FQDN) と IP アドレス、ネットワークの種類、および特定の役割に固有のコメントが文書化されています。</span><span class="sxs-lookup"><span data-stu-id="18e69-120">The location, fully qualified domain name (FQDN) and IP address, type of network, and comments specific to a given role are documented.</span></span>

<span data-ttu-id="18e69-121">設計者とインフラストラクチャを展開、管理、および保守する各チームは、概要レポートの正確性を確認し、エラーが最小限に抑え込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="18e69-121">The designer and each of the teams that will deploy, manage, and maintain the infrastructure should review the summary report for accuracy and to make sure that errors are at a minimum.</span></span>

<span data-ttu-id="18e69-122">さらに詳細なレポートを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="18e69-122">You can also view more detailed reports:</span></span>

- <span data-ttu-id="18e69-123">証明書レポート</span><span class="sxs-lookup"><span data-stu-id="18e69-123">Certificates Report</span></span>

- <span data-ttu-id="18e69-124">ファイアウォール レポート</span><span class="sxs-lookup"><span data-stu-id="18e69-124">Firewall Report</span></span>

- <span data-ttu-id="18e69-125">DNS レポート</span><span class="sxs-lookup"><span data-stu-id="18e69-125">DNS Report</span></span>

## <a name="review-the-certificates-report"></a><span data-ttu-id="18e69-126">証明書レポートを確認する</span><span class="sxs-lookup"><span data-stu-id="18e69-126">Review the Certificates Report</span></span>
<span data-ttu-id="18e69-127"><a name="Certificates_Report"> </a></span><span class="sxs-lookup"><span data-stu-id="18e69-127"><a name="Certificates_Report"> </a></span></span>

<span data-ttu-id="18e69-128">証明書レポートには、推奨される Skype for Business Server 2015 展開で必要なすべての証明書が含まれている。</span><span class="sxs-lookup"><span data-stu-id="18e69-128">The Certificates Report contains all certificates that are required in the recommended Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="18e69-129">計画ツールには、入力されたサブジェクト名とサブジェクトの代替名が含されます。</span><span class="sxs-lookup"><span data-stu-id="18e69-129">The Planning Tool accounts for the subject names and subject alternative names that are entered.</span></span> <span data-ttu-id="18e69-130">編集されていない既定のテキストは、証明書の要求と発行を担当するチームにとって潜在的な課題を表している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="18e69-130">Default text that is left unedited may represent a potential challenge for the team responsible for requesting and issuing the certificates.</span></span> <span data-ttu-id="18e69-131">証明書情報には、証明書が主としてどこから発行されるかについての情報も含まれています。</span><span class="sxs-lookup"><span data-stu-id="18e69-131">Certificate information also contains information about where the certificate can typically be issued from.</span></span> <span data-ttu-id="18e69-132">インフラストラクチャが内部公開キー基盤 (PKI) を持たない場合、すべての証明書はパブリック証明書プロバイダーを介して要求することができます。</span><span class="sxs-lookup"><span data-stu-id="18e69-132">If the infrastructure does not have an internal public key infrastructure (PKI) in place, all certificates can be requested through a public certificate provider.</span></span> <span data-ttu-id="18e69-133">拡張キー使用法 (EKU) およびレポートの [割り当て] フィールドは、それぞれの証明書の目的および場所を知るのに非常に有用です。</span><span class="sxs-lookup"><span data-stu-id="18e69-133">Extended key usages (EKU) and Assign To fields in the report are very helpful in understanding what the purpose and location for each certificate should be.</span></span>

![証明書の管理レポート](../../media/Certificates_Report_Admin_Report.png)

<span data-ttu-id="18e69-135">展開内の各証明書の使用と目的を注意深く確認し、理解してください。</span><span class="sxs-lookup"><span data-stu-id="18e69-135">Carefully review, and be sure to understand, the use and purpose of each certificate in the deployment.</span></span> <span data-ttu-id="18e69-136">証明書の動作に関する質問がある場合は、どのサーバーまたはサービスが何と話しているのかを判断します。</span><span class="sxs-lookup"><span data-stu-id="18e69-136">If there is a question about what a certificate does, determine which server or service is talking to what.</span></span> <span data-ttu-id="18e69-137">Skype for Business Server 2015 の証明書は、次の 2 つの主な目的で使用されます。</span><span class="sxs-lookup"><span data-stu-id="18e69-137">Certificates in Skype for Business Server 2015 are used for two primary purposes:</span></span>

- <span data-ttu-id="18e69-138">相互トランスポート層セキュリティ (MTLS) - 通信に関係するコンピューターは、それぞれ別のコンピューターに自分の ID を証明する証明書を提示します。</span><span class="sxs-lookup"><span data-stu-id="18e69-138">Mutual Transport Layer Security (MTLS) - The computers involved in the communication each present a certificate that proves their identity to another computer.</span></span> <span data-ttu-id="18e69-139">これはサーバー認証と呼ばれる。</span><span class="sxs-lookup"><span data-stu-id="18e69-139">This is known as server authentication.</span></span> <span data-ttu-id="18e69-140">各コンピューターが他のコンピューターの ID を信頼するまで、通信を開始できません。</span><span class="sxs-lookup"><span data-stu-id="18e69-140">Communication cannot begin until each computer trusts the other computer's identity.</span></span>

- <span data-ttu-id="18e69-141">暗号化 - 暗号化 (Secure Sockets Layer、SSL、トランスポート層セキュリティ、または TLS) は、通信のセキュリティ保護、プライバシーの確保、信頼できる通信およびコラボレーション システムの作成に役立つ重要な手段です。</span><span class="sxs-lookup"><span data-stu-id="18e69-141">Encryption - Encryption (Secure Sockets Layer, or SSL, and Transport Layer Security, or TLS) is a critical means to help secure communications, help ensure privacy, and to create a trusted communications and collaboration system.</span></span>

## <a name="review-the-firewall-report"></a><span data-ttu-id="18e69-142">ファイアウォール レポートの確認</span><span class="sxs-lookup"><span data-stu-id="18e69-142">Review the Firewall Report</span></span>
<span data-ttu-id="18e69-143"><a name="Firewall_report"> </a></span><span class="sxs-lookup"><span data-stu-id="18e69-143"><a name="Firewall_report"> </a></span></span>

<span data-ttu-id="18e69-144">Skype for Business Server 2015 には、一連のファイアウォールルールが複雑な可能性があります。</span><span class="sxs-lookup"><span data-stu-id="18e69-144">Skype for Business Server 2015 has a potentially complex set of firewall rules.</span></span> <span data-ttu-id="18e69-145">計画ツールは、デザイナーの入力条件に基づいて、すべてのファイアウォール要件を詳細に定義するレポートを生成することで、この複雑さを軽減します。</span><span class="sxs-lookup"><span data-stu-id="18e69-145">The Planning Tool reduces this complexity by generating a report that defines in detail all firewall requirements, based on the designer's input criteria.</span></span> <span data-ttu-id="18e69-146">IT 部門のファイアウォール管理者は、このレポートを使用して必要なルールを構成および定義することができます。</span><span class="sxs-lookup"><span data-stu-id="18e69-146">The IT firewall administrator will be able to use this report to configure and define the necessary rules.</span></span>

<span data-ttu-id="18e69-147">ファイアウォール管理の観点から、レポートを慎重に検討して、ファイアウォールルールの終了と競合が生じず、違反する可能性のあるポリシーや手順が存在しなかからなかってください。</span><span class="sxs-lookup"><span data-stu-id="18e69-147">From the standpoint of firewall management, the report should be carefully reviewed to make sure that there are no conflicts with exiting firewall rules and that there are no policies or procedures that might be violated.</span></span>

![ファイアウォール管理者レポート](../../media/Firewall_Report_Admin_Report.png)

## <a name="review-the-dns-report"></a><span data-ttu-id="18e69-149">DNS レポートを確認する</span><span class="sxs-lookup"><span data-stu-id="18e69-149">Review the DNS Report</span></span>
<span data-ttu-id="18e69-150"><a name="DNS_Report"> </a></span><span class="sxs-lookup"><span data-stu-id="18e69-150"><a name="DNS_Report"> </a></span></span>

<span data-ttu-id="18e69-151">管理者レポートの一部である DNS レポートは、内部ネットワーク、境界ネットワーク、および外部ネットワーク内のドメイン ネーム システム (DNS) の推奨エントリと既知のエントリの詳細を示します。</span><span class="sxs-lookup"><span data-stu-id="18e69-151">The DNS Report, which is part of the Administrator Report, details all of the recommended and known entries for the Domain Name System (DNS) in the internal, perimeter, and external networks.</span></span> <span data-ttu-id="18e69-152">設計者がネットワーク ダイアグラムの編集を完了し、すべての IP アドレスと完全修飾ドメイン名 (FQDN) が実稼働値に定義されている場合、DNS レポートは優れた構成リソースを提供します。</span><span class="sxs-lookup"><span data-stu-id="18e69-152">If the designer has completed the edits to the network diagram, and all IP addresses and fully qualified domain names (FQDNs) are defined to their production values, the DNS Report provides an excellent configuration resource.</span></span> <span data-ttu-id="18e69-153">このレポートは、運用上のトラブルシューティング ドキュメントとして機能する場合があります。</span><span class="sxs-lookup"><span data-stu-id="18e69-153">This report can also serve as an operational troubleshooting document.</span></span>

![DNS 管理者レポート](../../media/DNS_Report_Admin_Report.png)

<span data-ttu-id="18e69-155">DNS 管理チームに DNS レポートを十分に確認して、展開中に問題が発生したり、トラブルシューティング セッションを複雑にしたりする可能性があるエラーが発生しなくなさる必要があります。</span><span class="sxs-lookup"><span data-stu-id="18e69-155">You should have your DNS management team review the DNS Report thoroughly to make sure that there are no errors that may cause difficulty during deployment or that may complicate a troubleshooting session.</span></span>

## <a name="see-also"></a><span data-ttu-id="18e69-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="18e69-156">See also</span></span>
<span data-ttu-id="18e69-157"><a name="DNS_Report"> </a></span><span class="sxs-lookup"><span data-stu-id="18e69-157"><a name="DNS_Report"> </a></span></span>

[<span data-ttu-id="18e69-158">管理者レポートの確認</span><span class="sxs-lookup"><span data-stu-id="18e69-158">Reviewing the Administrator Reports</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-reviewing-the-administrator-reports)