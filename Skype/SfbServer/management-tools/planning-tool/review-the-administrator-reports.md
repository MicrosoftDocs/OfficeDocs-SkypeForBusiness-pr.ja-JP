---
title: Skype for Business Server 2015 で管理者レポートを確認する
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/5/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 22d480ea-cd64-4d09-99fe-96e997570844
description: 管理者レポートは、展開と運用に関する詳細情報です。 このレポートは、[サイトの設計] でマークされた選択肢に基づいて生成されます。 設計者は、ネットワーク ダイアグラムを編集し、サーバー、プール、およびロード バランサーの完全な IP アドレスと完全修飾ドメイン名 (FQDN) を定義することで、管理者レポートに値を追加できます。
ms.openlocfilehash: 5cab8231428ace2a0d77132481819eed304d3519
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222730"
---
# <a name="review-the-administrator-reports-in-skype-for-business-server-2015"></a>Review the Administrator Reports in Skype for Business Server 2015

管理者レポートは、展開と運用に関する詳細情報です。このレポートは、[**サイトの設計**] でマークされた選択肢に基づいて生成されます。設計者は、ネットワーク ダイアグラムを編集し、サーバー、プール、およびロード バランサーの完全な IP アドレスと完全修飾ドメイン名 (FQDN) を定義することで、管理者レポートに値を追加できます。

管理者レポート機能を使用すると以下のことができます:

- [Review the Summary Report](review-the-administrator-reports.md#Summary_report)

- [Review the Certificates Report](review-the-administrator-reports.md#Certificates_Report)

- [Review the Firewall Report](review-the-administrator-reports.md#Firewall_report)

- [Review the DNS Report](review-the-administrator-reports.md#DNS_Report)

## <a name="review-the-summary-report"></a>概要レポートの確認
<a name="Summary_report"> </a>

ビジネス管理者はレポートの Skype は、最初の 4 つの有益なレポートの詳細設計を文書化するのです。 このレポートおよび関連付けられた他の 3 つのレポートの情報は、情報テクノロジ チームにとって役立ちます。

![概要管理レポート](../../media/General_Summary_Report_Admin_Report.png)

概要レポートは、エッジ ネットワークに関連付けられた一般的な構成情報を示します。レポートには、位置、完全修飾ドメイン名 (FQDN) と IP アドレス、ネットワークの種類、特定の役割に固有のコメントが記録されます。

設計者および、インフラストラクチャの展開、管理、およびメンテナンスを担当する各チームは、概要レポートを参照して精度を高め、エラーを最小限に抑える必要があります。

また、ほかにも次のような詳細レポートを確認できます。

- 証明書レポート

- ファイアウォール レポート

- DNS レポート

## <a name="review-the-certificates-report"></a>証明書レポートの確認
<a name="Certificates_Report"> </a>

証明書レポートには、ビジネス サーバー 2015 の展開の推奨される Skype のために必要なすべての証明書が含まれています。 計画ツール アカウント、サブジェクト名とサブジェクト代替名を入力します。 編集前に残されている既定のテキストは、要求と証明書の発行を担当するチームの潜在的な課題です。 証明書の情報には、証明書が通常発行からの情報も含まれています。 インフラストラクチャが内部公開キー基盤 (PKI) の場所で、パブリック証明書プロバイダーからすべての証明書を要求できます。 拡張キー使用法 (EKU) およびレポートのフィールドを割り当てるにはどのような目的と各証明書の場所する必要がありますを理解するうえで非常に役に立つ。

![証明書管理レポート](../../media/Certificates_Report_Admin_Report.png)

展開内のそれぞれの証明書の使用法および目的を注意深く確認し、しっかりと理解してください。 証明書の役割についての質問がある場合は、どのサーバーまたはサービスが何を対象としているのかを確認します。 ビジネス サーバー 2015 の Skype での証明書は、2 つの主な目的で使用されます。

- 相互トランスポート層セキュリティ (MTLS) - 各通信に関係するコンピューターは、別のコンピューターに自分の身元を証明する証明書を提示します。 これは、サーバー認証として知られています。 通信は、各コンピューターが他のコンピューターの id を信頼するまで開始できません。

- 暗号化 - 暗号化 Secure Sockets Layer、または、SSL とトランスポート ・ レイヤ ・ セキュリティ (TLS) は、通信をセキュリティ保護には、プライバシーを確保し、信頼できるコミュニケーションおよびコラボレーション システムを作成する重要な手段です。

## <a name="review-the-firewall-report"></a>ファイアウォール レポートの確認
<a name="Firewall_report"> </a>

ビジネス サーバー 2015 の Skype では、可能性のある複雑なファイアウォールの規則のセットがあります。 計画ツールでは、デザイナーの入力条件に基づいて、すべてのファイアウォールの要件の詳細に定義するレポートを生成することによってこのような複雑さが軽減されます。 IT 部門のファイアウォール管理者は、このレポートを使用して、必要なルールを構成および定義することができます。

ファイアウォール管理の観点から、このレポートを慎重に確認して、既存のファイアウォール ルールと矛盾がないかどうか、また、違反する可能性があるポリシーや手順がないかどうかを確認することをお勧めします。

![ファイアウォール管理レポート](../../media/Firewall_Report_Admin_Report.png)

## <a name="review-the-dns-report"></a>DNS レポートの確認
<a name="DNS_Report"> </a>

管理者レポートに含まれる DNS レポートには、内部、境界、および外部ネットワークのドメイン ネーム システム (DNS) に対するすべての推奨エントリと既知のエントリが詳述されています。設計者がネットワーク ダイアグラムの編集を完了し、すべての IP アドレスと完全修飾ドメイン名 (FQDN) が実稼働環境値に定義されると、DNS レポートのエントリは、優れた構成リソースとして利用できます。また、このレポートは、実践的なトラブルシューティング ドキュメントとしての役割も果たします。

![DNS 管理レポート](../../media/DNS_Report_Admin_Report.png)

DNS レポートを徹底的に調べて、展開中に問題を引き起こす可能性のある、またはトラブルシューティング セッションを複雑にする可能性のあるエラーをなくすように DNS 管理チームに指示することをお勧めします。

## <a name="see-also"></a>関連項目
<a name="DNS_Report"> </a>

[Reviewing the Administrator Reports](https://technet.microsoft.com/library/1dee56a9-a033-4201-9765-e3469bd7d3e3.aspx)
