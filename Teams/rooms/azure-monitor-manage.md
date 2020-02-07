---
title: Azure モニターを使用して Microsoft Teams 室のデバイスを管理する
ms.author: v-lanac
author: lanachin
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
description: この記事では、Azure モニターを使用して、統合された方法で Microsoft Teams 室のデバイスを管理する方法について説明します。
ms.openlocfilehash: 1b7038c1a2b46164e233e54af18875318d1c47d4
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41826125"
---
# <a name="manage-microsoft-teams-rooms-devices-with-azure-monitor"></a>Azure モニターを使用して Microsoft Teams 室のデバイスを管理する

この記事では、Azure モニターを使用して、統合された方法で Microsoft Teams 室のデバイスを管理する方法について説明します。

Skype 会議室デバイスを管理するための基本的なテレメトリを提供するように Azure モニターを構成することができます。 詳細については、「 [Azure モニターを使用して Microsoft teams のルーム管理を計画](azure-monitor-plan.md)する」および「 [azure monitor を使用して microsoft teams を管理](azure-monitor-deploy.md)する」をご覧ください。 管理ソリューションが成熟すると、追加のデータと管理機能を使用して、デバイスのパフォーマンスの詳細な表示を作成できます。

## <a name="understand-the-log-entries"></a>ログ エントリを理解する

Microsoft Teams の会議アプリが Windows イベントログで対応する情報を記録すると、次のイベントの説明が5分間隔で [イベントログの説明] フィールドに挿入されます。 Microsoft Monitoring Agent は、これらのレコードを、azure Monitor のログ分析に渡します。これにより、azure monitor で[Microsoft Teams のルーム管理を展開](azure-monitor-deploy.md)するときに作成したダッシュボードに解析されます。 ダッシュボードを使うと、個々のログエントリを確認して、必要に応じて操作のコースを特定できます。

イベント Id 2000 および3000は、問題のデバイスが予期したとおりに動作していることを示します。 イベント Id 2001 および3001は、問題が検出されたことを示します。 設定したベースラインまたは組織内の他の展開されたデバイスと比較して、イベント ID 4000 は、予期したよりも頻繁に表示される場合があります。

これらのイベントの説明を理解することで、問題を速やかに把握して、より適切なトラブルシューティングを行う機会が得られます。

