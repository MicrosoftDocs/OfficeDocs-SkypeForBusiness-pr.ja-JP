---
title: 新しいダイレクト ルーティング
ms.reviewer: CarolynRowe
author: wlibebe
ms.author: wlibebe
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: この記事では、ダイレクト ルーティングの新機能について説明します。 更新プログラムを頻繁に確認してください。
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.collection:
- M365-voice
ms.openlocfilehash: 6d2496ef355df7a935dbf45321a8b8fd63b8e8de
ms.sourcegitcommit: fc1787ad74a8c454f750a294def188b532cbadd5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2022
ms.locfileid: "67854433"
---
# <a name="whats-new-for-direct-routing"></a>ダイレクト ルーティングの新機能

この記事では、ダイレクト ルーティングの新機能について説明します。 更新プログラムを頻繁に確認してください。

## <a name="trunk-demoting-logic-based-on-sip-options"></a>SIP オプションに基づくトランク降格ロジック

トランクの正常性については、SIP オプションに基づく新機能が導入されています。 ゲートウェイ構成で有効にすると (コマンドレットと SendSipOptions パラメーターSet-CsOnlinePSTNGateway参照)、発信呼び出しのルーティング ロジックによって、SIP オプションを定期的に送信しないトランクが降格されます (予想される期間は、SBC によって 1 分あたり 1 つの SIP オプションが送信されます)。 これらの降格されたトランクは、発信呼び出しで使用可能なトランクの最後の一覧に配置され、最後のトランクとして試行されます。これにより、通話セットアップ時間が短縮される可能性があります。
Microsoft リージョン (NOAM、EMEA、APAC、OCEA) のいずれの SIP プロキシにも、5 分以内に少なくとも 1 つの SIP オプションを送信しない、その機能に対して有効になっているトランクはすべて降格と見なされます。 トランクが MICROSOFT リージョンの SIP プロキシのサブセットのみに SIP オプションを送信する場合、最初にこれらのルートが試行され、残りのルートは降格されます。


## <a name="sip-support"></a>SIP サポート

2022 年 6 月 1 日に、Microsoft はダイレクト ルーティング構成から sip-all.pstnhub.microsoft.com および sip-all.pstnhub.gov.teams.microsoft.us FQDN のサポートを削除します。

6 月 1 日より前にアクションが実行されない場合、ユーザーはダイレクト ルーティングを介して通話を発信または受信できなくなります。

サービスへの影響を防ぐには、

- 推奨されるサブネット (52.112.0.0/14 および 52.120.0.0/14) を任意の分類ルールまたは ACL ルールに使用します。
- ダイレクト ルーティング用にセッション 罫線コントロールを構成するときに、sip-all FQDN の使用を中止します。

詳細については、「 [直接ルーティングを計画する](direct-routing-plan.md)」を参照してください。

## <a name="tls-certificates"></a>TLS 証明書

Microsoft 365 は、異なるルート証明機関 (CA) のセットを使用するように Teams やその他のサービスを更新しています。

影響を受けるサービスの詳細と完全な一覧については、 [Microsoft Teams を含む Microsoft 365 サービスに対する TLS 証明書の変更](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/tls-certificate-changes-to-microsoft-365-services-including/ba-p/3249676)に関するページを参照してください。

## <a name="certificate-authorities"></a>証明機関

2022 年 2 月 1 日以降、ダイレクト ルーティング SIP インターフェイスは、Microsoft 信頼ルート証明書プログラムの一部である証明機関 (CA) によって署名された証明書のみを信頼します。 サービスへの影響を回避するには、次の手順に従います。

- SBC 証明書が、Microsoft 信頼されたルート証明書プログラムの一部である CA によって署名されていることを確認します。
- 証明書の拡張キー使用法 (EKU) 拡張機能に "サーバー認証" が含まれていることを確認します。

Microsoft 信頼されたルート証明書プログラムの詳細については、「 [プログラム要件 - Microsoft 信頼されたルート プログラム」を](/security/trusted-root/program-requirements)参照してください。

信頼できる CA の一覧については、「 [Microsoft 付属の CA 証明書リスト](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)」を参照してください。

## <a name="replace-headers"></a>ヘッダーを置き換える

2022 年 4 月以降、ダイレクト ルーティングは、Replaces ヘッダーが定義されている SIP 要求を拒否します。 Microsoft が Replaces ヘッダーをセッション ボーダー コントローラー (SBC) に送信するフローに変更はありません。

SBC 構成を確認し、SIP 要求で Replaces ヘッダーを使用していないことを確認します。

## <a name="tls10-and-11"></a>TLS1.0 および 1.1

お客様にクラス最高の暗号化を提供するために、Microsoft はトランスポート層セキュリティ (TLS) バージョン 1.0 および 1.1 を非推奨にする予定です。 2022 年 4 月 3 日、Microsoft はダイレクト ルーティング SIP インターフェイスに TLS1.2 の使用を強制します。

サービスへの影響を回避するには、TLS1.2 をサポートするように SBC が構成され、次のいずれかの暗号スイートを使用して接続できることを確認します。

- TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384(ECDHE-RSA-AES256-GCM-SHA384)
- TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256(ECDHE-RSA-AES128-GCM-SHA256)
- TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384(ECDHE-RSA-AES256-SHA384)
- TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256(ECDHE-RSA-AES128-SHA256)

## <a name="related-topics"></a>関連項目

- [ダイレクト ルーティング - SIP プロトコル](direct-routing-protocols-sip.md)
