---
title: 共存およびアップグレードを設定する
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: bjwhalen
search.appverid: MET150
description: 共存モードを選択し、他の共存の設定を設定するには、この資料が役立ちます。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 55ed1396cd9c16b96e7d230429ccf25c1802473e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32204637"
---
# <a name="setting-your-coexistence-and-upgrade-settings"></a>共存およびアップグレードを設定する

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

チームを使用するビジネス ユーザー向けに、Skype をアップグレードするとき、ユーザーにシームレスなプロセスにするためのいくつかのオプションがあります。 共存し、組織内のユーザーのすべての設定をアップグレードするためのオプションがあるか、組織内の 1 つまたは一連のユーザー設定の変更を行うことができます。 Skype のビジネス クライアント用の以前のバージョンがこれらの設定を無視可能性があることに注意してください。 ビジネス クライアントのバージョンの Skype の詳細については[ビジネスの Skype がダウンロードされページの更新](https://docs.microsoft.com/en-us/skypeforbusiness/software-updates)を参照してください。 

[マイクロソフト チームの理解とビジネスの共存と相互運用性の Skype](teams-and-skypeforbusiness-coexistence-and-interoperability.md)または[Skype のビジネスとの共存](coexistence-chat-calls-presence.md)を参照して使用するモードの種類の理解を深めるを取得できます。  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a>組織内のすべてのユーザーのアップグレード ・ オプションを設定します。

![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **、マイクロソフトのチーム管理センターを使用して**

1. 左側のナビゲーションでは、**組織全体の設定**に移動 > **のチームをアップグレード**します。 

2. **チームのアップグレード**] ページの上部には、次の変更する場合にも使用する場合。
    - **共存**モードを設定します。
        - **島**のビジネスとチームの両方の Skype を同時に使用できるようにする場合、この設定を使用します。
        - **ビジネスのみの Skype**の使用する場合は、ユーザーにのみ、この設定は、ビジネスの Skype を使用します。
        - **チームのみ**(プレビューでいくつかの組織) のユーザーがチームのみを使用する場合、この設定を使用します。 であっても、この設定でユーザー参加できますビジネス用の Skype でホストされている会議に注意してください。
    - **Skype チームが使用可能にアップグレードするため、ビジネス ユーザー向けに通知**を設定します。 これをオンにする場合は分かります、Skype のビジネス ユーザーのことではすぐにアップグレードするチームのアプリケーションにします。
    - **Skype のビジネス ・ ミーティングに参加するユーザーのアプリケーションを優先**に設定します。 この設定では、Skype のビジネス ・ ミーティングに参加するためにアプリケーションが使用されるかを決定し、共存モードの値に関係なく受取済です。
      - **Skype 会議アプリケーション**
      - **限られた機能とビジネスの Skype**
    - **ビジネス ユーザー向け Skype をバック グラウンドでチームのアプリケーションをダウンロード**するかどうかを設定します。  この設定は、Windows 上でビジネス用の Skype を実行しているユーザーのチームのアプリケーションをサイレント モードでダウンロードします。 ビジネス用の Skype での保留中のアップグレードの通知が有効になっている場合またはユーザーの共存モードは、チームのみの場合にのみ受け入れられます。
3. 変更を加えた後、[**保存**] をクリックします。

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a>組織内の 1 人のユーザーのアップグレード ・ オプションを設定します。

![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **、マイクロソフトのチーム管理センターを使用して**

1. 左側のナビゲーションでは、**ユーザー**に移動し、一覧からユーザーを選択します。 
2. **チームのアップグレード**をするには、[ユーザー**アカウント**] タブで [**編集**] をクリックします。
3. **共存モード**を設定することができます。 次のオプションから選択します。
     - **使用して組織全体の設定**- ユーザーが**組織全体**の設定の設定を使用する場合、この設定を使用します。 
     - **島**のビジネスとチームの両方の Skype を使用できるユーザーの場合、この設定を使用します。 
     - **Skype のみのビジネス**- ビジネスの Skype を使用するユーザーの場合、この設定を使用します。 
     - だけチームが**チームのみ**のユーザーを使用する場合、この設定を使用します。 ユーザーは Skype をビジネス ・ ミーティングに参加できます。
4. **使用して組織全体の設定**以外の**共存モード**を選択する場合は、ビジネス アプリケーションをチームへのアップグレードの準備中で Skype のユーザーの通知を有効にするオプションがあります。 ユーザーの通知を有効にするには、**ビジネス ユーザーの Skype の通知**オプションをオンにします。
5. 変更を加えた後、[**保存**] をクリックします。

### <a name="related-topics"></a>関連トピック
[旅を計画します。](upgrade-plan-journey.md)

[共存を理解し、Skype のビジネスとチームの旅をアップグレード](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス](migration-interop-guidance-for-teams-with-skype.md)
