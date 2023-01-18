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
- highpri
ms.reviewer: roykuntz
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
description: Microsoft 通話プランと電話システム ダイレクト ルーティング動的緊急通話機能を構成する方法について説明します。
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1061adf81b8e9ae84ad028a5047636b6fee7a959
ms.sourcegitcommit: 052e4b3982b0b8ee7d4edc47da4d63b35518a757
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/18/2023
ms.locfileid: "69814359"
---
# <a name="plan-and-configure-dynamic-emergency-calling"></a>動的な緊急通話を計画して構成する 

Microsoft 通話プラン、オペレーター接続、Teams Phone Mobile、ダイレクト ルーティングの動的緊急通話は、Teams クライアントの現在の場所に基づいて緊急通報を構成してルーティングし、セキュリティ担当者に通知する機能を提供します。  

Teams クライアントは、テナント管理者が定義するネットワーク トポロジ (緊急対応アドレスに関連付けられたネットワーク要素) に基づいて、位置情報サービス (LIS) への要求でネットワーク接続情報を提供します。 一致するものがある場合、LIS はクライアントに場所を返します。

Teams クライアントには、緊急通報の一部として場所データが含まれます。 その後、このデータは緊急サービス プロバイダーによって使用され、適切な公衆安全応答ポイント (PSAP) を決定し、その PSAP への呼び出しをルーティングします。これにより、PSAP ディスパッチャーは呼び出し元の場所を取得できます。  

動的緊急通話の場合は、次の処理を行う必要があります。

1. ネットワーク管理者は、ネットワーク設定と LIS を構成して、ネットワーク/緊急位置情報マップを作成します。

