---
title: 動的な緊急通話を構成する
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: roykuntz
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
description: Microsoft 通話プランと電話システムダイレクト ルーティングの動的緊急通話機能を構成する方法について説明します。
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2531add2b43b7061b81a23676c54fbc557929c0f
ms.sourcegitcommit: 2ce82f301f2d59da57f579a23038b2cab5e31360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2021
ms.locfileid: "51858010"
---
# <a name="plan-and-configure-dynamic-emergency-calling"></a>動的な緊急通話を計画して構成する 

Microsoft 通話プランと電話システムダイレクト ルーティングの動的緊急通話は、Teams クライアントの現在の場所に基づいて緊急通話を構成およびルーティングし、セキュリティ担当者に通知する機能を提供します。  

テナント管理者が定義するネットワーク トポロジに基づいて、Teams クライアントは Location Information Service (LIS) への要求でネットワーク接続情報を提供します。 一致する値がある場合、LIS はクライアントに場所を返します。 この場所のデータは、クライアントに送信されます。  

Teams クライアントには、緊急通話の一部として場所データが含まれます。 このデータは、緊急サービス プロバイダーによって適切なパブリック セーフティ応答ポイント (PSAP) を決定し、その PSAP に通話をルーティングするために使用されます。これにより、PSAP ディスパッチャーは呼び出し元の場所を取得できます。  

動的緊急通話の場合は、次の処理を行う必要があります。

1. ネットワーク管理者がネットワーク設定と LIS を構成して、ネットワーク/緊急対応の場所マップを作成します。

   直接ルーティングの場合、緊急通話をルーティングする場合や、パートナー接続の場合は追加の構成が必要です。 管理者は、緊急ルーティング サービス (ERS) プロバイダー ( **米国)** への接続を構成するか、緊急位置情報識別番号 (ELIN) アプリケーションのセッション ボーダー コントローラー (SBC) を構成する必要があります。

