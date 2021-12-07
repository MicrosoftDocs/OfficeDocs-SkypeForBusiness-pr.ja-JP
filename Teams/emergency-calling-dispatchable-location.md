---
title: リモートの場所の緊急対応の住所
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: Microsoft が緊急通話をサポートするディスパッチ可能な位置情報をサポートする方法について説明します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7d241cee858d3ac19747be56b5a53e157b563f64
ms.sourcegitcommit: 05e7c8ac9d6d6f712742d08820d43118c8949bbc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/07/2021
ms.locfileid: "61323002"
---
# <a name="emergency-addresses-for-remote-locations"></a>リモートの場所の緊急対応の住所

この記事では、米国での 911 緊急通話の場所情報に対する Microsoft のサポートについて説明します。 このサポートにより、緊急通話を行うユーザーに対して、可能な限り正確なディスパッチ可能Teams情報が提供されます。 発信者の場所 (オンサイトまたは自宅での作業) に関係なく、公衆安全応答ポイント (PSAP) に送信される発信者の位置情報は正確である必要があります。

この記事では、MICROSOFT が RAY BAUM のマルチライン電話システム (MLTS) に対する法令遵守に関する情報を提供します。 RAY BAUM'S Act は、2021 年初めに有効にされた 、 、 、 Law の要件を拡張します。 RAY BAUM の法律と カミの法律の詳細については [、「911](https://www.fcc.gov/911-dispatchable-location) 通話のディスパッチ可能な場所」および「複数回線電話システム – はい法」および [「RAY BAUM の法律 911 ダイレクト](https://www.fcc.gov/mlts-911-requirements)ダイヤル、通知、ディスパッチ可能な場所の要件」を参照してください。 

自宅で作業しているユーザーは、該当する場合に自分の緊急対応の住所を設定できます。 この記事では、エンド ユーザーが緊急対応の住所を設定できるようユーザー ポリシーを構成する方法について説明します。

この情報は米国での緊急 911 通話に適用されます。ただし、ユーザーが入力した場所はカナダのスクリーニング センターにも伝達されます。

この記事では、次のセクションについて説明します。

- [緊急通話の場所情報のサポート](#support-for-emergency-calling-location-information)
- [場所の優先順位](#location-precedence)
- [緊急対応の住所の分類とルーティング](#emergency-address-classification-and-routing)
- [エンド ユーザーが緊急対応の住所を構成できる](#enable-end-users-to-configure-their-emergency-address)
- [注意事項と制限事項](#notes-and-restrictions)


## <a name="support-for-emergency-calling-location-information"></a>緊急通話の場所情報のサポート

これらの要件をサポートするために、Teams は、それぞれのオペレーティング システムによって提供される位置情報サービスを使用して、管理者またはユーザーがアクセス許可を付与した場合にアドレスを提案します。 エンド ユーザーは、提案された住所の場所の確認、編集、または新しい住所の手動入力を行うことができます。 その後、確認済み、編集済み、または手動で入力されたアドレスが Teams クライアントに保存され、クライアントがネットワークに接続されると、ユーザーが確認したアドレスが自動的に使用されます。 ユーザーが保存したアドレスは、クライアントがサインアウトTeams自動的にクリアされます。


## <a name="location-precedence"></a>場所の優先順位

ユーザーの緊急対応Teamsは、さまざまな種類で分類できます。 次の一覧は、緊急電話番号をダイヤルするときに使用される場所の優先順位を示しています。

1. Location Information Service で管理するテナントによって定義された動的に取得されたアドレス。

2. エンド ユーザーが確認、編集、または手動で入力したアドレス。これは、クライアントが接続されているローカル ネットワークTeams関連付けられているアドレスです。

3. オペレーティング システムによって自動的に提案されるアドレス。

4. 管理者が静的にユーザーに割り当てるアドレス。


## <a name="emergency-address-classification-and-routing"></a>緊急対応の住所の分類とルーティング

次の表は、各種類の緊急対応の住所と関連するルーティング方法を示しています。呼び出しがサービス PSAP に自動的にルーティングされるかどうか、またはサービス PSAP に転送する前に正確さを確認するために画面に表示されます。 このルーティング動作は、米国内のすべての通話プラン ユーザー、オペレーター Connect パートナー、ダイレクト ルーティング認定緊急通話サービス プロバイダーでサポートされています。


| 緊急対応の住所の種類 | 緊急ルーティング方法 |
| :------------| :-------|
| 管理者によって定義された動的に取得された緊急対応のアドレス。 | PSAP に直接接続します。 |
| ユーザーによる正確性の確認なしでオペレーティング システム **から取得した** 緊急対応の住所。 | 画面が表示され、PSAP に転送されます。 |
| ユーザーによる正確さを確認してオペレーティング システム **から取得した** 緊急対応の住所。| PSAP に直接接続します。 |
| オペレーティング システムから取得し、ユーザーによって編集および確認された緊急対応の住所。 | 画面が表示され、PSAP に転送されます。 |
| ユーザーが入力して確認した緊急対応の住所。 | 画面が表示され、PSAP に転送されます。 |
| ユーザー/番号に静的に割り当てられた緊急対応の住所。 | 画面が表示され、PSAP に転送されます。 |
| Null | 画面が表示され、PSAP に転送されます。 |


## <a name="enable-end-users-to-configure-their-emergency-address"></a>エンド ユーザーが緊急対応の住所を構成できる

エンド ユーザーに対してこの機能を有効にするには、New-CsTeamsEmergencyCallingPolicy PowerShell コマンドレットを使用し、ExternalLocationLookupMode パラメーターを [有効] に設定します。 次の例を参照してください。 


``` PowerShell
New-CsTeamsEmergencyCallingPolicy -Identity E911WFH -ExternalLocationLookupMode Enabled
```

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -PolicyName E911WFH -Identity user@contoso.com
```

エンド ユーザーに対してこの機能を有効にした後、[通話] タブから、緊急対応の住所を追加、編集、または確認し、設定後に住所を表示できます。 

このWindows、Windows 場所サービスを管理できます。また、アプリケーションが場所にアクセスできるかどうかは、グループ ポリシーを使用するか、モバイル デバイス管理[(MDM)](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesslocation)を使用して管理できます。

位置情報サービスの詳細についてはWindows位置情報サービスとプライバシーに関Windows[を参照してください](https://support.microsoft.com/windows/windows-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)。



## <a name="notes-and-restrictions"></a>注意事項と制限事項

以下の点について留意してください。

- 説明されている在宅作業環境は、Teams Mac Windowsデスクトップ向けです。

- Teamsは、在宅作業をサポートしません。

- Teamsでは、場所の自動検出はサポートされますが、説明されているユーザー入力エクスペリエンスはサポートされません。

- プライバシー設定は、場所の自動検出と競合する可能性があります。モバイル デバイス管理システムを使用できます。


## <a name="related-topics"></a>関連トピック

[緊急通話を管理する](what-are-emergency-locations-addresses-and-call-routing.md)

