---
title: Azure Monitorを使用して Microsoft Teams Rooms デバイスをデプロイする
ms.author: dstrome
author: dstrome
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
description: この記事では、Azure Monitor を使用して Microsoft Teams Rooms デバイスを統合的に管理する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fe523f4f4508dd81f5b7c007f91f32a43153dc42
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58592221"
---
# <a name="manage-microsoft-teams-rooms-devices-with-azure-monitor"></a>Azure Monitorを使用して Microsoft Teams Rooms デバイスをデプロイする

この記事では、Azure Monitor を使用して Microsoft Teams Rooms デバイスを統合的に管理する方法について説明します。

会議室のデバイスを管理するのに役立つ基本的なテレメトリを提供Microsoft Teams Azure Monitor を構成できます。 詳細[については、「Azure Monitor Microsoft Teams会議室](azure-monitor-plan.md)管理を計画する」および「Azure Monitor Microsoft Teams Rooms 管理をデプロイ[する」](azure-monitor-deploy.md)を参照してください。 管理ソリューションが成熟すると、追加のデータと管理機能を使用して、デバイスのパフォーマンスのより詳細なビューを作成できます。

## <a name="understand-the-log-entries"></a>ログ エントリを理解する

Microsoft Teams Rooms アプリが Windows イベント ログに対応する情報を記録すると、次のイベントの説明がイベント ログの説明フィールドに 5 分ごとに挿入されます。 このMicrosoft Monitoring Agent、これらのレコードを Azure Monitor の Log Analytics に渡します。このレコードは[、Azure Monitor](azure-monitor-deploy.md)を使用した Microsoft Teams Rooms 管理のデプロイに関するページで作成したダッシュボードに解析されます。 ダッシュボードを使用すると、個々のログ エントリを確認して、必要に応じてアクションのコースを決定できます。

イベントの 2000 と 3000 は、問題のデバイスが想定した動作を示します。 イベントの 2001 と 3001 は、問題が見つかったかどうかを示します。 イベント ID 4000 では、設定した基準計画や組織内の他のデプロイされたデバイスと比較して、予想よりも頻繁に表示される場合、アクションが必要な場合があります。

これらのイベントの説明を理解することで、問題を速やかに把握して、より適切なトラブルシューティングを行う機会が得られます。