| イベント&nbsp;ID&nbsp;レベル|イベント&nbsp;の動作&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|イベント&nbsp;の説明&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
|:---    |:---   |:---  |
| 2000  <br> 情報 | これは正常なハートビート イベントです。 Microsoft Teams ルームは、5分ごとに、microsoft Teams または Skype for Business にサインインしていることを確認し、ネットワークと Exchange の接続性を持ちます。 <br> 3つの要因がすべて真であれば、デバイスがオフラインになったり、1つ以上の条件が満たされなくなるまで、イベント ID 2000 が5分ごとにイベントログに書き込まれます。 | {"説明": "ハートビートは正常です。"、"ResourceState": "正常"、"OperationName": "ハートビート", "" OS ":" Pass "," 10.0.14393.693 ":" Windows 10 "," OSVersion ":" ","<span></span>alias ":" 1.0.38.0 "、" AppVersion ":" IPv4Address "、" appversion ":" "、" "@contoso:" 10.10.10.10 "、" IPv6Address " <br><br> この例では、すべてのハートビート条件が満たされ、Microsoft Teams の会議室のデバイスが正常にマークされています。 エラーがある場合は、アプリが記録するイベント ID は 2001 になります。 |
| 2001  <br> エラー | これはアプリのエラー イベントです。 Microsoft Teams の会議室は、5分ごとに microsoft teams または Skype for Business にサインインしていることを確認します。 1つまたは複数の要因が true でない場合は、デバイスがオフラインになるか、すべての条件が満たされるまで、イベントログに EventID 2001 が5分ごとに書き込まれます。  | {"Description":"Network status : Healthy. Exchange status : Connected. **Signin status: Unhealthy.** "," ResourceState ":" 異常 "," OperationName ":" 10.0.14393.693 "," OS ":" "が"、"OS": "1.0.38.0", "Appid": "IPv4Address"、"AppVersion": ""、"appversion": ""、"appversion": ""、"": "10.10.10.10"、""IPv6Address ":" ip v6 アドレス "} <br><br>  この例では、Microsoft Teams の会議室で、ネットワーク接続が正常であり、アプリが Exchange に接続されていることがわかりましたが、太字の部分は、アプリが接続されていないことを示しています。 これは、デバイスまたはホスト上の構成の問題である可能性があります。  <br> <br> ネットワークの状態は、正常または異常として表示されます。 状態が [問題] の場合は、ネットワークの問題が発生しているか、デバイスが切断されている可能性があります (ただし、Exchange および Microsoft Teams または Skype for Business のエラーがある可能性もあります)。  <br><br> Exchange の状態は、接続されているか、接続されていないか、または次のいずれかとして表示されます: 切断、接続、自動検出エラー (最も一般的なエラー)、一般エラー、または ServerVersionNotSupported。 この状態が Connecting の場合は、次の状態メッセージが送信されるまで待機して、その他のエラーについては、Exchange の問題解決の経験がある管理者にその問題について相談します。  <br><br>  サインイン状態 (アプリがサインインしていることを示す) は、"正常" または "異常" のどちらかと表示されます。 この状態が Unhealthy の場合は、技術者を派遣して詳しい調査を行ってください。 |
| 3000  <br> 情報 | このイベントは、ハードウェアのチェックが実行され、正常であることが検出されたことを確認します。 5分ごと Microsoft Teams の会議室のディスプレイ、マイク、スピーカー、およびカメラが接続され、機能していることを確認します。 すべてのコンポーネントが正常に稼働していれば、イベントログに EventID 3000 が書き込まれます。 このイベントは、接続されているデバイスに問題がある場合を除き、5分ごとに書き込まれます。  <br> | {"説明": "ハードウェアのチェックエンジンは正常に実行されています。", "ResourceState": "正常"、"OperationName": "ハードウェアチェックエンジン"、"OperationResult": "Pass", "OS": "10.0.14393.693", "Alias": ""<span></span>, "alias": "DisplayName"、"AppVersion": "1.0.38.0"、"appversion": ""、"IPv4Address": ""、"IPv6Address": "" @contoso  <br><br> この例では、すべてのハードウェア チェックに合格しています。 エラーが発生した場合、アプリはイベント ID 3001 を代わりに記録します。 |
| 3001  <br> エラーイベント  | これはハードウェアのエラー イベントです。 Microsoft Teams room アプリには、接続されているハードウェアコンポーネント (会議室、マイク、スピーカー、カメラなど) の正常性を5分間隔でチェックするプロセスがあります。 1つ以上のコンポーネントに問題がある場合は、イベントログに EventID 3001 が書き込まれます。 このイベントは、デバイスの問題が修正されるまで、5分間隔で書き込まれます。   | {"説明":**会議室の表示状態の正面: 異常。** Configured display count is 2. Real display count is 0. **Conference Microphone status : Unhealthy.** Conference Speaker status : Healthy. Default Speaker status : Healthy. カメラの状態: 正常。 "," ResourceState ":" 異常 "," OperationName ":" ハードウェアチェックエンジン "、" OperationResult ": Fail", "OS": "Windows 10", "OSVersion": "10.0.14393.1198", "<span></span>alias": "2.0.58.0"、"DisplayName"、"DisplayName": "IPv4Address": "10.10.10.10"、"IPv6Address": ""、"@contoso": ""、"IPv6Address": "10.10.10.10"、"IPv4Address2": "10.10.10.10"} <br><br>  ハードウェア周辺機器は Healthy または Unhealthy のいずれかとして表示されます。 <br> この例では、構成済みの正面の室内ディスプレイが 2 つあり、現在いずれも利用できません。 会議のマイクの状態は問題であり、いくつかの原因が考えられます。 少なくとも 1 つのリソースがチェックに合格していなかったため、ResourceState が Unhealthy として表示されます。 技術者を派遣して詳しい調査を行ってください。 |
| 4000  <br> 情報  <br> | これはアプリの再起動イベントです。 アプリが再起動するたびに、このイベントを必ず Windows イベント ログに記録します。  <br> | {"説明": "アプリは再起動します"、"ResourceState": "正常"、"OperationName": "再起動", "実行結果": "Pass", "OS": "10.0.14393.693"、"Alias": ""、"<span></span>alias": "1.0.38.0"、"AppVersion": "IPv4Address"、"appversion": ""、"" @domain: "10.10.10.10"、"IPv6Address": "" <br><br> アプリはさまざまな理由で再起動される場合があります。 同じ建物内および異なる建物内のデバイスの再起動頻度を比較します。 これにより、インフラストラクチャの問題が解決される可能性があるため、電力変動や障害などの既知の問題に留意してください。|

## <a name="see-also"></a>関連項目
 

[Azure モニターを使用して Microsoft Teams の会議室の管理を計画する](azure-monitor-plan.md)

[Azure モニターを使用して Microsoft Teams のルーム管理を展開する](azure-monitor-deploy.md)
