---
title: カスタム アプリとサイドロードされたアプリの管理
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Microsoft Teams のカスタム アプリとサイドロード アプリとは何かを理解し、アプリを管理して、その動作、ロールアウト、およびアクセス許可を管理します。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: 4ba559d605f1465fda7caf9b253c18864c8b4c20
ms.sourcegitcommit: ceba5fd8f098c8d0eafaffe5c5301c845a3ae7ab
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2022
ms.locfileid: "67837377"
---
# <a name="understand-and-manage-custom-and-sideloaded-apps"></a>カスタム アプリとサイドロードされたアプリの理解と管理

Microsoft Teams を使用すると、組織内の開発者は、組織の内部ユーザー向けのカスタム アプリを構築、テスト、展開できます。 このようなアプリは、カスタム アプリまたは基幹業務アプリと呼ばれます。 組織は、組織固有の要件に応じてカスタム アプリの作成を委託する場合があります。

管理者は、組織全体または特定のユーザーに対してそのようなアプリを許可またはブロックすることができます。 組織内の開発者は、Teams と [Microsoft Power Platform](/microsoftteams/platform/samples/teams-low-code-solutions) の統合を使用して、カスタムのローコード ソリューションを構築できます。

開発者は、Teams を介してカスタム アプリを送信し、管理者の承認を得ることができます。 アプリ セットアップ ポリシーを使用して、カスタム アプリのロールアウト、配布、およびアクセス許可を制御できます。

:::image type="content" source="media/custom-app-policy-trimmed.png" alt-text="組織全体の設定パネルで組織内のカスタム アプリを許可する方法を示すスクリーンショット。" lightbox="media/custom-app-policy.png":::

カスタム アプリの使用を許可すると、エンド ユーザーは、Teams ストアの左側のナビゲーションで **[組織向けに開発]** を選択して、それを見つけることができます。

:::image type="content" source="media/built-for-your-org1.png" alt-text="Teams デスクトップ アプリの Teams ストアにあるカスタム アプリのスクリーンショット。" lightbox="media/built-for-your-org2.png":::

## <a name="understand-sideloading-of-custom-apps"></a>カスタム アプリのサイドローディングを理解する

カスタム アプリを開発し、それらのアプリをエンド ユーザーに配布する前に、開発者はテストするために Teams ストアにアプリを追加してアプリをテストします。 開発者は自分自身で、または指定されたユーザー グループでテストできますが、組織内の他のエンド ユーザーがストア経由でアプリを利用することはできません。 この方法は、アプリのサイドローディングと呼ばれ、カスタム アプリにのみ適用されます。

開発者は、通常は開発中のアプリをテストするために、特定のチームのメンバーがアプリを利用できるようにアプリをサイドロードできます。 この方法でのアプリの使用はアプリ開発者に制限され、管理者が Teams でのサイドローディングを許可している限り、管理者の承認は必要ありません。

開発者は、サイドロードされたアプリを Teams アプリ カタログに送信せずに、特定のチームと共有できます。 これにより、サイドロードされたカスタム アプリは、エンド ユーザーの限定されたグループで使用できますが、組織のアプリ ストアではすべてのエンド ユーザーが使用できなくなります。

管理者は、すべての開発者に対してアプリのサイドローディングを禁止できます。 サイドローディングを禁止した場合でも、開発者は[別のテスト テナントを作成](/microsoftteams/platform/concepts/build-and-test/prepare-your-o365-tenant)してアプリをテストできます。 カスタム アプリの開発が完了すると、開発者はカスタム アプリをエンド ユーザーに配布するよう管理者に要求します。 詳細については、[カスタム アプリを発行する方法](/microsoftteams/upload-custom-apps)を参照してください。 管理者であるお客様は、特定のユーザーに対してカスタム アプリの使用を許可または禁止できます。

## <a name="allow-developers-to-upload-custom-apps"></a>開発者がカスタム アプリをアップロードできるようにする

カスタム ポリシーを作成するか、グローバル ポリシーを編集して、組織のニーズに基づいてカスタム アプリを許可またはブロックできます。 組織の開発者がカスタム アプリをアップロードできるようにするカスタム ポリシーを作成するには、次の手順を実行します。

1. Teams 管理センターにサインインし、**[Teams アプリ]** > **[[セットアップ ポリシー]](https://admin.teams.microsoft.com/policies/app-setup)** の順にアクセスします。

1. **[追加]** を選択します。

1. ポリシーの名前と説明を入力します。

1. **[カスタム アプリのアップロード]** を有効/無効にします。

> [!NOTE]
> この設定を変更するには、テナントの [[組織全体のアプリ設定]](manage-apps.md#manage-org-wide-app-settings) でサードパーティ アプリを許可します。

## <a name="related-articles"></a>関連記事

* [Teams のカスタム アプリのポリシーと設定を管理する](teams-custom-app-policies-and-settings.md)
* [アプリを管理するポリシーを理解する](app-policies.md)
* [Microsoft Teams のサード パーティ製アプリについて](overview-third-party-apps.md)
