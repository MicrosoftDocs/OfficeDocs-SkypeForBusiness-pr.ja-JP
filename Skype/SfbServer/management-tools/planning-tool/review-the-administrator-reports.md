---
title: Skype for Business Server 2015 で管理者レポートを確認する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 管理者レポートは、展開と運用に関する詳細情報です。 このレポートは、[サイトの設計] でマークされた選択肢に基づいて生成されます。 設計者は、ネットワーク ダイアグラムを編集し、サーバー、プール、およびロード バランサーの完全な IP アドレスと完全修飾ドメイン名 (FQDN) を定義することで、管理者レポートに値を追加できます。
ms.openlocfilehash: ae6dba3f5967fcd10618a8ab53c754a4f38da748
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816296"
---
# <a name="review-the-administrator-reports-in-skype-for-business-server-2015"></a><span data-ttu-id="12b45-105">Review the Administrator Reports in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="12b45-105">Review the Administrator Reports in Skype for Business Server 2015</span></span>

<span data-ttu-id="12b45-p102">管理者レポートは、展開と運用に関する詳細情報です。このレポートは、[**サイトの設計**] でマークされた選択肢に基づいて生成されます。設計者は、ネットワーク ダイアグラムを編集し、サーバー、プール、およびロード バランサーの完全な IP アドレスと完全修飾ドメイン名 (FQDN) を定義することで、管理者レポートに値を追加できます。</span><span class="sxs-lookup"><span data-stu-id="12b45-p102">The Administrator Reports are detailed information for deployment and operations. The reports are generated based on the selections marked in **Design Sites**. The designer can further add value to the Administrator Reports by editing the network diagrams and defining the complete IP addresses and fully qualified domain names (FQDNs) for servers, pools, and load balancers.</span></span>

<span data-ttu-id="12b45-109">管理者レポート機能を使用すると以下のことができます:</span><span class="sxs-lookup"><span data-stu-id="12b45-109">The Administrator reports feature allows you to:</span></span>