| イベント &nbsp; ID &nbsp; レベル|イベント &nbsp; の動作&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|イベント &nbsp; の説明&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
|:---    |:---   |:---  |
| 2000  <br> 情報 | これは正常なハートビート イベントです。 5 分ごとに、Microsoft Teams 会議室は、Microsoft Teams または Skype for Business にサインインし、ネットワークとネットワーク接続Exchangeします。 <br> 3 つの要素すべてが当てはまる場合、デバイスがオフラインになるまで、または 1 つ以上の条件が満たされなくなるまで、イベント ID 2000 がイベント ログに 5 分ごとに書き込まれます。 | `{"Description":"Heartbeat is healthy.", "ResourceState":"Healthy", "OperationName":"Heartbeat", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@contoso.com",  "DisplayName":"Display name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10",  "IPv6Address":"IP v6 address"}` <br><br> この例では、すべてのハートビート条件が満たされ、Microsoft Teams Rooms デバイスが正常としてマークされています。 エラーがある場合は、アプリが記録するイベント ID は 2001 になります。 |
| 2001  <br> エラー | これはアプリのエラー イベントです。 5 分おきにMicrosoft Teams、Microsoft Teams にサインインするか、ネットワークとSkype for Business接続を使用してサインインExchangeされます。 1 つ以上の要因が当てはいない場合、デバイスがオフラインになるまで、またはすべての条件が再び満たされるまで、イベント ログに EventID 2001 が 5 分ごとに書き込まれます。  | `{"Description":"Network status : Healthy. Exchange status : Connected. Signin status: Unhealthy. ", "ResourceState":"Unhealthy", "OperationName":"Heartbeat", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br>  この例では、Microsoft Teams Rooms はネットワーク接続が正常であり、アプリが Exchange に接続されていることを確認しましたが、太字の部分はアプリが接続されていない状態を示しています。 これは、デバイスまたはホスト上の構成の問題である可能性があります。  <br> <br> [ネットワークの状態] が [正常] または [正常ではない] と表示されます。 状態が問題の場合は、ネットワークの問題が発生している可能性があります。またはデバイスが取り外されている可能性があります (ただし、Exchange および Microsoft Teams または Skype for Business エラーも発生している可能性があります)。  <br><br> [Exchange状態] は、[接続済み] または [切断済み]、[接続中]、自動情報開示エラー (最も一般的なエラー)、GeneralError、または ServerVersionNotSupported のいずれかとして表示されます。 この状態が Connecting の場合は、次の状態メッセージが送信されるまで待機して、その他のエラーについては、Exchange の問題解決の経験がある管理者にその問題について相談します。  <br><br>  サインイン _の状態_(アプリがサインインしたことを示す) は、[正常] または [正常ではない]_のいずれかとして表示されます_。 この状態が Unhealthy の場合は、技術者を派遣して詳しい調査を行ってください。 |
| 3000  <br> 情報 | このイベントは、ハードウェア チェックが実行され、正常な状態が検出されたと確認します。 5 分ごとにMicrosoft Teamsルーム ディスプレイ、マイク、スピーカー、カメラなどの構成済みのハードウェア コンポーネントが接続され、機能しているのが会議室によってチェックされます。 すべてのコンポーネントが正常な場合は、EventID 3000 がイベント ログに書き込まれます。 このイベントは、接続されているデバイスに問題がない限り、5 分ごとに書き込まれます。  <br> | `{"Description":"HardwareCheckEngine is healthy.",  "ResourceState":"Healthy", "OperationName":"HardwareCheckEngine",  "OperationResult":"Pass", "OS":"Windows 10",  "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@contoso.com", "DisplayName":"Display Name", "AppVersion":"1.0.38.0",  "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br> この例では、すべてのハードウェア チェックに合格しています。 エラーが発生した場合、アプリは代わりにイベント ID 3001 を記録します。 |
| 3001  <br> エラー イベント  | これはハードウェアのエラー イベントです。 Microsoft Teams Rooms アプリには、接続されているハードウェア コンポーネント (会議室の前面、マイク、スピーカー、カメラ) の正常性を 5 分ごとにチェックするプロセスがあります。 1 つ以上のコンポーネントが不健康な場合、EventID 3001 がイベント ログに書き込まれます。 このイベントは、デバイスの問題が修正されるまで 5 分ごとに書き込まれます。   | `{"Description":" Front of Room Display status : Unhealthy. Configured display count is 2. Real display count is 0. Conference Microphone status : Unhealthy. Conference Speaker status : Healthy. Default Speaker status : Healthy. Camera status : Healthy.", "ResourceState":"Unhealthy", "OperationName":"HardwareCheckEngine", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.1198", "Alias":"alias<span></span>@contoso.com", "DisplayName":"Yosemite conference room", "AppVersion":"2.0.58.0", "IPv4Address":"10.10.10.10", "IPv6Address":"IPv6Address", "IPv4Address2":"10.10.10.10"}` <br><br>  ハードウェア周辺機器は Healthy または Unhealthy のいずれかとして表示されます。 <br> この例では、2 つの前面の _ルーム_ ディスプレイが構成されています。現在、どちらも使用できません。 電話 _会議マイクの状態__は、_ いくつかの原因が考えられる、不健康です。 少なくとも 1 つのリソースがチェックに合格していなかったため、ResourceState が Unhealthy として表示されます。 技術者を派遣して詳しい調査を行ってください。 |
| 4000  <br> 情報  <br> | これはアプリの再起動イベントです。 アプリが再起動するたびに、このイベントを必ず Windows イベント ログに記録します。  <br> | `{"Description":"App restarts.", "ResourceState":"Healthy", "OperationName":"Restart", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@domain.com", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br> アプリは、さまざまな理由で再起動される場合があります。 同じビルと異なるビル内のデバイスの再起動頻度を比較します。 電力の変動や障害などの既知の問題は、インフラストラクチャの問題の手掛かりになる可能性があります。|

## <a name="related-topics"></a>関連トピック
 

[Azure Monitor を使用して Microsoft Teams Rooms 管理を計画する](azure-monitor-plan.md)

[Azure Monitor を使用して Microsoft Teams Rooms 管理をデプロイする](azure-monitor-deploy.md)
