---
title: 共存およびアップグレードを設定する
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: bjwhalen
search.appverid: MET150
description: この記事では、共存モードを選択し、その他の共存設定を設定する方法について説明します。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: ce472ca1c5307dd8a5573ca076c58e32e2d41df9
ms.sourcegitcommit: 15fe483079847d24869e325eead35f252da8c7dd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/06/2019
ms.locfileid: "37571526"
---
# <a name="setting-your-coexistence-and-upgrade-settings"></a>共存およびアップグレードを設定する

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Skype for Business ユーザーをアップグレードして Teams を使用する場合、ユーザーのためのシームレスなプロセスを実現するためのいくつかのオプションが用意されています。 組織内のすべてのユーザーに対して共存とアップグレードの設定を同時に行うことができます。または、組織内の1人または複数のユーザーの設定を変更することもできます。 以前のバージョンの Skype for Business クライアントでは、これらの設定が認められない場合があることに注意してください。 Skype for Business クライアントのバージョンの詳細については、「 [skype For business のダウンロードと更新プログラム」ページ](https://docs.microsoft.com/en-us/skypeforbusiness/software-updates)を参照してください。 

[Microsoft Teams と skype For business の共存と](teams-and-skypeforbusiness-coexistence-and-interoperability.md)、skype for business との相互運用性や[共存](coexistence-chat-calls-presence.md)について理解しておくと、利用できるモードの種類をより深く理解できます。  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a>組織内のすべてのユーザーに対してアップグレードオプションを設定する

![Microsoft teams](media/teams-logo-30x30.png) **管理センターを使用し**た microsoft teams ロゴを示すアイコン

1. 左側のナビゲーションで、[**組織全体の設定** > ]**チームのアップグレード**に移動します。 

2. **チームのアップグレード**ページの上部で、次のような変更を行う場合は、次のように変更します。
    - **共存**モードを設定します。
        - [**諸島**]: ユーザーが Skype for Business と Teams の両方を同時に使用できるようにする場合は、この設定を使います。
        - **Skype For business のみ**-ユーザーが Skype for business のみを使用できるようにする場合は、この設定を使います。
        - **チームのみ**(一部の組織のプレビュー) では、ユーザーが teams のみを使用できるようにする場合は、この設定を使用します。 この設定でも、ユーザーは Skype for Business でホストされている会議に参加することができます。
    - **チームがアップグレード可能であることを Skype For business ユーザーに通知するよう**に設定します。 この設定を有効にすると、Skype for Business ユーザーに対して、チームアプリへのアップグレードが間もなく行われることが通知されます。
    - **ユーザーが Skype For business 会議に参加するための優先アプリを**設定します。 この設定では、Skype for Business 会議に参加するために使用するアプリを決定し、[共存] モードの値に関係なく有効になります。
      - **Skype 会議アプリ**
      - **機能が限定された Skype for Business**
    - **Skype For business ユーザーのバックグラウンドで Teams アプリをダウンロード**するかどうかを設定します。  この設定により、Windows で Skype for Business を実行しているユーザーの Teams アプリが自動的にダウンロードされます。 この機能は、ユーザーの共存モードが Teams のみの場合、または Skype for Business で保留中のアップグレードの通知が有効になっている場合にのみ受け入れられます。
3. 変更を加えた後、[**保存**] をクリックします。

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a>組織内の1人のユーザーに対してアップグレードオプションを設定する

![Microsoft teams](media/teams-logo-30x30.png) **管理センターを使用し**た microsoft teams ロゴを示すアイコン

1. 左側のナビゲーションで [**ユーザー**] に移動し、リストからユーザーを選びます。 
2. ユーザーの [**アカウント**] タブで、[**チームのアップグレード**] の下の [**編集**] をクリックします。
3. **共存モード**を設定できます。 次のオプションから選択します。
     - [**組織全体の設定を使用**する]: ユーザーが**組織全体**の設定の設定を使用する場合は、この設定を使います。 
     - [**諸島**]: ユーザーが Skype for Business と Teams の両方を使用できるようにする場合は、この設定を使います。 
     - **Skype For business のみ**-ユーザーが Skype for business を使用できるようにする場合は、この設定を使います。 
     - [**チームのみ**]-ユーザーが Teams のみを使用できるようにする場合は、この設定を使います。 ユーザーは、引き続き Skype for Business 会議に参加することができます。
4. [**組織全体の設定を使用**しない] を選択した場合、ユーザーの Skype for business アプリ**で、Teams**にアップグレードした通知を有効にするオプションが表示されます。 ユーザーに対してこの通知を有効にするには、[ **Skype For business ユーザーに通知**する] オプションをオンにします。
5. 変更を加えた後、[**保存**] をクリックします。

### <a name="related-topics"></a>関連トピック
[旅を計画する](upgrade-plan-journey.md)

[Skype for Business および Teams の共存とアップグレードの過程を理解する](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス](migration-interop-guidance-for-teams-with-skype.md)
