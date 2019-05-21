---
title: Microsoft Teams テナント アプリ カタログにアプリを公開する
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/15/2019
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
ms.openlocfilehash: ebc26292e41328589f302127980f4a303efd46a2
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32226712"
---
<a name="publish-apps-to-the-microsoft-teams-tenant-apps-catalog"></a>Microsoft Teams テナント アプリ カタログにアプリを公開する
=======================================================

Microsoft Teams テナントのアプリカタログを使って、基幹業務アプリケーションのテストと組織への配布を行うことができます。 

Teams テナントアプリカタログを使うと、組織専用に構築された基幹業務アプリケーションを配布できます。また、重要なビジネス機能をユーザーに対して実行することに依存します。 
 
グローバル管理者の資格情報を使用してチームクライアントにサインインし、組織のアプリを公開します。 

## <a name="publish-an-app-to-the-tenant-apps-catalog-from-the-teams-client"></a>Teams クライアントからテナントアプリカタログにアプリを発行する

注: 組織のアプリを公開するには、グローバル管理者の資格情報を使用して Microsoft Teams クライアントにサインインしている必要があります。

### <a name="get-a-teams-app-package"></a>Teams アプリパッケージを取得する

Teams アプリパッケージは、 [Teams アプリ Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)を使用して作成されます。 アプリパッケージを取得したら、エンタープライズアプリカタログに追加することができます。 テナントのすべてのユーザーがアプリカタログを表示できますが、現時点では、グローバル管理者のみが公開と管理を行うことができます。 (最終的には、チームの管理者がこの操作を実行できるようになります)。

### <a name="go-to-the-tenant-apps-catalog"></a>テナントアプリカタログに移動します。

Microsoft Teams クライアントを起動して、グローバル管理者の資格情報を使用してサインインします。 Microsoft Teams ストアで、特定の組織に対応する新しいセクション (この例では Contoso) を選びます。 組織内のユーザーは、カタログ内のアプリを表示して、メンバーになっているチームにインストールすることができます。 

![アプリカタログが表示されている Teams App Store のスクリーンショット。](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-apps-catalog"></a>テナントアプリカタログにアプリを追加する

ストアで、[ > **Contoso の****カスタムアプリアップロードのアップロード**] を選びます。

![アプリカタログが表示されている Teams App Store のスクリーンショット。](media/private-app-store-teams-image02.png)

([**自分のアップロード] または [自分のチーム**(サイドローディングと呼ばれる)] を選択して、アプリを自分または選択したチームのみが利用できるようにすることもできます。) 

アプリパッケージに移動して選択します。

![アプリカタログが表示されている Teams App Store のスクリーンショット。](media/private-app-store-teams-image03.png)

テナントアプリカタログに戻ると、新しいエンタープライズアプリが表示されます。 このアプリカタログには、自分と組織のメンバーのみがアクセスできます。

### <a name="update-an-app-in-the-tenant-apps-catalog"></a>テナントアプリカタログのアプリを更新する

1. テナントアプリカタログで、[**..**.] を選びます。 更新するアプリの右上にあります。
2. 更新されたアプリパッケージに移動し、それを選択します。

![アプリカタログが表示されている Teams App Store のスクリーンショット。](media/private-app-store-teams-image04.png)

アプリはバージョン2.0 に更新されます。 このメニューから会社全体のアプリを削除することもできます。

## <a name="use-the-office-365-admin-portal-to-manage-the-tenant-apps-catalog"></a>Office 365 管理ポータルを使用してテナントアプリカタログを管理する

バグの修正が必要なアプリがある場合は、Office 365 管理ポータルを使用してアプリを一時的に無効にすることができます。 [**設定** > **サービス & アドイン** > の**Microsoft Teams**] を選択します。 以前の設定に加えて、お客様の会社のアプリ専用のセクションが追加されました。 有効または無効にするアプリを選ぶことができます。

![アプリカタログが表示されている Teams App Store のスクリーンショット。](media/private-app-store-teams-image05.png)

これにより、ユーザーはアプリを完全に削除せずに、アプリとやり取りすることができなくなります。 これらのコントロールを使うと、管理者は、企業のアプリのガバナンスをさらに柔軟に管理できます。 


