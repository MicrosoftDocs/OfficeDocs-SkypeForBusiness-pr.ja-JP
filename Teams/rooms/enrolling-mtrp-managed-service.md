---
title: Pro Management ポータルへのアクセス
author: altsou
ms.author: altsou
manager: serdars
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Microsoft Teams Rooms Pro Management ポータルにアクセスする方法について説明します。
f1keywords: ''
ms.openlocfilehash: 64d2613b586a5c87f42b6a376a6c3a0d9ad3a799
ms.sourcegitcommit: 43db97b84ca70b1e6accfa7214d4106e4177a642
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2022
ms.locfileid: "68218081"
---
# <a name="accessing-the-pro-management-portal"></a>Pro Management ポータルへのアクセス

Teams Rooms Pro Management ポータルにアクセスするには、1 人以上のユーザーをマネージド サービス管理者に割り当て、そのユーザーを使用して登録手順を完了する必要があります。

## <a name="assign-users-to-the-managed-service-administrator-role"></a>マネージド サービス管理者ロールにユーザーを割り当てる

マネージド サービス管理者ロールにユーザーを割り当てるには、次の手順を実行します。

1. Microsoft 365 管理センターへのログインに使用したのと同じ管理者特権で、[Teams Rooms Pro Management ポータル](https://portal.rooms.microsoft.com/)にログインします。
2. **[設定の役割]** >  >  に移動し、[**マネージド サービス管理者**] を選択します。
3. **[マネージド サービス管理者**] で [**割り当て**] タブを選択し、[**追加**] を選択します。
4. ウィザードに従って割り当ての名前を指定し、割り当てに追加するユーザーを選択します。 割り当ては、すべての会議室とルーム グループに適用されます。
5. 割り当てウィザードの最後で、[割り当 **ての追加**] を選択します。

マネージド サービス管理者ロールが割り当てられているユーザーは、Teams Roomsの日常的な管理と監視を担当します。

マネージド サービス管理者ロールにユーザーを割り当てた後は、[Teams Rooms デバイスの登録](enroll-a-device.md)に進み、Teams Rooms デバイスをマネージド サービス ポータルに追加します。

<!-- ## Enroll a Teams Rooms device

 To enroll a device in the Teams Rooms Premium managed service, see [Monitoring device software installation](monitor-software-installation-guide.md).

2. Select on the **?** icon at the top right-hand corner of the portal to launch the help menu. The help menu includes an [Installation guide](https://portal.rooms.microsoft.com/docs/MMR%20Monitoring%20Software%20Installation%20Guide%20Feb%202021.pdf) containing detailed enrollment instructions:

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
