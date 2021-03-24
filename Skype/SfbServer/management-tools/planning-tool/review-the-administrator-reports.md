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
# <a name="review-the-administrator-reports-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の管理者レポートを確認する

管理者レポートは、展開と運用に関する詳細情報です。 レポートは、デザイン サイトでマークされている選択内容に基 **づいて生成されます**。 設計者は、ネットワーク ダイアグラムを編集し、サーバー、プール、およびロード バランサーの完全な IP アドレスと完全修飾ドメイン名 (FQDN) を定義することで、管理者レポートに値を追加できます。

管理者レポート機能を使用すると、次の機能を使用できます。

- [概要レポートを確認する](review-the-administrator-reports.md#Summary_report)

- [証明書レポートを確認する](review-the-administrator-reports.md#Certificates_Report)

- [ファイアウォール レポートの確認](review-the-administrator-reports.md#Firewall_report)

- [DNS レポートを確認する](review-the-administrator-reports.md#DNS_Report)

## <a name="review-the-summary-report"></a>概要レポートを確認する
<a name="Summary_report"> </a>

Skype for Business Administrator Report は、デザインを詳細に文書化する 4 つの貴重なレポートの最初のレポートです。 このレポートの情報と、関連付けられている他の 3 つのレポートは、情報テクノロジ チームに役立ちます。

![概要管理レポート](../../media/General_Summary_Report_Admin_Report.png)

概要レポートは、エッジ ネットワークに関連付けられた一般的な構成情報を示します。 場所、完全修飾ドメイン名 (FQDN) と IP アドレス、ネットワークの種類、および特定の役割に固有のコメントが文書化されています。

設計者とインフラストラクチャを展開、管理、および保守する各チームは、概要レポートの正確性を確認し、エラーが最小限に抑え込む必要があります。

さらに詳細なレポートを表示することもできます。

- 証明書レポート

- ファイアウォール レポート

- DNS レポート

## <a name="review-the-certificates-report"></a>証明書レポートを確認する
<a name="Certificates_Report"> </a>

証明書レポートには、推奨される Skype for Business Server 2015 展開で必要なすべての証明書が含まれている。 計画ツールには、入力されたサブジェクト名とサブジェクトの代替名が含されます。 編集されていない既定のテキストは、証明書の要求と発行を担当するチームにとって潜在的な課題を表している可能性があります。 証明書情報には、証明書が主としてどこから発行されるかについての情報も含まれています。 インフラストラクチャが内部公開キー基盤 (PKI) を持たない場合、すべての証明書はパブリック証明書プロバイダーを介して要求することができます。 拡張キー使用法 (EKU) およびレポートの [割り当て] フィールドは、それぞれの証明書の目的および場所を知るのに非常に有用です。

![証明書の管理レポート](../../media/Certificates_Report_Admin_Report.png)

展開内の各証明書の使用と目的を注意深く確認し、理解してください。 証明書の動作に関する質問がある場合は、どのサーバーまたはサービスが何と話しているのかを判断します。 Skype for Business Server 2015 の証明書は、次の 2 つの主な目的で使用されます。

- 相互トランスポート層セキュリティ (MTLS) - 通信に関係するコンピューターは、それぞれ別のコンピューターに自分の ID を証明する証明書を提示します。 これはサーバー認証と呼ばれる。 各コンピューターが他のコンピューターの ID を信頼するまで、通信を開始できません。

- 暗号化 - 暗号化 (Secure Sockets Layer、SSL、トランスポート層セキュリティ、または TLS) は、通信のセキュリティ保護、プライバシーの確保、信頼できる通信およびコラボレーション システムの作成に役立つ重要な手段です。

## <a name="review-the-firewall-report"></a>ファイアウォール レポートの確認
<a name="Firewall_report"> </a>

Skype for Business Server 2015 には、一連のファイアウォールルールが複雑な可能性があります。 計画ツールは、デザイナーの入力条件に基づいて、すべてのファイアウォール要件を詳細に定義するレポートを生成することで、この複雑さを軽減します。 IT 部門のファイアウォール管理者は、このレポートを使用して必要なルールを構成および定義することができます。

ファイアウォール管理の観点から、レポートを慎重に検討して、ファイアウォールルールの終了と競合が生じず、違反する可能性のあるポリシーや手順が存在しなかからなかってください。

![ファイアウォール管理者レポート](../../media/Firewall_Report_Admin_Report.png)

## <a name="review-the-dns-report"></a>DNS レポートを確認する
<a name="DNS_Report"> </a>

管理者レポートの一部である DNS レポートは、内部ネットワーク、境界ネットワーク、および外部ネットワーク内のドメイン ネーム システム (DNS) の推奨エントリと既知のエントリの詳細を示します。 設計者がネットワーク ダイアグラムの編集を完了し、すべての IP アドレスと完全修飾ドメイン名 (FQDN) が実稼働値に定義されている場合、DNS レポートは優れた構成リソースを提供します。 このレポートは、運用上のトラブルシューティング ドキュメントとして機能する場合があります。

![DNS 管理者レポート](../../media/DNS_Report_Admin_Report.png)

DNS 管理チームに DNS レポートを十分に確認して、展開中に問題が発生したり、トラブルシューティング セッションを複雑にしたりする可能性があるエラーが発生しなくなさる必要があります。

## <a name="see-also"></a>関連項目
<a name="DNS_Report"> </a>

[管理者レポートの確認](/previous-versions/office/lync-server-2013/lync-server-2013-reviewing-the-administrator-reports)