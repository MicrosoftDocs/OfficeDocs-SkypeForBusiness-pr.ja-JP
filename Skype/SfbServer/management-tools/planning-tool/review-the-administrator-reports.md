---
title: Skype for Business Server 2015 での管理者レポートの確認
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
description: 管理者レポートは、展開と運用に関する詳細情報です。 レポートは、デザイン サイトでマークされている選択内容に基づいて生成されます。 設計者は、ネットワーク ダイアグラムを編集し、サーバー、プール、およびロード バランサーの完全な IP アドレスと完全修飾ドメイン名 (FQDN) を定義することで、管理者レポートに値を追加できます。
ms.openlocfilehash: b8c18dcfef28ac93e8c2036fee7f7b105f5c69bd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823347"
---
# <a name="review-the-administrator-reports-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での管理者レポートの確認

管理者レポートは、展開と運用に関する詳細情報です。 レポートは、デザイン サイトでマークされている選択に基づいて **生成されます**。 設計者は、ネットワーク ダイアグラムを編集し、サーバー、プール、およびロード バランサーの完全な IP アドレスと完全修飾ドメイン名 (FQDN) を定義することで、管理者レポートに値を追加できます。

管理者レポート機能を使用すると、次の機能を実行できます。

- [概要レポートを確認する](review-the-administrator-reports.md#Summary_report)

- [証明書レポートを確認する](review-the-administrator-reports.md#Certificates_Report)

- [ファイアウォール レポートを確認する](review-the-administrator-reports.md#Firewall_report)

- [DNS レポートを確認する](review-the-administrator-reports.md#DNS_Report)

## <a name="review-the-summary-report"></a>概要レポートを確認する
<a name="Summary_report"> </a>

Skype for Business 管理者レポートは、設計を詳細に文書化した 4 つの貴重なレポートの最初のレポートです。 このレポートの情報と他の 3 つの関連レポートは、情報技術チームにとって役立ちます。

![一般的な概要管理レポート](../../media/General_Summary_Report_Admin_Report.png)

概要レポートは、エッジ ネットワークに関連付けられた一般的な構成情報を示します。 場所、完全修飾ドメイン名 (FQDN) と IP アドレス、ネットワークの種類、特定の役割に固有のコメントが文書化されています。

設計者と、インフラストラクチャの展開、管理、および保守を行う各チームは、概要レポートを確認して正確性を確認し、エラーが少なくとも確実に発生する必要があります。

さらに詳細なレポートを表示することもできます。

- 証明書レポート

- ファイアウォール レポート

- DNS レポート

## <a name="review-the-certificates-report"></a>証明書レポートを確認する
<a name="Certificates_Report"> </a>

証明書レポートには、Skype for Business Server 2015 の推奨展開で必要なすべての証明書が含まれている。 計画ツールでは、入力されたサブジェクト名とサブジェクトの代替名が使用されます。 編集されていない既定のテキストは、証明書の要求と発行を担当するチームにとって潜在的な課題を表している可能性があります。 証明書情報には、証明書が主としてどこから発行されるかについての情報も含まれています。 インフラストラクチャが内部公開キー基盤 (PKI) を持たない場合、すべての証明書はパブリック証明書プロバイダーを介して要求することができます。 拡張キー使用法 (EKU) およびレポートの [割り当て] フィールドは、それぞれの証明書の目的および場所を知るのに非常に有用です。

![証明書管理レポート](../../media/Certificates_Report_Admin_Report.png)

展開内の各証明書の用途と目的を慎重に確認し、理解してください。 証明書の動作に関する質問がある場合は、どのサーバーまたはサービスが何に話し合っているのかを確認します。 Skype for Business Server 2015 の証明書は、主に次の 2 つの目的で使用されます。

- 相互トランスポート層セキュリティ (MTLS) - 通信に関係するコンピューターは、それぞれ別のコンピューターに ID を証明する証明書を提示します。 これは、サーバー認証と呼ばれる機能です。 各コンピューターが他のコンピューターの ID を信頼するまで通信を開始できません。

- 暗号化 - 暗号化 (Secure Sockets Layer、SSL、およびトランスポート層セキュリティ (TLS) は、通信をセキュリティで保護し、プライバシーを確保し、信頼できる通信およびコラボレーション システムを作成するのに役立つ重要な手段です。

## <a name="review-the-firewall-report"></a>ファイアウォール レポートを確認する
<a name="Firewall_report"> </a>

Skype for Business Server 2015 には、潜在的に複雑な一連のファイアウォール ルールがあります。 計画ツールは、設計者の入力条件に基づいて、すべてのファイアウォール要件を詳細に定義するレポートを生成することで、この複雑さを軽減します。 IT 部門のファイアウォール管理者は、このレポートを使用して必要なルールを構成および定義することができます。

ファイアウォール管理の観点から、このレポートは慎重に確認し、ファイアウォールルールの終了と競合が生じず、違反する可能性のあるポリシーや手順が存在していないか確認する必要があります。

![ファイアウォール管理者レポート](../../media/Firewall_Report_Admin_Report.png)

## <a name="review-the-dns-report"></a>DNS レポートを確認する
<a name="DNS_Report"> </a>

管理者レポートの一部である DNS レポートでは、内部、境界、および外部ネットワークのドメイン ネーム システム (DNS) の推奨エントリと既知のエントリのすべてが詳細に示されます。 設計者がネットワーク ダイアグラムの編集を完了し、すべての IP アドレスと完全修飾ドメイン名 (FQDN) が実稼働環境の値に定義されている場合、DNS レポートは優れた構成リソースを提供します。 このレポートは、運用上のトラブルシューティングドキュメントの役割を果たします。

![DNS 管理者レポート](../../media/DNS_Report_Admin_Report.png)

DNS 管理チームに DNS レポートを十分に確認して、展開中に問題を引き起こす可能性があるエラーや、トラブルシューティング セッションを複雑にする可能性があるエラーが発生されていないことを確認する必要があります。

## <a name="see-also"></a>関連項目
<a name="DNS_Report"> </a>

[管理者レポートの確認](https://technet.microsoft.com/library/1dee56a9-a033-4201-9765-e3469bd7d3e3.aspx)
