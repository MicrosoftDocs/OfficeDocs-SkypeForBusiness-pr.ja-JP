---
title: Teams Android デバイスのユーザー インターフェイスMicrosoft設定する
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
appliesto:
- Microsoft Teams
ms.reviewer: ''
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Devices
description: Teams Android デバイスでユーザー インターフェイスを設定する方法について説明します。
ms.openlocfilehash: 0efabef522a791a56ac187da9a63fab10e4ab3e9
ms.sourcegitcommit: 0d97dc6616b3d633564409e39c08311af1522705
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2022
ms.locfileid: "69392436"
---
# <a name="set-microsoft-teams-android-devices-user-interface"></a>Teams Android デバイスのユーザー インターフェイスMicrosoft設定する

Microsoft Teams Android デバイスでは、サインインしているアカウントに割り当てられているライセンスの種類に基づいて、特定のユーザー インターフェイスを表示できます。 この動作をオーバーライドし、表示するインターフェイスを制御できます。 この記事では、既定のユーザー インターフェイスを選択する方法と、PowerShell ポリシーを使用してインターフェイスを変更する方法について詳しく説明します。

Teams Android デバイスには、次の 3 種類のユーザー インターフェイスがあります。

1. ユーザー
2. 共通領域
3. 会議

E3 や E5 ライセンスなどのユーザー ライセンスをアカウントに [割り当てる](/microsoftteams/user-access) 場合、Teams デバイスには、ほとんどのユーザー シナリオで完全に機能する既定のエンド ユーザー インターフェイスが表示されます。 ただし、デバイスが共通エリア電話や会議室などの特定の機能を実行している場合、これらの用途には特定のユーザー インターフェイスがあります。

次の 3 つの画像は、ユーザー アカウントに割り当てられたライセンスに基づいてユーザー インターフェイスがどのように変化するかを示しています。

## <a name="end-user-interface"></a>エンド ユーザー インターフェイス

ユーザー アカウントには E5 ライセンスが割り当てられます。 これはユーザー ライセンスであるため、デバイスには既定のエンド ユーザー インターフェイスが表示されます。

:::image type="content" source="../media/teams-android-devices-usermode1.jpg" alt-text="ユーザー モード インターフェイス。":::

## <a name="common-area-interface"></a>共通エリア・インターフェース

この画像では、ユーザー アカウントに [Teams 共有デバイスのライセンスMicrosoft](/microsoftteams/teams-add-on-licensing/teams-shared-device-license)割り当てられます。 共通エリア電話は、主に通話の発信と受信に使用されます。 そのため、ダイヤル パッドがディスプレイに表示されます。

:::image type="content" source="../media/teams-android-devices-cap1.jpg" alt-text="共通エリア電話インターフェイス。":::

## <a name="meeting-interface"></a>会議インターフェイス

この画像は、[Microsoft Teams Rooms ライセンス](/MicrosoftTeams/rooms/rooms-licensing)が割り当てられているユーザー アカウントを示しています。 Teams Roomsライセンスは、会議室または共有スペースで使用することを目的としているため、ユーザー インターフェイスが変更され、予定表ビューを表示して会議に簡単に参加できるようになります。

:::image type="content" source="../media/teams-android-devices-meeting.jpg" alt-text="会議インターフェイス。":::

> [!NOTE]
> ユーザー インターフェイスを変更しても、他のライセンス機能を使用する機能には影響しません。 たとえば、Team Rooms ライセンスの既定のビューが予定表ビューであっても、アカウントが正しくライセンスされ、構成されている場合でも、公衆交換電話網 (PSTN) の電話をかけることができます。

> [!IMPORTANT]
> インターフェイスには、変更する他の要素があります。 たとえば、エンド ユーザーが共通エリアの電話または会議室デバイスからサインアウトできないようにするために、これらのデバイスの [サインアウト] オプションは、管理者のアクセス許可を必要とする設定メニューの一部に移動されます。

## <a name="override-automatic-user-interface-detection"></a>ユーザー インターフェイスの自動検出をオーバーライドする

場合によっては、目的の用途と一致しないアカウントにライセンスを割り当てることを選択できます。 たとえば、Android でTeams Roomsにサインインするためのアカウントにユーザー ライセンスを割り当てることができます。 既定では、会議室インターフェイスではなくエンド ユーザー インターフェイスが表示されます。 既定のインターフェイスをオーバーライドするには、新しい [Teams IP Phone ポリシー](/powershell/module/skype/new-csteamsipphonepolicy) を作成し、そのアカウントに適用します。

> [!NOTE]
> ユーザー アカウントに割り当てられたライセンスには、少なくとも目的のユーザー インターフェイスと同じライセンスエンタイトルメントが必要です。 **Microsoft Teams 共有デバイス** ライセンスでは、共通エリアの電話ユーザー インターフェイスのみが許可されます。 **Teams Rooms** ライセンスを使用すると、会議室と共通エリアの電話ユーザー インターフェイスを使用できます。 E3 または E5 ライセンスでは、すべてのサインイン モードがサポートされます。

ライセンスの自動検出をオーバーライドする方法の例を次に示します。 この例では、conf-adams@contoso.com という名前の会議室リソース アカウントに E3 ライセンスが割り当てられているとします。 このアカウントがサインインしている場合は、ユーザーに会議室のユーザー インターフェイスを表示させます。

### <a name="create-a-new-policy-and-assign-to-user"></a>新しいポリシーを作成し、ユーザーに割り当てる

1. リモート Windows PowerShell セッションを開始し、次のコマンドレットを使用してMicrosoft Teams に接続します。

    ``` Powershell
    Connect-MicrosoftTeams
    ```

2. 新しい Teams IP Phone ポリシーを作成し、サインイン モードを "MeetingSignIn" に設定します。

   ``` Powershell
   New-CsTeamsIPPhonePolicy –Identity 'Meeting Sign in' –Description 'Meeting Sign In Phone Policy' -SignInMode 'MeetingSignIn'

   ```

3. これで、この新しいポリシーを会議室リソース アカウントに割り当てることができます。

   ``` Powershell
   Grant-CsTeamsIPPhonePolicy –Identity 'conf-adams@contoso.com' –PolicyName 'Meeting Sign In'
   ```

ミーティング ルーム リソース アカウントにポリシーを付与したら、ポリシーの割り当てがレプリケートされるまで待つ必要があります。 また、デバイスからサインアウトし、もう一度サインインする必要があります。

## <a name="impact-on-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターへの影響

Microsoft Teams 管理センターを使用すると、Microsoft Teams デバイスを管理できます。 Teams 管理センターを使用したデバイスの管理の詳細については、「Microsoft [Teams でデバイスを管理](device-management.md)する」を参照してください。

Teams 管理センターでは、Teams 電話を管理できます。 電話は、ユーザー電話、共通エリア電話、電話会議電話の機能に基づいて、3 つのタブのいずれかにフィルター処理されます。

 :::image type="content" source="../media/teams-admin-center-phones-header.png" alt-text="Teams 管理センターの電話ヘッダー。":::

ユーザー インターフェイスの検出と同様に、Teams 電話は、電話にサインインするアカウントに割り当てられたライセンスに基づいて分類されます。 たとえば、**Microsoft Teams 共有デバイス** ライセンスが割り当てられているアカウントが電話にサインインした場合、その電話は既定の **[すべての電話**] セクションと [**共通エリア電話**] セクションの両方に表示されます。

電話を別のセクションに表示する場合は、電話に別のライセンスを割り当てるか、 [上記](#override-automatic-user-interface-detection)のように Teams IP Phone ポリシーを作成して割り当てることができます。
