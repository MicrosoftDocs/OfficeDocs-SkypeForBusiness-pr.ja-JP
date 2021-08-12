---
title: 共存およびアップグレードの設定
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: bjwhalen
search.appverid: MET150
description: 組織内のすべてのユーザー、または組織内の 1 人または一連のユーザーの共存とアップグレードの設定を一度に設定する方法について学習します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: bb4c5de3db934b9a14a58504b9a7b7b676a038051b347560f3f7121577849d1a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54345326"
---
# <a name="set-your-coexistence-and-upgrade-settings"></a>共存およびアップグレードの設定


Teams を使用するように Skype for Business ユーザーをアップグレードする場合、ユーザーにとってシームレスなプロセスにするためのオプションがいくつかあります。 組織内のすべてのユーザーの共存とアップグレードの設定を一度に行うオプションがあります。また、組織内の 1 人または複数のユーザーの設定を変更することもできます。 以前のバージョンの Skype for Business クライアントでは、これらの設定が優先されないことがあります。 Skype for Business クライアント バージョンの詳細については、「[Skype for Business のダウンロードと更新プログラム](/skypeforbusiness/software-updates)」ページ を参照してください。 

「Microsoft Teams と [Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md) の共存と相互運用性を理解する」または「Skype for Business との共存」を参照して、利用できるモードについて理解を深 [めさせることができます](coexistence-chat-calls-presence.md)。  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a>組織内のすべてのユーザーに対するアップグレード オプションの設定

![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターの使用**

1. Microsoft [Teams 管理センター の左側の](https://admin.teams.microsoft.com/)ナビゲーションで、[組織全体の設定] [Teams のアップグレード]  >  **に移動します**。 

2. Teams のアップグレード ページの上部 **で** 、必要に応じて次のオプションを変更します。

    - [**共存**] モードを設定します。
        - **アイランド** - ユーザーが Skype for Business と Teams の両方を同時に使用できるようにする場合は、この設定を使用します。
        - **Skype for Business のみ** - ユーザーが Skype for Business のみを使用する場合は、この設定を使用します。
        - **Skype for Business と Teams のコラボレーション** - グループ コラボレーション (チャネル) に Teams を使用するだけでなく、Skype for Business も使用する場合は、この設定を使用します。
        - **Skype for Business と Teams のコラボレーションと会議** - グループ コラボレーション (チャネル) と会議に Teams を使用するだけでなく、Skype for Business も使用する場合は、この設定を使用します。
        - **Teams のみ** - ユーザーに Teams のみを使用する場合は、この設定を使用します。 この設定を使用しても、Skype for Business でホストされている会議に参加できます。

          > [!IMPORTANT]
          > 次の両方の手順が完了した後でのみ、TeamsOnly モードをテナント全体に割り当てできます。
          >  - すべてのオンプレミス ユーザーは、Skype for Business Server のオンプレミス ツールセットMove-CsUserを使用して Teams にのみ移動されています。
          >  - Microsoft 365 を指す Skype for Business DNS レコードを更新しました。 
          >
          > 詳細については、「ハイブリッド構成を無効にして Teams のみ [への移行を完了する」を参照してください](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)。
        
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
3. [**共存**] モードを設定できます。 Teams 以外のモードは、オンプレミスの Skype for Business Server にホームされているユーザーにのみ適用できます。逆に、クラウドにホームされているユーザーだけが TeamsOnly モードを使用できます。  次のオプションから選択します。
     - **組織全体の設定を使用する** - ユーザーが **組織全体** の設定の設定を使用する場合は、この設定を使用します。 
     - **アイランド** - ユーザーが Skype for Business と Teams の両方を使用できるようにする場合は、この設定を使用します。 
     - **Skype for Business のみ** - ユーザーが Skype for Business を使用する場合は、この設定を使用します。
     - **Skype for Business と Teams のコラボレーション** - グループ コラボレーション (チャネル) に Teams を使用するだけでなく、Skype for Business も使用する場合は、この設定を使用します。
      - **Skype for Business と Teams のコラボレーションと会議** - グループ コラボレーション (チャネル) と会議に Teams を使用するだけでなく、Skype for Business も使用する場合は、この設定を使用します。
     - **Teams のみ** - ユーザーが Teams のみを使用する場合は、この設定を使用します。 ユーザーは引き続き Skype for Business 会議に参加できます。
4. [**組織全体の設定を使用する**] 以外の [**共存モード**] を選択した場合、ユーザーの Skype for Business アプリで Teams へのアップグレードが間もなく開始されるという通知を有効にするオプションがあります。 ユーザーに対してこの通知を有効にするには、[**Skype for Business ユーザーに通知する**] オプションをオンにします。
5. 変更を完了したら、[**保存**] をクリックします。

### <a name="related-topics"></a>関連項目
[行程を計画する](upgrade-plan-journey.md)

[Skype for Business と Teams の共存とアップグレードの行程について理解する](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス](migration-interop-guidance-for-teams-with-skype.md)

[オンプレミスの Skype for Business 環境を使用停止する](/skypeforbusiness/hybrid/decommission-on-prem-overview)
