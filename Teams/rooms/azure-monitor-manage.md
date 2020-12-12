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
localization_priority: Normal
ms.assetid: f8109905-3279-475f-a64b-31d37af48bfe
ms.collection:
- M365-collaboration
description: この記事では、Azure Monitor を使用して Microsoft Teams Rooms デバイスを統合的に管理する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 16105e77c8e66afa00f089d1337984b7e7d9a502
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662052"
---
# <a name="manage-microsoft-teams-rooms-devices-with-azure-monitor"></a>Azure Monitorを使用して Microsoft Teams Rooms デバイスをデプロイする

この記事では、Azure Monitor を使用して Microsoft Teams Rooms デバイスを統合的に管理する方法について説明します。

Skype 会議室デバイスの管理に役立つ基本的なテレメトリを提供するように Azure Monitor を構成できます。 詳細 [については、「Azure Monitor を使用して Microsoft Teams の会議室](azure-monitor-plan.md) 管理を計画する」を参照し、Azure Monitor を使用して [Microsoft Teams の会議室管理を](azure-monitor-deploy.md) 展開します。 管理ソリューションの成熟に合わせ、追加のデータと管理機能を使用して、デバイスのパフォーマンスの詳細なビューを作成できます。

## <a name="understand-the-log-entries"></a>ログ エントリを理解する

Microsoft Teams Rooms アプリが Windows イベント ログに対応する情報を記録すると、次のイベントの説明が 5 分ごとにイベント ログの説明フィールドに挿入されます。 Microsoft モニタリング エージェントは、これらのレコードを Azure Monitor のログ分析に渡します。これは [、Azure Monitor](azure-monitor-deploy.md)を使用して Microsoft Teams Rooms 管理を展開するで作成したダッシュボードにレコードを解析します。 ダッシュボードでは、個々のログ エントリを確認して、必要に応じてアクションのコースを決定できます。

イベント ID 2000 と 3000 は、問題のデバイスが期待通り動作している状態を示します。 イベント IDs 2001 と 3001 は、問題が見つかったかどうかを示します。 イベント ID 4000 では、設定した基準計画や組織内の他の展開されたデバイスと比較して、予想よりも頻繁に表示される場合、アクションが必要な場合があります。

これらのイベントの説明を理解することで、問題を速やかに把握して、より適切なトラブルシューティングを行う機会が得られます。

