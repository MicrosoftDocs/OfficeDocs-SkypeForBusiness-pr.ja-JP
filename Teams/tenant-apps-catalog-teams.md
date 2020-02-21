---
title: Microsoft Teams テナントアプリカタログでアプリを公開する
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: prem
audience: admin
description: Microsoft Teams テナントアプリカタログでアプリを公開するためのガイダンス。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.publishtenantapps
- ms.teamsadmincenter.apppolicies.publishtenantapps
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1f3d4f5937c766c1c4f6f54a6a38872e793a3825
ms.sourcegitcommit: 10046048a670b66d93e8ac3ba7c3ebc9c3c5fc2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2020
ms.locfileid: "42161616"
---
<a name="publish-apps-in-the-microsoft-teams-tenant-app-catalog"></a>Microsoft Teams テナントアプリカタログでアプリを公開する
=======================================================

Microsoft Teams テナントアプリカタログを使用して、基幹業務アプリケーションのテストと組織への配布を行うことができます。

Teams テナントアプリカタログを使用すると、組織専用に構築された基幹業務アプリケーションを配布することができ、重要なビジネス機能の実行に依存することになります。

組織のアプリを公開するには、グローバル管理者または teams サービスの管理者の役割を持つアカウントを使用して Teams クライアントにサインインし、次の手順を実行します。

## <a name="publish-an-app-in-the-tenant-app-catalog-from-the-teams-client"></a>Teams クライアントからテナントアプリカタログ内のアプリを公開する

> [!NOTE]
> 次の手順では、Teams クライアントを使用してアプリを公開する方法について説明します。 Microsoft Teams 管理センターの [アプリの**管理**] ページでアプリを公開することもできます。 詳細については、「 [Teams でアプリを管理](manage-apps.md)する」を参照してください。

### <a name="get-a-teams-app-package"></a>Teams アプリパッケージを取得する

Teams アプリパッケージは、 [Teams アプリ Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)を使用して作成されます。 アプリパッケージを取得したら、テナントアプリカタログに追加することができます。 組織内のすべてのユーザーがアプリカタログを表示できますが、グローバル管理者と teams サービス管理者のみが公開および管理できます。

### <a name="go-to-the-tenant-app-catalog"></a>テナントアプリカタログに移動する

Teams を起動し、グローバルまたは teams サービス管理者の資格情報を使用してサインインします。 アプリの左側にある [**アプリ**] を選択し、特定の組織に対応する新しいセクション (この例では、Contoso) を選びます。 組織内のユーザーは、カタログ内のアプリを表示して、メンバーになっているチームに対してアプリをインストールできます。

![アプリカタログが表示されている Teams App Store のスクリーンショット。](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-app-catalog"></a>テナントアプリカタログにアプリを追加する

1. [**アプリ**] ページで、[ > **Contoso の****カスタムアプリアップロードをアップロードする**] を選びます。

    ![アプリカタログが表示されている Teams App Store のスクリーンショット。](media/private-app-store-teams-image02.png)

    ( **[自分のアップロード] または [自分のチーム**] (*サイドローディング*と呼ばれます) を選択することもできます。 サイドローディングによって、アプリはチームまたは選択したチームのみが利用できるようになります。)

2. アプリパッケージに移動して選択し、[**開く**] をクリックします。

    ![アプリカタログが表示されている Teams App Store のスクリーンショット。](media/private-app-store-teams-image03.png)

テナントアプリカタログに戻ると、新しいエンタープライズアプリが表示されます。 このアプリカタログには、自分と組織のメンバーのみがアクセスできます。

### <a name="update-an-app-in-the-tenant-app-catalog"></a>テナントアプリカタログのアプリを更新する

1. テナントのアプリカタログで、[**..**.] を選びます。 更新するアプリの右上にあります。

2. 更新されたアプリパッケージに移動して選択し、[**開く**] をクリックします。

    ![アプリカタログが表示されている Teams App Store のスクリーンショット。](media/private-app-store-teams-image04.png)

アプリはバージョン2.0 に更新されます。 このメニューから会社全体のアプリを削除することもできます。

## <a name="use-the-microsoft-teams-admin-center-to-manage-the-tenant-app-catalog"></a>Microsoft Teams 管理センターを使用して、テナントアプリカタログを管理する

バグ修正が必要なアプリがある場合は、アプリのアクセス許可ポリシーでユーザーのアプリを一時的に無効にすることができます。

1. Microsoft Teams 管理センターの左のナビゲーションで、[**チームアプリ** > の**アクセス許可ポリシー**] に移動します。
2. 編集するアプリのアクセス許可ポリシーを選択し、[**編集**] をクリックします。
3. [**テナントアプリ**] で、[**特定のアプリをブロックし、他のアプリを許可**する] を選択し、ブロックするアプリを追加します。

アプリを無効にすると、ユーザーはアプリを完全に削除せずに、アプリとやり取りすることができなくなります。 これらのコントロールを使うと、組織のアプリを管理するときに、さらに柔軟性と制御ができます。

詳細については、「 [Teams でアプリのアクセス許可ポリシーを管理](teams-app-permission-policies.md)する」を参照してください。