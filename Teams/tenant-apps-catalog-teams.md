---
title: Microsoft Teams テナントアプリカタログでアプリを公開する
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/20/2019
ms.topic: article
ms.service: msteams
ms.reviewer: prem
description: Microsoft Teams テナントアプリカタログにアプリを公開するためのガイダンス。
localization_priority: Normal
search.appverid: MET150
f1keywords: ms.teamsadmincenter.apppolicies.publishtenantapps
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5d016fd1c341774115b9b68edafcc47a63e42b0d
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221326"
---
<a name="publish-apps-in-the-microsoft-teams-tenant-apps-catalog"></a>Microsoft Teams テナントアプリカタログでアプリを公開する
=======================================================

Microsoft Teams テナントのアプリカタログを使って、基幹業務アプリケーションのテストと組織への配布を行うことができます。

Teams テナントアプリカタログを使用すると、組織専用に構築された基幹業務アプリケーションを配布することができ、重要なビジネス機能の実行に依存することになります。

組織のアプリを公開するには、グローバル管理者の資格情報を使用してチームクライアントにサインインし、次の手順に従います。

## <a name="publish-an-app-in-the-tenant-apps-catalog-from-the-teams-client"></a>Teams クライアントからテナントアプリカタログ内のアプリを公開する

> [!NOTE]
> 組織のアプリを公開するには、グローバル管理者の資格情報を使用して Microsoft Teams クライアントにサインインしている必要があります。

### <a name="get-a-teams-app-package"></a>Teams アプリパッケージを取得する

Teams アプリパッケージは、 [Teams アプリ Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)を使用して作成されます。 アプリパッケージを取得したら、エンタープライズアプリカタログに追加することができます。 テナントのすべてのユーザーがアプリカタログを表示できますが、現時点では、グローバル管理者のみが公開と管理を行うことができます。 (最終的には、チームの管理者がこの操作を実行できるようになります)。

### <a name="go-to-the-tenant-apps-catalog"></a>テナントアプリカタログに移動します。

Microsoft Teams クライアントを起動して、グローバル管理者の資格情報を使用してサインインします。 Microsoft Teams ストアで、特定の組織に対応する新しいセクション (この例では Contoso) を選びます。 組織内のユーザーは、カタログ内のアプリを表示して、メンバーになっているチームに対してアプリをインストールできます。

![アプリカタログが表示されている Teams App Store のスクリーンショット。](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-apps-catalog"></a>テナントアプリカタログにアプリを追加する

1. ストアで、[ > **Contoso の****カスタムアプリアップロードのアップロード**] を選びます。

    ![アプリカタログが表示されている Teams App Store のスクリーンショット。](media/private-app-store-teams-image02.png)

    ( **[自分のアップロード] または [自分のチーム**] (*サイドローディング*と呼ばれます) を選択することもできます。 サイドローディングによって、アプリはチームまたは選択したチームのみが利用できるようになります。)

2. アプリパッケージに移動して選択し、[**開く**] をクリックします。

    ![アプリカタログが表示されている Teams App Store のスクリーンショット。](media/private-app-store-teams-image03.png)

テナントアプリカタログに戻ると、新しいエンタープライズアプリが表示されます。 このアプリカタログには、自分と組織のメンバーのみがアクセスできます。

### <a name="update-an-app-in-the-tenant-apps-catalog"></a>テナントアプリカタログのアプリを更新する

1. テナントアプリカタログで、[**..**.] を選びます。 更新するアプリの右上にあります。

2. 更新されたアプリパッケージに移動して選択し、[**開く**] をクリックします。

    ![アプリカタログが表示されている Teams App Store のスクリーンショット。](media/private-app-store-teams-image04.png)

アプリはバージョン2.0 に更新されます。 このメニューから会社全体のアプリを削除することもできます。

## <a name="use-the-office-365-admin-portal-to-manage-the-tenant-apps-catalog"></a>Office 365 管理ポータルを使用してテナントアプリカタログを管理する

バグ修正が必要なアプリがある場合は、Office 365 管理ポータルを通じてアプリを一時的に無効にすることができます。 [**設定** > **サービス & アドインの** > **Microsoft Teams**] を選択します。 以前の設定に加えて、お客様の会社のアプリ専用のセクションが追加されました。 有効または無効にするアプリを選ぶことができます。

![アプリカタログが表示されている Teams App Store のスクリーンショット。](media/private-app-store-teams-image05.png)

アプリを無効にすると、アプリを完全に削除せずに、ユーザーがアプリを操作できなくなります。 これらのコントロールを使用すると、企業でアプリを管理するときの柔軟性と制御がさらに向上します。
