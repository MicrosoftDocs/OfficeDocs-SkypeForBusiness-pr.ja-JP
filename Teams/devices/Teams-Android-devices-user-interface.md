---
title: Android Microsoft Teamsのユーザー インターフェイスを設定する
ms.author: mitressl
author: flinchbot
manager: leopaiv
audience: ITPro
appliesto:
- Microsoft Teams
ms.reviewer: ''
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
description: Android デバイスでユーザー インターフェイスを設定するTeams説明します。
ms.openlocfilehash: 4d17158a6d76dd0d735392c8a441ca184968897a
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2021
ms.locfileid: "58732456"
---
# <a name="set-microsoft-teams-android-devices-user-interface"></a>Android Microsoft Teamsのユーザー インターフェイスを設定する

Microsoft TeamsAndroid デバイスは、サインインしたアカウントに割り当てられているライセンスの種類に基づいて、特定のユーザー インターフェイスを表示できます。 この動作をオーバーライドし、表示されるインターフェイスを制御できます。 この記事では、既定のユーザー インターフェイスを選択する方法と、PowerShell ポリシーを使用してインターフェイスを変更する方法について説明します。

Android デバイスには、次の 3 種類Teamsがあります。

1. ユーザー
2. 共通領域
3. 会議

E3[](/microsoftteams/user-access)や E5 ライセンスなどのアカウントにユーザー ライセンスを割り当てると、Teams デバイスには、ほとんどのユーザー シナリオで完全に機能する既定のエンド ユーザー インターフェイスが表示されます。 ただし、デバイスが共通エリア電話や会議室などの特定の機能を実行している場合は、これらの使用方法に固有のユーザー インターフェイスがあります。

次の 3 つの画像は、ユーザー アカウントに割り当てられたライセンスに基づいてユーザー インターフェイスがどのように変化するのか示しています。 最初の画像では、ユーザー アカウントに E5 ライセンスが割り当てられます。 これはユーザー ライセンスなので、デバイスには既定のエンド ユーザー インターフェイスが表示されます。

:::image type="content" source="../media/TeamsAndroidDevices-UserMode1.jpg" alt-text="ユーザー モード インターフェイス。":::

この画像では、ユーザー アカウントに共通エリア電話ライセンス [が割り当て済みです](/microsoftteams/set-up-common-area-phones)。 一般的なエリアの電話は、主に電話の送受信に使用されます。 そのため、ダイヤル パッドがディスプレイに表示されます。

:::image type="content" source="../media/TeamsAndroidDevices-CAP1.jpg" alt-text="共通領域の電話インターフェイス。":::

最後に、この画像は、Microsoft Teams Rooms [Standard ライセンスが割り当てられているユーザー アカウントを示](/MicrosoftTeams/rooms/rooms-licensing)しています。 Teams会議室ライセンスは会議室または共有スペースで使用することを意図しています。そのため、予定表ビューを表示することで、ユーザー インターフェイスが変更して会議に簡単に参加できます。

:::image type="content" source="../media/TeamsAndroidDevices-Meeting.jpg" alt-text="会議インターフェイス。":::

> [!NOTE]
> ユーザー インターフェイスを変更しても、他のライセンスされた機能を使用する機能には影響を与え得ない。 たとえば、Team Rooms ライセンスの既定のビューが予定表ビューである場合でも、アカウントのライセンスが正しく設定されている場合でも、パブリック スイッチ電話網 (PSTN) 通話を発信および受信できます。

> [!IMPORTANT]
> 変更するインターフェイスの他の要素があります。 たとえば、エンド ユーザーが共通のエリア電話または会議室デバイスからサインアウトしなけれない場合、これらのデバイスの [サインアウト] オプションは、アクセスに管理者のアクセス許可を必要とする設定メニューの一部に移動されます。

## <a name="override-automatic-user-interface-detection"></a>ユーザー インターフェイスの自動検出をオーバーライドする

場合によっては、目的の使用に一致しないアカウントにライセンスを割り当てる場合があります。 たとえば、Android 上の Teams Rooms にサインインすることを意図したアカウントにユーザー ライセンスを割り当てる場合があります。 既定では、会議室インターフェイスの代わりにエンド ユーザー インターフェイスが表示されます。 既定のインターフェイスをオーバーライドするには、新しい TEAMS IP 電話[ポリシー](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps)を作成し、そのアカウントに適用します。

> [!NOTE]
> ユーザー アカウントに割り当てられたライセンスには、少なくとも目的のユーザー インターフェイスと同じライセンス資格が必要です。 共通領域のライセンス電話、共通領域の電話のユーザー インターフェイスのみを許可します。 会議室ライセンスを使用すると、会議室と共通領域の電話のユーザー インターフェイスを使用できます。 E3 または E5 ライセンスでは、すべてのサインイン モードがサポートされます。

ライセンスの自動検出をオーバーライドする方法の例を次に示します。 この例では、conf-adams@contoso.com という名前の会議室リソース アカウントに E3 ライセンスが割り当てられているとします。 このアカウントがサインインしている場合は、ユーザーに会議室のユーザー インターフェイスを表示します。

### <a name="create-a-new-policy-and-assign-to-user"></a>新しいポリシーを作成してユーザーに割り当てる

1. 次のコマンドレットをWindows PowerShellリモート セッションを開始し、Microsoft Teamsに接続します。

    ``` Powershell
    Connect-MicrosoftTeams
    ```

2. 新しい TEAMS IP 電話作成し、サインイン モードを "MeetingSignIn" に設定します。

   ``` Powershell
   New-CsTeamsIPPhonePolicy –Identity 'Meeting Sign in' –Description 'Meeting Sign In Phone Policy' -SignInMode 'MeetingSignIn'

   ```

3. これで、この新しいポリシーを会議室のリソース アカウントに割り当てできます。

   ``` Powershell
   Grant-CsTeamsIPPhonePolicy –Identity 'conf-adams@contoso.com' –PolicyName 'Meeting Sign In'
   ```

会議室のリソース アカウントにポリシーを付与した後、ポリシーの割り当てがレプリケートされるのを待つ必要があります。 また、デバイスからサインアウトし、もう一度サインインする必要があります。