| イベント &nbsp; ID &nbsp; レベル|イベント &nbsp; の動作&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|イベント &nbsp; の説明&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
|:---    |:---   |:---  |
| 2000  <br> 情報 | これは正常なハートビート イベントです。 5 分ごとに、Microsoft Teams の会議室は、Microsoft Teams または Skype for Business にサインインし、ネットワークと Exchange の接続性を持っている場合に確認します。 <br> 3 つの要素すべてが満たされている場合、デバイスがオフラインになるまで、または 1 つ以上の条件が満たされなくなるまで、イベント ID 2000 が 5 分ごとにイベント ログに書き込まれます。 | {"Description":"Heartbeat is healthy.", "ResourceState":"Healthy", "OperationName":"Heartbeat", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias <span></span> @contoso.com", "DisplayName":"Display name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10.10", "IPv6Address":"IP v6 address"} <br><br> この例では、すべてのハートビート条件が満たされ、Microsoft Teams Rooms デバイスが正常としてマークされています。 エラーがある場合は、アプリが記録するイベント ID は 2001 になります。 |
| 2001  <br> エラー | これはアプリのエラー イベントです。 5 分ごとに、Microsoft Teams Rooms はネットワークと Exchange 接続を使用して Microsoft Teams または Skype for Business にサインインしているのを確認します。 1 つ以上の要因が満たされていない場合、デバイスがオフラインになるまで、またはすべての条件が再び満たされるまで、イベント ログに EventID 2001 が 5 分ごとに書き込まれます。  | {"Description":"Network status : Healthy. Exchange status : Connected. **Signin status: Unhealthy.** ", "ResourceState":"Unhealthy", "OperationName":"Heartbeat", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10.10", "IPv6Address":"ip v6 address"} <br><br>  この例では、Microsoft Teams Rooms はネットワーク接続が正常であり、アプリが Exchange に接続されたと判断しましたが、太字の部分はアプリが接続されていない状態を示しています。 これは、デバイスまたはホスト上の構成の問題である可能性があります。  <br> <br> ネットワークの状態は、正常または正常ではないと表示されます。 状態が不健康な場合は、ネットワークの問題が発生している可能性があります。またはデバイスが接続されていない可能性があります (ただし、Exchange および Microsoft Teams または Skype for Business のエラーも発生している可能性があります)。  <br><br> Exchange の状態は、[接続済み] または [切断済み]、[接続中]、自動情報開示エラー (最も一般的に表示されるエラー)、[GeneralError]、または [ServerVersionNotSupported] のいずれかとして表示されます。 この状態が Connecting の場合は、次の状態メッセージが送信されるまで待機して、その他のエラーについては、Exchange の問題解決の経験がある管理者にその問題について相談します。  <br><br>  サインイン状態 (アプリがサインイン済みであることを示す) は、[正常] または [正常ではない] として表示されます。 この状態が Unhealthy の場合は、技術者を派遣して詳しい調査を行ってください。 |
| 3000  <br> 情報 | このイベントは、ハードウェア チェックが実行され、正常に検出されたと確認します。 5 分ごとに、Microsoft Teams Rooms は、会議室の表示、マイク、スピーカー、カメラの前面などの構成済みハードウェア コンポーネントが接続され、機能している点を確認します。 すべてのコンポーネントが正常な場合は、EventID 3000 がイベント ログに書き込まれます。 このイベントは、接続されているデバイスに問題がない限り、5 分ごとに書き込まれます。  <br> | {"Description":"HardwareCheckEngine is healthy.", "ResourceState":"Healthy", "OperationName":"HardwareCheckEngine", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias <span></span> @contoso.com", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10.10", "IPv6Address":"ip v6 address"}  <br><br> この例では、すべてのハードウェア チェックに合格しています。 エラーが発生した場合、アプリは代わりにイベント ID 3001 を記録します。 |
| 3001  <br> エラー イベント  | これはハードウェアのエラー イベントです。 Microsoft Teams Rooms アプリには、接続されているハードウェア コンポーネント (会議室、マイク、スピーカー、カメラの前) の正常性を 5 分ごとにチェックするプロセスがあります。 1 つ以上のコンポーネントが不健康な場合は、EventID 3001 がイベント ログに書き込まれます。 このイベントは、デバイスの問題が修正されるまで、5 分ごとに書き込まれます。   | {"Description":" **Front of Room Display status : Unhealthy.** Configured display count is 2. Real display count is 0. **Conference Microphone status : Unhealthy.** Conference Speaker status : Healthy. Default Speaker status : Healthy. カメラの状態 : 正常","ResourceState":"Unhealthy", "OperationName":"HardwareCheckEngine", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.1198", "Alias":"alias <span></span> @contoso.com", "DisplayName":"Yosemite 会議室", "AppVersion":"2.0.58.0", "IPv4Address":"10.10.10.10", "IPv6Address":"IPv6Address", "IPv4Address2":""10.10.10.10"} <br><br>  ハードウェア周辺機器は Healthy または Unhealthy のいずれかとして表示されます。 <br> この例では、構成済みの正面の室内ディスプレイが 2 つあり、現在いずれも利用できません。 電話会議マイクの状態が不健康です。原因はいくつか考えられる可能性があります。 少なくとも 1 つのリソースがチェックに合格していなかったため、ResourceState が Unhealthy として表示されます。 技術者を派遣して詳しい調査を行ってください。 |
| 4000  <br> 情報  <br> | これはアプリの再起動イベントです。 アプリが再起動するたびに、このイベントを必ず Windows イベント ログに記録します。  <br> | {"Description":"App restarts.", "ResourceState":"Healthy", "OperationName":"Restart", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias <span></span> @domain.com", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10.10", "IPv6Address":"ip v6 address"} <br><br> さまざまな理由により、アプリが再起動される場合があります。 同じ建物と別の建物のデバイスの再起動頻度を比較します。 電源の変動や障害などの既知の問題は、インフラストラクチャの問題のヒントになる可能性があります。|

## <a name="related-topics"></a>関連項目
 

[Azure Monitor を使用して Microsoft Teams Rooms 管理を計画する](azure-monitor-plan.md)

[Azure Monitor を使用して Microsoft Teams Rooms 管理をデプロイする](azure-monitor-deploy.md)
