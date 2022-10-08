---
title: Teams でアプリを管理するためのアプリ ポリシーの概要
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: conceptual
ms.service: msteams
ms.subservice: teams-apps
ms.date: 09/25/2022
search.appverid: ''
description: Microsoft Teams でアプリを管理するために使用されるアプリのアクセス許可ポリシーとセットアップ ポリシーについて説明します。
audience: admin
ms.localizationpriority: high
appliesto:
- Microsoft Teams
ms.collection:
- M365-collaboration
ms.openlocfilehash: 1c99cd9c0be3251a237b547cd8a2096d2d0e02af
ms.sourcegitcommit: d6e180791134426445a35fd485dcca18bde2006b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2022
ms.locfileid: "68494650"
---
# <a name="app-policies-used-to-manage-access-to-and-installation-of-apps"></a>アプリへのアクセスとインストールを管理するために使用されるアプリ ポリシー

Microsoft Teams では、アプリ ポリシーを使用して、アプリのアクセスとインストールの動作を管理します。 アプリ ポリシーは、Teams 管理者が次のアプリの動作を制御するのに役立ちます。

* 個々のユーザーまたはユーザーのグループに対してアプリのアクセスを構成します。 これは、管理者がエンド ユーザーごとに許可されているアプリを制御するのに役立ちます。

* 組織のニーズに関連するエンド ユーザー向けにこれらのアプリをピン留めします。 また、管理者は、ユーザーの介入なしにエンド ユーザー用のアプリをインストールできます。 エンド ユーザーが関連するアプリを簡単に使い始めるのに役立ちます。

* 管理者の承認のためにカスタム アプリを送信できる組織内の開発者を制御します。 カスタム アプリのアップロード機能へのアクセスを制御するのに役立ちます。

## <a name="app-permission-policies"></a>アプリのアクセス許可ポリシー

Teams 管理者は、アプリのアクセス許可ポリシーを使用して、組織内の各ユーザーが使用できるアプリを制御します。 すべてのユーザーに対していくつかのアプリを許可したり、特定のユーザー グループに対していくつかのアプリを許可したり、特定のユーザーに対して特定のアプリを許可したりできます。 アプリのアクセス許可ポリシーは、組織全体の設定と連携して機能し、個々のアプリの状態を許可またはブロックします。

アプリのアクセス許可ポリシーは、 [Teams で使用可能なすべての種類のアプリに適用されます](deploy-apps-microsoft-teams-landing-page.md)。 アプリのアクセス許可ポリシーを使用するシナリオの例を次に示します。

* アプリを最初に一部のユーザーに段階的にロールアウトし、最終的にすべてのユーザーに展開します。
* 人事部門のメンバーのみに対してカスタムの採用およびタレント管理アプリを許可し、他のすべての組織ユーザーに対してブロックします。

:::image type="content" source="media/app-permission-policy-trimmed.png" alt-text="アプリのアクセス許可ポリシーのスクリーンショット。" lightbox="media/app-permission-policy.png":::

詳細については、 [アプリのアクセス許可ポリシーを管理する方法に関する](teams-app-permission-policies.md)ページを参照してください。

## <a name="app-setup-policies"></a>アプリケーションの設定ポリシー

アプリセットアップ ポリシーを使用すると、Teams クライアントのユーザーが利用できるアプリの方法と場所を構成できます。 Teams クライアントのアプリ バーにピン留めするアプリを選択し、アプリを表示する順序を定義します。

アプリのピン留めまたはインストールは、組織内の目的のアプリの認識と導入を促進するのに役立ちます。 変更は、Web、デスクトップ、およびモバイル Teams クライアントに適用されます。

アプリのセットアップ ポリシーを使用するシナリオの例を次に示します。

* 人事チームのメンバー用にカスタムの採用およびタレント管理アプリをピン留めします。
* 組織のユーザーの固定済みコア アプリの順序を変更します。

:::image type="content" source="media/app-setup-policy-trimmed.png" alt-text="Teams 管理センターのアプリのセットアップ ポリシーのスクリーンショット。" lightbox="media/app-setup-policy.png":::

詳細については、 [アプリのセットアップ ポリシーを管理する方法に関する](teams-app-setup-policies.md)ページを参照してください。

### <a name="option-to-upload-custom-apps"></a>カスタム アプリをアップロードするオプション

組織は、組織固有の要件に応じてカスタム アプリの作成を委託する場合があります。 組織内の開発者は、組織の Teams の内部ユーザー向けのカスタム アプリを構築、テスト、デプロイできます。 アプリセットアップ ポリシーを使用して、組織内でカスタム アプリをアップロードできるユーザーを制御します。 組織全体の設定を使用して、エンド ユーザーがカスタム アプリを使用できるようにします。 アクセス許可ポリシーを使用して、特定のエンド ユーザーのみがカスタム アプリを使用できるようにします。

:::image type="content" source="media/custom-app-policy-trimmed.png" alt-text="組織全体の設定パネルで組織内のカスタム アプリを許可する方法を示すスクリーンショット。" lightbox="media/custom-app-policy.png":::

詳細については、 [カスタム アプリのポリシーと設定を管理する方法について説明](teams-custom-app-policies-and-settings.md)します。

## <a name="related-articles"></a>関連記事

* [ポリシーを使用して Teams を管理する](manage-teams-with-policies.md)
* [アプリのアクセス許可ポリシーを管理する](teams-app-permission-policies.md)
* [アプリのセットアップ ポリシーを管理する](teams-app-setup-policies.md)
* [カスタム アプリのポリシーと設定を管理する](teams-custom-app-policies-and-settings.md)
