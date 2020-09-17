---
title: 共存およびアップグレードの設定
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
description: 組織内のすべてのユーザーに対して、または組織内の1人または複数のユーザーに対して、共存とアップグレードの設定を行う方法について説明します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: a20e8c355df4103980dc9da460d003382c721800
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940607"
---
# <a name="set-your-coexistence-and-upgrade-settings"></a>共存およびアップグレードの設定


Teams を使用するように Skype for Business ユーザーをアップグレードする場合、ユーザーにとってシームレスなプロセスにするためのオプションがいくつかあります。 組織内のすべてのユーザーの共存とアップグレードの設定を一度に行うオプションがあります。また、組織内の 1 人または複数のユーザーの設定を変更することもできます。 以前のバージョンの Skype for Business クライアントでは、これらの設定が優先されないことがあります。 Skype for Business クライアント バージョンの詳細については、「[Skype for Business のダウンロードと更新プログラム](https://docs.microsoft.com/skypeforbusiness/software-updates)」ページ を参照してください。 

[Microsoft Teams と skype For business の共存と](teams-and-skypeforbusiness-coexistence-and-interoperability.md)、 [skype for business と](coexistence-chat-calls-presence.md)の相互運用性や共存について理解しておくと、利用可能なモードについて理解を深めることができます。  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a>組織内のすべてのユーザーに対するアップグレード オプションの設定

![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターの使用**

1. [Microsoft Teams 管理センター](https://admin.teams.microsoft.com/)の左側のナビゲーションで、[**組織全体の設定**] チームの  >  **アップグレード**に移動します。 

2. [ **Teams のアップグレード** ] ページの上部で、必要に応じて次のオプションを変更します。
    - [**共存**] モードを設定します。
        - **アイランド** - ユーザーが Skype for Business と Teams の両方を同時に使用できるようにする場合は、この設定を使用します。
        - **Skype for Business のみ** - ユーザーが Skype for Business のみを使用する場合は、この設定を使用します。
        - **Skype for Business と Teams のコラボレーション** - グループ コラボレーション (チャネル) に Teams を使用するだけでなく、Skype for Business も使用する場合は、この設定を使用します。
        - **Skype for Business と Teams のコラボレーションと会議** - グループ コラボレーション (チャネル) と会議に Teams を使用するだけでなく、Skype for Business も使用する場合は、この設定を使用します。
        - **チームのみ** : ユーザーが Teams のみを使用できるようにする場合は、この設定を使います。 この設定を使用しても、Skype for Business でホストされている会議に参加できます。
        
    - [**Skype for Business ユーザーに Teams へのアップグレードが利用できることを通知します**] を設定します。 このオプションをオンにすると、Skype for Business ユーザーに間もなく Teams アプリにアップグレードされることが通知されます。
    - [**Skype for Business 会議に参加するユーザー向けの優先アプリ**] を設定します。 この設定では、Skype for Business 会議に参加するために使用されるアプリが決定され、共存モードの値に関係なく、適用されます。
      - **Skype 会議アプリ**
      - **機能が制限されている Skype for Business**
    - [**Skype for Business 向けにバックグラウンドで Teams アプリをダウンロードする**] かどうかを設定します。  この設定は、Windows 上で Skype for Business を実行しているユーザー向けに、自動的に Teams アプリをダウンロードします。 これは、ユーザーの共存モードが Teams のみになっているか、保留中のアップグレードの通知が Skype for Business アプリで有効になっている場合、適用されます。
3. 変更を完了したら、[**保存**] をクリックします。

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a>組織内の 1 人のユーザーに対するアップグレード オプションの設定

![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターの使用**

1. 左側のナビゲーションで、[**ユーザー**] に移動し、リストからユーザーを選択します。 
2. ユーザーの [**アカウント**] タブで、[**Teams アップグレード**] にある [**編集**] をクリックします。
3. [**共存**] モードを設定できます。 次のオプションから選択します。
     - **組織全体の設定を使用する** - ユーザーが**組織全体**の設定の設定を使用する場合は、この設定を使用します。 
     - **アイランド** - ユーザーが Skype for Business と Teams の両方を使用できるようにする場合は、この設定を使用します。 
     - **Skype for Business のみ** - ユーザーが Skype for Business を使用する場合は、この設定を使用します。
     - **Skype for Business と Teams のコラボレーション** - グループ コラボレーション (チャネル) に Teams を使用するだけでなく、Skype for Business も使用する場合は、この設定を使用します。
      - **Skype for Business と Teams のコラボレーションと会議** - グループ コラボレーション (チャネル) と会議に Teams を使用するだけでなく、Skype for Business も使用する場合は、この設定を使用します。
     - **Teams のみ** - ユーザーが Teams のみを使用する場合は、この設定を使用します。 ユーザーは引き続き Skype for Business 会議に参加できます。
4. [**組織全体の設定を使用する**] 以外の [**共存モード**] を選択した場合、ユーザーの Skype for Business アプリで Teams へのアップグレードが間もなく開始されるという通知を有効にするオプションがあります。 ユーザーに対してこの通知を有効にするには、[**Skype for Business ユーザーに通知する**] オプションをオンにします。
5. 変更を完了したら、[**保存**] をクリックします。

### <a name="related-topics"></a>関連項目
[Skype for Business から Teams へのアップグレード (IT 管理者向け)](upgrade-to-teams-on-prem-overview.md)

[行程を計画する](upgrade-plan-journey.md)

[Skype for Business と Teams の共存とアップグレードの行程について理解する](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス](migration-interop-guidance-for-teams-with-skype.md)
