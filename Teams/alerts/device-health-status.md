---
title: Microsoft Teams デバイスの監視と通知
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
description: Microsoft Teams 管理センターで Teams の監視機能と通知機能を使用して、Teams デバイスの正常性状態を積極的に監視する方法について説明します。
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 03a57da7af783fa95e0bccbcb6a96f183b2fbb90
ms.sourcegitcommit: c6b630f9193d7f82f0416bd567a1de390d4b260f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819502"
---
# <a name="microsoft-teams-device-health-monitoring"></a><span data-ttu-id="d12dd-103">Microsoft Teams デバイスの正常性の監視</span><span class="sxs-lookup"><span data-stu-id="d12dd-103">Microsoft Teams device health monitoring</span></span>

<span data-ttu-id="d12dd-104">Microsoft Teams 管理センターのデバイス正常性監視では、さまざまな Teams デバイスの正常性を積極的に監視することができます。</span><span class="sxs-lookup"><span data-stu-id="d12dd-104">Device health monitoring in the Microsoft Teams admin center gives you an ability to proactively monitor the health of various Teams devices.</span></span> <span data-ttu-id="d12dd-105">デバイスのオフライン状態を監視し、組織内の監視対象デバイスがオフラインの場合に通知をリアルタイムで受信します。</span><span class="sxs-lookup"><span data-stu-id="d12dd-105">Monitor the offline state of a device and receive alerts in real time if the monitored device in your organization goes offline.</span></span>  

<span data-ttu-id="d12dd-106">開始する前に、テナントにチーム/チャネルの作成権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="d12dd-106">Before you start, you'll need the teams/channel creation permissions in your tenant.</span></span> <span data-ttu-id="d12dd-107">[詳細については、次の情報を参照してください](https://docs.microsoft.com/microsoft-365/solutions/manage-creation-of-groups?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="d12dd-107">[Learn More](https://docs.microsoft.com/microsoft-365/solutions/manage-creation-of-groups?view=o365-worldwide).</span></span>

## <a name="configure-device-state-rule"></a><span data-ttu-id="d12dd-108">デバイス状態ルールを構成する</span><span class="sxs-lookup"><span data-stu-id="d12dd-108">Configure device state rule</span></span>

