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
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 53a1c2730ebf6db06fb92ac2fc4e0873563c98ce
ms.sourcegitcommit: 9e868a155bcd20dd5dafdedcff091ff77ca7398b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2022
ms.locfileid: "64584331"
---
# <a name="whats-new-for-direct-routing"></a>ダイレクト ルーティングの新機能

この記事では、ダイレクト ルーティングの新機能について説明します。 更新プログラムを頻繁に確認してください。

## <a name="sip-support"></a>SIP サポート

2022 年 6 月 1 日に、Microsoft はダイレクト ルーティング構成から sip-all.pstnhub.microsoft.com および sip-all.pstnhub.gov.teams.microsoft.us FQDN のサポートを削除します。

6 月 1 日より前にアクションが実行されない場合、ユーザーはダイレクト ルーティングを介して通話を発信または受信できなくなります。

サービスへの影響を防ぐには、

- 推奨されるサブネット (52.112.0.0/14 および 52.120.0.0/14) を任意の分類ルールまたは ACL ルールに使用します。
- ダイレクト ルーティング用にセッション 罫線コントロールを構成するときに、sip-all FQDN の使用を中止します。

詳細については、「 [直接ルーティングを計画する](direct-routing-plan.md)」を参照してください。

## <a name="tls-certificates"></a>TLS 証明書

Microsoft 365は、別のルート証明機関 (CA) のセットを使用するようにTeamsおよびその他のサービスを更新しています。

影響を受けるサービスの詳細と完全な一覧については、「[Microsoft Teamsを含むMicrosoft 365 サービスに対する TLS 証明書の変更](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/tls-certificate-changes-to-microsoft-365-services-including/ba-p/3249676)」を参照してください。

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
