---
title: Microsoft Teamsデバイスの監視とアラート
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: vapati
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: Microsoft Teams 管理センターで Teams 監視およびアラート機能を使用して、デバイスの正常性状態を事前に監視するTeamsします。
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: cca6be8274d26efe661a7a928ebb568aa054cfab2fb62206ee8f3649b37f4ea0
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54336211"
---
# <a name="microsoft-teams-device-health-monitoring"></a>Microsoft Teamsの正常性監視

管理センターのデバイスMicrosoft Teams監視を使用すると、さまざまなデバイスの正常性を事前にTeamsできます。 デバイスのオフライン状態を監視し、組織内の監視対象デバイスがオフラインになった場合、リアルタイムでアラートを受信します。  

開始する前に、テナントに teams/channel 作成のアクセス許可が必要です。 [詳細を参照してください](/microsoft-365/solutions/manage-creation-of-groups?view=o365-worldwide)。

## <a name="configure-device-state-rule"></a>デバイス状態ルールの構成

1. 管理センターの左側のナビゲーションで、[通知Microsoft Teams通知 **ルール] &**  >  **選択します**。

   ![管理センターの [ルール] セクション](../media/select-rules.png)

2. [ルール] **ページで** 、[デバイスの **状態ルール] を選択します**。

3. 通知を有効にするための状態ルールを構成するデバイスを選択します。

    ![Teamsデバイスの状態ルール ページ。](../media/device-state-rule.png )

## <a name="interpret-the-rule-configuration"></a>ルール構成の解釈


|フィールド |説明  |
|--------|-------------|
|**規則の種類**   |デバイスの状態ルールは、効果的に管理するのに役立ちます。 Teams、デバイス管理の種類として分類されます。 今後、他の関連機能を監視するために、デバイス管理の種類のルールが追加されます (たとえば、デバイスの不健康なデバイスとサインイン状態が含まれる場合があります)。|
|**Condition**   |デバイスがオフラインになっている場合は、デバイスの正常性を監視できます。 [管理センター](../devices/device-management.md)でのデバイス管理のTeams詳細を確認します。 |
|**Scope**   |ルールの評価頻度を指定して、デバイスの正常性状態を監視する頻度を指定できます。 既定では、Teams デバイスがオフラインになる場合、ほぼリアルタイムで監視されます。 |
|**デバイス ユーザー**   |サインインしているユーザーに基づいてデバイスを選択することで、プロアクティブなオフライン監視が必要なデバイスを指定できます。 詳細については [、「構成用デバイスの選択」](#select-devices-for-configuration) を参照してください。 |
|**アクション**  > **チャネルアラート**   |[アクション] セクションで、アラートを取得する Teams チャネルを指定できます。 現在、Admin Alerts and **Notifications** という名前の既定のチームと **MonitoringAlerts** という名前のチャネルが作成され、通知が配信されます。 <BR/> <BR/> テナントのグローバル管理者Teams管理者は、この既定のチームに自動的に追加されます。|
|**アクション**  > **Webhook**   |外部 Webhook で通知を取得することもできます (オプション)。 JSON 通知ペイロードが送信される Webhook セクションで外部パブリック Webhook URL を指定します。 <BR/> <BR/>  通知ペイロードは、Webhooks を介して組織内の他のシステムと統合して、カスタム ワークフローを作成できます。<br/><br/> 

**Webhook の JSON ペイロード スキーマ:** <BR/><BR/>
<pre lang="json">{ <br/>    "type": "object",<br>    "properties": { <br/>      "AlertTitle": { "type": "string "} ,<br/>      "DeviceLoggedInUserId": { "type": "string" } ,<br/>      "DeviceId": { "type": "string" } , <br/>      "MetricValues": { <br/>            "type": "object",<br/>            "properties": { <br/>                 "DeviceHealthStatus": { "type": "string"} <br/>            } <br/>       } ,<br/>       "RuleName": { "type": "string"} ,<br/>       "RuleDescription": { "type": "string"} ,<br/>       "RuleFrequency": { "type": "string"} ,<br/>       "RuleType": { "type": "string"} ,<br/>       "TenantId": { "type": "string"} , <br/>       "RuleCondition": { "type": "string"} , <br/>       "AlertRaisedAt": { "type": "string"} <br/>    } <br/>} </pre> <br/> 

  **サンプル JSON ペイロード**:<br/> <br/> <pre lang="JSON">    { <br/>      "AlertTitle":"*sample_device_name* of *User_Name* has become offline",<br/>      "DeviceLoggedInUserId": *User_GUID* ,<br/>      "DeviceId": *Device_GUID* , <br/>      "MetricValues": { <br/>         DeviceHealthStatus": "offline" <br/>            }, <br/>        <br/>       "RuleName": "Device state rule" ,<br/>       "RuleDescription": ":"Alerts when device health status is detected as offline" ,<br/>       "RuleFrequency": "Real-time" ,<br/>       "RuleType": "Device Management" ,<br/>       "TenantId": *Tenant_GUID* , <br/>       "RuleCondition": "DeviceHealthStatus = Offline" , <br/>       "AlertRaisedAt": "2020-02-28T12:49:06Z" <br/>    }  </pre> <br/> 

## <a name="select-devices-for-configuration"></a>構成用のデバイスを選択する

1. 監視するデバイスTeams選択するには、それらのデバイスにサインインしているユーザーを選択します。 [デバイス **ユーザー]** セクションから **[追加] を** 選択します。

2. デバイスの正常性状態を監視する 1 つ以上のユーザーを選択する

   ![デバイスの正常性状態ルールにユーザーを追加します。](../media/select-device-users.png )

   選択したユーザーの一覧が [デバイス ユーザー **] セクションに表示** されます。 このリストは、ユーザーを追加または削除することで変更できます。

選択したユーザーの一覧で使用されるサインイン デバイスはすべて、オフラインの正常性状態を監視します。

## <a name="notifications-in-teams-client"></a>クライアント内Teams通知

通知は、管理者通知と通知チームの **自動作成された MonitoringAlerts** **チャネルで配信** されます。

デバイスのオフライン通知には、次の情報を含めできます。

- オフラインのデバイス名。
- オフライン デバイスのユーザー。
- デバイスがオフラインになされた時刻。 (現在、時刻は UTC で表示されます)。
- アラートを発生したルールの種類。
- アラートが発生する理由。