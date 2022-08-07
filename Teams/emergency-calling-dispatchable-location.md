---
title: リモートの場所の緊急アドレス
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
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: 緊急通報をサポートするために、Microsoft がディスパッチ可能な位置情報をサポートする方法について説明します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9efa5f6e9ad5b5f2434efb95265f58c9a603fdd5
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2022
ms.locfileid: "67272072"
---
# <a name="emergency-addresses-for-remote-locations"></a>リモートの場所の緊急アドレス

この記事では、米国の 911 緊急通報場所情報に対する Microsoft のサポートについて説明します。 このサポートにより、可能な限り正確なディスパッチ可能な場所情報が、Teams ユーザーが緊急通報を行う際に提供されます。 呼び出し元の場所オンサイトまたは自宅からの作業に関係なく、パブリック セーフティ 応答ポイント (PSAP) に送信される発信者の位置情報は正確である必要があります。

この記事には、マルチライン電話システム (MLTS) に対する RAY BAUM 法への Microsoft の準拠に関する情報が含まれています。 RAY BAUM の法律は、2021 年初頭に発効した 卯法の要件を延長します。 RAY BAUM の法と 奔理の詳細については、「911 通話と複数行電話システム [のディスパッチ可能な場所](https://www.fcc.gov/911-dispatchable-location) [- 舘の法律と RAY BAUM の法 911 ダイレクト ダイヤル、通知、ディスパッチ可能な場所の要件」を](https://www.fcc.gov/mlts-911-requirements)参照してください。 

自宅で作業しているユーザーは、該当する場合は自分の緊急対応アドレスを設定できるようになりました。 この記事では、エンド ユーザーが緊急対応アドレスを設定できるようにユーザー ポリシーを構成する方法について説明します。

この情報は、米国の緊急 911 通話に適用されますが、ユーザーが入力した場所はカナダのスクリーニング センターにも伝達されます。

この記事には、次のセクションが含まれています。

- [緊急通報の場所情報のサポート](#support-for-emergency-calling-location-information)
- [場所の優先順位](#location-precedence)
- [緊急対応アドレスの分類とルーティング](#emergency-address-classification-and-routing)
- [エンド ユーザーが緊急対応アドレスを構成できるようにする](#enable-end-users-to-configure-their-emergency-address)
- [メモと制限](#notes-and-restrictions)


## <a name="support-for-emergency-calling-location-information"></a>緊急通報の場所情報のサポート

これらの要件をサポートするために、Teams は、それぞれのオペレーティング システムによって提供される位置情報サービスを使用して、アドレスを提案します。管理者またはユーザーからアクセス許可が付与されている場合。 エンド ユーザーは、提案されたアドレスの場所を確認したり、編集したり、新しいアドレスを手動で入力したりできます。 その後、確認済み、編集済み、または手動で入力されたアドレスが Teams クライアントに保存され、クライアントがそのネットワークに接続されたときにユーザーが確認したアドレスが自動的に使用されます。 ユーザーが保存したアドレスは、Teams クライアントがサインアウトされると自動的にクリアされます。


## <a name="location-precedence"></a>場所の優先順位

Teams の緊急対応アドレスは、さまざまな種類で分類できます。 次の一覧は、緊急電話番号がダイヤルされたときに使用される場所の優先順位を示しています。

1. 場所情報サービスで管理するテナントによって定義された動的に取得されたアドレス。

2. Teams クライアントが接続されているローカル ネットワークに関連付けられている、エンド ユーザーが確認、編集、または手動で入力したアドレス。

3. オペレーティング システムによって自動的に提案されるアドレス。

4. 管理者が静的にユーザーに割り当てるアドレス。


## <a name="emergency-address-classification-and-routing"></a>緊急対応アドレスの分類とルーティング

次の表は、各種類の緊急アドレスの種類と関連するルーティング方法を示しています。呼び出しがサービス PSAP に自動的にルーティングされるか、サービス PSAP に転送する前に精度が確認されるかを示します。 このルーティング動作は、すべての通話プラン ユーザー、オペレーター接続パートナー、およびダイレクト ルーティング認定緊急通話サービス プロバイダーの米国でサポートされています。


| 緊急対応アドレスの種類 | 緊急ルーティング方法 |
| :------------| :-------|
| 管理者によって定義された動的に取得された緊急アドレス。 | PSAP に直接接続します。 |
| ユーザーが **正確さを確認せずに** オペレーティング システムから取得した緊急アドレス。 | 画面が表示され、PSAP に転送されます。 |
| ユーザーが **正確さを確認** してオペレーティング システムから取得した緊急アドレス。| PSAP に直接接続します。 |
| オペレーティング システムから取得され、ユーザーによって編集および確認された緊急アドレス。 | 画面が表示され、PSAP に転送されます。 |
| ユーザーが入力して確認した緊急対応のアドレス。 | 画面が表示され、PSAP に転送されます。 |
| ユーザー/番号に静的に割り当てられた緊急対応アドレス。 | 画面が表示され、PSAP に転送されます。 |
| Null | 画面が表示され、PSAP に転送されます。 |


## <a name="enable-end-users-to-configure-their-emergency-address"></a>エンド ユーザーが緊急対応アドレスを構成できるようにする

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. Microsoft Teams 管理センターの左側のナビゲーションで、 **音声** > **緊急ポリシー** に移動します。
2. **[追加]** を選択します。
3. 緊急通報ポリシーの名前 ("E911WFH" など) を入力します。
4. **外部の場所の参照モード** を有効にします。
5. **[適用]** を選択します。

#### <a name="assign-a-custom-emergency-calling-policy-to-users"></a>ユーザーにカスタム緊急通報ポリシーを割り当てる

[!INCLUDE [assign-policy](includes/assign-policy.md)]

### <a name="using-powershell"></a>PowerShell の使用

エンド ユーザーに対してこの機能を有効にするには、New-CsTeamsEmergencyCallingPolicy PowerShell コマンドレットを使用し、ExternalLocationLookupMode パラメーターを Enabled に設定します。 次の例を参照してください。 


``` PowerShell
New-CsTeamsEmergencyCallingPolicy -Identity E911WFH -ExternalLocationLookupMode Enabled
```

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -PolicyName E911WFH -Identity user@contoso.com
```

エンド ユーザーに対してこの機能を有効にした後、[通話] タブから、緊急対応のアドレスを追加、編集、または確認し、設定後にアドレスを表示できます。 エンド ユーザーが位置情報サービスを設定する方法の詳細については、「 [Work from Home Emergency 911: ロケーション サービスを有効にする」を](https://support.microsoft.com/office/work-from-home-emergency-911-enable-location-services-583dd649-87fc-4b23-aed6-f4e2279297f9?storagetype=live)参照してください。

Windows では、グループ ポリシーを使用するか、 [モバイル デバイス管理 (MDM)](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesslocation) を使用して、Windows 位置情報サービスと、アプリケーションが場所にアクセスできるかどうかを管理できます。

Windows 位置情報サービスの詳細については、「 [Windows 位置情報サービスとプライバシー](https://support.microsoft.com/windows/windows-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)」を参照してください。



## <a name="notes-and-restrictions"></a>メモと制限

以下の点について留意してください。

- ここで説明する職場のエクスペリエンスは、Windows と Mac 上の Teams デスクトップ用です。

- Teams の電話では、自宅での職場でのエクスペリエンスはサポートされていません。

- Teams Mobile では、場所の自動検出がサポートされていますが、説明されているユーザー入力エクスペリエンスはサポートされていません。

- プライバシー設定は、場所の自動検出と競合する可能性があります。モバイル デバイス管理 システムを使用できます。


## <a name="related-topics"></a>関連項目

- [緊急通報を管理する](what-are-emergency-locations-addresses-and-call-routing.md)

- [自宅の緊急時 911 からの作業: 位置情報サービスを有効にする](https://support.microsoft.com/office/work-from-home-emergency-911-enable-location-services-583dd649-87fc-4b23-aed6-f4e2279297f9?storagetype=live)

