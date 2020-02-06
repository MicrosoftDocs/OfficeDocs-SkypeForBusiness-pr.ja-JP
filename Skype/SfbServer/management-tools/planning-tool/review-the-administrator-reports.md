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
# <a name="review-the-administrator-reports-in-skype-for-business-server-2015"></a>Review the Administrator Reports in Skype for Business Server 2015

管理者レポートは、展開と運用に関する詳細情報です。このレポートは、[**サイトの設計**] でマークされた選択肢に基づいて生成されます。設計者は、ネットワーク ダイアグラムを編集し、サーバー、プール、およびロード バランサーの完全な IP アドレスと完全修飾ドメイン名 (FQDN) を定義することで、管理者レポートに値を追加できます。

管理者レポート機能を使用すると以下のことができます:

- [Review the Summary Report](review-the-administrator-reports.md#Summary_report)

- [Review the Certificates Report](review-the-administrator-reports.md#Certificates_Report)

- [Review the Firewall Report](review-the-administrator-reports.md#Firewall_report)

- [Review the DNS Report](review-the-administrator-reports.md#DNS_Report)

## <a name="review-the-summary-report"></a>概要レポートの確認
<a name="Summary_report"> </a>

Skype for Business 管理者レポートは、設計の詳細を記載した4つの重要なレポートの最初です。 このレポートおよび関連付けられた他の 3 つのレポートの情報は、情報テクノロジ チームにとって役立ちます。

![概要管理レポート](../../media/General_Summary_Report_Admin_Report.png)

概要レポートは、エッジ ネットワークに関連付けられた一般的な構成情報を示します。レポートには、位置、完全修飾ドメイン名 (FQDN) と IP アドレス、ネットワークの種類、特定の役割に固有のコメントが記録されます。

設計者および、インフラストラクチャの展開、管理、およびメンテナンスを担当する各チームは、概要レポートを参照して精度を高め、エラーを最小限に抑える必要があります。

また、ほかにも次のような詳細レポートを確認できます。

- 証明書レポート

- ファイアウォール レポート

- DNS レポート

## <a name="review-the-certificates-report"></a>証明書レポートの確認
<a name="Certificates_Report"> </a>

証明書レポートには、推奨される Skype for Business Server 2015 の展開で必要なすべての証明書が含まれています。 入力されたサブジェクト名とサブジェクトの代替名の計画ツールアカウント。 未編集として残っている既定のテキストは、証明書の要求と発行を担当するチームの潜在的な問題を表している可能性があります。 証明書情報には、証明書の一般的な発行元に関する情報も含まれます。 インフラストラクチャに内部の公開キー基盤 (PKI) が配置されていない場合は、すべての証明書を公開証明書プロバイダーを通じて要求できます。 レポートの拡張キー使用法 (EKU) とフィールドへの割り当ては、各証明書の目的と場所を理解するのに非常に役立ちます。

![証明書管理レポート](../../media/Certificates_Report_Admin_Report.png)

展開内のそれぞれの証明書の使用法および目的を注意深く確認し、しっかりと理解してください。 証明書の役割についての質問がある場合は、どのサーバーまたはサービスが何を対象としているのかを確認します。 Skype for Business Server 2015 の証明書は、主に次の2つの目的で使用されます。

- 相互トランスポート層セキュリティ (MTLS)-通信に関係するコンピューターはそれぞれ、身元を証明する証明書を別のコンピューターに提示します。 これは、サーバー認証として知られています。 各コンピューターが他のコンピューターの id を信頼するまで、通信を開始することはできません。

- 暗号化-暗号化 (Secure Sockets Layer、SSL、トランスポート層セキュリティ、または TLS) は、通信をセキュリティで保護し、プライバシーを保護し、信頼された通信とコラボレーションシステムを作成するうえで重要な手段です。

## <a name="review-the-firewall-report"></a>ファイアウォール レポートの確認
<a name="Firewall_report"> </a>

Skype for Business Server 2015 には、複雑なファイアウォールルールがあります。 計画ツールでは、デザイナーの入力条件に基づいて、すべてのファイアウォール要件を詳細に定義するレポートを生成して、この複雑さを軽減します。 IT 部門のファイアウォール管理者は、このレポートを使用して、必要なルールを構成および定義することができます。

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
