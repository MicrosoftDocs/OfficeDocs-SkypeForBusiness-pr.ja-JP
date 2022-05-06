---
title: Azure Monitor を使用してMicrosoft Teams Roomsデバイスを監視する
ms.author: czawideh
author: cazawideh
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: f8109905-3279-475f-a64b-31d37af48bfe
ms.collection:
- M365-collaboration
description: この記事では、Azure Monitor を使用してMicrosoft Teams Roomsデバイスを統合された方法で監視する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a19a6be8f48bedca228457f7e5c2c85be1ef8374
ms.sourcegitcommit: b878c57b8e822913b7aac8c105f476bc4ebfcd7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2022
ms.locfileid: "63761901"
---
# <a name="monitor-microsoft-teams-rooms-devices-with-azure-monitor"></a>Azure Monitor を使用してMicrosoft Teams Roomsデバイスを監視する

この記事では、Azure Monitor を使用して統合された方法でMicrosoft Teams Roomsを監視する方法について説明します。

会議室デバイスの監視に役立つ基本的なテレメトリを提供するように Azure Monitor Microsoft Teams構成できます。 詳細については、「[Azure Monitor を使用してMicrosoft Teams Rooms管理を計画](azure-monitor-plan.md)し、Azure [Monitor でMicrosoft Teams Rooms管理をデプロイ](azure-monitor-deploy.md)する」を参照してください。 監視ソリューションが成熟するにつれて、追加のデータと監視機能を使用して、デバイスのパフォーマンスのより詳細なビューを作成できます。

## <a name="understand-the-log-entries"></a>ログ エントリを理解する

Microsoft Teams Rooms アプリが対応する情報をWindows イベント ログに記録すると、次のイベントの説明が 5 分ごとにイベント ログの説明フィールドに挿入されます。 Microsoft Monitoring Agentでは、これらのレコードが Azure Monitor の Log Analytics に渡され、Azure Monitor を使用した[デプロイMicrosoft Teams Rooms監視](azure-monitor-deploy.md)で作成したダッシュボードに解析されます。 ダッシュボードを使用すると、個々のログ エントリを調べて、必要に応じてアクションのコースを決定できます。

イベント ID 2000 と 3000 は、Teams Roomsが期待どおりに動作していることを示します。 イベント ID 2001 と 3001 は、問題が見つかったことを示します。 イベント ID 4000 では、設定したベースラインや組織内の他の展開済みデバイスと比較して、予想以上に頻繁に表示される場合にアクションが必要になる場合があります。

これらのイベントの説明を理解することで、問題を速やかに把握して、より適切なトラブルシューティングを行う機会が得られます。

