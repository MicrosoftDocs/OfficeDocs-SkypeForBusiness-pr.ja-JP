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
ms.reviewer: roykuntz
localization_priority: Normal
search.appverid: MET150
description: 動的な緊急通話を構成する
appliesto:
- Microsoft Teams
ms.openlocfilehash: a282d8c5cd923f6881a04da7f2569a5dca11421b
ms.sourcegitcommit: 013190ad10cdc02ce02e583961f433d024d5d370
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/31/2020
ms.locfileid: "41634810"
---
# <a name="plan-and-configure-dynamic-emergency-calling"></a>動的な緊急通話を計画して構成する 

Microsoft 通話プランや電話システムのダイレクトルーティングの動的な緊急通話では、チームクライアントの現在の場所に基づいて緊急通話の構成とルーティングを行う機能が提供されます。  

テナント管理者が定義したネットワークトポロジに基づいて、Teams クライアントは、位置情報サービス (LIS) に対する要求にネットワーク接続情報を提供します。  一致するものがある場合、LIS はクライアントに対して場所を返します。 この位置情報データはクライアントに戻されます。  

チームクライアントには、緊急通話の一部として位置情報データが含まれます。 このデータは、緊急サービスプロバイダーによって、適切な公開安全性の応答ポイント (PSAP) を特定し、その呼び出しをその PSAP にルーティングすることによって、呼び出し元の位置情報を取得できるようにすることを目的としています。  

動的な緊急通話の場合は、次のことを行う必要があります。

1. ネットワーク管理者がネットワーク設定と LIS を構成して、ネットワーク/緊急対応の場所マップを作成します。

   直接ルーティングの場合は、緊急通話をルーティングするために追加の構成が必要になります。また、パートナー接続の場合もあります。 管理者は、緊急ルーティングサービス (管理者) プロバイダーへの接続を構成する**か**(米国)、緊急対応の位置情報識別番号 (ELIN) アプリケーションのセッションボーダーコントローラー (SBC) を構成する必要があります。

