---
title: Microsoft Teams テナントアプリカタログでアプリを公開する
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/20/2019
ms.topic: article
ms.service: msteams
ms.reviewer: prem
audience: admin
description: Microsoft Teams テナントアプリカタログにアプリを公開するためのガイダンス。
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
ms.openlocfilehash: c1b2fb38dcca7142cad82d290b1225e69f035bae
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836917"
---
<a name="publish-apps-in-the-microsoft-teams-tenant-apps-catalog"></a>Microsoft Teams テナントアプリカタログでアプリを公開する
=======================================================

Microsoft Teams テナントのアプリカタログを使って、基幹業務アプリケーションのテストと組織への配布を行うことができます。

Teams テナントアプリカタログを使用すると、組織専用に構築された基幹業務アプリケーションを配布することができ、重要なビジネス機能の実行に依存することになります。

組織のアプリを公開するには、グローバル管理者または teams サービスの管理者ロールを持つアカウントを使用してチームクライアントにサインインし、次の手順に従います。

## <a name="publish-an-app-in-the-tenant-apps-catalog-from-the-teams-client"></a>Teams クライアントからテナントアプリカタログ内のアプリを公開する

> [!NOTE]
> 組織のアプリを公開するには、グローバル管理者または Teams サービスの管理者ロールが有効になっているアカウントを使用して、Microsoft Teams クライアントにサインインする必要があります。 [管理者ロールを使用してチームを管理する](https://docs.microsoft.com/MicrosoftTeams/using-admin-roles)方法について、詳細はこちらをご覧ください。

### <a name="get-a-teams-app-package"></a>Teams アプリパッケージを取得する

Teams アプリパッケージは、 [Teams アプリ Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)を使用して作成されます。 アプリパッケージを取得したら、エンタープライズアプリカタログに追加することができます。 テナントのすべてのユーザーがアプリカタログを表示できますが、グローバル管理者と teams サービス管理者だけが公開および管理できます。

### <a name="go-to-the-tenant-apps-catalog"></a>テナントアプリカタログに移動します。

Microsoft Teams クライアントを起動し、グローバルまたは Teams サービス管理者の資格情報を使用してサインインします。 アプリの左側にある [**アプリ**] を選択し、特定の組織に対応する新しいセクション (この例では、Contoso) を選びます。 組織内のユーザーは、カタログ内のアプリを表示して、メンバーになっているチームに対してアプリをインストールできます。

![アプリカタログが表示されている Teams App Store のスクリーンショット。](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-apps-catalog"></a>テナントアプリカタログにアプリを追加する

1. [**アプリ**] ページで、[ > **Contoso の****カスタムアプリアップロードをアップロードする**] を選びます。

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

バグの修正が必要なアプリがある場合は、Microsoft 365 管理** > <>** > **** > センターを使用**して、** アプリを一時的に無効にすることができます。たとえば、"グローバル (組織全体の既定)" という > の**テナント > アプリ**は、特定のアプリをブロックし、他のユーザーをブロックして、アプリをリストに追加することができます。

![アプリカタログが表示されている Teams App Store のスクリーンショット。](media/private-app-store-teams-image05.png)

アプリを無効にすると、アプリを完全に削除せずに、ユーザーがアプリを操作できなくなります。 これらのコントロールを使用すると、企業でアプリを管理するときの柔軟性と制御がさらに向上します。