- [<span data-ttu-id="12b45-110">Review the Summary Report</span><span class="sxs-lookup"><span data-stu-id="12b45-110">Review the Summary Report</span></span>](review-the-administrator-reports.md#Summary_report)

- [<span data-ttu-id="12b45-111">Review the Certificates Report</span><span class="sxs-lookup"><span data-stu-id="12b45-111">Review the Certificates Report</span></span>](review-the-administrator-reports.md#Certificates_Report)

- [<span data-ttu-id="12b45-112">Review the Firewall Report</span><span class="sxs-lookup"><span data-stu-id="12b45-112">Review the Firewall Report</span></span>](review-the-administrator-reports.md#Firewall_report)

- [<span data-ttu-id="12b45-113">Review the DNS Report</span><span class="sxs-lookup"><span data-stu-id="12b45-113">Review the DNS Report</span></span>](review-the-administrator-reports.md#DNS_Report)

## <a name="review-the-summary-report"></a><span data-ttu-id="12b45-114">概要レポートの確認</span><span class="sxs-lookup"><span data-stu-id="12b45-114">Review the Summary Report</span></span>
<span data-ttu-id="12b45-115"><a name="Summary_report"> </a></span><span class="sxs-lookup"><span data-stu-id="12b45-115"><a name="Summary_report"> </a></span></span>

<span data-ttu-id="12b45-116">Skype for Business 管理者レポートは、設計の詳細を記載した4つの重要なレポートの最初です。</span><span class="sxs-lookup"><span data-stu-id="12b45-116">The Skype for Business Administrator Report is the first of four valuable reports that document your design in detail.</span></span> <span data-ttu-id="12b45-117">このレポートおよび関連付けられた他の 3 つのレポートの情報は、情報テクノロジ チームにとって役立ちます。</span><span class="sxs-lookup"><span data-stu-id="12b45-117">The information in this report, and the other three associated reports, is useful for your Information Technology Teams:</span></span>

![概要管理レポート](../../media/General_Summary_Report_Admin_Report.png)

<span data-ttu-id="12b45-p104">概要レポートは、エッジ ネットワークに関連付けられた一般的な構成情報を示します。レポートには、位置、完全修飾ドメイン名 (FQDN) と IP アドレス、ネットワークの種類、特定の役割に固有のコメントが記録されます。</span><span class="sxs-lookup"><span data-stu-id="12b45-p104">The Summary Report lists general configuration information associated with your Edge network. The location, fully qualified domain name (FQDN) and IP address, type of network, and comments specific to a given role are documented.</span></span>

<span data-ttu-id="12b45-121">設計者および、インフラストラクチャの展開、管理、およびメンテナンスを担当する各チームは、概要レポートを参照して精度を高め、エラーを最小限に抑える必要があります。</span><span class="sxs-lookup"><span data-stu-id="12b45-121">The designer and each of the teams that will deploy, manage, and maintain the infrastructure should review the summary report for accuracy and to make sure that errors are at a minimum.</span></span>

<span data-ttu-id="12b45-122">また、ほかにも次のような詳細レポートを確認できます。</span><span class="sxs-lookup"><span data-stu-id="12b45-122">You can also view more detailed reports:</span></span>

- <span data-ttu-id="12b45-123">証明書レポート</span><span class="sxs-lookup"><span data-stu-id="12b45-123">Certificates Report</span></span>

- <span data-ttu-id="12b45-124">ファイアウォール レポート</span><span class="sxs-lookup"><span data-stu-id="12b45-124">Firewall Report</span></span>

- <span data-ttu-id="12b45-125">DNS レポート</span><span class="sxs-lookup"><span data-stu-id="12b45-125">DNS Report</span></span>

## <a name="review-the-certificates-report"></a><span data-ttu-id="12b45-126">証明書レポートの確認</span><span class="sxs-lookup"><span data-stu-id="12b45-126">Review the Certificates Report</span></span>
<span data-ttu-id="12b45-127"><a name="Certificates_Report"> </a></span><span class="sxs-lookup"><span data-stu-id="12b45-127"><a name="Certificates_Report"> </a></span></span>

<span data-ttu-id="12b45-128">証明書レポートには、推奨される Skype for Business Server 2015 の展開で必要なすべての証明書が含まれています。</span><span class="sxs-lookup"><span data-stu-id="12b45-128">The Certificates Report contains all certificates that are required in the recommended Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="12b45-129">入力されたサブジェクト名とサブジェクトの代替名の計画ツールアカウント。</span><span class="sxs-lookup"><span data-stu-id="12b45-129">The Planning Tool accounts for the subject names and subject alternative names that are entered.</span></span> <span data-ttu-id="12b45-130">未編集として残っている既定のテキストは、証明書の要求と発行を担当するチームの潜在的な問題を表している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="12b45-130">Default text that is left unedited may represent a potential challenge for the team responsible for requesting and issuing the certificates.</span></span> <span data-ttu-id="12b45-131">証明書情報には、証明書の一般的な発行元に関する情報も含まれます。</span><span class="sxs-lookup"><span data-stu-id="12b45-131">Certificate information also contains information about where the certificate can typically be issued from.</span></span> <span data-ttu-id="12b45-132">インフラストラクチャに内部の公開キー基盤 (PKI) が配置されていない場合は、すべての証明書を公開証明書プロバイダーを通じて要求できます。</span><span class="sxs-lookup"><span data-stu-id="12b45-132">If the infrastructure does not have an internal public key infrastructure (PKI) in place, all certificates can be requested through a public certificate provider.</span></span> <span data-ttu-id="12b45-133">レポートの拡張キー使用法 (EKU) とフィールドへの割り当ては、各証明書の目的と場所を理解するのに非常に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="12b45-133">Extended key usages (EKU) and Assign To fields in the report are very helpful in understanding what the purpose and location for each certificate should be.</span></span>

![証明書管理レポート](../../media/Certificates_Report_Admin_Report.png)

<span data-ttu-id="12b45-135">展開内のそれぞれの証明書の使用法および目的を注意深く確認し、しっかりと理解してください。</span><span class="sxs-lookup"><span data-stu-id="12b45-135">Carefully review, and be sure to understand, the use and purpose of each certificate in the deployment.</span></span> <span data-ttu-id="12b45-136">証明書の役割についての質問がある場合は、どのサーバーまたはサービスが何を対象としているのかを確認します。</span><span class="sxs-lookup"><span data-stu-id="12b45-136">If there is a question about what a certificate does, determine which server or service is talking to what.</span></span> <span data-ttu-id="12b45-137">Skype for Business Server 2015 の証明書は、主に次の2つの目的で使用されます。</span><span class="sxs-lookup"><span data-stu-id="12b45-137">Certificates in Skype for Business Server 2015 are used for two primary purposes:</span></span>

- <span data-ttu-id="12b45-138">相互トランスポート層セキュリティ (MTLS)-通信に関係するコンピューターはそれぞれ、身元を証明する証明書を別のコンピューターに提示します。</span><span class="sxs-lookup"><span data-stu-id="12b45-138">Mutual Transport Layer Security (MTLS) - The computers involved in the communication each present a certificate that proves their identity to another computer.</span></span> <span data-ttu-id="12b45-139">これは、サーバー認証として知られています。</span><span class="sxs-lookup"><span data-stu-id="12b45-139">This is known as server authentication.</span></span> <span data-ttu-id="12b45-140">各コンピューターが他のコンピューターの id を信頼するまで、通信を開始することはできません。</span><span class="sxs-lookup"><span data-stu-id="12b45-140">Communication cannot begin until each computer trusts the other computer's identity.</span></span>

- <span data-ttu-id="12b45-141">暗号化-暗号化 (Secure Sockets Layer、SSL、トランスポート層セキュリティ、または TLS) は、通信をセキュリティで保護し、プライバシーを保護し、信頼された通信とコラボレーションシステムを作成するうえで重要な手段です。</span><span class="sxs-lookup"><span data-stu-id="12b45-141">Encryption - Encryption (Secure Sockets Layer, or SSL, and Transport Layer Security, or TLS) is a critical means to help secure communications, help ensure privacy, and to create a trusted communications and collaboration system.</span></span>

## <a name="review-the-firewall-report"></a><span data-ttu-id="12b45-142">ファイアウォール レポートの確認</span><span class="sxs-lookup"><span data-stu-id="12b45-142">Review the Firewall Report</span></span>
<span data-ttu-id="12b45-143"><a name="Firewall_report"> </a></span><span class="sxs-lookup"><span data-stu-id="12b45-143"><a name="Firewall_report"> </a></span></span>

<span data-ttu-id="12b45-144">Skype for Business Server 2015 には、複雑なファイアウォールルールがあります。</span><span class="sxs-lookup"><span data-stu-id="12b45-144">Skype for Business Server 2015 has a potentially complex set of firewall rules.</span></span> <span data-ttu-id="12b45-145">計画ツールでは、デザイナーの入力条件に基づいて、すべてのファイアウォール要件を詳細に定義するレポートを生成して、この複雑さを軽減します。</span><span class="sxs-lookup"><span data-stu-id="12b45-145">The Planning Tool reduces this complexity by generating a report that defines in detail all firewall requirements, based on the designer's input criteria.</span></span> <span data-ttu-id="12b45-146">IT 部門のファイアウォール管理者は、このレポートを使用して、必要なルールを構成および定義することができます。</span><span class="sxs-lookup"><span data-stu-id="12b45-146">The IT firewall administrator will be able to use this report to configure and define the necessary rules.</span></span>

<span data-ttu-id="12b45-147">ファイアウォール管理の観点から、このレポートを慎重に確認して、既存のファイアウォール ルールと矛盾がないかどうか、また、違反する可能性があるポリシーや手順がないかどうかを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="12b45-147">From the standpoint of firewall management, the report should be carefully reviewed to make sure that there are no conflicts with exiting firewall rules and that there are no policies or procedures that might be violated.</span></span>

![ファイアウォール管理レポート](../../media/Firewall_Report_Admin_Report.png)

## <a name="review-the-dns-report"></a><span data-ttu-id="12b45-149">DNS レポートの確認</span><span class="sxs-lookup"><span data-stu-id="12b45-149">Review the DNS Report</span></span>
<span data-ttu-id="12b45-150"><a name="DNS_Report"> </a></span><span class="sxs-lookup"><span data-stu-id="12b45-150"><a name="DNS_Report"> </a></span></span>

<span data-ttu-id="12b45-p109">管理者レポートに含まれる DNS レポートには、内部、境界、および外部ネットワークのドメイン ネーム システム (DNS) に対するすべての推奨エントリと既知のエントリが詳述されています。設計者がネットワーク ダイアグラムの編集を完了し、すべての IP アドレスと完全修飾ドメイン名 (FQDN) が実稼働環境値に定義されると、DNS レポートのエントリは、優れた構成リソースとして利用できます。また、このレポートは、実践的なトラブルシューティング ドキュメントとしての役割も果たします。</span><span class="sxs-lookup"><span data-stu-id="12b45-p109">The DNS Report, which is part of the Administrator Report, details all of the recommended and known entries for the Domain Name System (DNS) in the internal, perimeter, and external networks. If the designer has completed the edits to the network diagram, and all IP addresses and fully qualified domain names (FQDNs) are defined to their production values, the DNS Report provides an excellent configuration resource. This report can also serve as an operational troubleshooting document.</span></span>

![DNS 管理レポート](../../media/DNS_Report_Admin_Report.png)

<span data-ttu-id="12b45-155">DNS レポートを徹底的に調べて、展開中に問題を引き起こす可能性のある、またはトラブルシューティング セッションを複雑にする可能性のあるエラーをなくすように DNS 管理チームに指示することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="12b45-155">You should have your DNS management team review the DNS Report thoroughly to make sure that there are no errors that may cause difficulty during deployment or that may complicate a troubleshooting session.</span></span>

## <a name="see-also"></a><span data-ttu-id="12b45-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="12b45-156">See also</span></span>
<span data-ttu-id="12b45-157"><a name="DNS_Report"> </a></span><span class="sxs-lookup"><span data-stu-id="12b45-157"><a name="DNS_Report"> </a></span></span>

[<span data-ttu-id="12b45-158">Reviewing the Administrator Reports</span><span class="sxs-lookup"><span data-stu-id="12b45-158">Reviewing the Administrator Reports</span></span>](https://technet.microsoft.com/library/1dee56a9-a033-4201-9765-e3469bd7d3e3.aspx)