2. 起動中および定期的に、またはネットワーク接続が変更された場合、Teams クライアントはネットワーク接続情報を含む場所要求をネットワーク設定と LIS に送信します。

   - ネットワーク設定サイトが一致する場合–緊急通話ポリシーは、そのサイトから Teams クライアントに返されます。 (ポリシーの詳細については、「緊急ポリシーを構成する [」を参照してください](#configure-emergency-policies))。

   - LIS が一致する場合は、Teams クライアントが接続されているネットワーク要素からの緊急対応の場所が Teams クライアントに返されます。 一致は次の順序で実行され、最初に一致した結果が返されます。
       - (1)
       - イーサネット スイッチ/ポート
       - イーサネット スイッチ
       - サブネット

3. Teams クライアントが緊急通話を行う場合、緊急対応の場所は PSTN ネットワークに伝達されます。

   直接ルーティングの場合、管理者は緊急通話を ERS プロバイダーに送信するか、SBC ELIN アプリケーションを構成するために SBC を構成する必要があります。

この記事では、次のセクションについて説明します。

- [緊急対応の住所を構成する](#assign-emergency-addresses)
- [ネットワーク設定を構成する](#configure-network-settings)
- [位置情報サービスを構成する](#configure-location-information-service)
- [緊急ポリシーを構成する](#configure-emergency-policies)
- [ユーザーとサイトを有効にする](#enable-users-and-sites)
- [緊急通話をテストする](#test-emergency-calling)

適切なパブリック セーフティ応答ポイント (PSAP) に自動ルーティングを実行する機能は、Teams ユーザーの使用国によって異なります。

緊急通話の詳細 (緊急対応の住所と緊急通話ルーティングに関する情報、国固有の情報、ネットワーク設定とネットワーク トポロジに関する情報など) については、次を参照してください。

- [緊急通話を管理する](what-are-emergency-locations-addresses-and-call-routing.md)
- [クラウド音声機能のネットワーク設定を管理する](cloud-voice-network-settings.md)
- [クラウド ボイス機能のネットワーク トポロジを管理する](manage-your-network-topology.md)

政府機関向けクラウドで利用できる機能の詳細については、この記事の[](#government-support)最後にある政府機関向けサポートを参照してください。


## <a name="supported-clients"></a>サポートされるクライアント

現在、次のクライアントがサポートされています。  この一覧の更新プログラムを確認するには、頻繁に確認してください。

- Microsoft Windows 用 Teams デスクトップ クライアント
- Apple macOS 用 Teams デスクトップ クライアント
- Apple iOS クライアント バージョン 1.0.92.2019121004 および App Store バージョン 1.0.92 以上用の Teams モバイル クライアント
- Android クライアントおよび Google Play ストア バージョン 1416/1.0.0.2019121201 以上用の Teams モバイル クライアント
- Teams の電話バージョン 1449/1.0.94.2019110802 以上
- Teams Rooms バージョン 4.4.25.0 以上

> [!NOTE]
> セキュリティ デスク通知を含む動的緊急通話は、Teams Web クライアントではサポートされていません。 ユーザーが Teams Web クライアントを使用して PSTN 番号を呼び出すのを防ぐために、Teams 通話ポリシーを設定し、[Web PSTN 通話を許可する] **設定をオフ** にします。 詳細については [、「Teams](teams-calling-policy.md) および [Set-CsTeamsCallingPolicy の通話ポリシー」を参照してください](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)。

## <a name="assign-emergency-addresses"></a>緊急対応の住所を割り当てる

通話プランのユーザーと、場所を動的に取得するために必要なネットワーク識別子の両方に緊急対応の住所を割り当てできます。 (サブネットと WiFi AP はサポートされています。 イーサネット スイッチ/ポートは、現時点では Windows 8.1 以降でサポートされています)。

米国内での緊急通話の自動ルーティングをサポートするには、ネットワーク識別子に割り当てられている緊急対応の場所に関連する地域コードが含まれる必要があります。 (地域コードのない緊急対応の住所は、動的な場所に必要なネットワーク識別子に割り当てできません)。

Azure Maps は、場所ベースのサービスに使用されます。  Microsoft Teams 管理センターを使用して緊急対応の住所を入力すると、Teams は Azure Maps で住所を確認します。

- 一致が見つかると、地理コードが自動的に含まれます。

- 一致が見つからない場合は、緊急対応の住所を手動で作成することができます。 PIN ドロップ機能を使って、この操作を行います。 

つまり、通話プランのユーザーに割り当てのために作成された既存の緊急対応の場所が動的な場所を対象としている場合、地域コードを含めるには、同じ住所を再作成する必要があります。 2 つの場所を区別するには、別の説明を含める必要があります。 新しい緊急対応の場所は、古い場所を持つユーザーに割り当てることができます。 完全に移行すると、古い場所を削除できます。

Microsoft Teams 管理センターで緊急対応の住所を追加して割り当てるには、PowerShell を使用します。 詳細については、「組織の緊急対応の場所を追加 [する」](add-change-remove-emergency-location-organization.md) および「ユーザーに緊急対応の場所を割り当てる [」を参照してください](assign-change-emergency-location-user.md)。

## <a name="configure-network-settings"></a>ネットワーク設定を構成する

ネットワーク設定は、Teams クライアントの場所を決定し、緊急通話ポリシーと緊急対応の場所を動的に取得するために使用されます。 組織が緊急通話の機能を求める方法に応じて、ネットワーク設定を構成できます。

ネットワーク設定には、サブネットのコレクションを含むサイトが含まれます。これらはユーザーへの動的ポリシー割り当て専用に使用されます。 たとえば、緊急通話ポリシーと緊急通話ルーティング ポリシーを "レドモンド サイト" に割り当てると、自宅または別の Microsoft の場所からローミングするユーザーが、レドモンド固有の緊急電話番号、ルーティング、セキュリティ デスクで構成されます。  

>[!Note]
>また、サブネットは LIS で定義し、緊急対応の場所に関連付けできます。  

次の定義を念頭に置きます。 詳細については、「クラウド音声機能 [のネットワーク設定」を参照してください](cloud-voice-network-settings.md)。

- 信頼済み IP アドレスには、エンタープライズ ネットワークのインターネット外部 IP アドレスのコレクションが含まれているので、ユーザーのエンドポイントが企業ネットワーク内にあるかどうかを判断するために使用されます。 動的ポリシーまたは場所の取得は、ユーザーの外部 IP アドレスが信頼済み IP アドレスの IP アドレスと一致する場合にのみ行います。 一致は IPv4 または IPv6 IP アドレスに対して行い、ネットワーク設定に送信される IP パケットの形式に依存します。  (パブリック IP アドレスに IPv4 と IPv6 の両方がある場合は、両方を信頼済み IP アドレスとして追加する必要があります)。

- ネットワーク地域にはネットワーク サイトのコレクションが含まれます。 

- ネットワーク サイトは、オフィス、建物のセット、キャンパスなど、組織が物理的な価値を持つ場所を表します。 これらのサイトは、IP サブネットのコレクションとして定義されます。

- ネットワーク サブネットは、特定のネットワーク サイトに関連付けられている必要があります。 クライアントの場所は、ネットワーク サブネットと関連するネットワーク サイトに基づいて決定されます。  

Microsoft Teams 管理センターで、または PowerShell を使用してネットワーク設定を構成します。 詳細については、「クラウド音声 [機能のネットワーク トポロジを管理する」を参照してください](manage-your-network-topology.md)。

ネットワーク設定の変更 (新しいアドレス、ネットワーク識別子など) が反映され、Teams クライアントで使用可能になるには、時間がかかることがあります (最大で数時間)。  

**通話プランのユーザーの場合:**

- セキュリティ デスク通知の動的構成が必要な場合は、信頼できる IP アドレスとネットワーク サイトの両方を構成する必要があります。

- 動的な場所だけが必要な場合は、信頼できる IP アドレスのみを構成する必要があります。

- どちらも必要ない場合は、ネットワーク設定を構成する必要はありません。 

**直接ルーティング ユーザーの場合:**

- 緊急通話の動的有効化またはセキュリティ デスク通知の動的構成が必要な場合は、信頼済み IP アドレスとネットワーク サイトの両方を構成する必要があります。

- 動的な場所だけが必要な場合は、信頼できる IP アドレスのみを構成する必要があります。

- どちらも必要ない場合は、ネットワーク設定を構成する必要はありません。


## <a name="configure-location-information-service"></a>位置情報サービスを構成する

Teams クライアントは、異なるネットワーク識別子に関連付けられている場所から緊急対応の住所を取得します。 サブネットとワイヤレス アクセス ポイント (WAP) の両方がサポートされます。 イーサネット スイッチ/ポートは、現時点では Windows 8.1 以降でサポートされています。

クライアントが場所を取得するには、ネットワーク識別子 (サブネット、WAP、スイッチ、ポート) と緊急対応の場所を LIS に入力する必要があります。 これは、Microsoft Teams 管理センターまたは PowerShell を使用して行います。

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. 左側のナビゲーションで、[**場所ネットワーク**] に  >  **移動&します**。
2. 追加するネットワーク識別子を表すタブをクリックします。 たとえば、[サブネット **]、[Wi-Fi アクセス ポイント]、[****スイッチ]、** または [ポート] を **クリックします**。  次に、[追加] を **クリックします**。
3. フィールドに入力し、緊急対応の場所を追加して、[適用] を **クリックします**。

### <a name="using-powershell"></a>PowerShell の使用

次のコマンドレットを使用して、ポート、スイッチ、サブネット、WAP を LIS に追加します。

- [取得](/powershell/module/skype/get-csonlinelissubnet?view=skype-ps)、[設定、](/powershell/module/skype/set-csonlinelissubnet?view=skype-ps)[削除](/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps)-CsOnlineLisSubnet
- [取得](/powershell/module/skype/get-csonlinelisport?view=skype-ps)、[設定、](/powershell/module/skype/set-csonlinelisport?view=skype-ps)[削除](/powershell/module/skype/remove-csonlinelisport?view=skype-ps)-CsOnlineLisPort
- [取得](/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps)、[設定、](/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps)[削除](/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps)-CsOnlineLisWirelessAccessPoint
- [取得](/powershell/module/skype/get-csonlinelisswitch?view=skype-ps)、[設定、](/powershell/module/skype/set-csonlinelisswitch?view=skype-ps)[削除](/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps)-CsOnlineLisSwitch

>[!Important]
>サブネットがネットワーク サイトの一部として使用されている場合、動的な場所を表示するには、Location Information Service でサブネットを再定義する必要があります。

## <a name="configure-emergency-policies"></a>緊急ポリシーを構成する

次のポリシーを使用して、緊急通話を構成します。 これらのポリシーは、Microsoft Teams 管理センターまたは PowerShell を使用して管理できます。

- **緊急通話ルーティング ポリシー** – ダイレクト ルーティングにのみ適用されます。 このポリシーは、緊急電話番号、必要に応じて番号ごとのマスク、番号ごとの PSTN ルートを構成します。  このポリシーは、ユーザー、ネットワーク サイト、または両方に割り当てできます。 (通話プラン Teams クライアントは、Microsoft 365 または Office 365 の使用場所に基づいて、国からの緊急電話番号での緊急通話に対して自動的に有効になります)。 詳細については、「ダイレクト ルーティングの [緊急通話ルーティング ポリシーを管理する」を参照してください](manage-emergency-call-routing-policies.md)。

- **緊急通話ポリシー** - 通話プランとダイレクト ルーティングに適用されます。 このポリシーは、緊急通話が行われた場合のセキュリティ デスク通知エクスペリエンスを構成します。 通知するユーザーと通知方法を設定できます。 たとえば、組織のセキュリティ デスクに自動的に通知し、緊急通話を聞く場合などです。  このポリシーは、ユーザーまたはネットワーク サイト、または両方に割り当てることができます。 詳細については、「Teams で緊急 [通話ポリシーを管理する」を参照してください](manage-emergency-calling-policies.md)。

## <a name="enable-users-and-sites"></a>ユーザーとサイトを有効にする

緊急通話ルーティング ポリシーと緊急通話ポリシーをユーザーとサイトに割り当てできます。 緊急通話ルーティング ポリシーは、ダイレクト ルーティングにのみ適用されます。 (このポリシーを通話プラン ユーザーに割り当て可能ですが、ポリシーは影響しません)。

Microsoft Teams 管理センターで、または PowerShell を使用してポリシーを割り当てる。 詳細については、次を参照してください。

- [ダイレクト ルーティングの緊急通話ルーティング ポリシーを管理する](manage-emergency-call-routing-policies.md)
- [Teams で緊急通話ポリシーを管理する](manage-emergency-calling-policies.md)

PowerShell の例を次に示します。

特定のユーザーにセキュリティ デスク通知を有効にするには、次のコマンドを使用します。

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

"Contoso 緊急通話ポリシー 1" というポリシーをサイト 1 に割り当てるには、次のコマンドを使用します。

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

特定のダイレクト ルーティング ユーザーによる緊急通話を有効にするには、次のコマンドを使用します。

```PowerShell
Grant-CsTeamsEmergencyCallRoutingPolicy -Identity user1 -PolicyName UnitedStates
```

"Contoso New York 緊急通話ルーティング" というポリシーをサイト 1 に割り当てるには、次のコマンドを使用します。

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Contoso New York Emergency Call Routing"
```

ネットワーク サイトとユーザーに緊急通話ポリシーを割り当て、そのユーザーがネットワーク サイトにある場合、ネットワーク サイトに割り当てられているポリシーは、ユーザーに割り当てられているポリシーを上書きします。

## <a name="test-emergency-calling"></a>緊急通話をテストする

米国の一部の緊急ルーティング サービス プロバイダー (ERSP) は、緊急通話テスト ボットを提供しています。

- **米国の通話プラン ユーザー** は、事前に定義されたテスト緊急電話番号 933 を使用して、緊急通話の構成を検証できます。 この番号はボットにルーティングされ、発信者番号 (通話回線 ID)、緊急対応の住所または場所、通話が自動的に PSAP にルーティングされるかどうか、または最初に表示されるかどうかがエコーされます。

- **米国のダイレクト ルーティングのお客様は、** テスト サービスのために ERSP と調整する必要があります。

## <a name="government-support"></a>政府機関のサポート

次の表は、政府クラウドでの動的緊急通話のサポートを示しています。

| クラウド | 使用するための条件 |
| :------------|:-------|
| World Wide Multi Tenant | すべての Teams クライアントで利用可能 |
| GCC | すべての Teams クライアントで利用可能 |
| GCCH | Teams デスクトップで利用可能 |
| DoD | Pending |

 ## <a name="related-topics"></a>関連項目

- [緊急通話を管理する](what-are-emergency-locations-addresses-and-call-routing.md)
- [緊急通話ポリシーを管理する](manage-emergency-calling-policies.md)
- [緊急通話ルーティング ポリシーを管理する ](manage-emergency-call-routing-policies.md)
- [組織の緊急対応の場所を追加、変更、削除する](add-change-remove-emergency-location-organization.md)
- [ユーザーの緊急対応の場所を割り当てる、または変更する](assign-change-emergency-location-user.md)
- [クラウド ボイス機能のネットワーク設定](cloud-voice-network-settings.md)
- [クラウド ボイス機能のネットワーク トポロジを管理する](manage-your-network-topology.md)