| EventIDlevel&nbsp;&nbsp;|Eventbehavior&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|EventDescription&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
|:---    |:---   |:---  |
| 2000  <br> 情報 | これは正常なハートビート イベントです。 Microsoft Teams Roomsは 5 分ごとに、Microsoft TeamsまたはSkype for Businessにサインインし、ネットワークとExchange接続があることを確認します。 <br> 3 つの要素がすべて true の場合、デバイスがオフラインになるか、1 つ以上の条件が満たされなくなるまで、イベント ログにイベント ID 2000 が 5 分ごとに書き込まれます。 | `{"Description":"Heartbeat is healthy.", "ResourceState":"Healthy", "OperationName":"Heartbeat", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@contoso.com",  "DisplayName":"Display name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10",  "IPv6Address":"IP v6 address"}` <br><br> この例では、すべてのハートビート条件が満たされ、Microsoft Teams Rooms デバイスが正常としてマークされました。 エラーがある場合は、アプリが記録するイベント ID は 2001 になります。 |
| 2001  <br> エラー | これはアプリのエラー イベントです。 Microsoft Teams Roomsは、5 分ごとに、ネットワークとExchange接続を使用してMicrosoft TeamsまたはSkype for Businessにサインインしていることを確認します。 1 つ以上の要因が正しくない場合は、デバイスがオフラインになるか、すべての条件が再び満たされるまで、イベント ログに EventID 2001 が 5 分ごとに書き込まれます。  | `{"Description":"Network status : Healthy. Exchange status : Connected. Signin status: Unhealthy. Teams Signin status: Healthy.", "ResourceState":"Unhealthy", "OperationName":"Heartbeat", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br>  この例では、ネットワーク接続が正常であり、アプリがExchangeに接続されていることを確認Microsoft Teams Roomsが、太字の部分はアプリが接続されていないことを示しています。 これは、デバイスまたはホスト上の構成の問題である可能性があります。  <br> <br> ネットワークの状態は、[正常] または [異常] と表示されます。 状態が異常な場合は、ネットワークの問題が発生したり、デバイスが取り外された可能性があります (ただし、ExchangeエラーやMicrosoft TeamsエラーやSkype for Businessエラーも発生する可能性があります)。  <br><br> Exchange状態は、接続済み、接続中、自動検出エラー (最もよく見られるエラー)、GeneralError、または ServerVersionNotSupported のいずれかとして表示されます。 この状態が Connecting の場合は、次の状態メッセージが送信されるまで待機して、その他のエラーについては、Exchange の問題解決の経験がある管理者にその問題について相談します。  <br><br>  _サインイン状態_/_Teamsサインイン状態_ (アプリがサインインしていることを示す) は _、[正常_] または [_異常]_ として表示されます。 この状態が Unhealthy の場合は、技術者を派遣して詳しい調査を行ってください。 |
| 3000  <br> 情報 | このイベントは、ハードウェア チェックが実行され、正常であることが判明したことを確認します。 5 分ごとにMicrosoft Teams Rooms、ルームディスプレイ、マイク、スピーカー、カメラなどの構成済みのハードウェア コンポーネントが接続され、機能していることを確認します。 すべてのコンポーネントが正常な場合は、EventID 3000 がイベント ログに書き込まれます。 このイベントは、接続されているデバイスに問題がない限り、5 分ごとに書き込まれます。  <br> | `{"Description":"HardwareCheckEngine is healthy.",  "ResourceState":"Healthy", "OperationName":"HardwareCheckEngine",  "OperationResult":"Pass", "OS":"Windows 10",  "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@contoso.com", "DisplayName":"Display Name", "AppVersion":"1.0.38.0",  "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br> この例では、すべてのハードウェア チェックに合格しています。 エラーが発生した場合、アプリは代わりにイベント ID 3001 を記録します。 |
| 3001  <br> エラー イベント  | これはハードウェアのエラー イベントです。 Microsoft Teams Rooms アプリには、接続されたハードウェア コンポーネント (部屋の前面、マイク、スピーカー、カメラ) の正常性を 5 分ごとにチェックするプロセスがあります。 1 つ以上のコンポーネントが異常な場合は、EventID 3001 がイベント ログに書き込まれます。 このイベントは、デバイスに関する問題が修正されるまで 5 分ごとに書き込まれます。   | `{"Description":" Front of Room Display status : Unhealthy. Configured display count is 2. Real display count is 0. Conference Microphone status : Unhealthy. Conference Speaker status : Healthy. Default Speaker status : Healthy. Camera status : Healthy.", "ResourceState":"Unhealthy", "OperationName":"HardwareCheckEngine", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.1198", "Alias":"alias<span></span>@contoso.com", "DisplayName":"Yosemite conference room", "AppVersion":"2.0.58.0", "IPv4Address":"10.10.10.10", "IPv6Address":"IPv6Address", "IPv4Address2":"10.10.10.10"}` <br><br>  ハードウェア周辺機器は Healthy または Unhealthy のいずれかとして表示されます。 <br> この例では、2 つの _前面のルーム_ ディスプレイが構成されており、現在はどちらも使用できません。 _会議マイクの状態_ が _異常_ であり、考えられるいくつかの原因が考えられます。 少なくとも 1 つのリソースがチェックに合格していなかったため、ResourceState が Unhealthy として表示されます。 技術者を派遣して詳しい調査を行ってください。 |
| 4000  <br> 情報  <br> | これはアプリの再起動イベントです。 アプリが再起動するたびに、このイベントを必ず Windows イベント ログに記録します。  <br> | `{"Description":"App restarts.", "ResourceState":"Healthy", "OperationName":"Restart", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@domain.com", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br> アプリは、さまざまな理由で再起動される場合があります。 同じ建物と異なるビル内のデバイスの再起動頻度を比較します。 電源の変動や障害などの既知の問題に注意してください。これはインフラストラクチャの問題の手がかりになる可能性があるためです。|

## <a name="related-topics"></a>関連項目
 

[Azure Monitor でMicrosoft Teams Rooms監視を計画する](azure-monitor-plan.md)

[Azure Monitor を使用してMicrosoft Teams Rooms監視をデプロイする](azure-monitor-deploy.md)
