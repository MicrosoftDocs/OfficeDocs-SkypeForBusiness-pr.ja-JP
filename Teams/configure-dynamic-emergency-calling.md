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
description: Microsoft 通話プランと直接ルーティングの動的緊急通話機能電話システムを構成する方法について説明します。
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5454eff6e09e923a6db8de1ba8c9e9fe47c3f0f2
ms.sourcegitcommit: 5c68298474d1782e69bde8c0940be7150cb93f6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2021
ms.locfileid: "53096311"
---
# <a name="plan-and-configure-dynamic-emergency-calling"></a>動的な緊急通話を計画して構成する 

Microsoft 通話プランと 電話システム ダイレクト ルーティングの動的緊急通話は、緊急通話を構成してルーティングし、Teams クライアントの現在の場所に基づいてセキュリティ担当者に通知する機能を提供します。  

テナント管理者が定義するネットワーク トポロジに基づいて、Teams クライアントは Location Information Service (LIS) への要求でネットワーク接続情報を提供します。 一致する場合、LIS はクライアントに場所を返します。 この場所データはクライアントに送信されます。  

クライアントTeams、緊急通話の一部として場所データが含まれます。 このデータは、緊急サービス プロバイダーによって適切なパブリック セーフティ応答ポイント (PSAP) を決定し、その PSAP に呼び出しをルーティングするために使用されます。これにより、PSAP ディスパッチャーは呼び出し元の場所を取得できます。  

動的緊急通話の場合は、次の処理を行う必要があります。

1. ネットワーク管理者は、ネットワーク設定と LIS を構成して、ネットワーク/緊急の場所マップを作成します。

   直接ルーティングの場合、緊急通話をルーティングするために、および場合によってはパートナーの接続に追加の構成が必要です。 管理者は、緊急ルーティング サービス (ERS) プロバイダー ( **米国)** への接続を構成するか、緊急位置情報識別番号 (ELIN) アプリケーションのセッション ボーダー コントローラー (SBC) を構成する必要があります。