1. <span data-ttu-id="d12dd-109">Microsoft Teams 管理センターの左側のナビゲーションで、[通知と通知&**選択**  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="d12dd-109">In the left navigation of the Microsoft Teams admin center, select **Notifications & alerts** > **Rules**.</span></span>

   ![管理センターの [ルール] セクション](../media/select-rules.png)

2. <span data-ttu-id="d12dd-111">[ルール **] ページで** 、[デバイスの **状態] ルールを選択します**。</span><span class="sxs-lookup"><span data-stu-id="d12dd-111">In the **Rules** Page, select **Device state rule**.</span></span>

3. <span data-ttu-id="d12dd-112">通知を有効にするための状態ルールを構成するデバイスを選択します。</span><span class="sxs-lookup"><span data-stu-id="d12dd-112">Select the device to configure the state rule for enabling alerts.</span></span>

    ![Teams デバイスの状態ルール ページ。](../media/device-state-rule.png )

## <a name="interpret-the-rule-configuration"></a><span data-ttu-id="d12dd-114">ルールの構成を解釈する</span><span class="sxs-lookup"><span data-stu-id="d12dd-114">Interpret the rule configuration</span></span>


|<span data-ttu-id="d12dd-115">フィールド</span><span class="sxs-lookup"><span data-stu-id="d12dd-115">Field</span></span> |<span data-ttu-id="d12dd-116">説明</span><span class="sxs-lookup"><span data-stu-id="d12dd-116">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="d12dd-117">**ルールの種類**</span><span class="sxs-lookup"><span data-stu-id="d12dd-117">**Rule type**</span></span>   |<span data-ttu-id="d12dd-118">デバイスの状態ルールは、効果的に管理するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d12dd-118">The device state rule helps you effectively manage.</span></span> <span data-ttu-id="d12dd-119">Teams デバイス。デバイス管理の種類として分類されます。</span><span class="sxs-lookup"><span data-stu-id="d12dd-119">Teams devices and is classified as a device management type.</span></span> <span data-ttu-id="d12dd-120">今後、他の関連する機能を監視するために、デバイス管理の種類のルールが追加される予定です (例には、デバイスの不健康なデバイスとサインイン状態が含まれる場合があります)。</span><span class="sxs-lookup"><span data-stu-id="d12dd-120">In the future, more rules of device management type will be available to monitor other related capabilities (examples may include: unhealthy device and the sign-in status of device).</span></span>|
|<span data-ttu-id="d12dd-121">**状態**</span><span class="sxs-lookup"><span data-stu-id="d12dd-121">**Condition**</span></span>   |<span data-ttu-id="d12dd-122">デバイスがオフラインの場合は、デバイスの正常性を監視できます。</span><span class="sxs-lookup"><span data-stu-id="d12dd-122">You can monitor the health of devices if they go offline.</span></span> <span data-ttu-id="d12dd-123">Teams[管理](https://docs.microsoft.com/microsoftteams/devices/device-management)センターでのデバイス管理の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="d12dd-123">[Learn more](https://docs.microsoft.com/microsoftteams/devices/device-management) about device management in Teams admin center.</span></span> |
|<span data-ttu-id="d12dd-124">**対象**</span><span class="sxs-lookup"><span data-stu-id="d12dd-124">**Scope**</span></span>   |<span data-ttu-id="d12dd-125">ルールの評価頻度を指定することで、デバイスの正常性状態を監視する頻度を指定できます。</span><span class="sxs-lookup"><span data-stu-id="d12dd-125">You can specify how frequently you want to monitor device health status by mentioning the rule evaluation frequency.</span></span> <span data-ttu-id="d12dd-126">既定では、オフラインになる場合、チーム のデバイスはほぼリアルタイムで監視されます。</span><span class="sxs-lookup"><span data-stu-id="d12dd-126">By default teams devices will be monitored in near real time if they go offline.</span></span> |
|<span data-ttu-id="d12dd-127">**デバイス ユーザー**</span><span class="sxs-lookup"><span data-stu-id="d12dd-127">**Device users**</span></span>   |<span data-ttu-id="d12dd-128">サインインしているユーザーに基づいてデバイスを選び、積極的にオフラインでの監視が必要なデバイスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="d12dd-128">You can specify which devices need proactive offline statue monitoring by selecting them based on signed-in users.</span></span> <span data-ttu-id="d12dd-129">詳細については、「構成 [のデバイスを選択する](#select-devices-for-configuration) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d12dd-129">Refer to [Select devices for configuration](#select-devices-for-configuration) for more details.</span></span> |
|<span data-ttu-id="d12dd-130">**アクション**  > **チャネル通知**</span><span class="sxs-lookup"><span data-stu-id="d12dd-130">**Actions** > **Channel alert**</span></span>   |<span data-ttu-id="d12dd-131">[アクション] セクションでは、通知を受け取るチーム チャネルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="d12dd-131">In the Actions section, you can specify teams channels you want to get alerts for.</span></span> <span data-ttu-id="d12dd-132">現在、管理者通知と通知 **という名前の** 既定のチームと **MonitoringAlerts** という名前のチャネルが作成され、通知が配信されます。</span><span class="sxs-lookup"><span data-stu-id="d12dd-132">Currently, a default team named **Admin Alerts and Notifications** and channel named **MonitoringAlerts** will be created where notifications will be delivered to.</span></span> <BR/> <BR/> <span data-ttu-id="d12dd-133">テナントのグローバル管理者と Teams 管理者は、この既定のチームに自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="d12dd-133">Global administrators and Teams administrators in your tenant will be automatically added to this default team.</span></span>|
|<span data-ttu-id="d12dd-134">**アクション**  > **Webhook**</span><span class="sxs-lookup"><span data-stu-id="d12dd-134">**Actions** > **Webhook**</span></span>   |<span data-ttu-id="d12dd-135">外部 Webhook で通知を受け取る (オプション)</span><span class="sxs-lookup"><span data-stu-id="d12dd-135">You can also get notifications with an external webhook (optional).</span></span> <span data-ttu-id="d12dd-136">JSON 通知ペイロードが送信される Webhook セクションで外部パブリック Webhook URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="d12dd-136">Specify an external public webhook URL in the webhook section where a JSON notification payload will be sent.</span></span> <BR/> <BR/>  <span data-ttu-id="d12dd-137">Webhook を介して通知ペイロードを組織内の他のシステムと統合し、カスタム ワークフローを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d12dd-137">The notification payload, via webhooks, can be integrated with other systems in your organization to create custom workflows.</span></span><br/><br/> 

<span data-ttu-id="d12dd-138">**Webhook の JSON ペイロード スキーマ:**</span><span class="sxs-lookup"><span data-stu-id="d12dd-138">**JSON payload schema for webhook:**</span></span> <BR/><BR/>
<span data-ttu-id="d12dd-139"><pre lang="json">{ <br/>    "type": "object",<br>    "properties": { <br/>      "AlertTitle": { "type": "string "} ,<br/>      "DeviceLoggedInUserId": { "type": "string" } ,<br/>      "DeviceId": { "type": "string" } , <br/>      "MetricValues": { <br/>            "type": "object",<br/>            "properties": { <br/>                 "DeviceHealthStatus": { "type": "string"} <br/>            } <br/>       } ,<br/>       "RuleName": { "type": "string"} ,<br/>       "RuleDescription": { "type": "string"} ,<br/>       "RuleFrequency": { "type": "string"} ,<br/>       "RuleType": { "type": "string"} ,<br/>       "TenantId": { "type": "string"} , <br/>       "RuleCondition": { "type": "string"} , <br/>       "AlertRaisedAt": { "type": "string"} <br/>    } <br/>} </pre> <br/></span><span class="sxs-lookup"><span data-stu-id="d12dd-139"><pre lang="json">{ <br/>    "type": "object",<br>    "properties": { <br/>      "AlertTitle": { "type": "string "} ,<br/>      "DeviceLoggedInUserId": { "type": "string" } ,<br/>      "DeviceId": { "type": "string" } , <br/>      "MetricValues": { <br/>            "type": "object",<br/>            "properties": { <br/>                 "DeviceHealthStatus": { "type": "string"} <br/>            } <br/>       } ,<br/>       "RuleName": { "type": "string"} ,<br/>       "RuleDescription": { "type": "string"} ,<br/>       "RuleFrequency": { "type": "string"} ,<br/>       "RuleType": { "type": "string"} ,<br/>       "TenantId": { "type": "string"} , <br/>       "RuleCondition": { "type": "string"} , <br/>       "AlertRaisedAt": { "type": "string"} <br/>    } <br/>} </pre> <br/></span></span> 

  <span data-ttu-id="d12dd-140">**JSON ペイロードの例**:</span><span class="sxs-lookup"><span data-stu-id="d12dd-140">**Sample JSON payload**:</span></span><br/> <br/> <pre lang="JSON">    { <br/>      <span data-ttu-id="d12dd-141">"AlertTitle":"*sample_device_name* of *User_Name* has become offline",</span><span class="sxs-lookup"><span data-stu-id="d12dd-141">"AlertTitle":"*sample_device_name* of *User_Name* has become offline",</span></span><br/>      <span data-ttu-id="d12dd-142">"DeviceLoggedInUserId": *User_GUID* ,</span><span class="sxs-lookup"><span data-stu-id="d12dd-142">"DeviceLoggedInUserId": *User_GUID* ,</span></span><br/>      <span data-ttu-id="d12dd-143">"DeviceId": *Device_GUID* , </span><span class="sxs-lookup"><span data-stu-id="d12dd-143">"DeviceId": *Device_GUID* , </span></span><br/>      "MetricValues": { <br/>         DeviceHealthStatus": "offline" <br/>            }, <br/>        <br/>       "RuleName": "Device state rule" ,<br/>       "RuleDescription": ":"Alerts when device health status is detected as offline" ,<br/>       "RuleFrequency": "Real-time" ,<br/>       "RuleType": "Device Management" ,<br/>       <span data-ttu-id="d12dd-144">"TenantId": *Tenant_GUID* , </span><span class="sxs-lookup"><span data-stu-id="d12dd-144">"TenantId": *Tenant_GUID* , </span></span><br/>       "RuleCondition": "DeviceHealthStatus = Offline" , <br/>       "AlertRaisedAt": "2020-02-28T12:49:06Z" <br/>    }  </pre> <br/> 

## <a name="select-devices-for-configuration"></a><span data-ttu-id="d12dd-145">構成するデバイスを選択する</span><span class="sxs-lookup"><span data-stu-id="d12dd-145">Select devices for configuration</span></span>

1. <span data-ttu-id="d12dd-146">監視する Teams デバイスを選択するには、それらのデバイスにサインインしているユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="d12dd-146">You can select Teams devices you want to monitor by selecting users signed in to those devices.</span></span> <span data-ttu-id="d12dd-147">[デバイス **ユーザー]** セクションから **[追加] を選択** します。</span><span class="sxs-lookup"><span data-stu-id="d12dd-147">Select **Add** from the **Device users** section.</span></span>

2. <span data-ttu-id="d12dd-148">デバイスの正常性状態を監視する 1 人または複数のユーザーを選択する</span><span class="sxs-lookup"><span data-stu-id="d12dd-148">Select one or more users for which you want to monitor device health state</span></span>

   ![デバイス正常性状態ルールにユーザーを追加します。](../media/select-device-users.png )

   <span data-ttu-id="d12dd-150">選択したユーザーのリストが [デバイス ユーザー **] セクションに表示** されます。</span><span class="sxs-lookup"><span data-stu-id="d12dd-150">The selected list of users shows in **Device users** section.</span></span> <span data-ttu-id="d12dd-151">ユーザーを追加または削除して、このリストを変更できます。</span><span class="sxs-lookup"><span data-stu-id="d12dd-151">You can modify this list by adding or removing users.</span></span>

<span data-ttu-id="d12dd-152">選択したユーザーのリストで使用されるサインイン デバイスはすべて、オフライン正常性状態を監視します。</span><span class="sxs-lookup"><span data-stu-id="d12dd-152">All the sign-in devices used by the selected list of users will be monitored for the offline health state.</span></span>

## <a name="notifications-in-teams-client"></a><span data-ttu-id="d12dd-153">Teams クライアントの通知</span><span class="sxs-lookup"><span data-stu-id="d12dd-153">Notifications in Teams client</span></span>

<span data-ttu-id="d12dd-154">通知は、管理者通知および通知チームの **自動作成 MonitoringAlerts** **チャネルで配信** されます。</span><span class="sxs-lookup"><span data-stu-id="d12dd-154">The notifications are delivered in the auto-created **MonitoringAlerts** channel of the **Admin Alerts and Notifications** Team.</span></span>

<span data-ttu-id="d12dd-155">デバイスのオフライン通知には、次の情報が含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d12dd-155">A device offline notification can include the following information:</span></span>

- <span data-ttu-id="d12dd-156">オフラインのデバイス名。</span><span class="sxs-lookup"><span data-stu-id="d12dd-156">The device name that's offline.</span></span>
- <span data-ttu-id="d12dd-157">オフライン デバイスのユーザー。</span><span class="sxs-lookup"><span data-stu-id="d12dd-157">The user of the offline device.</span></span>
- <span data-ttu-id="d12dd-158">デバイスがオフラインになった時刻。</span><span class="sxs-lookup"><span data-stu-id="d12dd-158">What time the device went offline.</span></span> <span data-ttu-id="d12dd-159">(現在、時刻は UTC で表示されます)。</span><span class="sxs-lookup"><span data-stu-id="d12dd-159">(Currently, the time is presented in UTC.)</span></span>
- <span data-ttu-id="d12dd-160">通知を発生したルールの種類。</span><span class="sxs-lookup"><span data-stu-id="d12dd-160">The type of rule that raised the alert.</span></span>
- <span data-ttu-id="d12dd-161">通知が発生する理由。</span><span class="sxs-lookup"><span data-stu-id="d12dd-161">Why an alert is raised.</span></span>
