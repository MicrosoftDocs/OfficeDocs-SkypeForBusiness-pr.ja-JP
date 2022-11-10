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
ms.openlocfilehash: 8e059199d4963004e287b456c98bb80717f849b3
ms.sourcegitcommit: 22f66e314e631b3c9262c5c7dc5664472f42971e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2022
ms.locfileid: "68912436"
---
# <a name="know-about-policies-to-manage-access-and-installation-of-teams-apps"></a>Teams アプリのアクセスとインストールを管理するためのポリシーについて知る

Microsoft Teams では、アプリ ポリシーを使用して、アプリのアクセスとインストールの動作を管理します。 アプリ ポリシーは、Teams 管理者が次のアプリの動作を制御するのに役立ちます。

* 個々のユーザーまたはユーザーのグループに対してアプリのアクセスを構成します。 これにより、エンド ユーザーごとに許可されるアプリを管理者が制御できます。

* 組織のニーズに関連するエンド ユーザー向けにこれらのアプリをピン留めします。 また、管理者は、ユーザーの介入なしにエンド ユーザー用のアプリをインストールできます。 エンドユーザーが関連するアプリを簡単に使い始めることができます。

* 管理者の承認のためにカスタム アプリを送信できる組織内の開発者を制御します。 カスタム アプリのアップロード機能へのアクセスを制御するのに役立ちます。

## <a name="app-permission-policies"></a>アプリのアクセス許可ポリシー

アプリのアクセス許可ポリシーを使用すると、Teams 管理者は組織内の各ユーザーが使用できるアプリを制御します。 すべてのユーザーに対していくつかのアプリを許可したり、特定のユーザー グループに対していくつかのアプリを許可したり、特定のユーザーに対して特定のアプリを許可したりできます。 アプリのアクセス許可ポリシーは、組織全体の設定と連携して機能し、個々のアプリの状態を許可またはブロックします。

アプリのアクセス許可ポリシーは、 [Teams で使用できるすべての種類のアプリに](deploy-apps-microsoft-teams-landing-page.md)適用されます。 アプリのアクセス許可ポリシーを使用するシナリオの例を次に示します。

* 最初は一部のユーザーに、最終的にはすべてのユーザーにアプリを段階的にロールアウトします。
* 人事部のメンバーに対してのみ、採用と人材管理用のカスタム アプリを許可し、他のすべての組織ユーザーに対してブロックします。

:::image type="content" source="media/app-permission-policy-trimmed.png" alt-text="アプリのアクセス許可ポリシーのスクリーンショット。" lightbox="media/app-permission-policy.png":::

詳細については、 [アプリのアクセス許可ポリシーを管理する方法に関するページを](teams-app-permission-policies.md)参照してください。

## <a name="app-setup-policies"></a>アプリケーションの設定ポリシー

アプリセットアップ ポリシーを使用すると、Teams クライアントでユーザーが使用できるアプリの方法と場所を構成できます。 Teams クライアントのアプリ バーにピン留めするアプリを選択し、アプリを表示する順序を定義します。

アプリのピン留めまたはインストールは、組織内の目的のアプリの認識と導入を促進するのに役立ちます。 変更は、Web、デスクトップ、モバイル Teams クライアントに適用されます。

アプリセットアップ ポリシーを使用するシナリオの例を次に示します。

* 人事チームのメンバー向けにカスタム採用およびタレント管理アプリをピン留めします。
* 組織のユーザーのピン留めを使用して [、Core アプリ](deploy-apps-microsoft-teams-landing-page.md#core-apps) の順序を変更します。

:::image type="content" source="media/app-setup-policy-trimmed.png" alt-text="Teams 管理センターのアプリのセットアップ ポリシーのスクリーンショット。" lightbox="media/app-setup-policy.png":::

詳細については、 [アプリのセットアップ ポリシーを管理する方法に関するページを](teams-app-setup-policies.md)参照してください。

### <a name="option-to-upload-custom-apps"></a>カスタム アプリをアップロードするオプション

組織は、組織固有の要件に応じてカスタム アプリの作成を委託する場合があります。 組織内の開発者は、Teams の組織の内部ユーザー向けのカスタム アプリを構築、テスト、デプロイできます。 アプリセットアップ ポリシーを使用して、組織内でカスタム アプリをアップロードできるユーザーを制御します。 組織全体の設定を使用して、エンド ユーザーがカスタム アプリを使用できるようにします。 アクセス許可ポリシーを使用して、特定のエンド ユーザーのみがカスタム アプリを使用できるようにします。

:::image type="content" source="media/custom-app-policy-trimmed.png" alt-text="組織全体の設定パネルで組織内のカスタム アプリを許可する方法を示すスクリーンショット。" lightbox="media/custom-app-policy.png":::

詳細については、 [カスタム アプリのポリシーと設定を管理する方法に関するページを](teams-custom-app-policies-and-settings.md)参照してください。

## <a name="related-articles"></a>関連記事

* [ポリシーを使用して Teams を管理する](manage-teams-with-policies.md)
* [アプリのアクセス許可ポリシーを管理する](teams-app-permission-policies.md)
* [アプリのセットアップ ポリシーを管理する](teams-app-setup-policies.md)
* [カスタム アプリのポリシーと設定を管理する](teams-custom-app-policies-and-settings.md)
