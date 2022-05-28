---
title: デバイスのユーザー インターフェイスMicrosoft Teams Android設定する
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
description: Teams Android デバイスでユーザー インターフェイスを設定する方法について説明します。
ms.openlocfilehash: f97603fa4dcd173192f1fdf2e715c2f9792c2f03
ms.sourcegitcommit: 726df9ecac561bda18e349a5adab9bc85e52844d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2022
ms.locfileid: "65761459"
---
# <a name="set-microsoft-teams-android-devices-user-interface"></a>デバイスのユーザー インターフェイスMicrosoft Teams Android設定する

Microsoft Teams Androidデバイスは、サインインアカウントに割り当てられているライセンスの種類に基づいて、特定のユーザー インターフェイスを表示できます。 この動作をオーバーライドし、表示されるインターフェイスを制御できます。 この記事では、既定のユーザー インターフェイスを選択する方法と、Powershell ポリシーを使用してインターフェイスを変更する方法について詳しく説明します。

Teams Android デバイスには、次の 3 種類のユーザー インターフェイスがあります。

1. ユーザー
2. 共通領域
3. 会議

E3 や E5 ライセンスなどのアカウントに[ユーザー ライセンスを割り当てる](/microsoftteams/user-access)と、Teams デバイスに既定のエンド ユーザー インターフェイスが表示され、ほとんどのユーザー シナリオで完全に機能します。 ただし、デバイスが共通エリアの電話や会議室などの特定の機能を実行している場合は、これらの用途に固有のユーザー インターフェイスがあります。

次の 3 つの画像は、ユーザー アカウントに割り当てられたライセンスに基づいてユーザー インターフェイスがどのように変化するかを示しています。 

## <a name="end-user-interface"></a>エンド ユーザー インターフェイス 

ユーザー アカウントには E5 ライセンスが割り当てられます。 これはユーザー ライセンスであるため、デバイスには既定のエンド ユーザー インターフェイスが表示されます。

:::image type="content" source="../media/teams-android-devices-usermode1.jpg" alt-text="ユーザー モード インターフェイス。":::

## <a name="common-area-interface"></a>共通領域インターフェイス

この画像では、ユーザー アカウントに[共通領域電話ライセンス](/microsoftteams/set-up-common-area-phones)が割り当てられています。 共通エリア電話は、主に電話の発信と受信に使用されます。 そのため、ダイヤル パッドがディスプレイに表示されます。

:::image type="content" source="../media/teams-android-devices-cap1.jpg" alt-text="共通領域の電話インターフェイス。":::

## <a name="meeting-interface"></a>会議インターフェイス

この画像は、[Microsoft Teams Rooms Standard ライセンス](/MicrosoftTeams/rooms/rooms-licensing)が割り当てられているユーザー アカウントを示しています。 Teams Rooms ライセンスは会議室や共有スペースで使用することを目的としているため、ユーザー インターフェイスが変更され、予定表ビューを表示して会議に簡単に参加できるようになります。

:::image type="content" source="../media/teams-android-devices-meeting.jpg" alt-text="会議インターフェイス。":::

> [!NOTE]
> ユーザー インターフェイスを変更しても、他のライセンス機能を使用する機能には影響しません。 たとえば、Team Rooms ライセンスの既定のビューが予定表ビューであっても、アカウントのライセンスと構成が正しい場合でも、公衆交換電話網 (PSTN) の通話を発信および受信できます。

> [!IMPORTANT]
> 変更するインターフェイスの他の要素があります。 たとえば、エンド ユーザーが共通エリアの電話または会議室のデバイスからサインアウトできないようにするために、これらのデバイスの [サインアウト] オプションは、管理者のアクセス許可が必要な設定メニューの一部に移動されます。

## <a name="override-automatic-user-interface-detection"></a>自動ユーザー インターフェイス検出をオーバーライドする

場合によっては、目的の使用に一致しないアカウントにライセンスを割り当てることを選択できます。 たとえば、AndroidでTeams Roomsにサインインすることを目的としたアカウントにユーザー ライセンスを割り当てることができます。 既定では、会議室のインターフェイスの代わりにエンド ユーザー インターフェイスが表示されます。 既定のインターフェイスをオーバーライドするには、新しい[Teams IP 電話 ポリシー](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps)を作成し、そのアカウントに適用します。

> [!NOTE]
> ユーザー アカウントに割り当てられているライセンスには、目的のユーザー インターフェイスと少なくとも同じライセンス資格が必要です。 Common Area 電話 ライセンスでは、Common Area Phone ユーザー インターフェイスのみが許可されます。 会議室ライセンスを使用すると、会議室と共通エリアの電話ユーザー インターフェイスを使用できます。 E3 または E5 ライセンスでは、すべてのサインイン モードがサポートされます。

ライセンスの自動検出をオーバーライドする方法の例を次に示します。 この例では、conf-adams@contoso.com という名前の会議室リソース アカウントに E3 ライセンスが割り当てられているとします。 このアカウントがサインインしている場合は、ユーザーに会議室のユーザー インターフェイスを表示させます。

### <a name="create-a-new-policy-and-assign-to-user"></a>新しいポリシーを作成し、ユーザーに割り当てる

1. リモート Windows PowerShell セッションを開始し、次のコマンドレットを使用してMicrosoft Teamsに接続します。

    ``` Powershell
    Connect-MicrosoftTeams
    ```

2. 新しいTeams IP 電話 ポリシーを作成し、サインイン モードを "MeetingSignIn" に設定します。

   ``` Powershell
   New-CsTeamsIPPhonePolicy –Identity 'Meeting Sign in' –Description 'Meeting Sign In Phone Policy' -SignInMode 'MeetingSignIn'

   ```

3. これで、この新しいポリシーを会議室リソース アカウントに割り当てることができます。

   ``` Powershell
   Grant-CsTeamsIPPhonePolicy –Identity 'conf-adams@contoso.com' –PolicyName 'Meeting Sign In'
   ```

ポリシーを会議室リソース アカウントに付与したら、ポリシーの割り当てがレプリケートされるまで待つ必要があります。 また、デバイスからサインアウトし、もう一度サインインする必要もあります。

## <a name="impact-on-microsoft-teams-admin-center"></a>Microsoft Teams管理センターへの影響

Microsoft Teams管理センターでは、Microsoft Teams デバイスを管理できます。 Teams管理センターを使用してデバイスを管理する方法の詳細については、「[Microsoft Teamsでデバイスを管理する」を参照してください](device-management.md)。


Teams管理センターでは、Teams電話を管理できます。 電話は、その機能に基づいて 3 つのタブのいずれかにフィルター処理されます。ユーザーの電話、共通エリアの電話、会議用の電話です。 

 :::image type="content" source="../media/teams-admin-center-phones-header.png" alt-text="Teams管理センターの電話ヘッダー。":::

ユーザー インターフェイスの検出と同様に、Teams電話は、電話にサインインするアカウントに割り当てられたライセンスに基づいて分類されます。 たとえば、共通領域の電話ライセンスが割り当てられているアカウントが電話にサインインすると、その電話は既定の **[すべての電話** ] セクションと [ **共通エリアの電話** ] セクションの両方に表示されます。

別のセクションに電話を表示する場合は、別のライセンスを電話に割り当てるか、[前述](#override-automatic-user-interface-detection)のようにTeams IP 電話 ポリシーを作成して割り当てることができます。
