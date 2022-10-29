---
title: 管理者に対するユーザー要求
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: how-to
ms.service: msteams
ms.subservice: teams-apps
audience: admin
ms.date: 09/20/2022
ms.collection:
- M365-collaboration
- m365-frontline
- highpri
ms.reviewer: mhayrapetyan
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: 組織でブロックされているアプリの承認を求めるエンド ユーザー要求を管理および構成する方法について説明します。
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: 00c8659d82b4c633790f1b663d11d27e015146f1
ms.sourcegitcommit: e6182aa3b15346dc955333a2bc571565ef463a57
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2022
ms.locfileid: "68784392"
---
# <a name="manage-user-requests"></a>ユーザー要求を管理する

組織でブロックされているアプリは、エンド ユーザーの生産性とコラボレーションに影響する可能性があります。 エンド ユーザーは、ブロックされたアプリを使用することはできませんが、そのようなアプリとその情報を Teams ストアで表示し、管理者に承認を要求します。 要求を評価した後、アプリを許可するか、要求を無視するかを選択できます。

この機能により、組織内のアプリの需要に関するシグナルが提供されます。 要求されたアプリごとの要求の合計数を簡単に表示できます。 これは、許可するために評価するアプリに関する情報に基づいた意思決定を行うのに役立ちます。

ユーザーに対して許可またはブロックされるアプリの完全な制御を保持します。 アプリを許可する場合、アプリを管理するためのコントロールと UI は変わりません。

* 既定のオプションは、ユーザー要求を表示し、要求されたアプリを許可できる Teams 管理センター [にユーザー要求を](#view-and-act-on-user-requests-in-teams-admin-center)送信します。

   :::image type="content" source="media/user-request-blocked-apps.png" alt-text="ブロックされたアプリの承認を管理者に要求するオプションを示すスクリーンショット。":::

* カスタマイズを使用すると、組織に最適な [エンド ユーザー エクスペリエンスを構成](#modify-the-default-setting-to-receive-end-user-requests) できます。 Teams アプリ ストアに表示される指示またはカスタム メッセージを指定し、要求の承認オプションを使用して、ユーザーに組織固有の URL を送信して要求を収集できます。

   :::image type="content" source="media/user-request-blocked-apps-redirected.png" alt-text="管理者が許可アプリ要求 URL を組織固有の URL にリダイレクトするときの、ストア内のアプリのエンド ユーザー エクスペリエンスを示すスクリーンショット。":::

## <a name="view-and-act-on-user-requests-in-teams-admin-center"></a>Teams 管理センターでユーザー要求を表示して操作する

既定の方法で受信したエンド ユーザー要求は、Teams 管理センターに表示されます。 要求を簡単に表示および管理できます。 エンドユーザーの要求を確認するには、通常のトリアージをお勧めします。 アプリを表示して許可するには、次の手順に従います。

1. Teams 管理センターにサインインし、[**Teams アプリ** > ][**[アプリの管理]**](https://admin.teams.microsoft.com/policies/manage-apps) に移動します。

1. [ **ユーザー別の要求** ] 列を表示することを選択します。 列を並べ替えることもできます。

   :::image type="content" source="media/user-requests-tac.png" alt-text="Teams 管理センターのユーザー要求の列と、並べ替えが可能であることを示すスクリーンショット。" lightbox="media/user-requests-tac-expanded.png":::

1. 許可するアプリの詳細ページを開くには、アプリの名前を選択します。

1. [ **要求の管理] を選択します**。

   :::image type="content" source="media/apps-manage-user-requests.png" alt-text="アプリの詳細ページの [要求の管理] オプションを示すスクリーンショット。" lightbox="media/apps-manage-user-requests-expanded.png":::

1. ポップアップ ダイアログに表示される次の手順の 1 つ以上に従います。 アプリを承認する手順は、アプリをブロックするために使用される方法によって異なります。

   * アクセス許可ポリシーを使用してアプリがブロックされている場合は、 [アクセス許可ポリシーを変更します](teams-app-permission-policies.md)。
   * すべてのユーザーに対してアプリがブロックされている場合は、[アプリを許可します](manage-apps.md#allow-and-block-apps)。
   * すべてのユーザーに対してすべてのアプリがブロックされている場合は、 [組織全体の設定を変更](manage-apps.md#manage-org-wide-app-settings)します。

エンド ユーザーは、Teams ストア内のアプリの **[追加]** オプションを表示して、アプリが許可されているかどうかを確認できます。 Teams 管理センターで要求を受信した後にアプリを許可すると、Teams は、要求が処理されたことをエンド ユーザーに通知しません。 アプリを許可すると、要求カウンターは 0 にリセットされません。

## <a name="modify-the-default-setting-to-receive-end-user-requests"></a>エンド ユーザー要求を受信するように既定の設定を変更する

Teams では、ユーザーがアプリへの承認を要求するための既定のメッセージが提供されます。 既定の設定を変更して、手順、組織固有の URL、またはその両方を含むカスタム メッセージを追加できます。 変更は、Teams ストア内のアプリごとに表示されます。

カスタム メッセージを構成し、ユーザーを組織固有の URL にリダイレクトするには、次の手順に従います。

1. Teams 管理センターにサインインし、[**Teams アプリ** > ][**[アプリの管理]**](https://admin.teams.microsoft.com/policies/manage-apps) に移動します。

1. 右上隅にある [ **組織全体のアプリ設定**] を選択します。

1. Teams ストアにカスタム メッセージまたは命令を表示するには、[ **ユーザー要求の構成**] の下のテキスト フィールドにテキスト メッセージを入力します。 フィールドの文字数は 300 文字です。

1. ユーザー要求を収集するための組織固有の URL を指定するには、次の手順に従います。

   1. [ **外部リンクへの要求のリダイレクト** ] トグルをオンにします。
   1. 組織固有の URL を指定します。

      :::image type="content" source="media/user-request-config-org-wide-setting.png" alt-text="組織全体の設定 UI でユーザー要求の URL のカスタマイズを切り替えるスクリーンショット。":::

1. **[保存]** を選択します。

これを選択した場合、サード パーティ製アプリを評価し、要求されたアプリを許可する方法は変わりません。

## <a name="dismiss-user-requests"></a>ユーザー要求を無視する

要求を無視するには、次の手順に従います。

1. ユーザー要求を無視するアプリの名前を選択します。
1. [ **要求の管理] を選択します**。
1. [ユーザー要求の管理] ダイアログで、[ **すべての要求を無視する**] を選択します。

   :::image type="content" source="media/dismiss-user-requests-apps.png" alt-text="管理者は、アプリを許可することでユーザー要求を承認したり、要求を却下したりして、何のアクションも実行しません。":::

要求を無視した場合、要求が処理されたことをエンド ユーザーに通知しません。 アプリを許可する要求を無視すると、管理センターの要求数は 0 にリセットされます。 また、数時間後に要求を無視した後、エンド ユーザーは同じアプリの許可を再度要求できます。

## <a name="related-article"></a>関連記事

* [サード パーティ製アプリを管理する方法の概要](manage-apps.md)。
