---
title: Azure のモニターを使用して Microsoft チームの会議室のデバイスを管理します。
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f8109905-3279-475f-a64b-31d37af48bfe
ms.collection: M365-voice
description: この資料では、Azure のモニターを使用して、統合されたエンド ・ ツー ・ エンドの方法でマイクロソフト チームの会議室のデバイスを管理する方法について説明します。
ms.openlocfilehash: 6e0fe9521248f75a670805f2f11f69fee1297779
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/30/2019
ms.locfileid: "31013074"
---
# <a name="manage-microsoft-teams-rooms-devices-with-azure-monitor"></a>Azure のモニターを使用して Microsoft チームの会議室のデバイスを管理します。

この資料では、Azure のモニターを使用して、統合されたエンド ・ ツー ・ エンドの方法でマイクロソフト チームの会議室のデバイスを管理する方法について説明します。

会議室のデバイス ( [Azure のモニターを使用して Microsoft チームの会議室を計画管理](../../plan-your-deployment/clients-and-devices/azure-monitor.md)され、 [Azure のモニターを使用してマイクロソフト チーム ルームの展開の管理](../../deploy/deploy-clients/azure-monitor.md)を参照してください Skype を管理するのに役立つ基本的な遠隔測定を提供する Azure のモニターを構成することができます。詳細情報)。 管理ソリューションが完成に近づくにつれて、追加のデータと管理機能を使用するにはデバイスのパフォーマンスの詳細なビューを作成します。

## <a name="understand-the-log-entries"></a>ログ エントリを理解する

次のイベントの説明は、5 分ごとにマイクロソフト チーム ルーム アプリケーションが Windows イベント ログに対応する情報を記録するときにイベント ログの説明] フィールドに挿入されます。 Microsoft の監視エージェントには、Azure モニターでは、 [Azure のモニターを使用してマイクロソフト チームの部屋の配置の管理](../../deploy/deploy-clients/azure-monitor.md)で作成したダッシュ ボードを解析し、ログの分析にこれらのレコードが渡されます。 ダッシュ ボードを使用する操作が必要な場合のコースを決定する個別のログ エントリを検索できます。 

イベント ID が 2000 および 3000 の場合は、問題になっているデバイスが、想定どおりに機能していることを示します。イベント ID が 2001 および 3001 の場合は問題が見つかったことを示します。イベント ID が 4000 の場合は、設定した基準または組織で展開された他のデバイスと比較して、より多く表示される場合は対処が必要になる可能性があります。

これらのイベントの説明を理解することで、問題を速やかに把握して、より適切なトラブルシューティングを行う機会が得られます。

