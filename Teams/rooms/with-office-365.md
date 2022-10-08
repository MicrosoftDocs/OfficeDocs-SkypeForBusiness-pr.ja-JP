---
title: 会議室と共有 Teams デバイスのリソース アカウントを作成する
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
ms.custom: seo-marvel-apr2020
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Microsoft Teams Rooms、Surface Hub でのTeams Rooms、Teams ディスプレイのホット デスクなど、会議室と共有デバイスのリソース アカウントを作成する方法については、この記事を参照してください。
ms.openlocfilehash: 1448496137088ce04dc087825e67f7d8b31afd80
ms.sourcegitcommit: 3ad7b46e31890fba7abe739138cd49527d5ca6b7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/05/2022
ms.locfileid: "68475499"
---
# <a name="create-and-configure-resource-accounts-for-rooms-and-shared-teams-devices"></a>会議室と共有 Teams デバイスのリソース アカウントを作成して構成する

この記事では、共有スペースとデバイスのリソース アカウントを作成する手順について説明します。また、Windows でのMicrosoft Teams Rooms、Android でのTeams Rooms、Surface Hub でのTeams Rooms、Teams ディスプレイでのホット デスク処理のリソース アカウントを構成する手順が含まれています。

Microsoft 365 リソース アカウントは、会議室やプロジェクターなどの特定のリソース専用のメールボックスと Teams アカウントです。 これらのリソース アカウントは、作成時に定義したルールを使用して会議出席依頼に自動的に応答できます。 たとえば、会議室などの共通リソースがある場合は、その会議室のリソース アカウントを設定し、予定表の可用性に応じて会議の招待を自動的に受け入れるか拒否します。 

すべてのリソース アカウントは、単一のMicrosoft Teams Roomsインストールに固有であるか、Teams がホットデスク処理の実装を表示します。

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

> [!NOTE]
> Microsoft Teams パネルを使用している場合、Teams Rooms リソース アカウントは、Teams Roomsおよび関連付けられた Teams パネルの両方にサインインします。

> [!NOTE]
> **Skype for Business** <br><br>
> リソース アカウントでSkype for Businessを操作できるようにする必要がある場合は、「Skype for Business Serverを使用[したMicrosoft Teams Roomsのデプロイ](with-skype-for-business-server-2015.md)」を参照してください。

## <a name="before-you-begin"></a>はじめに

### <a name="requirements"></a>要件

環境に応じて、リソース アカウントを作成するには、1 つ以上のロールが必要です。

|**環境**|**必要なロール**|
|-----|-----|
|Azure Active Directory  <br/> |グローバル管理者またはユーザー管理者  <br/> |
|Active Directory  <br/> |Active Directory Enterprise Admins、Domain Admins、またはユーザーを作成するための委任された権限を持っています。 Azure Active Directory Connect 同期権限。  <br/> |
|Exchange Online  <br/> |グローバル管理者または Exchange 管理者   <br/> |
|Exchange Server  <br/> |Exchange 組織の管理または受信者の管理   <br/> |

Teams Roomsのリソース アカウントを作成する場合、UPN はリソース アカウントの SMTP アドレスと一致する必要があります。 [Teams Roomsをデプロイする](requirements.md)前に、Microsoft Teams Rooms要件を確認してください。

### <a name="what-license-do-you-need"></a>必要なライセンスは何ですか?

[!INCLUDE [mtr-device-config-license-include](../includes/mtr-device-config-license-include.md)]

## <a name="create-a-resource-account"></a>リソース アカウントを作成する

[!INCLUDE [mtr-device-config-account-include](../includes/mtr-device-config-account-include.md)]

## <a name="configure-mailbox-properties"></a>メールボックスのプロパティを構成する

[!INCLUDE [mtr-device-config-mailbox-include](../includes/mtr-device-config-mailbox-include.md)]

## <a name="turn-off-password-expiration"></a>パスワードの有効期限を無効にする

[!INCLUDE [mtr-device-config-password-include](../includes/mtr-device-config-password-include.md)]

## <a name="assign-a-meeting-room-license"></a>会議室のライセンスを割り当てる

[!INCLUDE [mtr-device-config-assign-include](../includes/mtr-device-config-assign-include.md)]

## <a name="next-steps"></a>次の手順

### <a name="meeting-policies"></a>ミーティング ポリシー

[!INCLUDE [mtr-device-config-policies-include](../includes/mtr-device-config-policies-include.md)]

### <a name="calling"></a>通話

リソース アカウントでの呼び出しを有効にする一意の要件はありません。 通常のユーザーを有効にするのと同じ方法で、呼び出しに対してリソース アカウントを有効にします。

> [!NOTE]
> デバイス リソース アカウントに通話ポリシーを割り当てることで、共有デバイスのボイス メールをオフにすることをお勧めします。 詳細については、「 [Teams での通話と通話転送](../teams-calling-policy.md) 」を参照してください。

[!INCLUDE [mtr-device-config-calendar-include](../includes/mtr-device-config-calendar-include.md)]

## <a name="related-articles"></a>関連記事

[Microsoft Teams Rooms のアカウントを構成する](rooms-configure-accounts.md)

[Microsoft Teams Rooms を計画する](rooms-plan.md)

[Microsoft Teams Rooms をデプロイする](rooms-deploy.md)

[Microsoft Teams Rooms を管理する](rooms-manage.md)

[Microsoft Teams Rooms ライセンス](rooms-licensing.md)
