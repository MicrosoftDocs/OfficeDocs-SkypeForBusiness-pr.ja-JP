---
title: Teams でアプリを管理するためのアプリ ポリシーの概要
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: conceptual
ms.service: msteams
ms.subservice: teams-apps
search.appverid: ''
description: Microsoft Teams でアプリを管理するために使用するアプリのアクセス許可ポリシー、アプリのセットアップ ポリシー、およびカスタム アプリ ポリシーについて説明します。
audience: admin
ms.localizationpriority: high
appliesto:
- Microsoft Teams
ms.collection:
- M365-collaboration
ms.openlocfilehash: ad7e99d10ebf53c7a85394edda84061f6caf0d29
ms.sourcegitcommit: ceba5fd8f098c8d0eafaffe5c5301c845a3ae7ab
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2022
ms.locfileid: "67837567"
---
# <a name="overview-of-app-policies-used-to-manage-access-to-apps"></a>アプリへのアクセスを管理するために使用されるアプリ ポリシーの概要

Microsoft Teams では、ポリシーを使用してアクセスとインストールの動作を管理します。 ポリシーは、Teams 管理者が次のアプリの動作を制御するのに役立ちます。

* ユーザーのアプリへのアクセスをきめ細かなレベルで構成します。 これは、各エンド ユーザーが管理者が許可したアプリのみを使用するのに役立ちます。

* 特定のユーザーに関連するアプリをピン留めします。 ピン留めされたアプリは介入なしで自動インストールされるため、エンド ユーザーは簡単に起動し、関連するアプリにすばやくアクセスできます。

## <a name="app-permission-policies"></a>アプリのアクセス許可ポリシー

Teams 管理者は、アプリのアクセス許可ポリシーを使用して、組織内の特定のユーザーが利用できるアプリを制御できます。 アプリとユーザーの間の正確なアクセス マッピング、またはその両方の任意の組み合わせを定義できます。 たとえば、すべてのユーザーに対していくつかのアプリを許可したり、特定のユーザー グループに対していくつかのアプリを許可したり、特定のユーザーに対して特定のアプリを許可したりできます。

アプリのアクセス許可ポリシーは、Teams で使用可能なすべての種類のアプリに適用されます。 たとえば、アプリのアクセス許可ポリシーを使用して、特定のユーザーに対して許可することで、サードパーティのアプリまたはカスタム アプリを段階的にロールアウトできます。

:::image type="content" source="media/app-permission-policy-trimmed.png" alt-text="アプリのアクセス許可ポリシーのスクリーンショット。" lightbox="media/app-permission-policy.png":::

詳細については、 [カスタム アプリのポリシーと設定を管理する方法について説明します](teams-app-permission-policies.md)。

## <a name="app-setup-policies"></a>アプリケーションの設定ポリシー

アプリケーションの設定ポリシーで、ユーザーのアプリでの操作をカスタマイズできます。 Teams クライアントのアプリ バーに固定するアプリと、アプリが Web、デスクトップ、モバイル クライアントに表示される順序を選択します。

アプリの設定ポリシーの活用例は以下のとおりです。

* エンド ユーザー向けのアプリを個人の Teams 環境にインストールします。 これは、目的のアプリの認識と導入を促進するのに役立ちます。 たとえば、人事チームのメンバー用にカスタムの採用およびタレント管理アプリをピン留めします。
* チャット、Teams、通話などのコア アプリを選択的にピン留めします。

:::image type="content" source="media/app-setup-policy-trimmed.png" alt-text="Teams 管理センターのアプリのセットアップ ポリシーのスクリーンショット。" lightbox="media/app-setup-policy.png":::

詳細については、 [アプリのセットアップ ポリシーを管理する方法に関する](teams-app-setup-policies.md)ページを参照してください。

## <a name="custom-app-policies"></a>カスタム アプリ ポリシー

Teams を使用すると、組織内の開発者は、組織の内部ユーザー向けのカスタム アプリを構築、テスト、デプロイできます。 開発者は、Teams 管理者からの承認を得て、Teams 経由でカスタム アプリを送信できます。 組織でカスタム アプリをアップロードできる人物を管理するアプリの設定ポリシーを使用できます。 管理者は、組織全体のアプリ設定を使用して、組織のエンド ユーザーがカスタム アプリと開発者を使用してカスタム アプリをアップロードすることを許可できます。

:::image type="content" source="media/custom-app-policy-trimmed.png" alt-text="組織全体の設定パネルで組織内のカスタム アプリを許可する方法を示すスクリーンショット。" lightbox="media/custom-app-policy.png":::

詳細については、 [カスタム アプリのポリシーと設定を管理する方法に関するページを](teams-custom-app-policies-and-settings.md)参照してください。

## <a name="related-articles"></a>関連記事

* [ポリシーを使用して Teams を管理する](manage-teams-with-policies.md)