| イベント&nbsp;ID&nbsp;レベル|イベント&nbsp;の動作&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|イベント&nbsp;の説明&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
|:---    |:---   |:---  |
| 2000  <br> 情報 | これは正常なハートビート イベントです。 5 分ごとに、マイクロソフト チームの会議室は、ビジネスの Skype にサインインし、ネットワークと Exchange の接続性を持つことを確認します。 <br> これらの 3 つの要素がすべて True である場合、デバイスがオフラインになるか、1 つ以上の条件が満たされなくなるまで、5 分間隔でイベント ID 2000 がイベント ログに書き込まれます。 | {[説明]:「ハートビートは正常な状態」、"ResourceState":「正常」、"OperationName":「ハートビート」、"OperationResult":「パス」、"OS":"Windows 10」、「OSVersion」:"10.0.14393.693"、"エイリアス":"エイリアス<span></span>@contoso.com"、"表示名":"表示名"、"AppVersion":「1.0.38.0」、"IPv4Address":「10.10.10.10」、"IPv6Address":「v6 の IP アドレス」} <br><br> この例では、ハートビートのすべての条件が満たされて、マイクロソフト チームの会議室のデバイスが正常な状態であるとマークされました。 エラーがある場合は、アプリが記録するイベント ID は 2001 になります。 |
| 2001  <br> エラー | これはアプリのエラー イベントです。 5 分ごとに、マイクロソフト チームの会議室では、それが署名されているビジネス用の Skype をネットワークと Exchange の接続をチェックします。 1 つ以上の要素が True でない場合、デバイスがオフラインになるか、すべての条件が再び満たされるようになるまで、イベント ID 2001 を 5 分間隔でイベント ログに書き込みます。  | {"Description":"Network status : Healthy. Exchange status : Connected. **Signin status: Unhealthy.** 」、"ResourceState":「異常」、"OperationName":「ハートビート」、"OperationResult":「失敗」、"OS":」Windows 10」、「OSVersion」:「10.0.14393.693」、「エイリアス」:""、「表示名」:"表示名"、"AppVersion":"1.0.38.0"、"IPv4Address":"10.10.10.10」、」IPv6Address":「ip v6 アドレス」} <br><br>  この例では、ネットワーク接続が良好な状態、アプリケーションは、Exchange に接続していたが太字で表示される部分は、ビジネスの Skype には、アプリケーションは接続されていないことを示しますマイクロソフト チームの会議室が決定されます。 これは、デバイスまたはホスト上の構成の問題である可能性があります。  <br> <br> Network status は、Healthy または Unhealthy と表示されます。この状態が Unhealthy の場合、ネットワークの問題があるかデバイスが接続されていない可能性があります (ただし、この場合は Exchange および Skype for Business のエラーが発生していることが考えられます)。<br><br> 接続または次のいずれかのいずれかとして Exchange の状態が表示されます: 切断、接続、AutodiscoveryError (最もよく見られるエラー)、GeneralError、または ServerVersionNotSupported。 この状態が Connecting の場合は、次の状態メッセージが送信されるまで待機して、その他のエラーについては、Exchange の問題解決の経験がある管理者にその問題について相談します。  <br><br>  (アプリが Skype for Business にサインインしていることを示す) Signin status は Healthy または Unhealthy と表示されます。この状態が Unhealthy の場合は、技術者を派遣して詳しい調査を行ってください。 |
| 3000  <br> 情報 | このイベントは、ハードウェアのチェックが実行され、正常な状態であることを確認します。 ルームのディスプレイ、マイク、スピーカー、およびカメラの前面などのハードウェア コンポーネントを構成するすべての 5 分マイクロソフト チームの会議室のチェックは、接続されている機能です。 すべてのコンポーネントが正常な場合、イベント ID 3000 をイベント ログに書き込みます。 このイベントは、接続済みのデバイスに問題がある場合を除いて、引き続き 5 分間隔で書き込まれます。  <br> | {[説明]:「HardwareCheckEngine は正常な状態」、"ResourceState":「正常」、"OperationName":"HardwareCheckEngine"、"OperationResult":「パス」、"OS":"Windows 10」、「OSVersion」:"10.0.14393.693"、"エイリアス":"エイリアス<span></span>@contoso.com"、"表示名":「表示名」、"AppVersion":「1.0.38.0」、"IPv4Address":「10.10.10.10」、"IPv6Address":「ip v6 アドレス」}  <br><br> この例では、すべてのハードウェア チェックに合格しています。 エラーがある場合、アプリケーションによってイベント ID 3001 が代わりに記録は。 |
| 3001  <br> エラー イベント  | これはハードウェアのエラー イベントです。 マイクロソフト チームの会議室のアプリケーションには、5 分ごと (部屋、マイク、スピーカー、カメラの前面) の接続されているハードウェア ・ コンポーネントの稼働状態をチェックするプロセスがあります。 1 つ以上のコンポーネントが正常でない場合、イベント ID 3001 をイベント ログに書き込みます。 このイベントは、デバイスの問題が修正されるまで、引き続き 5 分間隔で書き込まれます。   | {[説明]:"**フロントの部屋表示ステータス: 問題がある**。 Configured display count is 2. Real display count is 0. **Conference Microphone status : Unhealthy.** Conference Speaker status : Healthy. Default Speaker status : Healthy. カメラの状態: 正常な"、"ResourceState":"異常な"、"OperationName":"HardwareCheckEngine"、"OperationResult":"失敗"、"OS":"Windows 10」、「OSVersion」:"10.0.14393.1198"、"エイリアス":"エイリアス<span></span>@contoso.com"、"表示名":"ヨセミテ。会議室"、"AppVersion":「2.0.58.0」、"IPv4Address":「10.10.10.10」、"IPv6Address":"IPv6Address"、"IPv4Address2":「10.10.10.10」} <br><br>  ハードウェア周辺機器は Healthy または Unhealthy のいずれかとして表示されます。 <br> この例では、構成済みの正面の室内ディスプレイが 2 つあり、現在いずれも利用できません。 Conference Microphone status が Unhealthy ですが、考えられる原因がいくつかあります。 少なくとも 1 つのリソースがチェックに合格していなかったため、ResourceState が Unhealthy として表示されます。 技術者を派遣して詳しい調査を行ってください。 |
| 4000  <br> 情報  <br> | これはアプリの再起動イベントです。 アプリが再起動するたびに、このイベントを必ず Windows イベント ログに記録します。  <br> | {[説明]: アプリケーションの再起動」、「ResourceState」:「正常」、"OperationName":「再起動」、"OperationResult":「パス」、"OS":"Windows 10」、「OSVersion」:"10.0.14393.693"、"エイリアス":"エイリアス<span></span>@domain.com"、"表示名":「表示名」、"AppVersion":「1.0.38.0」、"IPv4Address":「10.10.10.10」、"IPv6Address":「ip v6 アドレス」} <br><br> さまざまな理由から、Skype のビジネス アプリケーションが再起動されます。 インフラストラクチャの問題への手がかりを提供する場合がありますこれは、既知の電圧変動や電源障害などの問題を念頭に置き、別の建物と同じ建物にはデバイスの再起動の頻度を比較します。|

## <a name="see-also"></a>関連項目
 

[Azure のモニターを使用して Microsoft チームの会議室の管理を計画します。](../../plan-your-deployment/clients-and-devices/azure-monitor.md)

[Azure のモニターを使用して Microsoft チームの会議室の管理を展開します。](../../deploy/deploy-clients/azure-monitor.md)