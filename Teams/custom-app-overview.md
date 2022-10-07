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
ms.date: 09/25/2022
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
ms.openlocfilehash: 42c970f3b354ac1f5b490359f0df9bcc01e97019
ms.sourcegitcommit: d6e180791134426445a35fd485dcca18bde2006b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2022
ms.locfileid: "68494770"
---
# <a name="understand-and-manage-custom-and-sideloaded-apps"></a>カスタム アプリとサイドロードされたアプリの理解と管理

Microsoft Teams を使用すると、組織内の開発者は、組織の内部ユーザー向けのカスタム アプリを構築、テスト、展開できます。 このようなアプリは、カスタム アプリまたは基幹業務アプリと呼ばれます。 組織は、組織固有の要件に応じてカスタム アプリの作成を委託する場合があります。 管理者は、さまざまな設定とポリシーを使用して、カスタム アプリのロールアウトとアクセス許可を制御します。

:::image type="content" source="media/custom-app-orgwide-setting-trimmed.png" alt-text="組織全体の設定パネルで組織内のカスタム アプリを許可する方法を示すスクリーンショット。" lightbox="media/custom-app-orgwide-setting.png":::

カスタム アプリの使用を許可すると、エンド ユーザーは、Teams ストアの左側のナビゲーションで **[組織向けに開発]** を選択して、それを見つけることができます。

:::image type="content" source="media/built-for-your-org1.png" alt-text="Teams デスクトップ アプリの Teams ストアにあるカスタム アプリのスクリーンショット。" lightbox="media/built-for-your-org2.png":::

## <a name="understand-sideloading-of-custom-apps"></a>カスタム アプリのサイドローディングを理解する

カスタム アプリを開発し、それらのアプリをエンド ユーザーに配布する前に、開発者はテストするために Teams ストアにアプリを追加してアプリをテストします。 開発者は、自分でテストすることも、指定したユーザー のグループでテストすることもできますが、アプリはストア経由で組織内の他のエンド ユーザーが利用することはできません。 この方法は、アプリのサイドローディングと呼ばれ、カスタム アプリにのみ適用されます。

開発者は、通常は開発中のアプリをテストするために、特定のチームのメンバーがアプリを利用できるようにアプリをサイドロードできます。 この方法でのアプリの使用はアプリ開発者に制限され、管理者が Teams でのサイドローディングを許可している限り、管理者の承認は必要ありません。

開発者は、サイドロードされたアプリを Teams アプリ カタログに送信せずに、特定のチームと共有できます。 これにより、サイドロードされたカスタム アプリは、エンド ユーザーの限定されたグループで使用できますが、組織のアプリ ストアではすべてのエンド ユーザーが使用できなくなります。

管理者は、すべての開発者に対してアプリのサイドローディングを禁止できます。 サイドローディングを禁止した場合でも、開発者は[別のテスト テナントを作成](/microsoftteams/platform/concepts/build-and-test/prepare-your-o365-tenant)してアプリをテストできます。 カスタム アプリの開発が完了すると、開発者はカスタム アプリをエンド ユーザーに配布するよう管理者に要求します。 詳細については、[カスタム アプリを発行する方法](/microsoftteams/upload-custom-apps)を参照してください。 管理者は、すべてのユーザーまたは特定のユーザーに対してカスタム アプリの使用を許可 (またはブロック) します。

## <a name="allow-developers-to-upload-custom-apps"></a>開発者がカスタム アプリをアップロードできるようにする

アプリセットアップ ポリシーでは、カスタム ポリシーを作成するか、グローバル ポリシーを編集してカスタム アプリのアップロードを許可できます。 カスタム ポリシーを作成し、特定のユーザーに適用するには、次の手順に従います。

1. Teams 管理センターにサインインし、**[Teams アプリ]** > **[[セットアップ ポリシー]](https://admin.teams.microsoft.com/policies/app-setup)** の順にアクセスします。
1. **[追加]** を選択します。
1. ポリシーの名前と説明を入力します。
1. **[カスタム アプリのアップロード]** を有効/無効にします。
1. カスタム アプリを開発し、それらのアプリのアップロードを許可されている[ユーザーにポリシーを適用](assign-policies-users-and-groups.md#assign-a-policy-to-individual-users)します。

> [!NOTE]
> この設定を変更するには、組織全体のアプリ設定でカスタム アプリを許可 [します](manage-apps.md#manage-org-wide-app-settings)。

## <a name="related-articles"></a>関連記事

* [カスタム アプリのポリシーと設定を管理する](teams-custom-app-policies-and-settings.md)
* [アプリを管理するポリシーを理解する](app-policies.md)
* [Microsoft Teams のサード パーティ製アプリについて](overview-third-party-apps.md)