2. 起動中、または後で定期的に、またはネットワーク接続が変更された場合、Teams クライアントは、ネットワーク接続情報を含む場所要求をネットワーク設定と LIS に送信します。

   - ネットワーク設定サイトの一致がある場合–緊急通話ポリシーは、そのサイトからTeamsクライアントに返されます。 (ポリシーの詳細については、「緊急ポリシーを [構成する」を参照してください](#configure-emergency-policies))。

   - LIS が一致する場合は、Teams クライアントが接続されているネットワーク要素からの緊急対応の場所が、Teamsされます。 一致は次の順序で実行され、最初に一致した結果が返されます。
       - WAP
       - イーサネット スイッチ/ポート
       - イーサネット スイッチ
       - サブネット

3. クライアントがTeamsを発信すると、緊急対応の場所が PSTN ネットワークに伝達されます。

   直接ルーティングの場合、管理者は ERS プロバイダーに緊急通話を送信するか、SBC ELIN アプリケーションを構成するために SBC を構成する必要があります。

この記事では、次のセクションについて説明します。

- [緊急対応の住所を構成する](#assign-emergency-addresses)
- [ネットワーク設定を構成する](#configure-network-settings)
- [Location Information Service の構成](#configure-location-information-service)
- [緊急ポリシーを構成する](#configure-emergency-policies)
- [ユーザーとサイトを有効にする](#enable-users-and-sites)
- [緊急通話をテストする](#test-emergency-calling)

適切な Public Safety Answering Point (PSAP) への自動ルーティングを実行する機能は、ユーザーが使用する国によってTeamsされます。

緊急通話の詳細 (緊急対応の住所と緊急通話のルーティングに関する情報、国固有の情報、ネットワーク設定とネットワーク トポロジに関する情報など) については、次を参照してください。

- [緊急通話を管理する](what-are-emergency-locations-addresses-and-call-routing.md)
- [クラウド音声機能のネットワーク設定を管理する](cloud-voice-network-settings.md)
- [クラウド ボイス機能のネットワーク トポロジを管理する](manage-your-network-topology.md)

政府機関向けクラウドで使用できる機能の詳細については、この記事の最後にある「 [政府機関](#government-support) 向けサポート」を参照してください。


## <a name="supported-clients"></a>サポートされるクライアント

現在、次のクライアントがサポートされています。  この一覧の更新を確認するには、頻繁に確認してください。

- Teams用のデスクトップ クライアントWindows
- Teams Apple macOS 用デスクトップ クライアント
- Teams iOS クライアント バージョン 1.0.92.2019121004 および App Store バージョン 1.0.92 以上のモバイル クライアント
- Teams Android クライアントおよび Google Play ストア バージョン 1416/1.0.0.2019121201 以上のモバイル クライアント
- Teamsバージョン 1449/1.0.94.2019110802 以上
- Teams ミーティングバージョン 4.4.25.0 以上

> [!NOTE]
> セキュリティ デスク通知を含む動的緊急通話は、Web クライアントTeamsサポートされていません。 ユーザーが Teams Web クライアントを使用して PSTN 番号を呼び出すのを防ぐには、Teams 通話ポリシーを設定し、[Web PSTN 通話を許可する] 設定 **をオフ** にします。 詳細については、「Teams でのポリシーの呼び出し」[と](teams-calling-policy.md)[「Set-CsTeamsCallingPolicy」を参照してください](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)。 

> [!NOTE]
> サブネットと WiFi ベースの場所は、すべてのクライアントでTeamsされます。 <br>
> イーサネット/スイッチ (LLDP) は Windows でのみサポートされ、現時点では Windows バージョン 8.1 以降でのみサポートされます。

## <a name="assign-emergency-addresses"></a>緊急対応の住所を割り当てる

緊急対応の住所は、通話プランのユーザーと、場所を動的に取得するために必要なネットワーク識別子の両方に割り当て可能です。 (サブネットと WiFi AP はサポートされています。 イーサネット スイッチ/ポートは、Windows 8.1以降でサポートされます)。

米国内での緊急通話の自動ルーティングをサポートするには、ネットワーク識別子に割り当てられている緊急対応の場所に、関連する geo コードが含まれる必要があります。 (geo コードのない緊急対応の住所は、動的な場所に必要なネットワーク識別子に割り当てできません)。

Azure マップは、場所ベースのサービスに使用されます。  管理センターで緊急対応の住所を入力Microsoft Teams、Azure Teamsアドレスマップ確認できます。

- 一致が見つかった場合は、geo コードが自動的に含まれます。

- マッチが見つからない場合は、緊急対応の住所を手動で作成できます。 PIN ドロップ機能を使用してこれを行います。 

つまり、通話プランのユーザーに割り当てのために作成された既存の緊急対応の場所が動的な場所を対象とする場合、geo コードを含めるには同じ住所を再作成する必要があります。 2 つの場所を区別するには、別の説明を含める必要があります。 新しい緊急対応の場所は、古い場所を持つユーザーに割り当てることができます。 完全に移行すると、古い場所を削除できます。

管理者センターまたは PowerShell を使用して、Microsoft Teams緊急対応の住所を追加して割り当てる。 詳細については、「組織の緊急対応 [の場所を](add-change-remove-emergency-location-organization.md) 追加する」および「ユーザーの緊急対応 [の場所を割り当てる」を参照してください](assign-change-emergency-location-user.md)。

## <a name="configure-network-settings"></a>ネットワーク設定を構成する

ネットワーク設定は、クライアントの場所を特定しTeams、緊急通話ポリシーと緊急対応の場所を動的に取得するために使用されます。 組織が緊急通話を機能する方法に応じて、ネットワーク設定を構成できます。

ネットワーク設定には、サブネットのコレクションを含むサイトが含まれます。これらは、ユーザーへの動的ポリシーの割り当て専用に使用されます。 たとえば、緊急通話ポリシーと緊急通話ルーティング ポリシーを "Redmond サイト" に割り当て、自宅または別の Microsoft の場所からローミングするユーザーが、Redmond に固有の緊急電話番号、ルーティング、セキュリティ デスクで構成されます。  

> [!Note]
> サブネットは LIS で定義し、緊急対応の場所に関連付けできます。  LIS サブネットは、クライアントに割り当てられたサブネット IP 範囲と一致するネットワーク ID で定義する必要があります。 たとえば、10.10.10.150/25 のクライアント IP/マスクのネットワーク ID は **10.10.10.128** です。 詳細については [、TCP/IP アドレス指定とサブネット化の基本に関するページを参照してください](/troubleshoot/windows-client/networking/tcpip-addressing-and-subnetting)。

> [!Important]
> ネットワーク構成設定の参照は、クラウド プロキシ サービスのデプロイではサポートされていません。このデプロイでは、クライアントからソース IP アドレスTeamsされます。

次の定義を念頭に置きます。 詳細については、「クラウド音声機能 [のネットワーク設定」を参照してください](cloud-voice-network-settings.md)。

- 信頼できる IP アドレスには、エンタープライズ ネットワークのインターネット外部 IP アドレスのコレクションが含まれているので、ユーザーのエンドポイントが企業ネットワーク内にあるかどうかを判断するために使用されます。 動的ポリシーまたは場所を取得しようとすると、ユーザーの外部 IP アドレスが信頼された IP アドレスの IP アドレスと一致する場合にのみ行います。 IPv4 または IPv6 の IP アドレスに対して一致を行い、ネットワーク設定に送信される IP パケットの形式に依存します。  (パブリック IP アドレスに IPv4 と IPv6 の両方がある場合は、両方を信頼済み IP アドレスとして追加する必要があります)。

- ネットワーク地域にはネットワーク サイトのコレクションが含まれます。 

- ネットワーク サイトは、オフィス、ビルのセット、キャンパスなど、組織が物理的な価値を持つ場所を表します。 これらのサイトは、IP サブネットのコレクションとして定義されます。

- ネットワーク サブネットは、特定のネットワーク サイトに関連付けられている必要があります。 クライアントの場所は、ネットワーク サブネットと関連付けられているネットワーク サイトに基づいて決定されます。  

ネットワーク設定は、管理センター Microsoft Teams PowerShell を使用して構成します。 詳細については、「クラウド音声機能 [のネットワーク トポロジを管理する」を参照してください](manage-your-network-topology.md)。

ネットワーク設定 (新しいアドレス、ネットワーク識別子など) の一部の変更が反映され、Teams クライアントで使用できるまで、時間がかかる場合があります (最大 2 時間)。  

**通話プラン ユーザーの場合:**

- セキュリティ デスク通知の動的構成が必要な場合は、信頼できる IP アドレスとネットワーク サイトの両方を構成する必要があります。

- 動的な場所だけが必要な場合は、信頼できる IP アドレスのみを構成する必要があります。

- どちらも必要ない場合は、ネットワーク設定を構成する必要はありません。 

**ダイレクト ルーティング ユーザーの場合:**

- 緊急通話の動的有効化またはセキュリティ デスク通知の動的構成が必要な場合は、信頼済み IP アドレスとネットワーク サイトの両方を構成する必要があります。

- 動的な場所だけが必要な場合は、信頼できる IP アドレスのみを構成する必要があります。

- どちらも必要ない場合は、ネットワーク設定を構成する必要はありません。


## <a name="configure-location-information-service"></a>Location Information Service の構成

クライアントTeams、異なるネットワーク識別子に関連付けられている場所から緊急対応の住所を取得します。 サブネットとワイヤレス アクセス ポイント (WAP) の両方がサポートされています。 イーサネット スイッチ/ポートは、現時点Windows 8.1以降でサポートされています。

クライアントが場所を取得するには、ネットワーク識別子 (サブネット、WAP、スイッチ、ポート) と緊急対応の場所を LIS に設定する必要があります。 この操作は、管理センター Microsoft Teams PowerShell を使用して行います。

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. 左側のナビゲーションで、[場所] [**ネットワーク]**  >  **に移動&します**。
2. 追加するネットワーク識別子を表すタブをクリックします。 たとえば、[サブネット] **、Wi-Fi アクセス** ポイント、[スイッチ] 、または [**ポート**] を **クリックします**。  次に、[追加] **をクリックします**。
3. フィールドに入力し、緊急対応の場所を追加して、[適用] を **クリックします**。

### <a name="using-powershell"></a>PowerShell の使用

次のコマンドレットを使用して、ポート、スイッチ、サブネット、および WAP を LIS に追加します。

- [を取得](/powershell/module/skype/get-csonlinelissubnet?view=skype-ps)[し、設定](/powershell/module/skype/set-csonlinelissubnet?view=skype-ps)[し、-CsOnlineLisSubnet](/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps)を削除します。
- [を取得](/powershell/module/skype/get-csonlinelisport?view=skype-ps)[し、設定](/powershell/module/skype/set-csonlinelisport?view=skype-ps)し、-CsOnlineLisPort を削除します。 [](/powershell/module/skype/remove-csonlinelisport?view=skype-ps)
- [を取得](/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps)[し、設定](/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps)し、-CsOnlineLisWirelessAccessPoint を削除します。 [](/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps)
- [を取得](/powershell/module/skype/get-csonlinelisswitch?view=skype-ps)[し、設定](/powershell/module/skype/set-csonlinelisswitch?view=skype-ps)し、-CsOnlineLisSwitch を削除します。 [](/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps)

>[!Important]
>サブネットがネットワーク サイトの一部として使用されている場合は、動的な場所をレンダリングするために Location Information Service でサブネットを再定義する必要があります。

## <a name="configure-emergency-policies"></a>緊急ポリシーを構成する

緊急通話を構成するには、次のポリシーを使用します。 これらのポリシーは、Microsoft Teams または PowerShell を使用して管理できます。

- **緊急通話ルーティング ポリシー** – 直接ルーティングにのみ適用されます。 このポリシーでは、緊急電話番号、必要に応じて番号ごとのマスク、番号ごとの PSTN ルートを構成します。  このポリシーは、ユーザー、ネットワーク サイト、または両方に割り当てできます。 (通話プランTeamsは、お客様の電話番号または使用場所に基づいて、国からの緊急電話番号を使用した緊急通話Microsoft 365自動的Office 365有効になります)。 詳細については、「ダイレクト ルーティングの[緊急通話ルーティング ポリシーを管理する」を参照してください](manage-emergency-call-routing-policies.md)。

- **緊急通話ポリシー** - 通話プランと直接ルーティングに適用されます。 このポリシーは、緊急通話が行われたときにセキュリティ デスク通知エクスペリエンスを構成します。 通知するユーザーと通知方法を設定できます。 たとえば、組織のセキュリティ デスクに自動的に通知し、緊急通話でリッスンします。  このポリシーは、ユーザーまたはネットワーク サイト、または両方に割り当てることができます。 詳細については、「緊急通話ポリシー[を管理する」を参照Teams。](manage-emergency-calling-policies.md)

## <a name="enable-users-and-sites"></a>ユーザーとサイトを有効にする

緊急通話ルーティング ポリシーと緊急通話ポリシーをユーザーとサイトに割り当てできます。 緊急通話ルーティング ポリシーは直接ルーティングにのみ適用されます。 (このポリシーを通話プラン のユーザーに割り当ては可能ですが、ポリシーは影響しません)。

ポリシーを割り当てるには、Microsoft Teamsまたは PowerShell を使用します。 詳細については、次を参照してください。

- [ダイレクト ルーティングの緊急通話ルーティング ポリシーを管理する](manage-emergency-call-routing-policies.md)
- [緊急通話ポリシーを管理Teams](manage-emergency-calling-policies.md)

PowerShell の例を次に示します。

特定のユーザーにセキュリティ デスク通知を有効にするには、次のコマンドを使用します。

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

"Contoso 緊急通話ポリシー 1" というポリシーをサイト 1 に割り当てるには、次のコマンドを使用します。

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

特定のダイレクト ルーティング ユーザーが緊急通話を有効にするには、次のコマンドを使用します。

```PowerShell
Grant-CsTeamsEmergencyCallRoutingPolicy -Identity user1 -PolicyName UnitedStates
```

"Contoso New York 緊急通話ルーティング" というポリシーをサイト 1 に割り当てるには、次のコマンドを使用します。

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Contoso New York Emergency Call Routing"
```

緊急通話ポリシーをネットワーク サイトとユーザーに割り当て、そのユーザーがネットワーク サイトにある場合、ネットワーク サイトに割り当てられているポリシーは、ユーザーに割り当てられているポリシーを上書きします。

## <a name="test-emergency-calling"></a>緊急通話をテストする

米国の一部の緊急ルーティング サービス プロバイダー (ERSP) は、緊急通話テスト ボットを提供しています。

- **米国の通話プラン ユーザーは、** 事前に定義されたテスト緊急電話番号 933 を使用して、緊急通話の構成を検証できます。 この番号はボットにルーティングされ、呼び出し元の電話番号 (発信元の電話番号 ID)、緊急対応の住所または場所、および呼び出しが PSAP に自動的にルーティングされるのか、最初に画面に表示されるのかをエコーバックします。

- **米国のダイレクト ルーティングのお客様は、** テスト サービスのために ERSP と調整する必要があります。

## <a name="government-support"></a>政府機関のサポート

次の表は、政府機関向けクラウドでの動的緊急通話のサポートを示しています。

| クラウド | 使用するための条件 |
| :------------|:-------|
| World Wide Multi Tenant | すべてのクライアントでTeams可能 |
| GCC | すべてのクライアントでTeams可能 |
| GCCH | デスクトップでTeams可能 |
| DoD | Pending |

 ## <a name="related-topics"></a>関連項目

- [緊急通話を管理する](what-are-emergency-locations-addresses-and-call-routing.md)
- [緊急通話ポリシーを管理する](manage-emergency-calling-policies.md)
- [緊急通話ルーティング ポリシーを管理する ](manage-emergency-call-routing-policies.md)
- [組織の緊急対応の場所を追加、変更、削除する](add-change-remove-emergency-location-organization.md)
- [ユーザーの緊急対応の場所を割り当てるまたは変更する](assign-change-emergency-location-user.md)
- [クラウド ボイス機能のネットワーク設定](cloud-voice-network-settings.md)
- [クラウド ボイス機能のネットワーク トポロジを管理する](manage-your-network-topology.md)
