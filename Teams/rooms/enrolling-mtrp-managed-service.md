---
title: Teams Microsoft Teams Rooms Microsoft Teamsマネージド サービスに プレミアム Rooms デバイスを登録する
author: v-smandalika
ms.author: v-smandalika
manager: serdars
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 管理されたサービスの Microsoft Teams Rooms アカウントMicrosoft Teams登録するプレミアム説明します。
f1keywords: ''
ms.openlocfilehash: 79dee52cc9c814338c6c5dc4c91245155ef2fd41
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2022
ms.locfileid: "61766970"
---
# <a name="enroll-a-device-in-the-microsoft-teams-rooms-premium-managed-service"></a>管理対象サービスの Microsoft Teams Rooms プレミアムデバイスを登録する

Teams Rooms プレミアム マネージド サービスに Microsoft Teams Rooms デバイスを登録するには、1 人のユーザーを管理対象サービス管理者に割り当て、そのユーザーを使用して登録手順を完了する必要があります。

## <a name="assign-users-to-the-managed-service-administrator-role"></a>管理対象サービス管理者ロールにユーザーを割り当てる

マネージド サービス管理者ロールにユーザーを割り当てるには、次の手順を実行します。

1. Teams にログインプレミアム管理者特権で Teams [Rooms](https://portal.rooms.microsoft.com/)ポータルにログインMicrosoft 365 管理センター。
2. [ロール]  >  **設定設定**  >  **し、[** マネージド サービス管理者]**を選択します**。
3. [ **管理対象サービス管理者] で、[** 割り当て] タブ **を選択** し、[追加] を **選択します**。
4. ウィザードに従って割り当ての名前を付け、追加する必要があるユーザーを選択します。 課題は、すべてのルームとルーム グループに適用されます。
5. 割り当てウィザードの最後で、[割り当ての追加] **を選択します**。

マネージド サービス管理者ロールが割り当てられているユーザーは、マネージド サービス ポータルの Teams Rooms プレミアムの管理と監視を担当します。

管理対象サービス管理者ロールにユーザーを割り当てた後、[デバイスの登録][](#enroll-a-teams-rooms-device)セクションに進み、Teams Rooms デバイスをマネージド サービス ポータルに追加します。

## <a name="enroll-a-teams-rooms-device"></a>会議室デバイスTeams登録する

 管理対象サービスの Teams Rooms プレミアムデバイスを登録するには、デバイス ソフトウェアのインストールの監視[に関するページを参照してください](monitor-software-installation-guide.md)。

<!--2. Select on the **?** icon at the top right-hand corner of the portal to launch the help menu. The help menu includes an [Installation guide](https://portal.rooms.microsoft.com/docs/MMR%20Monitoring%20Software%20Installation%20Guide%20Feb%202021.pdf) containing detailed enrollment instructions:

    1. Review the **Pre-requisites** section in the Installation guide. Confirm that the URLs listed in the **URLs Required for Communication** list are added to your firewall's traffic allow list.
    2. Follow the instructions in the **Enabling TPM Settings** section to enable the Trusted Platform Module (TPM) functionality on your device.
    3. Follow the instructions in the **Adding Proxy Settings** section to configure your device to use your proxy gateway, if you have one.
    4. Follow the instructions in the **Process** section to install the monitoring agent software and configure the self enrollment key on your device.

3. After the monitoring agent and unique XML key are configured on your device, navigate to **Rooms** > room name > **Status**, and then select **Enroll**.

    > [!NOTE]
    > The Teams Rooms device will remain in the **Onboarding** state until a Managed Service Administrator enrolls the device using the portal.

    See [Monitoring device software installation](monitoring-software-installation-guide.md).

<!--## Link to Installation guide

The **Help** menu provides a link to the [Installation guide](https://portal.rooms.microsoft.com/docs/MMR%20Monitoring%20Software%20Installation%20Guide%20Feb%202021.pdf) which in turn provides the following information:

- Instructions on URLs that need to be allow-listed to serve to enable room telemetry to be sent to the managed service.
- Instructions for applying the Microsoft Teams Rooms Premium monitoring agent and unique XML key as part of enrolling a device in the managed service.
- Troubleshooting instructions.-->
