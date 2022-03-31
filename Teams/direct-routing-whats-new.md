---
title: 新しいダイレクト ルーティングの機能
ms.reviewer: CarolynRowe
author: wlibebe
ms.author: wlibebe
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: この記事では、ダイレクト ルーティングの新機能について説明します。 更新プログラムについては、頻繁に確認してください。
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b6f2ec21ec3e7f4278443d6bcab4b4220db3619f
ms.sourcegitcommit: cbdc80c302e97d18a923ef57bb5d4b6cf7676d00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/30/2022
ms.locfileid: "64556741"
---
# <a name="whats-new-for-direct-routing"></a>ダイレクト ルーティングの新機能

この記事では、ダイレクト ルーティングの新機能について説明します。 更新プログラムについては、頻繁に確認してください。

## <a name="sip-support"></a>SIP サポート

2022 年 6 月 1 日に、Microsoft は直接ルーティング構成から sip-all.pstnhub.microsoft.com FQDN sip-all.pstnhub.gov.teams.microsoft.us サポートを削除します。

6 月 1 日より前にアクションが実行されない場合、ユーザーは直接ルーティングを介して通話を行う、または受信できない。

サービスへの影響を防ぐには:

- 分類または ACL ルールには、推奨されるサブネット (52.112.0.0/14 および 52.120.0.0/14) を使用します。
- 直接ルーティングのセッション境界制御を構成するときに、sip-all FQDN の使用を中止します。

詳細については、「直接ルーティングを計画 [する」を参照してください](direct-routing-plan.md)。

## <a name="tls-certificates"></a>TLS 証明書

Microsoft 365、別Teamsルート証明機関 (CA) のセットを使用するために、他のサービスと他のサービスを更新しています。

影響を受けるサービスの詳細と完全な一覧については、「MICROSOFT 365 サービスに[対する TLS 証明書の変更」をMicrosoft Teams](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/tls-certificate-changes-to-microsoft-365-services-including/ba-p/3249676)。

## <a name="certificate-authorities"></a>証明書機関

2022 年 2 月 1 日より、ダイレクト ルーティング SIP インターフェイスは、Microsoft 信頼ルート証明書プログラムの一部である証明機関 (CA) によって署名された証明書のみを信頼します。 サービスへの影響を回避するには、次の手順を実行します。

- SBC 証明書が、Microsoft Trusted Root Certificate Program の一部である CA によって署名済みである必要があります。
- 証明書の拡張キー使用法 (EKU) 拡張機能に "サーバー認証" が含まれるか確認します。

Microsoft 信頼されたルート証明書プログラムの詳細については、「プログラム要件 [- Microsoft 信頼されたルート プログラム」を参照してください](/security/trusted-root/program-requirements)。

信頼できる CA の一覧については、「 [Microsoft Included CA Certificate List(Microsoft Included CA Certificate List(Microsoft 含まれる CA 証明書の一覧)」を参照してください](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)。

## <a name="replace-headers"></a>ヘッダーを置き換える

2022 年 4 月より、ダイレクト ルーティングは、Replaces ヘッダーが定義されている SIP 要求を拒否します。 Microsoft が Replaces ヘッダーをセッション ボーダー コントローラー (SBC) に送信するフローに変更はありません。

SBC 構成を確認し、SIP 要求で Replaces ヘッダーが使用されていないことを確認します。

## <a name="tls10-and-10"></a>TLS1.0 および 1.0

お客様にクラス最高の暗号化を提供するために、Microsoft はトランスポート層セキュリティ (TLS) バージョン 1.0 および 1.1 を非推奨にする予定です。 2022 年 4 月 3 日に、Microsoft はダイレクト ルーティング SIP インターフェイスに TLS1.2 の使用を強制します。

サービスへの影響を回避するには、SBC が TLS1.2 をサポートするように構成され、次のいずれかの暗号スイートを使用して接続できる必要があります。

- TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384 i.e. ECDHE-RSA-AES256-GCM-SHA384
- TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256 i.e. ECDHE-RSA-AES128-GCM-SHA256
- TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384(ECDHE-RSA-AES256-SHA384)
- TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256(ECDHE-RSA-AES128-SHA256)

## <a name="related-topics"></a>関連項目

- [ダイレクト ルーティング - SIP プロトコル](direct-routing-protocols-sip.md)
