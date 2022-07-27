---
title: Microsoft Teams デバイスの監視とアラート
author: cazawideh
ms.author: czawideh
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
description: Microsoft Teams 管理センターで Teams の監視機能とアラート機能を使用して Teams デバイスの正常性状態をプロアクティブに監視する方法について説明します
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 81994e3462fe678c40506d6a11b343ba733995cd
ms.sourcegitcommit: 3266fde54b92a18865d666b98e4e7e8322b9dedc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/26/2022
ms.locfileid: "67023808"
---
# <a name="microsoft-teams-device-health-monitoring"></a>Microsoft Teams デバイスの正常性監視

Microsoft Teams 管理センターのデバイス正常性監視では、さまざまな Teams デバイスの正常性をプロアクティブに監視できます。 組織内の監視対象デバイスがオフラインになった場合は、デバイスのオフライン状態を監視し、リアルタイムでアラートを受信します。  

開始する前に、テナント内のチーム/チャネル作成のアクセス許可が必要です。 [詳細については、こちらを参照してください](/microsoft-365/solutions/manage-creation-of-groups?view=o365-worldwide)。

## <a name="configure-device-state-rule"></a>デバイスの状態規則を構成する

1. Microsoft Teams 管理センターの左側のナビゲーションで、[ **通知&アラート** > **ルール**] を選択します。

   ![管理センターの [ルール] セクション。](../media/select-rules.png)

2. [ **ルール]** ページで、[ **デバイスの状態規則**] を選択します。

3. アラートを有効にするための状態ルールを構成するデバイスを選択します。

    ![Teams デバイスの状態ルール ページ。](../media/device-state-rule.png )

## <a name="interpret-the-rule-configuration"></a>ルールの構成を解釈する


|フィールド |説明  |
|--------|-------------|
|**ルールの種類**   |デバイス状態ルールは、効果的に管理するのに役立ちます。 Teams デバイスであり、デバイス管理の種類として分類されます。 今後、デバイス管理の種類に関するその他のルールを使用して、他の関連機能を監視できます (たとえば、異常なデバイスやデバイスのサインイン状態など)。|
|**状態**   |デバイスがオフラインになると、デバイスの正常性を監視できます。 Teams 管理センターでのデバイス管理の[詳細について説明](../devices/device-management.md)します。 |
|**対象**   |ルールの評価頻度に言及することで、デバイスの正常性状態を監視する頻度を指定できます。 既定では、オフラインになると、チーム のデバイスはほぼリアルタイムで監視されます。 |
|**デバイス ユーザー**   |サインインしているユーザーに基づいてデバイスを選択することで、アクティブなオフラインの監視が必要なデバイスを指定できます。 詳細については、「 [デバイスを選択して構成する](#select-devices-for-configuration) 」を参照してください。 |
|**アクション** > **チャネル アラート**   |[アクション] セクションでは、アラートを取得するチーム チャネルを指定できます。 現在、**管理 アラートと通知** という名前の既定のチームと **MonitoringAlerts** という名前のチャネルが作成され、通知が配信されます。 <BR/> <BR/> テナント内のグローバル管理者と Teams 管理者は、この既定のチームに自動的に追加されます。|
|**アクション** > **Webhook**   |外部 Webhook で通知を受け取ることもできます (省略可能)。 JSON 通知ペイロードが送信される webhook セクションで、外部パブリック Webhook URL を指定します。 <BR/> <BR/>  Webhook を介して通知ペイロードを組織内の他のシステムと統合して、カスタム ワークフローを作成できます。<br/><br/> 

**Webhook の JSON ペイロード スキーマ:** <BR/><BR/>
<pre lang="json">{ <br/>    "type": "object",<br>    "properties": { <br/>      "AlertTitle": { "type": "string"} ,<br/>      "DeviceLoggedInUserId": { "type": "string" } ,<br/>      "DeviceId": { "type": "string" } , <br/>      "MetricValues": { <br/>            "type": "object",<br/>            "properties": { <br/>                 "DeviceHealthStatus": { "type": "string"} <br/>            } <br/>       } ,<br/>       "RuleName": { "type": "string"} ,<br/>       "RuleDescription": { "type": "string"} ,<br/>       "RuleFrequency": { "type": "string"} ,<br/>       "RuleType": { "type": "string"} ,<br/>       "TenantId": { "type": "string"} , <br/>       "RuleCondition": { "type": "string"} , <br/>       "AlertRaisedAt": { "type": "string"} <br/>    } <br/>} </pre> <br/> 

  **JSON ペイロードのサンプル**:<br/> <br/> <pre lang="JSON">    { <br/>      "AlertTitle":"*sample_device_name* of *User_Name* has become offline",<br/>      "DeviceLoggedInUserId": *User_GUID* ,<br/>      "DeviceId": *Device_GUID* , <br/>      "MetricValues": { <br/>         "DeviceHealthStatus": "offline" <br/>            }, <br/>        <br/>       "RuleName": "Device state rule" ,<br/>       "RuleDescription": "Alerts when device health status is detected as offline" ,<br/>       "RuleFrequency": "Real-time" ,<br/>       "RuleType": "Device Management" ,<br/>       "TenantId": *Tenant_GUID* , <br/>       "RuleCondition": "DeviceHealthStatus = Offline" , <br/>       "AlertRaisedAt": "2020-02-28T12:49:06Z" <br/>    }  </pre> <br/> 

## <a name="select-devices-for-configuration"></a>構成用のデバイスを選択する

1. 監視する Teams デバイスを選択するには、それらのデバイスにサインインしているユーザーを選択します。 [**デバイス ユーザー**] セクションから [**追加]** を選択します。

2. デバイスの正常性状態を監視する 1 人以上のユーザーを選択する

   ![デバイスの正常性状態ルールにユーザーを追加します。](../media/select-device-users.png )

   選択したユーザーの一覧が [ **デバイス ユーザー]** セクションに表示されます。 この一覧は、ユーザーを追加または削除して変更できます。

選択したユーザーの一覧で使用されるすべてのサインイン デバイスは、オフラインの正常性状態を監視します。

## <a name="notifications-in-teams-client"></a>Teams クライアントの通知

通知は、**管理 アラートと通知** チームの自動作成された **MonitoringAlerts** チャネルで配信されます。 デバイスがオフラインになるまで 15 分以内にアラートを受け取ります。 

デバイスオフライン通知には、次の情報を含めることができます。

- オフラインのデバイス名。
- オフライン デバイスのユーザー。
- デバイスがオフラインになった時刻。 (現在、時刻は UTC で表示されます)。
- アラートを発生させたルールの種類。
- アラートが発生する理由。
