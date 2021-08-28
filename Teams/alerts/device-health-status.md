---
title: Microsoft Teamsデバイスの監視とアラート
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: vapati
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: Microsoft Teams 管理センターの Teams 監視およびアラート機能を使用して、デバイスの正常性状態を事前に監視する方法Teamsします。
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 844dddfc04e1dc29311a237c3fc4f7ac41a1ce7f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58636762"
---
# <a name="microsoft-teams-device-health-monitoring"></a>Microsoft Teams正常性の監視

Microsoft Teams 管理センターでのデバイスの正常性の監視では、さまざまなデバイスの正常性を事前Teamsできます。 デバイスのオフライン状態を監視し、組織内の監視対象デバイスがオフラインの場合にリアルタイムでアラートを受信します。  

開始する前に、テナントにチーム/チャネルの作成アクセス許可が必要です。 [詳細については、 を参照してください](/microsoft-365/solutions/manage-creation-of-groups?view=o365-worldwide)。

## <a name="configure-device-state-rule"></a>デバイスの状態規則を構成する

1. 管理センターの左側のナビゲーションで、[通知] Microsoft Teams通知 **ルール] を&選択**  >  **します**。

   ![管理センターの [ルール] セクション](../media/select-rules.png)

2. [ルール **] ページで** 、[デバイスの状態 **ルール] を選択します**。

3. アラートを有効にするための状態ルールを構成するデバイスを選択します。

    ![Teamsデバイスの状態規則] ページを開きます。](../media/device-state-rule.png )

## <a name="interpret-the-rule-configuration"></a>ルールの構成を解釈する


|フィールド |説明  |
|--------|-------------|
|**ルールの種類**   |デバイス状態ルールは、効果的に管理するのに役立ちます。 Teams、デバイス管理の種類として分類されます。 今後、他の関連機能を監視するために、デバイス管理の種類のルールが追加される予定です (たとえば、デバイスの状態が不健康な場合や、デバイスのサインイン状態が含まれる場合があります)。|
|**状態**   |デバイスがオフラインになっている場合は、デバイスの正常性を監視できます。 [管理センター](../devices/device-management.md)でのデバイス管理のTeams確認してください。 |
|**対象**   |ルールの評価頻度に言及することで、デバイスの正常性状態を監視する頻度を指定できます。 既定では、オフラインになる場合、Teams デバイスはほぼリアルタイムで監視されます。 |
|**デバイス ユーザー**   |サインインしているユーザーに基づいて選択することで、プロアクティブなオフライン監視が必要なデバイスを指定できます。 詳細については、 [構成のデバイスの選択に関](#select-devices-for-configuration) するページを参照してください。 |
|**アクション**  > **チャネル アラート**   |[アクション] セクションで、アラートを取得するチーム チャネルを指定できます。 現在、通知の配信先として **、管理** アラートと通知という名前の既定のチームと **MonitoringAlerts** という名前のチャネルが作成されます。 <BR/> <BR/> テナントのグローバル管理者Teams管理者は、この既定のチームに自動的に追加されます。|
|**アクション**  > **Webhook**   |外部 webhook で通知を受け取る (省略可能)。 JSON 通知ペイロードが送信される webhook セクションで、外部パブリック webhook URL を指定します。 <BR/> <BR/>  webhook を介して通知ペイロードを組織内の他のシステムと統合して、カスタム ワークフローを作成できます。<br/><br/> 

**webhook の JSON ペイロード スキーマ:** <BR/><BR/>
<pre lang="json">{ <br/>    "type": "object",<br>    "properties": { <br/>      "AlertTitle": { "type": "string "} ,<br/>      "DeviceLoggedInUserId": { "type": "string" } ,<br/>      "DeviceId": { "type": "string" } , <br/>      "MetricValues": { <br/>            "type": "object",<br/>            "properties": { <br/>                 "DeviceHealthStatus": { "type": "string"} <br/>            } <br/>       } ,<br/>       "RuleName": { "type": "string"} ,<br/>       "RuleDescription": { "type": "string"} ,<br/>       "RuleFrequency": { "type": "string"} ,<br/>       "RuleType": { "type": "string"} ,<br/>       "TenantId": { "type": "string"} , <br/>       "RuleCondition": { "type": "string"} , <br/>       "AlertRaisedAt": { "type": "string"} <br/>    } <br/>} </pre> <br/> 

  **サンプル JSON ペイロード**:<br/> <br/> <pre lang="JSON">    { <br/>      "AlertTitle":"*sample_device_name* of *User_Name* has become offline",<br/>      "DeviceLoggedInUserId": *User_GUID* ,<br/>      "DeviceId": *Device_GUID* , <br/>      "MetricValues": { <br/>         DeviceHealthStatus": "offline" <br/>            }, <br/>        <br/>       "RuleName": "Device state rule" ,<br/>       "RuleDescription": ":"Alerts when device health status is detected as offline" ,<br/>       "RuleFrequency": "Real-time" ,<br/>       "RuleType": "Device Management" ,<br/>       "TenantId": *Tenant_GUID* , <br/>       "RuleCondition": "DeviceHealthStatus = Offline" , <br/>       "AlertRaisedAt": "2020-02-28T12:49:06Z" <br/>    }  </pre> <br/> 

## <a name="select-devices-for-configuration"></a>構成するデバイスを選択する

1. これらのデバイスにTeamsユーザーを選択して、監視するデバイスを選択できます。 [デバイス **ユーザー]** セクションから [ **追加] を** 選択します。

2. デバイスの正常性状態を監視する 1 つ以上のユーザーを選択します。

   ![デバイスの正常性状態ルールにユーザーを追加します。](../media/select-device-users.png )

   選択したユーザーの一覧が [デバイス ユーザー **] セクションに表示** されます。 このリストを変更するには、ユーザーを追加または削除します。

選択したユーザーの一覧で使用されるサインイン デバイスはすべて、オフラインの正常性状態を監視します。

## <a name="notifications-in-teams-client"></a>Teams クライアントでの通知

通知は、管理アラートと通知チームの **自動作成された MonitoringAlerts** **チャネルで配信** されます。

デバイスのオフライン通知には、次の情報を含めできます。

- オフラインのデバイス名。
- オフライン デバイスのユーザー。
- デバイスがオフラインにされた時刻。 (現時点では、時刻は UTC で表示されます)。
- アラートを発生したルールの種類。
- アラートが発生する理由。