2. 起動中、その後定期的に、またはネットワーク接続が変更されると、Teams クライアントはネットワーク接続情報を含む場所要求をネットワーク設定と LIS に送信します。

   - ネットワーク設定サイトの一致がある場合は、緊急通話ポリシーがそのサイトから Teams クライアントに返されます。 (ポリシーの詳細については、「 [緊急ポリシーの構成](#configure-emergency-policies)」を参照してください)。

   - LIS の一致がある場合 - Teams クライアントが接続されているネットワーク要素からの緊急の場所が Teams クライアントに返されます。 一致は次の順序で実行され、最初に一致した結果が返されます。
       - Wap
       - イーサネット スイッチ/ポート
       - イーサネット スイッチ
       - サブネット

3. Teams クライアントが緊急通話を行うと、緊急の場所が PSTN ネットワークに伝達されます。

適切なパブリック セーフティ応答ポイント (PSAP) への自動ルーティングを実行する機能は、Teams ユーザーの使用国によって異なります。

Microsoft 通話プラン、オペレーター接続パートナー、および Teams Phone Mobile パートナーには、米国とカナダのユーザー向けの動的緊急ルーティング サービスが含まれています。

ただし、ダイレクト ルーティングの場合、緊急通報のルーティングやパートナー接続の場合は追加の構成が必要です。 管理者は、緊急通報をルーティングする PSTN ゲートウェイが、発信 INVITE に位置情報を追加するように構成されていることを確認する必要があります (オンライン PSTN ゲートウェイ オブジェクトでパラメーター PidfloSupported を True に設定します)。 さらに、管理者は緊急ルーティング サービス (ERS) プロバイダー (米国およびカナダ) への接続を構成 **するか**、緊急位置情報識別番号 (ELIN) アプリケーションのセッション ボーダー コントローラー (SBC) を構成する必要があります。 ERS プロバイダーの詳細については、「 [ダイレクト ルーティングの認定を受けたセッション ボーダー コントローラー](direct-routing-border-controllers.md)」を参照してください。

この記事には、次のセクションが含まれています。

- [緊急対応アドレスの割り当て](#assign-emergency-addresses)
- [ネットワーク設定を構成する](#configure-network-settings)
- [位置情報サービスの構成](#configure-location-information-service)
- [緊急ポリシーを構成する](#configure-emergency-policies)
- [ユーザーとサイトを有効にする](#enable-users-and-sites)
- [緊急通話をテストする](#test-emergency-calling)

緊急通報の詳細については、緊急対応と緊急通報のルーティングに関する情報、国固有の情報、ネットワーク設定とネットワーク トポロジに関する情報など、次の情報を参照してください。

- [緊急通話を管理する](what-are-emergency-locations-addresses-and-call-routing.md)
- [クラウド音声機能のネットワーク設定を管理する](cloud-voice-network-settings.md)
- [クラウド ボイス機能のネットワーク トポロジを管理する](manage-your-network-topology.md)

政府機関向けクラウドで使用できる機能の詳細については、この記事の最後にある [「Government サポート](#government-support) 」を参照してください。


## <a name="supported-clients"></a>サポートされるクライアント

現在、次のクライアントがサポートされています。  頻繁に確認して、この一覧の更新を確認してください。

- Microsoft Windows 用 Teams デスクトップ クライアント
- Apple macOS 用 Teams デスクトップ クライアント
- Apple iOS クライアント バージョン 1.0.92.2019121004 および App Store バージョン 1.0.92 以降の Teams モバイル クライアント
- Android クライアントおよび Google Play ストア バージョン 1416/1.0.0.2019121201 以降用の Teams モバイル クライアント
- Teams 電話バージョン 1449/1.0.94.2019110802 以降
- Teams Rooms バージョン 4.4.25.0 以降

> [!NOTE]
> サブネットと WiFi ベースの場所は、サポートされているすべての Teams クライアントでサポートされます。 <br><br>
> イーサネット/スイッチ (LLDP) は、次の場合にサポートされます。
> - 現時点では、Windows バージョン 10.0 以降。<br>
> - [LLDP 有効化ソフトウェア](https://www.microsoft.com/download/details.aspx?id=103383)が必要な Mac OS。<br>
> - Teams アプリ バージョン 1449/1.0.94.2021110101 以降の Teams 電話。

> [!NOTE]
> セキュリティ デスク通知を含む動的緊急通話は、Teams Web クライアントではサポートされていません。 ユーザーが Teams Web クライアントを使用して PSTN 番号を呼び出さないようにするには、Teams 通話ポリシーを設定し、[ **Web PSTN 通話を許可する]** 設定をオフにします。 詳細については、「 [Teams でのポリシーの呼び出し](teams-calling-policy.md) 」と [「Set-CsTeamsCallingPolicy」を](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)参照してください。 

> [!NOTE]
> 3PIP 電話は動的緊急通話をサポートしていません。 



## <a name="assign-emergency-addresses"></a>緊急対応アドレスの割り当て

緊急対応アドレスは、次のように割り当てることができます。

- 通話プラン のユーザーに。

- オペレーター Connect ユーザーと Teams Phone Mobile ユーザー&mdash;は、運送業者が顧客のインベントリにアップロードするときに番号に割り当てられた機能に応じて異なります。

- 場所を動的に取得するために必要なネットワーク識別子。 

米国内の緊急通報の自動ルーティングをサポートするには、ネットワーク識別子に割り当てられている緊急の場所に、関連付けられている地域コードが含まれるようにする必要があります。 (地理的コードのない緊急住所は、動的な場所に必要なネットワーク識別子に割り当てることはできません)。

Azure Mapsは、場所ベースのサービスに使用されます。 Microsoft Teams 管理センターを使用して緊急対応アドレスを入力すると、Teams はAzure Mapsアドレスを確認します。

- 一致するものが見つかった場合は、geo コードが自動的に含まれます。

- 一致するものが見つからない場合は、緊急対応アドレスを手動で作成する機会があります。 PIN ドロップ機能を使用してこれを行うことができます。 

> [!NOTE]
> 2 年以上前の緊急対応アドレスをネットワーク識別子に割り当てることはできません。 古いアドレスを再作成する必要があります。

Microsoft Teams 管理センターまたは PowerShell を使用して、緊急対応アドレスを追加して割り当てます。 詳細については、「 [組織の緊急対応場所を追加する](add-change-remove-emergency-location-organization.md) 」および「 [ユーザーに緊急の場所を割り当てる」を参照してください](assign-change-emergency-location-user.md)。

## <a name="configure-network-settings"></a>ネットワーク設定を構成する

ネットワーク設定は、Teams クライアントの場所を決定し、緊急通報ポリシーと緊急対応の場所を動的に取得するために使用されます。 組織が緊急通話を機能させる方法に応じて、ネットワーク設定を構成できます。

ネットワーク設定には、サブネットのコレクションを含むサイトが含まれており、これらはユーザーへの動的ポリシー割り当て専用に使用されます。 たとえば、自宅や別の Microsoft の場所からローミングするユーザーが Redmond 固有の緊急電話番号、ルーティング、セキュリティ デスクで構成されるように、緊急通話ポリシーと緊急通話ルーティング ポリシーが "Redmond サイト" に割り当てられる場合があります。  

信頼された IP アドレスには、エンタープライズ ネットワークのインターネット外部 IP アドレスのコレクションが含まれており、ユーザーのエンドポイントが企業ネットワーク内にあるかどうかを判断するために使用されます。 動的ポリシーまたは場所の取得は、ユーザーの外部 IP アドレスが信頼された IP アドレスの IP アドレスと一致する場合にのみ行われます。

IP アドレス、ネットワークリージョン、サイト、サブネット アドレスの詳細については、「 [クラウド音声機能のネットワーク設定](cloud-voice-network-settings.md)」を参照してください。

ネットワーク設定は、Microsoft Teams 管理センターまたは PowerShell を使用して構成します。 詳細については、「 [クラウド音声機能のネットワーク トポロジを管理する](manage-your-network-topology.md)」を参照してください。

ネットワーク設定の一部の変更 (新しいアドレス、ネットワーク識別子など) が反映され、Teams クライアントで使用できるようになるまで、しばらく (数時間) かかる場合があることに注意してください。  

> [!Note]
> サブネットは LIS で定義することも、緊急の場所に関連付けることもできます。  LIS サブネットは、クライアントに割り当てられたサブネット IP 範囲に一致するネットワーク ID によって定義する必要があります。 たとえば、10.10.10.150/25 のクライアント IP/マスクのネットワーク ID は 10.10.10.128 です。 詳細については、「 [TCP/IP アドレス指定とサブネット化の基本について」](/troubleshoot/windows-client/networking/tcpip-addressing-and-subnetting)を参照してください。

> [!Important]
> Teams クライアントからのソース IP アドレスを変更するクラウド プロキシ サービスのデプロイでは、ネットワーク構成設定の参照はサポートされていません。



**通話プラン、オペレーター接続、および Teams Phone Mobile ユーザーの場合:**

- セキュリティ デスク通知の動的構成が必要な場合は、信頼された IP アドレスとネットワーク サイトの両方を構成する必要があります。

- 動的な場所のみが必要な場合は、信頼された IP アドレスのみを構成する必要があります。ネットワーク設定の構成は必要ありません。

- どちらも必要ない場合は、ネットワーク設定を構成する必要はありません。 

**ダイレクト ルーティング ユーザーの場合:**

- 緊急通話の動的有効化またはセキュリティ デスク通知の動的構成が必要な場合は、信頼された IP アドレスとネットワーク サイトの両方を構成する必要があります。

- 動的な場所のみが必要な場合は、信頼された IP アドレスのみを構成する必要があります。ネットワーク設定の構成は必要ありません。

- どちらも必要ない場合は、ネットワーク設定を構成する必要はありません。


## <a name="configure-location-information-service"></a>位置情報サービスの構成

Teams クライアントは、さまざまなネットワーク識別子に関連付けられている場所から緊急アドレスを取得します。 

クライアントが場所を取得するには、ネットワーク識別子 (サブネット、WAP、スイッチ、ポート) と緊急の場所を LIS に設定する必要があります。 これを行うには、Microsoft Teams 管理センターまたは PowerShell を使用します。

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. 左側のナビゲーションで、[場所ネットワーク **]** > **& [場所**] に移動します。
2. 追加するネットワーク識別子を表すタブをクリックします。 たとえば、[ **サブネット**]、[ **Wi-Fi アクセス ポイント**]、[ **スイッチ**]、または **[ポート]** をクリックします。 次に、[ **追加**] をクリックします。
3. フィールドに入力し、緊急対応の場所を追加して、[ **適用**] をクリックします。

### <a name="using-powershell"></a>PowerShell の使用

次のコマンドレットを使用して、ポート、スイッチ、サブネット、WAP を LIS に追加します。

- [取得](/powershell/module/skype/get-csonlinelissubnet?view=skype-ps)、 [設定](/powershell/module/skype/set-csonlinelissubnet?view=skype-ps)、 [削除](/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) -CsOnlineLisSubnet
- [取得](/powershell/module/skype/get-csonlinelisport?view=skype-ps)、 [設定](/powershell/module/skype/set-csonlinelisport?view=skype-ps)、 [削除](/powershell/module/skype/remove-csonlinelisport?view=skype-ps) -CsOnlineLisPort
- [取得](/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps)、 [設定](/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps)、 [削除](/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps) -CsOnlineLisWirelessAccessPoint
- [取得](/powershell/module/skype/get-csonlinelisswitch?view=skype-ps)、 [設定](/powershell/module/skype/set-csonlinelisswitch?view=skype-ps)、 [削除](/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps) -CsOnlineLisSwitch

>[!Important]
>サブネットがネットワーク サイトの一部として使用されている場合、動的な場所をレンダリングするには、位置情報サービスでサブネットを再定義する必要があります。

## <a name="configure-emergency-policies"></a>緊急ポリシーを構成する

緊急通話を構成するには、次のポリシーを使用します。 これらのポリシーは、Microsoft Teams 管理センターまたは PowerShell を使用して管理できます。

- **緊急通話ルーティング ポリシー – ダイレクト ルーティングにのみ適用されます**。 このポリシーでは、緊急電話番号、必要に応じて番号ごとのマスク、および番号ごとの PSTN ルートを構成します。 このポリシーは、ユーザー、ネットワーク サイト、またはその両方に割り当てることができます。 詳細については、「 [ダイレクト ルーティングの緊急通話ルーティング ポリシーを管理する](manage-emergency-call-routing-policies.md)」を参照してください。  

   (通話プラン、オペレーター接続、および Teams Phone Mobile ユーザーは、Microsoft 365 または Office 365 の使用場所に基づいて、国の緊急電話番号を使用して緊急通話を自動的に有効にします)。

- **緊急通話ポリシー - 通話プラン、オペレーター接続、Teams 電話モバイル、ダイレクト ルーティングに適用されます。** このポリシーは、緊急通報が行われたときにセキュリティ デスク通知エクスペリエンスを構成します。 通知するユーザーと通知方法を設定できます。 たとえば、組織のセキュリティ デスクに自動的に通知し、緊急通報でリッスンさせます。  このポリシーは、ユーザーまたはネットワーク サイト、またはその両方に割り当てることができます。 詳細については、「 [Teams で緊急通話ポリシーを管理する](manage-emergency-calling-policies.md)」を参照してください。

## <a name="enable-users-and-sites"></a>ユーザーとサイトを有効にする

緊急通報ルーティング ポリシーと緊急通報ポリシーをユーザーとサイトに割り当てることができます。 緊急通話ルーティング ポリシーはダイレクト ルーティングにのみ適用されることに注意してください。 (通話プラン、オペレーター接続、または Teams Phone Mobile ユーザーにこのポリシーを割り当てることはできますが、ポリシーは効果がありません)。

ポリシーは、Microsoft Teams 管理センターまたは PowerShell を使用して割り当てます。 詳細については、次を参照してください。

- [ダイレクト ルーティングの緊急通話ルーティング ポリシーを管理する](manage-emergency-call-routing-policies.md)
- [Teams で緊急通話ポリシーを管理する](manage-emergency-calling-policies.md)

PowerShell の例を次に示します。

セキュリティ デスク通知に対して特定のユーザーを有効にするには、次のコマンドを使用します。

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

"Contoso 緊急通話ポリシー 1" というポリシーをサイト 1 に割り当てるには、次のコマンドを使用します。

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

緊急通話に対して特定のダイレクト ルーティング ユーザーを有効にするには、次のコマンドを使用します。

```PowerShell
Grant-CsTeamsEmergencyCallRoutingPolicy -Identity user1 -PolicyName UnitedStates
```

サイト 1 に "Contoso New York 緊急通話ルーティング" というポリシーを割り当てるには、次のコマンドを使用します。

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Contoso New York Emergency Call Routing"
```

緊急通話ポリシーをネットワーク サイトとユーザーに割り当て、そのユーザーがそのネットワーク サイトにいる場合、ネットワーク サイトに割り当てられているポリシーは、ユーザーに割り当てられているポリシーよりも優先されます。

## <a name="test-emergency-calling"></a>緊急通話をテストする

米国の一部の緊急ルーティング サービス プロバイダー (ERSP) では、緊急通話テスト ボットが提供されています。

- **米国またはカナダの通話プラン、オペレーター接続、および Teams Phone Mobile ユーザーは、** 定義済みのテスト緊急電話番号 933 を使用して、緊急通話の構成を検証できます。 この番号はボットにルーティングされ、発信者番号 (通話回線 ID)、緊急対応の住所または場所、および通話が自動的に PSAP にルーティングされるか、最初にスクリーニングされるかがエコーバックされます。

- **米国のダイレクト ルーティングのお客様** は、テスト サービスの ERSP と調整する必要があります。

## <a name="government-support"></a>政府機関向けサポート

次の表は、政府クラウドでの動的緊急通話のサポートを示しています。

| クラウド | 使用するための条件 |
| :------------|:-------|
| ワールド ワイド マルチ テナント | すべての Teams クライアントで使用可能 |
| Gcc | すべての Teams クライアントで使用可能 |
| GCCH | -Teams デスクトップで使用可能 <br> -Teams モバイル クライアントで利用可能 <br> -Teams 電話で利用できるアプリバージョン: 1449/1.0.94.2022061702 |
| 国防 総省 | -Teams デスクトップで使用可能 <br>-Teams モバイル クライアントで利用可能 <br>-Teams 電話での保留中 |

 ## <a name="related-topics"></a>関連項目

- [緊急通話を管理する](what-are-emergency-locations-addresses-and-call-routing.md)
- [緊急通話ポリシーを管理する](manage-emergency-calling-policies.md)
- [緊急通報ルーティング ポリシーを管理する ](manage-emergency-call-routing-policies.md)
- [組織の緊急対応の場所を追加、変更、削除する](add-change-remove-emergency-location-organization.md)
- [ユーザーの緊急対応場所の割り当てまたは変更](assign-change-emergency-location-user.md)
- [クラウド ボイス機能のネットワーク設定](cloud-voice-network-settings.md)
- [クラウド ボイス機能のネットワーク トポロジを管理する](manage-your-network-topology.md)
