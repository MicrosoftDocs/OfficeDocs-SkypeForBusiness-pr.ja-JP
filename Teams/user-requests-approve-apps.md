---
title: アプリを許可する管理者のユーザー要求
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
audience: admin
ms.collection:
- M365-collaboration
- m365-frontline
ms.reviewer: mhayrapetyan
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: 組織でブロックされているアプリを許可するようにエンド ユーザー要求を管理および構成する方法について説明します。
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: 122d41de6f1cb5ea67a5ce85ba9f8f7d02e26339
ms.sourcegitcommit: 41a75f1ba5ceb09f8db7d468aa41b63a89ab9c30
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2022
ms.locfileid: "67647541"
---
# <a name="manage-user-requests"></a>ユーザー要求を管理する

組織内でブロックするアプリは、エンド ユーザーの生産性とコラボレーションに影響を与える可能性があります。 Teams ストアで使用できるが、組織内でブロックされているアプリは、エンド ユーザーが使用することはできません。 ただし、常に情報を得るために、エンド ユーザーはブロックされたアプリを表示し、アプリの情報を表示し、サーバーのユース ケースを表示できます。 ユーザーは、要求を評価した後、Teams でこれらのアプリを使用するように管理者の承認を要求します。

この機能は、組織内のアプリの需要に関するシグナルを提供します。 アプリの要求の合計数を簡単に表示できます。 これは、組織内で許可するように評価するアプリに関する情報に基づいた決定を行うのに役立ちます。

ユーザーに対して許可またはブロックされているアプリの完全な制御を保持します。 アプリを許可することを選択した場合、アプリを管理するためのコントロールと UI は変わりません。

* 既定のオプションは、Teams 管理センターでユーザー要求を送信します。ユーザー [要求を表示し、要求されたアプリを許可](#view-user-requests)できます。

   :::image type="content" source="media/user-request-blocked-apps.png" alt-text="管理者にブロックされたアプリの承認を要求するオプションを示すスクリーンショット。":::

* カスタマイズを使用すると、組織に最適な [エンド ユーザー エクスペリエンスを構成](#modify-the-default-setting-to-receive-end-user-requests) できます。 Teams アプリ ストア内のブロックされたアプリのエンド ユーザーに表示されるカスタム命令を指定し、ユーザーを内部サイトに誘導して要求を収集できます。

   :::image type="content" source="media/user-request-blocked-apps-redirected.png" alt-text="管理者がアプリ要求の許可 URL を内部サイトにリダイレクトしたときの、ストア内のアプリのエンド ユーザー エクスペリエンスを示すスクリーンショット。":::

## <a name="modify-the-default-setting-to-receive-end-user-requests"></a>エンド ユーザー要求を受信するように既定の設定を変更する

カスタム メッセージを構成し、ユーザーを組織固有の URL にリダイレクトしてアプリの承認を要求するには、次の手順に従います。

1. Teams 管理センターにサインインし、**Teams アプリ** の **[[アプリ](https://admin.teams.microsoft.com/policies/manage-apps)** > の管理] ページにアクセスします。

1. 組織全体のアプリ設定を選択します。

1. Teams クライアント ストアにカスタム メッセージまたは命令を表示するには、ユーザー要求の構成にテキスト メッセージを入力します。

1. ユーザー要求を収集するための組織固有の URL を指定するには、次の操作を行います。

   1. [外部ツールへのリダイレクト要求] オプションを [オン] に変更します。
   1. 組織固有のカスタム URL を指定します。

      :::image type="content" source="media/user-request-config-org-wide-setting.png" alt-text="組織全体の設定 UI でアプリのブロックを解除するユーザー要求の URL のカスタマイズを切り替えるスクリーンショット。":::

1. **[保存]** を選択します。

## <a name="view-user-requests"></a>ユーザー要求を表示する

既定の方法で受信したエンド ユーザー要求は、Teams 管理センターに表示されます。 要求を簡単に表示および管理できます。 エンド ユーザー要求を確認するための定期的なトリアージをお勧めします。 アプリを表示して許可するには、次の手順に従います。

1. Teams 管理センターにサインインし、**Teams アプリ** の **[[アプリ](https://admin.teams.microsoft.com/policies/manage-apps)** > の管理] ページにアクセスします。

1. [ **ユーザーによる要求] 列を** 表示することを選択します。 列を並べ替えることもできます。

   :::image type="content" source="media/user-requests-tac.png" alt-text="Teams 管理センターのユーザー要求の列と並べ替え可能な列を示すスクリーンショット。" lightbox="media/user-requests-tac-expanded.png":::

1. 許可するアプリの詳細ページを開くには、アプリの名前を選択します。

1. [ **要求の管理**] を選択します。

   :::image type="content" source="media/apps-manage-user-requests.png" alt-text="アプリの詳細ページの [要求の管理] オプションを示すスクリーンショット。" lightbox="media/apps-manage-user-requests-expanded.png":::

1. ポップアップ ダイアログに表示されているように、次の手順の 1 つ以上に従います。 アプリを承認する手順は、アプリをブロックするために使用される方法によって異なります。

   * アクセス許可ポリシーを使用してアプリがブロックされている場合は、 [アクセス許可ポリシーを変更します](teams-app-permission-policies.md)。
   * すべてのユーザーに対してアプリがブロックされている場合は、[アプリを許可します](manage-apps.md#allow-and-block-apps)。
   * すべてのアプリがすべてのユーザーに対してブロックされている場合は、 [組織全体の設定を変更します](manage-apps.md#manage-org-wide-app-settings)。

1. 必要に応じて、カスタム構成を組織固有の URL に切り替えるには、[ユーザー要求の管理] ダイアログで [ユーザー要求の構成] リンクを選択します。 組織全体のアプリ設定ウィンドウが開き、 [エンド ユーザー要求エクスペリエンスを構成](#modify-the-default-setting-to-receive-end-user-requests)できます。

Teams 管理センターで要求を受信した後にアプリを許可した場合、Teams は要求が処理されたことをエンド ユーザーに通知しません。 ユーザーは Teams ストアでアプリを確認して、アプリが許可されているかどうかを確認できます。 アプリを追加するオプションは、ユーザーがアプリを許可した後で使用できます。 組織固有のメソッドを使用して要求を受信した後にアプリを許可する場合、エンド ユーザーに状態更新を提供するための内部メカニズムが適用されます。

アプリ要求の数を 0 にリセットするには、要求を無視します。 アプリを許可するだけでは、要求カウンターは 0 にリセットされません。

## <a name="dismiss-user-requests"></a>ユーザー要求を無視する

アプリを許可する要求を却下するには、次の手順に従います。

1. ユーザー要求を無視するアプリの名前を選択します。
1. **[要求の管理]** を選択し、ダイアログ ボックスで **[すべての要求を閉じる]** を選択します。

   :::image type="content" source="media/dismiss-user-requests-apps.png" alt-text="管理者は、アプリを許可することでユーザー要求を承認したり、要求を却下したりして、何のアクションも実行しません。":::

要求を却下しても、要求が処理されたことをエンド ユーザーに通知しません。 アプリを許可する要求を無視すると、管理センターの要求数は 0 にリセットされます。 また、数時間後に要求を却下した後、エンド ユーザーは同じアプリを再度許可するように要求できます。

## <a name="related-article"></a>関連記事

* [サード パーティ製アプリを管理する方法の概要](manage-apps.md)。