2. 起動時と定期的に定期的に、またはネットワーク接続が変更されると、チームクライアントはネットワーク接続情報が含まれている場所要求をネットワーク設定と LIS に送信します。

   - [ネットワーク設定] サイトがある場合は、緊急通話のポリシーがそのサイトから Teams クライアントに返されます。 (ポリシーの詳細については、「[緊急ポリシーを構成する](#configure-emergency-policies)」を参照してください)。

   - LIS の一致がある場合は、Teams クライアントが接続されているネットワーク要素の緊急対応の場所が Teams クライアントに返されます。

3. チームクライアントが緊急通報を行うと、緊急対応の場所が PSTN ネットワークに伝達されます。

   直接ルーティングの場合、管理者は、アプリを緊急通報に送信するように SBC を構成するか、SBC ELIN アプリケーションを構成する必要があります。

この記事は、次のセクションで構成されています。

- [緊急対応の住所を設定する](#assign-emergency-addresses)
- [ネットワーク設定を構成する](#configure-network-settings)
- [位置情報サービスを構成する](#configure-location-information-service)
- [緊急ポリシーを構成する](#configure-emergency-policies)
- [ユーザーとサイトを有効にする](#enable-users-and-sites)
- [緊急通話のテスト](#test-emergency-calling)


適切な公開安全性の応答ポイント (PSAP) に自動的にルーティングする機能は、Teams ユーザーの使用国によって異なります。 

緊急通話の詳細については、緊急対応の住所と緊急通話のルーティングに関する情報、国に固有の情報、ネットワーク設定とネットワークトポロジに関する情報を含む緊急通話の詳細については、以下を参照してください。

- [緊急通話を管理する](what-are-emergency-locations-addresses-and-call-routing.md)
- [クラウド音声機能のネットワーク設定を管理する](cloud-voice-network-settings.md)
- [クラウド ボイス機能のネットワーク トポロジを管理する](manage-your-network-topology.md)


## <a name="supported-clients"></a>サポートされるクライアント

現在、次のクライアントがサポートされています。  このリストの更新を確認するには、もう一度チェックインします。

- Windows 用 Teams デスクトップクライアント
- Mac 用の Teams のデスクトップクライアント
- Lync mobile クライアント for IOS クライアントバージョン1.0.92.2019121004 とアプリストアバージョン1.0.92 以上
- Android クライアント向け Teams モバイルクライアントとストアバージョン 1416/1.0.0.2019121201 以上
- Teams 電話バージョン 1449/1.0.94.2019110802 以降

## <a name="assign-emergency-addresses"></a>緊急対応の住所を割り当てる

緊急対応の住所は、通話プランのユーザーと、場所を動的に取得するために必要なネットワーク識別子の両方に割り当てることができます。 (Subnet および WiFi AP はサポートされています。イーサネットスイッチ/ポートのサポートは保留中)。

米国内での緊急通話の自動ルーティングをサポートするには、ネットワーク識別子に割り当てられている緊急対応の場所に関連する geo コードが含まれていることを確認する必要があります。 (地理コードのない緊急対応の住所を、動的な場所に必要なネットワーク識別子に割り当てることはできません。)

Azure Maps は、位置ベースのサービスに使用されます。  Microsoft Teams 管理センターを使用して緊急対応の住所を入力すると、チームは次のアドレスの Azure Maps を確認します。

- 一致するものが見つかった場合は、geo コードが自動的に含まれます。

- 一致が見つからなかった場合は、緊急対応の住所を手動で作成することができます。 PIN のドロップ機能を使用して、この操作を行うことができます。   

これは、通話プランユーザに割り当てるために作成された既存の緊急対応の場所が、動的な場所を目的としている場合は、その住所を再作成して geo コードを含める必要があることを意味します。 2つの場所を区別するには、別の説明を含める必要があります。 以前の場所を持っているユーザーに新しい緊急対応の場所を割り当てることができます。 完全に移行された場合、古い場所は削除できます。

緊急対応の住所の設定の詳細については、「[組織の緊急対応の場所を追加](add-change-remove-emergency-location-organization.md)する」および「[緊急対応の場所をユーザーに割り当てる](assign-change-emergency-location-user.md)」を参照してください。

## <a name="configure-network-settings"></a>ネットワーク設定を構成する

[ネットワーク設定] は、Teams クライアントの場所を決定するために使用され、緊急通話ポリシーと緊急対応の場所を動的に取得します。 組織で緊急電話が機能する方法に応じて、ネットワーク設定を構成できます。

ネットワーク設定には、サブネットのコレクションが含まれているサイトが含まれます。これらは、ユーザーへの動的なポリシーの割り当てに対してのみ使用されます。  たとえば、TeamsEmergencyCalling ポリシーと TeamsEmergencyCallRouting ポリシーが "Redmond サイト" に割り当てられている可能性があります。これにより、ホームまたは別の Microsoft 場所からローミングするユーザーは、緊急電話番号、ルーティング、セキュリティデスクで構成されます。レドモンドに固有です。  

>[!Note]
>サブネットは、LIS で定義することもできます。また、緊急対応の場所に関連付けることもできます。  

次の定義を念頭に置いてください。

- 信頼できる IP には、企業ネットワークのインターネット外部 Ip のコレクションが含まれており、ユーザーのエンドポイントが企業ネットワーク内にあるかどうかを判断するために使用されます。 動的なポリシーまたは場所を取得しようとしても、ユーザーの外部 IP が信頼された IP アドレスの IP アドレスと一致した場合にのみ行われます。 一致は、IPv4 または IPv6 の IP アドレスに対して行うことができます。また、ネットワーク設定に送信される IP パケットの形式によって異なります。  (パブリック IP アドレスに IPv4 と IPv6 の両方が含まれている場合は、両方を信頼できる IP アドレスとして追加する必要があります)。

- ネットワーク地域にはネットワーク サイトのコレクションが含まれます。 

- ネットワークサイトは、オフィス、建物のセット、キャンパスなど、組織の物理的な値が含まれている場所を表します。 これらのサイトは、IP サブネットのコレクションとして定義されます。

- ネットワークサブネットは、特定のネットワークサイトに関連付けられている必要があります。 クライアントの場所は、ネットワークサブネットと関連付けられたネットワークサイトに基づいて決定されます。  

詳細については、「[クラウド音声機能のネットワーク設定](cloud-voice-network-settings.md)」と「[クラウド音声機能のネットワークトポロジを管理](manage-your-network-topology.md)する」を参照してください。

ネットワーク設定の変更 (新しいアドレス、ネットワーク識別子など) がチームクライアントに伝達されて利用可能になるまでに少し時間がかかる場合があることに注意してください。  

**通話プランユーザーの場合:**

- セキュリティデスク通知の動的構成が必要な場合は、信頼できる IP アドレスとネットワークサイトの両方を構成する必要があります。

- 動的な場所のみが必要な場合は、信頼できる IP アドレスのみを構成する必要があります。 

- どちらも必要ない場合は、ネットワーク設定の構成は必要ありません。 

**ダイレクトルーティングユーザーの場合:**

- 緊急通報またはセキュリティデスクの動的構成の通知が動的に使用されるようにするには、信頼できる IP アドレスとネットワークサイトの両方を構成する必要があります。

- 動的な場所のみが必要な場合は、信頼できる IP アドレスのみを構成する必要があります。

- どちらも必要ない場合は、ネットワーク設定の構成は必要ありません。


## <a name="configure-location-information-service"></a>位置情報サービスを構成する

チームクライアントは、異なるネットワーク識別子に関連付けられている場所から緊急対応の住所を取得します。 サブネットとワイヤレスアクセスポイント (Wap) はどちらもサポートされています。 (イーサネットスイッチ/ポートのサポートは保留中です)。

クライアントが場所を取得するには、次のコマンドレットを使用して、場所情報サービス (LIS) にネットワーク識別子と緊急対応の場所を設定する必要があります。  


- [取得](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisport?view=skype-ps)、[設定](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisport?view=skype-ps)、[削除](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisport?view=skype-ps)-csonlinのスポーツ
- [取得](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisswitch?view=skype-ps)、[設定](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisswitch?view=skype-ps)、[削除](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps)-csonlinの切り替え
- [Get](https://docs.microsoft.com/powershell/module/skype/get-csonlinelissubnet?view=skype-ps)、 [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlinelissubnet?view=skype-ps)、 [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) -csonlinのサブネット
- [Get](https://docs.microsoft.com/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps)、 [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps)、 [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps
) -CsOnlineLisWirelessAccessPoint 


>[!Important] 
>サブネットがネットワークサイトの一部として使われている場合は、動的な場所を表示するために、場所情報サービスでサブネットを再定義する必要があります。


## <a name="configure-emergency-policies"></a>緊急ポリシーを構成する

緊急通話を構成するには、次のポリシーを使用します。

- **TeamsEmergencyCallRoutingPolicy** –直接ルーティングにのみ適用されます。 このポリシーでは、緊急電話番号、必要に応じて番号のマスク、および電話番号ごとの PSTN ルートを構成します。  このポリシーは、ユーザー、ネットワークサイト、またはその両方に割り当てることができます。 (通話プランのチームクライアントは、Office 365 の利用場所に基づいて、国の緊急電話番号を使用して、自動的に有効になります。) このポリシーを管理するには、新しい-、CsTeamsEmergencyCallRouting コマンドレットを使用します。 

- **TeamsEmergencyCallingPolicy** -通話プランとダイレクトルーティングに適用されます。 このポリシーは、緊急通話が行われたときのセキュリティデスクの通知を構成します。 通知する相手と通知方法を設定できます。 たとえば、組織のセキュリティデスクに通知を自動的に送信し、そのユーザーが緊急通話をリッスンするようにします。  このポリシーは、ユーザーまたはネットワークサイトまたはその両方に割り当てることができます。 このポリシーを管理するには、新しい-、CsTeamsEmergencyCallingPolicy コマンドレットを使用します。 

詳細については、「 [Teams で緊急通話のポリシーを管理](manage-emergency-calling-policies.md)する」および「[ダイレクトルーティングの緊急通話ルーティングポリシーを管理する](manage-emergency-call-routing-policies.md)」を参照してください。


## <a name="enable-users-and-sites"></a>ユーザーとサイトを有効にする

**TeamsEmergencyCalling**と**TeamsEmergencyCallROuting**のポリシーは、ユーザーとサイトに割り当てることができます。  

TeamsEmergencyCallRouting ポリシーは、直接ルーティング専用に適用されます。 (このポリシーは、通話プランのユーザーに割り当てることもできますが、ポリシーは影響を与えません)。

たとえば、セキュリティデスクの通知に特定のユーザーを有効にするには、次のコマンドを使用します。

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

"Contoso 緊急通話ポリシー 1" と呼ばれるポリシーをサイト1に割り当てるには、次のコマンドを使用します。

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

緊急通話のために特定の直接ルーティングユーザーを有効にするには、次のコマンドを使用します。

```PowerShell
Grant-CsTeamsEmergencyCallRoutingPolicy -Identity user1 -PolicyName UnitedStates
```

"Contoso New 都エマージェンシールーティング" と呼ばれるポリシーをサイト1に割り当てるには、次のコマンドを使用します。

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Contoso New York Emergency Call Routing"
```

緊急通話のポリシーをネットワークサイトとユーザーに割り当て、そのユーザーがそのネットワークサイトを使用している場合、そのネットワークサイトに割り当てられているポリシーが、ユーザーに割り当てられているポリシーよりも優先されます。


## <a name="test-emergency-calling"></a>緊急通話のテスト

米国の一部の緊急ルーティングサービスプロバイダー (ERSPs) では、緊急対応のテストボットが提供されています。

- **米国の通話プランユーザー**は、事前に定義されたテスト緊急電話番号933を使って、緊急通話の構成を検証できます。 この番号はボットにルーティングされます。これは、発信者番号 (発信者の電話番号)、緊急対応の住所、場所、通話が自動的に PSAP にルーティングされるか、最初に表示されるかどうかを示します。

- **米国のダイレクトルーティングのお客様**は、テストサービスの ersp と連携する必要があります。

 ## <a name="related-topics"></a>関連項目

- [緊急通話を管理する](what-are-emergency-locations-addresses-and-call-routing.md)
- [緊急通話ポリシーを管理する](manage-emergency-calling-policies.md)
- [緊急通話ルーティングポリシーを管理する](manage-emergency-call-routing-policies.md)
- [組織の緊急対応の場所を追加、変更、削除する](add-change-remove-emergency-location-organization.md)
- [ユーザーの緊急対応の場所を割り当てる、または変更する](assign-change-emergency-location-user.md)
- [クラウド ボイス機能のネットワーク設定](cloud-voice-network-settings.md)
- [クラウド ボイス機能のネットワーク トポロジを管理する](manage-your-network-topology.md)
