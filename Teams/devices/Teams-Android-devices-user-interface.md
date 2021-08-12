---
title: Microsoft Teams Android デバイスのユーザー インターフェイスを設定する
ms.author: mitressl
author: flinchbot
manager: leopaiv
audience: ITPro
appliesto:
- Microsoft Teams
ms.reviewer: ''
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Android デバイスでユーザー インターフェイスを設定するTeams説明します。
ms.openlocfilehash: d3b625e4a54a6a9dcb75d0d1518a65b3e91c23185736672458b0fa1bbd6d55e1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54327353"
---
# <a name="set-microsoft-teams-android-devices-user-interface"></a>Microsoft Teams Android デバイスのユーザー インターフェイスを設定する

Microsoft TeamsAndroid デバイスは、サインインしているアカウントに割り当てられたライセンスの種類に基づいて、特定のユーザー インターフェイスを表示できます。 この動作をオーバーライドして、表示されるインターフェイスを制御できます。 この記事では、既定のユーザー インターフェイスの選択方法と、Powershell ポリシーを使用してインターフェイスを変更する方法について説明します。

Android デバイスには、次の 3 種類Teamsがあります。

1. User
2. 共通領域
3. 会議

E3[](/microsoftteams/user-access)ライセンスや E5 ライセンスなどのユーザー ライセンスをアカウントに割り当てると、Teams デバイスには、ほとんどのユーザー シナリオで完全に機能する既定のエンド ユーザー インターフェイスが表示されます。 ただし、デバイスが共通エリア電話や会議室などの特定の機能を実行している場合は、これらの使用法に固有のユーザー インターフェイスがあります。

次の 3 つのイメージは、ユーザー アカウントに割り当てられたライセンスに基づいてユーザー インターフェイスがどのように変化するのか示しています。 最初の画像では、ユーザー アカウントに E5 ライセンスが割り当てられます。 これはユーザー ライセンスなので、デバイスには既定のエンド ユーザー インターフェイスが表示されます。

:::image type="content" source="../media/TeamsAndroidDevices-UserMode1.jpg" alt-text="ユーザー モード インターフェイス":::

この画像では、ユーザー アカウントに共通エリア電話ライセンス [が割り当てされています](/microsoftteams/set-up-common-area-phones)。 共通領域電話は、主に電話の送受信に使用されます。 そのため、ダイヤル パッドがディスプレイに表示されます。

:::image type="content" source="../media/TeamsAndroidDevices-CAP1.jpg" alt-text="共通領域電話インターフェイス":::

最後に、このイメージは、Rooms Standard ライセンスが割り当Microsoft Teamsユーザー アカウント[を示](/MicrosoftTeams/rooms/rooms-licensing)しています。 Teams会議室のライセンスは会議室または共有スペースで使用することを意図しています。そのため、ユーザー インターフェイスが変更された場合は、予定表ビューを表示して会議に簡単に参加できます。

:::image type="content" source="../media/TeamsAndroidDevices-Meeting.jpg" alt-text="会議インターフェイス":::

> [!NOTE]
> ユーザー インターフェイスを変更しても、他のライセンス機能を使用する機能には影響を与えかねない。 たとえば、Team Rooms ライセンスの既定のビューが予定表ビューである場合でも、アカウントが正しくライセンスを取得して構成されている場合でも、公衆交換電話網 (PSTN) の通話を発信および受信できます。

> [!IMPORTANT]
> 変更するインターフェイスの他の要素があります。 たとえば、エンド ユーザーが共通エリアの電話または会議室デバイスからサインアウトを行うのを防ぐため、これらのデバイスの [サインアウト] オプションは、管理者のアクセス許可が必要な設定メニューの一部に移動されます。

## <a name="override-automatic-user-interface-detection"></a>ユーザー インターフェイスの自動検出を上書きする

場合によっては、意図した使用に一致しないアカウントにライセンスを割り当てる場合があります。 たとえば、Android 上の会議室にサインインすることを意図したアカウントにユーザー ライセンスTeams割り当てできます。 既定では、会議室インターフェイスの代わりにエンド ユーザー インターフェイスが表示されます。 既定のインターフェイスを上書きするには、ポリシーに新Teams IP 電話を作成し[、](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps)そのアカウントに適用します。

> [!NOTE]
> ユーザー アカウントに割り当てられているライセンスには、少なくとも必要なユーザー インターフェイスと同じライセンス資格が必要です。 共通領域のライセンス電話、共通領域の電話ユーザー インターフェイスのみを許可します。 会議室ライセンスを使用すると、会議室と共通領域の電話ユーザー インターフェイスを使用できます。 E3 または E5 ライセンスは、すべてのサインイン モードをサポートします。

ライセンスの自動検出を上書きする方法の例を次に示します。 この例では、E3 ライセンスが割り当 conf-adams@contoso.com という名前の会議室リソース アカウントを想定しています。 このアカウントがサインインしている場合は、ユーザーに会議室のユーザー インターフェイスを表示します。

### <a name="create-a-new-policy-and-assign-to-user"></a>新しいポリシーを作成し、ユーザーに割り当てる

1. 次のコマンドレットをWindows PowerShellリモート セッションを開始し、Microsoft Teamsに接続します。

    ``` Powershell
    Connect-MicrosoftTeams
    ```

2. 新しい IP Teams IP 電話作成し、サインイン モードを "MeetingSignIn" に設定します。

   ``` Powershell
   New-CsTeamsIPPhonePolicy –Identity 'Meeting Sign in' –Description 'Meeting Sign In Phone Policy' -SignInMode 'MeetingSignIn'

   ```

3. これで、この新しいポリシーを会議室リソース アカウントに割り当てできます。

   ``` Powershell
   Grant-CsTeamsIPPhonePolicy –Identity 'conf-adams@contoso.com' –PolicyName 'Meeting Sign In'
   ```

会議室リソース アカウントにポリシーを付与した後、ポリシーの割り当てがレプリケートされるのを待つ必要があります。 また、デバイスからサインアウトしてサインインする必要があります。
