---
title: 新しいダイレクト ルーティングの概要
ms.reviewer: CarolynRowe
author: wlibebe
ms.author: wlibebe
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: この記事では、ダイレクト ルーティングの新機能について説明します。 頻繁に更新プログラムを確認してください。
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.collection:
- M365-voice
ms.openlocfilehash: 85a700faf37044c97c432707b07b6d6699c6692b
ms.sourcegitcommit: 1f4a0b7cf03f63438bb37668d053853494c92168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2023
ms.locfileid: "69948584"
---
# <a name="whats-new-for-direct-routing"></a>ダイレクト ルーティングの新機能

この記事では、ダイレクト ルーティングの新機能について説明します。 頻繁に更新プログラムを確認してください。

## <a name="new-direct-routing-sip-endpoints"></a>新しいダイレクト ルーティング SIP エンドポイント 

Microsoft では、Teams ダイレクト ルーティング SIP エンドポイントに新しいシグナリング IP を導入します。 この変更がサービスの可用性に影響しないようにするには、分類規則と ACL 規則に推奨サブネット 52.112.0.0/14 と 52.120.0.0/14 を使用するようにセッション ボーダー コントローラーとファイアウォールが構成されていることを確認します。 詳細については、「[Microsoft 365、Office 365、Office 365 GCC 環境](direct-routing-plan.md#microsoft-365-office-365-and-office-365-gcc-environments)」を参照してください。  

## <a name="trunk-demoting-logic-based-on-sip-options"></a>SIP オプションに基づくトランク降格ロジック

SIP オプションに基づく新しい機能がトランクの正常性に導入されました。 ゲートウェイ構成で有効にした場合 (Set-CsOnlinePSTNGateway コマンドレットと SendSipOptions パラメーターを参照)、送信呼び出しのルーティング ロジックは、SIP オプションを定期的に送信しないトランクを降格します (予想される期間は、SBC によって 1 分あたり 1 つの SIP オプションが送信されます)。 これらの降格されたトランクは、発信コールで使用可能なトランク リストの末尾に配置され、最後のトランクとして試行されます。これにより、呼び出しのセットアップ時間が短縮される可能性があります。
5 分以内に少なくとも 1 つの SIP オプションを Microsoft リージョン (NOAM、EMEA、APAC、OCEA) SIP プロキシに送信しないその機能に対して有効になっているトランクは、降格と見なされます。 トランクが Microsoft リージョン SIP プロキシのサブセットにのみ SIP オプションを送信する場合、これらのルートは最初に試行され、残りは降格されます。


## <a name="sip-support"></a>SIP サポート

2022 年 6 月 1 日に、Microsoft はダイレクト ルーティング構成から sip-all.pstnhub.microsoft.com と sip-all.pstnhub.gov.teams.microsoft.us FQDN のサポートを削除します。

6 月 1 日より前にアクションが実行されない場合、ユーザーはダイレクト ルーティングを介して通話を行ったり受信したりすることはできません。

サービスへの影響を防ぐには:

- 推奨されるサブネット (52.112.0.0/14 および 52.120.0.0/14) は、分類または ACL 規則に使用します。
- ダイレクト ルーティング用のセッション 境界制御を構成する場合は、sip-all FQDN の使用を中止します。

詳細については、「 [直接ルーティングを計画する](direct-routing-plan.md)」を参照してください。

## <a name="tls-certificates"></a>TLS 証明書

Microsoft 365 では、別のルート証明機関 (CA) のセットを使用するように Teams やその他のサービスを更新しています。

影響を受けるサービスの詳細と完全な一覧については、「 [Microsoft Teams を含む Microsoft 365 サービスへの TLS 証明書の変更](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/tls-certificate-changes-to-microsoft-365-services-including/ba-p/3249676)」を参照してください。

## <a name="certificate-authorities"></a>証明機関

2022 年 2 月 1 日から、ダイレクト ルーティング SIP インターフェイスは、Microsoft 信頼されたルート証明書プログラムの一部である証明機関 (CA) によって署名された証明書のみを信頼します。 サービスへの影響を回避するには、次の手順を実行します。

- SBC 証明書が、Microsoft 信頼されたルート証明書プログラムの一部である CA によって署名されていることを確認します。
- 証明書の拡張キー使用法 (EKU) 拡張機能に "サーバー認証" が含まれていることを確認します。

Microsoft 信頼されたルート証明書プログラムの詳細については、「 [プログラムの要件 - Microsoft 信頼されたルート プログラム](/security/trusted-root/program-requirements)」を参照してください。

信頼された CA の一覧については、「 [Microsoft Included CA Certificate List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)」を参照してください。

## <a name="replace-headers"></a>ヘッダーを置き換える

2022 年 4 月以降、ダイレクト ルーティングでは、Replaces ヘッダーが定義されている SIP 要求が拒否されます。 Microsoft が Replaces ヘッダーをセッション ボーダー コントローラー (SBC) に送信するフローに変更はありません。

SBC 構成を確認し、SIP 要求で置換ヘッダーを使用していないことを確認します。

## <a name="tls10-and-11"></a>TLS1.0 と 1.1

お客様にクラス最高の暗号化を提供するために、Microsoft はトランスポート層セキュリティ (TLS) バージョン 1.0 および 1.1 を非推奨にする予定です。 2022 年 4 月 3 日、Microsoft はダイレクト ルーティング SIP インターフェイスの TLS1.2 の使用を強制します。

サービスへの影響を回避するには、SBC が TLS1.2 をサポートするように構成されており、次のいずれかの暗号スイートを使用して接続できることを確認します。

- TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384すなわち ECDHE-RSA-AES256-GCM-SHA384
- TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256すなわち ECDHE-RSA-AES128-GCM-SHA256
- TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384すなわち ECDHE-RSA-AES256-SHA384
- TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256すなわち ECDHE-RSA-AES128-SHA256

## <a name="related-topics"></a>関連項目

- [ダイレクト ルーティング - SIP プロトコル](direct-routing-protocols-sip.md)
