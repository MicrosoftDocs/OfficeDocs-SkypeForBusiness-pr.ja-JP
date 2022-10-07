---
title: 管理者に対するユーザー要求
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
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
description: 組織でブロックされているアプリの承認に対するエンド ユーザー要求を管理および構成する方法について説明します。
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: 382d3923d008f0bf70b2d9b9a4f3364709b4f2e1
ms.sourcegitcommit: 6e85f3f70f8488ab827ac352c0f324b6dfd4b856
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2022
ms.locfileid: "68377605"
---
# <a name="manage-user-requests"></a>ユーザー要求を管理する

組織内でブロックされているアプリは、エンド ユーザーの生産性とコラボレーションに影響を与える可能性があります。 エンド ユーザーは、ブロックされたアプリを使用することはできませんが、Teams ストアでそのようなアプリとその情報を表示し、管理者に承認を要求します。 要求を評価した後、アプリを許可するか、要求を却下するかを選択できます。

この機能は、組織内のアプリの需要に関するシグナルを提供します。 要求されたアプリごとに、要求の合計数を簡単に表示できます。 これにより、許可を評価するアプリに関する情報に基づいた意思決定を行うことができます。

ユーザーに対して許可またはブロックされているアプリの完全な制御を保持します。 アプリを許可することを選択した場合、アプリを管理するためのコントロールと UI は変わりません。

* 既定のオプションでは、ユーザー要求を Teams 管理センターに送信し、 [ユーザー要求を表示し、要求されたアプリを許可](#view-and-act-on-user-requests-in-teams-admin-center)できます。

   :::image type="content" source="media/user-request-blocked-apps.png" alt-text="管理者にブロックされたアプリの承認を要求するオプションを示すスクリーンショット。":::

* カスタマイズを使用すると、組織に最適な [エンド ユーザー エクスペリエンスを構成](#modify-the-default-setting-to-receive-end-user-requests) できます。 Teams アプリ ストアに表示される指示またはカスタム メッセージを指定できます。要求承認オプションを使用すると、ユーザーは組織固有の URL に誘導され、要求が収集されます。

   :::image type="content" source="media/user-request-blocked-apps-redirected.png" alt-text="管理者が許可アプリ要求 URL を組織固有の URL にリダイレクトしたときのストア内のアプリのエンド ユーザー エクスペリエンスを示すスクリーンショット。":::

## <a name="view-and-act-on-user-requests-in-teams-admin-center"></a>Teams 管理センターでユーザー要求を表示して操作する

既定の方法で受信したエンド ユーザー要求は、Teams 管理センターに表示されます。 要求を簡単に表示および管理できます。 エンド ユーザー要求を確認するには、通常のトリアージをお勧めします。 アプリを表示して許可するには、次の手順に従います。

1. Teams 管理センターにサインインし、**Teams アプリ**[**の管理アプリ**](https://admin.teams.microsoft.com/policies/manage-apps) > に移動します。

1. [ **ユーザーによる要求] 列を** 表示することを選択します。 列を並べ替えることもできます。

   :::image type="content" source="media/user-requests-tac.png" alt-text="Teams 管理センターのユーザー要求の列と並べ替え可能な列を示すスクリーンショット。" lightbox="media/user-requests-tac-expanded.png":::

1. 許可するアプリの詳細ページを開くには、アプリの名前を選択します。

1. [ **要求の管理**] を選択します。

   :::image type="content" source="media/apps-manage-user-requests.png" alt-text="アプリの詳細ページの [要求の管理] オプションを示すスクリーンショット。" lightbox="media/apps-manage-user-requests-expanded.png":::

1. ポップアップ ダイアログに表示されているように、次の手順の 1 つ以上に従います。 アプリを承認する手順は、アプリをブロックするために使用される方法によって異なります。

   * アクセス許可ポリシーを使用してアプリがブロックされている場合は、 [アクセス許可ポリシーを変更します](teams-app-permission-policies.md)。
   * すべてのユーザーに対してアプリがブロックされている場合は、[アプリを許可します](manage-apps.md#allow-and-block-apps)。
   * すべてのアプリがすべてのユーザーに対してブロックされている場合は、 [組織全体の設定を変更します](manage-apps.md#manage-org-wide-app-settings)。

エンド ユーザーは、Teams ストア内のアプリの **[追加]** オプションを表示して、アプリが許可されているかどうかを確認できます。 Teams 管理センターで要求を受信した後にアプリを許可すると、Teams は要求が処理されたことをエンド ユーザーに通知しません。 アプリを許可すると、要求カウンターは 0 にリセットされません。

## <a name="modify-the-default-setting-to-receive-end-user-requests"></a>エンド ユーザー要求を受信するように既定の設定を変更する

Teams は、ユーザーがアプリに承認を要求するための既定のメッセージを提供します。 既定の設定を変更して、手順、組織固有の URL、またはその両方を含むカスタム メッセージを追加できます。 Teams ストア内の各アプリに対する変更が表示されます。

カスタム メッセージを構成し、ユーザーを組織固有の URL にリダイレクトするには、次の手順に従います。

1. Teams 管理センターにサインインし、**Teams アプリ**[**の管理アプリ**](https://admin.teams.microsoft.com/policies/manage-apps) > に移動します。

1. 右上隅にある **[組織全体のアプリ設定**] を選択します。

1. Teams ストアにカスタム メッセージまたは命令を表示するには、[ **ユーザー要求の構成**] の下のテキスト フィールドにテキスト メッセージを入力します。 フィールドには 300 文字の制限があります。

1. ユーザー要求を収集するための組織固有の URL を指定するには、次の手順に従います。

   1. **[外部リンクへの要求のリダイレクト**] トグルをオンにします。
   1. 組織固有の URL を指定します。

      :::image type="content" source="media/user-request-config-org-wide-setting.png" alt-text="組織全体の設定 UI でユーザー要求の URL のカスタマイズを切り替えるスクリーンショット。":::

1. **[保存]** を選択します。

これを選択した場合、サードパーティのアプリを評価し、要求されたアプリを許可する方法は変わりません。

## <a name="dismiss-user-requests"></a>ユーザー要求を無視する

要求を却下するには、次の手順に従います。

1. ユーザー要求を無視するアプリの名前を選択します。
1. [ **要求の管理**] を選択します。
1. [ユーザー要求の管理] ダイアログで、[ **すべての要求を閉じる**] を選択します。

   :::image type="content" source="media/dismiss-user-requests-apps.png" alt-text="管理者は、アプリを許可することでユーザー要求を承認したり、要求を却下したりして、何のアクションも実行しません。":::

要求を却下しても、要求が処理されたことをエンド ユーザーに通知しません。 アプリを許可する要求を無視すると、管理センターの要求数は 0 にリセットされます。 また、要求を無視して数時間後に、エンド ユーザーは同じアプリを再度許可するように要求できます。

## <a name="related-article"></a>関連記事

* [サード パーティ製アプリを管理する方法の概要](manage-apps.md)。
